# RequiredLanguageFeaturesInstaller::GetFeatureToInstallState(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,PayloadType)

- ea: `0x1800178e0`
- end: `0x180017a78`
- name: `?GetFeatureToInstallState@RequiredLanguageFeaturesInstaller@@CA?AW4RequestedInstallationState@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PayloadType@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(_QWORD *Src, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180013c74`

## callees

- `0x180003520`
- `0x180004100`
- `0x1800058dc`
- `0x180006380`
- `0x18000a844`
- `0x1800178e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017a2d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017a2d`

## string_xrefs

- `0x1800179ea`: `FeaturesToInstall`

## pseudocode

```c
__int64 __fastcall RequiredLanguageFeaturesInstaller::GetFeatureToInstallState(_QWORD *Src, int a2)
{
  __int64 v2; // r14
  _QWORD *v3; // rbx
  __int64 v4; // rcx
  __int64 v6; // rsi
  __int64 v7; // rax
  WCHAR *v8; // rdi
  const WCHAR *v9; // rdx
  int v10; // ebx
  __int64 v12; // [rsp+40h] [rbp-19h] BYREF
  int pvData; // [rsp+48h] [rbp-11h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-Dh] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-9h] BYREF
  __int128 v16; // [rsp+60h] [rbp+7h]

  v2 = Src[2];
  v3 = Src;
  v4 = 0x7FFFFFFFFFFFFFFELL;
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v2) < 0x29 )
    std::_Xlen_string();
  if ( v3[3] > 7u )
    v3 = (_QWORD *)*v3;
  v6 = v2 + 41;
  v7 = 7;
  *(_OWORD *)lpSubKey = 0;
  v16 = 0;
  if ( (unsigned __int64)(v2 + 41) <= 7 )
  {
    v8 = (WCHAR *)lpSubKey;
  }
  else
  {
    if ( (v6 | 7uLL) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v4 = v6 | 7;
      if ( (v6 | 7uLL) < 0xA )
        v4 = 10;
    }
    v12 = v4;
    v8 = (WCHAR *)std::wstring::_Allocate_for_capacity<0>(v4, &v12);
    lpSubKey[0] = v8;
    v7 = v12;
  }
  *((_QWORD *)&v16 + 1) = v7;
  *(_QWORD *)&v16 = v2 + 41;
  *(_OWORD *)v8 = *(_OWORD *)L"Control Panel\\International\\User Profile\\";
  *((_OWORD *)v8 + 1) = *(_OWORD *)L"Panel\\International\\User Profile\\";
  *((_OWORD *)v8 + 2) = *(_OWORD *)L"ternational\\User Profile\\";
  *((_OWORD *)v8 + 3) = *(_OWORD *)L"nal\\User Profile\\";
  *((_OWORD *)v8 + 4) = *(_OWORD *)L" Profile\\";
  v8[40] = aControlPanelIn[40];
  memcpy_0(v8 + 41, v3, 2 * v2);
  v9 = (const WCHAR *)lpSubKey;
  v8[v6] = 0;
  pvData = 0;
  if ( *((_QWORD *)&v16 + 1) > 7u )
    v9 = lpSubKey[0];
  pcbData = 4;
  if ( RegGetValueW(HKEY_CURRENT_USER, v9, L"FeaturesToInstall", 0x10u, 0, &pvData, &pcbData) )
  {
    std::wstring::~wstring((char **)lpSubKey);
    return 0;
  }
  else
  {
    v10 = -((a2 & pvData) != 0);
    std::wstring::~wstring((char **)lpSubKey);
    return (unsigned int)(v10 + 2);
  }
}

```

## disassembly

