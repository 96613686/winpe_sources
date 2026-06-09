# StateCreation::VerifyPermission(_ACL *,WELL_KNOWN_SID_TYPE,ulong)

- ea: `0x18007f050`
- end: `0x18007f388`
- name: `?VerifyPermission@StateCreation@@AEAAJPEAU_ACL@@W4WELL_KNOWN_SID_TYPE@@K@Z`
- size: `824`
- prototype: `int(StateCreation *__hidden this, struct _ACL *, enum WELL_KNOWN_SID_TYPE, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801f16ac`

## callees

- `0x18000e6e0`
- `0x1800138e0`
- `0x18007f050`
- `0x18007f390`
- `0x18007f3ac`
- `0x1800a219c`
- `0x1800a5970`
- `0x1800a8f80`
- `0x1800a8fc8`
- `0x1800aa988`
- `0x1800f0700`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007f2d4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007f2d4`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18007f12f`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18007f255`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18007f12f`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18007f255`
- `ntdll!RtlFreeUnicodeString` at `0x18007f170`
- `ntdll!RtlFreeUnicodeString` at `0x18007f296`
- `ntdll!RtlFreeUnicodeString` at `0x18007f170`
- `ntdll!RtlFreeUnicodeString` at `0x18007f296`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007f0d7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007f0d7`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18007f1e3`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18007f1e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007f084`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007f084`

## string_xrefs

- `0x18007f140`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x18007f266`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x18007f0ea`: `CreateWellKnownSid %u`
- `0x18007f183`: `ConvertSidToString %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall StateCreation::VerifyPermission(StateCreation *this, struct _ACL *a2, enum WELL_KNOWN_SID_TYPE a3)
{
  Common *v5; // rax
  Common *v6; // rbx
  void *v7; // rdx
  unsigned int LastErrorMsg; // edi
  void *v10; // rdx
  NTSTATUS v11; // eax
  void *v12; // rdx
  DWORD v13; // r14d
  char *v14; // rsi
  _BOOL8 Ace; // rdi
  _DWORD *v16; // r13
  int v17; // edi
  NTSTATUS v18; // eax
  WCHAR *v19; // rdi
  void *v20; // rdx
  void *v21; // rdx
  const char *bIgnoreCase; // [rsp+20h] [rbp-60h]
  int bIgnoreCasea; // [rsp+20h] [rbp-60h]
  char *v24; // [rsp+28h] [rbp-58h]
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-40h] BYREF
  LPCWCH lpString2[2]; // [rsp+50h] [rbp-30h] BYREF
  int v27; // [rsp+60h] [rbp-20h]
  LPCWCH lpString1[2]; // [rsp+68h] [rbp-18h] BYREF
  int v29; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  LPVOID pAce; // [rsp+C0h] [rbp+40h] BYREF
  DWORD cbSid; // [rsp+D8h] [rbp+58h] BYREF

  pAce = this;
  cbSid = 68;
  v5 = (Common *)LocalAlloc(0, 0x44u);
  v6 = v5;
  if ( !v5 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3D3,
      (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
      (const char *)0x8007000ELL,
      (int)"LocalAlloc",
      v24);
    Common::AutoHandleFreeHLocal(0, v7);
    return 2147942414LL;
  }
  if ( !CreateWellKnownSid(a3, 0, v5, &cbSid) )
  {
    LODWORD(bIgnoreCase) = a3;
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x3D5,
                     (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
                     "CreateWellKnownSid %u",
                     bIgnoreCase);
    Common::AutoHandleFreeHLocal(v6, v10);
    return LastErrorMsg;
  }
  *(_OWORD *)lpString2 = 0;
  v27 = 0;
  UnicodeString = 0;
  v11 = RtlConvertSidToUnicodeString(&UnicodeString, v6, 1u);
  if ( v11 >= 0 )
  {
    LastErrorMsg = Common::StringBuffer::SetValue(
                     (Common::StringBuffer *)lpString2,
                     UnicodeString.Buffer,
                     UnicodeString.Length >> 1);
    RtlFreeUnicodeString(&UnicodeString);
  }
  else
  {
    LastErrorMsg = wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)0x1E,
                     (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
                     (const char *)(unsigned int)v11,
                     (int)bIgnoreCase);
  }
  if ( (LastErrorMsg & 0x80000000) != 0 )
  {
    LODWORD(v24) = a3;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3D9,
      (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
      (const char *)LastErrorMsg,
      (int)"ConvertSidToString %u",
      v24);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpString2);
    Common::AutoHandleFreeHLocal(v6, v12);
    return LastErrorMsg;
  }
  v13 = 0;
  v14 = (char *)lpString2[1];
  while ( 1 )
  {
    if ( v13 >= a2->AceCount )
    {
      LastErrorMsg = wil::details::in1diag3::Return_Win32Msg(
                       retaddr,
                       (void *)0x3F1,
                       (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
                       (const char *)0x490,
                       (unsigned int)"User %ls 0x%0x",
                       v14,
                       983103);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpString2);
      Common::AutoHandleFreeHLocal(v6, v21);
      return LastErrorMsg;
    }
    pAce = 0;
    Ace = GetAce(a2, v13, &pAce);
    wil::details::in1diag3::Log_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x3DF,
      (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
      (const char *)Ace,
      (int)"GetAce %ls %u",
      v14);
    v16 = pAce;
    if ( *(_BYTE *)pAce == 0 && Ace )
      break;
LABEL_23:
    ++v13;
  }
  *(_OWORD *)lpString1 = 0;
  v29 = 0;
  if ( pAce == (LPVOID)-8LL )
  {
    v17 = -2147024809;
  }
  else
  {
    UnicodeString = 0;
    v18 = RtlConvertSidToUnicodeString(&UnicodeString, (char *)pAce + 8, 1u);
    if ( v18 >= 0 )
    {
      v17 = Common::StringBuffer::SetValue(
              (Common::StringBuffer *)lpString1,
              UnicodeString.Buffer,
              UnicodeString.Length >> 1);
      RtlFreeUnicodeString(&UnicodeString);
    }
    else
    {
      v17 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x1E,
              (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
              (const char *)(unsigned int)v18,
              bIgnoreCasea);
    }
  }
  if ( v17 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3E5,
      (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
      (const char *)(unsigned int)v17,
      bIgnoreCasea);
LABEL_22:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpString1);
    goto LABEL_23;
  }
  v19 = (WCHAR *)lpString1[1];
  if ( CompareStringOrdinal(lpString1[1], -1, (LPCWCH)v14, -1, 1) != 2 || v16[1] != 983103 )
    goto LABEL_22;
  if ( v19 )
    operator delete(v19, (unsigned __int64)v20);
  if ( v14 )
    operator delete(v14, (unsigned __int64)v20);
  Common::AutoHandleFreeHLocal(v6, v20);
  return 0;
}

