# SettingsCopier::DeleteATSettings(ATL::CRegKey &)

- ea: `0x140011f08`
- end: `0x140012338`
- name: `?DeleteATSettings@SettingsCopier@@CAJAEAVCRegKey@ATL@@@Z`
- size: `1072`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x140011c60`

## callees

- `0x140006a78`
- `0x140009aa8`
- `0x14000ce48`
- `0x140011f08`
- `0x140015830`
- `0x140017010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1400121d0`
- `ADVAPI32!RegQueryValueExW` at `0x1400121d0`
- `ADVAPI32!RegOpenKeyExW` at `0x14001215c`
- `ADVAPI32!RegOpenKeyExW` at `0x14001215c`
- `ADVAPI32!RegCloseKey` at `0x1400121a8`
- `ADVAPI32!RegCloseKey` at `0x1400121dd`
- `ADVAPI32!RegCloseKey` at `0x1400121a8`
- `ADVAPI32!RegCloseKey` at `0x1400121dd`
- `KERNEL32!WaitForSingleObject` at `0x1400121e8`
- `KERNEL32!WaitForSingleObject` at `0x1400121e8`
- `KERNEL32!GetLastError` at `0x1400120fb`
- `KERNEL32!GetLastError` at `0x1400120fb`
- `KERNEL32!CloseHandle` at `0x14001216b`
- `KERNEL32!CloseHandle` at `0x14001219e`
- `KERNEL32!CloseHandle` at `0x1400121f3`
- `KERNEL32!CloseHandle` at `0x14001216b`
- `KERNEL32!CloseHandle` at `0x14001219e`
- `KERNEL32!CloseHandle` at `0x1400121f3`
- `KERNEL32!RegDeleteTreeW` at `0x1400122bb`
- `KERNEL32!RegDeleteTreeW` at `0x1400122bb`
- `KERNEL32!RegNotifyChangeKeyValue` at `0x14001218f`
- `KERNEL32!RegNotifyChangeKeyValue` at `0x14001218f`
- `KERNEL32!CreateEventW` at `0x1400120ed`
- `KERNEL32!CreateEventW` at `0x1400120ed`
- `msvcrt!malloc` at `0x140012044`
- `msvcrt!malloc` at `0x140012044`
- `msvcrt!free` at `0x140012072`
- `msvcrt!free` at `0x14001209e`
- `msvcrt!free` at `0x140012113`
- `msvcrt!free` at `0x140012200`
- `msvcrt!free` at `0x14001224f`
- `msvcrt!free` at `0x140012287`
- `msvcrt!free` at `0x1400122c9`
- `msvcrt!free` at `0x1400122f7`
- `msvcrt!free` at `0x140012072`
- `msvcrt!free` at `0x14001209e`
- `msvcrt!free` at `0x140012113`
- `msvcrt!free` at `0x140012200`
- `msvcrt!free` at `0x14001224f`
- `msvcrt!free` at `0x140012287`
- `msvcrt!free` at `0x1400122c9`
- `msvcrt!free` at `0x1400122f7`

## string_xrefs

- `0x1400121c5`: `SymbolicLinkValue`
- `0x140011fae`: `%s\ATConfig`
- `0x140012059`: `%s\ATConfig`
- `0x1400120dc`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`

## pseudocode

