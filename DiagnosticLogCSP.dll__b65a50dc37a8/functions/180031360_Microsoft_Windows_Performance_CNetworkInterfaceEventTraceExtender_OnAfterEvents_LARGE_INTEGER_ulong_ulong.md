# Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x180031360`
- end: `0x180031542`
- name: `?OnAfterEvents@CNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `482`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001b90`
- `0x18000265c`
- `0x18002834c`
- `0x180031360`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800314f8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031532`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800314f8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031532`

## string_xrefs

- `0x180031389`: `Iphlpapi.dll`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  int v4; // edi
  unsigned int v9; // r14d
  FARPROC v10; // rax
  _DWORD *v11; // rsi
  __int64 v12; // rcx
  int v13; // esi
  FARPROC v14; // rax
  __int64 v15; // rcx
  _DWORD *v17; // [rsp+30h] [rbp-D0h] BYREF
  HMODULE hLibModule[3]; // [rsp+38h] [rbp-C8h] BYREF
  char v19; // [rsp+50h] [rbp-B0h]
  __int64 v20[3]; // [rsp+58h] [rbp-A8h] BYREF
  char v21; // [rsp+70h] [rbp-90h]
  __int64 v22[3]; // [rsp+78h] [rbp-88h] BYREF
  char v23; // [rsp+90h] [rbp-70h]
  _WORD v24[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v25; // [rsp+A4h] [rbp-5Ch]
  union _LARGE_INTEGER v26; // [rsp+B0h] [rbp-50h]
  __int128 v27; // [rsp+B8h] [rbp-48h]
  _DWORD *v28; // [rsp+E8h] [rbp-18h]
  int v29; // [rsp+F0h] [rbp-10h]
  unsigned int v30; // [rsp+F4h] [rbp-Ch]

  v4 = 0;
  hLibModule[1] = (HMODULE)L"Iphlpapi.dll";
  hLibModule[0] = 0;
  v20[0] = (__int64)hLibModule;
  hLibModule[2] = 0;
  v20[1] = (__int64)"GetIfTable2Ex";
  v19 = 0;
  v22[0] = (__int64)hLibModule;
  v20[2] = 0;
  v22[1] = (__int64)"FreeMibTable";
  v21 = 0;
  v22[2] = 0;
  v23 = 0;
  v9 = 1;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v20) )
    goto LABEL_8;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v22) )
    goto LABEL_8;
  v17 = 0;
  v10 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v20);
  if ( ((unsigned int (__fastcall *)(_QWORD, _DWORD **))v10)(0, &v17) )
    goto LABEL_8;
  v11 = v17;
  if ( !*v17 )
  {
LABEL_7:
    v14 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v22);
    ((void (__fastcall *)(_DWORD *))v14)(v17);
