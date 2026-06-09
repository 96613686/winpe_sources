# InkPresenterStencilRendererBase::_IsProcessAppContainer(void)

- ea: `0x1800c8eb8`
- end: `0x1800c8f3f`
- name: `?_IsProcessAppContainer@InkPresenterStencilRendererBase@@IEAA_NXZ`
- size: `135`
- prototype: `bool __fastcall(InkPresenterStencilRendererBase *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c8e84`

## callees

- `0x1800c8eb8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c8eec`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c8eec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c8ed9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c8ed9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c8f2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c8f2c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c8f14`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c8f14`

## pseudocode

```c
bool __fastcall InkPresenterStencilRendererBase::_IsProcessAppContainer(InkPresenterStencilRendererBase *this)
{
  HANDLE CurrentProcess; // rax
  BOOL v2; // eax
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  int v5; // [rsp+44h] [rbp+Ch]
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v5 = HIDWORD(this);
  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  CurrentProcess = GetCurrentProcess();
  v2 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  if ( v2 )
  {
    if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
      TokenInformation = 0;
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    LOBYTE(v2) = TokenInformation != 0;
  }
  return v2;
}

```

## disassembly

```asm
0x1800c8eb8  mov     rax, rsp
0x1800c8ebb  mov     [rax+8], rcx
0x1800c8ebf  sub     rsp, 38h
0x1800c8ec3  mov     qword ptr [rax+18h], 0
0x1800c8ecb  mov     dword ptr [rax+8], 0
0x1800c8ed2  mov     dword ptr [rax+10h], 0
0x1800c8ed9  call    cs:__imp_GetCurrentProcess
0x1800c8edf  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800c8ee4  mov     edx, 8; DesiredAccess
0x1800c8ee9  mov     rcx, rax; ProcessHandle
0x1800c8eec  call    cs:__imp_OpenProcessToken
0x1800c8ef2  test    eax, eax
0x1800c8ef4  jz      short loc_1800C8F3A
0x1800c8ef6  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800c8efb  lea     rax, [rsp+38h+arg_8]
0x1800c8f00  mov     r9d, 4; TokenInformationLength
0x1800c8f06  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800c8f0b  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800c8f10  lea     edx, [r9+19h]; TokenInformationClass
0x1800c8f14  call    cs:__imp_GetTokenInformation
0x1800c8f1a  test    eax, eax
0x1800c8f1c  jnz     short loc_1800C8F22
0x1800c8f1e  mov     [rsp+38h+TokenInformation], eax
0x1800c8f22  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800c8f27  test    rcx, rcx
0x1800c8f2a  jz      short loc_1800C8F32
0x1800c8f2c  call    cs:__imp_CloseHandle
0x1800c8f32  cmp     [rsp+38h+TokenInformation], 0
0x1800c8f37  setnz   al
0x1800c8f3a  add     rsp, 38h
0x1800c8f3e  retn
```
