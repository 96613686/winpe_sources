# Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x180022930`
- end: `0x180022b05`
- name: `?OnAfterEvents@CNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `469`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001870`
- `0x180002420`
- `0x1800163cc`
- `0x180022930`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180022ac8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180022afb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180022ac8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180022afb`

## string_xrefs

- `0x180022959`: `Iphlpapi.dll`

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
  unsigned int (__fastcall *v10)(_QWORD, _DWORD **); // rax
  _DWORD *v11; // rsi
  __int64 v12; // rcx
  int v13; // esi
  void (__fastcall *v14)(_DWORD *); // rax
  __int64 v15; // rcx
  _DWORD *v17; // [rsp+30h] [rbp-D0h] BYREF
  HMODULE hLibModule[3]; // [rsp+38h] [rbp-C8h] BYREF
  char v19; // [rsp+50h] [rbp-B0h]
  _QWORD v20[3]; // [rsp+58h] [rbp-A8h] BYREF
  char v21; // [rsp+70h] [rbp-90h]
  _QWORD v22[3]; // [rsp+78h] [rbp-88h] BYREF
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
  v20[0] = hLibModule;
  hLibModule[2] = 0;
  v20[1] = "GetIfTable2Ex";
  v19 = 0;
  v22[0] = hLibModule;
  v20[2] = 0;
  v22[1] = "FreeMibTable";
  v21 = 0;
  v22[2] = 0;
  v23 = 0;
  v9 = 1;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v20) )
    goto LABEL_8;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v22) )
    goto LABEL_8;
  v17 = 0;
  v10 = (unsigned int (__fastcall *)(_QWORD, _DWORD **))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v20);
  if ( v10(0, &v17) )
    goto LABEL_8;
  v11 = v17;
  if ( !*v17 )
  {
LABEL_7:
    v14 = (void (__fastcall *)(_DWORD *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v22);
    v14(v17);
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
0x180022930  push    rbp
0x180022932  push    rbx
0x180022933  push    rsi
0x180022934  push    rdi
0x180022935  push    r12
0x180022937  push    r13
0x180022939  push    r14
0x18002293b  push    r15
0x18002293d  lea     rbp, [rsp-18h]
0x180022942  sub     rsp, 118h
0x180022949  mov     rax, cs:__security_cookie
0x180022950  xor     rax, rsp
0x180022953  mov     [rbp+50h+var_50], rax
0x180022957  xor     edi, edi
0x180022959  lea     rax, aIphlpapiDll; "Iphlpapi.dll"
0x180022960  mov     [rsp+150h+var_110], rax
0x180022965  mov     r15, rcx
0x180022968  lea     rax, [rsp+150h+hLibModule]
0x18002296d  mov     [rsp+150h+hLibModule], rdi
0x180022972  mov     [rsp+150h+var_F8], rax
0x180022977  lea     rcx, [rsp+150h+var_F8]
0x18002297c  lea     rax, aGetiftable2ex; "GetIfTable2Ex"
0x180022983  mov     [rsp+150h+var_108], rdi
0x180022988  mov     [rsp+150h+var_F0], rax
0x18002298d  mov     r13d, r9d
0x180022990  lea     rax, [rsp+150h+hLibModule]
0x180022995  mov     [rsp+150h+var_100], dil
0x18002299a  mov     [rsp+150h+var_D8], rax
0x18002299f  mov     r12d, r8d
0x1800229a2  lea     rax, aFreemibtable; "FreeMibTable"
0x1800229a9  mov     [rsp+150h+var_E8], rdi
0x1800229ae  mov     [rbp+50h+var_D0], rax
0x1800229b2  mov     rbx, rdx
0x1800229b5  mov     [rsp+150h+var_E0], dil
0x1800229ba  mov     [rbp+50h+var_C8], rdi
0x1800229be  mov     [rbp+50h+var_C0], dil
0x1800229c2  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x1800229c7  lea     r14d, [rdi+1]
0x1800229cb  test    rax, rax
0x1800229ce  jz      loc_180022A9D
0x1800229d4  lea     rcx, [rsp+150h+var_D8]
0x1800229d9  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x1800229de  test    rax, rax
0x1800229e1  jz      loc_180022A9D
0x1800229e7  lea     rcx, [rsp+150h+var_F8]
0x1800229ec  mov     [rsp+150h+var_120], rdi
0x1800229f1  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x1800229f6  lea     rdx, [rsp+150h+var_120]
0x1800229fb  xor     ecx, ecx
0x1800229fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a02  test    eax, eax
0x180022a04  jnz     loc_180022A9D
0x180022a0a  mov     rsi, [rsp+150h+var_120]
0x180022a0f  cmp     [rsi], edi
0x180022a11  jbe     short loc_180022A89
0x180022a13  xor     edx, edx; Val
0x180022a15  lea     rcx, [rbp+50h+var_B0]; void *
0x180022a19  lea     r8d, [rdx+58h]; Size
0x180022a1d  call    memset_0
0x180022a22  movups  xmm0, cs:SystemConfigExGuid
0x180022a29  mov     rcx, [r15+10h]
0x180022a2d  lea     rdx, [rbp+50h+var_B0]
0x180022a31  mov     [rbp+50h+var_B0], r13w
0x180022a36  xor     r9d, r9d
0x180022a39  mov     [rbp+50h+var_A0], rbx
0x180022a3d  xor     r8d, r8d
0x180022a40  movdqu  [rbp+50h+var_98], xmm0
0x180022a45  mov     [rbp+50h+var_AC], 24h ; '$'
0x180022a49  mov     [rbp+50h+var_60], 548h
0x180022a50  mov     [rbp+50h+var_5C], r12d
0x180022a54  mov     eax, edi
0x180022a56  imul    rax, 548h
0x180022a5d  add     rax, 8
0x180022a61  add     rax, rsi
0x180022a64  mov     [rbp+50h+var_68], rax
0x180022a68  mov     rax, [rcx]
0x180022a6b  mov     rax, [rax+0C0h]
0x180022a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a77  mov     esi, eax
0x180022a79  test    eax, eax
0x180022a7b  js      short loc_180022AF1
0x180022a7d  mov     rsi, [rsp+150h+var_120]
0x180022a82  add     edi, r14d
0x180022a85  cmp     edi, [rsi]
0x180022a87  jb      short loc_180022A13
0x180022a89  lea     rcx, [rsp+150h+var_D8]
0x180022a8e  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180022a93  mov     rcx, [rsp+150h+var_120]
0x180022a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a9d  mov     rcx, [r15+8]
0x180022aa1  test    rcx, rcx
0x180022aa4  jz      short loc_180022ABE
0x180022aa6  mov     rax, [rcx]
0x180022aa9  mov     r9d, r13d
0x180022aac  mov     r8d, r12d
0x180022aaf  mov     rdx, rbx
0x180022ab2  mov     rax, [rax+60h]
0x180022ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022abb  mov     r14d, eax
0x180022abe  mov     rcx, [rsp+150h+hLibModule]; hLibModule
0x180022ac3  test    rcx, rcx
0x180022ac6  jz      short loc_180022ACE
0x180022ac8  call    cs:__imp_FreeLibrary
0x180022ace  mov     eax, r14d
0x180022ad1  mov     rcx, [rbp+50h+var_50]
0x180022ad5  xor     rcx, rsp; StackCookie
0x180022ad8  call    __security_check_cookie
0x180022add  add     rsp, 118h
0x180022ae4  pop     r15
0x180022ae6  pop     r14
0x180022ae8  pop     r13
0x180022aea  pop     r12
0x180022aec  pop     rdi
0x180022aed  pop     rsi
0x180022aee  pop     rbx
0x180022aef  pop     rbp
0x180022af0  retn
0x180022af1  mov     rcx, [rsp+150h+hLibModule]; hLibModule
0x180022af6  test    rcx, rcx
0x180022af9  jz      short loc_180022B01
0x180022afb  call    cs:__imp_FreeLibrary
0x180022b01  mov     eax, esi
0x180022b03  jmp     short loc_180022AD1
```
