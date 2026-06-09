# CDoc::AttemptBFCacheNavigation(ulong,ulong)

- ea: `0x18084626c`
- end: `0x1808464cb`
- name: `?AttemptBFCacheNavigation@CDoc@@QEAAJKK@Z`
- size: `607`
- prototype: `int(CDoc *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1806d3d68`
- `0x18087cc10`

## callees

- `0x1804fa5e0`
- `0x1805fe298`
- `0x18084626c`
- `0x181061be0`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1808462ec`
- `KERNEL32!GetCurrentProcessId` at `0x1808462ec`
- `KERNEL32!GetCurrentThreadId` at `0x1808462a0`
- `KERNEL32!GetCurrentThreadId` at `0x180846329`
- `KERNEL32!GetCurrentThreadId` at `0x1808462a0`
- `KERNEL32!GetCurrentThreadId` at `0x180846329`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1808463f4`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1808463f4`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180846312`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180846312`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x18084633d`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x18084633d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18084631b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18084631b`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1808462fa`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1808462fa`
- `OLEAUT32!__imp_VariantInit` at `0x180846382`
- `OLEAUT32!__imp_VariantInit` at `0x1808463cc`
- `OLEAUT32!__imp_VariantInit` at `0x180846382`
- `OLEAUT32!__imp_VariantInit` at `0x1808463cc`
- `OLEAUT32!__imp_VariantClear` at `0x1808463d7`
- `OLEAUT32!__imp_VariantClear` at `0x1808463d7`

## pseudocode

```c
__int64 __fastcall CDoc::AttemptBFCacheNavigation(struct IUnknown **this, int a2, unsigned int a3)
{
  int v6; // ebx
  DWORD CurrentThreadId; // eax
  bool *v8; // r9
  char Integrity; // al
  DWORD v10; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v14; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  struct IEUserBroker *v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[80]; // [rsp+70h] [rbp-90h] BYREF
  LONGLONG llVal; // [rsp+C0h] [rbp-40h]
  __int128 v21; // [rsp+100h] [rbp+0h] BYREF
  int v22; // [rsp+110h] [rbp+10h]
  unsigned int v23; // [rsp+120h] [rbp+20h] BYREF
  int v24; // [rsp+124h] [rbp+24h]
  DWORD CurrentProcessId; // [rsp+138h] [rbp+38h]
  int v26; // [rsp+13Ch] [rbp+3Ch]
  int v27; // [rsp+140h] [rbp+40h]
  int DWORD; // [rsp+148h] [rbp+48h]
  __int128 v29; // [rsp+154h] [rbp+54h]

  LOBYTE(v14) = 0;
  v6 = -2147467259;
  CurrentThreadId = GetCurrentThreadId();
  BFCacheUtils::IsAdvertisedBFCacheCookie((BFCacheUtils *)a3, CurrentThreadId, (unsigned int)&v14, v8);
  if ( (_BYTE)v14 )
  {
    memset_0(v19, 0, 0x90u);
    v22 = 0;
    v21 = 0;
    memset_0(&v23, 0, 0x44u);
    CurrentProcessId = GetCurrentProcessId();
    Integrity = IsoGetIntegrity(1);
    v27 = 0;
    v26 = Integrity & 0x7F;
    DWORD = IEConfiguration_GetDWORD(536870929);
    v29 = *(_OWORD *)GlobalThreadState();
    v10 = GetCurrentThreadId();
    LCIEGetTypedComponentFromThread(0x203u, v10, &v23, 0);
    v24 |= a2;
    LODWORD(v21) = 3;
    HIDWORD(v21) = a3;
    if ( !(unsigned int)CDoc::CheckBFCacheCandidacy(this, 809035761, v11, v12) )
      v24 |= 0x40000u;
    if ( this[8] )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      if ( (int)CTExec(this[8], &CGID_Explorer, 0x78u, 0, 0, &pvarg) >= 0 )
      {
        if ( pvarg.vt == 8 )
        {
          llVal = pvarg.llVal;
          VariantInit(&pvarg);
        }
        VariantClear(&pvarg);
      }
    }
    v17 = 0;
    v16 = 0;
    v6 = CoCreateUserBroker(&v16);
    if ( v6 >= 0 )
    {
      v15 = 0;
      v6 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v16 + 48LL))(
             v16,
             &CLSID_CShdocvwBroker,
             &IID_IUnknown,
             &v15);
      if ( v6 >= 0 )
      {
        v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v15)(
               v15,
               &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
               &v17);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v16 + 16LL))(v16);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *, unsigned int *, __int128 *))(*(_QWORD *)v17 + 1144LL))(
               v17,
               v19,
               &v23,
               &v21);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18084626c  push    rbp
