# Common::Deployment::TakeOwnership::GetAccess(ushort const *,bool,bool)

- ea: `0x18001ffd0`
- end: `0x180020240`
- name: `?GetAccess@TakeOwnership@Deployment@Common@@AEAAJPEBG_N1@Z`
- size: `624`
- prototype: `__int64 __fastcall(Common::Deployment::TakeOwnership *this, const unsigned __int16 *, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002ff90`

## callees

- `0x180007a10`
- `0x180016118`
- `0x180017f50`
- `0x18001ffd0`
- `0x180020248`
- `0x180020290`
- `0x1800203e0`
- `0x18004a054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200eb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800200c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800200c7`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002012b`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002012b`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002020c`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002020c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800201ca`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800201ca`

## string_xrefs

- `0x18002003c`: `onecore\admin\appmodel\common\takeownership.cpp`
- `0x180020175`: `onecore\admin\appmodel\common\takeownership.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::TakeOwnership::GetAccess(
        Common::Deployment::TakeOwnership *this,
        const unsigned __int16 *a2,
        char a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  unsigned __int64 v8; // r9
  int v10; // eax
  void *v11; // rdx
  HANDLE FileW; // rbx
  signed int LastError; // eax
  void *v14; // rdx
  PSECURITY_DESCRIPTOR v15; // rbx
  Common *v16; // rcx
  int CurrentUserSid; // eax
  PSID v18; // rbx
  unsigned int v19; // edi
  struct _ACL *v20; // r8
  signed int v21; // eax
  bool v22; // cc
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  PSID psidOwner; // [rsp+40h] [rbp-40h] BYREF
  PACL NewAcl; // [rsp+48h] [rbp-38h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+B0h] [rbp+30h] BYREF

  NewAcl = 0;
  ppSecurityDescriptor = 0;
  psidOwner = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  v6 = Common::Deployment::Privilege::Initialize((PHANDLE)this + 10, 18);
  if ( v6 < 0 )
  {
    v7 = 61;
LABEL_3:
    v8 = (unsigned int)v6;
LABEL_4:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\admin\\appmodel\\common\\takeownership.cpp",
      (const char *)v8,
      dwCreationDisposition);
LABEL_5:
    Common::GlobalHeap::Free(0);
    return (unsigned int)v6;
  }
  v6 = Common::Deployment::Privilege::Initialize((PHANDLE)this + 5, 17);
  if ( v6 < 0 )
  {
    v7 = 62;
    goto LABEL_3;
  }
  v6 = Common::Deployment::Privilege::Enable((Common::Deployment::TakeOwnership *)((char *)this + 80));
  if ( v6 < 0 )
  {
    v7 = 63;
    goto LABEL_3;
  }
  v10 = Common::Deployment::Privilege::Enable((Common::Deployment::TakeOwnership *)((char *)this + 40));
  v6 = v10;
  if ( v10 < 0 )
  {
    v8 = (unsigned int)v10;
    v7 = 64;
    goto LABEL_4;
  }
  FileW = CreateFileW(a2, 0xE0000u, 0, 0, 3u, 0x2000080u, 0);
  if ( *(HANDLE *)this == FileW )
  {
    FileW = *(HANDLE *)this;
  }
  else
  {
    Common::CloseHandleHelper(*(Common **)this, v11);
    *(_QWORD *)this = FileW;
  }
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
LABEL_18:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = LastError;
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
    goto LABEL_18;
  v15 = ppSecurityDescriptor;
  v16 = (Common *)*((_QWORD *)this + 3);
  if ( v16 != ppSecurityDescriptor )
  {
    Common::AutoHandleFreeHLocal(v16, v14);
    *((_QWORD *)this + 3) = v15;
  }
  CurrentUserSid = Common::SidHelper::GetCurrentUserSid(&psidOwner);
  v18 = psidOwner;
  v19 = CurrentUserSid;
  if ( CurrentUserSid >= 0 )
  {
    v20 = (struct _ACL *)*((_QWORD *)this + 1);
    pListOfExplicitEntries.grfAccessPermissions = 269221888;
    pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
    pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
    *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
    pListOfExplicitEntries.grfInheritance = a3 != 0 ? 3 : 0;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)psidOwner;
    v21 = SetEntriesInAclW(1u, &pListOfExplicitEntries, v20, &NewAcl);
    v22 = v21 <= 0;
    if ( v21 || (v21 = SetSecurityInfo(*(HANDLE *)this, SE_FILE_OBJECT, 5u, v18, 0, NewAcl, 0), v22 = v21 <= 0, v21) )
    {
      if ( !v22 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      v19 = v21;
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
  Common::GlobalHeap::Free(v18);
  return v19;
}

```

## disassembly

```asm
0x18001ffd0  mov     [rsp-28h+arg_8], rbx
0x18001ffd5  mov     [rsp-28h+arg_10], rsi
0x18001ffda  push    rbp
0x18001ffdb  push    rdi
0x18001ffdc  push    r12
0x18001ffde  push    r14
0x18001ffe0  push    r15
0x18001ffe2  mov     rbp, rsp
0x18001ffe5  sub     rsp, 80h
0x18001ffec  xorps   xmm0, xmm0
0x18001ffef  mov     [rbp+NewAcl], 0
0x18001fff7  mov     r15, rdx
0x18001fffa  mov     [rbp+arg_0], 0
0x180020002  mov     rsi, rcx
0x180020005  mov     [rbp+psidOwner], 0
0x18002000d  mov     edx, 12h; int
0x180020012  add     rcx, 50h ; 'P'; TokenHandle
0x180020016  movups  xmmword ptr [rbp+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18002001a  mov     r12b, r8b
0x18002001d  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x180020021  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x180020025  call    ?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z; Common::Deployment::Privilege::Initialize(long)
0x18002002a  mov     ebx, eax
0x18002002c  test    eax, eax
0x18002002e  jns     short loc_180020056
0x180020030  mov     edx, 3Dh ; '='; void *
0x180020035  mov     r9d, ebx; char *
0x180020038  mov     rcx, [rbp+28h]; this
0x18002003c  lea     r8, aOnecoreAdminAp_23; "onecore\\admin\\appmodel\\common\\takeo"...
0x180020043  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020048  xor     ecx, ecx; void *
0x18002004a  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18002004f  mov     eax, ebx
0x180020051  jmp     loc_180020224
0x180020056  mov     edx, 11h; int
0x18002005b  lea     rcx, [rsi+28h]; TokenHandle
0x18002005f  call    ?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z; Common::Deployment::Privilege::Initialize(long)
0x180020064  mov     ebx, eax
0x180020066  test    eax, eax
0x180020068  jns     short loc_180020071
0x18002006a  mov     edx, 3Eh ; '>'
0x18002006f  jmp     short loc_180020035
0x180020071  lea     rcx, [rsi+50h]; this
0x180020075  call    ?Enable@Privilege@Deployment@Common@@QEAAJXZ; Common::Deployment::Privilege::Enable(void)
0x18002007a  mov     ebx, eax
0x18002007c  test    eax, eax
0x18002007e  jns     short loc_180020087
0x180020080  mov     edx, 3Fh ; '?'
0x180020085  jmp     short loc_180020035
0x180020087  lea     rcx, [rsi+28h]; this
0x18002008b  call    ?Enable@Privilege@Deployment@Common@@QEAAJXZ; Common::Deployment::Privilege::Enable(void)
0x180020090  mov     ebx, eax
0x180020092  test    eax, eax
0x180020094  jns     short loc_1800200A0
0x180020096  mov     r9d, eax
0x180020099  mov     edx, 40h ; '@'
0x18002009e  jmp     short loc_180020038
0x1800200a0  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x1800200a9  xor     r9d, r9d; lpSecurityAttributes
0x1800200ac  mov     [rsp+80h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x1800200b4  xor     r8d, r8d; dwShareMode
0x1800200b7  mov     edx, 0E0000h; dwDesiredAccess
0x1800200bc  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x1800200c4  mov     rcx, r15; lpFileName
0x1800200c7  call    cs:__imp_CreateFileW
0x1800200cd  mov     rbx, rax
0x1800200d0  cmp     [rsi], rax
0x1800200d3  jz      short loc_1800200E2
0x1800200d5  mov     rcx, [rsi]; this
0x1800200d8  call    ?CloseHandleHelper@Common@@YAXPEAX@Z; Common::CloseHandleHelper(void *)
0x1800200dd  mov     [rsi], rbx
0x1800200e0  jmp     short loc_1800200E5
0x1800200e2  mov     rbx, [rsi]
0x1800200e5  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800200e9  jnz     short loc_1800200F3
0x1800200eb  call    cs:__imp_GetLastError
0x1800200f1  jmp     short loc_180020135
0x1800200f3  mov     r8d, 5; SecurityInfo
0x1800200f9  lea     rax, [rbp+arg_0]
0x1800200fd  mov     [rsp+80h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180020102  lea     r14, [rsi+8]
0x180020106  mov     [rsp+80h+hTemplateFile], 0; ppSacl
0x18002010f  lea     r9, [rsi+10h]; ppsidOwner
0x180020113  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r14; ppDacl
0x180020118  mov     rcx, rbx; handle
0x18002011b  lea     r15d, [r8-4]
0x18002011f  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; int
0x180020128  mov     edx, r15d; ObjectType
0x18002012b  call    cs:__imp_GetSecurityInfo
0x180020131  test    eax, eax
0x180020133  jz      short loc_180020148
0x180020135  test    eax, eax
0x180020137  jle     short loc_180020141
0x180020139  movzx   eax, ax
0x18002013c  or      eax, 80070000h
0x180020141  mov     ebx, eax
0x180020143  jmp     loc_180020048
0x180020148  mov     rbx, [rbp+arg_0]
0x18002014c  mov     rcx, [rsi+18h]; this
0x180020150  cmp     rcx, rbx
0x180020153  jz      short loc_18002015E
0x180020155  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x18002015a  mov     [rsi+18h], rbx
0x18002015e  lea     rcx, [rbp+psidOwner]; void **
0x180020162  call    ?GetCurrentUserSid@SidHelper@Common@@SAJPEAPEAX@Z; Common::SidHelper::GetCurrentUserSid(void * *)
0x180020167  mov     rbx, [rbp+psidOwner]
0x18002016b  mov     edi, eax
0x18002016d  test    eax, eax
0x18002016f  jns     short loc_18002018E
0x180020171  mov     rcx, [rbp+28h]; this
0x180020175  lea     r8, aOnecoreAdminAp_23; "onecore\\admin\\appmodel\\common\\takeo"...
0x18002017c  mov     r9d, eax; char *
0x18002017f  mov     edx, 72h ; 'r'; void *
0x180020184  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020189  jmp     loc_18002021A
0x18002018e  mov     r8, [r14]; OldAcl
0x180020191  lea     r9, [rbp+NewAcl]; NewAcl
0x180020195  neg     r12b
0x180020198  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], 100C0000h
0x18002019f  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800201a3  mov     [rbp+pListOfExplicitEntries.grfAccessMode], r15d
0x1800201a7  sbb     eax, eax
0x1800201a9  mov     [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], 0
0x1800201b1  and     eax, 3
0x1800201b4  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], 0
0x1800201bc  mov     ecx, r15d; cCountOfExplicitEntries
0x1800201bf  mov     [rbp+pListOfExplicitEntries.grfInheritance], eax
0x1800201c2  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeType], r15d
0x1800201c6  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rbx
0x1800201ca  call    cs:__imp_SetEntriesInAclW
0x1800201d0  test    eax, eax
0x1800201d2  jz      short loc_1800201E2
0x1800201d4  jle     short loc_1800201DE
0x1800201d6  movzx   eax, ax
0x1800201d9  or      eax, 80070000h
0x1800201de  mov     edi, eax
0x1800201e0  jmp     short loc_18002021A
0x1800201e2  mov     rax, [rbp+NewAcl]
0x1800201e6  mov     r9, rbx; psidOwner
0x1800201e9  mov     rcx, [rsi]; handle
0x1800201ec  mov     r8d, 5; SecurityInfo
0x1800201f2  mov     [rsp+80h+hTemplateFile], 0; pSacl
0x1800201fb  mov     edx, r15d; ObjectType
0x1800201fe  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax; pDacl
0x180020203  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; psidGroup
0x18002020c  call    cs:__imp_SetSecurityInfo
0x180020212  test    eax, eax
0x180020214  jnz     short loc_1800201D4
0x180020216  mov     [rsi+20h], r15b
0x18002021a  mov     rcx, rbx; void *
0x18002021d  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180020222  mov     eax, edi
0x180020224  lea     r11, [rsp+80h+var_s0]
0x18002022c  mov     rbx, [r11+38h]
0x180020230  mov     rsi, [r11+40h]
0x180020234  mov     rsp, r11
0x180020237  pop     r15
0x180020239  pop     r14
0x18002023b  pop     r12
0x18002023d  pop     rdi
0x18002023e  pop     rbp
0x18002023f  retn
```
