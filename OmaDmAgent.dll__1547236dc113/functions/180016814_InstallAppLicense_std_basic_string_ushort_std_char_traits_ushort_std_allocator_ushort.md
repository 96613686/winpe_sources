# InstallAppLicense(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180016814`
- end: `0x1800169b1`
- name: `?InstallAppLicense@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180010700`

## callees

- `0x1800062ac`
- `0x18000a290`
- `0x18000a2c0`
- `0x180015154`
- `0x180016814`

## import_xrefs

- `WSClient!WSLicenseClose` at `0x18001698b`
- `WSClient!WSLicenseClose` at `0x18001698b`
- `WSClient!WSLicenseInstallLicense` at `0x180016930`
- `WSClient!WSLicenseInstallLicense` at `0x180016930`
- `WSClient!WSLicenseOpen` at `0x1800168f4`
- `WSClient!WSLicenseOpen` at `0x1800168f4`

## pseudocode

```c
__int64 __fastcall InstallAppLicense(const WCHAR *lpWideCharStr)
{
  const WCHAR *v2; // rcx
  int v3; // eax
  __int64 v4; // rdx
  unsigned int v5; // ebx
  LPCWSTR v6; // rcx
  __int64 v7; // rdx
  __int64 v9; // [rsp+28h] [rbp-40h] BYREF
  __int64 v10; // [rsp+30h] [rbp-38h]

  v9 = 0;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
      *((unsigned int *)lpWideCharStr + 4));
  if ( *((_QWORD *)lpWideCharStr + 3) < 8u )
    v2 = lpWideCharStr;
  else
    v2 = *(const WCHAR **)lpWideCharStr;
  v3 = ConvertToUTF8(v2);
  v5 = v3;
  if ( v3 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_17887b334fcf349edf3df6ab34803119_Traceguids, 0);
    v3 = WSLicenseOpen(&v9);
    v5 = v3;
    if ( v3 >= 0 )
    {
      v3 = WSLicenseInstallLicense(v9, 0, v10, 0);
      v5 = v3;
      if ( v3 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_17887b334fcf349edf3df6ab34803119_Traceguids);
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          v7 = 14;
          goto LABEL_11;
        }
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v7 = 13;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v7 = 11;
LABEL_11:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, &WPP_17887b334fcf349edf3df6ab34803119_Traceguids, (unsigned int)v3);
    }
  }
  if ( v9 )
    WSLicenseClose();
  LOBYTE(v4) = 1;
  std::wstring::_Tidy(lpWideCharStr, v4, 0);
  return v5;
}

```

## disassembly

