# CUserLogonProcessingList::GetDefaultConnectedIdentityProviderGuid(_GUID *)

- ea: `0x1800543b8`
- end: `0x18005462e`
- name: `?GetDefaultConnectedIdentityProviderGuid@CUserLogonProcessingList@@KAJPEAU_GUID@@@Z`
- size: `630`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800263fc`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18002b6ac`
- `0x18002f86c`
- `0x180034070`
- `0x1800543b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800545e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800545e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054463`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054463`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x18005441b`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x18005441b`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18005444a`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1800544e4`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18005444a`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1800544e4`

## pseudocode

```c
__int64 __fastcall CUserLogonProcessingList::GetDefaultConnectedIdentityProviderGuid(struct _GUID *a1)
{
  _BYTE *v1; // rsi
  int DefaultIdentityProvider; // eax
  signed int v4; // edi
  _BYTE *v5; // rax
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  int IdentityProviderInfoByGUID; // eax
  unsigned int FirstConnectedIdentityProviderGuid; // eax
  const char *v11; // [rsp+28h] [rbp-60h]
  SIZE_T cb; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v13; // [rsp+38h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v1 = 0;
  v13 = 0;
  LODWORD(cb) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 269, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  DefaultIdentityProvider = GetDefaultIdentityProvider(&v13);
  v4 = DefaultIdentityProvider;
  if ( DefaultIdentityProvider > 0 )
    v4 = (unsigned __int16)DefaultIdentityProvider | 0x80070000;
  if ( v4 < 0 || (unsigned int)GetIdentityProviderInfoByGUID(&v13, 0, &cb) != 122 )
    goto LABEL_20;
  v5 = CoTaskMemAlloc((unsigned int)cb);
  v1 = v5;
  if ( v5 )
  {
    IdentityProviderInfoByGUID = GetIdentityProviderInfoByGUID(&v13, v5, &cb);
    v6 = IdentityProviderInfoByGUID;
    if ( IdentityProviderInfoByGUID )
    {
      if ( IdentityProviderInfoByGUID > 0 )
        v6 = (unsigned __int16)IdentityProviderInfoByGUID | 0x80070000;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xF10,
        (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
        (const char *)v6,
        (int)"GetIdentityProviderInfoByGUID2",
        v11);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 271, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v6);
      goto LABEL_27;
    }
    if ( (v1[32] & 1) != 0 )
    {
      v6 = v4;
      *a1 = v13;
LABEL_27:
      CoTaskMemFree(v1);
      goto LABEL_28;
    }
LABEL_20:
    FirstConnectedIdentityProviderGuid = CUserLogonProcessingList::GetFirstConnectedIdentityProviderGuid(&v13);
    v6 = FirstConnectedIdentityProviderGuid;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        272,
        &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
        FirstConnectedIdentityProviderGuid);
    if ( (v6 & 0x80000000) == 0 )
      *a1 = v13;
    else
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xF26,
        (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
        (const char *)v6,
        (int)"GetFirstConnectedIdentityProviderGuid",
        v11);
    if ( !v1 )
      goto LABEL_28;
    goto LABEL_27;
  }
  v6 = -2147024882;
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)0xF08,
    (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
    (const char *)0x8007000ELL,
    (int)"OutOfMemory",
    v11);
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 270, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, 2147942414LL);
LABEL_28:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
    WPP_SF_(v7[2], 273, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  return v6;
}

