# SettingsCopier::DeleteATSettings(ATL::CRegKey &)

- ea: `0x18039f380`
- end: `0x18039f6ec`
- name: `?DeleteATSettings@SettingsCopier@@CAJAEAVCRegKey@ATL@@@Z`
- size: `876`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18039f0ec`

## callees

- `0x18002fb8c`
- `0x180136c44`
- `0x1803978ec`
- `0x180397ad0`
- `0x1803985b0`
- `0x180398894`
- `0x180399bec`
- `0x18039f380`
- `0x18039ff50`
- `0x1803a0104`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f48a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f4c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f545`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f653`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f690`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f6ad`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f6c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f48a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f4c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f545`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f653`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f690`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f6ad`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f6c1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18039f510`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18039f510`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18039f62f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18039f62f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039f524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039f524`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f587`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f5c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f640`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f587`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f5c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f640`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18039f60b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18039f60b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18039f5b3`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18039f5b3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18039f67c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18039f67c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039f5d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039f61e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039f5d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039f61e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18039f571`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18039f571`

## string_xrefs

- `0x18039f600`: `SymbolicLinkValue`
- `0x18039f43d`: `%s\ATConfig`
- `0x18039f4a4`: `%s\ATConfig`
- `0x18039f4fb`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`

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
    if ( (int)StringCchPrintfW((unsigned __int16 *)Block, v10, SettingsCopier::_ATSessionConfigKeyString, v4) < 0 )
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
0x18039f380  push    rbp
0x18039f382  push    rbx
0x18039f383  push    rsi
0x18039f384  push    rdi
0x18039f385  push    r12
0x18039f387  push    r14
0x18039f389  push    r15
0x18039f38b  mov     rbp, rsp
0x18039f38e  sub     rsp, 60h
0x18039f392  mov     r12, rcx
0x18039f395  lea     rcx, [rbp+arg_18]
0x18039f399  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18039f39e  nop
0x18039f39f  mov     [rbp+var_20], 0
0x18039f3a7  mov     [rbp+var_18], 0
0x18039f3af  xor     ebx, ebx
0x18039f3b1  mov     [rbp+Block], rbx
0x18039f3b5  mov     [rbp+hKey], rbx
0x18039f3b9  mov     [rbp+Type], ebx
0x18039f3bc  mov     [rbp+cbData], ebx
0x18039f3bf  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x18039f3c4  test    eax, eax
0x18039f3c6  jz      loc_18039F4F4
0x18039f3cc  lea     rcx, [rbp+var_10]
0x18039f3d0  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x18039f3d5  nop
0x18039f3d6  mov     rdx, [rax]
0x18039f3d9  lea     rcx, [rdx-18h]
0x18039f3dd  mov     rdi, [rbp+arg_18]
0x18039f3e1  lea     rbx, [rdi-18h]
0x18039f3e5  cmp     rcx, rbx
0x18039f3e8  jz      short loc_18039F423
0x18039f3ea  cmp     dword ptr [rbx+10h], 0
0x18039f3ee  jl      short loc_18039F412
0x18039f3f0  mov     rax, [rbx]
0x18039f3f3  cmp     [rcx], rax
0x18039f3f6  jnz     short loc_18039F412
0x18039f3f8  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18039f3fd  mov     rdi, rax
0x18039f400  mov     rcx, rbx; this
0x18039f403  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18039f408  add     rdi, 18h
0x18039f40c  mov     [rbp+arg_18], rdi
0x18039f410  jmp     short loc_18039F423
0x18039f412  mov     r8d, [rdx-10h]
0x18039f416  lea     rcx, [rbp+arg_18]
0x18039f41a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18039f41f  mov     rdi, [rbp+arg_18]
0x18039f423  mov     rcx, [rbp+var_10]
0x18039f427  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18039f42b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18039f430  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18039f434  mov     r11d, 7FFFFFFFh
0x18039f43a  mov     edx, r11d; unsigned __int64
0x18039f43d  lea     rcx, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x18039f444  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18039f449  test    eax, eax
0x18039f44b  js      loc_18039F4ED
0x18039f451  lea     r8, [rbp+var_18]; unsigned __int64 *
0x18039f455  mov     edx, r11d; unsigned __int64
0x18039f458  mov     rcx, rdi; unsigned __int16 *
0x18039f45b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18039f460  test    eax, eax
0x18039f462  js      loc_18039F4ED
0x18039f468  mov     rbx, [rbp+var_18]
0x18039f46c  add     rbx, [rbp+var_20]
0x18039f470  cmp     rbx, [rbp+var_20]
0x18039f474  jb      short loc_18039F4ED
0x18039f476  mov     rdx, rbx
0x18039f479  lea     rcx, [rbp+Block]
0x18039f47d  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x18039f482  test    al, al
0x18039f484  jnz     short loc_18039F4A1
0x18039f486  mov     rcx, [rbp+Block]; Block
0x18039f48a  call    cs:__imp_free
0x18039f491  nop     dword ptr [rax+rax+00h]
0x18039f496  mov     r14d, 8007000Eh
0x18039f49c  jmp     loc_18039F6D0
0x18039f4a1  mov     r9, rdi
0x18039f4a4  lea     r8, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x18039f4ab  mov     rdx, rbx; unsigned __int64
0x18039f4ae  mov     rbx, [rbp+Block]
0x18039f4b2  mov     rcx, rbx; unsigned __int16 *
0x18039f4b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18039f4ba  test    eax, eax
0x18039f4bc  jns     short loc_18039F4E1
0x18039f4be  mov     rcx, rbx; Block
0x18039f4c1  call    cs:__imp_free
0x18039f4c8  nop     dword ptr [rax+rax+00h]
0x18039f4cd  nop
0x18039f4ce  lea     rcx, [rdi-18h]; this
0x18039f4d2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18039f4d7  mov     eax, 80004005h
0x18039f4dc  jmp     loc_18039F6DC
0x18039f4e1  mov     rsi, 0FFFFFFFF80000002h
0x18039f4e8  mov     r14, rbx
0x18039f4eb  jmp     short loc_18039F506
0x18039f4ed  xor     ecx, ecx
0x18039f4ef  jmp     loc_18039F690
0x18039f4f4  mov     rsi, 0FFFFFFFF80000001h
0x18039f4fb  lea     r14, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18039f502  mov     rdi, [rbp+arg_18]
0x18039f506  xor     r9d, r9d; lpName
0x18039f509  xor     r8d, r8d; bInitialState
0x18039f50c  xor     edx, edx; bManualReset
0x18039f50e  xor     ecx, ecx; lpEventAttributes
0x18039f510  call    cs:__imp_CreateEventW
0x18039f517  nop     dword ptr [rax+rax+00h]
0x18039f51c  mov     r15, rax
0x18039f51f  test    rax, rax
0x18039f522  jnz     short loc_18039F556
0x18039f524  call    cs:__imp_GetLastError
0x18039f52b  nop     dword ptr [rax+rax+00h]
0x18039f530  mov     r14d, eax
0x18039f533  test    eax, eax
0x18039f535  jle     short loc_18039F542
0x18039f537  movzx   r14d, ax
0x18039f53b  or      r14d, 80070000h
0x18039f542  mov     rcx, rbx; Block
0x18039f545  call    cs:__imp_free
0x18039f54c  nop     dword ptr [rax+rax+00h]
0x18039f551  jmp     loc_18039F6D0
0x18039f556  lea     rax, [rbp+hKey]
0x18039f55a  mov     [rsp+60h+phkResult], rax; phkResult
0x18039f55f  mov     r9d, 20019h; samDesired
0x18039f565  mov     r8d, 8; ulOptions
0x18039f56b  mov     rdx, r14; lpSubKey
0x18039f56e  mov     rcx, rsi; hKey
0x18039f571  call    cs:__imp_RegOpenKeyExW
0x18039f578  nop     dword ptr [rax+rax+00h]
0x18039f57d  mov     r14d, eax
0x18039f580  test    eax, eax
0x18039f582  jz      short loc_18039F59E
0x18039f584  mov     rcx, r15; hObject
0x18039f587  call    cs:__imp_CloseHandle
0x18039f58e  nop     dword ptr [rax+rax+00h]
0x18039f593  test    r14d, r14d
0x18039f596  jle     short loc_18039F542
0x18039f598  movzx   r14d, r14w
0x18039f59c  jmp     short loc_18039F53B
0x18039f59e  mov     dword ptr [rsp+60h+phkResult], 1; fAsynchronous
0x18039f5a6  mov     r9, r15; hEvent
0x18039f5a9  xor     edx, edx; bWatchSubtree
0x18039f5ab  lea     r8d, [rdx+5]; dwNotifyFilter
0x18039f5af  mov     rcx, [rbp+hKey]; hKey
0x18039f5b3  call    cs:__imp_RegNotifyChangeKeyValue
0x18039f5ba  nop     dword ptr [rax+rax+00h]
0x18039f5bf  mov     r14d, eax
0x18039f5c2  test    eax, eax
0x18039f5c4  jz      short loc_18039F5E7
0x18039f5c6  mov     rcx, r15; hObject
0x18039f5c9  call    cs:__imp_CloseHandle
0x18039f5d0  nop     dword ptr [rax+rax+00h]
0x18039f5d5  mov     rcx, [rbp+hKey]; hKey
0x18039f5d9  call    cs:__imp_RegCloseKey
0x18039f5e0  nop     dword ptr [rax+rax+00h]
0x18039f5e5  jmp     short loc_18039F593
0x18039f5e7  lea     rax, [rbp+cbData]
0x18039f5eb  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18039f5f0  mov     [rsp+60h+phkResult], 0; lpData
0x18039f5f9  lea     r9, [rbp+Type]; lpType
0x18039f5fd  xor     r8d, r8d; lpReserved
0x18039f600  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x18039f607  mov     rcx, [rbp+hKey]; hKey
0x18039f60b  call    cs:__imp_RegQueryValueExW
0x18039f612  nop     dword ptr [rax+rax+00h]
0x18039f617  mov     r14d, eax
0x18039f61a  mov     rcx, [rbp+hKey]; hKey
0x18039f61e  call    cs:__imp_RegCloseKey
0x18039f625  nop     dword ptr [rax+rax+00h]
0x18039f62a  xor     edx, edx; dwMilliseconds
0x18039f62c  mov     rcx, r15; hHandle
0x18039f62f  call    cs:__imp_WaitForSingleObject
0x18039f636  nop     dword ptr [rax+rax+00h]
0x18039f63b  mov     esi, eax
0x18039f63d  mov     rcx, r15; hObject
0x18039f640  call    cs:__imp_CloseHandle
0x18039f647  nop     dword ptr [rax+rax+00h]
0x18039f64c  test    esi, esi
0x18039f64e  jnz     short loc_18039F667
0x18039f650  mov     rcx, rbx; Block
0x18039f653  call    cs:__imp_free
0x18039f65a  nop     dword ptr [rax+rax+00h]
0x18039f65f  mov     r14d, 8007051Ah
0x18039f665  jmp     short loc_18039F6D0
0x18039f667  test    r14d, r14d
0x18039f66a  jz      short loc_18039F6A4
0x18039f66c  cmp     r14d, 2
0x18039f670  jnz     loc_18039F593
0x18039f676  xor     edx, edx; lpSubKey
0x18039f678  mov     rcx, [r12]; hKey
0x18039f67c  call    cs:__imp_RegDeleteTreeW
0x18039f683  nop     dword ptr [rax+rax+00h]
0x18039f688  nop
0x18039f689  mov     rcx, rbx; Block
0x18039f68c  test    eax, eax
0x18039f68e  jz      short loc_18039F6C1
0x18039f690  call    cs:__imp_free
0x18039f697  nop     dword ptr [rax+rax+00h]
0x18039f69c  mov     r14d, 80004005h
0x18039f6a2  jmp     short loc_18039F6D0
0x18039f6a4  cmp     [rbp+Type], 6
0x18039f6a8  jnz     short loc_18039F676
0x18039f6aa  mov     rcx, rbx; Block
0x18039f6ad  call    cs:__imp_free
0x18039f6b4  nop     dword ptr [rax+rax+00h]
0x18039f6b9  mov     r14d, 800705B8h
0x18039f6bf  jmp     short loc_18039F6D0
0x18039f6c1  call    cs:__imp_free
0x18039f6c8  nop     dword ptr [rax+rax+00h]
0x18039f6cd  xor     r14d, r14d
0x18039f6d0  lea     rcx, [rdi-18h]; this
0x18039f6d4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18039f6d9  mov     eax, r14d
0x18039f6dc  add     rsp, 60h
0x18039f6e0  pop     r15
0x18039f6e2  pop     r14
0x18039f6e4  pop     r12
0x18039f6e6  pop     rdi
0x18039f6e7  pop     rsi
0x18039f6e8  pop     rbx
0x18039f6e9  pop     rbp
0x18039f6ea  retn
```
