# SettingsCopier::DeleteATSettings(ATL::CRegKey &)

- ea: `0x180028b64`
- end: `0x180028e59`
- name: `?DeleteATSettings@SettingsCopier@@CAJAEAVCRegKey@ATL@@@Z`
- size: `757`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800288dc`

## callees

- `0x1800043d4`
- `0x180005534`
- `0x180015780`
- `0x18001855c`
- `0x18001a6c0`
- `0x18001e984`
- `0x180021704`
- `0x180028b64`
- `0x1800295f4`
- `0x1800296b8`

## import_xrefs

- `msvcrt!free` at `0x180028c6a`
- `msvcrt!free` at `0x180028c9b`
- `msvcrt!free` at `0x180028d0d`
- `msvcrt!free` at `0x180028ddf`
- `msvcrt!free` at `0x180028e10`
- `msvcrt!free` at `0x180028e27`
- `msvcrt!free` at `0x180028e35`
- `msvcrt!free` at `0x180028c6a`
- `msvcrt!free` at `0x180028c9b`
- `msvcrt!free` at `0x180028d0d`
- `msvcrt!free` at `0x180028ddf`
- `msvcrt!free` at `0x180028e10`
- `msvcrt!free` at `0x180028e27`
- `msvcrt!free` at `0x180028e35`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028dc7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028dc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028cf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028cf2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028d43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028d79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028dd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028d43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028d79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028dd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028d83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028dbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028d83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028dbc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028daf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028daf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028d33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028d33`
- `KERNEL32!CreateEventW` at `0x180028ce4`
- `KERNEL32!CreateEventW` at `0x180028ce4`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x180028d69`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x180028d69`
- `ADVAPI32!RegDeleteTreeW` at `0x180028e02`
- `ADVAPI32!RegDeleteTreeW` at `0x180028e02`

## string_xrefs

