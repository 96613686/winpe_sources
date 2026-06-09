# CAccessControlImpl::AccessCheck(ulong &,void *)

- ea: `0x18007a1cc`
- end: `0x18007a352`
- name: `?AccessCheck@CAccessControlImpl@@QEAAJAEAKPEAX@Z`
- size: `390`
- prototype: `__int64 __fastcall(CAccessControlImpl *this, unsigned int *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180078328`
- `0x18007a164`

## callees

- `0x18000f880`
- `0x180019bb0`
- `0x180061f78`
- `0x18007a1cc`
- `0x18007a358`
- `0x1801244c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a321`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a319`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a319`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18007a284`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18007a284`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18007a25b`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18007a2c6`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18007a25b`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18007a2c6`

## string_xrefs

- `0x18007a33f`: `onecoreuap\base\appmodel\search\common\pkmutill\acladm.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAccessControlImpl::AccessCheck(CAccessControlImpl *this, unsigned int *a2, void *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  BOOL v8; // ebx
  signed int LastError; // eax
  int PrivilegeSet; // [rsp+20h] [rbp-50h]
  WINBOOL AccessStatus; // [rsp+40h] [rbp-30h] BYREF
  DWORD PrivilegeSetLength; // [rsp+44h] [rbp-2Ch] BYREF
  void *DuplicateTokenHandle; // [rsp+48h] [rbp-28h] BYREF
  struct _PRIVILEGE_SET v15; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v6 = CAccessControlImpl::InitWithLoad(this);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutill\\acladm.cxx",
      (const char *)(unsigned int)v6,
      PrivilegeSet);
  }
  else
  {
    CSyncReadWrite::GetWriteAccess((CAccessControlImpl *)((char *)this + 24));
    memset(&v15, 0, sizeof(v15));
    PrivilegeSetLength = 20;
    AccessStatus = 0;
    v8 = AccessCheck((char *)this + 144, a3, 0x2000000u, &GenericMapping, &v15, &PrivilegeSetLength, a2, &AccessStatus);
    if ( GetLastError() == 1309 )
    {
      DuplicateTokenHandle = 0;
      if ( DuplicateToken(a3, SecurityImpersonation, &DuplicateTokenHandle) )
        v8 = AccessCheck(
               (char *)this + 144,
               DuplicateTokenHandle,
               0x2000000u,
               &GenericMapping,
               &v15,
               &PrivilegeSetLength,
               a2,
               &AccessStatus);
      if ( (char *)DuplicateTokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(DuplicateTokenHandle);
    }
    if ( v8 )
    {
      v7 = 0;
      if ( !AccessStatus )
        v7 = -2147024891;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    CSyncReadWrite::ReleaseWriteAccess((CAccessControlImpl *)((char *)this + 24));
  }
  return v7;
}

```

## disassembly

