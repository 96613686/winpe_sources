# SuspCountRegKeyPathStartupApps(_SUS_COUNTS *,HKEY__ *,ushort const *,ushort const *,StartupScanFlags)

- ea: `0x180003164`
- end: `0x180003472`
- name: `?SuspCountRegKeyPathStartupApps@@YAJPEAU_SUS_COUNTS@@PEAUHKEY__@@PEBG2W4StartupScanFlags@@@Z`
- size: `782`
- prototype: `__int64 __fastcall(_DWORD *, HKEY, wchar_t *, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180003610`

## callees

- `0x180001bc0`
- `0x180003164`
- `0x1800039f8`
- `0x180003cfc`
- `0x180003dec`
- `0x180004130`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800032ec`
- `msvcrt!wcsstr` at `0x1800032ec`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180003284`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800033ed`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180003284`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800033ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800031dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800031dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003410`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003410`

## pseudocode

```c
__int64 __fastcall SuspCountRegKeyPathStartupApps(_DWORD *a1, HKEY a2, wchar_t *a3, __int64 a4, char a5)
{
  int v7; // ebx
  DWORD v8; // r12d
  int v9; // r15d
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  BOOL v13; // ebx
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h]
  wchar_t *Str; // [rsp+60h] [rbp-A0h]
  WCHAR ValueName[264]; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[528]; // [rsp+280h] [rbp+180h] BYREF

  v20 = a4;
  Str = a3;
  hKey = 0;
  cchValueName = 0;
  cbData = 0;
  Type = 0;
  v7 = RegOpenKeyExW(a2, a3, 0, 0x20019u, &hKey);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_91e8665fb8f03560ae482285a745ac49_Traceguids, 16389);
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_29;
  }
  cbData = 520;
  cchValueName = 260;
  v8 = 0;
  v9 = 0;
  v15 = 0;
  v7 = RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, &Type, Data, &cbData);
  if ( v7 == 259 )
  {
LABEL_28:
    a1[1] += v9;
    v7 = 0;
    goto LABEL_29;
  }
  while ( !v7 )
  {
    if ( Type - 1 <= 1 )
    {
      v12 = Str;
      ++a1[2];
      v13 = wcsstr(v12, L"Wow6432Node") != 0;
      if ( (int)SuspUtilsCheckFlags(&v15, ValueName, a2, v20, 0, v13) < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13);
      }
      if ( (v15 & 4) != 0 )
        ++*a1;
      if ( (v15 & 2) != 0 )
        goto LABEL_27;
      if ( (a5 & 1) == 0 || (int)SuspUtilsMarkAsOEM(ValueName, a2, v20, 0, v13) >= 0 )
      {
        ++v9;
        goto LABEL_27;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_27;
      v11 = 14;
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_27;
      v11 = 12;
    }
    WPP_SF_(v10[2], v11);
LABEL_27:
    v15 = 0;
    cbData = 520;
    ++v8;
    cchValueName = 260;
    v7 = RegEnumValueW(hKey, v8, ValueName, &cchValueName, 0, &Type, Data, &cbData);
    if ( v7 == 259 )
      goto LABEL_28;
  }
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_91e8665fb8f03560ae482285a745ac49_Traceguids,
      (unsigned __int16)v7);
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003164  push    rbp
0x180003166  push    rbx
0x180003167  push    rsi
0x180003168  push    r12
0x18000316a  push    r13
0x18000316c  push    r14
0x18000316e  push    r15
0x180003170  lea     rbp, [rsp-3A0h]
0x180003178  sub     rsp, 4A0h
0x18000317f  mov     rax, cs:__security_cookie
0x180003186  xor     rax, rsp
0x180003189  mov     [rbp+3D0h+var_40], rax
0x180003190  mov     rax, r8
0x180003193  mov     [rsp+4D0h+var_478], r9
0x180003198  mov     r14, rcx
0x18000319b  mov     [rsp+4D0h+Str], rax
0x1800031a0  mov     r13, rdx
0x1800031a3  mov     [rsp+4D0h+hKey], 0
0x1800031ac  lea     rcx, [rsp+4D0h+hKey]
0x1800031b1  mov     [rsp+4D0h+cchValueName], 0
0x1800031b9  mov     [rsp+4D0h+phkResult], rcx; phkResult
0x1800031be  mov     r9d, 20019h; samDesired
0x1800031c4  mov     rcx, r13; hKey
0x1800031c7  mov     [rsp+4D0h+cbData], 0
0x1800031cf  xor     r8d, r8d; ulOptions
0x1800031d2  mov     [rsp+4D0h+Type], 0
0x1800031da  mov     rdx, rax; lpSubKey
0x1800031dd  call    cs:__imp_RegOpenKeyExW
0x1800031e3  mov     ebx, eax
0x1800031e5  test    eax, eax
0x1800031e7  jz      short loc_180003233
0x1800031e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031f0  lea     rsi, WPP_GLOBAL_Control
0x1800031f7  cmp     rcx, rsi
0x1800031fa  jz      short loc_18000321D
0x1800031fc  test    byte ptr [rcx+1Ch], 1
0x180003200  jz      short loc_18000321D
0x180003202  mov     rcx, [rcx+10h]
0x180003206  lea     r8, WPP_91e8665fb8f03560ae482285a745ac49_Traceguids
0x18000320d  mov     edx, 0Ah
0x180003212  mov     r9d, 4005h
0x180003218  call    WPP_SF_D
0x18000321d  test    ebx, ebx
0x18000321f  jle     loc_180003406
0x180003225  movzx   ebx, bx
0x180003228  or      ebx, 80070000h
0x18000322e  jmp     loc_180003406
0x180003233  mov     rcx, [rsp+4D0h+hKey]; hKey
0x180003238  lea     rax, [rsp+4D0h+cbData]
0x18000323d  mov     [rsp+4D0h+lpcbData], rax; lpcbData
0x180003242  lea     r9, [rsp+4D0h+cchValueName]; lpcchValueName
0x180003247  lea     rax, [rbp+3D0h+Data]
0x18000324e  mov     [rsp+4D0h+cbData], 208h
0x180003256  mov     [rsp+4D0h+lpData], rax; lpData
0x18000325b  lea     r8, [rsp+4D0h+ValueName]; lpValueName
0x180003260  lea     rax, [rsp+4D0h+Type]
0x180003265  mov     [rsp+4D0h+cchValueName], 104h
0x18000326d  xor     r12d, r12d
0x180003270  mov     [rsp+4D0h+lpType], rax; lpType
0x180003275  xor     edx, edx; dwIndex
0x180003277  mov     [rsp+4D0h+phkResult], r12; lpReserved
0x18000327c  xor     r15d, r15d
0x18000327f  mov     [rsp+4D0h+var_490], r12d
0x180003284  call    cs:__imp_RegEnumValueW
0x18000328a  mov     ebx, eax
0x18000328c  cmp     eax, 103h
0x180003291  jz      loc_180003400
0x180003297  lea     rsi, WPP_GLOBAL_Control
0x18000329e  test    ebx, ebx
0x1800032a0  jnz     loc_18000343A
0x1800032a6  mov     eax, [rsp+4D0h+Type]
0x1800032aa  dec     eax
0x1800032ac  cmp     eax, 1
0x1800032af  jbe     short loc_1800032DC
0x1800032b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032b8  cmp     rcx, rsi
0x1800032bb  jz      loc_180003397
0x1800032c1  test    byte ptr [rcx+1Ch], 1
0x1800032c5  jz      loc_180003397
0x1800032cb  lea     edx, [rbx+0Ch]
0x1800032ce  mov     rcx, [rcx+10h]
0x1800032d2  call    WPP_SF_
0x1800032d7  jmp     loc_180003397
0x1800032dc  mov     rcx, [rsp+4D0h+Str]; Str
0x1800032e1  lea     rdx, aWow6432node; "Wow6432Node"
0x1800032e8  inc     dword ptr [r14+8]
0x1800032ec  call    cs:__imp_wcsstr
0x1800032f2  mov     r9, [rsp+4D0h+var_478]
0x1800032f7  lea     rdx, [rsp+4D0h+ValueName]
0x1800032fc  xor     ebx, ebx
0x1800032fe  lea     rcx, [rsp+4D0h+var_490]
0x180003303  test    rax, rax
0x180003306  mov     r8, r13
0x180003309  setnz   bl
0x18000330c  mov     dword ptr [rsp+4D0h+lpType], ebx
0x180003310  mov     dword ptr [rsp+4D0h+phkResult], 0
0x180003318  call    ?SuspUtilsCheckFlags@@YAJPEAKPEAGPEAUHKEY__@@PEBGW4_SUS_STARTUP_TYPE@@H@Z; SuspUtilsCheckFlags(ulong *,ushort *,HKEY__ *,ushort const *,_SUS_STARTUP_TYPE,int)
0x18000331d  test    eax, eax
0x18000331f  jns     short loc_180003341
0x180003321  mov     rcx, cs:WPP_GLOBAL_Control
0x180003328  cmp     rcx, rsi
0x18000332b  jz      short loc_180003341
0x18000332d  test    byte ptr [rcx+1Ch], 1
0x180003331  jz      short loc_180003341
0x180003333  mov     rcx, [rcx+10h]
0x180003337  mov     edx, 0Dh
0x18000333c  call    WPP_SF_
0x180003341  test    byte ptr [rsp+4D0h+var_490], 4
0x180003346  jz      short loc_18000334B
0x180003348  inc     dword ptr [r14]
0x18000334b  test    byte ptr [rsp+4D0h+var_490], 2
0x180003350  jnz     short loc_180003397
0x180003352  test    [rbp+3D0h+arg_20], 1
0x180003359  jz      short loc_180003394
0x18000335b  mov     r8, [rsp+4D0h+var_478]
0x180003360  lea     rcx, [rsp+4D0h+ValueName]
0x180003365  xor     r9d, r9d
0x180003368  mov     dword ptr [rsp+4D0h+phkResult], ebx
0x18000336c  mov     rdx, r13
0x18000336f  call    ?SuspUtilsMarkAsOEM@@YAJPEAGPEAUHKEY__@@PEBGW4_SUS_STARTUP_TYPE@@H@Z; SuspUtilsMarkAsOEM(ushort *,HKEY__ *,ushort const *,_SUS_STARTUP_TYPE,int)
0x180003374  test    eax, eax
0x180003376  jns     short loc_180003394
0x180003378  mov     rcx, cs:WPP_GLOBAL_Control
0x18000337f  cmp     rcx, rsi
0x180003382  jz      short loc_180003397
0x180003384  test    byte ptr [rcx+1Ch], 1
0x180003388  jz      short loc_180003397
0x18000338a  mov     edx, 0Eh
0x18000338f  jmp     loc_1800032CE
0x180003394  inc     r15d
0x180003397  mov     rcx, [rsp+4D0h+hKey]; hKey
0x18000339c  lea     rax, [rsp+4D0h+cbData]
0x1800033a1  mov     [rsp+4D0h+lpcbData], rax; lpcbData
0x1800033a6  lea     r9, [rsp+4D0h+cchValueName]; lpcchValueName
0x1800033ab  lea     rax, [rbp+3D0h+Data]
0x1800033b2  mov     [rsp+4D0h+var_490], 0
0x1800033ba  mov     [rsp+4D0h+lpData], rax; lpData
0x1800033bf  lea     r8, [rsp+4D0h+ValueName]; lpValueName
0x1800033c4  lea     rax, [rsp+4D0h+Type]
0x1800033c9  mov     [rsp+4D0h+cbData], 208h
0x1800033d1  mov     [rsp+4D0h+lpType], rax; lpType
0x1800033d6  inc     r12d
0x1800033d9  mov     edx, r12d; dwIndex
0x1800033dc  mov     [rsp+4D0h+phkResult], 0; lpReserved
0x1800033e5  mov     [rsp+4D0h+cchValueName], 104h
0x1800033ed  call    cs:__imp_RegEnumValueW
0x1800033f3  mov     ebx, eax
0x1800033f5  cmp     eax, 103h
0x1800033fa  jnz     loc_18000329E
0x180003400  add     [r14+4], r15d
0x180003404  xor     ebx, ebx
0x180003406  mov     rcx, [rsp+4D0h+hKey]; hKey
0x18000340b  test    rcx, rcx
0x18000340e  jz      short loc_180003416
0x180003410  call    cs:__imp_RegCloseKey
0x180003416  mov     eax, ebx
0x180003418  mov     rcx, [rbp+3D0h+var_40]
0x18000341f  xor     rcx, rsp; StackCookie
0x180003422  call    __security_check_cookie
0x180003427  add     rsp, 4A0h
0x18000342e  pop     r15
0x180003430  pop     r14
0x180003432  pop     r13
0x180003434  pop     r12
0x180003436  pop     rsi
0x180003437  pop     rbx
0x180003438  pop     rbp
0x180003439  retn
0x18000343a  jle     short loc_180003445
0x18000343c  movzx   ebx, bx
0x18000343f  or      ebx, 80070000h
0x180003445  mov     rcx, cs:WPP_GLOBAL_Control
0x18000344c  cmp     rcx, rsi
0x18000344f  jz      short loc_180003406
0x180003451  test    byte ptr [rcx+1Ch], 1
0x180003455  jz      short loc_180003406
0x180003457  mov     rcx, [rcx+10h]
0x18000345b  lea     r8, WPP_91e8665fb8f03560ae482285a745ac49_Traceguids
0x180003462  movzx   r9d, bx
0x180003466  mov     edx, 0Bh
0x18000346b  call    WPP_SF_D
0x180003470  jmp     short loc_180003406
```
