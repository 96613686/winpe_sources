# SyspartEnumerateDisks

- ea: `0x140020ba4`
- end: `0x140020dd0`
- name: `SyspartEnumerateDisks`
- size: `556`
- prototype: `__int64 __fastcall(unsigned __int8 (__fastcall *)(wchar_t *, _QWORD, __int64), __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400171b4`
- `0x14001dd64`
- `0x140020e68`

## callees

- `0x140020ae8`
- `0x140020ba4`
- `0x140027010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x140020d6d`
- `msvcrt!swprintf_s` at `0x140020d6d`
- `ntdll!NtOpenDirectoryObject` at `0x140020c29`
- `ntdll!NtOpenDirectoryObject` at `0x140020c29`
- `ntdll!NtQueryDirectoryObject` at `0x140020c6b`
- `ntdll!NtQueryDirectoryObject` at `0x140020c6b`
- `ntdll!RtlAllocateHeap` at `0x140020ca7`
- `ntdll!RtlAllocateHeap` at `0x140020d1f`
- `ntdll!RtlAllocateHeap` at `0x140020ca7`
- `ntdll!RtlAllocateHeap` at `0x140020d1f`
- `ntdll!RtlFreeHeap` at `0x140020c8c`
- `ntdll!RtlFreeHeap` at `0x140020da4`
- `ntdll!RtlFreeHeap` at `0x140020dc5`
- `ntdll!RtlFreeHeap` at `0x140020c8c`
- `ntdll!RtlFreeHeap` at `0x140020da4`
- `ntdll!RtlFreeHeap` at `0x140020dc5`
- `ntdll!NtClose` at `0x140020cc3`
- `ntdll!NtClose` at `0x140020cea`
- `ntdll!NtClose` at `0x140020cc3`
- `ntdll!NtClose` at `0x140020cea`
- `ntdll!RtlInitUnicodeString` at `0x140020bf5`
- `ntdll!RtlInitUnicodeString` at `0x140020bf5`

## pseudocode

