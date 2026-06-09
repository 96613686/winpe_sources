# CProfileManager::LoadProfile(UserRecord *,void *,IRequestContext *)

- ea: `0x180180390`
- end: `0x180180751`
- name: `?LoadProfile@CProfileManager@@QEAAHPEAVUserRecord@@PEAXPEAVIRequestContext@@@Z`
- size: `961`
- prototype: `__int64 __fastcall(CProfileManager *this, struct UserRecord *, void *, struct IRequestContext *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180094470`

## callees

- `0x180005d10`
- `0x18002dd20`
- `0x180068b24`
- `0x180071400`
- `0x1800c6320`
- `0x180112380`
- `0x1801123a8`
- `0x180180390`
- `0x180180a38`
- `0x18018128c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801806e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801806e3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180180554`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180180554`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18018064e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18018064e`

## string_xrefs

- `0x180180403`: `onecore\admin\wmi\wmx\service\profilemanager.cpp`
- `0x1801804a3`: `onecore\admin\wmi\wmx\service\profilemanager.cpp`
- `0x180180548`: `onecore\admin\wmi\wmx\service\profilemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CProfileManager::LoadProfile(
        CProfileManager *this,
        struct UserRecord *a2,
        void *a3,
        struct IRequestContext *a4)
{
  __int64 v9; // rcx
  __int64 v10; // r9
  unsigned int v11; // edi
  DWORD v12; // eax
  HANDLE v13; // rbx
  DWORD v14; // eax
  void (__fastcall *v15)(struct IRequestContext *, _QWORD); // rbx
  DWORD LastError; // eax
  DWORD v17; // eax
  char *v18; // [rsp+30h] [rbp-50h] BYREF
  int v19; // [rsp+38h] [rbp-48h]
  void **v20; // [rsp+40h] [rbp-40h] BYREF
  signed __int32 v21[4]; // [rsp+48h] [rbp-38h] BYREF
  char v22; // [rsp+58h] [rbp-28h]
  const wchar_t *v23; // [rsp+60h] [rbp-20h]
  const wchar_t *v24; // [rsp+68h] [rbp-18h]
  const wchar_t *v25; // [rsp+70h] [rbp-10h]
  const wchar_t *v26; // [rsp+78h] [rbp-8h]
  HANDLE hToken; // [rsp+C8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids);
  if ( !a4 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\profilemanager.cpp", 0x2Du, L"45", 0x54Fu, 0);
    return 0;
  }
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\profilemanager.cpp", 0x2Eu, L"46", 0x54Fu, a4);
    return 0;
  }
  v18 = (char *)this + 8;
  v19 = 0;
  CWSManCriticalSection::Acquire((CProfileManager *)((char *)this + 8));
  v9 = *((_QWORD *)a2 + 7);
  v10 = *(unsigned int *)(v9 + 32);
  if ( (int)v10 <= 0 )
  {
    if ( (int)v10 >= 0 )
    {
      hToken = 0;
      v11 = 1;
      if ( (unsigned int)CSecurity::DuplicateCurrentToken(
                           &hToken,
                           0x6000Eu,
                           0,
                           SecurityImpersonation,
                           TokenImpersonation,
                           1) )
      {
        v13 = hToken;
        if ( !hToken )
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\profilemanager.cpp", 0x4Bu, L"75", 0x54Fu, 0);
        if ( RevertToSelf() )
        {
          if ( CProfileManager::WMILoadProfile(this, a2, a3, a4) )
            goto LABEL_45;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids);
          if ( CProfileManager::WMILoadProfile(this, a2, a3, a4) )
          {
LABEL_45:
            if ( ImpersonateLoggedOnUser(v13) )
            {
              ++*(_DWORD *)(*((_QWORD *)a2 + 7) + 32LL);
              AutoCleanup<AutoHandle,void *>::ReleasePtr(&hToken);
              goto LABEL_42;
            }
            v15 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a4 + 72LL);
            LastError = GetLastError();
            v15(a4, LastError);
            v21[0] = 0;
            v20 = &CErrorContext::`vftable';
            v21[2] = 0;
            v21[3] = -1;
            v23 = &Class;
            v24 = &Class;
            v25 = &Class;
            v26 = &Class;
            v22 = 1;
            _InterlockedAdd(v21, 1u);
            CProfileManager::WMIUnloadProfile(this, a2, a3, (struct IRequestContext *)&v20);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            {
              v17 = GetLastError();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids, v17);
            }
            v20 = &ILifeTimeMgmt::`vftable';
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          v14 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids, v14);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v12 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids, v12);
      }
      AutoCleanup<AutoHandle,void *>::ReleasePtr(&hToken);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids, v10);
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\profilemanager.cpp", 0x3Eu, L"62", 0x54Fu, a4);
    }
    v11 = 0;
  }
  else
  {
    *(_DWORD *)(v9 + 32) = v10 + 1;
    v11 = 1;
  }
LABEL_42:
  InCritSec::~InCritSec((InCritSec *)&v18);
  return v11;
}

```

