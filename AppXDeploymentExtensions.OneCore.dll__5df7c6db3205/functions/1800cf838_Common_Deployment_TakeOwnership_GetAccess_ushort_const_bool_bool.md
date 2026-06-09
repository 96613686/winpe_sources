# Common::Deployment::TakeOwnership::GetAccess(ushort const *,bool,bool)

- ea: `0x1800cf838`
- end: `0x1800cfaa6`
- name: `?GetAccess@TakeOwnership@Deployment@Common@@AEAAJPEBG_N1@Z`
- size: `622`
- prototype: `int(Common::Deployment::TakeOwnership *__hidden this, const unsigned __int16 *, bool, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800a8144`
- `0x1800cf228`

## callees

- `0x18007f390`
- `0x1800937d4`
- `0x1800a219c`
- `0x1800cf838`
- `0x1800cfaac`
- `0x1800cfaf4`
- `0x1800f0700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf961`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf961`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cf94d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cf94d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800cf932`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800cf932`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800cfa7e`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800cfa7e`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800cfa3c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800cfa3c`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1800cf9a1`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1800cf9a1`

## string_xrefs

- `0x1800cf89a`: `onecore\admin\appmodel\common\takeownership.cpp`
- `0x1800cf9ee`: `onecore\admin\appmodel\common\takeownership.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Common::Deployment::TakeOwnership::GetAccess(
        Common::Deployment::TakeOwnership *this,
        const unsigned __int16 *a2)
{
  int v4; // ebx
  wil::details::in1diag3 *v5; // rcx
  __int64 v6; // rdx
  unsigned __int64 v7; // r9
  void *v8; // rdx
  int v10; // eax
  HANDLE FileW; // rbx
  char *v12; // rcx
  signed int LastError; // eax
  PSECURITY_DESCRIPTOR v14; // rbx
  Common *v15; // rcx
  int CurrentUserSid; // eax
  unsigned int v17; // edi
  PSID v18; // rbx
  unsigned __int64 v19; // rdx
  signed int v20; // eax
  bool v21; // cc
  int dwCreationDisposition; // [rsp+20h] [rbp-39h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-39h]
  PSID psidOwner; // [rsp+40h] [rbp-19h] BYREF
  PACL NewAcl; // [rsp+48h] [rbp-11h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+50h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+C0h] [rbp+67h] BYREF

  NewAcl = 0;
  ppSecurityDescriptor = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  psidOwner = 0;
  v4 = Common::Deployment::Privilege::Initialize((PHANDLE)this + 10, 18);
  v5 = retaddr;
  if ( v4 < 0 )
  {
    v6 = 61;
LABEL_3:
    v7 = (unsigned int)v4;
LABEL_4:
    wil::details::in1diag3::_Log_Hr(
      v5,
      (void *)v6,
      (unsigned int)"onecore\\admin\\appmodel\\common\\takeownership.cpp",
      (const char *)v7,
      dwCreationDisposition);
LABEL_5:
    operator delete(0, (unsigned __int64)v8);
    return (unsigned int)v4;
  }
  v4 = Common::Deployment::Privilege::Initialize((PHANDLE)this + 5, 17);
  v5 = retaddr;
  if ( v4 < 0 )
  {
    v6 = 62;
    goto LABEL_3;
  }
  v4 = Common::Deployment::Privilege::Enable((Common::Deployment::TakeOwnership *)((char *)this + 80));
  v5 = retaddr;
  if ( v4 < 0 )
  {
    v6 = 63;
    goto LABEL_3;
  }
  v10 = Common::Deployment::Privilege::Enable((Common::Deployment::TakeOwnership *)((char *)this + 40));
  v4 = v10;
  v5 = retaddr;
  if ( v10 < 0 )
  {
    v7 = (unsigned int)v10;
    v6 = 64;
    goto LABEL_4;
  }
  FileW = CreateFileW(a2, 0xE0000u, 0, 0, 3u, 0x2000080u, 0);
  v12 = *(char **)this;
  if ( *(HANDLE *)this == FileW )
  {
    FileW = *(HANDLE *)this;
  }
  else
  {
    if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v12);
    *(_QWORD *)this = FileW;
  }
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
LABEL_20:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = LastError;
    goto LABEL_5;
  }
  LastError = GetSecurityInfo(
                FileW,
                SE_FILE_OBJECT,
                5u,
                (PSID *)this + 2,
                0,
                (PACL *)this + 1,
                0,
                &ppSecurityDescriptor);
  if ( LastError )
    goto LABEL_20;
  v14 = ppSecurityDescriptor;
  v15 = (Common *)*((_QWORD *)this + 3);
  if ( v15 != ppSecurityDescriptor )
  {
    Common::AutoHandleFreeHLocal(v15, v8);
    *((_QWORD *)this + 3) = v14;
  }
  CurrentUserSid = Common::SidHelper::GetCurrentUserSid(&psidOwner);
  v17 = CurrentUserSid;
  v18 = psidOwner;
  if ( CurrentUserSid >= 0 )
  {
    pListOfExplicitEntries.grfInheritance = 3;
    pListOfExplicitEntries.grfAccessPermissions = 269221888;
    pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
    pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
    *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)psidOwner;
    v20 = SetEntriesInAclW(1u, &pListOfExplicitEntries, *((PACL *)this + 1), &NewAcl);
    v21 = v20 <= 0;
    if ( v20 || (v20 = SetSecurityInfo(*(HANDLE *)this, SE_FILE_OBJECT, 5u, v18, 0, NewAcl, 0), v21 = v20 <= 0, v20) )
    {
      if ( !v21 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      v17 = v20;
    }
    else
    {
      *((_BYTE *)this + 32) = 1;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\admin\\appmodel\\common\\takeownership.cpp",
      (const char *)(unsigned int)CurrentUserSid,
      dwCreationDispositiona);
  }
  operator delete(v18, v19);
  return v17;
}

```

