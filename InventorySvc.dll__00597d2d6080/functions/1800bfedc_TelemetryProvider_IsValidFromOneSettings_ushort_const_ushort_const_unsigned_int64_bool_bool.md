# TelemetryProvider::IsValidFromOneSettings(ushort const *,ushort const *,unsigned __int64,bool &,bool &)

- ea: `0x1800bfedc`
- end: `0x1800c0377`
- name: `?IsValidFromOneSettings@TelemetryProvider@@CAJPEBG0_KAEA_N2@Z`
- size: `1179`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpValue@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int64@<r8>, bool *@<r9>, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800beed0`

## callees

- `0x180002bf0`
- `0x180003100`
- `0x180003888`
- `0x1800038b8`
- `0x18000543c`
- `0x18000f7bc`
- `0x1800152d0`
- `0x1800153e0`
- `0x1800bfedc`
- `0x1800c073c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800c02b2`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800c02b2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800c01ff`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800c01ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bff96`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c0021`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bff96`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c0021`

## string_xrefs

- `0x1800c028a`: `StringCchCopyW failed [%#x]`
- `0x1800c029c`: `StringCchCopyW failed [%#x]`
- `0x1800c00c6`: `AslFileGetVersionForPath failed [%#x]`
- `0x1800bff75`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\ProviderEos`
- `0x1800bfffc`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\ProviderEos`

## pseudocode