```c
__int64 __fastcall SettingsCopier::DeleteATSettings(HKEY *a1)
{
  __int64 v2; // rsi
  unsigned __int16 *v3; // rbx
  __int64 v4; // rax
  _QWORD *v5; // rdx
  __int64 v6; // rdx
  unsigned __int16 *v7; // rax
  unsigned __int64 v8; // r9
  __int64 v9; // rcx
  _WORD *v10; // rax
  __int64 v11; // rdx
  unsigned __int64 v12; // rdi
  size_t v13; // rcx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rcx
  _QWORD *v16; // rdx
  bool v17; // cc
  __int64 v18; // rdi
  const WCHAR *v19; // r14
  HANDLE EventW; // r15
  signed int LastError; // eax
  LSTATUS v23; // edi
  int v24; // r14d
  DWORD v25; // edi
  _WORD *v26; // [rsp+30h] [rbp-20h] BYREF
  __int64 v27; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v28; // [rsp+40h] [rbp-10h]
  DWORD Type; // [rsp+98h] [rbp+48h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+58h] BYREF

  v2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v26 = (_WORD *)v2;
  v3 = 0;
  v28 = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( IsInteractiveUser() )
  {
    v4 = CATUtils::SessionKeyString(&v27);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(&v26, v4);
    v5 = (_QWORD *)(v27 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v27 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
    v6 = 0x7FFFFFFF;
    v7 = SettingsCopier::_ATSessionConfigKeyString;
    do
    {
      if ( !*v7 )
        break;
      ++v7;
      --v6;
    }
    while ( v6 );
    v8 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
    v2 = (__int64)v26;
    if ( !v6 || !v26 )
      goto LABEL_26;
    v9 = 0x7FFFFFFF;
    v10 = v26;
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v9;
    }
    while ( v9 );
    v11 = (0x7FFFFFFF - v9) & ((unsigned __int128)-(__int128)(unsigned __int64)v9 >> 64);
    if ( !v9 || (v12 = v8 + v11, v8 + v11 < v8) )
    {
LABEL_26:
      v15 = 0;
      goto LABEL_21;
    }
    if ( v12 )
    {
      if ( 0xFFFFFFFFFFFFFFFFuLL / v12 < 2 )
        goto LABEL_23;
      v13 = 2 * v12;
    }
    else
    {
      v13 = 0;
    }
    v14 = (unsigned __int16 *)malloc(v13);
    v3 = v14;
    v28 = v14;
    if ( v14 )
    {
      if ( (int)StringCchPrintfW(v14, v12, SettingsCopier::_ATSessionConfigKeyString, v2) < 0 )
      {
        v15 = v3;
LABEL_21:
        free(v15);
        v16 = (_QWORD *)(v2 - 24);
        v17 = _InterlockedDecrement((volatile signed __int32 *)(v2 - 24 + 16)) <= 0;
LABEL_58:
        if ( v17 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 8LL))(*v16);
        return 2147500037LL;
      }
      v18 = -2147483646;
      v19 = v3;
      goto LABEL_28;
    }
LABEL_23:
    free(v3);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v2 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
    return 2147942414LL;
  }
  v18 = -2147483647;
  v19 = SettingsCopier::_ATConfigKeyString;
LABEL_28:
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    v23 = LastError;
    if ( LastError <= 0 )
    {
LABEL_32:
      free(v3);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
      return (unsigned int)v23;
    }
    v23 = (unsigned __int16)LastError;
LABEL_31:
    v23 |= 0x80070000;
    goto LABEL_32;
  }
  v23 = RegOpenKeyExW((HKEY)v18, v19, 8u, 0x20019u, &hKey);
  if ( v23 )
  {
    CloseHandle(EventW);
LABEL_37:
    if ( v23 <= 0 )
      goto LABEL_32;
    v23 = (unsigned __int16)v23;
    goto LABEL_31;
  }
  v23 = RegNotifyChangeKeyValue(hKey, 0, 5u, EventW, 1);
  if ( v23 )
  {
    CloseHandle(EventW);
    RegCloseKey(hKey);
    goto LABEL_37;
  }
  v24 = RegQueryValueExW(hKey, L"SymbolicLinkValue", 0, &Type, 0, &cbData);
  RegCloseKey(hKey);
  v25 = WaitForSingleObject(EventW, 0);
  CloseHandle(EventW);
  if ( !v25 )
  {
    free(v3);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
    return 2147943706LL;
  }
  if ( v24 )
  {
    if ( v24 != 2 )
    {
      if ( v24 > 0 )
        v24 = (unsigned __int16)v24 | 0x80070000;
      free(v3);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
      return (unsigned int)v24;
    }
  }
  else if ( Type == 6 )
  {
    free(v3);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
    return 2147943864LL;
  }
  if ( RegDeleteTreeW(*a1, 0) )
  {
    free(v3);
    v16 = (_QWORD *)(v2 - 24);
    v17 = _InterlockedExchangeAdd((volatile signed __int32 *)(v2 - 24 + 16), 0xFFFFFFFF) <= 1;
    goto LABEL_58;
  }
  free(v3);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
  return 0;
}

```

## disassembly

