# OpenExtensionKey

- ea: `0x140080614`
- end: `0x1400808b7`
- name: `OpenExtensionKey`
- size: `675`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140083330`
- `0x140084fb8`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004fe4`
- `0x140074f18`
- `0x140080614`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14008070b`
- `ADVAPI32!RegCloseKey` at `0x14008070b`
- `KERNEL32!GetLastError` at `0x1400806bd`
- `KERNEL32!GetLastError` at `0x14008084d`
- `KERNEL32!GetLastError` at `0x1400806bd`
- `KERNEL32!GetLastError` at `0x14008084d`

## string_xrefs

- `0x1400807b7`: `UnassociatedExtensionData`

## pseudocode

```c
__int64 __fastcall OpenExtensionKey(int a1, int a2, HKEY *a3)
{
  __int64 result; // rax
  HKEY v7; // rax
  DWORD LastError; // eax
  DWORD v9; // ebx
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  HKEY v13; // rax
  unsigned __int16 v14[264]; // [rsp+30h] [rbp-238h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a2 != 1 )
        return 31;
      v7 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\TAPIDevices", 1, 0x20019u);
      if ( !v7 )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
        }
        return v9;
      }
      RegCloseKey(v7);
      v10 = StringCchPrintfW(v14, 0x104u, L"%s\\%08lx", L"Software\\Microsoft\\Fax\\TAPIDevices", a1);
      v9 = v10;
      if ( v10 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            89,
            &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
            (unsigned int)v10);
        }
        if ( (v9 & 0x1FFF0000) == 0x70000 )
          return (unsigned __int16)v9;
        return v9;
      }
LABEL_31:
      v9 = 0;
      v13 = OpenRegistryKey(HKEY_LOCAL_MACHINE, v14, 1, 0x2001Fu);
      *a3 = v13;
      if ( !v13 )
      {
        v9 = GetLastError();
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
        }
      }
      return v9;
    }
    v11 = StringCchPrintfW(
            v14,
            0x104u,
            L"%s\\%010d\\%s",
            L"Software\\Microsoft\\Fax\\Devices",
            a1,
            L"{F10A5326-0261-4715-B367-2970427BBD99}");
  }
  else
  {
    v11 = StringCchPrintfW(v14, 0x104u, L"%s\\%s", L"Software\\Microsoft\\Fax\\Devices", L"UnassociatedExtensionData");
  }
  v12 = v11;
  if ( v11 >= 0 )
    goto LABEL_31;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      87,
      &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
      (unsigned int)v11);
  }
  result = (unsigned __int16)v12;
  if ( (v12 & 0x1FFF0000) != 0x70000 )
    return v12;
  return result;
}

