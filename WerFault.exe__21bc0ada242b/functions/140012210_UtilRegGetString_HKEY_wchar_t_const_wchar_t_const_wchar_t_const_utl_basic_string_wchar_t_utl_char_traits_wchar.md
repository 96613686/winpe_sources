# UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)

- ea: `0x140012210`
- end: `0x140012413`
- name: `?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z`
- size: `515`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, __int64, char, DWORD)`
- caller_count: `8`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1400102c0`
- `0x140010a7c`
- `0x1400135c0`
- `0x140031544`
- `0x140041ef4`
- `0x140043d54`
- `0x140043f20`
- `0x140053f7c`

## callees

- `0x140002728`
- `0x140005468`
- `0x14000be58`
- `0x14000c8a0`
- `0x14000cc58`
- `0x14000e6dc`
- `0x140012210`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140012375`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140012375`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140012306`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001235b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140012306`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001235b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400123f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400123f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400122b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400122b2`

## pseudocode

```c
__int64 __fastcall UtilRegGetString(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValue,
        _WORD *a4,
        _QWORD *a5,
        char a6,
        DWORD pcbData)
{
  _QWORD *v7; // rsi
  unsigned __int64 v13; // r8
  unsigned int v14; // ebx
  HKEY *phkResult; // rax
  LSTATUS ValueW; // eax
  bool v17; // cc
  HKEY v18; // r14
  size_t v19; // rax
  _WORD *v20; // rcx
  PVOID pvData; // [rsp+40h] [rbp-20h] BYREF
  char *v22; // [rsp+48h] [rbp-18h]
  _WORD v23[8]; // [rsp+50h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+90h] [rbp+30h] BYREF

  v7 = a5;
  pvData = v23;
  pcbData = 0;
  v22 = (char *)v23;
  hkey = 0;
  v23[0] = 0;
  if ( !a5 )
    return 2147942487LL;
  if ( a4 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a4[v13] );
    if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
            (__int64)&pvData,
            a4,
            v13) )
      goto LABEL_7;
  }
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  ValueW = RegOpenKeyExW(hKey, lpSubKey, 0, 0x101u, phkResult);
  v14 = ValueW;
  if ( ValueW
    || (v18 = hkey, pcbData = 0, ValueW = RegGetValueW(hkey, 0, lpValue, 2u, 0, 0, &pcbData), (v14 = ValueW) != 0) )
  {
    if ( a4 )
      goto LABEL_19;
    v17 = ValueW <= 0;
    goto LABEL_11;
  }
  v22 = (char *)pvData;
  *(_WORD *)pvData = 0;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          &pvData,
                          ((unsigned __int64)pcbData >> 1) + 1) )
  {
    ValueW = RegGetValueW(v18, 0, lpValue, 2u, 0, pvData, &pcbData);
    v14 = ValueW;
    v17 = ValueW <= 0;
    if ( !ValueW )
    {
      v19 = wcsnlen((const wchar_t *)pvData, (unsigned __int64)pcbData >> 1);
      if ( v19 > (v22 - (_BYTE *)pvData) >> 1 )
        __int2c();
      v22 = (char *)pvData + 2 * v19;
      *(_WORD *)v22 = 0;
LABEL_19:
      v14 = 0;
      if ( a6 )
        v14 = UtilExpandEnvironmentStrings((LPCWSTR)pvData);
      else
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(
          (__int64)v7,
          (__int64)&pvData);
      if ( !v14 )
        goto LABEL_24;
      goto LABEL_23;
    }
LABEL_11:
    if ( !v17 )
      v14 = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_23;
  }
LABEL_7:
  v14 = -2147024882;
LABEL_23:
  v20 = (_WORD *)*v7;
  v7[1] = *v7;
  *v20 = 0;
LABEL_24:
  if ( pvData != v23 )
    operator delete(pvData, (const struct std::nothrow_t *)&std::nothrow);
  if ( hkey )
    RegCloseKey(hkey);
  return v14;
}

