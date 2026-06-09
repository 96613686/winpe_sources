# UMReflectorOpenWorker

- ea: `0x180029000`
- end: `0x18002912b`
- name: `UMReflectorOpenWorker`
- size: `299`
- prototype: `__int64 __fastcall(_DWORD *, void ***)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ca80`
- `0x18000ce10`

## callees

- `0x180029000`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800290b7`
- `ntdll!NtOpenFile` at `0x1800290b7`
- `ntdll!RtlNtStatusToDosError` at `0x1800290ce`
- `ntdll!RtlNtStatusToDosError` at `0x1800290ce`
- `ntdll!RtlInitUnicodeString` at `0x18002906e`
- `ntdll!RtlInitUnicodeString` at `0x18002906e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800290c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029113`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800290c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029113`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029060`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029060`
- `KERNEL32!LocalFree` at `0x1800290dd`
- `KERNEL32!LocalFree` at `0x1800290dd`
- `KERNEL32!LocalAlloc` at `0x18002903c`
- `KERNEL32!LocalAlloc` at `0x18002903c`

## pseudocode

```c
__int64 __fastcall UMReflectorOpenWorker(_DWORD *a1, void ***a2)
{
  void **v4; // rax
  void **v5; // rdi
  unsigned int v6; // ebx
  void ***v7; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-9h] BYREF

  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  v4 = (void **)LocalAlloc(0x40u, 0x28u);
  *a2 = v4;
  v5 = v4;
  if ( !v4 )
  {
    v6 = 8;
LABEL_6:
    *a2 = 0;
    return v6;
  }
  v4[2] = a1;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 4));
  RtlInitUnicodeString(&DestinationString, *((PCWSTR *)a1 + 7));
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = NtOpenFile(v5 + 4, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x10u);
  if ( v6 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 4));
    v6 = RtlNtStatusToDosError(v6);
    if ( v6 )
    {
      LocalFree(v5);
      goto LABEL_6;
    }
  }
  else
  {
    ++*a1;
    v7 = (void ***)*((_QWORD *)a1 + 10);
    if ( *v7 != (void **)(a1 + 18) )
      __fastfail(3u);
    v5[1] = v7;
    *v5 = a1 + 18;
    *v7 = v5;
    *((_QWORD *)a1 + 10) = v5;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 4));
  }
  return v6;
}

```

## disassembly

```asm
0x180029000  push    rbp
0x180029002  push    rbx
0x180029003  push    rsi
0x180029004  push    rdi
0x180029005  push    r14
0x180029007  push    r15
0x180029009  lea     rbp, [rsp-2Fh]
0x18002900e  sub     rsp, 88h
0x180029015  xorps   xmm0, xmm0
0x180029018  xor     eax, eax
0x18002901a  mov     r15, rdx
0x18002901d  mov     rsi, rcx
0x180029020  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180029024  lea     ebx, [rax+40h]
0x180029027  mov     ecx, ebx; uFlags
0x180029029  lea     edx, [rax+28h]; uBytes
0x18002902c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180029030  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180029034  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180029038  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002903c  call    cs:__imp_LocalAlloc
0x180029042  mov     [r15], rax
0x180029045  mov     rdi, rax
0x180029048  test    rax, rax
0x18002904b  jnz     short loc_180029055
0x18002904d  lea     ebx, [rax+8]
0x180029050  jmp     loc_1800290E3
0x180029055  lea     r14, [rsi+10h]
0x180029059  mov     [rax+10h], rsi
0x18002905d  mov     rcx, r14; lpCriticalSection
0x180029060  call    cs:__imp_EnterCriticalSection
0x180029066  mov     rdx, [rsi+38h]; SourceString
0x18002906a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002906e  call    cs:__imp_RtlInitUnicodeString
0x180029074  lea     rax, [rbp+57h+DestinationString]
0x180029078  mov     [rsp+0B0h+OpenOptions], 10h; OpenOptions
0x180029080  xorps   xmm0, xmm0
0x180029083  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180029087  lea     rcx, [rdi+20h]; FileHandle
0x18002908b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180029092  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180029096  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18002909e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800290a2  mov     [rbp+57h+ObjectAttributes.Attributes], ebx
0x1800290a5  mov     edx, 100000h; DesiredAccess
0x1800290aa  mov     [rsp+0B0h+ShareAccess], 7; ShareAccess
0x1800290b2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800290b7  call    cs:__imp_NtOpenFile
0x1800290bd  mov     ebx, eax
0x1800290bf  test    eax, eax
0x1800290c1  jz      short loc_1800290EC
0x1800290c3  mov     rcx, r14; lpCriticalSection
0x1800290c6  call    cs:__imp_LeaveCriticalSection
0x1800290cc  mov     ecx, ebx; Status
0x1800290ce  call    cs:__imp_RtlNtStatusToDosError
0x1800290d4  mov     ebx, eax
0x1800290d6  test    eax, eax
0x1800290d8  jz      short loc_180029119
0x1800290da  mov     rcx, rdi; hMem
0x1800290dd  call    cs:__imp_LocalFree
0x1800290e3  mov     qword ptr [r15], 0
0x1800290ea  jmp     short loc_180029119
0x1800290ec  inc     dword ptr [rsi]
0x1800290ee  lea     rax, [rsi+48h]
0x1800290f2  mov     rcx, [rax+8]
0x1800290f6  cmp     [rcx], rax
0x1800290f9  jz      short loc_180029102
0x1800290fb  mov     ecx, 3
0x180029100  int     29h; Win8: RtlFailFast(ecx)
0x180029102  mov     [rdi+8], rcx
0x180029106  mov     [rdi], rax
0x180029109  mov     [rcx], rdi
0x18002910c  mov     rcx, r14; lpCriticalSection
0x18002910f  mov     [rax+8], rdi
0x180029113  call    cs:__imp_LeaveCriticalSection
0x180029119  mov     eax, ebx
0x18002911b  add     rsp, 88h
0x180029122  pop     r15
0x180029124  pop     r14
0x180029126  pop     rdi
0x180029127  pop     rsi
0x180029128  pop     rbx
0x180029129  pop     rbp
0x18002912a  retn
```
