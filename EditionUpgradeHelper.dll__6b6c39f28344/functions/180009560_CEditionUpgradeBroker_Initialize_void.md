# CEditionUpgradeBroker::Initialize(void)

- ea: `0x180009560`
- end: `0x1800096e2`
- name: `?Initialize@CEditionUpgradeBroker@@UEAAJXZ`
- size: `386`
- prototype: `__int64 __fastcall(CEditionUpgradeBroker *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800018e0`
- `0x180007020`
- `0x180008c60`
- `0x180009560`
- `0x180009978`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009603`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009603`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000968e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000968e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800095cb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800095cb`
- `ole32!CoGetObject` at `0x180009670`
- `ole32!CoGetObject` at `0x180009670`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeBroker::Initialize(CEditionUpgradeBroker *this)
{
  void **v1; // r14
  int v2; // ebx
  unsigned int v3; // edi
  __int64 v4; // rsi
  unsigned int v5; // edi
  __int64 v6; // r15
  HRESULT v7; // eax
  __int64 v8; // rcx
  HRESULT Object; // eax
  __int64 v10; // rcx
  int v11; // eax
  BIND_OPTS pBindOptions[3]; // [rsp+20h] [rbp-E0h] BYREF
  OLECHAR sz[56]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszName[304]; // [rsp+C0h] [rbp-40h] BYREF

  v1 = (void **)((char *)this + 48);
  v2 = 0;
  memset(pBindOptions, 0, sizeof(pBindOptions));
  if ( this == (CEditionUpgradeBroker *)-48LL )
  {
    v3 = -2147024809;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
    v4 = -8;
    goto LABEL_13;
  }
  v4 = (__int64)this + 40;
  v5 = 0;
  v6 = *((int *)this + 10);
  v7 = CoInitializeEx(0, 0);
  if ( v7 < 0 )
  {
    if ( v7 != -2147417850 )
    {
      v5 = v7;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v7);
    }
  }
  else
  {
    v2 = 1;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( !StringFromGUID2(&CLSID_EditionUpgradeManager, sz, 50) )
  {
    v3 = -2147467259;
    v8 = 2147500037LL;
LABEL_12:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_13;
  }
  Object = StringCchPrintfW(
             pszName,
             0x12Cu,
             L"Elevation:Administrator!new:%s",
             sz,
             *(_QWORD *)&pBindOptions[0].cbStruct,
             *(_QWORD *)&pBindOptions[0].grfMode,
             *(_OWORD *)&pBindOptions[1],
             *(_OWORD *)&pBindOptions[2]);
  v3 = Object;
  if ( Object < 0
    || (pBindOptions[0].cbStruct = 48,
        *(_QWORD *)&pBindOptions[2].grfMode = v6,
        pBindOptions[1].grfFlags = 4,
        *(_OWORD *)&pBindOptions[0].grfFlags = 0,
        *(_OWORD *)&pBindOptions[1].grfMode = 0,
        Object = CoGetObject(pszName, pBindOptions, &GUID_f2dcb80d_0670_44bc_9002_cd18688730af, v1),
        v3 = Object,
        Object < 0) )
  {
    v8 = (unsigned int)Object;
    goto LABEL_12;
  }
LABEL_13:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( v2 )
    CoUninitialize();
  if ( (v3 & 0x80000000) != 0 )
  {
    v10 = v3;
LABEL_19:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    goto LABEL_20;
  }
  v11 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v1 + 24LL))(*v1, *(unsigned int *)v4);
  v3 = v11;
  if ( v11 < 0 )
  {
    v10 = (unsigned int)v11;
    goto LABEL_19;
  }
LABEL_20:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  return v3;
}

```

## disassembly