- `0x180028da4`: `SymbolicLinkValue`
- `0x180028c21`: `%s\ATConfig`
- `0x180028c7e`: `%s\ATConfig`
- `0x180028ccf`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`

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
0x180028b64  push    rbp
0x180028b66  push    rbx
0x180028b67  push    rsi
0x180028b68  push    rdi
0x180028b69  push    r12
0x180028b6b  push    r14
0x180028b6d  push    r15
0x180028b6f  mov     rbp, rsp
0x180028b72  sub     rsp, 60h
0x180028b76  mov     r12, rcx
0x180028b79  lea     rcx, [rbp+arg_18]
0x180028b7d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180028b82  nop
0x180028b83  mov     [rbp+var_20], 0
0x180028b8b  mov     [rbp+var_18], 0
0x180028b93  xor     ebx, ebx
0x180028b95  mov     [rbp+Block], rbx
0x180028b99  mov     [rbp+hKey], rbx
0x180028b9d  mov     [rbp+Type], ebx
0x180028ba0  mov     [rbp+cbData], ebx
0x180028ba3  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x180028ba8  test    eax, eax
0x180028baa  jz      loc_180028CC8
0x180028bb0  lea     rcx, [rbp+var_10]
0x180028bb4  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x180028bb9  nop
0x180028bba  mov     rdx, [rax]
0x180028bbd  lea     rcx, [rdx-18h]
0x180028bc1  mov     rdi, [rbp+arg_18]
0x180028bc5  lea     rbx, [rdi-18h]
0x180028bc9  cmp     rcx, rbx
0x180028bcc  jz      short loc_180028C07
0x180028bce  cmp     dword ptr [rbx+10h], 0
0x180028bd2  jl      short loc_180028BF6
0x180028bd4  mov     rax, [rbx]
0x180028bd7  cmp     [rcx], rax
0x180028bda  jnz     short loc_180028BF6
0x180028bdc  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180028be1  mov     rdi, rax
0x180028be4  mov     rcx, rbx; this
0x180028be7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180028bec  add     rdi, 18h
0x180028bf0  mov     [rbp+arg_18], rdi
0x180028bf4  jmp     short loc_180028C07
0x180028bf6  mov     r8d, [rdx-10h]
0x180028bfa  lea     rcx, [rbp+arg_18]
0x180028bfe  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180028c03  mov     rdi, [rbp+arg_18]
0x180028c07  mov     rcx, [rbp+var_10]
0x180028c0b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180028c0f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180028c14  lea     r8, [rbp+var_20]; unsigned __int64 *
0x180028c18  mov     r11d, 7FFFFFFFh
0x180028c1e  mov     edx, r11d; unsigned __int64
0x180028c21  lea     rcx, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x180028c28  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180028c2d  test    eax, eax
0x180028c2f  js      loc_180028CC1
0x180028c35  lea     r8, [rbp+var_18]; unsigned __int64 *
0x180028c39  mov     edx, r11d; unsigned __int64
0x180028c3c  mov     rcx, rdi; unsigned __int16 *
0x180028c3f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180028c44  test    eax, eax
0x180028c46  js      short loc_180028CC1
0x180028c48  mov     rbx, [rbp+var_18]
0x180028c4c  add     rbx, [rbp+var_20]
0x180028c50  cmp     rbx, [rbp+var_20]
0x180028c54  jb      short loc_180028CC1
0x180028c56  mov     rdx, rbx
0x180028c59  lea     rcx, [rbp+Block]
0x180028c5d  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x180028c62  test    al, al
0x180028c64  jnz     short loc_180028C7B
0x180028c66  mov     rcx, [rbp+Block]; Block
0x180028c6a  call    cs:__imp_free
0x180028c70  mov     r14d, 8007000Eh
0x180028c76  jmp     loc_180028E3E
0x180028c7b  mov     r9, rdi
0x180028c7e  lea     r8, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x180028c85  mov     rdx, rbx; unsigned __int64
0x180028c88  mov     rbx, [rbp+Block]
0x180028c8c  mov     rcx, rbx; unsigned __int16 *
0x180028c8f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028c94  test    eax, eax
0x180028c96  jns     short loc_180028CB5
0x180028c98  mov     rcx, rbx; Block
0x180028c9b  call    cs:__imp_free
0x180028ca1  nop
0x180028ca2  lea     rcx, [rdi-18h]; this
0x180028ca6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180028cab  mov     eax, 80004005h
0x180028cb0  jmp     loc_180028E4A
0x180028cb5  mov     rsi, 0FFFFFFFF80000002h
0x180028cbc  mov     r14, rbx
0x180028cbf  jmp     short loc_180028CDA
0x180028cc1  xor     ecx, ecx
0x180028cc3  jmp     loc_180028E10
0x180028cc8  mov     rsi, 0FFFFFFFF80000001h
0x180028ccf  lea     r14, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180028cd6  mov     rdi, [rbp+arg_18]
0x180028cda  xor     r9d, r9d; lpName
0x180028cdd  xor     r8d, r8d; bInitialState
0x180028ce0  xor     edx, edx; bManualReset
0x180028ce2  xor     ecx, ecx; lpEventAttributes
0x180028ce4  call    cs:__imp_CreateEventW
0x180028cea  mov     r15, rax
0x180028ced  test    rax, rax
0x180028cf0  jnz     short loc_180028D18
0x180028cf2  call    cs:__imp_GetLastError
0x180028cf8  mov     r14d, eax
0x180028cfb  test    eax, eax
0x180028cfd  jle     short loc_180028D0A
0x180028cff  movzx   r14d, ax
0x180028d03  or      r14d, 80070000h
0x180028d0a  mov     rcx, rbx; Block
0x180028d0d  call    cs:__imp_free
0x180028d13  jmp     loc_180028E3E
0x180028d18  lea     rax, [rbp+hKey]
0x180028d1c  mov     [rsp+60h+phkResult], rax; phkResult
0x180028d21  mov     r9d, 20019h; samDesired
0x180028d27  mov     r8d, 8; ulOptions
0x180028d2d  mov     rdx, r14; lpSubKey
0x180028d30  mov     rcx, rsi; hKey
0x180028d33  call    cs:__imp_RegOpenKeyExW
0x180028d39  mov     r14d, eax
0x180028d3c  test    eax, eax
0x180028d3e  jz      short loc_180028D54
0x180028d40  mov     rcx, r15; hObject
0x180028d43  call    cs:__imp_CloseHandle
0x180028d49  test    r14d, r14d
0x180028d4c  jle     short loc_180028D0A
0x180028d4e  movzx   r14d, r14w
0x180028d52  jmp     short loc_180028D03
0x180028d54  mov     dword ptr [rsp+60h+phkResult], 1; fAsynchronous
0x180028d5c  mov     r9, r15; hEvent
0x180028d5f  xor     edx, edx; bWatchSubtree
0x180028d61  lea     r8d, [rdx+5]; dwNotifyFilter
0x180028d65  mov     rcx, [rbp+hKey]; hKey
0x180028d69  call    cs:__imp_RegNotifyChangeKeyValue
0x180028d6f  mov     r14d, eax
0x180028d72  test    eax, eax
0x180028d74  jz      short loc_180028D8B
0x180028d76  mov     rcx, r15; hObject
0x180028d79  call    cs:__imp_CloseHandle
0x180028d7f  mov     rcx, [rbp+hKey]; hKey
0x180028d83  call    cs:__imp_RegCloseKey
0x180028d89  jmp     short loc_180028D49
0x180028d8b  lea     rax, [rbp+cbData]
0x180028d8f  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180028d94  mov     [rsp+60h+phkResult], 0; lpData
0x180028d9d  lea     r9, [rbp+Type]; lpType
0x180028da1  xor     r8d, r8d; lpReserved
0x180028da4  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x180028dab  mov     rcx, [rbp+hKey]; hKey
0x180028daf  call    cs:__imp_RegQueryValueExW
0x180028db5  mov     r14d, eax
0x180028db8  mov     rcx, [rbp+hKey]; hKey
0x180028dbc  call    cs:__imp_RegCloseKey
0x180028dc2  xor     edx, edx; dwMilliseconds
0x180028dc4  mov     rcx, r15; hHandle
0x180028dc7  call    cs:__imp_WaitForSingleObject
0x180028dcd  mov     esi, eax
0x180028dcf  mov     rcx, r15; hObject
0x180028dd2  call    cs:__imp_CloseHandle
0x180028dd8  test    esi, esi
0x180028dda  jnz     short loc_180028DED
0x180028ddc  mov     rcx, rbx; Block
0x180028ddf  call    cs:__imp_free
0x180028de5  mov     r14d, 8007051Ah
0x180028deb  jmp     short loc_180028E3E
0x180028ded  test    r14d, r14d
0x180028df0  jz      short loc_180028E1E
0x180028df2  cmp     r14d, 2
0x180028df6  jnz     loc_180028D49
0x180028dfc  xor     edx, edx; lpSubKey
0x180028dfe  mov     rcx, [r12]; hKey
0x180028e02  call    cs:__imp_RegDeleteTreeW
0x180028e08  nop
0x180028e09  mov     rcx, rbx; Block
0x180028e0c  test    eax, eax
0x180028e0e  jz      short loc_180028E35
0x180028e10  call    cs:__imp_free
0x180028e16  mov     r14d, 80004005h
0x180028e1c  jmp     short loc_180028E3E
0x180028e1e  cmp     [rbp+Type], 6
0x180028e22  jnz     short loc_180028DFC
0x180028e24  mov     rcx, rbx; Block
0x180028e27  call    cs:__imp_free
0x180028e2d  mov     r14d, 800705B8h
0x180028e33  jmp     short loc_180028E3E
0x180028e35  call    cs:__imp_free
0x180028e3b  xor     r14d, r14d
0x180028e3e  lea     rcx, [rdi-18h]; this
0x180028e42  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180028e47  mov     eax, r14d
0x180028e4a  add     rsp, 60h
0x180028e4e  pop     r15
0x180028e50  pop     r14
0x180028e52  pop     r12
0x180028e54  pop     rdi
0x180028e55  pop     rsi
0x180028e56  pop     rbx
0x180028e57  pop     rbp
0x180028e58  retn
```