LABEL_8:
    v15 = *((_QWORD *)this + 1);
    if ( v15 )
      v9 = (*(__int64 (__fastcall **)(__int64, union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v15 + 96LL))(
             v15,
             a2,
             a3,
             a4);
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
    return v9;
  }
  while ( 1 )
  {
    memset_0(v24, 0, 0x58u);
    v12 = *((_QWORD *)this + 2);
    v24[0] = a4;
    v26 = a2;
    v27 = SystemConfigExGuid;
    v25 = 36;
    v29 = 1352;
    v30 = a3;
    v28 = &v11[338 * v4 + 2];
    v13 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD, _QWORD))(*(_QWORD *)v12 + 192LL))(v12, v24, 0, 0);
    if ( v13 < 0 )
      break;
    v11 = v17;
    if ( (unsigned int)++v4 >= *v17 )
      goto LABEL_7;
  }
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180031360  push    rbp
0x180031362  push    rbx
0x180031363  push    rsi
0x180031364  push    rdi
0x180031365  push    r12
0x180031367  push    r13
0x180031369  push    r14
0x18003136b  push    r15
0x18003136d  lea     rbp, [rsp-18h]
0x180031372  sub     rsp, 118h
0x180031379  mov     rax, cs:__security_cookie
0x180031380  xor     rax, rsp
0x180031383  mov     [rbp+50h+var_50], rax
0x180031387  xor     edi, edi
0x180031389  lea     rax, aIphlpapiDll; "Iphlpapi.dll"
0x180031390  mov     [rsp+150h+var_110], rax
0x180031395  mov     r15, rcx
0x180031398  lea     rax, [rsp+150h+hLibModule]
0x18003139d  mov     [rsp+150h+hLibModule], rdi
0x1800313a2  mov     [rsp+150h+var_F8], rax
0x1800313a7  lea     rcx, [rsp+150h+var_F8]
0x1800313ac  lea     rax, aGetiftable2ex; "GetIfTable2Ex"
0x1800313b3  mov     [rsp+150h+var_108], rdi
0x1800313b8  mov     [rsp+150h+var_F0], rax
0x1800313bd  mov     r13d, r9d
0x1800313c0  lea     rax, [rsp+150h+hLibModule]
0x1800313c5  mov     [rsp+150h+var_100], dil
0x1800313ca  mov     [rsp+150h+var_D8], rax
0x1800313cf  mov     r12d, r8d
0x1800313d2  lea     rax, aFreemibtable; "FreeMibTable"
0x1800313d9  mov     [rsp+150h+var_E8], rdi
0x1800313de  mov     [rbp+50h+var_D0], rax
0x1800313e2  mov     rbx, rdx
0x1800313e5  mov     [rsp+150h+var_E0], dil
0x1800313ea  mov     [rbp+50h+var_C8], rdi
0x1800313ee  mov     [rbp+50h+var_C0], dil
0x1800313f2  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x1800313f7  lea     r14d, [rdi+1]
0x1800313fb  test    rax, rax
0x1800313fe  jz      loc_1800314CD
0x180031404  lea     rcx, [rsp+150h+var_D8]
0x180031409  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18003140e  test    rax, rax
0x180031411  jz      loc_1800314CD
0x180031417  lea     rcx, [rsp+150h+var_F8]
0x18003141c  mov     [rsp+150h+var_120], rdi
0x180031421  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180031426  lea     rdx, [rsp+150h+var_120]
0x18003142b  xor     ecx, ecx
0x18003142d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031432  test    eax, eax
0x180031434  jnz     loc_1800314CD
0x18003143a  mov     rsi, [rsp+150h+var_120]
0x18003143f  cmp     [rsi], edi
0x180031441  jbe     short loc_1800314B9
0x180031443  xor     edx, edx; Val
0x180031445  lea     rcx, [rbp+50h+var_B0]; void *
0x180031449  lea     r8d, [rdx+58h]; Size
0x18003144d  call    memset_0
0x180031452  movups  xmm0, cs:SystemConfigExGuid
0x180031459  mov     rcx, [r15+10h]
0x18003145d  lea     rdx, [rbp+50h+var_B0]
0x180031461  mov     [rbp+50h+var_B0], r13w
0x180031466  xor     r9d, r9d
0x180031469  mov     [rbp+50h+var_A0], rbx
0x18003146d  xor     r8d, r8d
0x180031470  movdqu  [rbp+50h+var_98], xmm0
0x180031475  mov     [rbp+50h+var_AC], 24h ; '$'
0x180031479  mov     [rbp+50h+var_60], 548h
0x180031480  mov     [rbp+50h+var_5C], r12d
0x180031484  mov     eax, edi
0x180031486  imul    rax, 548h
0x18003148d  add     rax, 8
0x180031491  add     rax, rsi
0x180031494  mov     [rbp+50h+var_68], rax
0x180031498  mov     rax, [rcx]
0x18003149b  mov     rax, [rax+0C0h]
0x1800314a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314a7  mov     esi, eax
0x1800314a9  test    eax, eax
0x1800314ab  js      short loc_180031528
0x1800314ad  mov     rsi, [rsp+150h+var_120]
0x1800314b2  add     edi, r14d
0x1800314b5  cmp     edi, [rsi]
0x1800314b7  jb      short loc_180031443
0x1800314b9  lea     rcx, [rsp+150h+var_D8]
0x1800314be  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x1800314c3  mov     rcx, [rsp+150h+var_120]
0x1800314c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314cd  mov     rcx, [r15+8]
0x1800314d1  test    rcx, rcx
0x1800314d4  jz      short loc_1800314EE
0x1800314d6  mov     rax, [rcx]
0x1800314d9  mov     r9d, r13d
0x1800314dc  mov     r8d, r12d
0x1800314df  mov     rdx, rbx
0x1800314e2  mov     rax, [rax+60h]
0x1800314e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314eb  mov     r14d, eax
0x1800314ee  mov     rcx, [rsp+150h+hLibModule]; hLibModule
0x1800314f3  test    rcx, rcx
0x1800314f6  jz      short loc_180031504
0x1800314f8  call    cs:__imp_FreeLibrary
0x1800314ff  nop     dword ptr [rax+rax+00h]
0x180031504  mov     eax, r14d
0x180031507  mov     rcx, [rbp+50h+var_50]
0x18003150b  xor     rcx, rsp; StackCookie
0x18003150e  call    __security_check_cookie
0x180031513  add     rsp, 118h
0x18003151a  pop     r15
0x18003151c  pop     r14
0x18003151e  pop     r13
0x180031520  pop     r12
0x180031522  pop     rdi
0x180031523  pop     rsi
0x180031524  pop     rbx
0x180031525  pop     rbp
0x180031526  retn
0x180031528  mov     rcx, [rsp+150h+hLibModule]; hLibModule
0x18003152d  test    rcx, rcx
0x180031530  jz      short loc_18003153E
0x180031532  call    cs:__imp_FreeLibrary
0x180031539  nop     dword ptr [rax+rax+00h]
0x18003153e  mov     eax, esi
0x180031540  jmp     short loc_180031507
```
