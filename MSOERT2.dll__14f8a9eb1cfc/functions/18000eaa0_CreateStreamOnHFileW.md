# CreateStreamOnHFileW

- ea: `0x18000eaa0`
- end: `0x18000ebb5`
- name: `CreateStreamOnHFileW`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e9b0`

## callees

- `0x180001c80`
- `0x18000e940`
- `0x18000eaa0`
- `0x180010e1c`
- `0x180012fc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000eb84`
- `KERNEL32!CloseHandle` at `0x18000eb84`
- `KERNEL32!GetTempPathW` at `0x18000eb05`
- `KERNEL32!GetTempPathW` at `0x18000eb05`
- `KERNEL32!GetTempFileNameW` at `0x18000eb2b`
- `KERNEL32!GetTempFileNameW` at `0x18000eb2b`

## pseudocode

```c
__int64 __fastcall CreateStreamOnHFileW(
        WCHAR *a1,
        unsigned int a2,
        unsigned int a3,
        struct _SECURITY_ATTRIBUTES *a4,
        DWORD a5,
        DWORD a6,
        HANDLE a7,
        _QWORD *a8)
{
  DWORD v10; // ebx
  void *FileW; // rax
  void *v14; // rdi
  int StreamOnHANDLE; // ebx
  WCHAR Buffer[264]; // [rsp+40h] [rbp-468h] BYREF
  WCHAR TempFileName[264]; // [rsp+250h] [rbp-258h] BYREF

  v10 = a6;
  *a8 = 0;
  if ( !a1 || !*a1 )
  {
    if ( GetTempPathW(0x104u, Buffer) - 1 > 0x103 || !GetTempFileNameW(Buffer, L"tmp", 0, TempFileName) )
      return (unsigned int)-2147467259;
    a1 = TempFileName;
    v10 = a6 | 0x4000000;
    a5 = 3;
  }
  FileW = AthCreateFileW(a1, a2, a3, a4, a5, v10, a7);
  v14 = FileW;
  if ( FileW == (void *)-1LL )
    return HrGetLastError();
  StreamOnHANDLE = CreateStreamOnHANDLE(FileW, a8);
  if ( StreamOnHANDLE < 0 )
    CloseHandle(v14);
  return (unsigned int)StreamOnHANDLE;
}

```

## disassembly

```asm
0x18000eaa0  push    rbx
0x18000eaa2  push    rbp
0x18000eaa3  push    rsi
0x18000eaa4  push    rdi
0x18000eaa5  push    r12
0x18000eaa7  push    r14
0x18000eaa9  push    r15
0x18000eaab  sub     rsp, 470h
0x18000eab2  mov     rax, cs:__security_cookie
0x18000eab9  xor     rax, rsp
0x18000eabc  mov     [rsp+4A8h+var_48], rax
0x18000eac4  mov     rsi, [rsp+4A8h+arg_38]
0x18000eacc  xor     r12d, r12d
0x18000eacf  mov     eax, [rsp+4A8h+arg_20]
0x18000ead6  mov     r14, r9
0x18000ead9  mov     ebx, [rsp+4A8h+arg_28]
0x18000eae0  mov     ebp, r8d
0x18000eae3  mov     r15, [rsp+4A8h+arg_30]
0x18000eaeb  mov     edi, edx
0x18000eaed  mov     [rsi], r12
0x18000eaf0  test    rcx, rcx
0x18000eaf3  jz      short loc_18000EAFB
0x18000eaf5  cmp     [rcx], r12w
0x18000eaf9  jnz     short loc_18000EB46
0x18000eafb  lea     rdx, [rsp+4A8h+Buffer]; lpBuffer
0x18000eb00  mov     ecx, 104h; nBufferLength
0x18000eb05  call    cs:__imp_GetTempPathW
0x18000eb0b  dec     eax
0x18000eb0d  cmp     eax, 103h
0x18000eb12  ja      short loc_18000EB8C
0x18000eb14  lea     r9, [rsp+4A8h+TempFileName]; lpTempFileName
0x18000eb1c  xor     r8d, r8d; uUnique
0x18000eb1f  lea     rdx, aTmp; "tmp"
0x18000eb26  lea     rcx, [rsp+4A8h+Buffer]; lpPathName
0x18000eb2b  call    cs:__imp_GetTempFileNameW
0x18000eb31  test    eax, eax
0x18000eb33  jz      short loc_18000EB8C
0x18000eb35  lea     rcx, [rsp+4A8h+TempFileName]; unsigned __int16 *
0x18000eb3d  bts     ebx, 1Ah
0x18000eb41  mov     eax, 3
0x18000eb46  mov     [rsp+4A8h+var_478], r15; HANDLE
0x18000eb4b  mov     r9, r14; struct _SECURITY_ATTRIBUTES *
0x18000eb4e  mov     [rsp+4A8h+var_480], ebx; DWORD
0x18000eb52  mov     r8d, ebp; unsigned int
0x18000eb55  mov     edx, edi; unsigned int
0x18000eb57  mov     [rsp+4A8h+var_488], eax; DWORD
0x18000eb5b  call    ?AthCreateFileW@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; AthCreateFileW(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x18000eb60  mov     rdi, rax
0x18000eb63  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000eb67  jnz     short loc_18000EB70
0x18000eb69  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18000eb6e  jmp     short loc_18000EB93
0x18000eb70  mov     rdx, rsi
0x18000eb73  mov     rcx, rdi
0x18000eb76  call    CreateStreamOnHANDLE
0x18000eb7b  mov     ebx, eax
0x18000eb7d  test    eax, eax
0x18000eb7f  jns     short loc_18000EB91
0x18000eb81  mov     rcx, rdi; hObject
0x18000eb84  call    cs:__imp_CloseHandle
0x18000eb8a  jmp     short loc_18000EB91
0x18000eb8c  mov     ebx, 80004005h
0x18000eb91  mov     eax, ebx
0x18000eb93  mov     rcx, [rsp+4A8h+var_48]
0x18000eb9b  xor     rcx, rsp; StackCookie
0x18000eb9e  call    __security_check_cookie
0x18000eba3  add     rsp, 470h
0x18000ebaa  pop     r15
0x18000ebac  pop     r14
0x18000ebae  pop     r12
0x18000ebb0  pop     rdi
0x18000ebb1  pop     rsi
0x18000ebb2  pop     rbp
0x18000ebb3  pop     rbx
0x18000ebb4  retn
```
