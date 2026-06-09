# SiBootEntryGetNtFilePath

- ea: `0x14001dbe0`
- end: `0x14001dc97`
- name: `SiBootEntryGetNtFilePath`
- size: `183`
- prototype: `__int64 __fastcall(__int64, struct _FILE_PATH **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14001df18`

## callees

- `0x14001dbe0`

## import_xrefs

- `ntdll!NtTranslateFilePath` at `0x14001dc16`
- `ntdll!NtTranslateFilePath` at `0x14001dc5e`
- `ntdll!NtTranslateFilePath` at `0x14001dc16`
- `ntdll!NtTranslateFilePath` at `0x14001dc5e`
- `ntdll!RtlAllocateHeap` at `0x14001dc39`
- `ntdll!RtlAllocateHeap` at `0x14001dc39`
- `ntdll!RtlFreeHeap` at `0x14001dc86`
- `ntdll!RtlFreeHeap` at `0x14001dc86`

## pseudocode

```c
__int64 __fastcall SiBootEntryGetNtFilePath(__int64 a1, struct _FILE_PATH **a2)
{
  NTSTATUS v3; // ebx
  struct _FILE_PATH *v4; // rdi
  struct _FILE_PATH *v5; // rbp
  struct _FILE_PATH *Heap; // rax
  ULONG OutputFilePathLength; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 20) )
  {
    v4 = 0;
    v5 = (struct _FILE_PATH *)(a1 + *(unsigned int *)(a1 + 20));
    OutputFilePathLength = 0;
    v3 = NtTranslateFilePath(v5, 3u, 0, (ULONG)&OutputFilePathLength);
    if ( v3 == -1073741789 )
    {
      Heap = (struct _FILE_PATH *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, OutputFilePathLength);
      v4 = Heap;
      if ( !Heap )
        return (unsigned int)-1073741801;
      v3 = NtTranslateFilePath(v5, 3u, Heap, (ULONG)&OutputFilePathLength);
    }
    if ( v3 < 0 )
    {
      if ( v4 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    }
    else
    {
      *a2 = v4;
    }
  }
  else
  {
    return (unsigned int)-1073741275;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001dbe0  push    rbx
0x14001dbe2  push    rbp
0x14001dbe3  push    rsi
0x14001dbe4  push    rdi
0x14001dbe5  sub     rsp, 28h
0x14001dbe9  cmp     dword ptr [rcx+14h], 0
0x14001dbed  mov     rsi, rdx
0x14001dbf0  jnz     short loc_14001DBFC
0x14001dbf2  mov     ebx, 0C0000225h
0x14001dbf7  jmp     loc_14001DC8C
0x14001dbfc  mov     ebp, [rcx+14h]
0x14001dbff  lea     r9, [rsp+48h+OutputFilePathLength]; OutputFilePathLength
0x14001dc04  xor     edi, edi
0x14001dc06  add     rbp, rcx
0x14001dc09  xor     r8d, r8d; OutputFilePath
0x14001dc0c  mov     [rsp+48h+OutputFilePathLength], edi
0x14001dc10  mov     rcx, rbp; InputFilePath
0x14001dc13  lea     edx, [rdi+3]; OutputType
0x14001dc16  call    cs:__imp_NtTranslateFilePath
0x14001dc1c  mov     ebx, eax
0x14001dc1e  cmp     eax, 0C0000023h
0x14001dc23  jnz     short loc_14001DC66
0x14001dc25  mov     rcx, gs:60h
0x14001dc2e  xor     edx, edx; Flags
0x14001dc30  mov     r8d, [rsp+48h+OutputFilePathLength]; Size
0x14001dc35  mov     rcx, [rcx+30h]; HeapHandle
0x14001dc39  call    cs:__imp_RtlAllocateHeap
0x14001dc3f  mov     rdi, rax
0x14001dc42  test    rax, rax
0x14001dc45  jnz     short loc_14001DC4E
0x14001dc47  mov     ebx, 0C0000017h
0x14001dc4c  jmp     short loc_14001DC8C
0x14001dc4e  lea     r9, [rsp+48h+OutputFilePathLength]; OutputFilePathLength
0x14001dc53  mov     r8, rax; OutputFilePath
0x14001dc56  mov     edx, 3; OutputType
0x14001dc5b  mov     rcx, rbp; InputFilePath
0x14001dc5e  call    cs:__imp_NtTranslateFilePath
0x14001dc64  mov     ebx, eax
0x14001dc66  test    ebx, ebx
0x14001dc68  js      short loc_14001DC6F
0x14001dc6a  mov     [rsi], rdi
0x14001dc6d  jmp     short loc_14001DC8C
0x14001dc6f  test    rdi, rdi
0x14001dc72  jz      short loc_14001DC8C
0x14001dc74  mov     rcx, gs:60h
0x14001dc7d  mov     r8, rdi; P
0x14001dc80  xor     edx, edx; Flags
0x14001dc82  mov     rcx, [rcx+30h]; HeapHandle
0x14001dc86  call    cs:__imp_RtlFreeHeap
0x14001dc8c  mov     eax, ebx
0x14001dc8e  add     rsp, 28h
0x14001dc92  pop     rdi
0x14001dc93  pop     rsi
0x14001dc94  pop     rbp
0x14001dc95  pop     rbx
0x14001dc96  retn
```