## disassembly

```asm
0x1800cf838  push    rbp
0x1800cf83a  push    rbx
0x1800cf83b  push    rsi
0x1800cf83c  push    rdi
0x1800cf83d  push    r14
0x1800cf83f  push    r15
0x1800cf841  lea     rbp, [rsp-2Fh]
0x1800cf846  sub     rsp, 88h
0x1800cf84d  mov     r15, rdx
0x1800cf850  mov     rsi, rcx
0x1800cf853  mov     [rbp+57h+NewAcl], 0
0x1800cf85b  mov     [rbp+57h+arg_0], 0
0x1800cf863  xorps   xmm0, xmm0
0x1800cf866  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x1800cf86a  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1800cf86e  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1800cf872  mov     [rbp+57h+psidOwner], 0
0x1800cf87a  mov     edx, 12h; int
0x1800cf87f  add     rcx, 50h ; 'P'; TokenHandle
0x1800cf883  call    ?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z; Common::Deployment::Privilege::Initialize(long)
0x1800cf888  mov     ebx, eax
0x1800cf88a  mov     rcx, [rbp+5Fh]; this
0x1800cf88e  test    eax, eax
0x1800cf890  jns     short loc_1800CF8B5
0x1800cf892  mov     edx, 3Dh ; '='; void *
0x1800cf897  mov     r9d, ebx; char *
0x1800cf89a  lea     r8, aOnecoreAdminAp_150; "onecore\\admin\\appmodel\\common\\takeo"...
0x1800cf8a1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cf8a6  nop
0x1800cf8a7  xor     ecx, ecx; void *
0x1800cf8a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cf8ae  mov     eax, ebx
0x1800cf8b0  jmp     loc_1800CFA96
0x1800cf8b5  mov     edx, 11h; int
0x1800cf8ba  lea     rcx, [rsi+28h]; TokenHandle
0x1800cf8be  call    ?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z; Common::Deployment::Privilege::Initialize(long)
0x1800cf8c3  mov     ebx, eax
0x1800cf8c5  mov     rcx, [rbp+5Fh]
0x1800cf8c9  test    eax, eax
0x1800cf8cb  jns     short loc_1800CF8D4
0x1800cf8cd  mov     edx, 3Eh ; '>'
0x1800cf8d2  jmp     short loc_1800CF897
0x1800cf8d4  lea     rcx, [rsi+50h]; this
0x1800cf8d8  call    ?Enable@Privilege@Deployment@Common@@QEAAJXZ; Common::Deployment::Privilege::Enable(void)
0x1800cf8dd  mov     ebx, eax
0x1800cf8df  mov     rcx, [rbp+5Fh]
0x1800cf8e3  test    eax, eax
0x1800cf8e5  jns     short loc_1800CF8EE
0x1800cf8e7  mov     edx, 3Fh ; '?'
0x1800cf8ec  jmp     short loc_1800CF897
0x1800cf8ee  lea     rcx, [rsi+28h]; this
0x1800cf8f2  call    ?Enable@Privilege@Deployment@Common@@QEAAJXZ; Common::Deployment::Privilege::Enable(void)
0x1800cf8f7  mov     ebx, eax
0x1800cf8f9  mov     rcx, [rbp+5Fh]
0x1800cf8fd  test    eax, eax
0x1800cf8ff  jns     short loc_1800CF90B
0x1800cf901  mov     r9d, eax
0x1800cf904  mov     edx, 40h ; '@'
0x1800cf909  jmp     short loc_1800CF89A
0x1800cf90b  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x1800cf914  mov     [rsp+0B0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x1800cf91c  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800cf924  xor     r9d, r9d; lpSecurityAttributes
0x1800cf927  xor     r8d, r8d; dwShareMode
0x1800cf92a  mov     edx, 0E0000h; dwDesiredAccess
0x1800cf92f  mov     rcx, r15; lpFileName
0x1800cf932  call    cs:__imp_CreateFileW
0x1800cf938  mov     rbx, rax
0x1800cf93b  mov     rcx, [rsi]; hObject
0x1800cf93e  cmp     rcx, rax
0x1800cf941  jz      short loc_1800CF958
0x1800cf943  lea     rax, [rcx-1]
0x1800cf947  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800cf94b  ja      short loc_1800CF953
0x1800cf94d  call    cs:__imp_CloseHandle
0x1800cf953  mov     [rsi], rbx
0x1800cf956  jmp     short loc_1800CF95B
0x1800cf958  mov     rbx, rcx
0x1800cf95b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800cf95f  jnz     short loc_1800CF969
0x1800cf961  call    cs:__imp_GetLastError
0x1800cf967  jmp     short loc_1800CF9AB
0x1800cf969  lea     r14, [rsi+8]
0x1800cf96d  lea     r9, [rsi+10h]; ppsidOwner
0x1800cf971  lea     rax, [rbp+57h+arg_0]
0x1800cf975  mov     [rsp+0B0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800cf97a  mov     [rsp+0B0h+hTemplateFile], 0; ppSacl
0x1800cf983  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r14; ppDacl
0x1800cf988  mov     qword ptr [rsp+0B0h+dwCreationDisposition], 0; int
0x1800cf991  mov     r8d, 5; SecurityInfo
0x1800cf997  lea     r15d, [r8-4]
0x1800cf99b  mov     edx, r15d; ObjectType
0x1800cf99e  mov     rcx, rbx; handle
0x1800cf9a1  call    cs:__imp_GetSecurityInfo
0x1800cf9a7  test    eax, eax
0x1800cf9a9  jz      short loc_1800CF9BE
0x1800cf9ab  test    eax, eax
0x1800cf9ad  jle     short loc_1800CF9B7
0x1800cf9af  movzx   eax, ax
0x1800cf9b2  or      eax, 80070000h
0x1800cf9b7  mov     ebx, eax
0x1800cf9b9  jmp     loc_1800CF8A7
0x1800cf9be  mov     rbx, [rbp+57h+arg_0]
0x1800cf9c2  mov     rcx, [rsi+18h]; this
0x1800cf9c6  cmp     rcx, rbx
0x1800cf9c9  jz      short loc_1800CF9D4
0x1800cf9cb  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x1800cf9d0  mov     [rsi+18h], rbx
0x1800cf9d4  lea     rcx, [rbp+57h+psidOwner]; void **
0x1800cf9d8  call    ?GetCurrentUserSid@SidHelper@Common@@SAJPEAPEAX@Z; Common::SidHelper::GetCurrentUserSid(void * *)
0x1800cf9dd  mov     edi, eax
0x1800cf9df  mov     rcx, [rbp+5Fh]; this
0x1800cf9e3  mov     rbx, [rbp+57h+psidOwner]
0x1800cf9e7  test    eax, eax
0x1800cf9e9  jns     short loc_1800CFA04
0x1800cf9eb  mov     r9d, eax; char *
0x1800cf9ee  lea     r8, aOnecoreAdminAp_150; "onecore\\admin\\appmodel\\common\\takeo"...
0x1800cf9f5  mov     edx, 72h ; 'r'; void *
0x1800cf9fa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cf9ff  jmp     loc_1800CFA8C
0x1800cfa04  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x1800cfa0b  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 100C0000h
0x1800cfa12  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], r15d
0x1800cfa16  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], 0
0x1800cfa1e  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], 0
0x1800cfa26  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], r15d
0x1800cfa2a  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rbx
0x1800cfa2e  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x1800cfa32  mov     r8, [r14]; OldAcl
0x1800cfa35  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800cfa39  mov     ecx, r15d; cCountOfExplicitEntries
0x1800cfa3c  call    cs:__imp_SetEntriesInAclW
0x1800cfa42  test    eax, eax
0x1800cfa44  jz      short loc_1800CFA54
0x1800cfa46  jle     short loc_1800CFA50
0x1800cfa48  movzx   eax, ax
0x1800cfa4b  or      eax, 80070000h
0x1800cfa50  mov     edi, eax
0x1800cfa52  jmp     short loc_1800CFA8C
0x1800cfa54  mov     rax, [rbp+57h+NewAcl]
0x1800cfa58  mov     [rsp+0B0h+hTemplateFile], 0; pSacl
0x1800cfa61  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax; pDacl
0x1800cfa66  mov     qword ptr [rsp+0B0h+dwCreationDisposition], 0; psidGroup
0x1800cfa6f  mov     r9, rbx; psidOwner
0x1800cfa72  mov     r8d, 5; SecurityInfo
0x1800cfa78  mov     edx, r15d; ObjectType
0x1800cfa7b  mov     rcx, [rsi]; handle
0x1800cfa7e  call    cs:__imp_SetSecurityInfo
0x1800cfa84  test    eax, eax
0x1800cfa86  jnz     short loc_1800CFA46
0x1800cfa88  mov     [rsi+20h], r15b
0x1800cfa8c  mov     rcx, rbx; void *
0x1800cfa8f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cfa94  mov     eax, edi
0x1800cfa96  add     rsp, 88h
0x1800cfa9d  pop     r15
0x1800cfa9f  pop     r14
0x1800cfaa1  pop     rdi
0x1800cfaa2  pop     rsi
0x1800cfaa3  pop     rbx
0x1800cfaa4  pop     rbp
0x1800cfaa5  retn
```
