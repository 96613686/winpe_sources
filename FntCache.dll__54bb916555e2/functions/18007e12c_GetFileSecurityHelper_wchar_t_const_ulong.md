# GetFileSecurityHelper(wchar_t const *,ulong)

- ea: `0x18007e12c`
- end: `0x18007e246`
- name: `?GetFileSecurityHelper@@YAPEAU_SECURITY_DESCRIPTOR@@PEB_WK@Z`
- size: `282`
- prototype: `struct _SECURITY_DESCRIPTOR *__fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007df28`

## callees

- `0x1800217ac`
- `0x18002faf0`
- `0x18007e12c`
- `0x1800aa674`
- `0x1800aaa58`
- `0x1800b4760`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e167`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18007e159`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18007e19d`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18007e159`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18007e19d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _SECURITY_DESCRIPTOR *__fastcall GetFileSecurityHelper(LPCWSTR lpFileName)
{
  signed int LastError; // eax
  void *v3; // rbx
  unsigned int v5; // edx
  DWORD nLength; // [rsp+48h] [rbp+10h] BYREF
  void *v7; // [rsp+50h] [rbp+18h] BYREF

  nLength = 0;
  if ( GetFileSecurityW(lpFileName, 0x20000004u, 0, 0, &nLength) )
  {
    Exception::Exception((Exception *)&v7, -2147418113, 0);
    LogAndThrow<OSException>((int *)&v7, 0x636553656C6946LL, 218);
  }
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    else
      v5 = LastError;
    Exception::Exception((Exception *)&v7, v5, LastError);
    LogAndThrow<OSException>((int *)&v7, 0x636553656C6946LL, 225);
  }
  v3 = operator new(nLength);
  v7 = v3;
  if ( !GetFileSecurityW(lpFileName, 0x20000004u, v3, nLength, &nLength) )
    LogAndThrowLastError(0x636553656C6946LL, 237);
  operator delete(0, 0x28u);
  return (struct _SECURITY_DESCRIPTOR *)v3;
}

```

## disassembly

```asm
0x18007e12c  mov     rax, rsp
0x18007e12f  mov     [rax+8], rbx
0x18007e133  mov     [rax+10h], edx
0x18007e136  push    rdi
0x18007e137  sub     rsp, 30h
0x18007e13b  mov     rdi, rcx
0x18007e13e  mov     dword ptr [rax+10h], 0
0x18007e145  lea     rax, [rax+10h]
0x18007e149  mov     [rsp+38h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18007e14e  xor     r9d, r9d; nLength
0x18007e151  xor     r8d, r8d; pSecurityDescriptor
0x18007e154  mov     edx, 20000004h; RequestedInformation
0x18007e159  call    cs:__imp_GetFileSecurityW
0x18007e15f  test    eax, eax
0x18007e161  jnz     loc_18007E201
0x18007e167  call    cs:__imp_GetLastError
0x18007e16d  cmp     eax, 7Ah ; 'z'
0x18007e170  jnz     short loc_18007E1C5
0x18007e172  mov     ecx, [rsp+38h+nLength]; Size
0x18007e176  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007e17b  mov     rbx, rax
0x18007e17e  mov     [rsp+38h+arg_10], rax
0x18007e183  lea     rax, [rsp+38h+nLength]
0x18007e188  mov     [rsp+38h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18007e18d  mov     r9d, [rsp+38h+nLength]; nLength
0x18007e192  mov     r8, rbx; pSecurityDescriptor
0x18007e195  mov     edx, 20000004h; RequestedInformation
0x18007e19a  mov     rcx, rdi; lpFileName
0x18007e19d  call    cs:__imp_GetFileSecurityW
0x18007e1a3  test    eax, eax
0x18007e1a5  jz      loc_18007E231
0x18007e1ab  mov     edx, 28h ; '('; unsigned __int64
0x18007e1b0  xor     ecx, ecx; void *
0x18007e1b2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007e1b7  mov     rax, rbx
0x18007e1ba  mov     rbx, [rsp+38h+arg_0]
0x18007e1bf  add     rsp, 30h
0x18007e1c3  pop     rdi
0x18007e1c4  retn
0x18007e1c5  mov     rbx, 636553656C6946h
0x18007e1cf  test    eax, eax
0x18007e1d1  jg      short loc_18007E1F6
0x18007e1d3  mov     edx, eax; int
0x18007e1d5  mov     r8d, eax; unsigned int
0x18007e1d8  lea     rcx, [rsp+38h+arg_10]; this
0x18007e1dd  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18007e1e2  mov     r8d, 0E1h
0x18007e1e8  mov     rdx, rbx
0x18007e1eb  lea     rcx, [rsp+38h+arg_10]
0x18007e1f0  call    ??$LogAndThrow@VOSException@@@@YAXAEBVOSException@@VEventTag@@I@Z; LogAndThrow<OSException>(OSException const &,EventTag,uint)
0x18007e1f6  movzx   edx, ax
0x18007e1f9  or      edx, 80070000h
0x18007e1ff  jmp     short loc_18007E1D5
0x18007e201  mov     rbx, 636553656C6946h
0x18007e20b  xor     r8d, r8d; unsigned int
0x18007e20e  mov     edx, 8000FFFFh; int
0x18007e213  lea     rcx, [rsp+38h+arg_10]; this
0x18007e218  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18007e21d  mov     r8d, 0DAh
0x18007e223  mov     rdx, rbx
0x18007e226  lea     rcx, [rsp+38h+arg_10]
0x18007e22b  call    ??$LogAndThrow@VOSException@@@@YAXAEBVOSException@@VEventTag@@I@Z; LogAndThrow<OSException>(OSException const &,EventTag,uint)
0x18007e231  mov     rcx, 636553656C6946h
0x18007e23b  mov     edx, 0EDh
0x18007e240  call    ?LogAndThrowLastError@@YAXVEventTag@@I@Z; LogAndThrowLastError(EventTag,uint)
```
