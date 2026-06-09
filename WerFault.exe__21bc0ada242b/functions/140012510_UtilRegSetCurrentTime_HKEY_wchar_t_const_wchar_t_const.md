# UtilRegSetCurrentTime(HKEY__ *,wchar_t const *,wchar_t const *)

- ea: `0x140012510`
- end: `0x1400126d3`
- name: `?UtilRegSetCurrentTime@@YAJPEAUHKEY__@@PEB_W1@Z`
- size: `451`
- prototype: `__int64 __fastcall(HKEY hKey, const wchar_t *, const wchar_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400295b8`
- `0x14004a768`
- `0x14004d690`
- `0x140052238`
- `0x140053bbc`

## callees

- `0x140012510`
- `0x14001444c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001257d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400125ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400126b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001257d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400125ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400126b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001266b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001266b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400125ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400125ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140012639`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140012639`

## pseudocode

```c
__int64 __fastcall UtilRegSetCurrentTime(HKEY hKey, const wchar_t *a2, const wchar_t *a3)
{
  HKEY v5; // rcx
  LSTATUS v7; // ebx
  HKEY v8; // rcx
  unsigned int v9; // ebx
  CUserModeHangReport *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  HKEY *p_hKeya; // [rsp+60h] [rbp-10h]
  struct _FILETIME Data; // [rsp+88h] [rbp+18h] BYREF
  HKEY hKeya; // [rsp+98h] [rbp+28h] BYREF

  v5 = 0;
  hKeya = 0;
  SystemTimeAsFileTime = 0;
  Data = 0;
  if ( __PAIR128__((unsigned __int64)hKey, 0) == (unsigned __int64)a2 || !a3 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
      v5 = hKeya;
    }
    if ( v5 )
      RegCloseKey(v5);
    return 2147942487LL;
  }
  if ( a2 )
  {
    p_hKeya = &hKeya;
    phkResult = 0;
    v7 = RegCreateKeyExW(hKey, a2, 0, 0, 0, 0x20106u, 0, &phkResult, 0);
    if ( phkResult )
    {
      v8 = *p_hKeya;
      *p_hKeya = phkResult;
      if ( v8 )
        RegCloseKey(v8);
    }
    if ( v7 )
    {
      v9 = -2147467259;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_26;
      }
      v11 = 88;
      goto LABEL_17;
    }
    hKey = hKeya;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  Data = SystemTimeAsFileTime;
  v12 = RegSetValueExW(hKey, a3, 0, 0xBu, (const BYTE *)&Data, 8u);
  if ( !v12 )
  {
    v9 = 0;
    goto LABEL_26;
  }
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  v9 = v12;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    goto LABEL_26;
  }
  v11 = 89;
LABEL_17:
  WPP_SF_(*((_QWORD *)v10 + 2), v11, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
LABEL_26:
  if ( hKeya )
    RegCloseKey(hKeya);
  return v9;
}

