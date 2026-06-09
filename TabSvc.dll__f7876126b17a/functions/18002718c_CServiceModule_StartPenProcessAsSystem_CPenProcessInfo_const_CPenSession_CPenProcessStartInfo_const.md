# CServiceModule::StartPenProcessAsSystem(CPenProcessInfo const *,CPenSession *,CPenProcessStartInfo const *)

- ea: `0x18002718c`
- end: `0x180027417`
- name: `?StartPenProcessAsSystem@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEBUCPenProcessStartInfo@@@Z`
- size: `651`
- prototype: `void __fastcall(CServiceModule *__hidden this, const struct CPenProcessInfo *, struct CPenSession *, const struct CPenProcessStartInfo *)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f0fc`
- `0x18001506c`
- `0x1800244ec`

## callees

- `0x180001008`
- `0x180001778`
- `0x180001d08`
- `0x180014d40`
- `0x180015630`
- `0x18002718c`
- `0x18002b378`
- `0x18002b3a8`
- `0x18002b574`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180027294`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180027294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800272e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800272e1`

## string_xrefs

- `0x1800271c6`: `PENSERVICE_CServiceModule::StartPenProcessAsSystem`
- `0x18002732e`: `PENSERVICE_CServiceModule::StartPenProcessAsSystem`
- `0x180027388`: `PENSERVICE_CServiceModule::StartPenProcessAsSystem`
- `0x1800273b1`: `PENSERVICE_CServiceModule::StartPenProcessAsSystem`
- `0x1800272f1`: `SetTokenInformation failed.`

## pseudocode

```c
void __fastcall CServiceModule::StartPenProcessAsSystem(
        CServiceModule *this,
        const struct CPenProcessInfo *a2,
        struct CPenSession *a3,
        const struct CPenProcessStartInfo *a4)
{
  struct _GUID *v8; // rcx
  int v9; // ecx
  int v10; // r9d
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // [rsp+40h] [rbp-28h] BYREF
  int v18; // [rsp+44h] [rbp-24h] BYREF
  int TokenInformation; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v20[3]; // [rsp+50h] [rbp-18h] BYREF
  const char *v21; // [rsp+A8h] [rbp+40h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      25,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::StartPenProcessAsSystem");
    v8 = WPP_GLOBAL_Control;
  }
  if ( a2 && a3 )
  {
    if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    {
      LOBYTE(v21) = *((_BYTE *)this + 64);
      v17 = *((_DWORD *)this + 17);
      v18 = *((_DWORD *)a3 + 1);
      v20[0] = *((_QWORD *)a2 + 68);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        v9,
        (unsigned int)word_180039EC2,
        (_DWORD)a3,
        v10,
        (__int64)v20,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v21);
    }
    TokenInformation = *((_DWORD *)a3 + 1);
    if ( (a2 == *((const struct CPenProcessInfo **)this + 74) || a2 == *((const struct CPenProcessInfo **)this + 75))
      && !SetTokenInformation(*((HANDLE *)this + 6), TokenSessionId, &TokenInformation, 4u) )
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
        WPP_SF_(*(_QWORD *)&WPP_GLOBAL_Control[1].Data1);
      if ( (unsigned int)dword_1800411A8 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
        {
          LODWORD(v21) = GetLastError();
          v20[0] = "SetTokenInformation failed.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v11,
            (unsigned int)&byte_18003930F,
            v12,
            v13,
            (__int64)v20,
            (__int64)&v21);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_sSl(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          28,
          (_DWORD)a3,
          (unsigned int)"PENSERVICE_CServiceModule::StartPenProcessAsSystem",
          *((_QWORD *)a2 + 68),
          *((_DWORD *)a3 + 1));
      CServiceModule::StartPenProcessCore(this, a2, a3, *((void **)this + 6), a4);
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          29,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::StartPenProcessAsSystem");
    }
  }
  else
  {
    if ( v8 != (struct _GUID *)&WPP_GLOBAL_Control && (v8[1].Data4[4] & 4) != 0 )
      WPP_SF_s(
        *(_QWORD *)&v8[1].Data1,
        26,
        WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
        "PENSERVICE_CServiceModule::StartPenProcessAsSystem");
    if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    {
      v21 = "NULL pInfo or pSession.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v14,
        (unsigned int)byte_1800396E3,
        v15,
        v16,
        (__int64)&v21);
    }
  }
}

```