```

## disassembly

```asm
0x18007f050  mov     [rsp-38h+arg_8], rbx
0x18007f055  mov     [rsp-38h+cbSid], r9d
0x18007f05a  mov     [rsp-38h+pAce], rcx
0x18007f05f  push    rbp
0x18007f060  push    rsi
0x18007f061  push    rdi
0x18007f062  push    r12
0x18007f064  push    r13
0x18007f066  push    r14
0x18007f068  push    r15
0x18007f06a  mov     rbp, rsp
0x18007f06d  sub     rsp, 80h
0x18007f074  mov     r15d, r8d
0x18007f077  mov     r12, rdx
0x18007f07a  mov     edx, 44h ; 'D'; uBytes
0x18007f07f  mov     [rbp+cbSid], edx
0x18007f082  xor     ecx, ecx; uFlags
0x18007f084  call    cs:__imp_LocalAlloc
0x18007f08a  mov     rbx, rax
0x18007f08d  test    rax, rax
0x18007f090  jnz     short loc_18007F0CB
0x18007f092  mov     rcx, [rbp+38h]; this
0x18007f096  lea     rax, aLocalalloc; "LocalAlloc"
0x18007f09d  mov     qword ptr [rsp+80h+bIgnoreCase], rax; int
0x18007f0a2  mov     ebx, 8007000Eh
0x18007f0a7  mov     r9d, ebx; char *
0x18007f0aa  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x18007f0b1  mov     edx, 3D3h; void *
0x18007f0b6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007f0bb  nop
0x18007f0bc  xor     ecx, ecx; this
0x18007f0be  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x18007f0c3  nop
0x18007f0c4  mov     eax, ebx
0x18007f0c6  jmp     loc_18007F36D
0x18007f0cb  lea     r9, [rbp+cbSid]; cbSid
0x18007f0cf  mov     r8, rbx; pSid
0x18007f0d2  xor     edx, edx; DomainSid
0x18007f0d4  mov     ecx, r15d; WellKnownSidType
0x18007f0d7  call    cs:__imp_CreateWellKnownSid
0x18007f0dd  test    eax, eax
0x18007f0df  jnz     short loc_18007F112
0x18007f0e1  mov     rcx, [rbp+38h]; this
0x18007f0e5  mov     [rsp+80h+bIgnoreCase], r15d; char *
0x18007f0ea  lea     r9, aCreatewellknow; "CreateWellKnownSid %u"
0x18007f0f1  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x18007f0f8  mov     edx, 3D5h; void *
0x18007f0fd  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18007f102  mov     edi, eax
0x18007f104  mov     rcx, rbx; this
0x18007f107  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x18007f10c  nop
0x18007f10d  jmp     loc_18007F36B
0x18007f112  xor     eax, eax
0x18007f114  xorps   xmm0, xmm0
0x18007f117  movups  xmmword ptr [rbp+lpString2], xmm0
0x18007f11b  mov     [rbp+var_20], eax
0x18007f11e  xorps   xmm1, xmm1
0x18007f121  movups  xmmword ptr [rbp+UnicodeString.Length], xmm1
0x18007f125  mov     r8b, 1; AllocateDestinationString
0x18007f128  mov     rdx, rbx; Sid
0x18007f12b  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18007f12f  call    cs:__imp_RtlConvertSidToUnicodeString
0x18007f135  test    eax, eax
0x18007f137  jns     short loc_18007F155
0x18007f139  mov     rcx, [rbp+38h]; this
0x18007f13d  mov     r9d, eax; char *
0x18007f140  lea     r8, aOnecoreBaseApp_65; "onecore\\base\\appmodel\\common\\sidhel"...
0x18007f147  mov     edx, 1Eh; void *
0x18007f14c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007f151  mov     edi, eax
0x18007f153  jmp     short loc_18007F176
0x18007f155  movzx   r8d, [rbp+UnicodeString.Length]
0x18007f15a  shr     r8d, 1; unsigned int
0x18007f15d  mov     rdx, [rbp+UnicodeString.Buffer]; unsigned __int16 *
0x18007f161  lea     rcx, [rbp+lpString2]; this
0x18007f165  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x18007f16a  mov     edi, eax
0x18007f16c  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18007f170  call    cs:__imp_RtlFreeUnicodeString
0x18007f176  test    edi, edi
0x18007f178  jns     short loc_18007F1BB
0x18007f17a  mov     rcx, [rbp+38h]; this
0x18007f17e  mov     dword ptr [rsp+80h+var_58], r15d; char *
0x18007f183  lea     rax, aConvertsidtost_0; "ConvertSidToString %u"
0x18007f18a  mov     qword ptr [rsp+80h+bIgnoreCase], rax; int
0x18007f18f  mov     r9d, edi; char *
0x18007f192  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x18007f199  mov     edx, 3D9h; void *
0x18007f19e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007f1a3  lea     rcx, [rbp+lpString2]; this
0x18007f1a7  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18007f1ac  nop
0x18007f1ad  mov     rcx, rbx; this
0x18007f1b0  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x18007f1b5  nop
0x18007f1b6  jmp     loc_18007F36B
0x18007f1bb  xor     r14d, r14d
0x18007f1be  mov     rsi, [rbp+lpString2+8]
0x18007f1c2  movzx   eax, word ptr [r12+4]
0x18007f1c8  cmp     r14d, eax
0x18007f1cb  jnb     loc_18007F322
0x18007f1d1  mov     [rbp+pAce], 0
0x18007f1d9  lea     r8, [rbp+pAce]; pAce
0x18007f1dd  mov     edx, r14d; dwAceIndex
0x18007f1e0  mov     rcx, r12; pAcl
0x18007f1e3  call    cs:__imp_GetAce
0x18007f1e9  mov     edi, eax
0x18007f1eb  mov     rcx, [rbp+38h]; this
0x18007f1ef  mov     [rsp+80h+var_50], r15d
0x18007f1f4  mov     [rsp+80h+var_58], rsi; char *
0x18007f1f9  lea     rax, aGetaceLsU; "GetAce %ls %u"
0x18007f200  mov     qword ptr [rsp+80h+bIgnoreCase], rax; int
0x18007f205  mov     r9d, edi; char *
0x18007f208  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x18007f20f  mov     edx, 3DFh; void *
0x18007f214  call    ?Log_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Log_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18007f219  xor     ecx, ecx
0x18007f21b  mov     r13, [rbp+pAce]
0x18007f21f  cmp     [r13+0], cl
0x18007f223  setz    cl
0x18007f226  test    edi, ecx
0x18007f228  jz      loc_18007F2F2
0x18007f22e  xor     eax, eax
0x18007f230  xorps   xmm0, xmm0
0x18007f233  movups  xmmword ptr [rbp+lpString1], xmm0
0x18007f237  mov     [rbp+var_8], eax
0x18007f23a  lea     rdx, [r13+8]; Sid
0x18007f23e  test    rdx, rdx
0x18007f241  jnz     short loc_18007F24A
0x18007f243  mov     edi, 80070057h
0x18007f248  jmp     short loc_18007F29C
0x18007f24a  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18007f24e  mov     r8b, 1; AllocateDestinationString
0x18007f251  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18007f255  call    cs:__imp_RtlConvertSidToUnicodeString
0x18007f25b  test    eax, eax
0x18007f25d  jns     short loc_18007F27B
0x18007f25f  mov     rcx, [rbp+38h]; this
0x18007f263  mov     r9d, eax; char *
0x18007f266  lea     r8, aOnecoreBaseApp_65; "onecore\\base\\appmodel\\common\\sidhel"...
0x18007f26d  mov     edx, 1Eh; void *
0x18007f272  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007f277  mov     edi, eax
0x18007f279  jmp     short loc_18007F29C
0x18007f27b  movzx   r8d, [rbp+UnicodeString.Length]
0x18007f280  shr     r8d, 1; unsigned int
0x18007f283  mov     rdx, [rbp+UnicodeString.Buffer]; unsigned __int16 *
0x18007f287  lea     rcx, [rbp+lpString1]; this
0x18007f28b  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x18007f290  mov     edi, eax
0x18007f292  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18007f296  call    cs:__imp_RtlFreeUnicodeString
0x18007f29c  mov     rcx, [rbp+38h]; this
0x18007f2a0  test    edi, edi
0x18007f2a2  jns     short loc_18007F2BA
0x18007f2a4  mov     r9d, edi; char *
0x18007f2a7  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x18007f2ae  mov     edx, 3E5h; void *
0x18007f2b3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007f2b8  jmp     short loc_18007F2E9
0x18007f2ba  mov     [rsp+80h+bIgnoreCase], 1; bIgnoreCase
0x18007f2c2  or      eax, 0FFFFFFFFh
0x18007f2c5  mov     r9d, eax; cchCount2
0x18007f2c8  mov     r8, rsi; lpString2
0x18007f2cb  mov     edx, eax; cchCount1
0x18007f2cd  mov     rdi, [rbp+lpString1+8]
0x18007f2d1  mov     rcx, rdi; lpString1
0x18007f2d4  call    cs:__imp_CompareStringOrdinal
0x18007f2da  add     eax, 0FFFFFFFEh
0x18007f2dd  jnz     short loc_18007F2E9
0x18007f2df  cmp     dword ptr [r13+4], 0F003Fh
0x18007f2e7  jz      short loc_18007F2FA
0x18007f2e9  lea     rcx, [rbp+lpString1]; this
0x18007f2ed  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18007f2f2  inc     r14d
0x18007f2f5  jmp     loc_18007F1C2
0x18007f2fa  test    rdi, rdi
0x18007f2fd  jz      short loc_18007F307
0x18007f2ff  mov     rcx, rdi; void *
0x18007f302  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007f307  test    rsi, rsi
0x18007f30a  jz      short loc_18007F315
0x18007f30c  mov     rcx, rsi; void *
0x18007f30f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007f314  nop
0x18007f315  mov     rcx, rbx; this
0x18007f318  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x18007f31d  nop
0x18007f31e  xor     eax, eax
0x18007f320  jmp     short loc_18007F36D
0x18007f322  mov     rcx, [rbp+38h]; this
0x18007f326  mov     [rsp+80h+var_50], 0F003Fh
0x18007f32e  mov     [rsp+80h+var_58], rsi; char *
0x18007f333  lea     rax, aUserLs0x0x; "User %ls 0x%0x"
0x18007f33a  mov     qword ptr [rsp+80h+bIgnoreCase], rax; unsigned int
0x18007f33f  mov     r9d, 490h; char *
0x18007f345  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x18007f34c  mov     edx, 3F1h; void *
0x18007f351  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18007f356  mov     edi, eax
0x18007f358  lea     rcx, [rbp+lpString2]; this
0x18007f35c  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18007f361  nop
0x18007f362  mov     rcx, rbx; this
0x18007f365  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x18007f36a  nop
0x18007f36b  mov     eax, edi
0x18007f36d  mov     rbx, [rsp+80h+arg_8]
0x18007f375  add     rsp, 80h
0x18007f37c  pop     r15
0x18007f37e  pop     r14
0x18007f380  pop     r13
0x18007f382  pop     r12
0x18007f384  pop     rdi
0x18007f385  pop     rsi
0x18007f386  pop     rbp
0x18007f387  retn
```
