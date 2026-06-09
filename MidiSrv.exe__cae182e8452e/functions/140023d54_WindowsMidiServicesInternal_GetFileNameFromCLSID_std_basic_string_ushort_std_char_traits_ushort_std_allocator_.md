# WindowsMidiServicesInternal::GetFileNameFromCLSID(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140023d54`
- end: `0x140023ec0`
- name: `?GetFileNameFromCLSID@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `364`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400252b8`

## callees

- `0x1400054c0`
- `0x1400060f8`
- `0x1400072d4`
- `0x140007c20`
- `0x14000c630`
- `0x1400216cc`
- `0x140022d80`
- `0x140023d54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140023e46`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140023e46`

## string_xrefs

- `0x140023dc1`: `CLSID\`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::GetFileNameFromCLSID(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v4; // rcx
  const WCHAR *v5; // rdx
  LSTATUS ValueW; // eax
  __int64 v7; // r8
  const wchar_t *v8; // rdx
  DWORD pcbData[4]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v12[32]; // [rsp+70h] [rbp-90h] BYREF
  _WORD pvData[264]; // [rsp+90h] [rbp-70h] BYREF

  *(_QWORD *)pcbData = a1;
  v4 = a2[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v4) < 6 )
    std::_Xlen_string();
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::wstring::wstring(v12, a2, a3, L"CLSID\\", 6, a2, v4);
  std::operator+<unsigned short>(lpSubKey, v12, L"\\InprocServer32");
  std::wstring::~wstring(v12);
  memset_0(pvData, 0, 0x208u);
  pcbData[0] = 520;
  v5 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v5 = lpSubKey[0];
  ValueW = RegGetValueW(HKEY_CLASSES_ROOT, v5, 0, 2u, 0, pvData, pcbData);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  if ( ValueW )
  {
    v7 = 0;
    v8 = &S2;
  }
  else
  {
    v7 = -1;
    do
      ++v7;
    while ( pvData[v7] );
    v8 = pvData;
  }
  std::wstring::_Construct<1,unsigned short const *>(a1, v8, v7);
  std::wstring::~wstring(lpSubKey);
  return a1;
}

```

## disassembly

```asm
0x140023d54  mov     [rsp-8+arg_10], rbx
0x140023d59  mov     [rsp-8+arg_18], rsi
0x140023d5e  push    rbp
0x140023d5f  lea     rbp, [rsp-1B0h]
0x140023d67  sub     rsp, 2B0h
0x140023d6e  mov     rax, cs:__security_cookie
0x140023d75  xor     rax, rsp
0x140023d78  mov     [rbp+1B0h+var_10], rax
0x140023d7f  mov     rbx, rcx
0x140023d82  mov     qword ptr [rsp+2B0h+var_270], rcx
0x140023d87  xor     esi, esi
0x140023d89  mov     rcx, [rdx+10h]
0x140023d8d  mov     rax, 7FFFFFFFFFFFFFFEh
0x140023d97  sub     rax, rcx
0x140023d9a  cmp     rax, 6
0x140023d9e  jb      loc_140023EBA
0x140023da4  cmp     qword ptr [rdx+18h], 7
0x140023da9  jbe     short loc_140023DAE
0x140023dab  mov     rdx, [rdx]
0x140023dae  mov     [rsp+2B0h+pcbData], rcx
0x140023db3  mov     [rsp+2B0h+pvData], rdx
0x140023db8  mov     [rsp+2B0h+pdwType], 6
0x140023dc1  lea     r9, aClsid; "CLSID\\"
0x140023dc8  lea     rcx, [rsp+2B0h+var_240]
0x140023dcd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x140023dd2  nop
0x140023dd3  lea     r8, aInprocserver32; "\\InprocServer32"
0x140023dda  lea     rdx, [rsp+2B0h+var_240]
0x140023ddf  lea     rcx, [rsp+2B0h+lpSubKey]
0x140023de4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x140023de9  nop
0x140023dea  lea     rcx, [rsp+2B0h+var_240]; void *
0x140023def  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023df4  xor     edx, edx; Val
0x140023df6  mov     r8d, 208h; Size
0x140023dfc  lea     rcx, [rbp+1B0h+var_220]; void *
0x140023e00  call    memset_0
0x140023e05  mov     [rsp+2B0h+var_270], 208h
0x140023e0d  lea     rdx, [rsp+2B0h+lpSubKey]
0x140023e12  cmp     [rsp+2B0h+var_248], 7
0x140023e18  cmova   rdx, [rsp+2B0h+lpSubKey]; lpSubKey
0x140023e1e  lea     rax, [rsp+2B0h+var_270]
0x140023e23  mov     [rsp+2B0h+pcbData], rax; pcbData
0x140023e28  lea     rax, [rbp+1B0h+var_220]
0x140023e2c  mov     [rsp+2B0h+pvData], rax; pvData
0x140023e31  mov     [rsp+2B0h+pdwType], rsi; pdwType
0x140023e36  mov     r9d, 2; dwFlags
0x140023e3c  xor     r8d, r8d; lpValue
0x140023e3f  mov     rcx, 0FFFFFFFF80000000h; hkey
0x140023e46  call    cs:__imp_RegGetValueW
0x140023e4c  xorps   xmm0, xmm0
0x140023e4f  movups  xmmword ptr [rbx], xmm0
0x140023e52  mov     [rbx+10h], rsi
0x140023e56  mov     [rbx+18h], rsi
0x140023e5a  test    eax, eax
0x140023e5c  jz      short loc_140023E6A
0x140023e5e  xor     r8d, r8d
0x140023e61  lea     rdx, S2
0x140023e68  jmp     short loc_140023E80
0x140023e6a  lea     rax, [rbp+1B0h+var_220]
0x140023e6e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140023e72  inc     r8
0x140023e75  cmp     [rax+r8*2], si
0x140023e7a  jnz     short loc_140023E72
0x140023e7c  lea     rdx, [rbp+1B0h+var_220]
0x140023e80  mov     rcx, rbx
0x140023e83  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140023e88  nop
0x140023e89  lea     rcx, [rsp+2B0h+lpSubKey]; void *
0x140023e8e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023e93  mov     rax, rbx
0x140023e96  mov     rcx, [rbp+1B0h+var_10]
0x140023e9d  xor     rcx, rsp; StackCookie
0x140023ea0  call    __security_check_cookie
0x140023ea5  lea     r11, [rsp+2B0h+var_s0]
0x140023ead  mov     rbx, [r11+20h]
0x140023eb1  mov     rsi, [r11+28h]
0x140023eb5  mov     rsp, r11
0x140023eb8  pop     rbp
0x140023eb9  retn
0x140023eba  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