## disassembly

```asm
0x180180390  mov     [rsp-28h+arg_0], rbx
0x180180395  mov     [rsp-28h+arg_8], rsi
0x18018039a  push    rbp
0x18018039b  push    rdi
0x18018039c  push    r12
0x18018039e  push    r14
0x1801803a0  push    r15
0x1801803a2  mov     rbp, rsp
0x1801803a5  sub     rsp, 80h
0x1801803ac  mov     rsi, r9
0x1801803af  mov     r12, r8
0x1801803b2  mov     r14, rdx
0x1801803b5  mov     r15, rcx
0x1801803b8  lea     rbx, WPP_GLOBAL_Control
0x1801803bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1801803c6  cmp     rcx, rbx
0x1801803c9  jz      short loc_1801803E9
0x1801803cb  test    dword ptr [rcx+1Ch], 400h
0x1801803d2  jz      short loc_1801803E9
0x1801803d4  mov     edx, 0Eh
0x1801803d9  lea     r8, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids
0x1801803e0  mov     rcx, [rcx+10h]
0x1801803e4  call    WPP_SF_
0x1801803e9  test    rsi, rsi
0x1801803ec  jnz     short loc_180180416
0x1801803ee  mov     qword ptr [rsp+80h+var_60], rsi; struct IRequestContext *
0x1801803f3  lea     r8, a45; "45"
0x1801803fa  lea     edx, [rsi+2Dh]; unsigned int
0x1801803fd  mov     r9d, 54Fh; unsigned int
0x180180403  lea     rcx, aOnecoreAdminWm_128; "onecore\\admin\\wmi\\wmx\\service\\prof"...
0x18018040a  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18018040f  xor     eax, eax
0x180180411  jmp     loc_180180735
0x180180416  test    r14, r14
0x180180419  jnz     short loc_18018042D
0x18018041b  mov     qword ptr [rsp+80h+var_60], rsi
0x180180420  lea     r8, a46; "46"
0x180180427  lea     edx, [r14+2Eh]
0x18018042b  jmp     short loc_1801803FD
0x18018042d  lea     rcx, [r15+8]; this
0x180180431  mov     [rbp+var_50], rcx
0x180180435  mov     [rbp+var_48], 0
0x18018043c  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x180180441  nop
0x180180442  mov     rcx, [r14+38h]
0x180180446  mov     r9d, [rcx+20h]
0x18018044a  test    r9d, r9d
0x18018044d  jle     short loc_180180460
0x18018044f  lea     eax, [r9+1]
0x180180453  mov     [rcx+20h], eax
0x180180456  mov     edi, 1
0x18018045b  jmp     loc_18018072A
0x180180460  jns     short loc_1801804B6
0x180180462  mov     rcx, cs:WPP_GLOBAL_Control
0x180180469  cmp     rcx, rbx
0x18018046c  jz      short loc_18018048C
0x18018046e  test    dword ptr [rcx+1Ch], 200h
0x180180475  jz      short loc_18018048C
0x180180477  mov     edx, 0Fh
0x18018047c  lea     r8, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids
0x180180483  mov     rcx, [rcx+10h]
0x180180487  call    WPP_SF_d
0x18018048c  mov     qword ptr [rsp+80h+var_60], rsi; struct IRequestContext *
0x180180491  mov     r9d, 54Fh; unsigned int
0x180180497  lea     r8, a62; "62"
0x18018049e  mov     edx, 3Eh ; '>'; unsigned int
0x1801804a3  lea     rcx, aOnecoreAdminWm_128; "onecore\\admin\\wmi\\wmx\\service\\prof"...
0x1801804aa  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801804af  xor     edi, edi
0x1801804b1  jmp     loc_18018072A
0x1801804b6  mov     [rbp+hToken], 0
0x1801804be  mov     edi, 1
0x1801804c3  mov     [rsp+80h+var_58], edi; int
0x1801804c7  lea     r9d, [rdi+1]; ImpersonationLevel
0x1801804cb  mov     [rsp+80h+var_60], r9d; TOKEN_TYPE
0x1801804d0  xor     r8d, r8d; lpTokenAttributes
0x1801804d3  mov     edx, 6000Eh; dwDesiredAccess
0x1801804d8  lea     rcx, [rbp+hToken]; void **
0x1801804dc  call    ?DuplicateCurrentToken@CSecurity@@SAHPEAPEAXKPEAU_SECURITY_ATTRIBUTES@@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@H@Z; CSecurity::DuplicateCurrentToken(void * *,ulong,_SECURITY_ATTRIBUTES *,_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE,int)
0x1801804e1  test    eax, eax
0x1801804e3  jnz     short loc_18018052A
0x1801804e5  mov     rax, cs:WPP_GLOBAL_Control
0x1801804ec  cmp     rax, rbx
0x1801804ef  jz      loc_18018063D
0x1801804f5  test    dword ptr [rax+1Ch], 200h
0x1801804fc  jz      loc_18018063D
0x180180502  call    cs:__imp_GetLastError
0x180180508  lea     edx, [rdi+0Fh]
0x18018050b  mov     r9d, eax
0x18018050e  lea     r8, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids
0x180180515  mov     rcx, cs:WPP_GLOBAL_Control
0x18018051c  mov     rcx, [rcx+10h]
0x180180520  call    WPP_SF_d
0x180180525  jmp     loc_18018063D
0x18018052a  mov     rbx, [rbp+hToken]
0x18018052e  test    rbx, rbx
0x180180531  jnz     short loc_180180554
0x180180533  mov     qword ptr [rsp+80h+var_60], rbx; struct IRequestContext *
0x180180538  mov     r9d, 54Fh; unsigned int
0x18018053e  lea     r8, a75; "75"
0x180180545  lea     edx, [rbx+4Bh]; unsigned int
0x180180548  lea     rcx, aOnecoreAdminWm_128; "onecore\\admin\\wmi\\wmx\\service\\prof"...
0x18018054f  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180180554  call    cs:__imp_RevertToSelf
0x18018055a  test    eax, eax
0x18018055c  jnz     short loc_1801805AC
0x18018055e  mov     rax, cs:WPP_GLOBAL_Control
0x180180565  lea     rcx, WPP_GLOBAL_Control
0x18018056c  cmp     rax, rcx
0x18018056f  jz      loc_18018063D
0x180180575  test    dword ptr [rax+1Ch], 200h
0x18018057c  jz      loc_18018063D
0x180180582  call    cs:__imp_GetLastError
0x180180588  mov     edx, 11h
0x18018058d  mov     r9d, eax
0x180180590  lea     r8, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids
0x180180597  mov     rcx, cs:WPP_GLOBAL_Control
0x18018059e  mov     rcx, [rcx+10h]
0x1801805a2  call    WPP_SF_d
0x1801805a7  jmp     loc_18018063D
0x1801805ac  mov     r9, rsi; struct IRequestContext *
0x1801805af  mov     r8, r12; void *
0x1801805b2  mov     rdx, r14; struct UserRecord *
0x1801805b5  mov     rcx, r15; this
0x1801805b8  call    ?WMILoadProfile@CProfileManager@@IEAAHPEAVUserRecord@@PEAXPEAVIRequestContext@@@Z; CProfileManager::WMILoadProfile(UserRecord *,void *,IRequestContext *)
0x1801805bd  test    eax, eax
0x1801805bf  jnz     loc_18018064B
0x1801805c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801805cc  lea     rax, WPP_GLOBAL_Control
0x1801805d3  cmp     rcx, rax
0x1801805d6  jz      short loc_1801805F6
0x1801805d8  test    dword ptr [rcx+1Ch], 400h
0x1801805df  jz      short loc_1801805F6
0x1801805e1  mov     edx, 12h
0x1801805e6  lea     r8, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids
0x1801805ed  mov     rcx, [rcx+10h]
0x1801805f1  call    WPP_SF_
0x1801805f6  mov     r9, rsi; struct IRequestContext *
0x1801805f9  mov     r8, r12; void *
0x1801805fc  mov     rdx, r14; struct UserRecord *
0x1801805ff  mov     rcx, r15; this
0x180180602  call    ?WMILoadProfile@CProfileManager@@IEAAHPEAVUserRecord@@PEAXPEAVIRequestContext@@@Z; CProfileManager::WMILoadProfile(UserRecord *,void *,IRequestContext *)
0x180180607  test    eax, eax
0x180180609  jnz     short loc_18018064B
0x18018060b  mov     rcx, cs:WPP_GLOBAL_Control
0x180180612  lea     rax, WPP_GLOBAL_Control
0x180180619  cmp     rcx, rax
0x18018061c  jz      short loc_18018063D
0x18018061e  test    dword ptr [rcx+1Ch], 200h
0x180180625  jz      short loc_18018063D
0x180180627  mov     edx, 13h
0x18018062c  lea     r8, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids
0x180180633  mov     rcx, [rcx+10h]
0x180180637  call    WPP_SF_
0x18018063c  nop
0x18018063d  lea     rcx, [rbp+hToken]
0x180180641  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x180180646  jmp     loc_1801804AF
0x18018064b  mov     rcx, rbx; hToken
0x18018064e  call    cs:__imp_ImpersonateLoggedOnUser
0x180180654  test    eax, eax
0x180180656  jnz     loc_180180719
0x18018065c  mov     rax, [rsi]
0x18018065f  mov     rbx, [rax+48h]
0x180180663  call    cs:__imp_GetLastError
0x180180669  mov     edx, eax
0x18018066b  mov     rcx, rsi
0x18018066e  mov     rax, rbx
0x180180671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180180676  mov     [rbp+var_38], 0
0x18018067d  lea     rax, ??_7CErrorContext@@6B@; const CErrorContext::`vftable'
0x180180684  mov     [rbp+var_40], rax
0x180180688  mov     [rbp+var_30], 0
0x18018068f  mov     [rbp+var_2C], 0FFFFFFFFh
0x180180696  lea     rax, Class
0x18018069d  mov     [rbp+var_20], rax
0x1801806a1  mov     [rbp+var_18], rax
0x1801806a5  mov     [rbp+var_10], rax
0x1801806a9  mov     [rbp+var_8], rax
0x1801806ad  mov     [rbp+var_28], dil
0x1801806b1  lock add [rbp+var_38], edi
0x1801806b5  lea     r9, [rbp+var_40]; struct IRequestContext *
0x1801806b9  mov     r8, r12; void *
0x1801806bc  mov     rdx, r14; struct UserRecord *
0x1801806bf  mov     rcx, r15; this
0x1801806c2  call    ?WMIUnloadProfile@CProfileManager@@IEAAHPEAVUserRecord@@PEAXPEAVIRequestContext@@@Z; CProfileManager::WMIUnloadProfile(UserRecord *,void *,IRequestContext *)
0x1801806c7  mov     rax, cs:WPP_GLOBAL_Control
0x1801806ce  lea     rcx, WPP_GLOBAL_Control
0x1801806d5  cmp     rax, rcx
0x1801806d8  jz      short loc_180180709
0x1801806da  test    dword ptr [rax+1Ch], 200h
0x1801806e1  jz      short loc_180180709
0x1801806e3  call    cs:__imp_GetLastError
0x1801806e9  mov     edx, 14h
0x1801806ee  mov     r9d, eax
0x1801806f1  lea     r8, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids
0x1801806f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801806ff  mov     rcx, [rcx+10h]
0x180180703  call    WPP_SF_d
0x180180708  nop
0x180180709  lea     rax, ??_7ILifeTimeMgmt@@6B@; const ILifeTimeMgmt::`vftable'
0x180180710  mov     [rbp+var_40], rax
0x180180714  jmp     loc_18018063D
0x180180719  mov     rcx, [r14+38h]
0x18018071d  add     [rcx+20h], edi
0x180180720  lea     rcx, [rbp+hToken]
0x180180724  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x180180729  nop
0x18018072a  lea     rcx, [rbp+var_50]; this
0x18018072e  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180180733  mov     eax, edi
0x180180735  lea     r11, [rsp+80h+var_s0]
0x18018073d  mov     rbx, [r11+30h]
0x180180741  mov     rsi, [r11+38h]
0x180180745  mov     rsp, r11
0x180180748  pop     r15
0x18018074a  pop     r14
0x18018074c  pop     r12
0x18018074e  pop     rdi
0x18018074f  pop     rbp
0x180180750  retn
```