```

## disassembly

```asm
0x140012210  mov     [rsp-28h+arg_8], rbx
0x140012215  mov     [rsp-28h+arg_10], rsi
0x14001221a  push    rbp
0x14001221b  push    rdi
0x14001221c  push    r12
0x14001221e  push    r14
0x140012220  push    r15
0x140012222  mov     rbp, rsp
0x140012225  sub     rsp, 60h
0x140012229  mov     rsi, [rbp+arg_20]
0x14001222d  lea     rax, [rbp+var_10]
0x140012231  xor     r12d, r12d
0x140012234  mov     [rbp+var_20], rax
0x140012238  mov     [rbp+arg_30], r12d
0x14001223c  lea     rax, [rbp+var_10]
0x140012240  mov     [rbp+var_18], rax
0x140012244  mov     rdi, r9
0x140012247  mov     [rbp+hkey], r12
0x14001224b  mov     r15, r8
0x14001224e  mov     [rbp+var_10], r12w
0x140012253  mov     rbx, rdx
0x140012256  mov     r14, rcx
0x140012259  test    rsi, rsi
0x14001225c  jnz     short loc_140012268
0x14001225e  mov     eax, 80070057h
0x140012263  jmp     loc_1400123FA
0x140012268  test    rdi, rdi
0x14001226b  jz      short loc_140012295
0x14001226d  or      r8, 0FFFFFFFFFFFFFFFFh
0x140012271  inc     r8
0x140012274  cmp     [r9+r8*2], r12w
0x140012279  jnz     short loc_140012271
0x14001227b  mov     rdx, rdi
0x14001227e  lea     rcx, [rbp+var_20]
0x140012282  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140012287  test    al, al
0x140012289  jnz     short loc_140012295
0x14001228b  mov     ebx, 8007000Eh
0x140012290  jmp     loc_1400123C5
0x140012295  lea     rcx, [rbp+hkey]
0x140012299  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14001229e  mov     r9d, 101h; samDesired
0x1400122a4  mov     [rsp+60h+phkResult], rax; phkResult
0x1400122a9  xor     r8d, r8d; ulOptions
0x1400122ac  mov     rdx, rbx; lpSubKey
0x1400122af  mov     rcx, r14; hKey
0x1400122b2  call    cs:__imp_RegOpenKeyExW
0x1400122b8  mov     ebx, eax
0x1400122ba  test    eax, eax
0x1400122bc  jz      short loc_1400122DD
0x1400122be  test    rdi, rdi
0x1400122c1  jnz     loc_14001239C
0x1400122c7  test    eax, eax
0x1400122c9  jle     loc_1400123C5
0x1400122cf  movzx   ebx, ax
0x1400122d2  or      ebx, 80070000h
0x1400122d8  jmp     loc_1400123C5
0x1400122dd  mov     r14, [rbp+hkey]
0x1400122e1  lea     rax, [rbp+arg_30]
0x1400122e5  mov     [rsp+60h+pcbData], rax; pcbData
0x1400122ea  mov     r9d, 2; dwFlags
0x1400122f0  mov     [rsp+60h+pvData], r12; pvData
0x1400122f5  mov     r8, r15; lpValue
0x1400122f8  xor     edx, edx; lpSubKey
0x1400122fa  mov     [rsp+60h+phkResult], r12; pdwType
0x1400122ff  mov     rcx, r14; hkey
0x140012302  mov     [rbp+arg_30], r12d
0x140012306  call    cs:__imp_RegGetValueW
0x14001230c  mov     ebx, eax
0x14001230e  test    eax, eax
0x140012310  jnz     short loc_1400122BE
0x140012312  mov     rcx, [rbp+var_20]
0x140012316  mov     [rbp+var_18], rcx
0x14001231a  mov     [rcx], r12w
0x14001231e  lea     rcx, [rbp+var_20]
0x140012322  mov     edx, [rbp+arg_30]
0x140012325  shr     rdx, 1
0x140012328  inc     rdx
0x14001232b  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x140012330  test    al, al
0x140012332  jz      loc_14001228B
0x140012338  lea     rax, [rbp+arg_30]
0x14001233c  mov     r8, r15; lpValue
0x14001233f  mov     [rsp+60h+pcbData], rax; pcbData
0x140012344  lea     r9d, [rbx+2]; dwFlags
0x140012348  mov     rax, [rbp+var_20]
0x14001234c  xor     edx, edx; lpSubKey
0x14001234e  mov     [rsp+60h+pvData], rax; pvData
0x140012353  mov     rcx, r14; hkey
0x140012356  mov     [rsp+60h+phkResult], r12; pdwType
0x14001235b  call    cs:__imp_RegGetValueW
0x140012361  mov     ebx, eax
0x140012363  test    eax, eax
0x140012365  jnz     loc_1400122C9
0x14001236b  mov     edx, [rbp+arg_30]
0x14001236e  mov     rcx, [rbp+var_20]; Source
0x140012372  shr     rdx, 1; MaxCount
0x140012375  call    cs:__imp_wcsnlen
0x14001237b  mov     rcx, [rbp+var_18]
0x14001237f  mov     rdx, [rbp+var_20]
0x140012383  sub     rcx, rdx
0x140012386  sar     rcx, 1
0x140012389  cmp     rax, rcx
0x14001238c  jbe     short loc_140012390
0x14001238e  int     2Ch; Windows NT - assertion failure
0x140012390  lea     rcx, [rdx+rax*2]
0x140012394  mov     [rbp+var_18], rcx
0x140012398  mov     [rcx], r12w
0x14001239c  mov     ebx, r12d
0x14001239f  cmp     [rbp+arg_28], r12b
0x1400123a3  jz      short loc_1400123B5
0x1400123a5  mov     rcx, [rbp+var_20]; lpSrc
0x1400123a9  mov     rdx, rsi
0x1400123ac  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1400123b1  mov     ebx, eax
0x1400123b3  jmp     short loc_1400123C1
0x1400123b5  lea     rdx, [rbp+var_20]
0x1400123b9  mov     rcx, rsi
0x1400123bc  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x1400123c1  test    ebx, ebx
0x1400123c3  jz      short loc_1400123D0
0x1400123c5  mov     rcx, [rsi]
0x1400123c8  mov     [rsi+8], rcx
0x1400123cc  mov     [rcx], r12w
0x1400123d0  mov     rcx, [rbp+var_20]; void *
0x1400123d4  lea     rax, [rbp+var_10]
0x1400123d8  cmp     rcx, rax
0x1400123db  jz      short loc_1400123E9
0x1400123dd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400123e4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400123e9  mov     rcx, [rbp+hkey]; hKey
0x1400123ed  test    rcx, rcx
0x1400123f0  jz      short loc_1400123F8
0x1400123f2  call    cs:__imp_RegCloseKey
0x1400123f8  mov     eax, ebx
0x1400123fa  lea     r11, [rsp+60h+var_s0]
0x1400123ff  mov     rbx, [r11+38h]
0x140012403  mov     rsi, [r11+40h]
0x140012407  mov     rsp, r11
0x14001240a  pop     r15
0x14001240c  pop     r14
0x14001240e  pop     r12
0x140012410  pop     rdi
0x140012411  pop     rbp
0x140012412  retn
```
