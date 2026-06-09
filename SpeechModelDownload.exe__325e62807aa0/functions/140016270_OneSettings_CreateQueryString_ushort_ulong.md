# OneSettings::CreateQueryString(ushort *,ulong)

- ea: `0x140016270`
- end: `0x140016750`
- name: `?CreateQueryString@OneSettings@@AEAAJPEAGK@Z`
- size: `1248`
- prototype: `__int64 __fastcall(OneSettings *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x140018534`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x1400138c8`
- `0x140013a2c`
- `0x1400146e4`
- `0x1400148e0`
- `0x140014e98`
- `0x140016270`
- `0x140019c34`
- `0x14001a4e4`
- `0x14001bba8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400166ae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400166ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140016704`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140016704`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016714`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016714`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001642a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140016652`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001642a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140016652`

## string_xrefs

- `0x14001641c`: `NamespaceExtension`

## pseudocode

```c
__int64 __fastcall OneSettings::CreateQueryString(OneSettings *this, unsigned __int16 *a2)
{
  __int64 v4; // r15
  int v5; // esi
  _QWORD *v6; // rcx
  _QWORD *v7; // rax
  __int64 *v8; // rbx
  const wchar_t *v9; // rdx
  const wchar_t *v10; // rcx
  const WCHAR *v11; // rdx
  LSTATUS ValueW; // eax
  __int64 v13; // r8
  bool v14; // sf
  unsigned __int64 v15; // rdx
  void **v16; // rsi
  __int64 v17; // rdi
  void **v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rsi
  BYTE **v21; // rdi
  BYTE **v22; // rcx
  wchar_t **v23; // rax
  __int64 **v24; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  signed int v27; // ebx
  const WCHAR *v28; // rdi
  const WCHAR *v29; // rdx
  LSTATUS v30; // eax
  const BYTE *v31; // rcx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  BYTE *lpData[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v37; // [rsp+78h] [rbp-88h]
  void *v38[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v39; // [rsp+98h] [rbp-68h]
  unsigned __int64 v40; // [rsp+A0h] [rbp-60h]
  wchar_t *S1[2]; // [rsp+B0h] [rbp-50h] BYREF
  size_t N; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v43; // [rsp+C8h] [rbp-38h]
  _BYTE v44[32]; // [rsp+D0h] [rbp-30h] BYREF
  _WORD Src[264]; // [rsp+F0h] [rbp-10h] BYREF

  hKey = (HKEY)a2;
  v35 = 512;
  v4 = -1;
  if ( !*((_QWORD *)this + 25) )
  {
    v5 = -2147418113;
    goto LABEL_57;
  }
  v6 = (_QWORD *)((char *)this + 64);
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  v7 = (_QWORD *)((char *)this + 32);
  if ( *((_QWORD *)this + 7) > 7u )
    v7 = (_QWORD *)*v7;
  v5 = StringCchPrintfExW(
         a2,
         0x200u,
         (unsigned __int16 **)&hKey,
         &v35,
         0x400u,
         L"%ls/%ls/%ls?os=Windows",
         L"settings/v2.0",
         v7,
         v6);
  if ( v5 >= 0 )
  {
    v8 = (__int64 *)***((_QWORD ***)this + 25);
    while ( 1 )
    {
      if ( *((_BYTE *)v8 + 25) )
      {
        v5 = 0;
        break;
      }
      std::wstring::wstring(S1, v8 + 4);
      std::wstring::wstring(v44, v8 + 8);
      std::wstring::wstring(lpData, v44);
      v9 = (const wchar_t *)&OneSettings::DefaultProperties::Namespaces;
      if ( (unsigned __int64)qword_140030AE8 > 7 )
        v9 = OneSettings::DefaultProperties::Namespaces;
      v10 = (const wchar_t *)S1;
      if ( v43 > 7 )
        v10 = S1[0];
      if ( N == qword_140030AE0 && (!N || !wmemcmp(v10, v9, N)) )
      {
        *(_OWORD *)v38 = 0;
        v40 = 7;
        memset_0(Src, 0, 0x208u);
        pcbData = 520;
        v39 = 0;
        LOWORD(v38[0]) = 0;
        v11 = (const WCHAR *)((char *)this + 128);
        if ( *((_QWORD *)this + 19) > 7u )
          v11 = *(const WCHAR **)v11;
        ValueW = RegGetValueW(*((HKEY *)this + 20), v11, L"NamespaceExtension", 2u, 0, Src, &pcbData);
        v14 = ValueW < 0;
        if ( !ValueW )
          goto LABEL_23;
        if ( ValueW > 0 )
          v14 = 1;
        if ( !v14 )
        {
LABEL_23:
          v15 = -1;
          do
            ++v15;
          while ( Src[v15] );
          if ( v15 )
          {
            if ( v15 > v40 )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                v38,
                v15,
                v13,
                Src);
            }
            else
            {
              v16 = v38;
              if ( v40 > 7 )
                v16 = (void **)v38[0];
              v39 = v15;
              v17 = 2 * v15;
              memmove_0(v16, Src, 2 * v15);
              *(_WORD *)((char *)v16 + v17) = 0;
            }
            v18 = v38;
            if ( v40 > 7 )
              v18 = (void **)v38[0];
            v19 = v37;
            if ( (unsigned __int64)v39 > *((_QWORD *)&v37 + 1) - (_QWORD)v37 )
            {
              std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
                lpData,
                v39);
            }
            else
            {
              v20 = v39 + v37;
              *(_QWORD *)&v37 = v39 + v37;
              v21 = lpData;
              if ( *((_QWORD *)&v37 + 1) > 7u )
                v21 = (BYTE **)lpData[0];
              memmove_0((char *)v21 + 2 * v19, v18, 2 * v39);
              *((_WORD *)v21 + v20) = 0;
            }
          }
        }
        v5 = 0;
        std::wstring::~wstring(v38);
      }
      else if ( v5 < 0 )
      {
        goto LABEL_47;
      }
      if ( (_QWORD)v37 )
      {
        v22 = lpData;
        if ( *((_QWORD *)&v37 + 1) > 7u )
          v22 = (BYTE **)lpData[0];
        v23 = S1;
        if ( v43 > 7 )
          v23 = (wchar_t **)S1[0];
        StringCchPrintfExW((wchar_t *)hKey, v35, (unsigned __int16 **)&hKey, &v35, 0x400u, L"&%s=%s", v23, v22);
      }
      else
      {
        v5 = -2147418113;
      }
LABEL_47:
      std::wstring::~wstring(lpData);
      std::wstring::~wstring(v44);
      std::wstring::~wstring(S1);
      v24 = (__int64 **)v8[2];
      if ( *((_BYTE *)v24 + 25) )
      {
        for ( i = (__int64 *)v8[1]; !*((_BYTE *)i + 25) && v8 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v8 = i;
        v8 = i;
      }
      else
      {
        v8 = (__int64 *)v8[2];
        for ( j = *v24; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v8 = j;
      }
    }
  }
LABEL_57:
  *(_OWORD *)lpData = 0;
  v37 = 0;
  do
    ++v4;
  while ( a2[v4] );
  std::wstring::_Construct<1,unsigned short const *>(lpData, a2, v4);
  v27 = 0;
  hKey = 0;
  v28 = (const WCHAR *)((char *)this + 128);
  if ( *((_QWORD *)this + 19) <= 7u )
    v29 = (const WCHAR *)((char *)this + 128);
  else
    v29 = *(const WCHAR **)v28;
  if ( !RegGetValueW(*((HKEY *)this + 20), v29, L"LastUsedQueryString", 2u, 0, 0, 0) )
  {
    if ( *((_QWORD *)this + 19) > 7u )
      v28 = *(const WCHAR **)v28;
    v30 = RegCreateKeyExW(*((HKEY *)this + 20), v28, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v30 )
    {
      if ( v30 > 0 )
        v27 = (unsigned __int16)v30 | 0x80070000;
      else
        v27 = v30;
    }
    if ( v27 >= 0 )
    {
      v31 = (const BYTE *)lpData;
      if ( *((_QWORD *)&v37 + 1) > 7u )
        v31 = lpData[0];
      RegSetValueExW(hKey, L"LastUsedQueryString", 0, 1u, v31, 2 * v37 + 2);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(lpData);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140016270  mov     [rsp-8+arg_10], rbx
0x140016275  push    rbp
0x140016276  push    rsi
0x140016277  push    rdi
0x140016278  push    r12
0x14001627a  push    r13
0x14001627c  push    r14
0x14001627e  push    r15
0x140016280  lea     rbp, [rsp-210h]
0x140016288  sub     rsp, 310h
0x14001628f  mov     rax, cs:__security_cookie
0x140016296  xor     rax, rsp
0x140016299  mov     [rbp+240h+var_40], rax
0x1400162a0  mov     r12, rdx
0x1400162a3  mov     r14, rcx
0x1400162a6  mov     [rsp+340h+hKey], rdx
0x1400162ab  mov     edx, 200h; unsigned __int64
0x1400162b0  mov     [rsp+340h+var_2E0], rdx
0x1400162b5  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400162b9  xor     r13d, r13d
0x1400162bc  cmp     [rcx+0C8h], r13
0x1400162c3  jnz     short loc_1400162CF
0x1400162c5  mov     esi, 8000FFFFh
0x1400162ca  jmp     loc_1400165E6
0x1400162cf  add     rcx, 40h ; '@'
0x1400162d3  cmp     qword ptr [rcx+18h], 7
0x1400162d8  jbe     short loc_1400162DD
0x1400162da  mov     rcx, [rcx]
0x1400162dd  lea     rax, [r14+20h]
0x1400162e1  cmp     qword ptr [rax+18h], 7
0x1400162e6  jbe     short loc_1400162EB
0x1400162e8  mov     rax, [rax]
0x1400162eb  mov     [rsp+340h+lpdwDisposition], rcx
0x1400162f0  mov     [rsp+340h+phkResult], rax
0x1400162f5  lea     rax, aSettingsV20; "settings/v2.0"
0x1400162fc  mov     [rsp+340h+pcbData], rax
0x140016301  lea     rax, aLsLsLsOsWindow; "%ls/%ls/%ls?os=Windows"
0x140016308  mov     [rsp+340h+pvData], rax; unsigned __int16 *
0x14001630d  mov     dword ptr [rsp+340h+pdwType], 400h; unsigned int
0x140016315  lea     r9, [rsp+340h+var_2E0]; unsigned __int64 *
0x14001631a  lea     r8, [rsp+340h+hKey]; unsigned __int16 **
0x14001631f  mov     rcx, r12; Buffer
0x140016322  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x140016327  mov     esi, eax
0x140016329  test    eax, eax
0x14001632b  js      loc_1400165E6
0x140016331  mov     rcx, [r14+0C8h]
0x140016338  mov     rbx, [rcx]
0x14001633b  mov     rbx, [rbx]
0x14001633e  cmp     [rbx+19h], r13b
0x140016342  jnz     loc_1400165E3
0x140016348  lea     rdx, [rbx+20h]
0x14001634c  lea     rcx, [rbp+240h+S1]
0x140016350  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140016355  nop
0x140016356  lea     rdx, [rbx+40h]
0x14001635a  lea     rcx, [rbp+240h+var_270]
0x14001635e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140016363  nop
0x140016364  lea     rdx, [rbp+240h+var_270]
0x140016368  lea     rcx, [rsp+340h+lpData]
0x14001636d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140016372  nop
0x140016373  lea     rdx, ?Namespaces@DefaultProperties@OneSettings@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const OneSettings::DefaultProperties::Namespaces
0x14001637a  cmp     cs:qword_140030AE8, 7
0x140016382  cmova   rdx, cs:?Namespaces@DefaultProperties@OneSettings@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; S2
0x14001638a  mov     r8, [rbp+240h+N]; N
0x14001638e  lea     rcx, [rbp+240h+S1]
0x140016392  cmp     [rbp+240h+var_278], 7
0x140016397  cmova   rcx, [rbp+240h+S1]; S1
0x14001639c  cmp     r8, cs:qword_140030AE0
0x1400163a3  jnz     loc_14001650F
0x1400163a9  test    r8, r8
0x1400163ac  jz      short loc_1400163BB
0x1400163ae  call    wmemcmp
0x1400163b3  test    eax, eax
0x1400163b5  jnz     loc_14001650F
0x1400163bb  xorps   xmm0, xmm0
0x1400163be  movups  xmmword ptr [rbp+240h+var_2B8], xmm0
0x1400163c2  mov     [rbp+240h+var_2A0], 7
0x1400163ca  mov     edi, 208h
0x1400163cf  mov     r8d, edi; Size
0x1400163d2  xor     edx, edx; Val
0x1400163d4  lea     rcx, [rbp+240h+Src]; void *
0x1400163d8  call    memset_0
0x1400163dd  mov     [rsp+340h+var_2E8], edi
0x1400163e1  mov     [rbp+240h+var_2A8], r13
0x1400163e5  mov     word ptr [rbp+240h+var_2B8], r13w
0x1400163ea  lea     rdx, [r14+80h]
0x1400163f1  cmp     qword ptr [r14+98h], 7
0x1400163f9  jbe     short loc_1400163FE
0x1400163fb  mov     rdx, [rdx]; lpSubKey
0x1400163fe  lea     rax, [rsp+340h+var_2E8]
0x140016403  mov     [rsp+340h+pcbData], rax; pcbData
0x140016408  lea     rax, [rbp+240h+Src]
0x14001640c  mov     [rsp+340h+pvData], rax; pvData
0x140016411  mov     [rsp+340h+pdwType], r13; pdwType
0x140016416  mov     r9d, 2; dwFlags
0x14001641c  lea     r8, aNamespaceexten; "NamespaceExtension"
0x140016423  mov     rcx, [r14+0A0h]; hkey
0x14001642a  call    cs:__imp_RegGetValueW
0x140016430  test    eax, eax
0x140016432  jz      short loc_140016446
0x140016434  jle     short loc_140016440
0x140016436  movzx   eax, ax
0x140016439  or      eax, 80070000h
0x14001643e  test    eax, eax
0x140016440  js      loc_140016501
0x140016446  lea     rax, [rbp+240h+Src]
0x14001644a  mov     rdx, r15
0x14001644d  inc     rdx
0x140016450  cmp     [rax+rdx*2], r13w
0x140016455  jnz     short loc_14001644D
0x140016457  test    rdx, rdx
0x14001645a  jz      loc_140016501
0x140016460  cmp     rdx, [rbp+240h+var_2A0]
0x140016464  ja      short loc_140016492
0x140016466  lea     rsi, [rbp+240h+var_2B8]
0x14001646a  cmp     [rbp+240h+var_2A0], 7
0x14001646f  cmova   rsi, [rbp+240h+var_2B8]
0x140016474  mov     [rbp+240h+var_2A8], rdx
0x140016478  lea     rdi, [rdx+rdx]
0x14001647c  mov     r8, rdi; Size
0x14001647f  lea     rdx, [rbp+240h+Src]; Src
0x140016483  mov     rcx, rsi; void *
0x140016486  call    memmove_0
0x14001648b  mov     [rsi+rdi], r13w
0x140016490  jmp     short loc_14001649F
0x140016492  lea     r9, [rbp+240h+Src]
0x140016496  lea     rcx, [rbp+240h+var_2B8]
0x14001649a  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14001649f  mov     rdx, [rbp+240h+var_2A8]
0x1400164a3  lea     r9, [rbp+240h+var_2B8]
0x1400164a7  cmp     [rbp+240h+var_2A0], 7
0x1400164ac  cmova   r9, [rbp+240h+var_2B8]
0x1400164b1  mov     rcx, qword ptr [rsp+340h+var_2C8]
0x1400164b6  mov     rax, qword ptr [rbp+240h+var_2C8+8]
0x1400164ba  sub     rax, rcx
0x1400164bd  cmp     rdx, rax
0x1400164c0  ja      short loc_1400164F2
0x1400164c2  lea     rsi, [rdx+rcx]
0x1400164c6  mov     qword ptr [rsp+340h+var_2C8], rsi
0x1400164cb  lea     rdi, [rsp+340h+lpData]
0x1400164d0  cmp     qword ptr [rbp+240h+var_2C8+8], 7
0x1400164d5  cmova   rdi, [rsp+340h+lpData]
0x1400164db  lea     r8, [rdx+rdx]; Size
0x1400164df  lea     rcx, [rdi+rcx*2]; void *
0x1400164e3  mov     rdx, r9; Src
0x1400164e6  call    memmove_0
0x1400164eb  mov     [rdi+rsi*2], r13w
0x1400164f0  jmp     short loc_140016501
0x1400164f2  mov     [rsp+340h+pdwType], rdx; __int64
0x1400164f7  lea     rcx, [rsp+340h+lpData]; Src
0x1400164fc  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x140016501  mov     esi, r13d
0x140016504  lea     rcx, [rbp+240h+var_2B8]
0x140016508  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001650d  jmp     short loc_140016513
0x14001650f  test    esi, esi
0x140016511  js      short loc_140016577
0x140016513  cmp     qword ptr [rsp+340h+var_2C8], r13
0x140016518  jnz     short loc_140016521
0x14001651a  mov     esi, 8000FFFFh
0x14001651f  jmp     short loc_140016577
0x140016521  lea     rcx, [rsp+340h+lpData]
0x140016526  cmp     qword ptr [rbp+240h+var_2C8+8], 7
0x14001652b  cmova   rcx, [rsp+340h+lpData]
0x140016531  lea     rax, [rbp+240h+S1]
0x140016535  cmp     [rbp+240h+var_278], 7
0x14001653a  cmova   rax, [rbp+240h+S1]
0x14001653f  mov     [rsp+340h+phkResult], rcx
0x140016544  mov     [rsp+340h+pcbData], rax
0x140016549  lea     rax, aSS_0; "&%s=%s"
0x140016550  mov     [rsp+340h+pvData], rax; unsigned __int16 *
0x140016555  mov     dword ptr [rsp+340h+pdwType], 400h; unsigned int
0x14001655d  lea     r9, [rsp+340h+var_2E0]; unsigned __int64 *
0x140016562  lea     r8, [rsp+340h+hKey]; unsigned __int16 **
0x140016567  mov     rdx, [rsp+340h+var_2E0]; unsigned __int64
0x14001656c  mov     rcx, [rsp+340h+hKey]; Buffer
0x140016571  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x140016576  nop
0x140016577  lea     rcx, [rsp+340h+lpData]
0x14001657c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140016581  nop
0x140016582  lea     rcx, [rbp+240h+var_270]
0x140016586  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001658b  lea     rcx, [rbp+240h+S1]
0x14001658f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140016594  mov     rcx, [rbx+10h]
0x140016598  cmp     [rcx+19h], r13b
0x14001659c  jz      short loc_1400165BF
0x14001659e  mov     rax, [rbx+8]
0x1400165a2  jmp     short loc_1400165B1
0x1400165a4  cmp     rbx, [rax+10h]
0x1400165a8  jnz     short loc_1400165B7
0x1400165aa  mov     rbx, rax
0x1400165ad  mov     rax, [rax+8]
0x1400165b1  cmp     [rax+19h], r13b
0x1400165b5  jz      short loc_1400165A4
0x1400165b7  mov     rbx, rax
0x1400165ba  jmp     loc_14001633E
0x1400165bf  mov     rbx, rcx
0x1400165c2  mov     rcx, [rcx]
0x1400165c5  cmp     [rcx+19h], r13b
0x1400165c9  jnz     loc_14001633E
0x1400165cf  mov     rbx, rcx
0x1400165d2  mov     rax, [rcx]
0x1400165d5  mov     rcx, rax
0x1400165d8  cmp     [rax+19h], r13b
0x1400165dc  jz      short loc_1400165CF
0x1400165de  jmp     loc_14001633E
0x1400165e3  mov     esi, r13d
0x1400165e6  xorps   xmm0, xmm0
0x1400165e9  movups  xmmword ptr [rsp+340h+lpData], xmm0
0x1400165ee  xorps   xmm1, xmm1
0x1400165f1  movdqu  [rsp+340h+var_2C8], xmm1
0x1400165f7  inc     r15
0x1400165fa  cmp     [r12+r15*2], r13w
0x1400165ff  jnz     short loc_1400165F7
0x140016601  mov     r8, r15
0x140016604  mov     rdx, r12
0x140016607  lea     rcx, [rsp+340h+lpData]
0x14001660c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140016611  mov     ebx, r13d
0x140016614  mov     [rsp+340h+hKey], r13
0x140016619  lea     rdi, [r14+80h]
0x140016620  cmp     qword ptr [rdi+18h], 7
0x140016625  jbe     short loc_14001662C
0x140016627  mov     rdx, [rdi]
0x14001662a  jmp     short loc_14001662F
0x14001662c  mov     rdx, rdi; lpSubKey
0x14001662f  mov     [rsp+340h+pcbData], r13; pcbData
0x140016634  mov     [rsp+340h+pvData], r13; pvData
0x140016639  mov     [rsp+340h+pdwType], r13; pdwType
0x14001663e  mov     r9d, 2; dwFlags
0x140016644  lea     r8, aLastusedquerys; "LastUsedQueryString"
0x14001664b  mov     rcx, [r14+0A0h]; hkey
0x140016652  call    cs:__imp_RegGetValueW
0x140016658  test    eax, eax
0x14001665a  jz      short loc_140016673
0x14001665c  jg      short loc_140016662
0x14001665e  mov     ebx, eax
0x140016660  jmp     short loc_14001666B
0x140016662  movzx   ebx, ax
0x140016665  or      ebx, 80070000h
0x14001666b  test    ebx, ebx
0x14001666d  js      loc_14001670A
0x140016673  cmp     qword ptr [rdi+18h], 7
0x140016678  jbe     short loc_14001667D
0x14001667a  mov     rdi, [rdi]
0x14001667d  mov     [rsp+340h+lpdwDisposition], r13; lpdwDisposition
0x140016682  lea     rax, [rsp+340h+hKey]
0x140016687  mov     [rsp+340h+phkResult], rax; phkResult
0x14001668c  mov     [rsp+340h+pcbData], r13; lpSecurityAttributes
0x140016691  mov     dword ptr [rsp+340h+pvData], 0F003Fh; samDesired
0x140016699  mov     dword ptr [rsp+340h+pdwType], r13d; dwOptions
0x14001669e  xor     r9d, r9d; lpClass
0x1400166a1  xor     r8d, r8d; Reserved
0x1400166a4  mov     rdx, rdi; lpSubKey
0x1400166a7  mov     rcx, [r14+0A0h]; hKey
0x1400166ae  call    cs:__imp_RegCreateKeyExW
0x1400166b4  test    eax, eax
0x1400166b6  jz      short loc_1400166C7
0x1400166b8  jg      short loc_1400166BE
0x1400166ba  mov     ebx, eax
0x1400166bc  jmp     short loc_1400166C7
0x1400166be  movzx   ebx, ax
0x1400166c1  or      ebx, 80070000h
0x1400166c7  test    ebx, ebx
0x1400166c9  js      short loc_14001670A
0x1400166cb  mov     eax, dword ptr [rsp+340h+var_2C8]
0x1400166cf  lea     rcx, [rsp+340h+lpData]
0x1400166d4  cmp     qword ptr [rbp+240h+var_2C8+8], 7
0x1400166d9  cmova   rcx, [rsp+340h+lpData]
0x1400166df  lea     eax, ds:2[rax*2]
0x1400166e6  mov     dword ptr [rsp+340h+pvData], eax; cbData
0x1400166ea  mov     [rsp+340h+pdwType], rcx; lpData
0x1400166ef  mov     r9d, 1; dwType
0x1400166f5  xor     r8d, r8d; Reserved
0x1400166f8  lea     rdx, aLastusedquerys; "LastUsedQueryString"
0x1400166ff  mov     rcx, [rsp+340h+hKey]; hKey
0x140016704  call    cs:__imp_RegSetValueExW
0x14001670a  mov     rcx, [rsp+340h+hKey]; hKey
0x14001670f  test    rcx, rcx
0x140016712  jz      short loc_14001671A
0x140016714  call    cs:__imp_RegCloseKey
0x14001671a  lea     rcx, [rsp+340h+lpData]
0x14001671f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140016724  mov     eax, esi
0x140016726  mov     rcx, [rbp+240h+var_40]
0x14001672d  xor     rcx, rsp; StackCookie
0x140016730  call    __security_check_cookie
0x140016735  mov     rbx, [rsp+340h+arg_10]
0x14001673d  add     rsp, 310h
0x140016744  pop     r15
0x140016746  pop     r14
0x140016748  pop     r13
0x14001674a  pop     r12
0x14001674c  pop     rdi
0x14001674d  pop     rsi
  ... truncated ...
```