```asm
0x1800178e0  push    rbp
0x1800178e2  push    rbx
0x1800178e3  push    rsi
0x1800178e4  push    rdi
0x1800178e5  push    r14
0x1800178e7  push    r15
0x1800178e9  lea     rbp, [rsp-2Fh]
0x1800178ee  sub     rsp, 88h
0x1800178f5  mov     rax, cs:__security_cookie
0x1800178fc  xor     rax, rsp
0x1800178ff  mov     [rbp+57h+var_40], rax
0x180017903  mov     r14, [rcx+10h]
0x180017907  mov     rbx, rcx
0x18001790a  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180017914  mov     r15d, edx
0x180017917  mov     rax, rcx
0x18001791a  sub     rax, r14
0x18001791d  cmp     rax, 29h ; ')'
0x180017921  jb      loc_180017A72
0x180017927  cmp     qword ptr [rbx+18h], 7
0x18001792c  jbe     short loc_180017931
0x18001792e  mov     rbx, [rbx]
0x180017931  lea     rsi, [r14+29h]
0x180017935  mov     eax, 7
0x18001793a  xorps   xmm0, xmm0
0x18001793d  xorps   xmm1, xmm1
0x180017940  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x180017944  movdqu  [rbp+57h+var_50], xmm1
0x180017949  cmp     rsi, rax
0x18001794c  jbe     short loc_180017983
0x18001794e  mov     rax, rsi
0x180017951  or      rax, 7
0x180017955  cmp     rax, rcx
0x180017958  ja      short loc_180017969
0x18001795a  mov     edx, 0Ah
0x18001795f  mov     rcx, rax
0x180017962  cmp     rax, rdx
0x180017965  cmovb   rcx, rdx
0x180017969  lea     rdx, [rbp+57h+var_70]
0x18001796d  mov     [rbp+57h+var_70], rcx
0x180017971  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180017976  mov     rdi, rax
0x180017979  mov     [rbp+57h+lpSubKey], rax
0x18001797d  mov     rax, [rbp+57h+var_70]
0x180017981  jmp     short loc_180017987
0x180017983  lea     rdi, [rbp+57h+lpSubKey]
0x180017987  movaps  xmm0, xmmword ptr cs:aControlPanelIn; "Control Panel\\International\\User Prof"...
0x18001798e  lea     r8, [r14+r14]; Size
0x180017992  mov     qword ptr [rbp+57h+var_50+8], rax
0x180017996  lea     rcx, [rdi+52h]; void *
0x18001799a  mov     qword ptr [rbp+57h+var_50], rsi
0x18001799e  mov     rdx, rbx; Src
0x1800179a1  movups  xmmword ptr [rdi], xmm0
0x1800179a4  movaps  xmm1, xmmword ptr cs:aControlPanelIn+10h; "Panel\\International\\User Profile\\"
0x1800179ab  movups  xmmword ptr [rdi+10h], xmm1
0x1800179af  movaps  xmm0, xmmword ptr cs:aControlPanelIn+20h; "ternational\\User Profile\\"
0x1800179b6  movups  xmmword ptr [rdi+20h], xmm0
0x1800179ba  movaps  xmm1, xmmword ptr cs:aControlPanelIn+30h; "nal\\User Profile\\"
0x1800179c1  movups  xmmword ptr [rdi+30h], xmm1
0x1800179c5  movaps  xmm0, xmmword ptr cs:aControlPanelIn+40h; " Profile\\"
0x1800179cc  movups  xmmword ptr [rdi+40h], xmm0
0x1800179d0  movzx   eax, word ptr cs:aControlPanelIn+50h; "\\"
0x1800179d7  mov     [rdi+50h], ax
0x1800179db  call    memcpy_0
0x1800179e0  xor     eax, eax
0x1800179e2  lea     rdx, [rbp+57h+lpSubKey]
0x1800179e6  mov     [rdi+rsi*2], ax
0x1800179ea  lea     r8, aFeaturestoinst; "FeaturesToInstall"
0x1800179f1  cmp     qword ptr [rbp+57h+var_50+8], 7
0x1800179f6  mov     r9d, 10h; dwFlags
0x1800179fc  mov     [rbp+57h+var_68], eax
0x1800179ff  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180017a06  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180017a0b  lea     rax, [rbp+57h+var_64]
0x180017a0f  mov     [rsp+0B0h+pcbData], rax; pcbData
0x180017a14  lea     rax, [rbp+57h+var_68]
0x180017a18  mov     [rsp+0B0h+pvData], rax; pvData
0x180017a1d  mov     [rsp+0B0h+pdwType], 0; pdwType
0x180017a26  mov     [rbp+57h+var_64], 4
0x180017a2d  call    cs:__imp_RegGetValueW
0x180017a33  lea     rcx, [rbp+57h+lpSubKey]; void *
0x180017a37  test    eax, eax
0x180017a39  jnz     short loc_180017A4F
0x180017a3b  mov     eax, [rbp+57h+var_68]
0x180017a3e  and     eax, r15d
0x180017a41  neg     eax
0x180017a43  sbb     ebx, ebx
0x180017a45  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017a4a  lea     eax, [rbx+2]
0x180017a4d  jmp     short loc_180017A56
0x180017a4f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017a54  xor     eax, eax
0x180017a56  mov     rcx, [rbp+57h+var_40]
0x180017a5a  xor     rcx, rsp; StackCookie
0x180017a5d  call    __security_check_cookie
0x180017a62  add     rsp, 88h
0x180017a69  pop     r15
0x180017a6b  pop     r14
0x180017a6d  pop     rdi
0x180017a6e  pop     rsi
0x180017a6f  pop     rbx
0x180017a70  pop     rbp
0x180017a71  retn
0x180017a72  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
