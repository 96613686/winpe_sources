# GetHighestAvailableToken(void *,void * *)

- ea: `0x14000f67c`
- end: `0x14000f822`
- name: `?GetHighestAvailableToken@@YAJPEAXPEAPEAX@Z`
- size: `422`
- prototype: `__int64 __fastcall(void *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140012124`

## callees

- `0x140006538`
- `0x1400076c8`
- `0x14000f67c`
- `0x1400135b8`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x14000f761`
- `ADVAPI32!GetTokenInformation` at `0x14000f7b8`
- `ADVAPI32!GetTokenInformation` at `0x14000f761`
- `ADVAPI32!GetTokenInformation` at `0x14000f7b8`
- `KERNEL32!CloseHandle` at `0x14000f802`
- `KERNEL32!CloseHandle` at `0x14000f802`
- `KERNEL32!GetLastError` at `0x14000f771`
- `KERNEL32!GetLastError` at `0x14000f771`
- `ntdll!NtDuplicateToken` at `0x14000f723`
- `ntdll!NtDuplicateToken` at `0x14000f723`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetHighestAvailableToken(void *a1, void **a2)
{
  NTSTATUS v3; // ecx
  unsigned int v4; // ebx
  signed int LastError; // eax
  HANDLE v6; // rax
  HANDLE TokenHandle; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v9[3]; // [rsp+38h] [rbp-48h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v11; // [rsp+90h] [rbp+10h] BYREF
  int TokenInformation; // [rsp+A0h] [rbp+20h] BYREF
  DWORD ReturnLength; // [rsp+A8h] [rbp+28h] BYREF

  v9[1] = -2;
  TokenHandle = 0;
  v9[2] = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v9[0] = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v11 = 0;
  if ( !a1 || !a2 )
  {
    v4 = -2147024809;
    goto LABEL_16;
  }
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtDuplicateToken(a1, 0, &ObjectAttributes, 0, TokenPrimary, &TokenHandle);
  if ( SErrorConverterT<CEmptyType>::C_NtStatus2HR(v3, &v11) )
  {
    if ( !GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
      goto LABEL_6;
    if ( TokenInformation != 3 )
      goto LABEL_13;
    if ( !GetTokenInformation(TokenHandle, TokenLinkedToken, v9, 8u, &ReturnLength) )
    {
LABEL_6:
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v4 = -2147467259;
      }
      goto LABEL_16;
    }
    v6 = (HANDLE)v9[0];
    if ( !v9[0] )
    {
LABEL_13:
      v6 = TokenHandle;
      TokenHandle = 0;
    }
    *a2 = v6;
    v4 = v11;
    goto LABEL_17;
  }
  v4 = v11;
LABEL_16:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
LABEL_17:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x14000f67c  mov     r11, rsp
0x14000f67f  push    rbp
0x14000f680  mov     rbp, rsp
0x14000f683  sub     rsp, 80h
0x14000f68a  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x14000f692  mov     [r11+10h], rbx
0x14000f696  mov     rbx, rdx
0x14000f699  mov     [rbp+TokenHandle], 0
0x14000f6a1  mov     [rbp+var_38], 0
0x14000f6a9  xorps   xmm0, xmm0
0x14000f6ac  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000f6b0  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000f6b4  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000f6b8  mov     [rbp+var_48], 0
0x14000f6c0  mov     [rbp+TokenInformation], 0
0x14000f6c7  mov     [rbp+ReturnLength], 0
0x14000f6ce  mov     [rbp+arg_0], 0
0x14000f6d5  test    rcx, rcx
0x14000f6d8  jz      loc_14000F7E5
0x14000f6de  test    rdx, rdx
0x14000f6e1  jz      loc_14000F7E5
0x14000f6e7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000f6ee  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14000f6f6  mov     [rbp+ObjectAttributes.Attributes], 0
0x14000f6fd  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14000f705  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000f70a  lea     rax, [rbp+TokenHandle]
0x14000f70e  mov     [r11-60h], rax
0x14000f712  mov     [rsp+80h+TokenType], 1; TokenType
0x14000f71a  xor     r9d, r9d; EffectiveOnly
0x14000f71d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000f721  xor     edx, edx; DesiredAccess
0x14000f723  call    cs:__imp_NtDuplicateToken
0x14000f72a  nop     dword ptr [rax+rax+00h]
0x14000f72f  mov     ecx, eax
0x14000f731  lea     rdx, [rbp+arg_0]
0x14000f735  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x14000f73a  test    eax, eax
0x14000f73c  jnz     short loc_14000F746
0x14000f73e  mov     ebx, [rbp+arg_0]
0x14000f741  jmp     loc_14000F7EA
0x14000f746  lea     rax, [rbp+ReturnLength]
0x14000f74a  mov     qword ptr [rsp+80h+TokenType], rax; ReturnLength
0x14000f74f  mov     r9d, 4; TokenInformationLength
0x14000f755  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14000f759  lea     edx, [r9+0Eh]; TokenInformationClass
0x14000f75d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14000f761  call    cs:__imp_GetTokenInformation
0x14000f768  nop     dword ptr [rax+rax+00h]
0x14000f76d  test    eax, eax
0x14000f76f  jnz     short loc_14000F797
0x14000f771  call    cs:__imp_GetLastError
0x14000f778  nop     dword ptr [rax+rax+00h]
0x14000f77d  test    eax, eax
0x14000f77f  mov     ebx, eax
0x14000f781  jnz     short loc_14000F78A
0x14000f783  mov     ebx, 80004005h
0x14000f788  jmp     short loc_14000F7EA
0x14000f78a  jle     short loc_14000F7EA
0x14000f78c  movzx   ebx, ax
0x14000f78f  or      ebx, 80070000h
0x14000f795  jmp     short loc_14000F7EA
0x14000f797  cmp     [rbp+TokenInformation], 3
0x14000f79b  jnz     short loc_14000F7D1
0x14000f79d  lea     rax, [rbp+ReturnLength]
0x14000f7a1  mov     qword ptr [rsp+80h+TokenType], rax; ReturnLength
0x14000f7a6  mov     r9d, 8; TokenInformationLength
0x14000f7ac  lea     r8, [rbp+var_48]; TokenInformation
0x14000f7b0  lea     edx, [r9+0Bh]; TokenInformationClass
0x14000f7b4  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14000f7b8  call    cs:__imp_GetTokenInformation
0x14000f7bf  nop     dword ptr [rax+rax+00h]
0x14000f7c4  test    eax, eax
0x14000f7c6  jz      short loc_14000F771
0x14000f7c8  mov     rax, [rbp+var_48]
0x14000f7cc  test    rax, rax
0x14000f7cf  jnz     short loc_14000F7DD
0x14000f7d1  mov     rax, [rbp+TokenHandle]
0x14000f7d5  mov     [rbp+TokenHandle], 0
0x14000f7dd  mov     [rbx], rax
0x14000f7e0  mov     ebx, [rbp+arg_0]
0x14000f7e3  jmp     short loc_14000F7F1
0x14000f7e5  mov     ebx, 80070057h
0x14000f7ea  mov     ecx, ebx
0x14000f7ec  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000f7f1  mov     ecx, ebx
0x14000f7f3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000f7f8  nop
0x14000f7f9  mov     rcx, [rbp+TokenHandle]; hObject
0x14000f7fd  test    rcx, rcx
0x14000f800  jz      short loc_14000F80E
0x14000f802  call    cs:__imp_CloseHandle
0x14000f809  nop     dword ptr [rax+rax+00h]
0x14000f80e  mov     eax, ebx
0x14000f810  mov     rbx, [rsp+80h+arg_8]
0x14000f818  add     rsp, 80h
0x14000f81f  pop     rbp
0x14000f820  retn
```
