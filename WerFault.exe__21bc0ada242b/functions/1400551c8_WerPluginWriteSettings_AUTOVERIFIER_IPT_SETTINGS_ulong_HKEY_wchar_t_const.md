# WerPluginWriteSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,HKEY__ *,wchar_t const *)

- ea: `0x1400551c8`
- end: `0x14005545b`
- name: `?WerPluginWriteSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUHKEY__@@PEB_W@Z`
- size: `659`
- prototype: `__int64 __fastcall(const BYTE *, unsigned int, HKEY, const wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140049364`
- `0x14004cbac`

## callees

- `0x140005468`
- `0x14001444c`
- `0x140014474`
- `0x1400551c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400553af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140055447`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400553af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140055447`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140055303`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005538c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140055303`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005538c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005523d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005523d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140055254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140055254`

## pseudocode

```c
__int64 __fastcall WerPluginWriteSettings(const BYTE *a1, unsigned int a2, HKEY a3, const wchar_t *a4)
{
  HKEY v5; // rdi
  HKEY *phkResult; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx
  unsigned int v11; // esi
  __int64 v12; // rcx
  CUserModeHangReport *v13; // rcx
  __int64 v14; // rdx
  const BYTE *v15; // rax
  const BYTE *v16; // r8
  unsigned __int64 v17; // rax
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  hKey = 0;
  v5 = a3;
  if ( !a1 || !a3 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids);
    }
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942487LL;
  }
  if ( a4 )
  {
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    if ( RegCreateKeyExW(v5, a4, 0, 0, 0, 2u, 0, phkResult, 0) || (v5 = hKey) == 0 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids, v10);
      }
      goto LABEL_25;
    }
  }
  v11 = 0;
  if ( !a2 )
  {
LABEL_24:
    v10 = 0;
    goto LABEL_25;
  }
  while ( 1 )
  {
    v12 = 568LL * v11;
    if ( !*(_DWORD *)&a1[v12 + 564] )
      goto LABEL_23;
    if ( *(_DWORD *)&a1[v12] == 1 )
      break;
    if ( *(_DWORD *)&a1[v12] == 4 && RegSetValueExW(v5, (LPCWSTR)&a1[v12 + 4], 0, 4u, &a1[v12 + 560], 4u) )
    {
      v10 = -2147467259;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 21;
LABEL_19:
        WPP_SF_(*((_QWORD *)v13 + 2), v14, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids);
        goto LABEL_25;
      }
      goto LABEL_25;
    }
LABEL_23:
    if ( ++v11 >= a2 )
      goto LABEL_24;
  }
  v15 = *(const BYTE **)&a1[v12 + 536];
  v16 = *(const BYTE **)&a1[v12 + 528];
  if ( v16 == v15 )
    goto LABEL_23;
  v17 = (v15 - v16) >> 1;
  if ( v17 >= 0x7FFFFFFF )
  {
    v10 = -2147024362;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 22;
      goto LABEL_19;
    }
    goto LABEL_25;
  }
  if ( !RegSetValueExW(v5, (LPCWSTR)&a1[v12 + 4], 0, 1u, v16, 2 * v17 + 2) )
    goto LABEL_23;
  v10 = -2147467259;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v14 = 23;
    goto LABEL_19;
  }
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x1400551c8  mov     rax, rsp
0x1400551cb  push    rbx
0x1400551cc  push    rbp
0x1400551cd  push    rsi
0x1400551ce  push    rdi
0x1400551cf  sub     rsp, 58h
0x1400551d3  mov     qword ptr [rax+8], 0
0x1400551db  mov     rsi, r9
0x1400551de  mov     rdi, r8
0x1400551e1  mov     ebp, edx
0x1400551e3  mov     rbx, rcx
0x1400551e6  test    rcx, rcx
0x1400551e9  jz      loc_14005540C
0x1400551ef  test    r8, r8
0x1400551f2  jz      loc_14005540C
0x1400551f8  test    r9, r9
0x1400551fb  jz      loc_1400552A7
0x140055201  lea     rcx, [rax+8]
0x140055205  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14005520a  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x140055213  xor     r9d, r9d; lpClass
0x140055216  mov     [rsp+78h+phkResult], rax; phkResult
0x14005521b  xor     r8d, r8d; Reserved
0x14005521e  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140055227  mov     rdx, rsi; lpSubKey
0x14005522a  mov     [rsp+78h+samDesired], 2; samDesired
0x140055232  mov     rcx, rdi; hKey
0x140055235  mov     [rsp+78h+dwOptions], 0; dwOptions
0x14005523d  call    cs:__imp_RegCreateKeyExW
0x140055243  test    eax, eax
0x140055245  jnz     short loc_140055254
0x140055247  mov     rdi, [rsp+78h+hKey]
0x14005524f  test    rdi, rdi
0x140055252  jnz     short loc_1400552A7
0x140055254  call    cs:__imp_GetLastError
0x14005525a  mov     ebx, eax
0x14005525c  test    eax, eax
0x14005525e  jle     short loc_140055269
0x140055260  movzx   ebx, ax
0x140055263  or      ebx, 80070000h
0x140055269  mov     rcx, cs:WPP_GLOBAL_Control
0x140055270  lea     rax, WPP_GLOBAL_Control
0x140055277  cmp     rcx, rax
0x14005527a  jz      loc_1400553A2
0x140055280  test    byte ptr [rcx+1Ch], 1
0x140055284  jz      loc_1400553A2
0x14005528a  mov     rcx, [rcx+10h]
0x14005528e  lea     r8, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids
0x140055295  mov     edx, 14h
0x14005529a  mov     r9d, ebx
0x14005529d  call    WPP_SF_d
0x1400552a2  jmp     loc_1400553A2
0x1400552a7  xor     esi, esi
0x1400552a9  test    ebp, ebp
0x1400552ab  jz      loc_1400553A0
0x1400552b1  mov     eax, esi
0x1400552b3  imul    rcx, rax, 238h
0x1400552ba  cmp     dword ptr [rcx+rbx+234h], 0
0x1400552c2  jz      loc_140055396
0x1400552c8  mov     edx, [rcx+rbx]
0x1400552cb  sub     edx, 1
0x1400552ce  jz      short loc_140055346
0x1400552d0  cmp     edx, 3
0x1400552d3  jnz     loc_140055396
0x1400552d9  lea     rax, [rbx+230h]
0x1400552e0  mov     [rsp+78h+samDesired], 4; cbData
0x1400552e8  add     rax, rcx
0x1400552eb  lea     rdx, [rbx+4]
0x1400552ef  add     rdx, rcx; lpValueName
0x1400552f2  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x1400552f7  mov     rcx, rdi; hKey
0x1400552fa  mov     r9d, 4; dwType
0x140055300  xor     r8d, r8d; Reserved
0x140055303  call    cs:__imp_RegSetValueExW
0x140055309  test    eax, eax
0x14005530b  jz      loc_140055396
0x140055311  mov     ebx, 80004005h
0x140055316  mov     rcx, cs:WPP_GLOBAL_Control
0x14005531d  lea     rax, WPP_GLOBAL_Control
0x140055324  cmp     rcx, rax
0x140055327  jz      short loc_1400553A2
0x140055329  test    byte ptr [rcx+1Ch], 1
0x14005532d  jz      short loc_1400553A2
0x14005532f  mov     edx, 15h
0x140055334  mov     rcx, [rcx+10h]
0x140055338  lea     r8, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids
0x14005533f  call    WPP_SF_
0x140055344  jmp     short loc_1400553A2
0x140055346  mov     rax, [rcx+rbx+218h]
0x14005534e  mov     r8, [rcx+rbx+210h]
0x140055356  cmp     r8, rax
0x140055359  jz      short loc_140055396
0x14005535b  sub     rax, r8
0x14005535e  sar     rax, 1
0x140055361  cmp     rax, 7FFFFFFFh
0x140055367  jnb     short loc_1400553E4
0x140055369  lea     eax, ds:2[rax*2]
0x140055370  mov     r9d, 1; dwType
0x140055376  mov     [rsp+78h+samDesired], eax; cbData
0x14005537a  lea     rdx, [rbx+4]
0x14005537e  mov     qword ptr [rsp+78h+dwOptions], r8; lpData
0x140055383  add     rdx, rcx; lpValueName
0x140055386  xor     r8d, r8d; Reserved
0x140055389  mov     rcx, rdi; hKey
0x14005538c  call    cs:__imp_RegSetValueExW
0x140055392  test    eax, eax
0x140055394  jnz     short loc_1400553BC
0x140055396  inc     esi
0x140055398  cmp     esi, ebp
0x14005539a  jb      loc_1400552B1
0x1400553a0  xor     ebx, ebx
0x1400553a2  mov     rcx, [rsp+78h+hKey]; hKey
0x1400553aa  test    rcx, rcx
0x1400553ad  jz      short loc_1400553B5
0x1400553af  call    cs:__imp_RegCloseKey
0x1400553b5  mov     eax, ebx
0x1400553b7  jmp     loc_140055452
0x1400553bc  mov     ebx, 80004005h
0x1400553c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400553c8  lea     rax, WPP_GLOBAL_Control
0x1400553cf  cmp     rcx, rax
0x1400553d2  jz      short loc_1400553A2
0x1400553d4  test    byte ptr [rcx+1Ch], 1
0x1400553d8  jz      short loc_1400553A2
0x1400553da  mov     edx, 17h
0x1400553df  jmp     loc_140055334
0x1400553e4  mov     ebx, 80070216h
0x1400553e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400553f0  lea     rax, WPP_GLOBAL_Control
0x1400553f7  cmp     rcx, rax
0x1400553fa  jz      short loc_1400553A2
0x1400553fc  test    byte ptr [rcx+1Ch], 1
0x140055400  jz      short loc_1400553A2
0x140055402  mov     edx, 16h
0x140055407  jmp     loc_140055334
0x14005540c  mov     rcx, cs:WPP_GLOBAL_Control
0x140055413  lea     rax, WPP_GLOBAL_Control
0x14005541a  cmp     rcx, rax
0x14005541d  jz      short loc_14005543A
0x14005541f  test    byte ptr [rcx+1Ch], 1
0x140055423  jz      short loc_14005543A
0x140055425  mov     rcx, [rcx+10h]
0x140055429  lea     r8, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids
0x140055430  mov     edx, 13h
0x140055435  call    WPP_SF_
0x14005543a  mov     rcx, [rsp+78h+hKey]; hKey
0x140055442  test    rcx, rcx
0x140055445  jz      short loc_14005544D
0x140055447  call    cs:__imp_RegCloseKey
0x14005544d  mov     eax, 80070057h
0x140055452  add     rsp, 58h
0x140055456  pop     rdi
0x140055457  pop     rsi
0x140055458  pop     rbp
0x140055459  pop     rbx
0x14005545a  retn
```