```

## disassembly

```asm
0x1800543b8  push    rbx
0x1800543ba  push    rbp
0x1800543bb  push    rsi
0x1800543bc  push    rdi
0x1800543bd  push    r12
0x1800543bf  push    r15
0x1800543c1  sub     rsp, 58h
0x1800543c5  mov     rax, cs:__security_cookie
0x1800543cc  xor     rax, rsp
0x1800543cf  mov     [rsp+88h+var_40], rax
0x1800543d4  xorps   xmm0, xmm0
0x1800543d7  xor     esi, esi
0x1800543d9  movups  xmmword ptr [rsp+88h+var_50.Data1], xmm0
0x1800543de  mov     dword ptr [rsp+88h+cb], esi
0x1800543e2  mov     rbp, rcx
0x1800543e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800543ec  lea     r12, WPP_GLOBAL_Control
0x1800543f3  lea     r15, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x1800543fa  cmp     rcx, r12
0x1800543fd  jz      short loc_180054416
0x1800543ff  test    byte ptr [rcx+1Ch], 20h
0x180054403  jz      short loc_180054416
0x180054405  mov     rcx, [rcx+10h]
0x180054409  mov     edx, 10Dh
0x18005440e  mov     r8, r15
0x180054411  call    WPP_SF_
0x180054416  lea     rcx, [rsp+88h+var_50]
0x18005441b  call    cs:__imp_GetDefaultIdentityProvider
0x180054422  nop     dword ptr [rax+rax+00h]
0x180054427  mov     edi, eax
0x180054429  test    eax, eax
0x18005442b  jle     short loc_180054436
0x18005442d  movzx   edi, ax
0x180054430  or      edi, 80070000h
0x180054436  test    edi, edi
0x180054438  js      loc_180054570
0x18005443e  lea     r8, [rsp+88h+cb]
0x180054443  xor     edx, edx
0x180054445  lea     rcx, [rsp+88h+var_50]
0x18005444a  call    cs:__imp_GetIdentityProviderInfoByGUID
0x180054451  nop     dword ptr [rax+rax+00h]
0x180054456  cmp     eax, 7Ah ; 'z'
0x180054459  jnz     loc_180054570
0x18005445f  mov     ecx, dword ptr [rsp+88h+cb]; cb
0x180054463  call    cs:__imp_CoTaskMemAlloc
0x18005446a  nop     dword ptr [rax+rax+00h]
0x18005446f  mov     rsi, rax
0x180054472  test    rax, rax
0x180054475  jnz     short loc_1800544D7
0x180054477  mov     rcx, [rsp+88h]; this
0x18005447f  lea     rax, aOutofmemory; "OutOfMemory"
0x180054486  mov     ebx, 8007000Eh
0x18005448b  mov     qword ptr [rsp+88h+var_68], rax; int
0x180054490  mov     r9d, ebx; char *
0x180054493  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x18005449a  mov     edx, 0F08h; void *
0x18005449f  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800544a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800544ab  cmp     rcx, r12
0x1800544ae  jz      loc_180054611
0x1800544b4  test    byte ptr [rcx+1Ch], 40h
0x1800544b8  jz      loc_1800545F5
0x1800544be  mov     rcx, [rcx+10h]
0x1800544c2  mov     edx, 10Eh
0x1800544c7  mov     r9d, ebx
0x1800544ca  mov     r8, r15
0x1800544cd  call    WPP_SF_d
0x1800544d2  jmp     loc_1800545EE
0x1800544d7  lea     r8, [rsp+88h+cb]
0x1800544dc  mov     rdx, rsi
0x1800544df  lea     rcx, [rsp+88h+var_50]
0x1800544e4  call    cs:__imp_GetIdentityProviderInfoByGUID
0x1800544eb  nop     dword ptr [rax+rax+00h]
0x1800544f0  mov     ebx, eax
0x1800544f2  test    eax, eax
0x1800544f4  jz      short loc_18005455C
0x1800544f6  jle     short loc_180054501
0x1800544f8  movzx   ebx, ax
0x1800544fb  or      ebx, 80070000h
0x180054501  mov     rcx, [rsp+88h]; this
0x180054509  lea     rax, aGetidentitypro_0; "GetIdentityProviderInfoByGUID2"
0x180054510  mov     r9d, ebx; char *
0x180054513  mov     qword ptr [rsp+88h+var_68], rax; int
0x180054518  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x18005451f  mov     edx, 0F10h; void *
0x180054524  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180054529  mov     rcx, cs:WPP_GLOBAL_Control
0x180054530  cmp     rcx, r12
0x180054533  jz      loc_1800545DF
0x180054539  test    byte ptr [rcx+1Ch], 40h
0x18005453d  jz      loc_1800545DF
0x180054543  mov     rcx, [rcx+10h]
0x180054547  mov     edx, 10Fh
0x18005454c  mov     r9d, ebx
0x18005454f  mov     r8, r15
0x180054552  call    WPP_SF_d
0x180054557  jmp     loc_1800545DF
0x18005455c  test    byte ptr [rsi+20h], 1
0x180054560  jz      short loc_180054570
0x180054562  movups  xmm0, xmmword ptr [rsp+88h+var_50.Data1]
0x180054567  mov     ebx, edi
0x180054569  movdqu  xmmword ptr [rbp+0], xmm0
0x18005456e  jmp     short loc_1800545DF
0x180054570  lea     rcx, [rsp+88h+var_50]; struct _GUID *
0x180054575  call    ?GetFirstConnectedIdentityProviderGuid@CUserLogonProcessingList@@KAJPEAU_GUID@@@Z; CUserLogonProcessingList::GetFirstConnectedIdentityProviderGuid(_GUID *)
0x18005457a  mov     ebx, eax
0x18005457c  mov     rcx, cs:WPP_GLOBAL_Control
0x180054583  cmp     rcx, r12
0x180054586  jz      short loc_1800545A2
0x180054588  test    byte ptr [rcx+1Ch], 40h
0x18005458c  jz      short loc_1800545A2
0x18005458e  mov     rcx, [rcx+10h]
0x180054592  mov     edx, 110h
0x180054597  mov     r9d, eax
0x18005459a  mov     r8, r15
0x18005459d  call    WPP_SF_d
0x1800545a2  test    ebx, ebx
0x1800545a4  jns     short loc_1800545D0
0x1800545a6  mov     rcx, [rsp+88h]; this
0x1800545ae  lea     rax, aGetfirstconnec; "GetFirstConnectedIdentityProviderGuid"
0x1800545b5  mov     r9d, ebx; char *
0x1800545b8  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800545bd  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x1800545c4  mov     edx, 0F26h; void *
0x1800545c9  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800545ce  jmp     short loc_1800545DA
0x1800545d0  movups  xmm0, xmmword ptr [rsp+88h+var_50.Data1]
0x1800545d5  movdqu  xmmword ptr [rbp+0], xmm0
0x1800545da  test    rsi, rsi
0x1800545dd  jz      short loc_1800545EE
0x1800545df  mov     rcx, rsi; pv
0x1800545e2  call    cs:__imp_CoTaskMemFree
0x1800545e9  nop     dword ptr [rax+rax+00h]
0x1800545ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800545f5  cmp     rcx, r12
0x1800545f8  jz      short loc_180054611
0x1800545fa  test    byte ptr [rcx+1Ch], 20h
0x1800545fe  jz      short loc_180054611
0x180054600  mov     rcx, [rcx+10h]
0x180054604  mov     edx, 111h
0x180054609  mov     r8, r15
0x18005460c  call    WPP_SF_
0x180054611  mov     eax, ebx
0x180054613  mov     rcx, [rsp+88h+var_40]
0x180054618  xor     rcx, rsp; StackCookie
0x18005461b  call    __security_check_cookie
0x180054620  add     rsp, 58h
0x180054624  pop     r15
0x180054626  pop     r12
0x180054628  pop     rdi
0x180054629  pop     rsi
0x18005462a  pop     rbp
0x18005462b  pop     rbx
0x18005462c  retn
```
