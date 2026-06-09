# ShieldProvider::GetServiceCorePath

- ea: `0x140003e58`
- end: `0x14000416c`
- name: `ShieldProvider::GetServiceCorePath`
- size: `788`
- prototype: `__int64 __fastcall(void **, int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140004588`

## callees

- `0x1400015f4`
- `0x140003640`
- `0x140003db4`
- `0x140003e58`
- `0x140005394`
- `0x140007384`
- `0x14000eb7c`
- `0x14000f3ac`
- `0x14000fb20`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x140003fd0`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x140003fd0`
- `KERNEL32!GetSystemDirectoryW` at `0x140003e7f`
- `KERNEL32!GetSystemDirectoryW` at `0x140004018`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003f3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400040b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004127`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004144`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003f3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400040b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004127`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004144`

## string_xrefs

- `0x140003e86`: `SecurityHealthCore.dll`
- `0x14000401f`: `SecurityHealthCore.dll`
- `0x140004052`: `SecurityHealthCore.dll`
- `0x140003eee`: `SOFTWARE\Microsoft\Windows Security Health\Platform`

## pseudocode

```c
__int64 __fastcall ShieldProvider::GetServiceCorePath(void **a1, int a2, __int64 a3, unsigned int a4)
{
  int WindowsPath; // eax
  unsigned __int64 v7; // rdx
  unsigned int v8; // ebx
  int v10; // eax
  unsigned __int64 v11; // rdx
  HKEY v12; // rbx
  unsigned __int16 *v13; // rsi
  int v14; // edi
  int v15; // edi
  const wchar_t *v16; // rdx
  int ValueString; // eax
  bool v18; // r15
  int NormalizedPath; // eax
  unsigned __int64 v20; // rdx
  HKEY v21; // rdi
  size_t v22; // r8
  unsigned __int64 v23; // rdx
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  unsigned __int16 *v26; // [rsp+30h] [rbp-10h] BYREF
  void *v27; // [rsp+90h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+58h] BYREF

  v27 = 0;
  if ( !a2 )
  {
    WindowsPath = CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &v27, L"SecurityHealthCore.dll");
    v8 = WindowsPath;
    if ( WindowsPath < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)(a2 + 11),
          WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
          (unsigned int)WindowsPath);
      if ( v27 )
        operator delete(v27, v7);
      return v8;
    }
    goto LABEL_60;
  }
  hKey = 0;
  v10 = ShieldProvider::ShieldUtilRegOpenKey(
          (ShieldProvider *)&hKey,
          (HKEY *)L"SOFTWARE\\Microsoft\\Windows Security Health\\Platform",
          (const unsigned __int16 *)0x20019,
          a4);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
        (unsigned int)v10);
    if ( hKey )
      RegCloseKey(hKey);
    return v8;
  }
  v12 = hKey;
  v13 = 0;
  v26 = 0;
  v14 = a2 - 1;
  if ( v14 )
  {
    if ( v14 != 1 )
    {
      v15 = -2147024846;
LABEL_49:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
          (unsigned int)v15);
      if ( v13 )
        operator delete(v13, v11);
      if ( v12 )
        RegCloseKey(v12);
      return (unsigned int)v15;
    }
    v16 = L"NewLocation";
  }
  else
  {
    v16 = L"CoreLocation";
  }
  ValueString = CommonUtil::UtilRegGetValueString(hKey, v16, &v26);
  v13 = v26;
  v15 = ValueString;
  if ( ValueString < 0 )
  {
    if ( ValueString != -2147024894 && ValueString != -2147024891 )
      goto LABEL_49;
LABEL_31:
    v15 = CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &v27, L"SecurityHealthCore.dll");
    if ( v15 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_40;
      v25 = 15;
LABEL_39:
      WPP_SF_d(v24[2], v25, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids, (unsigned int)v15);
LABEL_40:
      if ( v13 )
        operator delete(v13, v23);
      if ( v12 )
        RegCloseKey(v12);
      if ( v27 )
        operator delete(v27, v23);
      return (unsigned int)v15;
    }
    goto LABEL_56;
  }
  hKey = 0;
  v18 = 0;
  NormalizedPath = ShieldProvider::GetNormalizedPath(v26);
  v21 = hKey;
  if ( NormalizedPath >= 0 )
  {
    v22 = -1;
    do
      ++v22;
    while ( String1[v22] );
    v18 = _wcsnicmp(String1, (const wchar_t *)hKey, v22) == 0;
  }
  if ( v21 )
    operator delete(v21, v20);
  if ( !v18 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids, v13);
    goto LABEL_31;
  }
  v15 = CommonUtil::NewSprintfW((CommonUtil *)&v27, (unsigned __int16 **)L"%ls\\%ls", v13, L"SecurityHealthCore.dll");
  if ( v15 < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_40;
    v25 = 14;
    goto LABEL_39;
  }
LABEL_56:
  if ( v13 )
    operator delete(v13, v23);
  if ( v12 )
    RegCloseKey(v12);
LABEL_60:
  *a1 = v27;
  return 0;
}

```

