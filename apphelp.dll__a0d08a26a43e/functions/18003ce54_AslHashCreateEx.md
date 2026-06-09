# AslHashCreateEx

- ea: `0x18003ce54`
- end: `0x18003cf78`
- name: `AslHashCreateEx`
- size: `292`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003ce10`

## callees

- `0x18000f114`
- `0x1800260e0`
- `0x18003ce54`
- `0x18003cf80`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18003ceae`
- `ntdll!RtlAllocateHeap` at `0x18003cf3f`
- `ntdll!RtlAllocateHeap` at `0x18003ceae`
- `ntdll!RtlAllocateHeap` at `0x18003cf3f`

## string_xrefs

- `0x18003ce82`: `AslHashCreateEx`
- `0x18003cecc`: `AslHashCreateEx`
- `0x18003cf0f`: `AslHashCreateEx`

## pseudocode

```c
__int64 __fastcall AslHashCreateEx(_QWORD *a1)
{
  _DWORD *Heap; // rax
  _DWORD *v4; // rdi
  __int64 v5; // r8
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // r9d
  PVOID v9; // rax
  SIZE_T Size; // [rsp+40h] [rbp+8h] BYREF

  Size = 0;
  if ( !a1 )
  {
    AslLogCallPrintf(1, "AslHashCreateEx", 73, "Invalid parameter");
    return 3221225485LL;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
  v4 = Heap;
  if ( Heap )
  {
    *Heap = 8147;
    v7 = RtlULongLongMult(8, 8147, &Size);
    v6 = v7;
    if ( v7 < 0 )
    {
      AslLogCallPrintf(1, "AslHashCreateEx", 88, "RtlSIZETMult failed for Size = %d [%x]", v8, v7);
      goto LABEL_11;
    }
    v9 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Size);
    *((_QWORD *)v4 + 1) = v9;
    if ( v9 )
    {
      *a1 = v4;
      v4 = 0;
      v6 = 0;
      goto LABEL_11;
    }
    v5 = 95;
  }
  else
  {
    v5 = 80;
  }
  v6 = -1073741801;
  AslLogCallPrintf(1, "AslHashCreateEx", v5, "Out of memory");
LABEL_11:
  AslHashFree(v4);
  return v6;
}

```

## disassembly

```asm
0x18003ce54  mov     [rsp+arg_8], rbx
0x18003ce59  mov     [rsp+arg_10], rsi
0x18003ce5e  push    rdi
0x18003ce5f  sub     rsp, 30h
0x18003ce63  mov     [rsp+38h+Size], 0
0x18003ce6c  mov     rsi, rcx
0x18003ce6f  test    rcx, rcx
0x18003ce72  jnz     short loc_18003CE98
0x18003ce74  lea     r8d, [rcx+49h]
0x18003ce78  lea     ecx, [rsi+1]
0x18003ce7b  lea     r9, aInvalidParamet_1; "Invalid parameter"
0x18003ce82  lea     rdx, aAslhashcreatee; "AslHashCreateEx"
0x18003ce89  call    AslLogCallPrintf
0x18003ce8e  mov     eax, 0C000000Dh
0x18003ce93  jmp     loc_18003CF68
0x18003ce98  mov     rcx, gs:60h
0x18003cea1  mov     edx, 8; Flags
0x18003cea6  mov     rcx, [rcx+30h]; HeapHandle
0x18003ceaa  lea     r8d, [rdx+8]; Size
0x18003ceae  call    cs:__imp_RtlAllocateHeap
0x18003ceb4  mov     rdi, rax
0x18003ceb7  test    rax, rax
0x18003ceba  jnz     short loc_18003CEDF
0x18003cebc  lea     r8d, [rax+50h]
0x18003cec0  lea     r9, aOutOfMemory; "Out of memory"
0x18003cec7  mov     ecx, 1
0x18003cecc  lea     rdx, aAslhashcreatee; "AslHashCreateEx"
0x18003ced3  mov     ebx, 0C0000017h
0x18003ced8  call    AslLogCallPrintf
0x18003cedd  jmp     short loc_18003CF5E
0x18003cedf  mov     r9d, 1FD3h
0x18003cee5  lea     r8, [rsp+38h+Size]
0x18003ceea  mov     edx, r9d
0x18003ceed  mov     [rax], r9d
0x18003cef0  mov     ecx, 8
0x18003cef5  call    RtlULongLongMult
0x18003cefa  mov     ebx, eax
0x18003cefc  test    eax, eax
0x18003cefe  jns     short loc_18003CF28
0x18003cf00  mov     r8d, 58h ; 'X'
0x18003cf06  mov     [rsp+38h+var_10], eax
0x18003cf0a  mov     [rsp+38h+var_18], r9d
0x18003cf0f  lea     rdx, aAslhashcreatee; "AslHashCreateEx"
0x18003cf16  lea     r9, aRtlsizetmultFa; "RtlSIZETMult failed for Size = %d [%x]"
0x18003cf1d  lea     ecx, [r8-57h]
0x18003cf21  call    AslLogCallPrintf
0x18003cf26  jmp     short loc_18003CF5E
0x18003cf28  mov     rcx, gs:60h
0x18003cf31  mov     edx, 8; Flags
0x18003cf36  mov     r8, [rsp+38h+Size]; Size
0x18003cf3b  mov     rcx, [rcx+30h]; HeapHandle
0x18003cf3f  call    cs:__imp_RtlAllocateHeap
0x18003cf45  mov     [rdi+8], rax
0x18003cf49  test    rax, rax
0x18003cf4c  jnz     short loc_18003CF57
0x18003cf4e  lea     r8d, [rax+5Fh]
0x18003cf52  jmp     loc_18003CEC0
0x18003cf57  mov     [rsi], rdi
0x18003cf5a  xor     edi, edi
0x18003cf5c  xor     ebx, ebx
0x18003cf5e  mov     rcx, rdi
0x18003cf61  call    AslHashFree
0x18003cf66  mov     eax, ebx
0x18003cf68  mov     rbx, [rsp+38h+arg_8]
0x18003cf6d  mov     rsi, [rsp+38h+arg_10]
0x18003cf72  add     rsp, 30h
0x18003cf76  pop     rdi
0x18003cf77  retn
```
