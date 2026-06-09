# UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)

- ea: `0x140012a9c`
- end: `0x140012cbe`
- name: `?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z`
- size: `546`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, __int64, char, DWORD)`
- caller_count: `8`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x14001096c`
- `0x140011158`
- `0x140013f04`
- `0x140033798`
- `0x140044cd0`
- `0x140046d00`
- `0x140046ed8`
- `0x140057940`

## callees

- `0x140002748`
- `0x14000551c`
- `0x14000c060`
- `0x14000ca20`
- `0x14000cf48`
- `0x14000e9d4`
- `0x140012a9c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140012c13`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140012c13`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140012b98`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140012bf3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140012b98`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140012bf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012c96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012c96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012b3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012b3e`

## pseudocode

```c
__int64 __fastcall UtilRegGetString(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValue,
        __int64 a4,
        __int64 a5,
        char a6,
        DWORD pcbData)
{
  __int64 v7; // rsi
  __int64 v13; // r8
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
    while ( *(_WORD *)(a4 + 2 * v13) );
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             &pvData,
                             a4) )
      goto LABEL_7;
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
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
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v7, &pvData);
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
  v20 = *(_WORD **)v7;
  *(_QWORD *)(v7 + 8) = *(_QWORD *)v7;
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
0x140012a9c  mov     [rsp-28h+arg_8], rbx
0x140012aa1  mov     [rsp-28h+arg_10], rsi
0x140012aa6  push    rbp
0x140012aa7  push    rdi
0x140012aa8  push    r12
0x140012aaa  push    r14
0x140012aac  push    r15
0x140012aae  mov     rbp, rsp
0x140012ab1  sub     rsp, 60h
0x140012ab5  mov     rsi, [rbp+arg_20]
0x140012ab9  lea     rax, [rbp+var_10]
0x140012abd  xor     r12d, r12d
0x140012ac0  mov     [rbp+var_20], rax
0x140012ac4  mov     [rbp+arg_30], r12d
0x140012ac8  lea     rax, [rbp+var_10]
0x140012acc  mov     [rbp+var_18], rax
0x140012ad0  mov     rdi, r9
0x140012ad3  mov     [rbp+hkey], r12
0x140012ad7  mov     r15, r8
0x140012ada  mov     [rbp+var_10], r12w
0x140012adf  mov     rbx, rdx
0x140012ae2  mov     r14, rcx
0x140012ae5  test    rsi, rsi
0x140012ae8  jnz     short loc_140012AF4
0x140012aea  mov     eax, 80070057h
0x140012aef  jmp     loc_140012CA4
0x140012af4  test    rdi, rdi
0x140012af7  jz      short loc_140012B21
0x140012af9  or      r8, 0FFFFFFFFFFFFFFFFh
0x140012afd  inc     r8
0x140012b00  cmp     [r9+r8*2], r12w
0x140012b05  jnz     short loc_140012AFD
0x140012b07  mov     rdx, rdi
0x140012b0a  lea     rcx, [rbp+var_20]
0x140012b0e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140012b13  test    al, al
0x140012b15  jnz     short loc_140012B21
0x140012b17  mov     ebx, 8007000Eh
0x140012b1c  jmp     loc_140012C69
0x140012b21  lea     rcx, [rbp+hkey]
0x140012b25  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140012b2a  mov     r9d, 101h; samDesired
0x140012b30  mov     [rsp+60h+phkResult], rax; phkResult
0x140012b35  xor     r8d, r8d; ulOptions
0x140012b38  mov     rdx, rbx; lpSubKey
0x140012b3b  mov     rcx, r14; hKey
0x140012b3e  call    cs:__imp_RegOpenKeyExW
0x140012b45  nop     dword ptr [rax+rax+00h]
0x140012b4a  mov     ebx, eax
0x140012b4c  test    eax, eax
0x140012b4e  jz      short loc_140012B6F
0x140012b50  test    rdi, rdi
0x140012b53  jnz     loc_140012C40
0x140012b59  test    eax, eax
0x140012b5b  jle     loc_140012C69
0x140012b61  movzx   ebx, ax
0x140012b64  or      ebx, 80070000h
0x140012b6a  jmp     loc_140012C69
0x140012b6f  mov     r14, [rbp+hkey]
0x140012b73  lea     rax, [rbp+arg_30]
0x140012b77  mov     [rsp+60h+pcbData], rax; pcbData
0x140012b7c  mov     r9d, 2; dwFlags
0x140012b82  mov     [rsp+60h+pvData], r12; pvData
0x140012b87  mov     r8, r15; lpValue
0x140012b8a  xor     edx, edx; lpSubKey
0x140012b8c  mov     [rsp+60h+phkResult], r12; pdwType
0x140012b91  mov     rcx, r14; hkey
0x140012b94  mov     [rbp+arg_30], r12d
0x140012b98  call    cs:__imp_RegGetValueW
0x140012b9f  nop     dword ptr [rax+rax+00h]
0x140012ba4  mov     ebx, eax
0x140012ba6  test    eax, eax
0x140012ba8  jnz     short loc_140012B50
0x140012baa  mov     rcx, [rbp+var_20]
0x140012bae  mov     [rbp+var_18], rcx
0x140012bb2  mov     [rcx], r12w
0x140012bb6  lea     rcx, [rbp+var_20]
0x140012bba  mov     edx, [rbp+arg_30]
0x140012bbd  shr     rdx, 1
0x140012bc0  inc     rdx
0x140012bc3  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x140012bc8  test    al, al
0x140012bca  jz      loc_140012B17
0x140012bd0  lea     rax, [rbp+arg_30]
0x140012bd4  mov     r8, r15; lpValue
0x140012bd7  mov     [rsp+60h+pcbData], rax; pcbData
0x140012bdc  lea     r9d, [rbx+2]; dwFlags
0x140012be0  mov     rax, [rbp+var_20]
0x140012be4  xor     edx, edx; lpSubKey
0x140012be6  mov     [rsp+60h+pvData], rax; pvData
0x140012beb  mov     rcx, r14; hkey
0x140012bee  mov     [rsp+60h+phkResult], r12; pdwType
0x140012bf3  call    cs:__imp_RegGetValueW
0x140012bfa  nop     dword ptr [rax+rax+00h]
0x140012bff  mov     ebx, eax
0x140012c01  test    eax, eax
0x140012c03  jnz     loc_140012B5B
0x140012c09  mov     edx, [rbp+arg_30]
0x140012c0c  mov     rcx, [rbp+var_20]; Source
0x140012c10  shr     rdx, 1; MaxCount
0x140012c13  call    cs:__imp_wcsnlen
0x140012c1a  nop     dword ptr [rax+rax+00h]
0x140012c1f  mov     rcx, [rbp+var_18]
0x140012c23  mov     rdx, [rbp+var_20]
0x140012c27  sub     rcx, rdx
0x140012c2a  sar     rcx, 1
0x140012c2d  cmp     rax, rcx
0x140012c30  jbe     short loc_140012C34
0x140012c32  int     2Ch; Windows NT - assertion failure
0x140012c34  lea     rcx, [rdx+rax*2]
0x140012c38  mov     [rbp+var_18], rcx
0x140012c3c  mov     [rcx], r12w
0x140012c40  mov     ebx, r12d
0x140012c43  cmp     [rbp+arg_28], r12b
0x140012c47  jz      short loc_140012C59
0x140012c49  mov     rcx, [rbp+var_20]; lpSrc
0x140012c4d  mov     rdx, rsi
0x140012c50  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140012c55  mov     ebx, eax
0x140012c57  jmp     short loc_140012C65
0x140012c59  lea     rdx, [rbp+var_20]
0x140012c5d  mov     rcx, rsi
0x140012c60  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x140012c65  test    ebx, ebx
0x140012c67  jz      short loc_140012C74
0x140012c69  mov     rcx, [rsi]
0x140012c6c  mov     [rsi+8], rcx
0x140012c70  mov     [rcx], r12w
0x140012c74  mov     rcx, [rbp+var_20]; void *
0x140012c78  lea     rax, [rbp+var_10]
0x140012c7c  cmp     rcx, rax
0x140012c7f  jz      short loc_140012C8D
0x140012c81  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140012c88  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140012c8d  mov     rcx, [rbp+hkey]; hKey
0x140012c91  test    rcx, rcx
0x140012c94  jz      short loc_140012CA2
0x140012c96  call    cs:__imp_RegCloseKey
0x140012c9d  nop     dword ptr [rax+rax+00h]
0x140012ca2  mov     eax, ebx
0x140012ca4  lea     r11, [rsp+60h+var_s0]
0x140012ca9  mov     rbx, [r11+38h]
0x140012cad  mov     rsi, [r11+40h]
0x140012cb1  mov     rsp, r11
0x140012cb4  pop     r15
0x140012cb6  pop     r14
0x140012cb8  pop     r12
0x140012cba  pop     rdi
0x140012cbb  pop     rbp
0x140012cbc  retn
```
