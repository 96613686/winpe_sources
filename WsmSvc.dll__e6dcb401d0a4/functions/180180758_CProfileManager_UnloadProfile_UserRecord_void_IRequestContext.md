# CProfileManager::UnloadProfile(UserRecord *,void *,IRequestContext *)

- ea: `0x180180758`
- end: `0x180180a32`
- name: `?UnloadProfile@CProfileManager@@QEAAHPEAVUserRecord@@PEAXPEAVIRequestContext@@@Z`
- size: `730`
- prototype: `__int64 __fastcall(CProfileManager *this, struct UserRecord *, void *, struct IRequestContext *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180183084`

## callees

- `0x180005d10`
- `0x18002dd20`
- `0x180068b24`
- `0x180071400`
- `0x1800c6320`
- `0x180112380`
- `0x1801123a8`
- `0x180180758`
- `0x18018128c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801808b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018093e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801809a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801809cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801808b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018093e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801809a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801809cd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180180908`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180180908`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180180994`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180180994`

## string_xrefs

- `0x1801807c8`: `onecore\admin\wmi\wmx\service\profilemanager.cpp`
- `0x180180852`: `onecore\admin\wmi\wmx\service\profilemanager.cpp`
- `0x1801808fc`: `onecore\admin\wmi\wmx\service\profilemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CProfileManager::UnloadProfile(
        CProfileManager *this,
        struct UserRecord *a2,
        void *a3,
        struct IRequestContext *a4)
{
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // edi
  DWORD LastError; // eax
  HANDLE v13; // rbx
  DWORD v14; // eax
  __int64 v15; // rdx
  void (__fastcall *v16)(struct IRequestContext *, _QWORD); // rbx
  DWORD v17; // eax
  char *v18; // [rsp+30h] [rbp-38h] BYREF
  int v19; // [rsp+38h] [rbp-30h]
  HANDLE hToken; // [rsp+78h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids);
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\profilemanager.cpp", 0x73u, L"115", 0x54Fu, 0);
    return 0;
  }
  v18 = (char *)this + 8;
  v19 = 0;
  CWSManCriticalSection::Acquire((CProfileManager *)((char *)this + 8));
  v9 = *((_QWORD *)a2 + 7);
  v10 = *(_DWORD *)(v9 + 32);
  v11 = 1;
  if ( v10 <= 1 )
  {
    if ( v10 < 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids,
          (unsigned int)v10);
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\profilemanager.cpp", 0x83u, L"131", 0x54Fu, 0);
      goto LABEL_13;
    }
    *(_DWORD *)(v9 + 32) = v10 - 1;
    hToken = 0;
    if ( !(unsigned int)CSecurity::DuplicateCurrentToken(
                          &hToken,
                          0x6000Eu,
                          0,
                          SecurityImpersonation,
                          TokenImpersonation,
                          1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids, LastError);
      }
      goto LABEL_33;
    }
    v13 = hToken;
    if ( !hToken )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\profilemanager.cpp", 0x95u, L"149", 0x54Fu, 0);
    if ( RevertToSelf() )
    {
      if ( !CProfileManager::WMIUnloadProfile(this, a2, a3, a4) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids);
        goto LABEL_33;
      }
      if ( ImpersonateLoggedOnUser(v13) )
      {
        AutoCleanup<AutoHandle,void *>::ReleasePtr(&hToken);
        goto LABEL_35;
      }
      v16 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a4 + 72LL);
      v17 = GetLastError();
      v16(a4, v17);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_33;
      v14 = GetLastError();
      v15 = 26;
    }
    else
    {
      (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 24LL))(a4);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_33;
      v14 = GetLastError();
      v15 = 24;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids, v14);
LABEL_33:
    AutoCleanup<AutoHandle,void *>::ReleasePtr(&hToken);
LABEL_13:
    v11 = 0;
    goto LABEL_35;
  }
  *(_DWORD *)(v9 + 32) = v10 - 1;
LABEL_35:
  InCritSec::~InCritSec((InCritSec *)&v18);
  return v11;
}