```asm
0x140011f08  mov     [rsp-38h+arg_0], rbx
0x140011f0d  push    rbp
0x140011f0e  push    rsi
0x140011f0f  push    rdi
0x140011f10  push    r12
0x140011f12  push    r13
0x140011f14  push    r14
0x140011f16  push    r15
0x140011f18  mov     rbp, rsp
0x140011f1b  sub     rsp, 50h
0x140011f1f  mov     r12, rcx
0x140011f22  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140011f29  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140011f30  mov     rax, [rax+18h]
0x140011f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011f39  lea     rsi, [rax+18h]
0x140011f3d  mov     [rbp+var_20], rsi
0x140011f41  xor     r13d, r13d
0x140011f44  mov     ebx, r13d
0x140011f47  mov     [rbp+var_10], rbx
0x140011f4b  mov     [rbp+hKey], r13
0x140011f4f  mov     [rbp+Type], r13d
0x140011f53  mov     [rbp+cbData], r13d
0x140011f57  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x140011f5c  or      r14, 0FFFFFFFFFFFFFFFFh
0x140011f60  test    eax, eax
0x140011f62  jz      loc_1400120D5
0x140011f68  lea     rcx, [rbp+var_18]
0x140011f6c  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x140011f71  nop
0x140011f72  mov     rdx, rax
0x140011f75  lea     rcx, [rbp+var_20]
0x140011f79  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140011f7e  nop
0x140011f7f  mov     rdx, [rbp+var_18]
0x140011f83  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140011f87  mov     eax, r14d
0x140011f8a  lock xadd [rdx+10h], eax
0x140011f8f  add     eax, r14d
0x140011f92  test    eax, eax
0x140011f94  jg      short loc_140011FA5
0x140011f96  mov     rcx, [rdx]
0x140011f99  mov     rax, [rcx]
0x140011f9c  mov     rax, [rax+8]
0x140011fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011fa5  mov     r8d, 7FFFFFFFh
0x140011fab  mov     edx, r8d
0x140011fae  lea     rax, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x140011fb5  cmp     [rax], r13w
0x140011fb9  jz      short loc_140011FC5
0x140011fbb  add     rax, 2
0x140011fbf  sub     rdx, 1
0x140011fc3  jnz     short loc_140011FB5
0x140011fc5  mov     rax, rdx
0x140011fc8  mov     rcx, r8
0x140011fcb  sub     rcx, rdx
0x140011fce  neg     rax
0x140011fd1  sbb     r9, r9
0x140011fd4  and     r9, rcx
0x140011fd7  mov     rsi, [rbp+var_20]
0x140011fdb  test    rdx, rdx
0x140011fde  jz      loc_1400120D1
0x140011fe4  test    rsi, rsi
0x140011fe7  jz      loc_1400120D1
0x140011fed  mov     rcx, r8
0x140011ff0  mov     rax, rsi
0x140011ff3  cmp     [rax], r13w
0x140011ff7  jz      short loc_140012003
0x140011ff9  add     rax, 2
0x140011ffd  sub     rcx, 1
0x140012001  jnz     short loc_140011FF3
0x140012003  mov     rax, rcx
0x140012006  sub     r8, rcx
0x140012009  neg     rax
0x14001200c  sbb     rdx, rdx
0x14001200f  and     rdx, r8
0x140012012  test    rcx, rcx
0x140012015  jz      loc_1400120D1
0x14001201b  lea     rdi, [r9+rdx]
0x14001201f  cmp     rdi, r9
0x140012022  jb      loc_1400120D1
0x140012028  test    rdi, rdi
0x14001202b  jnz     short loc_140012032
0x14001202d  mov     rcx, r13
0x140012030  jmp     short loc_140012044
0x140012032  xor     edx, edx
0x140012034  mov     rax, r14
0x140012037  div     rdi
0x14001203a  cmp     rax, 2
0x14001203e  jb      short loc_14001209B
0x140012040  lea     rcx, [rdi+rdi]; Size
0x140012044  call    cs:__imp_malloc
0x14001204a  mov     rbx, rax
0x14001204d  mov     [rbp+var_10], rax
0x140012051  test    rax, rax
0x140012054  jz      short loc_14001209B
0x140012056  mov     r9, rsi
0x140012059  lea     r8, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x140012060  mov     rdx, rdi; unsigned __int64
0x140012063  mov     rcx, rax; unsigned __int16 *
0x140012066  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001206b  test    eax, eax
0x14001206d  jns     short loc_14001208F
0x14001206f  mov     rcx, rbx; Block
0x140012072  call    cs:__imp_free
0x140012078  nop
0x140012079  lea     rdx, [rsi-18h]
0x14001207d  mov     eax, r14d
0x140012080  lock xadd [rdx+10h], eax
0x140012085  add     eax, r14d
0x140012088  test    eax, eax
0x14001208a  jmp     loc_1400122DF
0x14001208f  mov     rdi, 0FFFFFFFF80000002h
0x140012096  mov     r14, rbx
0x140012099  jmp     short loc_1400120E3
0x14001209b  mov     rcx, rbx; Block
0x14001209e  call    cs:__imp_free
0x1400120a4  nop
0x1400120a5  lea     rdx, [rsi-18h]
0x1400120a9  mov     eax, r14d
0x1400120ac  lock xadd [rdx+10h], eax
0x1400120b1  add     eax, r14d
0x1400120b4  test    eax, eax
0x1400120b6  jg      short loc_1400120C7
0x1400120b8  mov     rcx, [rdx]
0x1400120bb  mov     rax, [rcx]
0x1400120be  mov     rax, [rax+8]
0x1400120c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400120c7  mov     eax, 8007000Eh
0x1400120cc  jmp     loc_140012320
0x1400120d1  xor     ecx, ecx
0x1400120d3  jmp     short loc_140012072
0x1400120d5  mov     rdi, 0FFFFFFFF80000001h
0x1400120dc  lea     r14, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400120e3  xor     r9d, r9d; lpName
0x1400120e6  xor     r8d, r8d; bInitialState
0x1400120e9  xor     edx, edx; bManualReset
0x1400120eb  xor     ecx, ecx; lpEventAttributes
0x1400120ed  call    cs:__imp_CreateEventW
0x1400120f3  mov     r15, rax
0x1400120f6  test    rax, rax
0x1400120f9  jnz     short loc_140012141
0x1400120fb  call    cs:__imp_GetLastError
0x140012101  mov     edi, eax
0x140012103  test    eax, eax
0x140012105  jle     short loc_140012110
0x140012107  movzx   edi, ax
0x14001210a  or      edi, 80070000h
0x140012110  mov     rcx, rbx; Block
0x140012113  call    cs:__imp_free
0x140012119  nop
0x14001211a  lea     rdx, [rsi-18h]
0x14001211e  or      ecx, 0FFFFFFFFh
0x140012121  lock xadd [rdx+10h], ecx
0x140012126  sub     ecx, 1
0x140012129  jg      short loc_14001213A
0x14001212b  mov     rcx, [rdx]
0x14001212e  mov     r8, [rcx]
0x140012131  mov     rax, [r8+8]
0x140012135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001213a  mov     eax, edi
0x14001213c  jmp     loc_140012320
0x140012141  lea     rax, [rbp+hKey]
0x140012145  mov     [rsp+50h+phkResult], rax; phkResult
0x14001214a  mov     r9d, 20019h; samDesired
0x140012150  mov     r8d, 8; ulOptions
0x140012156  mov     rdx, r14; lpSubKey
0x140012159  mov     rcx, rdi; hKey
0x14001215c  call    cs:__imp_RegOpenKeyExW
0x140012162  mov     edi, eax
0x140012164  test    eax, eax
0x140012166  jz      short loc_14001217A
0x140012168  mov     rcx, r15; hObject
0x14001216b  call    cs:__imp_CloseHandle
0x140012171  test    edi, edi
0x140012173  jle     short loc_140012110
0x140012175  movzx   edi, di
0x140012178  jmp     short loc_14001210A
0x14001217a  mov     dword ptr [rsp+50h+phkResult], 1; fAsynchronous
0x140012182  mov     r9, r15; hEvent
0x140012185  xor     edx, edx; bWatchSubtree
0x140012187  lea     r8d, [rdx+5]; dwNotifyFilter
0x14001218b  mov     rcx, [rbp+hKey]; hKey
0x14001218f  call    cs:__imp_RegNotifyChangeKeyValue
0x140012195  mov     edi, eax
0x140012197  test    eax, eax
0x140012199  jz      short loc_1400121B0
0x14001219b  mov     rcx, r15; hObject
0x14001219e  call    cs:__imp_CloseHandle
0x1400121a4  mov     rcx, [rbp+hKey]; hKey
0x1400121a8  call    cs:__imp_RegCloseKey
0x1400121ae  jmp     short loc_140012171
0x1400121b0  lea     rax, [rbp+cbData]
0x1400121b4  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1400121b9  mov     [rsp+50h+phkResult], r13; lpData
0x1400121be  lea     r9, [rbp+Type]; lpType
0x1400121c2  xor     r8d, r8d; lpReserved
0x1400121c5  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x1400121cc  mov     rcx, [rbp+hKey]; hKey
0x1400121d0  call    cs:__imp_RegQueryValueExW
0x1400121d6  mov     r14d, eax
0x1400121d9  mov     rcx, [rbp+hKey]; hKey
0x1400121dd  call    cs:__imp_RegCloseKey
0x1400121e3  xor     edx, edx; dwMilliseconds
0x1400121e5  mov     rcx, r15; hHandle
0x1400121e8  call    cs:__imp_WaitForSingleObject
0x1400121ee  mov     edi, eax
0x1400121f0  mov     rcx, r15; hObject
0x1400121f3  call    cs:__imp_CloseHandle
0x1400121f9  test    edi, edi
0x1400121fb  jnz     short loc_140012231
0x1400121fd  mov     rcx, rbx; Block
0x140012200  call    cs:__imp_free
0x140012206  nop
0x140012207  lea     rdx, [rsi-18h]
0x14001220b  or      eax, 0FFFFFFFFh
0x14001220e  lock xadd [rdx+10h], eax
0x140012213  sub     eax, 1
0x140012216  jg      short loc_140012227
0x140012218  mov     rcx, [rdx]
0x14001221b  mov     rax, [rcx]
0x14001221e  mov     rax, [rax+8]
0x140012222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012227  mov     eax, 8007051Ah
0x14001222c  jmp     loc_140012320
0x140012231  test    r14d, r14d
0x140012234  jz      short loc_14001227E
0x140012236  cmp     r14d, 2
0x14001223a  jz      short loc_1400122B5
0x14001223c  test    r14d, r14d
0x14001223f  jle     short loc_14001224C
0x140012241  movzx   r14d, r14w
0x140012245  or      r14d, 80070000h
0x14001224c  mov     rcx, rbx; Block
0x14001224f  call    cs:__imp_free
0x140012255  nop
0x140012256  lea     rdx, [rsi-18h]
0x14001225a  or      ecx, 0FFFFFFFFh
0x14001225d  lock xadd [rdx+10h], ecx
0x140012262  sub     ecx, 1
0x140012265  jg      short loc_140012276
0x140012267  mov     rcx, [rdx]
0x14001226a  mov     r8, [rcx]
0x14001226d  mov     rax, [r8+8]
0x140012271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012276  mov     eax, r14d
0x140012279  jmp     loc_140012320
0x14001227e  cmp     [rbp+Type], 6
0x140012282  jnz     short loc_1400122B5
0x140012284  mov     rcx, rbx; Block
0x140012287  call    cs:__imp_free
0x14001228d  nop
0x14001228e  lea     rdx, [rsi-18h]
0x140012292  or      eax, 0FFFFFFFFh
0x140012295  lock xadd [rdx+10h], eax
0x14001229a  sub     eax, 1
0x14001229d  jg      short loc_1400122AE
0x14001229f  mov     rcx, [rdx]
0x1400122a2  mov     rax, [rcx]
0x1400122a5  mov     rax, [rax+8]
0x1400122a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400122ae  mov     eax, 800705B8h
0x1400122b3  jmp     short loc_140012320
0x1400122b5  xor     edx, edx; lpSubKey
0x1400122b7  mov     rcx, [r12]; hKey
0x1400122bb  call    cs:__imp_RegDeleteTreeW
0x1400122c1  nop
0x1400122c2  mov     rcx, rbx; Block
0x1400122c5  test    eax, eax
0x1400122c7  jz      short loc_1400122F7
0x1400122c9  call    cs:__imp_free
0x1400122cf  nop
0x1400122d0  lea     rdx, [rsi-18h]
0x1400122d4  or      eax, 0FFFFFFFFh
0x1400122d7  lock xadd [rdx+10h], eax
0x1400122dc  sub     eax, 1
0x1400122df  jg      short loc_1400122F0
0x1400122e1  mov     rcx, [rdx]
0x1400122e4  mov     rax, [rcx]
0x1400122e7  mov     rax, [rax+8]
0x1400122eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400122f0  mov     eax, 80004005h
0x1400122f5  jmp     short loc_140012320
0x1400122f7  call    cs:__imp_free
0x1400122fd  nop
0x1400122fe  lea     rdx, [rsi-18h]
0x140012302  or      eax, 0FFFFFFFFh
0x140012305  lock xadd [rdx+10h], eax
0x14001230a  sub     eax, 1
0x14001230d  jg      short loc_14001231E
0x14001230f  mov     rcx, [rdx]
0x140012312  mov     rax, [rcx]
0x140012315  mov     rax, [rax+8]
0x140012319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001231e  xor     eax, eax
0x140012320  mov     rbx, [rsp+50h+arg_0]
0x140012328  add     rsp, 50h
0x14001232c  pop     r15
0x14001232e  pop     r14
0x140012330  pop     r13
  ... truncated ...
```