## disassembly

```asm
0x140003e58  mov     [rsp-38h+arg_0], rbx
0x140003e5d  push    rbp
0x140003e5e  push    rsi
0x140003e5f  push    rdi
0x140003e60  push    r12
0x140003e62  push    r13
0x140003e64  push    r14
0x140003e66  push    r15
0x140003e68  mov     rbp, rsp
0x140003e6b  sub     rsp, 40h
0x140003e6f  xor     r13d, r13d
0x140003e72  mov     edi, edx
0x140003e74  mov     [rbp+arg_10], r13
0x140003e78  mov     r12, rcx
0x140003e7b  test    edx, edx
0x140003e7d  jnz     short loc_140003EE4
0x140003e7f  mov     rcx, cs:__imp_GetSystemDirectoryW
0x140003e86  lea     r8, aSecurityhealth; "SecurityHealthCore.dll"
0x140003e8d  lea     rdx, [rbp+arg_10]
0x140003e91  call    CommonUtil__UtilGetWindowsPath
0x140003e96  mov     ebx, eax
0x140003e98  test    eax, eax
0x140003e9a  jns     loc_14000414A
0x140003ea0  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ea7  lea     r14, WPP_GLOBAL_Control
0x140003eae  cmp     rcx, r14
0x140003eb1  jz      short loc_140003ECF
0x140003eb3  test    byte ptr [rcx+1Ch], 1
0x140003eb7  jz      short loc_140003ECF
0x140003eb9  mov     rcx, [rcx+10h]
0x140003ebd  lea     edx, [rdi+0Bh]
0x140003ec0  mov     r9d, eax
0x140003ec3  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x140003eca  call    WPP_SF_d
0x140003ecf  mov     rcx, [rbp+arg_10]; void *
0x140003ed3  test    rcx, rcx
0x140003ed6  jz      short loc_140003EDD
0x140003ed8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003edd  mov     eax, ebx
0x140003edf  jmp     loc_140004154
0x140003ee4  mov     r8d, 20019h; unsigned __int16 *
0x140003eea  mov     [rbp+hKey], r13
0x140003eee  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows Security H"...
0x140003ef5  lea     rcx, [rbp+hKey]; this
0x140003ef9  call    ?ShieldUtilRegOpenKey@ShieldProvider@@YAJPEAPEAUHKEY__@@PEBGK@Z; ShieldProvider::ShieldUtilRegOpenKey(HKEY__ * *,ushort const *,ulong)
0x140003efe  mov     ebx, eax
0x140003f00  test    eax, eax
0x140003f02  jns     short loc_140003F46
0x140003f04  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f0b  lea     r14, WPP_GLOBAL_Control
0x140003f12  cmp     rcx, r14
0x140003f15  jz      short loc_140003F35
0x140003f17  test    byte ptr [rcx+1Ch], 1
0x140003f1b  jz      short loc_140003F35
0x140003f1d  mov     rcx, [rcx+10h]
0x140003f21  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x140003f28  mov     edx, 0Ch
0x140003f2d  mov     r9d, eax
0x140003f30  call    WPP_SF_d
0x140003f35  mov     rcx, [rbp+hKey]; hKey
0x140003f39  test    rcx, rcx
0x140003f3c  jz      short loc_140003EDD
0x140003f3e  call    cs:__imp_RegCloseKey
0x140003f44  jmp     short loc_140003EDD
0x140003f46  mov     rbx, [rbp+hKey]
0x140003f4a  mov     rsi, r13
0x140003f4d  mov     [rbp+var_10], r13
0x140003f51  sub     edi, 1
0x140003f54  jz      short loc_140003F75
0x140003f56  cmp     edi, 1
0x140003f59  jz      short loc_140003F6C
0x140003f5b  mov     edi, 80070032h
0x140003f60  lea     r14, WPP_GLOBAL_Control
0x140003f67  jmp     loc_1400040E8
0x140003f6c  lea     rdx, ValueName; "NewLocation"
0x140003f73  jmp     short loc_140003F7C
0x140003f75  lea     rdx, aCorelocation; "CoreLocation"
0x140003f7c  lea     r8, [rbp+var_10]
0x140003f80  mov     rcx, rbx
0x140003f83  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAPEAGW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,ushort const *,ushort * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x140003f88  mov     rsi, [rbp+var_10]
0x140003f8c  mov     edi, eax
0x140003f8e  lea     r14, WPP_GLOBAL_Control
0x140003f95  test    eax, eax
0x140003f97  js      loc_1400040D0
0x140003f9d  lea     rdx, [rbp+hKey]
0x140003fa1  mov     [rbp+hKey], r13
0x140003fa5  mov     rcx, rsi; unsigned __int16 *
0x140003fa8  mov     r15b, r13b
0x140003fab  call    ShieldProvider__GetNormalizedPath
0x140003fb0  mov     rdi, [rbp+hKey]
0x140003fb4  test    eax, eax
0x140003fb6  js      short loc_140003FDC
0x140003fb8  mov     rcx, cs:String1; String1
0x140003fbf  or      r8, 0FFFFFFFFFFFFFFFFh
0x140003fc3  inc     r8; MaxCount
0x140003fc6  cmp     [rcx+r8*2], r13w
0x140003fcb  jnz     short loc_140003FC3
0x140003fcd  mov     rdx, rdi; String2
0x140003fd0  call    cs:__imp__wcsnicmp
0x140003fd6  test    eax, eax
0x140003fd8  setz    r15b
0x140003fdc  test    rdi, rdi
0x140003fdf  jz      short loc_140003FE9
0x140003fe1  mov     rcx, rdi; void *
0x140003fe4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003fe9  test    r15b, r15b
0x140003fec  jnz     short loc_140004052
0x140003fee  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ff5  cmp     rcx, r14
0x140003ff8  jz      short loc_140004018
0x140003ffa  test    byte ptr [rcx+1Ch], 2
0x140003ffe  jz      short loc_140004018
0x140004000  mov     rcx, [rcx+10h]
0x140004004  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x14000400b  mov     edx, 0Dh
0x140004010  mov     r9, rsi
0x140004013  call    WPP_SF_S
0x140004018  mov     rcx, cs:__imp_GetSystemDirectoryW
0x14000401f  lea     r8, aSecurityhealth; "SecurityHealthCore.dll"
0x140004026  lea     rdx, [rbp+arg_10]
0x14000402a  call    CommonUtil__UtilGetWindowsPath
0x14000402f  mov     edi, eax
0x140004031  test    eax, eax
0x140004033  jns     loc_14000412F
0x140004039  mov     rcx, cs:WPP_GLOBAL_Control
0x140004040  cmp     rcx, r14
0x140004043  jz      short loc_1400040A0
0x140004045  test    byte ptr [rcx+1Ch], 1
0x140004049  jz      short loc_1400040A0
0x14000404b  mov     edx, 0Fh
0x140004050  jmp     short loc_14000408D
0x140004052  lea     r9, aSecurityhealth; "SecurityHealthCore.dll"
0x140004059  mov     r8, rsi; unsigned __int16 *
0x14000405c  lea     rdx, aLsLs; "%ls\\%ls"
0x140004063  lea     rcx, [rbp+arg_10]; this
0x140004067  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x14000406c  mov     edi, eax
0x14000406e  test    eax, eax
0x140004070  jns     loc_14000412F
0x140004076  mov     rcx, cs:WPP_GLOBAL_Control
0x14000407d  cmp     rcx, r14
0x140004080  jz      short loc_1400040A0
0x140004082  test    byte ptr [rcx+1Ch], 1
0x140004086  jz      short loc_1400040A0
0x140004088  mov     edx, 0Eh
0x14000408d  mov     rcx, [rcx+10h]
0x140004091  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x140004098  mov     r9d, edi
0x14000409b  call    WPP_SF_d
0x1400040a0  test    rsi, rsi
0x1400040a3  jz      short loc_1400040AD
0x1400040a5  mov     rcx, rsi; void *
0x1400040a8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400040ad  test    rbx, rbx
0x1400040b0  jz      short loc_1400040BB
0x1400040b2  mov     rcx, rbx; hKey
0x1400040b5  call    cs:__imp_RegCloseKey
0x1400040bb  mov     rcx, [rbp+arg_10]; void *
0x1400040bf  test    rcx, rcx
0x1400040c2  jz      short loc_1400040C9
0x1400040c4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400040c9  mov     eax, edi
0x1400040cb  jmp     loc_140004154
0x1400040d0  cmp     edi, 80070002h
0x1400040d6  jz      loc_140004018
0x1400040dc  cmp     edi, 80070005h
0x1400040e2  jz      loc_140004018
0x1400040e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400040ef  cmp     rcx, r14
0x1400040f2  jz      short loc_140004112
0x1400040f4  test    byte ptr [rcx+1Ch], 1
0x1400040f8  jz      short loc_140004112
0x1400040fa  mov     rcx, [rcx+10h]
0x1400040fe  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x140004105  mov     edx, 10h
0x14000410a  mov     r9d, edi
0x14000410d  call    WPP_SF_d
0x140004112  test    rsi, rsi
0x140004115  jz      short loc_14000411F
0x140004117  mov     rcx, rsi; void *
0x14000411a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000411f  test    rbx, rbx
0x140004122  jz      short loc_1400040C9
0x140004124  mov     rcx, rbx; hKey
0x140004127  call    cs:__imp_RegCloseKey
0x14000412d  jmp     short loc_1400040C9
0x14000412f  test    rsi, rsi
0x140004132  jz      short loc_14000413C
0x140004134  mov     rcx, rsi; void *
0x140004137  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000413c  test    rbx, rbx
0x14000413f  jz      short loc_14000414A
0x140004141  mov     rcx, rbx; hKey
0x140004144  call    cs:__imp_RegCloseKey
0x14000414a  mov     rax, [rbp+arg_10]
0x14000414e  mov     [r12], rax
0x140004152  xor     eax, eax
0x140004154  mov     rbx, [rsp+40h+arg_0]
0x14000415c  add     rsp, 40h
0x140004160  pop     r15
0x140004162  pop     r14
0x140004164  pop     r13
0x140004166  pop     r12
0x140004168  pop     rdi
0x140004169  pop     rsi
0x14000416a  pop     rbp
0x14000416b  retn
```