```c
__int64 __fastcall TelemetryProvider::IsValidFromOneSettings(
        LPCWSTR lpValue,
        const unsigned __int16 *a2,
        unsigned __int64 a3,
        bool *a4,
        bool *a5)
{
  bool *v5; // r14
  unsigned __int64 v9; // r15
  void *v10; // r12
  __int64 v11; // r8
  signed int ValueW; // ebx
  wchar_t *v13; // rdx
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rax
  int v16; // ebx
  int v17; // eax
  __int64 v18; // r9
  int VersionForPath; // eax
  int v20; // eax
  wchar_t *v21; // rax
  unsigned __int8 v22; // di
  __int64 v23; // rsi
  __int64 v24; // r15
  __int64 v25; // rcx
  wchar_t *v26; // r8
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  wchar_t v29; // ax
  wchar_t *v30; // r14
  wchar_t *v31; // rcx
  wchar_t *v32; // rcx
  const char *v33; // r9
  __int64 v34; // r8
  unsigned __int64 v35; // rdx
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  LPDWORD pdwTypea; // [rsp+20h] [rbp-E0h]
  PVOID pvData; // [rsp+28h] [rbp-D8h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v41; // [rsp+44h] [rbp-BCh] BYREF
  int v42; // [rsp+48h] [rbp-B8h] BYREF
  int v43; // [rsp+4Ch] [rbp-B4h] BYREF
  wchar_t *Context; // [rsp+50h] [rbp-B0h] BYREF
  bool *v45; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v46; // [rsp+60h] [rbp-A0h]
  wchar_t Str[8]; // [rsp+68h] [rbp-98h] BYREF
  int v48; // [rsp+78h] [rbp-88h]
  wchar_t SubStr[32]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t String[32]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = a5;
  *a4 = 0;
  v46 = a3;
  v45 = a5;
  *a5 = 0;
  v9 = a3;
  v10 = operator new[](0x80u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v10 )
  {
    v11 = 970;
LABEL_3:
    LODWORD(pdwType) = -2147024882;
    ValueW = -2147024882;
    AslLogCallPrintf(1, "TelemetryProvider::IsValidFromOneSettings", v11, "new failed [%#x]", pdwType);
    goto LABEL_60;
  }
  pcbData = 128;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\ProviderEos",
             lpValue,
             2u,
             0,
             v10,
             &pcbData);
  if ( ValueW == 234 )
  {
    v14 = pcbData >> 1;
    operator delete(v10, (const struct std::nothrow_t *)v13);
    v15 = 2 * v14;
    if ( !is_mul_ok(v14, 2u) )
      v15 = -1;
    v10 = operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v10 )
    {
      v11 = 984;
      goto LABEL_3;
    }
    pcbData = 2 * v14;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\ProviderEos",
               lpValue,
               2u,
               0,
               v10,
               &pcbData);
  }
  if ( ValueW == 2 )
  {
    ValueW = 1;
    goto LABEL_60;
  }
  if ( ValueW )
  {
    AslLogCallPrintf(
      1,
      "TelemetryProvider::IsValidFromOneSettings",
      1001,
      "OneSettingsQuery::GetSetting failed [%d]",
      ValueW);
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_60;
  }
  v16 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  if ( TelemetryProvider::UseOneSettingsPpe() )
  {
    v17 = 21341;
    v18 = 10;
  }
  else
  {
    VersionForPath = AslFileGetVersionForPath(&v41, &v42, &v43, a2);
    if ( (VersionForPath & 0xC0000000) == 0xC0000000 )
    {
      LODWORD(pdwType) = VersionForPath;
      ValueW = VersionForPath | 0x10000000;
      AslLogCallPrintf(
        1,
        "TelemetryProvider::IsValidFromOneSettings",
        1019,
        "AslFileGetVersionForPath failed [%#x]",
        pdwType);
      goto LABEL_60;
    }
    v18 = v41;
    v16 = v42;
    v17 = v43;
  }
  LODWORD(pvData) = v17;
  v48 = 0;
  LODWORD(pdwType) = v16;
  *(_OWORD *)Str = 0;
  v20 = StringCchPrintfW(Str, 0xAu, L"%02d%01d%05d", v18, pdwType, pvData);
  ValueW = v20;
  if ( v20 < 0 )
  {
    LODWORD(pdwTypea) = v20;
    AslLogCallPrintf(1, "TelemetryProvider::IsValidFromOneSettings", 1028, "StringCchPrintfW failed [%#x]", pdwTypea);
    goto LABEL_60;
  }
  Context = 0;
  memset_0(String, 0, sizeof(String));
  v21 = o_wcstok_s_0((wchar_t *)v10, L";", &Context);
  v22 = 1;
  if ( !v21 )
  {
LABEL_41:
    if ( String[0] )
    {
      v35 = _wtoi64(String);
      if ( v35 > 0x1F7E33BE0D39C00LL )
      {
        ValueW = -2147418113;
        v33 = "OneSettings EoL match found but invalid expiration date [%#x]";
        v34 = 1100;
        goto LABEL_58;
      }
      *a4 = v35 == 0;
      if ( !v35 || v35 >= v9 )
        v22 = 0;
      *v5 = v22;
      AslLogCallPrintf(
        3,
        "TelemetryProvider::IsValidFromOneSettings",
        1111,
        "OneSettings match was found:%I64u. KillSwitch:%d EoL:%d",
        v35,
        *a4,
        v22);
    }
    else
    {
      ValueW = 1;
    }
    goto LABEL_60;
  }
  v23 = 32;
  v24 = 2147483646;
  while ( 1 )
  {
    v25 = 2147483646;
    v26 = SubStr;
    v27 = 32;
    do
    {
      if ( !v25 )
        break;
      if ( !*v21 )
        break;
      *v26++ = *v21++;
      --v25;
      --v27;
    }
    while ( v27 );
    v28 = v26 - 1;
    ValueW = v27 == 0 ? 0x8007007A : 0;
    if ( v27 )
      v28 = v26;
    *v28 = 0;
    if ( !v27 )
    {
      v33 = "StringCchCopyW failed [%#x]";
      v34 = 1047;
      goto LABEL_58;
    }
    v29 = SubStr[0];
    v30 = 0;
    if ( SubStr[0] )
    {
      v31 = SubStr;
      while ( 1 )
      {
        if ( v29 == 42 )
          goto LABEL_36;
        if ( v29 == 58 )
          break;
LABEL_37:
        v29 = *++v31;
        if ( !*v31 )
          goto LABEL_38;
      }
      v30 = v31 + 1;
LABEL_36:
      *v31 = 0;
      if ( v30 )
        goto LABEL_38;
      goto LABEL_37;
    }
LABEL_38:
    if ( wcsstr(Str, SubStr) )
      break;
    v21 = o_wcstok_s_0(0, L";", &Context);
    if ( !v21 )
      goto LABEL_40;
  }
  v13 = String;
  do
  {
    if ( !v24 )
      break;
    if ( !*v30 )
      break;
    *v13++ = *v30++;
    --v24;
    --v23;
  }
  while ( v23 );
  v32 = v13 - 1;
  ValueW = v23 == 0 ? 0x8007007A : 0;
  if ( v23 )
    v32 = v13;
  *v32 = 0;
  if ( v23 )
  {
LABEL_40:
    v9 = v46;
    v5 = v45;
    goto LABEL_41;
  }
  v33 = "StringCchCopyW failed [%#x]";
  v34 = 1083;
LABEL_58:
  LODWORD(pdwTypea) = ValueW;
  AslLogCallPrintf(1, "TelemetryProvider::IsValidFromOneSettings", v34, v33, pdwTypea);
LABEL_60:
  operator delete(v10, (const struct std::nothrow_t *)v13);
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x1800bfedc  mov     [rsp-8+arg_10], rbx
0x1800bfee1  push    rbp
0x1800bfee2  push    rsi
0x1800bfee3  push    rdi
0x1800bfee4  push    r12
0x1800bfee6  push    r13
0x1800bfee8  push    r14
0x1800bfeea  push    r15
0x1800bfeec  lea     rbp, [rsp-10h]
0x1800bfef1  sub     rsp, 110h
0x1800bfef8  mov     rax, cs:__security_cookie
0x1800bfeff  xor     rax, rsp
0x1800bff02  mov     [rbp+40h+var_40], rax
0x1800bff06  mov     r14, [rbp+40h+arg_20]
0x1800bff0a  xor     ebx, ebx
0x1800bff0c  mov     rsi, rdx
0x1800bff0f  mov     [r9], bl
0x1800bff12  mov     rdi, rcx
0x1800bff15  mov     [rsp+140h+var_E0], r8
0x1800bff1a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bff21  mov     [rsp+140h+var_E8], r14
0x1800bff26  mov     ecx, 80h; unsigned __int64
0x1800bff2b  mov     [r14], bl
0x1800bff2e  mov     r13, r9
0x1800bff31  mov     r15, r8
0x1800bff34  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800bff39  mov     r12, rax
0x1800bff3c  test    rax, rax
0x1800bff3f  jnz     short loc_1800BFF63
0x1800bff41  mov     r8d, 3CAh
0x1800bff47  mov     ecx, 8007000Eh
0x1800bff4c  lea     r9, aNewFailedX; "new failed [%#x]"
0x1800bff53  mov     dword ptr [rsp+140h+pdwType], ecx
0x1800bff57  mov     ebx, ecx
0x1800bff59  mov     ecx, 1
0x1800bff5e  jmp     loc_1800C033A
0x1800bff63  lea     rax, [rsp+140h+var_100]
0x1800bff68  mov     [rsp+140h+var_100], 80h
0x1800bff70  mov     [rsp+140h+pcbData], rax; pcbData
0x1800bff75  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800bff7c  mov     [rsp+140h+pvData], r12; pvData
0x1800bff81  mov     r9d, 2; dwFlags
0x1800bff87  mov     r8, rdi; lpValue
0x1800bff8a  mov     [rsp+140h+pdwType], rbx; pdwType
0x1800bff8f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800bff96  call    cs:__imp_RegGetValueW
0x1800bff9c  mov     ebx, eax
0x1800bff9e  cmp     eax, 0EAh
0x1800bffa3  jnz     loc_1800C0029
0x1800bffa9  mov     ebx, [rsp+140h+var_100]
0x1800bffad  mov     rcx, r12; void *
0x1800bffb0  shr     ebx, 1
0x1800bffb2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bffb7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800bffbe  mov     eax, 2
0x1800bffc3  mul     rbx
0x1800bffc6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bffcd  cmovb   rax, rcx
0x1800bffd1  mov     rcx, rax; unsigned __int64
0x1800bffd4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800bffd9  xor     r8d, r8d
0x1800bffdc  mov     r12, rax
0x1800bffdf  test    rax, rax
0x1800bffe2  jnz     short loc_1800BFFEF
0x1800bffe4  mov     r8d, 3D8h
0x1800bffea  jmp     loc_1800BFF47
0x1800bffef  lea     eax, [rbx+rbx]
0x1800bfff2  mov     r9d, 2; dwFlags
0x1800bfff8  mov     [rsp+140h+var_100], eax
0x1800bfffc  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800c0003  lea     rax, [rsp+140h+var_100]
0x1800c0008  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800c000f  mov     [rsp+140h+pcbData], rax; pcbData
0x1800c0014  mov     [rsp+140h+pvData], r12; pvData
0x1800c0019  mov     [rsp+140h+pdwType], r8; pdwType
0x1800c001e  mov     r8, rdi; lpValue
0x1800c0021  call    cs:__imp_RegGetValueW
0x1800c0027  mov     ebx, eax
0x1800c0029  cmp     ebx, 2
0x1800c002c  jnz     short loc_1800C0038
0x1800c002e  mov     ebx, 1
0x1800c0033  jmp     loc_1800C0346
0x1800c0038  xor     edi, edi
0x1800c003a  test    ebx, ebx
0x1800c003c  jz      short loc_1800C0074
0x1800c003e  lea     r9, aOnesettingsque; "OneSettingsQuery::GetSetting failed [%d"...
0x1800c0045  mov     dword ptr [rsp+140h+pdwType], ebx
0x1800c0049  mov     r8d, 3E9h
0x1800c004f  lea     rdx, aTelemetryprovi_12; "TelemetryProvider::IsValidFromOneSettin"...
0x1800c0056  lea     ecx, [rdi+1]
0x1800c0059  call    AslLogCallPrintf
0x1800c005e  test    ebx, ebx
0x1800c0060  jle     loc_1800C0346
0x1800c0066  movzx   ebx, bx
0x1800c0069  or      ebx, 80070000h
0x1800c006f  jmp     loc_1800C0346
0x1800c0074  mov     ebx, edi
0x1800c0076  mov     [rsp+140h+var_FC], edi
0x1800c007a  mov     [rsp+140h+var_F8], ebx
0x1800c007e  mov     [rsp+140h+var_F4], edi
0x1800c0082  call    ?UseOneSettingsPpe@TelemetryProvider@@CA_NXZ; TelemetryProvider::UseOneSettingsPpe(void)
0x1800c0087  test    al, al
0x1800c0089  jz      short loc_1800C0098
0x1800c008b  mov     eax, 535Dh
0x1800c0090  mov     r9d, 0Ah
0x1800c0096  jmp     short loc_1800C00E5
0x1800c0098  mov     r9, rsi
0x1800c009b  lea     r8, [rsp+140h+var_F4]
0x1800c00a0  lea     rdx, [rsp+140h+var_F8]
0x1800c00a5  lea     rcx, [rsp+140h+var_FC]
0x1800c00aa  call    AslFileGetVersionForPath
0x1800c00af  mov     edx, 0C0000000h
0x1800c00b4  mov     ecx, eax
0x1800c00b6  and     ecx, edx
0x1800c00b8  cmp     ecx, edx
0x1800c00ba  jnz     short loc_1800C00D8
0x1800c00bc  mov     ebx, eax
0x1800c00be  mov     dword ptr [rsp+140h+pdwType], eax
0x1800c00c2  bts     ebx, 1Ch
0x1800c00c6  lea     r9, aAslfilegetvers; "AslFileGetVersionForPath failed [%#x]"
0x1800c00cd  mov     r8d, 3FBh
0x1800c00d3  jmp     loc_1800BFF59
0x1800c00d8  mov     r9d, [rsp+140h+var_FC]
0x1800c00dd  mov     ebx, [rsp+140h+var_F8]
0x1800c00e1  mov     eax, [rsp+140h+var_F4]
0x1800c00e5  xor     ecx, ecx
0x1800c00e7  mov     dword ptr [rsp+140h+pvData], eax
0x1800c00eb  xorps   xmm0, xmm0
0x1800c00ee  mov     [rsp+140h+var_C8], ecx
0x1800c00f2  lea     r8, a02d01d05d; "%02d%01d%05d"
0x1800c00f9  mov     dword ptr [rsp+140h+pdwType], ebx
0x1800c00fd  movups  xmmword ptr [rsp+140h+Str], xmm0
0x1800c0102  lea     edx, [rcx+0Ah]; unsigned __int64
0x1800c0105  lea     rcx, [rsp+140h+Str]; unsigned __int16 *
0x1800c010a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c010f  mov     ebx, eax
0x1800c0111  test    eax, eax
0x1800c0113  jns     short loc_1800C012B
0x1800c0115  mov     dword ptr [rsp+140h+pdwType], eax
0x1800c0119  lea     r9, aStringcchprint_1; "StringCchPrintfW failed [%#x]"
0x1800c0120  mov     r8d, 404h
0x1800c0126  jmp     loc_1800BFF59
0x1800c012b  xor     edx, edx; Val
0x1800c012d  mov     [rsp+140h+Context], rdi
0x1800c0132  lea     rcx, [rbp+40h+String]; void *
0x1800c0136  lea     r8d, [rdx+40h]; Size
0x1800c013a  call    memset_0
0x1800c013f  lea     r8, [rsp+140h+Context]; Context
0x1800c0144  mov     rcx, r12; String
0x1800c0147  lea     rdx, Delimiter; ";"
0x1800c014e  call    _o_wcstok_s_0
0x1800c0153  xor     r10d, r10d
0x1800c0156  mov     edi, 1
0x1800c015b  test    rax, rax
0x1800c015e  jz      loc_1800C0236
0x1800c0164  lea     esi, [rdi+1Fh]
0x1800c0167  mov     r15d, 7FFFFFFEh
0x1800c016d  mov     rcx, r15
0x1800c0170  lea     r8, [rbp+40h+SubStr]
0x1800c0174  mov     rdx, rsi
0x1800c0177  test    rcx, rcx
0x1800c017a  jz      short loc_1800C019A
0x1800c017c  movzx   r9d, word ptr [rax]
0x1800c0180  test    r9w, r9w
0x1800c0184  jz      short loc_1800C019A
0x1800c0186  mov     [r8], r9w
0x1800c018a  add     rax, 2
0x1800c018e  add     r8, 2
0x1800c0192  sub     rcx, rdi
0x1800c0195  sub     rdx, rdi
0x1800c0198  jnz     short loc_1800C0177
0x1800c019a  mov     rax, rdx
0x1800c019d  lea     rcx, [r8-2]
0x1800c01a1  neg     rax
0x1800c01a4  sbb     ebx, ebx
0x1800c01a6  not     ebx
0x1800c01a8  and     ebx, 8007007Ah
0x1800c01ae  test    rdx, rdx
0x1800c01b1  cmovnz  rcx, r8
0x1800c01b5  mov     [rcx], r10w
0x1800c01b9  jz      loc_1800C029C
0x1800c01bf  movzx   eax, [rbp+40h+SubStr]
0x1800c01c3  mov     r14, r10
0x1800c01c6  test    ax, ax
0x1800c01c9  jz      short loc_1800C01F6
0x1800c01cb  lea     rcx, [rbp+40h+SubStr]
0x1800c01cf  cmp     ax, 2Ah ; '*'
0x1800c01d3  jz      short loc_1800C01DF
0x1800c01d5  cmp     ax, 3Ah ; ':'
0x1800c01d9  jnz     short loc_1800C01EA
0x1800c01db  lea     r14, [rcx+2]
0x1800c01df  mov     eax, r10d
0x1800c01e2  mov     [rcx], ax
0x1800c01e5  test    r14, r14
0x1800c01e8  jnz     short loc_1800C01F6
0x1800c01ea  add     rcx, 2
0x1800c01ee  movzx   eax, word ptr [rcx]
0x1800c01f1  test    ax, ax
0x1800c01f4  jnz     short loc_1800C01CF
0x1800c01f6  lea     rdx, [rbp+40h+SubStr]; SubStr
0x1800c01fa  lea     rcx, [rsp+140h+Str]; Str
0x1800c01ff  call    cs:__imp_wcsstr
0x1800c0205  xor     r10d, r10d
0x1800c0208  test    rax, rax
0x1800c020b  jnz     short loc_1800C0244
0x1800c020d  lea     r8, [rsp+140h+Context]; Context
0x1800c0212  xor     ecx, ecx; String
0x1800c0214  lea     rdx, Delimiter; ";"
0x1800c021b  call    _o_wcstok_s_0
0x1800c0220  xor     r10d, r10d
0x1800c0223  test    rax, rax
0x1800c0226  jnz     loc_1800C016D
0x1800c022c  mov     r15, [rsp+140h+var_E0]
0x1800c0231  mov     r14, [rsp+140h+var_E8]
0x1800c0236  cmp     [rbp+40h+String], r10w
0x1800c023b  jnz     short loc_1800C02AE
0x1800c023d  mov     ebx, edi
0x1800c023f  jmp     loc_1800C0346
0x1800c0244  lea     rdx, [rbp+40h+String]
0x1800c0248  test    r15, r15
0x1800c024b  jz      short loc_1800C0269
0x1800c024d  movzx   eax, word ptr [r14]
0x1800c0251  test    ax, ax
0x1800c0254  jz      short loc_1800C0269
0x1800c0256  mov     [rdx], ax
0x1800c0259  add     r14, 2
0x1800c025d  add     rdx, 2
0x1800c0261  sub     r15, rdi
0x1800c0264  sub     rsi, rdi
0x1800c0267  jnz     short loc_1800C0248
0x1800c0269  mov     rax, rsi
0x1800c026c  lea     rcx, [rdx-2]
0x1800c0270  neg     rax
0x1800c0273  sbb     ebx, ebx
0x1800c0275  not     ebx
0x1800c0277  and     ebx, 8007007Ah
0x1800c027d  test    rsi, rsi
0x1800c0280  cmovnz  rcx, rdx
0x1800c0284  mov     [rcx], r10w
0x1800c0288  jnz     short loc_1800C022C
0x1800c028a  lea     r9, aStringcchcopyw; "StringCchCopyW failed [%#x]"
0x1800c0291  mov     r8d, 43Bh
0x1800c0297  jmp     loc_1800C0334
0x1800c029c  lea     r9, aStringcchcopyw; "StringCchCopyW failed [%#x]"
0x1800c02a3  mov     r8d, 417h
0x1800c02a9  jmp     loc_1800C0334
0x1800c02ae  lea     rcx, [rbp+40h+String]; String
0x1800c02b2  call    cs:__imp__wtoi64
0x1800c02b8  mov     rdx, rax
0x1800c02bb  mov     rax, 1F7E33BE0D39C00h
0x1800c02c5  cmp     rdx, rax
0x1800c02c8  ja      short loc_1800C0322
0x1800c02ca  xor     r8d, r8d
0x1800c02cd  test    rdx, rdx
0x1800c02d0  setz    cl
0x1800c02d3  mov     [r13+0], cl
0x1800c02d7  test    rdx, rdx
0x1800c02da  jz      short loc_1800C02E1
0x1800c02dc  cmp     rdx, r15
0x1800c02df  jb      short loc_1800C02E4
0x1800c02e1  mov     dil, r8b
0x1800c02e4  mov     ecx, r8d
0x1800c02e7  mov     [r14], dil
0x1800c02ea  cmp     [r13+0], r8b
0x1800c02ee  lea     r9, aOnesettingsMat; "OneSettings match was found:%I64u. Kill"...
0x1800c02f5  movzx   eax, dil
0x1800c02f9  mov     r8d, 457h
0x1800c02ff  setnz   cl
0x1800c0302  mov     dword ptr [rsp+140h+pcbData], eax
0x1800c0306  mov     dword ptr [rsp+140h+pvData], ecx
0x1800c030a  mov     ecx, 3
0x1800c030f  mov     [rsp+140h+pdwType], rdx
0x1800c0314  lea     rdx, aTelemetryprovi_12; "TelemetryProvider::IsValidFromOneSettin"...
0x1800c031b  call    AslLogCallPrintf
0x1800c0320  jmp     short loc_1800C0346
0x1800c0322  mov     ebx, 8000FFFFh
0x1800c0327  lea     r9, aOnesettingsEol; "OneSettings EoL match found but invalid"...
0x1800c032e  mov     r8d, 44Ch
0x1800c0334  mov     dword ptr [rsp+140h+pdwType], ebx
0x1800c0338  mov     ecx, edi
0x1800c033a  lea     rdx, aTelemetryprovi_12; "TelemetryProvider::IsValidFromOneSettin"...
0x1800c0341  call    AslLogCallPrintf
0x1800c0346  mov     rcx, r12; void *
0x1800c0349  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c034e  mov     eax, ebx
0x1800c0350  mov     rcx, [rbp+40h+var_40]
0x1800c0354  xor     rcx, rsp; StackCookie
0x1800c0357  call    __security_check_cookie
0x1800c035c  mov     rbx, [rsp+140h+arg_10]
0x1800c0364  add     rsp, 110h
0x1800c036b  pop     r15
0x1800c036d  pop     r14
0x1800c036f  pop     r13
0x1800c0371  pop     r12
0x1800c0373  pop     rdi
0x1800c0374  pop     rsi
0x1800c0375  pop     rbp
0x1800c0376  retn
```