```asm
0x180009560  push    rbp
0x180009562  push    rbx
0x180009563  push    rsi
0x180009564  push    rdi
0x180009565  push    r14
0x180009567  push    r15
0x180009569  lea     rbp, [rsp-238h]
0x180009571  sub     rsp, 338h
0x180009578  mov     rax, cs:__security_cookie
0x18000957f  xor     rax, rsp
0x180009582  mov     [rbp+260h+var_40], rax
0x180009589  xorps   xmm0, xmm0
0x18000958c  lea     r14, [rcx+30h]
0x180009590  xor     ebx, ebx
0x180009592  mov     rsi, rcx
0x180009595  movups  xmmword ptr [rsp+360h+pBindOptions.cbStruct], xmm0
0x18000959a  movups  [rsp+360h+var_330], xmm0
0x18000959f  movups  [rsp+360h+var_320], xmm0
0x1800095a4  test    r14, r14
0x1800095a7  jnz     short loc_1800095BE
0x1800095a9  mov     edi, 80070057h
0x1800095ae  mov     ecx, edi
0x1800095b0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800095b5  add     rsi, 28h ; '('
0x1800095b9  jmp     loc_180009683
0x1800095be  add     rsi, 28h ; '('
0x1800095c2  xor     edx, edx; dwCoInit
0x1800095c4  xor     ecx, ecx; pvReserved
0x1800095c6  xor     edi, edi
0x1800095c8  movsxd  r15, dword ptr [rsi]
0x1800095cb  call    cs:__imp_CoInitializeEx
0x1800095d1  test    eax, eax
0x1800095d3  js      short loc_1800095DA
0x1800095d5  lea     ebx, [rdi+1]
0x1800095d8  jmp     short loc_1800095EA
0x1800095da  cmp     eax, 80010106h
0x1800095df  jz      short loc_1800095EA
0x1800095e1  mov     ecx, eax
0x1800095e3  mov     edi, eax
0x1800095e5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800095ea  mov     ecx, edi
0x1800095ec  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800095f1  mov     r8d, 32h ; '2'; cchMax
0x1800095f7  lea     rdx, [rsp+360h+sz]; lpsz
0x1800095fc  lea     rcx, CLSID_EditionUpgradeManager; rguid
0x180009603  call    cs:__imp_StringFromGUID2
0x180009609  test    eax, eax
0x18000960b  jnz     short loc_180009616
0x18000960d  mov     edi, 80004005h
0x180009612  mov     ecx, edi
0x180009614  jmp     short loc_18000967E
0x180009616  lea     r9, [rsp+360h+sz]
0x18000961b  mov     edx, 12Ch; unsigned __int64
0x180009620  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x180009627  lea     rcx, [rbp+260h+pszName]; unsigned __int16 *
0x18000962b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009630  mov     edi, eax
0x180009632  test    eax, eax
0x180009634  js      short loc_18000967C
0x180009636  xorps   xmm0, xmm0
0x180009639  mov     [rsp+360h+pBindOptions.cbStruct], 30h ; '0'
0x180009641  xorps   xmm1, xmm1
0x180009644  mov     qword ptr [rsp+360h+var_320+8], r15
0x180009649  mov     r9, r14; ppv
0x18000964c  mov     dword ptr [rsp+360h+var_330+4], 4
0x180009654  lea     r8, _GUID_f2dcb80d_0670_44bc_9002_cd18688730af; riid
0x18000965b  lea     rdx, [rsp+360h+pBindOptions]; pBindOptions
0x180009660  lea     rcx, [rbp+260h+pszName]; pszName
0x180009664  movdqu  xmmword ptr [rsp+360h+pBindOptions.grfFlags], xmm0
0x18000966a  movdqu  [rsp+360h+var_330+8], xmm1
0x180009670  call    cs:__imp_CoGetObject
0x180009676  mov     edi, eax
0x180009678  test    eax, eax
0x18000967a  jns     short loc_180009683
0x18000967c  mov     ecx, eax
0x18000967e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180009683  mov     ecx, edi
0x180009685  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000968a  test    ebx, ebx
0x18000968c  jz      short loc_180009694
0x18000968e  call    cs:__imp_CoUninitialize
0x180009694  test    edi, edi
0x180009696  jns     short loc_18000969C
0x180009698  mov     ecx, edi
0x18000969a  jmp     short loc_1800096B5
0x18000969c  mov     rcx, [r14]
0x18000969f  mov     edx, [rsi]
0x1800096a1  mov     rax, [rcx]
0x1800096a4  mov     rax, [rax+18h]
0x1800096a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096ad  mov     edi, eax
0x1800096af  test    eax, eax
0x1800096b1  jns     short loc_1800096BA
0x1800096b3  mov     ecx, eax
0x1800096b5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800096ba  mov     ecx, edi
0x1800096bc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800096c1  mov     eax, edi
0x1800096c3  mov     rcx, [rbp+260h+var_40]
0x1800096ca  xor     rcx, rsp; StackCookie
0x1800096cd  call    __security_check_cookie
0x1800096d2  add     rsp, 338h
0x1800096d9  pop     r15
0x1800096db  pop     r14
0x1800096dd  pop     rdi
0x1800096de  pop     rsi
0x1800096df  pop     rbx
0x1800096e0  pop     rbp
0x1800096e1  retn
```
