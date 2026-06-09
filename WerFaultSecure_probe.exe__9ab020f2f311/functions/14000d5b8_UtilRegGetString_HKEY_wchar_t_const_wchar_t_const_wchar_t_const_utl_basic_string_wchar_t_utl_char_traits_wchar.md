# UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)

- ea: `0x14000d5b8`
- end: `0x14000d78e`
- name: `?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z`
- size: `470`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, DWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000cfc4`

## callees

- `0x1400023f4`
- `0x1400085f0`
- `0x140008d3c`
- `0x14000d5b8`
- `0x14000dc44`
- `0x14000e1e8`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14000d71e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14000d71e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000d64d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000d64d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000d776`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000d776`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d68f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d6ef`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d68f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d6ef`

## string_xrefs

- `0x14000d65f`: `StorePath`
- `0x14000d6d1`: `StorePath`

## pseudocode

```c
__int64 __fastcall UtilRegGetString(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, DWORD pcbData)
{
  __int64 v6; // rdi
  unsigned int v8; // ebx
  HKEY *phkResult; // rax
  HKEY v10; // rbx
  LSTATUS ValueW; // eax
  _WORD *v12; // rcx
  size_t v13; // rax
  PVOID pvData; // [rsp+40h] [rbp-20h] BYREF
  char *v15; // [rsp+48h] [rbp-18h]
  _WORD v16[8]; // [rsp+50h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+88h] [rbp+28h] BYREF

  v6 = a5;
  pvData = v16;
  v15 = (char *)v16;
  pcbData = 0;
  hkey = 0;
  v16[0] = 0;
  if ( !a5 )
    return 2147942487LL;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &pvData,
                           &unk_140014A6C) )
    goto LABEL_4;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\Windows Error Reporting", 0, 0x101u, phkResult)
    || (v10 = hkey, pcbData = 0, RegGetValueW(hkey, 0, L"StorePath", 2u, 0, 0, &pcbData)) )
  {
LABEL_15:
    v8 = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v6, &pvData);
    goto LABEL_16;
  }
  v15 = (char *)pvData;
  *(_WORD *)pvData = 0;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          &pvData,
                          ((unsigned __int64)pcbData >> 1) + 1) )
  {
    ValueW = RegGetValueW(v10, 0, L"StorePath", 2u, 0, pvData, &pcbData);
    v8 = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v8 = (unsigned __int16)ValueW | 0x80070000;
      goto LABEL_11;
    }
    v13 = wcsnlen((const wchar_t *)pvData, (unsigned __int64)pcbData >> 1);
    if ( v13 > (v15 - (_BYTE *)pvData) >> 1 )
      __int2c();
    v15 = (char *)pvData + 2 * v13;
    *(_WORD *)v15 = 0;
    goto LABEL_15;
  }
LABEL_4:
  v8 = -2147024882;
LABEL_11:
  v12 = *(_WORD **)v6;
  *(_QWORD *)(v6 + 8) = *(_QWORD *)v6;
  *v12 = 0;
LABEL_16:
  if ( pvData != v16 )
    operator delete(pvData, (const struct std::nothrow_t *)&std::nothrow);
  if ( hkey )
    RegCloseKey(hkey);
  return v8;
}

