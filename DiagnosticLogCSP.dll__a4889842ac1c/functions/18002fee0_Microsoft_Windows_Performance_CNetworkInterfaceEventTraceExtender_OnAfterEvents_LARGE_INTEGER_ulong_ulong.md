# Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18002fee0`
- end: `0x1800300b5`
- name: `?OnAfterEvents@CNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `469`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001b60`
- `0x18000262c`
- `0x1800271c8`
- `0x18002fee0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030078`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800300ab`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030078`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800300ab`

## string_xrefs

- `0x18002ff09`: `Iphlpapi.dll`

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
0x18002fee0  push    rbp
0x18002fee2  push    rbx
0x18002fee3  push    rsi
0x18002fee4  push    rdi
0x18002fee5  push    r12
0x18002fee7  push    r13
0x18002fee9  push    r14
0x18002feeb  push    r15
0x18002feed  lea     rbp, [rsp-18h]
0x18002fef2  sub     rsp, 118h
0x18002fef9  mov     rax, cs:__security_cookie
0x18002ff00  xor     rax, rsp
0x18002ff03  mov     [rbp+50h+var_50], rax
0x18002ff07  xor     edi, edi
0x18002ff09  lea     rax, aIphlpapiDll; "Iphlpapi.dll"
0x18002ff10  mov     [rsp+150h+var_110], rax
0x18002ff15  mov     r15, rcx
0x18002ff18  lea     rax, [rsp+150h+hLibModule]
0x18002ff1d  mov     [rsp+150h+hLibModule], rdi
0x18002ff22  mov     [rsp+150h+var_F8], rax
0x18002ff27  lea     rcx, [rsp+150h+var_F8]
0x18002ff2c  lea     rax, aGetiftable2ex; "GetIfTable2Ex"
0x18002ff33  mov     [rsp+150h+var_108], rdi
0x18002ff38  mov     [rsp+150h+var_F0], rax
0x18002ff3d  mov     r13d, r9d
0x18002ff40  lea     rax, [rsp+150h+hLibModule]
0x18002ff45  mov     [rsp+150h+var_100], dil
0x18002ff4a  mov     [rsp+150h+var_D8], rax
0x18002ff4f  mov     r12d, r8d
0x18002ff52  lea     rax, aFreemibtable; "FreeMibTable"
0x18002ff59  mov     [rsp+150h+var_E8], rdi
0x18002ff5e  mov     [rbp+50h+var_D0], rax
0x18002ff62  mov     rbx, rdx
0x18002ff65  mov     [rsp+150h+var_E0], dil
0x18002ff6a  mov     [rbp+50h+var_C8], rdi
0x18002ff6e  mov     [rbp+50h+var_C0], dil
0x18002ff72  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002ff77  lea     r14d, [rdi+1]
0x18002ff7b  test    rax, rax
0x18002ff7e  jz      loc_18003004D
0x18002ff84  lea     rcx, [rsp+150h+var_D8]
0x18002ff89  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002ff8e  test    rax, rax
0x18002ff91  jz      loc_18003004D
0x18002ff97  lea     rcx, [rsp+150h+var_F8]
0x18002ff9c  mov     [rsp+150h+var_120], rdi
0x18002ffa1  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002ffa6  lea     rdx, [rsp+150h+var_120]
0x18002ffab  xor     ecx, ecx
0x18002ffad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffb2  test    eax, eax
0x18002ffb4  jnz     loc_18003004D
0x18002ffba  mov     rsi, [rsp+150h+var_120]
0x18002ffbf  cmp     [rsi], edi
0x18002ffc1  jbe     short loc_180030039
0x18002ffc3  xor     edx, edx; Val
0x18002ffc5  lea     rcx, [rbp+50h+var_B0]; void *
0x18002ffc9  lea     r8d, [rdx+58h]; Size
0x18002ffcd  call    memset_0
0x18002ffd2  movups  xmm0, cs:SystemConfigExGuid
0x18002ffd9  mov     rcx, [r15+10h]
0x18002ffdd  lea     rdx, [rbp+50h+var_B0]
0x18002ffe1  mov     [rbp+50h+var_B0], r13w
0x18002ffe6  xor     r9d, r9d
0x18002ffe9  mov     [rbp+50h+var_A0], rbx
0x18002ffed  xor     r8d, r8d
0x18002fff0  movdqu  [rbp+50h+var_98], xmm0
0x18002fff5  mov     [rbp+50h+var_AC], 24h ; '$'
0x18002fff9  mov     [rbp+50h+var_60], 548h
0x180030000  mov     [rbp+50h+var_5C], r12d
0x180030004  mov     eax, edi
0x180030006  imul    rax, 548h
0x18003000d  add     rax, 8
0x180030011  add     rax, rsi
0x180030014  mov     [rbp+50h+var_68], rax
0x180030018  mov     rax, [rcx]
0x18003001b  mov     rax, [rax+0C0h]
0x180030022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030027  mov     esi, eax
0x180030029  test    eax, eax
0x18003002b  js      short loc_1800300A1
0x18003002d  mov     rsi, [rsp+150h+var_120]
0x180030032  add     edi, r14d
0x180030035  cmp     edi, [rsi]
0x180030037  jb      short loc_18002FFC3
0x180030039  lea     rcx, [rsp+150h+var_D8]
0x18003003e  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180030043  mov     rcx, [rsp+150h+var_120]
0x180030048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003004d  mov     rcx, [r15+8]
0x180030051  test    rcx, rcx
0x180030054  jz      short loc_18003006E
0x180030056  mov     rax, [rcx]
0x180030059  mov     r9d, r13d
0x18003005c  mov     r8d, r12d
0x18003005f  mov     rdx, rbx
0x180030062  mov     rax, [rax+60h]
0x180030066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003006b  mov     r14d, eax
0x18003006e  mov     rcx, [rsp+150h+hLibModule]; hLibModule
0x180030073  test    rcx, rcx
0x180030076  jz      short loc_18003007E
0x180030078  call    cs:__imp_FreeLibrary
0x18003007e  mov     eax, r14d
0x180030081  mov     rcx, [rbp+50h+var_50]
0x180030085  xor     rcx, rsp; StackCookie
0x180030088  call    __security_check_cookie
0x18003008d  add     rsp, 118h
0x180030094  pop     r15
0x180030096  pop     r14
0x180030098  pop     r13
0x18003009a  pop     r12
0x18003009c  pop     rdi
0x18003009d  pop     rsi
0x18003009e  pop     rbx
0x18003009f  pop     rbp
0x1800300a0  retn
0x1800300a1  mov     rcx, [rsp+150h+hLibModule]; hLibModule
0x1800300a6  test    rcx, rcx
0x1800300a9  jz      short loc_1800300B1
0x1800300ab  call    cs:__imp_FreeLibrary
0x1800300b1  mov     eax, esi
0x1800300b3  jmp     short loc_180030081
```