```

## disassembly

```asm
0x180180758  mov     [rsp+arg_0], rbx
0x18018075d  mov     [rsp+arg_10], rbp
0x180180762  push    rsi
0x180180763  push    rdi
0x180180764  push    r13
0x180180766  push    r14
0x180180768  push    r15
0x18018076a  sub     rsp, 40h
0x18018076e  mov     rsi, r9
0x180180771  mov     r15, r8
0x180180774  mov     rbp, rdx
0x180180777  mov     r14, rcx
0x18018077a  lea     r13, WPP_GLOBAL_Control
0x180180781  lea     rbx, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids
0x180180788  mov     rcx, cs:WPP_GLOBAL_Control
0x18018078f  cmp     rcx, r13
0x180180792  jz      short loc_1801807AE
0x180180794  test    dword ptr [rcx+1Ch], 400h
0x18018079b  jz      short loc_1801807AE
0x18018079d  mov     edx, 15h
0x1801807a2  mov     r8, rbx
0x1801807a5  mov     rcx, [rcx+10h]
0x1801807a9  call    WPP_SF_
0x1801807ae  test    rbp, rbp
0x1801807b1  jnz     short loc_1801807DB
0x1801807b3  mov     qword ptr [rsp+68h+var_48], rbp; struct IRequestContext *
0x1801807b8  mov     r9d, 54Fh; unsigned int
0x1801807be  lea     r8, a115; "115"
0x1801807c5  lea     edx, [rbp+73h]; unsigned int
0x1801807c8  lea     rcx, aOnecoreAdminWm_128; "onecore\\admin\\wmi\\wmx\\service\\prof"...
0x1801807cf  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801807d4  xor     eax, eax
0x1801807d6  jmp     loc_180180A19
0x1801807db  lea     rcx, [r14+8]; this
0x1801807df  mov     [rsp+68h+var_38], rcx
0x1801807e4  mov     [rsp+68h+var_30], 0
0x1801807ec  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x1801807f1  nop
0x1801807f2  mov     rcx, [rbp+38h]
0x1801807f6  mov     eax, [rcx+20h]
0x1801807f9  mov     edi, 1
0x1801807fe  cmp     eax, edi
0x180180800  jle     short loc_18018080C
0x180180802  dec     eax
0x180180804  mov     [rcx+20h], eax
0x180180807  jmp     loc_180180A0D
0x18018080c  jge     short loc_180180865
0x18018080e  mov     rcx, cs:WPP_GLOBAL_Control
0x180180815  cmp     rcx, r13
0x180180818  jz      short loc_180180837
0x18018081a  test    dword ptr [rcx+1Ch], 200h
0x180180821  jz      short loc_180180837
0x180180823  mov     edx, 16h
0x180180828  mov     r9d, eax
0x18018082b  mov     r8, rbx
0x18018082e  mov     rcx, [rcx+10h]
0x180180832  call    WPP_SF_d
0x180180837  mov     qword ptr [rsp+68h+var_48], 0; struct IRequestContext *
0x180180840  mov     r9d, 54Fh; unsigned int
0x180180846  lea     r8, a131; "131"
0x18018084d  mov     edx, 83h; unsigned int
0x180180852  lea     rcx, aOnecoreAdminWm_128; "onecore\\admin\\wmi\\wmx\\service\\prof"...
0x180180859  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18018085e  xor     edi, edi
0x180180860  jmp     loc_180180A0D
0x180180865  dec     eax
0x180180867  mov     [rcx+20h], eax
0x18018086a  mov     [rsp+68h+hToken], 0
0x180180873  mov     [rsp+68h+var_40], edi; int
0x180180877  mov     r9d, 2; ImpersonationLevel
0x18018087d  mov     [rsp+68h+var_48], r9d; TOKEN_TYPE
0x180180882  xor     r8d, r8d; lpTokenAttributes
0x180180885  mov     edx, 6000Eh; dwDesiredAccess
0x18018088a  lea     rcx, [rsp+68h+hToken]; void **
0x18018088f  call    ?DuplicateCurrentToken@CSecurity@@SAHPEAPEAXKPEAU_SECURITY_ATTRIBUTES@@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@H@Z; CSecurity::DuplicateCurrentToken(void * *,ulong,_SECURITY_ATTRIBUTES *,_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE,int)
0x180180894  test    eax, eax
0x180180896  jnz     short loc_1801808DB
0x180180898  mov     rax, cs:WPP_GLOBAL_Control
0x18018089f  cmp     rax, r13
0x1801808a2  jz      loc_1801809F3
0x1801808a8  test    dword ptr [rax+1Ch], 200h
0x1801808af  jz      loc_1801809F3
0x1801808b5  call    cs:__imp_GetLastError
0x1801808bb  mov     edx, 17h
0x1801808c0  mov     r9d, eax
0x1801808c3  mov     r8, rbx
0x1801808c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801808cd  mov     rcx, [rcx+10h]
0x1801808d1  call    WPP_SF_d
0x1801808d6  jmp     loc_1801809F3
0x1801808db  mov     rbx, [rsp+68h+hToken]
0x1801808e0  test    rbx, rbx
0x1801808e3  jnz     short loc_180180908
0x1801808e5  mov     qword ptr [rsp+68h+var_48], rbx; struct IRequestContext *
0x1801808ea  mov     r9d, 54Fh; unsigned int
0x1801808f0  lea     r8, a149; "149"
0x1801808f7  mov     edx, 95h; unsigned int
0x1801808fc  lea     rcx, aOnecoreAdminWm_128; "onecore\\admin\\wmi\\wmx\\service\\prof"...
0x180180903  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180180908  call    cs:__imp_RevertToSelf
0x18018090e  test    eax, eax
0x180180910  jnz     short loc_18018094E
0x180180912  mov     rax, [rsi]
0x180180915  mov     rcx, rsi
0x180180918  mov     rax, [rax+18h]
0x18018091c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180180921  mov     rax, cs:WPP_GLOBAL_Control
0x180180928  cmp     rax, r13
0x18018092b  jz      loc_1801809F3
0x180180931  test    dword ptr [rax+1Ch], 200h
0x180180938  jz      loc_1801809F3
0x18018093e  call    cs:__imp_GetLastError
0x180180944  mov     edx, 18h
0x180180949  jmp     loc_1801809D8
0x18018094e  mov     r9, rsi; struct IRequestContext *
0x180180951  mov     r8, r15; void *
0x180180954  mov     rdx, rbp; struct UserRecord *
0x180180957  mov     rcx, r14; this
0x18018095a  call    ?WMIUnloadProfile@CProfileManager@@IEAAHPEAVUserRecord@@PEAXPEAVIRequestContext@@@Z; CProfileManager::WMIUnloadProfile(UserRecord *,void *,IRequestContext *)
0x18018095f  test    eax, eax
0x180180961  jnz     short loc_180180991
0x180180963  mov     rcx, cs:WPP_GLOBAL_Control
0x18018096a  cmp     rcx, r13
0x18018096d  jz      loc_1801809F3
0x180180973  test    dword ptr [rcx+1Ch], 200h
0x18018097a  jz      short loc_1801809F3
0x18018097c  lea     edx, [rax+19h]
0x18018097f  lea     r8, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids
0x180180986  mov     rcx, [rcx+10h]
0x18018098a  call    WPP_SF_
0x18018098f  jmp     short loc_1801809F3
0x180180991  mov     rcx, rbx; hToken
0x180180994  call    cs:__imp_ImpersonateLoggedOnUser
0x18018099a  test    eax, eax
0x18018099c  jnz     short loc_180180A02
0x18018099e  mov     rax, [rsi]
0x1801809a1  mov     rbx, [rax+48h]
0x1801809a5  call    cs:__imp_GetLastError
0x1801809ab  mov     edx, eax
0x1801809ad  mov     rcx, rsi
0x1801809b0  mov     rax, rbx
0x1801809b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801809b8  mov     rax, cs:WPP_GLOBAL_Control
0x1801809bf  cmp     rax, r13
0x1801809c2  jz      short loc_1801809F3
0x1801809c4  test    dword ptr [rax+1Ch], 200h
0x1801809cb  jz      short loc_1801809F3
0x1801809cd  call    cs:__imp_GetLastError
0x1801809d3  mov     edx, 1Ah
0x1801809d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801809df  mov     r9d, eax
0x1801809e2  lea     r8, WPP_2a79ba26dcab3cad55070b88393fc780_Traceguids
0x1801809e9  mov     rcx, [rcx+10h]
0x1801809ed  call    WPP_SF_d
0x1801809f2  nop
0x1801809f3  lea     rcx, [rsp+68h+hToken]
0x1801809f8  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1801809fd  jmp     loc_18018085E
0x180180a02  lea     rcx, [rsp+68h+hToken]
0x180180a07  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x180180a0c  nop
0x180180a0d  lea     rcx, [rsp+68h+var_38]; this
0x180180a12  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180180a17  mov     eax, edi
0x180180a19  lea     r11, [rsp+68h+var_28]
0x180180a1e  mov     rbx, [r11+30h]
0x180180a22  mov     rbp, [r11+40h]
0x180180a26  mov     rsp, r11
0x180180a29  pop     r15
0x180180a2b  pop     r14
0x180180a2d  pop     r13
0x180180a2f  pop     rdi
0x180180a30  pop     rsi
0x180180a31  retn
```
