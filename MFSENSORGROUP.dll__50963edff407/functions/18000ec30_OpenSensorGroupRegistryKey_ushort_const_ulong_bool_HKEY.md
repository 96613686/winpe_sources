# OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)

- ea: `0x18000ec30`
- end: `0x18000ee25`
- name: `?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, bool *, HKEY *)`
- caller_count: `14`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009dbc`
- `0x180009ed0`
- `0x18000c6d8`
- `0x18000c9d0`
- `0x18000cb74`
- `0x18000cf40`
- `0x180010a30`
- `0x180011d94`
- `0x180030cd0`
- `0x180035080`
- `0x18004e800`
- `0x18004f600`
- `0x1800544c4`
- `0x1800553d8`

## callees

- `0x180005fa0`
- `0x18000ec30`
- `0x18000f200`
- `0x18000f518`
- `0x180044f30`
- `0x180045900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ecc9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ee10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ecc9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ee10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed25`

## pseudocode

```c
__int64 __fastcall OpenSensorGroupRegistryKey(const unsigned __int16 *a1, int a2, bool *a3, HKEY *a4)
{
  REGSAM v8; // ebp
  unsigned int v9; // r8d
  int SensorGroupStorePath; // eax
  bool v11; // r14
  unsigned int v12; // esi
  LSTATUS v13; // eax
  __int64 result; // rax
  __int64 v15; // rdx
  bool v16; // sf
  int v17; // eax
  WCHAR *v18; // rdx
  LSTATUS v19; // eax
  bool v20; // [rsp+30h] [rbp-268h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-260h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-258h] BYREF

  v20 = 0;
  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  v8 = a2 | 0x100;
  SensorGroupStorePath = GetSensorGroupStorePath(a1, SubKey, v9, &v20);
  v11 = v20;
  if ( SensorGroupStorePath < 0 )
    goto LABEL_22;
  v12 = 0;
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, v8, &hKey);
  if ( !v13 )
    goto LABEL_3;
  if ( v11 )
  {
LABEL_22:
    if ( a1 )
    {
      v17 = StringCchPrintfW(
              SubKey,
              0x104u,
              L"%s\\%s",
              L"SOFTWARE\\Microsoft\\Windows Media Foundation\\FrameServer\\SensorGroups",
              a1);
      v12 = v17;
      if ( v17 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v17);
        goto LABEL_3;
      }
      v18 = SubKey;
    }
    else
    {
      v18 = (WCHAR *)L"SOFTWARE\\Microsoft\\Windows Media Foundation\\FrameServer\\SensorGroups";
    }
    v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v18, 0, v8, &hKey);
    v12 = v19;
    v16 = v19 < 0;
    if ( v19 )
    {
      if ( v19 > 0 )
      {
        v12 = (unsigned __int16)v19 | 0x80070000;
        v16 = 1;
      }
      if ( v16 && g_wppLevels )
      {
        v15 = 18;
        goto LABEL_21;
      }
    }
  }
  else
  {
    if ( v13 <= 0 )
      v12 = v13;
    else
      v12 = (unsigned __int16)v13 | 0x80070000;
    if ( g_wppLevels )
    {
      v15 = 16;
LABEL_21:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v12);
    }
  }
LABEL_3:
  if ( a4 )
  {
    *a4 = hKey;
  }
  else if ( hKey )
  {
    RegCloseKey(hKey);
  }
  result = v12;
  if ( a3 )
    *a3 = v11;
  return result;
}