```c
__int64 __fastcall SyspartEnumerateDisks(unsigned __int8 (__fastcall *a1)(wchar_t *, _QWORD, __int64), __int64 a2)
{
  NTSTATUS v4; // ebx
  ULONG v5; // esi
  SIZE_T i; // r8
  _WORD *Heap; // rdi
  wchar_t *v9; // r14
  wchar_t **v10; // rsi
  void *FileHandle; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-11h] BYREF
  unsigned int v14; // [rsp+E0h] [rbp+77h] BYREF
  ULONG Context; // [rsp+E8h] [rbp+7Fh] BYREF

  Context = 0;
  v14 = 0;
  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenDirectoryObject(&FileHandle, 1u, &ObjectAttributes);
  if ( v4 >= 0 )
  {
    v5 = 4096;
    for ( i = 4096; ; i = v5 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, i);
      if ( !Heap )
      {
        v4 = -1073741801;
        goto LABEL_7;
      }
      Context = 0;
      v4 = NtQueryDirectoryObject(FileHandle, Heap, v5, 0, 1u, &Context, 0);
      if ( v4 != 261 )
        break;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v5 += 4096;
    }
    NtClose(FileHandle);
    FileHandle = 0;
    if ( (int)(v4 + 0x80000000) < 0 || v4 == -2147483622 )
    {
      v9 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x6Au);
      if ( v9 )
      {
        v4 = 0;
        v10 = (wchar_t **)Heap;
        if ( *Heap )
        {
          do
          {
            if ( SiIsValidDiskDevice(v10[1], v10[3], (int *)&v14) )
            {
              swprintf_s(v9, 0x35u, L"\\Device\\Harddisk%lu\\Partition%lu", v14, 0);
              if ( a1(v9, v14, a2) )
                break;
            }
            v10 += 4;
          }
          while ( *(_WORD *)v10 );
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
      }
      else
      {
        v4 = -1073741801;
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
LABEL_7:
  if ( FileHandle )
    NtClose(FileHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140020ba4  mov     [rsp-8+arg_0], rbx
0x140020ba9  push    rbp
0x140020baa  push    rsi
0x140020bab  push    rdi
0x140020bac  push    r12
0x140020bae  push    r13
0x140020bb0  push    r14
0x140020bb2  push    r15
0x140020bb4  lea     rbp, [rsp-27h]
0x140020bb9  sub     rsp, 90h
0x140020bc0  xorps   xmm0, xmm0
0x140020bc3  xor     r13d, r13d
0x140020bc6  mov     r15, rdx
0x140020bc9  mov     [rbp+57h+arg_18], r13d
0x140020bcd  mov     r12, rcx
0x140020bd0  mov     [rbp+57h+arg_10], r13d
0x140020bd4  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140020bd8  xor     eax, eax
0x140020bda  mov     [rbp+57h+FileHandle], r13
0x140020bde  lea     rdx, aDevice; "\\Device"
0x140020be5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140020be9  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140020bed  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140020bf1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140020bf5  call    cs:__imp_RtlInitUnicodeString
0x140020bfb  lea     rax, [rbp+57h+DestinationString]
0x140020bff  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140020c06  xorps   xmm0, xmm0
0x140020c09  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140020c0d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140020c11  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x140020c15  lea     edx, [r13+1]; DesiredAccess
0x140020c19  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140020c20  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140020c24  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140020c29  call    cs:__imp_NtOpenDirectoryObject
0x140020c2f  mov     ebx, eax
0x140020c31  test    eax, eax
0x140020c33  js      loc_140020CBA
0x140020c39  mov     r14d, 1000h
0x140020c3f  mov     esi, r14d
0x140020c42  mov     r8d, r14d
0x140020c45  jmp     short loc_140020C98
0x140020c47  mov     rcx, [rbp+57h+FileHandle]; DirectoryHandle
0x140020c4b  lea     rax, [rbp+57h+arg_18]
0x140020c4f  mov     [rsp+0C0h+ReturnLength], r13; ReturnLength
0x140020c54  xor     r9d, r9d; ReturnSingleEntry
0x140020c57  mov     [rsp+0C0h+Context], rax; Context
0x140020c5c  mov     r8d, esi; BufferLength
0x140020c5f  mov     rdx, rdi; Buffer
0x140020c62  mov     [rsp+0C0h+RestartScan], 1; RestartScan
0x140020c67  mov     [rbp+57h+arg_18], r13d
0x140020c6b  call    cs:__imp_NtQueryDirectoryObject
0x140020c71  mov     ebx, eax
0x140020c73  cmp     eax, 105h
0x140020c78  jnz     short loc_140020CE6
0x140020c7a  mov     rcx, gs:60h
0x140020c83  mov     r8, rdi; P
0x140020c86  xor     edx, edx; Flags
0x140020c88  mov     rcx, [rcx+30h]; HeapHandle
0x140020c8c  call    cs:__imp_RtlFreeHeap
0x140020c92  add     esi, r14d
0x140020c95  mov     r8d, esi; Size
0x140020c98  mov     rcx, gs:60h
0x140020ca1  xor     edx, edx; Flags
0x140020ca3  mov     rcx, [rcx+30h]; HeapHandle
0x140020ca7  call    cs:__imp_RtlAllocateHeap
0x140020cad  mov     rdi, rax
0x140020cb0  test    rax, rax
0x140020cb3  jnz     short loc_140020C47
0x140020cb5  mov     ebx, 0C0000017h
0x140020cba  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140020cbe  test    rcx, rcx
0x140020cc1  jz      short loc_140020CC9
0x140020cc3  call    cs:__imp_NtClose
0x140020cc9  mov     eax, ebx
0x140020ccb  mov     rbx, [rsp+0C0h+arg_0]
0x140020cd3  add     rsp, 90h
0x140020cda  pop     r15
0x140020cdc  pop     r14
0x140020cde  pop     r13
0x140020ce0  pop     r12
0x140020ce2  pop     rdi
0x140020ce3  pop     rsi
0x140020ce4  pop     rbp
0x140020ce5  retn
0x140020ce6  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140020cea  call    cs:__imp_NtClose
0x140020cf0  mov     ecx, 80000000h
0x140020cf5  mov     [rbp+57h+FileHandle], r13
0x140020cf9  lea     eax, [rbx+rcx]
0x140020cfc  test    ecx, eax
0x140020cfe  jnz     short loc_140020D0C
0x140020d00  cmp     ebx, 8000001Ah
0x140020d06  jnz     loc_140020DAA
0x140020d0c  mov     rcx, gs:60h
0x140020d15  xor     edx, edx; Flags
0x140020d17  mov     rcx, [rcx+30h]; HeapHandle
0x140020d1b  lea     r8d, [rdx+6Ah]; Size
0x140020d1f  call    cs:__imp_RtlAllocateHeap
0x140020d25  mov     r14, rax
0x140020d28  test    rax, rax
0x140020d2b  jnz     short loc_140020D34
0x140020d2d  mov     ebx, 0C0000017h
0x140020d32  jmp     short loc_140020DAA
0x140020d34  mov     ebx, r13d
0x140020d37  mov     rsi, rdi
0x140020d3a  cmp     [rdi], r13w
0x140020d3e  jz      short loc_140020D92
0x140020d40  mov     rdx, [rsi+18h]; wchar_t *
0x140020d44  lea     r8, [rbp+57h+arg_10]
0x140020d48  mov     rcx, [rsi+8]; String1
0x140020d4c  call    SiIsValidDiskDevice
0x140020d51  test    al, al
0x140020d53  jz      short loc_140020D88
0x140020d55  mov     r9d, [rbp+57h+arg_10]
0x140020d59  lea     r8, aDeviceHarddisk_0; "\\Device\\Harddisk%lu\\Partition%lu"
0x140020d60  mov     edx, 35h ; '5'; BufferCount
0x140020d65  mov     qword ptr [rsp+0C0h+RestartScan], r13
0x140020d6a  mov     rcx, r14; Buffer
0x140020d6d  call    cs:__imp_swprintf_s
0x140020d73  mov     edx, [rbp+57h+arg_10]
0x140020d76  mov     r8, r15
0x140020d79  mov     rcx, r14
0x140020d7c  mov     rax, r12
0x140020d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020d84  test    al, al
0x140020d86  jnz     short loc_140020D92
0x140020d88  add     rsi, 20h ; ' '
0x140020d8c  cmp     [rsi], r13w
0x140020d90  jnz     short loc_140020D40
0x140020d92  mov     rcx, gs:60h
0x140020d9b  mov     r8, r14; P
0x140020d9e  xor     edx, edx; Flags
0x140020da0  mov     rcx, [rcx+30h]; HeapHandle
0x140020da4  call    cs:__imp_RtlFreeHeap
0x140020daa  test    rdi, rdi
0x140020dad  jz      loc_140020CBA
0x140020db3  mov     rcx, gs:60h
0x140020dbc  mov     r8, rdi; P
0x140020dbf  xor     edx, edx; Flags
0x140020dc1  mov     rcx, [rcx+30h]; HeapHandle
0x140020dc5  call    cs:__imp_RtlFreeHeap
0x140020dcb  jmp     loc_140020CBA
```
