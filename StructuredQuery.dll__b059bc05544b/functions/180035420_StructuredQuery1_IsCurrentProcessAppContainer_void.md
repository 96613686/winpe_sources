# StructuredQuery1::IsCurrentProcessAppContainer(void)

- ea: `0x180035420`
- end: `0x1800354cc`
- name: `?IsCurrentProcessAppContainer@StructuredQuery1@@YA_NXZ`
- size: `172`
- prototype: `bool __fastcall(StructuredQuery1 *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180034f50`
- `0x18003531c`

## callees

- `0x180035420`
- `0x180059920`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035431`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035431`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180035444`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180035444`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800354c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800354c4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003547c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003547c`

## pseudocode

```c
bool __fastcall StructuredQuery1::IsCurrentProcessAppContainer(StructuredQuery1 *this)
{
  bool v1; // bl
  HANDLE CurrentProcess; // rax
  char *v3; // rcx
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v1 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) || (int)ResultFromKnownLastError() >= 0 )
  {
    ReturnLength = 0;
    TokenInformation = 0;
    if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength)
      || (int)ResultFromKnownLastError() >= 0 )
    {
      v1 = TokenInformation != 0;
    }
  }
  v3 = (char *)TokenHandle;
  TokenHandle = 0;
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
  return v1;
}

```

## disassembly

```asm
0x180035420  push    rbx
0x180035422  sub     rsp, 30h
0x180035426  xor     bl, bl
0x180035428  mov     [rsp+38h+TokenHandle], 0
0x180035431  call    cs:__imp_GetCurrentProcess
0x180035437  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18003543c  mov     edx, 8; DesiredAccess
0x180035441  mov     rcx, rax; ProcessHandle
0x180035444  call    cs:__imp_OpenProcessToken
0x18003544a  test    eax, eax
0x18003544c  jz      short loc_1800354AE
0x18003544e  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180035453  lea     rax, [rsp+38h+arg_8]
0x180035458  mov     r9d, 4; TokenInformationLength
0x18003545e  mov     [rsp+38h+arg_8], 0
0x180035466  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18003546b  mov     [rsp+38h+TokenInformation], 0
0x180035473  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180035478  lea     edx, [r9+19h]; TokenInformationClass
0x18003547c  call    cs:__imp_GetTokenInformation
0x180035482  test    eax, eax
0x180035484  jz      short loc_1800354B9
0x180035486  cmp     [rsp+38h+TokenInformation], 0
0x18003548b  setnz   bl
0x18003548e  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180035493  mov     [rsp+38h+TokenHandle], 0
0x18003549c  lea     rdx, [rcx-1]
0x1800354a0  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800354a4  jbe     short loc_1800354C4
0x1800354a6  mov     al, bl
0x1800354a8  add     rsp, 30h
0x1800354ac  pop     rbx
0x1800354ad  retn
0x1800354ae  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800354b3  test    eax, eax
0x1800354b5  js      short loc_18003548E
0x1800354b7  jmp     short loc_18003544E
0x1800354b9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800354be  test    eax, eax
0x1800354c0  jns     short loc_180035486
0x1800354c2  jmp     short loc_18003548E
0x1800354c4  call    cs:__imp_CloseHandle
0x1800354ca  jmp     short loc_1800354A6
```