```

## disassembly

```asm
0x140012510  mov     [rsp-8+arg_0], rbx
0x140012515  mov     [rsp-8+arg_10], rdi
0x14001251a  push    rbp
0x14001251b  mov     rbp, rsp
0x14001251e  sub     rsp, 70h
0x140012522  mov     rbx, rcx
0x140012525  mov     rdi, r8
0x140012528  xor     ecx, ecx
0x14001252a  mov     [rbp+hKey], rcx
0x14001252e  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rcx
0x140012532  mov     [rbp+Data], rcx
0x140012536  test    rdx, rdx
0x140012539  jnz     short loc_140012540
0x14001253b  test    rbx, rbx
0x14001253e  jz      short loc_140012545
0x140012540  test    rdi, rdi
0x140012543  jnz     short loc_14001258D
0x140012545  mov     r9, cs:WPP_GLOBAL_Control
0x14001254c  lea     rax, WPP_GLOBAL_Control
0x140012553  cmp     r9, rax
0x140012556  jz      short loc_140012578
0x140012558  test    byte ptr [r9+1Ch], 1
0x14001255d  jz      short loc_140012578
0x14001255f  mov     rcx, [r9+10h]
0x140012563  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x14001256a  mov     edx, 57h ; 'W'
0x14001256f  call    WPP_SF_
0x140012574  mov     rcx, [rbp+hKey]; hKey
0x140012578  test    rcx, rcx
0x14001257b  jz      short loc_140012583
0x14001257d  call    cs:__imp_RegCloseKey
0x140012583  mov     eax, 80070057h
0x140012588  jmp     loc_1400126C1
0x14001258d  test    rdx, rdx
0x140012590  jz      loc_140012635
0x140012596  mov     [rsp+70h+lpdwDisposition], rcx; lpdwDisposition
0x14001259b  lea     rax, [rbp+hKey]
0x14001259f  mov     [rbp+var_10], rax
0x1400125a3  xor     r9d, r9d; lpClass
0x1400125a6  lea     rax, [rbp+var_18]
0x1400125aa  mov     [rbp+var_18], rcx
0x1400125ae  mov     [rsp+70h+phkResult], rax; phkResult
0x1400125b3  xor     r8d, r8d; Reserved
0x1400125b6  mov     [rsp+70h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x1400125bb  mov     [rsp+70h+samDesired], 20106h; samDesired
0x1400125c3  mov     [rsp+70h+dwOptions], ecx; dwOptions
0x1400125c7  mov     rcx, rbx; hKey
0x1400125ca  call    cs:__imp_RegCreateKeyExW
0x1400125d0  mov     r8, [rbp+var_18]
0x1400125d4  mov     ebx, eax
0x1400125d6  test    r8, r8
0x1400125d9  jz      short loc_1400125F0
0x1400125db  mov     rdx, [rbp+var_10]
0x1400125df  mov     rcx, [rdx]; hKey
0x1400125e2  mov     [rdx], r8
0x1400125e5  test    rcx, rcx
0x1400125e8  jz      short loc_1400125F0
0x1400125ea  call    cs:__imp_RegCloseKey
0x1400125f0  test    ebx, ebx
0x1400125f2  jz      short loc_140012631
0x1400125f4  mov     ebx, 80004005h
0x1400125f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140012600  lea     rax, WPP_GLOBAL_Control
0x140012607  cmp     rcx, rax
0x14001260a  jz      loc_1400126B0
0x140012610  test    byte ptr [rcx+1Ch], 1
0x140012614  jz      loc_1400126B0
0x14001261a  mov     edx, 58h ; 'X'
0x14001261f  mov     rcx, [rcx+10h]
0x140012623  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x14001262a  call    WPP_SF_
0x14001262f  jmp     short loc_1400126B0
0x140012631  mov     rbx, [rbp+hKey]
0x140012635  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140012639  call    cs:__imp_GetSystemTimeAsFileTime
0x14001263f  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x140012642  mov     r9d, 0Bh; dwType
0x140012648  mov     dword ptr [rbp+Data+4], eax
0x14001264b  xor     r8d, r8d; Reserved
0x14001264e  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140012651  mov     rdx, rdi; lpValueName
0x140012654  mov     dword ptr [rbp+Data], eax
0x140012657  mov     rcx, rbx; hKey
0x14001265a  lea     rax, [rbp+Data]
0x14001265e  mov     [rsp+70h+samDesired], 8; cbData
0x140012666  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x14001266b  call    cs:__imp_RegSetValueExW
0x140012671  test    eax, eax
0x140012673  jz      short loc_1400126AE
0x140012675  jle     short loc_14001267F
0x140012677  movzx   eax, ax
0x14001267a  or      eax, 80070000h
0x14001267f  mov     ebx, 80004005h
0x140012684  test    eax, eax
0x140012686  cmovns  eax, ebx
0x140012689  mov     ebx, eax
0x14001268b  mov     rcx, cs:WPP_GLOBAL_Control
0x140012692  lea     rax, WPP_GLOBAL_Control
0x140012699  cmp     rcx, rax
0x14001269c  jz      short loc_1400126B0
0x14001269e  test    byte ptr [rcx+1Ch], 1
0x1400126a2  jz      short loc_1400126B0
0x1400126a4  mov     edx, 59h ; 'Y'
0x1400126a9  jmp     loc_14001261F
0x1400126ae  xor     ebx, ebx
0x1400126b0  mov     rcx, [rbp+hKey]; hKey
0x1400126b4  test    rcx, rcx
0x1400126b7  jz      short loc_1400126BF
0x1400126b9  call    cs:__imp_RegCloseKey
0x1400126bf  mov     eax, ebx
0x1400126c1  lea     r11, [rsp+70h+var_s0]
0x1400126c6  mov     rbx, [r11+10h]
0x1400126ca  mov     rdi, [r11+20h]
0x1400126ce  mov     rsp, r11
0x1400126d1  pop     rbp
0x1400126d2  retn
```