```asm
0x18007a1cc  mov     [rsp-28h+arg_18], rbx
0x18007a1d1  push    rbp
0x18007a1d2  push    rsi
0x18007a1d3  push    rdi
0x18007a1d4  push    r14
0x18007a1d6  push    r15
0x18007a1d8  mov     rbp, rsp
0x18007a1db  sub     rsp, 70h
0x18007a1df  mov     rax, cs:__security_cookie
0x18007a1e6  xor     rax, rsp
0x18007a1e9  mov     [rbp+var_8], rax
0x18007a1ed  mov     rsi, r8
0x18007a1f0  mov     r14, rdx
0x18007a1f3  mov     rdi, rcx
0x18007a1f6  call    ?InitWithLoad@CAccessControlImpl@@AEAAJXZ; CAccessControlImpl::InitWithLoad(void)
0x18007a1fb  mov     ebx, eax
0x18007a1fd  test    eax, eax
0x18007a1ff  js      loc_18007A338
0x18007a205  lea     rcx, [rdi+18h]; this
0x18007a209  call    ?GetWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetWriteAccess(void)
0x18007a20e  xorps   xmm0, xmm0
0x18007a211  xor     eax, eax
0x18007a213  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm0
0x18007a217  mov     [rbp+var_20.Privilege.Attributes], eax
0x18007a21a  mov     [rbp+var_2C], 14h
0x18007a221  mov     [rbp+var_30], eax
0x18007a224  lea     rax, [rbp+var_30]
0x18007a228  mov     [rsp+70h+AccessStatus], rax; AccessStatus
0x18007a22d  mov     [rsp+70h+GrantedAccess], r14; GrantedAccess
0x18007a232  lea     rax, [rbp+var_2C]
0x18007a236  mov     [rsp+70h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18007a23b  lea     rax, [rbp+var_20]
0x18007a23f  mov     [rsp+70h+PrivilegeSet], rax; PrivilegeSet
0x18007a244  lea     r9, GenericMapping; GenericMapping
0x18007a24b  mov     r8d, 2000000h; DesiredAccess
0x18007a251  mov     rdx, rsi; ClientToken
0x18007a254  lea     rcx, [rdi+90h]; pSecurityDescriptor
0x18007a25b  call    cs:__imp_AccessCheck
0x18007a261  mov     ebx, eax
0x18007a263  call    cs:__imp_GetLastError
0x18007a269  cmp     eax, 51Dh
0x18007a26e  jnz     short loc_18007A2DC
0x18007a270  mov     [rbp+DuplicateTokenHandle], 0
0x18007a278  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x18007a27c  mov     edx, 2; ImpersonationLevel
0x18007a281  mov     rcx, rsi; ExistingTokenHandle
0x18007a284  call    cs:__imp_DuplicateToken
0x18007a28a  test    eax, eax
0x18007a28c  jz      short loc_18007A2CE
0x18007a28e  lea     rax, [rbp+var_30]
0x18007a292  mov     [rsp+70h+AccessStatus], rax; AccessStatus
0x18007a297  mov     [rsp+70h+GrantedAccess], r14; GrantedAccess
0x18007a29c  lea     rax, [rbp+var_2C]
0x18007a2a0  mov     [rsp+70h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18007a2a5  lea     rax, [rbp+var_20]
0x18007a2a9  mov     [rsp+70h+PrivilegeSet], rax; PrivilegeSet
0x18007a2ae  lea     r9, GenericMapping; GenericMapping
0x18007a2b5  mov     r8d, 2000000h; DesiredAccess
0x18007a2bb  mov     rdx, [rbp+DuplicateTokenHandle]; ClientToken
0x18007a2bf  lea     rcx, [rdi+90h]; pSecurityDescriptor
0x18007a2c6  call    cs:__imp_AccessCheck
0x18007a2cc  mov     ebx, eax
0x18007a2ce  mov     rcx, [rbp+DuplicateTokenHandle]; hObject
0x18007a2d2  lea     rax, [rcx-1]
0x18007a2d6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007a2da  jbe     short loc_18007A319
0x18007a2dc  test    ebx, ebx
0x18007a2de  jz      short loc_18007A321
0x18007a2e0  xor     ebx, ebx
0x18007a2e2  mov     eax, 80070005h
0x18007a2e7  cmp     [rbp+var_30], ebx
0x18007a2ea  cmovz   ebx, eax
0x18007a2ed  lea     rcx, [rdi+18h]; this
0x18007a2f1  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x18007a2f6  nop
0x18007a2f7  mov     eax, ebx
0x18007a2f9  mov     rcx, [rbp+var_8]
0x18007a2fd  xor     rcx, rsp; StackCookie
0x18007a300  call    __security_check_cookie
0x18007a305  mov     rbx, [rsp+70h+arg_18]
0x18007a30d  add     rsp, 70h
0x18007a311  pop     r15
0x18007a313  pop     r14
0x18007a315  pop     rdi
0x18007a316  pop     rsi
0x18007a317  pop     rbp
0x18007a318  retn
0x18007a319  call    cs:__imp_CloseHandle
0x18007a31f  jmp     short loc_18007A2DC
0x18007a321  call    cs:__imp_GetLastError
0x18007a327  mov     ebx, eax
0x18007a329  test    eax, eax
0x18007a32b  jle     short loc_18007A2ED
0x18007a32d  movzx   ebx, ax
0x18007a330  or      ebx, 80070000h
0x18007a336  jmp     short loc_18007A2ED
0x18007a338  mov     rcx, [rbp+28h]; this
0x18007a33c  mov     r9d, ebx; char *
0x18007a33f  lea     r8, aOnecoreuapBase_91; "onecoreuap\\base\\appmodel\\search\\com"...
0x18007a346  mov     edx, 136h; void *
0x18007a34b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a350  jmp     short loc_18007A2F7
```