```asm
0x180016814  push    rbx
0x180016816  push    rsi
0x180016817  push    rdi
0x180016818  push    r14
0x18001681a  sub     rsp, 48h
0x18001681e  mov     rdi, rcx
0x180016821  mov     [rsp+68h+var_40], 0
0x18001682a  mov     [rsp+68h+var_48], 0
0x180016832  mov     [rsp+68h+var_38], 0
0x18001683b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016842  lea     rsi, WPP_GLOBAL_Control
0x180016849  lea     r14, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180016850  cmp     rcx, rsi
0x180016853  jz      short loc_180016870
0x180016855  test    byte ptr [rcx+1Ch], 1
0x180016859  jz      short loc_180016870
0x18001685b  mov     r9d, [rdi+10h]
0x18001685f  mov     edx, 0Ah
0x180016864  mov     rcx, [rcx+10h]
0x180016868  mov     r8, r14
0x18001686b  call    WPP_SF_d
0x180016870  cmp     qword ptr [rdi+18h], 8
0x180016875  jb      short loc_18001687C
0x180016877  mov     rcx, [rdi]
0x18001687a  jmp     short loc_18001687F
0x18001687c  mov     rcx, rdi; lpWideCharStr
0x18001687f  lea     r8, [rsp+68h+var_48]
0x180016884  lea     rdx, [rsp+68h+var_38]
0x180016889  call    ConvertToUTF8
0x18001688e  mov     ebx, eax
0x180016890  test    eax, eax
0x180016892  jns     short loc_1800168C7
0x180016894  mov     rcx, cs:WPP_GLOBAL_Control
0x18001689b  cmp     rcx, rsi
0x18001689e  jz      loc_180016981
0x1800168a4  test    byte ptr [rcx+1Ch], 4
0x1800168a8  jz      loc_180016981
0x1800168ae  mov     edx, 0Bh
0x1800168b3  mov     rcx, [rcx+10h]
0x1800168b7  mov     r9d, eax
0x1800168ba  mov     r8, r14
0x1800168bd  call    WPP_SF_d
0x1800168c2  jmp     loc_180016981
0x1800168c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168ce  cmp     rcx, rsi
0x1800168d1  jz      short loc_1800168EF
0x1800168d3  test    byte ptr [rcx+1Ch], 1
0x1800168d7  jz      short loc_1800168EF
0x1800168d9  mov     r9d, [rsp+68h+var_48]
0x1800168de  mov     edx, 0Ch
0x1800168e3  mov     rcx, [rcx+10h]
0x1800168e7  mov     r8, r14
0x1800168ea  call    WPP_SF_d
0x1800168ef  lea     rcx, [rsp+68h+var_40]
0x1800168f4  call    cs:__imp_WSLicenseOpen
0x1800168fb  nop     dword ptr [rax+rax+00h]
0x180016900  mov     ebx, eax
0x180016902  test    eax, eax
0x180016904  jns     short loc_18001691F
0x180016906  mov     rcx, cs:WPP_GLOBAL_Control
0x18001690d  cmp     rcx, rsi
0x180016910  jz      short loc_180016981
0x180016912  test    byte ptr [rcx+1Ch], 4
0x180016916  jz      short loc_180016981
0x180016918  mov     edx, 0Dh
0x18001691d  jmp     short loc_1800168B3
0x18001691f  mov     r8, [rsp+68h+var_38]
0x180016924  xor     r9d, r9d
0x180016927  mov     edx, [rsp+68h+var_48]
0x18001692b  mov     rcx, [rsp+68h+var_40]
0x180016930  call    cs:__imp_WSLicenseInstallLicense
0x180016937  nop     dword ptr [rax+rax+00h]
0x18001693c  mov     ebx, eax
0x18001693e  test    eax, eax
0x180016940  jns     short loc_18001695E
0x180016942  mov     rcx, cs:WPP_GLOBAL_Control
0x180016949  cmp     rcx, rsi
0x18001694c  jz      short loc_180016981
0x18001694e  test    byte ptr [rcx+1Ch], 4
0x180016952  jz      short loc_180016981
0x180016954  mov     edx, 0Eh
0x180016959  jmp     loc_1800168B3
0x18001695e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016965  cmp     rcx, rsi
0x180016968  jz      short loc_180016981
0x18001696a  test    byte ptr [rcx+1Ch], 1
0x18001696e  jz      short loc_180016981
0x180016970  mov     rcx, [rcx+10h]
0x180016974  mov     edx, 0Fh
0x180016979  mov     r8, r14
0x18001697c  call    WPP_SF_
0x180016981  mov     rcx, [rsp+68h+var_40]
0x180016986  test    rcx, rcx
0x180016989  jz      short loc_180016997
0x18001698b  call    cs:__imp_WSLicenseClose
0x180016992  nop     dword ptr [rax+rax+00h]
0x180016997  xor     r8d, r8d
0x18001699a  mov     dl, 1
0x18001699c  mov     rcx, rdi
0x18001699f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800169a4  mov     eax, ebx
0x1800169a6  add     rsp, 48h
0x1800169aa  pop     r14
0x1800169ac  pop     rdi
0x1800169ad  pop     rsi
0x1800169ae  pop     rbx
0x1800169af  retn
```