```

## disassembly

```asm
0x14000d5b8  mov     [rsp-8+arg_0], rbx
0x14000d5bd  mov     [rsp-8+arg_8], rdi
0x14000d5c2  mov     [rsp-8+hkey], r9
0x14000d5c7  push    rbp
0x14000d5c8  mov     rbp, rsp
0x14000d5cb  sub     rsp, 60h
0x14000d5cf  mov     rdi, [rbp+arg_20]
0x14000d5d3  lea     rax, [rbp+var_10]
0x14000d5d7  mov     [rbp+var_20], rax
0x14000d5db  lea     rax, [rbp+var_10]
0x14000d5df  mov     [rbp+var_18], rax
0x14000d5e3  xor     eax, eax
0x14000d5e5  mov     [rbp+arg_28], 0
0x14000d5ec  mov     [rbp+hkey], 0
0x14000d5f4  mov     [rbp+var_10], ax
0x14000d5f8  test    rdi, rdi
0x14000d5fb  jnz     short loc_14000D607
0x14000d5fd  mov     eax, 80070057h
0x14000d602  jmp     loc_14000D77E
0x14000d607  xor     r8d, r8d
0x14000d60a  lea     rdx, unk_140014A6C
0x14000d611  lea     rcx, [rbp+var_20]
0x14000d615  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14000d61a  test    al, al
0x14000d61c  jnz     short loc_14000D628
0x14000d61e  mov     ebx, 8007000Eh
0x14000d623  jmp     loc_14000D706
0x14000d628  lea     rcx, [rbp+hkey]
0x14000d62c  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14000d631  mov     r9d, 101h; samDesired
0x14000d637  mov     [rsp+60h+phkResult], rax; phkResult
0x14000d63c  xor     r8d, r8d; ulOptions
0x14000d63f  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\Windows E"...
0x14000d646  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000d64d  call    cs:__imp_RegOpenKeyExW
0x14000d653  test    eax, eax
0x14000d655  jnz     loc_14000D746
0x14000d65b  mov     rbx, [rbp+hkey]
0x14000d65f  lea     r8, Value; "StorePath"
0x14000d666  mov     [rbp+arg_28], eax
0x14000d669  mov     r9d, 2; dwFlags
0x14000d66f  lea     rax, [rbp+arg_28]
0x14000d673  xor     edx, edx; lpSubKey
0x14000d675  mov     [rsp+60h+pcbData], rax; pcbData
0x14000d67a  mov     rcx, rbx; hkey
0x14000d67d  mov     [rsp+60h+pvData], 0; pvData
0x14000d686  mov     [rsp+60h+phkResult], 0; pdwType
0x14000d68f  call    cs:__imp_RegGetValueW
0x14000d695  test    eax, eax
0x14000d697  jnz     loc_14000D746
0x14000d69d  mov     rcx, [rbp+var_20]
0x14000d6a1  mov     [rbp+var_18], rcx
0x14000d6a5  mov     [rcx], ax
0x14000d6a8  lea     rcx, [rbp+var_20]
0x14000d6ac  mov     edx, [rbp+arg_28]
0x14000d6af  shr     rdx, 1
0x14000d6b2  inc     rdx
0x14000d6b5  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x14000d6ba  test    al, al
0x14000d6bc  jz      loc_14000D61E
0x14000d6c2  lea     rax, [rbp+arg_28]
0x14000d6c6  mov     r9d, 2; dwFlags
0x14000d6cc  mov     [rsp+60h+pcbData], rax; pcbData
0x14000d6d1  lea     r8, Value; "StorePath"
0x14000d6d8  mov     rax, [rbp+var_20]
0x14000d6dc  xor     edx, edx; lpSubKey
0x14000d6de  mov     [rsp+60h+pvData], rax; pvData
0x14000d6e3  mov     rcx, rbx; hkey
0x14000d6e6  mov     [rsp+60h+phkResult], 0; pdwType
0x14000d6ef  call    cs:__imp_RegGetValueW
0x14000d6f5  mov     ebx, eax
0x14000d6f7  test    eax, eax
0x14000d6f9  jz      short loc_14000D714
0x14000d6fb  jle     short loc_14000D706
0x14000d6fd  movzx   ebx, ax
0x14000d700  or      ebx, 80070000h
0x14000d706  mov     rcx, [rdi]
0x14000d709  xor     eax, eax
0x14000d70b  mov     [rdi+8], rcx
0x14000d70f  mov     [rcx], ax
0x14000d712  jmp     short loc_14000D754
0x14000d714  mov     edx, [rbp+arg_28]
0x14000d717  mov     rcx, [rbp+var_20]; Source
0x14000d71b  shr     rdx, 1; MaxCount
0x14000d71e  call    cs:__imp_wcsnlen
0x14000d724  mov     rcx, [rbp+var_18]
0x14000d728  mov     rdx, [rbp+var_20]
0x14000d72c  sub     rcx, rdx
0x14000d72f  sar     rcx, 1
0x14000d732  cmp     rax, rcx
0x14000d735  jbe     short loc_14000D739
0x14000d737  int     2Ch; Windows NT - assertion failure
0x14000d739  lea     rdx, [rdx+rax*2]
0x14000d73d  xor     eax, eax
0x14000d73f  mov     [rbp+var_18], rdx
0x14000d743  mov     [rdx], ax
0x14000d746  xor     ebx, ebx
0x14000d748  lea     rdx, [rbp+var_20]
0x14000d74c  mov     rcx, rdi
0x14000d74f  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x14000d754  mov     rcx, [rbp+var_20]; void *
0x14000d758  lea     rax, [rbp+var_10]
0x14000d75c  cmp     rcx, rax
0x14000d75f  jz      short loc_14000D76D
0x14000d761  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d768  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d76d  mov     rcx, [rbp+hkey]; hKey
0x14000d771  test    rcx, rcx
0x14000d774  jz      short loc_14000D77C
0x14000d776  call    cs:__imp_RegCloseKey
0x14000d77c  mov     eax, ebx
0x14000d77e  mov     rbx, [rsp+60h+arg_0]
0x14000d783  mov     rdi, [rsp+60h+arg_8]
0x14000d788  add     rsp, 60h
0x14000d78c  pop     rbp
0x14000d78d  retn
```