0x18084626e  push    rbx
0x18084626f  push    rsi
0x180846270  push    rdi
0x180846271  push    r14
0x180846273  lea     rbp, [rsp-80h]
0x180846278  sub     rsp, 180h
0x18084627f  mov     rax, cs:__security_cookie
0x180846286  xor     rax, rsp
0x180846289  mov     [rbp+0A0h+var_30], rax
0x18084628d  mov     esi, r8d
0x180846290  mov     byte ptr [rsp+1A0h+var_170], 0
0x180846295  mov     r14d, edx
0x180846298  mov     rdi, rcx
0x18084629b  mov     ebx, 80004005h
0x1808462a0  call    cs:__imp_GetCurrentThreadId
0x1808462a6  lea     r8, [rsp+1A0h+var_170]; unsigned int
0x1808462ab  mov     ecx, esi; this
0x1808462ad  mov     edx, eax; unsigned int
0x1808462af  call    ?IsAdvertisedBFCacheCookie@BFCacheUtils@@YAJKKPEA_N@Z; BFCacheUtils::IsAdvertisedBFCacheCookie(ulong,ulong,bool *)
0x1808462b4  cmp     byte ptr [rsp+1A0h+var_170], 0
0x1808462b9  jz      loc_1808464AF
0x1808462bf  xor     edx, edx; Val
0x1808462c1  lea     rcx, [rsp+1A0h+var_130]; void *
0x1808462c6  mov     r8d, 90h; Size
0x1808462cc  call    memset_0
0x1808462d1  xor     eax, eax
0x1808462d3  lea     rcx, [rbp+0A0h+var_80]; void *
0x1808462d7  xorps   xmm0, xmm0
0x1808462da  mov     [rbp+0A0h+var_90], eax
0x1808462dd  xor     edx, edx; Val
0x1808462df  movups  [rbp+0A0h+var_A0], xmm0
0x1808462e3  lea     r8d, [rax+44h]; Size
0x1808462e7  call    memset_0
0x1808462ec  call    cs:__imp_GetCurrentProcessId
0x1808462f2  mov     ecx, 1
0x1808462f7  mov     [rbp+0A0h+var_68], eax
0x1808462fa  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180846300  mov     ecx, 20000011h
0x180846305  mov     [rbp+0A0h+var_60], 0
0x18084630c  and     eax, 7Fh
0x18084630f  mov     [rbp+0A0h+var_64], eax
0x180846312  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180846318  mov     [rbp+0A0h+var_58], eax
0x18084631b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180846321  movups  xmm0, xmmword ptr [rax]
0x180846324  movdqu  [rbp+0A0h+var_4C], xmm0
0x180846329  call    cs:__imp_GetCurrentThreadId
0x18084632f  xor     r9d, r9d
0x180846332  lea     r8, [rbp+0A0h+var_80]
0x180846336  mov     edx, eax
0x180846338  mov     ecx, 203h
0x18084633d  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x180846343  or      [rbp+0A0h+var_7C], r14d
0x180846347  mov     edx, 3038E7F1h
0x18084634c  mov     rcx, rdi
0x18084634f  mov     dword ptr [rbp+0A0h+var_A0], 3
0x180846356  mov     dword ptr [rbp+0A0h+var_A0+0Ch], esi
0x180846359  call    ?CheckBFCacheCandidacy@CDoc@@QEAA?AW4tagBFCACHE_CANDIDACY_FAILURE_FLAGS@@W42@@Z; CDoc::CheckBFCacheCandidacy(tagBFCACHE_CANDIDACY_FAILURE_FLAGS)
0x18084635e  test    eax, eax
0x180846360  jnz     short loc_180846367
0x180846362  bts     [rbp+0A0h+var_7C], 12h
0x180846367  cmp     qword ptr [rdi+40h], 0
0x18084636c  jz      short loc_1808463DD
0x18084636e  xorps   xmm0, xmm0
0x180846371  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x180846376  xor     eax, eax
0x180846378  movups  xmmword ptr [rsp+1A0h+pvarg], xmm0
0x18084637d  mov     qword ptr [rsp+1A0h+pvarg+10h], rax
0x180846382  call    cs:__imp_VariantInit
0x180846388  mov     rcx, [rdi+40h]; struct IUnknown *
0x18084638c  lea     rax, [rsp+1A0h+pvarg]
0x180846391  xor     r9d, r9d; unsigned int
0x180846394  mov     [rsp+1A0h+var_178], rax; struct tagVARIANT *
0x180846399  lea     rdx, CGID_Explorer; struct _GUID *
0x1808463a0  mov     [rsp+1A0h+var_180], 0; struct tagVARIANT *
0x1808463a9  lea     r8d, [r9+78h]; unsigned int
0x1808463ad  call    ?CTExec@@YAJPEAUIUnknown@@PEBU_GUID@@KKPEAUtagVARIANT@@2@Z; CTExec(IUnknown *,_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x1808463b2  test    eax, eax
0x1808463b4  js      short loc_1808463DD
0x1808463b6  cmp     word ptr [rsp+1A0h+pvarg], 8
0x1808463bc  jnz     short loc_1808463D2
0x1808463be  mov     rax, qword ptr [rsp+1A0h+pvarg+8]
0x1808463c3  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x1808463c8  mov     [rbp+0A0h+var_E0], rax
0x1808463cc  call    cs:__imp_VariantInit
0x1808463d2  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x1808463d7  call    cs:__imp_VariantClear
0x1808463dd  lea     rcx, [rsp+1A0h+var_160]
0x1808463e2  mov     [rsp+1A0h+var_158], 0
0x1808463eb  mov     [rsp+1A0h+var_160], 0
0x1808463f4  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1808463fa  mov     ebx, eax
0x1808463fc  test    eax, eax
0x1808463fe  js      loc_1808464AF
0x180846404  mov     rcx, [rsp+1A0h+var_160]
0x180846409  lea     r9, [rsp+1A0h+var_168]
0x18084640e  mov     [rsp+1A0h+var_168], 0
0x180846417  lea     r8, IID_IUnknown
0x18084641e  lea     rdx, CLSID_CShdocvwBroker
0x180846425  mov     rax, [rcx]
0x180846428  mov     rax, [rax+30h]
0x18084642c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180846431  mov     ebx, eax
0x180846433  test    eax, eax
0x180846435  js      short loc_180846466
0x180846437  mov     rcx, [rsp+1A0h+var_168]
0x18084643c  lea     r8, [rsp+1A0h+var_158]
0x180846441  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180846448  mov     rax, [rcx]
0x18084644b  mov     rax, [rax]
0x18084644e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180846453  mov     rcx, [rsp+1A0h+var_168]
0x180846458  mov     ebx, eax
0x18084645a  mov     rax, [rcx]
0x18084645d  mov     rax, [rax+10h]
0x180846461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180846466  mov     rcx, [rsp+1A0h+var_160]
0x18084646b  mov     rax, [rcx]
0x18084646e  mov     rax, [rax+10h]
0x180846472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180846477  test    ebx, ebx
0x180846479  js      short loc_1808464AF
0x18084647b  mov     rcx, [rsp+1A0h+var_158]
0x180846480  lea     r9, [rbp+0A0h+var_A0]
0x180846484  lea     r8, [rbp+0A0h+var_80]
0x180846488  lea     rdx, [rsp+1A0h+var_130]
0x18084648d  mov     rax, [rcx]
0x180846490  mov     rax, [rax+478h]
0x180846497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18084649c  mov     rcx, [rsp+1A0h+var_158]
0x1808464a1  mov     ebx, eax
0x1808464a3  mov     rax, [rcx]
0x1808464a6  mov     rax, [rax+10h]
0x1808464aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808464af  mov     eax, ebx
0x1808464b1  mov     rcx, [rbp+0A0h+var_30]
0x1808464b5  xor     rcx, rsp; StackCookie
0x1808464b8  call    __security_check_cookie
0x1808464bd  add     rsp, 180h
0x1808464c4  pop     r14
0x1808464c6  pop     rdi
0x1808464c7  pop     rsi
0x1808464c8  pop     rbx
0x1808464c9  pop     rbp
0x1808464ca  retn
```