## disassembly

```asm
0x18002718c  push    rbp
0x18002718e  push    rsi
0x18002718f  push    rdi
0x180027190  push    r12
0x180027192  push    r14
0x180027194  push    r15
0x180027196  mov     rbp, rsp
0x180027199  sub     rsp, 68h
0x18002719d  mov     r15, r9
0x1800271a0  mov     r14, r8
0x1800271a3  mov     rdi, rdx
0x1800271a6  mov     rsi, rcx
0x1800271a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271b0  lea     r12, WPP_GLOBAL_Control
0x1800271b7  cmp     rcx, r12
0x1800271ba  jz      short loc_1800271E5
0x1800271bc  test    byte ptr [rcx+1Ch], 10h
0x1800271c0  jz      short loc_1800271E5
0x1800271c2  mov     rcx, [rcx+10h]
0x1800271c6  lea     r9, aPenserviceCser_15; "PENSERVICE_CServiceModule::StartPenProc"...
0x1800271cd  mov     edx, 19h
0x1800271d2  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800271d9  call    WPP_SF_s
0x1800271de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271e5  test    rdi, rdi
0x1800271e8  jz      loc_1800273A2
0x1800271ee  test    r14, r14
0x1800271f1  jz      loc_1800273A2
0x1800271f7  mov     eax, cs:dword_1800411A8
0x1800271fd  cmp     eax, 5
0x180027200  jbe     short loc_180027265
0x180027202  mov     edx, 4000000h
0x180027207  lea     rcx, dword_1800411A8
0x18002720e  call    _tlgKeywordOn
0x180027213  test    al, al
0x180027215  jz      short loc_180027265
0x180027217  mov     al, [rsi+40h]
0x18002721a  lea     rdx, word_180039EC2
0x180027221  mov     byte ptr [rbp+arg_8], al
0x180027224  mov     eax, [rsi+44h]
0x180027227  mov     [rbp+var_28], eax
0x18002722a  mov     eax, [r14+4]
0x18002722e  mov     [rbp+var_24], eax
0x180027231  mov     rax, [rdi+220h]
0x180027238  mov     [rbp+var_18], rax
0x18002723c  lea     rax, [rbp+arg_8]
0x180027240  mov     [rsp+68h+var_30], rax
0x180027245  lea     rax, [rbp+var_28]
0x180027249  mov     [rsp+68h+var_38], rax
0x18002724e  lea     rax, [rbp+var_24]
0x180027252  mov     [rsp+68h+var_40], rax
0x180027257  lea     rax, [rbp+var_18]
0x18002725b  mov     [rsp+68h+var_48], rax
0x180027260  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180027265  mov     eax, [r14+4]
0x180027269  mov     [rbp+TokenInformation], eax
0x18002726c  cmp     rdi, [rsi+250h]
0x180027273  jz      short loc_180027282
0x180027275  cmp     rdi, [rsi+258h]
0x18002727c  jnz     loc_180027318
0x180027282  mov     rcx, [rsi+30h]; TokenHandle
0x180027286  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002728a  mov     r9d, 4; TokenInformationLength
0x180027290  lea     edx, [r9+8]; TokenInformationClass
0x180027294  call    cs:__imp_SetTokenInformation
0x18002729a  test    eax, eax
0x18002729c  jnz     short loc_180027318
0x18002729e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800272a5  cmp     rcx, r12
0x1800272a8  jz      short loc_1800272B9
0x1800272aa  test    byte ptr [rcx+1Ch], 4
0x1800272ae  jz      short loc_1800272B9
0x1800272b0  mov     rcx, [rcx+10h]
0x1800272b4  call    WPP_SF_
0x1800272b9  mov     eax, cs:dword_1800411A8
0x1800272bf  cmp     eax, 5
0x1800272c2  jbe     loc_180027409
0x1800272c8  mov     edx, 4000000h
0x1800272cd  lea     rcx, dword_1800411A8
0x1800272d4  call    _tlgKeywordOn
0x1800272d9  test    al, al
0x1800272db  jz      loc_180027409
0x1800272e1  call    cs:__imp_GetLastError
0x1800272e7  mov     dword ptr [rbp+arg_8], eax
0x1800272ea  lea     rdx, byte_18003930F
0x1800272f1  lea     rax, aSettokeninform; "SetTokenInformation failed."
0x1800272f8  mov     [rbp+var_18], rax
0x1800272fc  lea     rax, [rbp+arg_8]
0x180027300  mov     [rsp+68h+var_40], rax
0x180027305  lea     rax, [rbp+var_18]
0x180027309  mov     [rsp+68h+var_48], rax
0x18002730e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180027313  jmp     loc_180027409
0x180027318  mov     rcx, cs:WPP_GLOBAL_Control
0x18002731f  cmp     rcx, r12
0x180027322  jz      short loc_180027353
0x180027324  test    byte ptr [rcx+1Ch], 10h
0x180027328  jz      short loc_180027353
0x18002732a  mov     eax, [r14+4]
0x18002732e  lea     r9, aPenserviceCser_15; "PENSERVICE_CServiceModule::StartPenProc"...
0x180027335  mov     rcx, [rcx+10h]
0x180027339  mov     edx, 1Ch
0x18002733e  mov     dword ptr [rsp+68h+var_40], eax
0x180027342  mov     rax, [rdi+220h]
0x180027349  mov     [rsp+68h+var_48], rax
0x18002734e  call    WPP_SF_sSl
0x180027353  mov     r9, [rsi+30h]; void *
0x180027357  mov     r8, r14; struct CPenSession *
0x18002735a  mov     rdx, rdi; struct CPenProcessInfo *
0x18002735d  mov     [rsp+68h+var_48], r15; struct CPenProcessStartInfo *
0x180027362  mov     rcx, rsi; this
0x180027365  call    ?StartPenProcessCore@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEAXPEBUCPenProcessStartInfo@@@Z; CServiceModule::StartPenProcessCore(CPenProcessInfo const *,CPenSession *,void *,CPenProcessStartInfo const *)
0x18002736a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027371  cmp     rcx, r12
0x180027374  jz      loc_180027409
0x18002737a  test    byte ptr [rcx+1Ch], 10h
0x18002737e  jz      loc_180027409
0x180027384  mov     rcx, [rcx+10h]
0x180027388  lea     r9, aPenserviceCser_15; "PENSERVICE_CServiceModule::StartPenProc"...
0x18002738f  mov     edx, 1Dh
0x180027394  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18002739b  call    WPP_SF_s
0x1800273a0  jmp     short loc_180027409
0x1800273a2  cmp     rcx, r12
0x1800273a5  jz      short loc_1800273C9
0x1800273a7  test    byte ptr [rcx+1Ch], 4
0x1800273ab  jz      short loc_1800273C9
0x1800273ad  mov     rcx, [rcx+10h]
0x1800273b1  lea     r9, aPenserviceCser_15; "PENSERVICE_CServiceModule::StartPenProc"...
0x1800273b8  mov     edx, 1Ah
0x1800273bd  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800273c4  call    WPP_SF_s
0x1800273c9  mov     eax, cs:dword_1800411A8
0x1800273cf  cmp     eax, 5
0x1800273d2  jbe     short loc_180027409
0x1800273d4  mov     edx, 4000000h
0x1800273d9  lea     rcx, dword_1800411A8
0x1800273e0  call    _tlgKeywordOn
0x1800273e5  test    al, al
0x1800273e7  jz      short loc_180027409
0x1800273e9  lea     rax, aNullPinfoOrPse; "NULL pInfo or pSession."
0x1800273f0  mov     [rbp+arg_8], rax
0x1800273f4  lea     rdx, byte_1800396E3
0x1800273fb  lea     rax, [rbp+arg_8]
0x1800273ff  mov     [rsp+68h+var_48], rax
0x180027404  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180027409  add     rsp, 68h
0x18002740d  pop     r15
0x18002740f  pop     r14
0x180027411  pop     r12
0x180027413  pop     rdi
0x180027414  pop     rsi
0x180027415  pop     rbp
0x180027416  retn
```