```

## disassembly

```asm
0x18000ec30  mov     r11, rsp
0x18000ec33  push    rbx
0x18000ec34  push    rsi
0x18000ec35  push    r14
0x18000ec37  sub     rsp, 280h
0x18000ec3e  mov     rax, cs:__security_cookie
0x18000ec45  xor     rax, rsp
0x18000ec48  mov     [rsp+298h+var_48], rax
0x18000ec50  mov     [r11-20h], rbp
0x18000ec54  mov     rbx, r8
0x18000ec57  mov     [r11-28h], rdi
0x18000ec5b  mov     ebp, edx
0x18000ec5d  mov     [r11-30h], r15
0x18000ec61  xor     edx, edx; Val
0x18000ec63  mov     r15, rcx
0x18000ec66  mov     [rsp+298h+var_268], 0
0x18000ec6b  lea     rcx, [rsp+298h+SubKey]; void *
0x18000ec70  mov     [rsp+298h+hKey], 0
0x18000ec79  mov     r8d, 208h; Size
0x18000ec7f  mov     rdi, r9
0x18000ec82  call    memset_0
0x18000ec87  lea     r9, [rsp+298h+var_268]; bool *
0x18000ec8c  mov     rcx, r15; unsigned __int16 *
0x18000ec8f  lea     rdx, [rsp+298h+SubKey]; unsigned __int16 *
0x18000ec94  bts     ebp, 8
0x18000ec98  call    ?GetSensorGroupStorePath@@YAJPEBGPEAGKPEA_N@Z; GetSensorGroupStorePath(ushort const *,ushort *,ulong,bool *)
0x18000ec9d  movzx   r14d, [rsp+298h+var_268]
0x18000eca3  test    eax, eax
0x18000eca5  js      loc_18000EDAF
0x18000ecab  lea     rax, [rsp+298h+hKey]
0x18000ecb0  mov     r9d, ebp; samDesired
0x18000ecb3  xor     r8d, r8d; ulOptions
0x18000ecb6  mov     [rsp+298h+phkResult], rax; phkResult
0x18000ecbb  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x18000ecc0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ecc7  xor     esi, esi
0x18000ecc9  call    cs:__imp_RegOpenKeyExW
0x18000eccf  test    eax, eax
0x18000ecd1  jnz     short loc_18000ED32
0x18000ecd3  mov     r15, [rsp+298h+var_30]
0x18000ecdb  mov     rbp, [rsp+298h+var_20]
0x18000ece3  test    rdi, rdi
0x18000ece6  jz      short loc_18000ED1B
0x18000ece8  mov     rax, [rsp+298h+hKey]
0x18000eced  mov     [rdi], rax
0x18000ecf0  mov     rdi, [rsp+298h+var_28]
0x18000ecf8  mov     eax, esi
0x18000ecfa  test    rbx, rbx
0x18000ecfd  jnz     short loc_18000ED2D
0x18000ecff  mov     rcx, [rsp+298h+var_48]
0x18000ed07  xor     rcx, rsp; StackCookie
0x18000ed0a  call    __security_check_cookie
0x18000ed0f  add     rsp, 280h
0x18000ed16  pop     r14
0x18000ed18  pop     rsi
0x18000ed19  pop     rbx
0x18000ed1a  retn
0x18000ed1b  mov     rcx, [rsp+298h+hKey]; hKey
0x18000ed20  test    rcx, rcx
0x18000ed23  jz      short loc_18000ECF0
0x18000ed25  call    cs:__imp_RegCloseKey
0x18000ed2b  jmp     short loc_18000ECF0
0x18000ed2d  mov     [rbx], r14b
0x18000ed30  jmp     short loc_18000ECFF
0x18000ed32  test    r14b, r14b
0x18000ed35  jnz     short loc_18000EDAF
0x18000ed37  test    eax, eax
0x18000ed39  jle     short loc_18000ED58
0x18000ed3b  movzx   esi, ax
0x18000ed3e  or      esi, 80070000h
0x18000ed44  test    esi, esi
0x18000ed46  jns     short loc_18000ECD3
0x18000ed48  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000ed4f  jb      short loc_18000ECD3
0x18000ed51  mov     edx, 10h
0x18000ed56  jmp     short loc_18000ED81
0x18000ed58  mov     esi, eax
0x18000ed5a  jmp     short loc_18000ED44
0x18000ed5c  jle     short loc_18000ED69
0x18000ed5e  movzx   esi, si
0x18000ed61  or      esi, 80070000h
0x18000ed67  test    esi, esi
0x18000ed69  jns     loc_18000ECD3
0x18000ed6f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000ed76  jb      loc_18000ECD3
0x18000ed7c  mov     edx, 12h
0x18000ed81  mov     dword ptr [rsp+298h+phkResult], esi
0x18000ed85  jmp     short loc_18000ED90
0x18000ed87  mov     edx, 11h
0x18000ed8c  mov     dword ptr [rsp+298h+phkResult], eax
0x18000ed90  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed97  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18000ed9e  xor     r9d, r9d
0x18000eda1  mov     rcx, [rcx+10h]
0x18000eda5  call    WPP_SF_qD
0x18000edaa  jmp     loc_18000ECD3
0x18000edaf  test    r15, r15
0x18000edb2  jz      short loc_18000EDF2
0x18000edb4  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Media Foun"...
0x18000edbb  mov     [rsp+298h+phkResult], r15
0x18000edc0  lea     r8, aSS; "%s\\%s"
0x18000edc7  mov     edx, 104h; unsigned __int64
0x18000edcc  lea     rcx, [rsp+298h+SubKey]; unsigned __int16 *
0x18000edd1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000edd6  mov     esi, eax
0x18000edd8  test    eax, eax
0x18000edda  jns     short loc_18000EDEB
0x18000eddc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000ede3  jb      loc_18000ECD3
0x18000ede9  jmp     short loc_18000ED87
0x18000edeb  lea     rdx, [rsp+298h+SubKey]
0x18000edf0  jmp     short loc_18000EDF9
0x18000edf2  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Media Foun"...
0x18000edf9  lea     rax, [rsp+298h+hKey]
0x18000edfe  mov     r9d, ebp; samDesired
0x18000ee01  xor     r8d, r8d; ulOptions
0x18000ee04  mov     [rsp+298h+phkResult], rax; phkResult
0x18000ee09  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ee10  call    cs:__imp_RegOpenKeyExW
0x18000ee16  mov     esi, eax
0x18000ee18  test    eax, eax
0x18000ee1a  jnz     loc_18000ED5C
0x18000ee20  jmp     loc_18000ECD3
```