```

## disassembly

```asm
0x140080614  mov     [rsp+arg_8], rbx
0x140080619  mov     [rsp+arg_18], rsi
0x14008061e  push    rdi
0x14008061f  push    r14
0x140080621  push    r15
0x140080623  sub     rsp, 250h
0x14008062a  mov     rax, cs:__security_cookie
0x140080631  xor     rax, rsp
0x140080634  mov     [rsp+268h+var_28], rax
0x14008063c  mov     rsi, r8
0x14008063f  mov     ebx, edx
0x140080641  mov     edi, ecx
0x140080643  mov     rcx, cs:WPP_GLOBAL_Control
0x14008064a  lea     r14, WPP_GLOBAL_Control
0x140080651  lea     r15, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140080658  cmp     rcx, r14
0x14008065b  jz      short loc_14008067A
0x14008065d  test    byte ptr [rcx+1Ch], 2
0x140080661  jz      short loc_14008067A
0x140080663  cmp     byte ptr [rcx+19h], 5
0x140080667  jb      short loc_14008067A
0x140080669  mov     rcx, [rcx+10h]
0x14008066d  mov     edx, 56h ; 'V'
0x140080672  mov     r8, r15
0x140080675  call    WPP_SF_
0x14008067a  test    edi, edi
0x14008067c  jz      loc_1400807B7
0x140080682  test    ebx, ebx
0x140080684  jz      loc_140080788
0x14008068a  cmp     ebx, 1
0x14008068d  jz      short loc_140080699
0x14008068f  mov     eax, 1Fh
0x140080694  jmp     loc_14008088D
0x140080699  mov     r9d, 20019h
0x14008069f  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Fax\\TAPIDevices"
0x1400806a6  mov     r8d, 1
0x1400806ac  mov     rcx, 0FFFFFFFF80000002h
0x1400806b3  call    OpenRegistryKey
0x1400806b8  test    rax, rax
0x1400806bb  jnz     short loc_140080708
0x1400806bd  call    cs:__imp_GetLastError
0x1400806c4  nop     dword ptr [rax+rax+00h]
0x1400806c9  mov     ebx, eax
0x1400806cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400806d2  cmp     rcx, r14
0x1400806d5  jz      loc_14008088B
0x1400806db  test    byte ptr [rcx+1Ch], 2
0x1400806df  jz      loc_14008088B
0x1400806e5  cmp     byte ptr [rcx+19h], 2
0x1400806e9  jb      loc_14008088B
0x1400806ef  mov     rcx, [rcx+10h]
0x1400806f3  mov     edx, 58h ; 'X'
0x1400806f8  mov     r9d, eax
0x1400806fb  mov     r8, r15
0x1400806fe  call    WPP_SF_d
0x140080703  jmp     loc_14008088B
0x140080708  mov     rcx, rax; hKey
0x14008070b  call    cs:__imp_RegCloseKey
0x140080712  nop     dword ptr [rax+rax+00h]
0x140080717  lea     r9, aSoftwareMicros_7; "Software\\Microsoft\\Fax\\TAPIDevices"
0x14008071e  mov     dword ptr [rsp+268h+var_248], edi
0x140080722  lea     r8, aS08lx; "%s\\%08lx"
0x140080729  mov     edx, 104h; unsigned __int64
0x14008072e  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x140080733  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140080738  mov     ebx, eax
0x14008073a  test    eax, eax
0x14008073c  jns     loc_140080828
0x140080742  mov     rcx, cs:WPP_GLOBAL_Control
0x140080749  cmp     rcx, r14
0x14008074c  jz      short loc_14008076E
0x14008074e  test    byte ptr [rcx+1Ch], 2
0x140080752  jz      short loc_14008076E
0x140080754  cmp     byte ptr [rcx+19h], 2
0x140080758  jb      short loc_14008076E
0x14008075a  mov     rcx, [rcx+10h]
0x14008075e  mov     edx, 59h ; 'Y'
0x140080763  mov     r9d, eax
0x140080766  mov     r8, r15
0x140080769  call    WPP_SF_d
0x14008076e  mov     eax, ebx
0x140080770  and     eax, 1FFF0000h
0x140080775  cmp     eax, 70000h
0x14008077a  jnz     loc_14008088B
0x140080780  movzx   ebx, bx
0x140080783  jmp     loc_14008088B
0x140080788  lea     rax, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x14008078f  mov     edx, 104h; unsigned __int64
0x140080794  mov     [rsp+268h+var_240], rax
0x140080799  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x1400807a0  lea     r8, aS010dS; "%s\\%010d\\%s"
0x1400807a7  mov     dword ptr [rsp+268h+var_248], edi
0x1400807ab  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x1400807b0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400807b5  jmp     short loc_1400807E0
0x1400807b7  lea     rax, aUnassociatedex; "UnassociatedExtensionData"
0x1400807be  mov     edx, 104h; unsigned __int64
0x1400807c3  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x1400807ca  mov     [rsp+268h+var_248], rax
0x1400807cf  lea     r8, aSS_0; "%s\\%s"
0x1400807d6  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x1400807db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400807e0  mov     ebx, eax
0x1400807e2  test    eax, eax
0x1400807e4  jns     short loc_140080828
0x1400807e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400807ed  cmp     rcx, r14
0x1400807f0  jz      short loc_140080812
0x1400807f2  test    byte ptr [rcx+1Ch], 2
0x1400807f6  jz      short loc_140080812
0x1400807f8  cmp     byte ptr [rcx+19h], 2
0x1400807fc  jb      short loc_140080812
0x1400807fe  mov     rcx, [rcx+10h]
0x140080802  mov     edx, 57h ; 'W'
0x140080807  mov     r9d, eax
0x14008080a  mov     r8, r15
0x14008080d  call    WPP_SF_d
0x140080812  mov     ecx, ebx
0x140080814  movzx   eax, bx
0x140080817  and     ecx, 1FFF0000h
0x14008081d  cmp     ecx, 70000h
0x140080823  cmovnz  eax, ebx
0x140080826  jmp     short loc_14008088D
0x140080828  xor     ebx, ebx
0x14008082a  lea     rdx, [rsp+268h+var_238]
0x14008082f  mov     r9d, 2001Fh
0x140080835  mov     rcx, 0FFFFFFFF80000002h
0x14008083c  lea     r8d, [rbx+1]
0x140080840  call    OpenRegistryKey
0x140080845  mov     [rsi], rax
0x140080848  test    rax, rax
0x14008084b  jnz     short loc_14008088B
0x14008084d  call    cs:__imp_GetLastError
0x140080854  nop     dword ptr [rax+rax+00h]
0x140080859  mov     ebx, eax
0x14008085b  mov     rcx, cs:WPP_GLOBAL_Control
0x140080862  cmp     rcx, r14
0x140080865  jz      short loc_14008088B
0x140080867  test    byte ptr [rcx+1Ch], 2
0x14008086b  jz      short loc_14008088B
0x14008086d  cmp     byte ptr [rcx+19h], 2
0x140080871  jb      short loc_14008088B
0x140080873  mov     rcx, [rcx+10h]
0x140080877  mov     edx, 5Ah ; 'Z'
0x14008087c  mov     r9d, edi
0x14008087f  mov     dword ptr [rsp+268h+var_248], eax
0x140080883  mov     r8, r15
0x140080886  call    WPP_SF_dd
0x14008088b  mov     eax, ebx
0x14008088d  mov     rcx, [rsp+268h+var_28]
0x140080895  xor     rcx, rsp; StackCookie
0x140080898  call    __security_check_cookie
0x14008089d  lea     r11, [rsp+268h+var_18]
0x1400808a5  mov     rbx, [r11+28h]
0x1400808a9  mov     rsi, [r11+38h]
0x1400808ad  mov     rsp, r11
0x1400808b0  pop     r15
0x1400808b2  pop     r14
0x1400808b4  pop     rdi
0x1400808b5  retn
```
