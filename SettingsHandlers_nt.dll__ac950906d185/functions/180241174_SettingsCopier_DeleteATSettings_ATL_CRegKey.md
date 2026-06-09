# SettingsCopier::DeleteATSettings(ATL::CRegKey &)

- ea: `0x180241174`
- end: `0x1802414e0`
- name: `?DeleteATSettings@SettingsCopier@@CAJAEAVCRegKey@ATL@@@Z`
- size: `876`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180240ee0`

## callees

- `0x18001a64c`
- `0x18009af1c`
- `0x180238cdc`
- `0x180239100`
- `0x180239f74`
- `0x18023a4b8`
- `0x18023b6f0`
- `0x180241174`
- `0x180241d44`
- `0x180241ef8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18024127e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802412b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180241339`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180241447`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180241484`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802414a1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802414b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18024127e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802412b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180241339`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180241447`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180241484`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802414a1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802414b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180241318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180241318`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024137b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802413bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180241434`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024137b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802413bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180241434`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180241423`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180241423`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180241304`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180241304`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1802413a7`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1802413a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802413ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802413ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802413cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241412`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802413cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241412`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180241365`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180241365`
- `KERNEL32!RegDeleteTreeW` at `0x180241470`
- `KERNEL32!RegDeleteTreeW` at `0x180241470`

## string_xrefs

- `0x1802413f4`: `SymbolicLinkValue`
- `0x180241231`: `%s\ATConfig`
- `0x180241298`: `%s\ATConfig`
- `0x1802412ef`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SettingsCopier::DeleteATSettings(HKEY *a1)
{
  void *v2; // rbx
  __int64 v3; // rdx
  unsigned __int16 *v4; // rdi
  int *v5; // rbx
  __int64 v6; // rdi
  unsigned int v7; // r11d
  unsigned __int64 v8; // rbx
  LSTATUS v9; // r14d
  unsigned __int64 v10; // rdx
  __int64 v12; // rsi
  const WCHAR *v13; // r14
  void *v14; // rcx
  HANDLE EventW; // r15
  signed int LastError; // eax
  DWORD v17; // esi
  LSTATUS v18; // eax
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  void *Block; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v21; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v22; // [rsp+48h] [rbp-18h] BYREF
  __int64 v23; // [rsp+50h] [rbp-10h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int16 *v26; // [rsp+B8h] [rbp+58h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v26);
  v21 = 0;
  v22 = 0;
  v2 = 0;
  Block = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( !CATUtils::IsInteractiveUser() )
  {
    v12 = -2147483647;
    v13 = SettingsCopier::_ATConfigKeyString;
    v4 = v26;
LABEL_17:
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError <= 0 )
      {
LABEL_21:
        free(v2);
        goto LABEL_37;
      }
      v9 = (unsigned __int16)LastError;
LABEL_20:
      v9 |= 0x80070000;
      goto LABEL_21;
    }
    v9 = RegOpenKeyExW((HKEY)v12, v13, 8u, 0x20019u, &hKey);
    if ( v9 )
    {
      CloseHandle(EventW);
LABEL_24:
      if ( v9 <= 0 )
        goto LABEL_21;
      v9 = (unsigned __int16)v9;
      goto LABEL_20;
    }
    v9 = RegNotifyChangeKeyValue(hKey, 0, 5u, EventW, 1);
    if ( v9 )
    {
      CloseHandle(EventW);
      RegCloseKey(hKey);
      goto LABEL_24;
    }
    v9 = RegQueryValueExW(hKey, L"SymbolicLinkValue", 0, &Type, 0, &cbData);
    RegCloseKey(hKey);
    v17 = WaitForSingleObject(EventW, 0);
    CloseHandle(EventW);
    if ( !v17 )
    {
      free(v2);
      v9 = -2147023590;
      goto LABEL_37;
    }
    if ( v9 )
    {
      if ( v9 != 2 )
        goto LABEL_24;
    }
    else if ( Type == 6 )
    {
      free(v2);
      v9 = -2147023432;
      goto LABEL_37;
    }
    v18 = RegDeleteTreeW(*a1, 0);
    v14 = v2;
    if ( !v18 )
    {
      free(v2);
      v9 = 0;
      goto LABEL_37;
    }
LABEL_33:
    free(v14);
    v9 = -2147467259;
    goto LABEL_37;
  }
  v3 = *(_QWORD *)CATUtils::SessionKeyString(&v23);
  v4 = v26;
  v5 = (int *)(v26 - 12);
  if ( (unsigned __int16 *)(v3 - 24) != v26 - 12 )
  {
    if ( v5[4] >= 0 && *(_QWORD *)(v3 - 24) == *(_QWORD *)v5 )
    {
      v6 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
      ATL::CStringData::Release((ATL::CStringData *)v5);
      v4 = (unsigned __int16 *)(v6 + 24);
      v26 = v4;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v26, v3, *(unsigned int *)(v3 - 16));
      v4 = v26;
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
  if ( (int)StringCchLengthW(SettingsCopier::_ATSessionConfigKeyString, 0x7FFFFFFFu, &v21) < 0
    || (int)StringCchLengthW(v4, v7, &v22) < 0
    || (v8 = v21 + v22, v21 + v22 < v21) )
  {
    v14 = 0;
    goto LABEL_33;
  }
  if ( (unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v21 + v22) )
  {
    v10 = v8;
    v2 = Block;
    if ( StringCchPrintfW((unsigned __int16 *)Block, v10, SettingsCopier::_ATSessionConfigKeyString, v4) < 0 )
    {
      free(v2);
      ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
      return 2147500037LL;
    }
    v12 = -2147483646;
    v13 = (const WCHAR *)v2;
    goto LABEL_17;
  }
  free(Block);
  v9 = -2147024882;
LABEL_37:
  ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180241174  push    rbp
0x180241176  push    rbx
0x180241177  push    rsi
0x180241178  push    rdi
0x180241179  push    r12
0x18024117b  push    r14
0x18024117d  push    r15
0x18024117f  mov     rbp, rsp
0x180241182  sub     rsp, 60h
0x180241186  mov     r12, rcx
0x180241189  lea     rcx, [rbp+arg_18]
0x18024118d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180241192  nop
0x180241193  mov     [rbp+var_20], 0
0x18024119b  mov     [rbp+var_18], 0
0x1802411a3  xor     ebx, ebx
0x1802411a5  mov     [rbp+Block], rbx
0x1802411a9  mov     [rbp+hKey], rbx
0x1802411ad  mov     [rbp+Type], ebx
0x1802411b0  mov     [rbp+cbData], ebx
0x1802411b3  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x1802411b8  test    eax, eax
0x1802411ba  jz      loc_1802412E8
0x1802411c0  lea     rcx, [rbp+var_10]
0x1802411c4  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x1802411c9  nop
0x1802411ca  mov     rdx, [rax]
0x1802411cd  lea     rcx, [rdx-18h]
0x1802411d1  mov     rdi, [rbp+arg_18]
0x1802411d5  lea     rbx, [rdi-18h]
0x1802411d9  cmp     rcx, rbx
0x1802411dc  jz      short loc_180241217
0x1802411de  cmp     dword ptr [rbx+10h], 0
0x1802411e2  jl      short loc_180241206
0x1802411e4  mov     rax, [rbx]
0x1802411e7  cmp     [rcx], rax
0x1802411ea  jnz     short loc_180241206
0x1802411ec  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1802411f1  mov     rdi, rax
0x1802411f4  mov     rcx, rbx; this
0x1802411f7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1802411fc  add     rdi, 18h
0x180241200  mov     [rbp+arg_18], rdi
0x180241204  jmp     short loc_180241217
0x180241206  mov     r8d, [rdx-10h]
0x18024120a  lea     rcx, [rbp+arg_18]
0x18024120e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180241213  mov     rdi, [rbp+arg_18]
0x180241217  mov     rcx, [rbp+var_10]
0x18024121b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18024121f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180241224  lea     r8, [rbp+var_20]; unsigned __int64 *
0x180241228  mov     r11d, 7FFFFFFFh
0x18024122e  mov     edx, r11d; unsigned __int64
0x180241231  lea     rcx, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x180241238  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18024123d  test    eax, eax
0x18024123f  js      loc_1802412E1
0x180241245  lea     r8, [rbp+var_18]; unsigned __int64 *
0x180241249  mov     edx, r11d; unsigned __int64
0x18024124c  mov     rcx, rdi; unsigned __int16 *
0x18024124f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180241254  test    eax, eax
0x180241256  js      loc_1802412E1
0x18024125c  mov     rbx, [rbp+var_18]
0x180241260  add     rbx, [rbp+var_20]
0x180241264  cmp     rbx, [rbp+var_20]
0x180241268  jb      short loc_1802412E1
0x18024126a  mov     rdx, rbx
0x18024126d  lea     rcx, [rbp+Block]
0x180241271  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x180241276  test    al, al
0x180241278  jnz     short loc_180241295
0x18024127a  mov     rcx, [rbp+Block]; Block
0x18024127e  call    cs:__imp_free
0x180241285  nop     dword ptr [rax+rax+00h]
0x18024128a  mov     r14d, 8007000Eh
0x180241290  jmp     loc_1802414C4
0x180241295  mov     r9, rdi
0x180241298  lea     r8, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x18024129f  mov     rdx, rbx; unsigned __int64
0x1802412a2  mov     rbx, [rbp+Block]
0x1802412a6  mov     rcx, rbx; unsigned __int16 *
0x1802412a9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1802412ae  test    eax, eax
0x1802412b0  jns     short loc_1802412D5
0x1802412b2  mov     rcx, rbx; Block
0x1802412b5  call    cs:__imp_free
0x1802412bc  nop     dword ptr [rax+rax+00h]
0x1802412c1  nop
0x1802412c2  lea     rcx, [rdi-18h]; this
0x1802412c6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1802412cb  mov     eax, 80004005h
0x1802412d0  jmp     loc_1802414D0
0x1802412d5  mov     rsi, 0FFFFFFFF80000002h
0x1802412dc  mov     r14, rbx
0x1802412df  jmp     short loc_1802412FA
0x1802412e1  xor     ecx, ecx
0x1802412e3  jmp     loc_180241484
0x1802412e8  mov     rsi, 0FFFFFFFF80000001h
0x1802412ef  lea     r14, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1802412f6  mov     rdi, [rbp+arg_18]
0x1802412fa  xor     r9d, r9d; lpName
0x1802412fd  xor     r8d, r8d; bInitialState
0x180241300  xor     edx, edx; bManualReset
0x180241302  xor     ecx, ecx; lpEventAttributes
0x180241304  call    cs:__imp_CreateEventW
0x18024130b  nop     dword ptr [rax+rax+00h]
0x180241310  mov     r15, rax
0x180241313  test    rax, rax
0x180241316  jnz     short loc_18024134A
0x180241318  call    cs:__imp_GetLastError
0x18024131f  nop     dword ptr [rax+rax+00h]
0x180241324  mov     r14d, eax
0x180241327  test    eax, eax
0x180241329  jle     short loc_180241336
0x18024132b  movzx   r14d, ax
0x18024132f  or      r14d, 80070000h
0x180241336  mov     rcx, rbx; Block
0x180241339  call    cs:__imp_free
0x180241340  nop     dword ptr [rax+rax+00h]
0x180241345  jmp     loc_1802414C4
0x18024134a  lea     rax, [rbp+hKey]
0x18024134e  mov     [rsp+60h+phkResult], rax; phkResult
0x180241353  mov     r9d, 20019h; samDesired
0x180241359  mov     r8d, 8; ulOptions
0x18024135f  mov     rdx, r14; lpSubKey
0x180241362  mov     rcx, rsi; hKey
0x180241365  call    cs:__imp_RegOpenKeyExW
0x18024136c  nop     dword ptr [rax+rax+00h]
0x180241371  mov     r14d, eax
0x180241374  test    eax, eax
0x180241376  jz      short loc_180241392
0x180241378  mov     rcx, r15; hObject
0x18024137b  call    cs:__imp_CloseHandle
0x180241382  nop     dword ptr [rax+rax+00h]
0x180241387  test    r14d, r14d
0x18024138a  jle     short loc_180241336
0x18024138c  movzx   r14d, r14w
0x180241390  jmp     short loc_18024132F
0x180241392  mov     dword ptr [rsp+60h+phkResult], 1; fAsynchronous
0x18024139a  mov     r9, r15; hEvent
0x18024139d  xor     edx, edx; bWatchSubtree
0x18024139f  lea     r8d, [rdx+5]; dwNotifyFilter
0x1802413a3  mov     rcx, [rbp+hKey]; hKey
0x1802413a7  call    cs:__imp_RegNotifyChangeKeyValue
0x1802413ae  nop     dword ptr [rax+rax+00h]
0x1802413b3  mov     r14d, eax
0x1802413b6  test    eax, eax
0x1802413b8  jz      short loc_1802413DB
0x1802413ba  mov     rcx, r15; hObject
0x1802413bd  call    cs:__imp_CloseHandle
0x1802413c4  nop     dword ptr [rax+rax+00h]
0x1802413c9  mov     rcx, [rbp+hKey]; hKey
0x1802413cd  call    cs:__imp_RegCloseKey
0x1802413d4  nop     dword ptr [rax+rax+00h]
0x1802413d9  jmp     short loc_180241387
0x1802413db  lea     rax, [rbp+cbData]
0x1802413df  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1802413e4  mov     [rsp+60h+phkResult], 0; lpData
0x1802413ed  lea     r9, [rbp+Type]; lpType
0x1802413f1  xor     r8d, r8d; lpReserved
0x1802413f4  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x1802413fb  mov     rcx, [rbp+hKey]; hKey
0x1802413ff  call    cs:__imp_RegQueryValueExW
0x180241406  nop     dword ptr [rax+rax+00h]
0x18024140b  mov     r14d, eax
0x18024140e  mov     rcx, [rbp+hKey]; hKey
0x180241412  call    cs:__imp_RegCloseKey
0x180241419  nop     dword ptr [rax+rax+00h]
0x18024141e  xor     edx, edx; dwMilliseconds
0x180241420  mov     rcx, r15; hHandle
0x180241423  call    cs:__imp_WaitForSingleObject
0x18024142a  nop     dword ptr [rax+rax+00h]
0x18024142f  mov     esi, eax
0x180241431  mov     rcx, r15; hObject
0x180241434  call    cs:__imp_CloseHandle
0x18024143b  nop     dword ptr [rax+rax+00h]
0x180241440  test    esi, esi
0x180241442  jnz     short loc_18024145B
0x180241444  mov     rcx, rbx; Block
0x180241447  call    cs:__imp_free
0x18024144e  nop     dword ptr [rax+rax+00h]
0x180241453  mov     r14d, 8007051Ah
0x180241459  jmp     short loc_1802414C4
0x18024145b  test    r14d, r14d
0x18024145e  jz      short loc_180241498
0x180241460  cmp     r14d, 2
0x180241464  jnz     loc_180241387
0x18024146a  xor     edx, edx; lpSubKey
0x18024146c  mov     rcx, [r12]; hKey
0x180241470  call    cs:__imp_RegDeleteTreeW
0x180241477  nop     dword ptr [rax+rax+00h]
0x18024147c  nop
0x18024147d  mov     rcx, rbx; Block
0x180241480  test    eax, eax
0x180241482  jz      short loc_1802414B5
0x180241484  call    cs:__imp_free
0x18024148b  nop     dword ptr [rax+rax+00h]
0x180241490  mov     r14d, 80004005h
0x180241496  jmp     short loc_1802414C4
0x180241498  cmp     [rbp+Type], 6
0x18024149c  jnz     short loc_18024146A
0x18024149e  mov     rcx, rbx; Block
0x1802414a1  call    cs:__imp_free
0x1802414a8  nop     dword ptr [rax+rax+00h]
0x1802414ad  mov     r14d, 800705B8h
0x1802414b3  jmp     short loc_1802414C4
0x1802414b5  call    cs:__imp_free
0x1802414bc  nop     dword ptr [rax+rax+00h]
0x1802414c1  xor     r14d, r14d
0x1802414c4  lea     rcx, [rdi-18h]; this
0x1802414c8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1802414cd  mov     eax, r14d
0x1802414d0  add     rsp, 60h
0x1802414d4  pop     r15
0x1802414d6  pop     r14
0x1802414d8  pop     r12
0x1802414da  pop     rdi
0x1802414db  pop     rsi
0x1802414dc  pop     rbx
0x1802414dd  pop     rbp
0x1802414de  retn
```
