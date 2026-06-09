# WindowsMidiServicesInternal::GetFileNameFromCLSID(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180043d40`
- end: `0x180043eac`
- name: `?GetFileNameFromCLSID@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180044458`

## callees

- `0x180005020`
- `0x180005e9c`
- `0x18000d430`
- `0x180013118`
- `0x18001996c`
- `0x180021b3c`
- `0x180043908`
- `0x180043d40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043e32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043e32`

## string_xrefs

- `0x180043dad`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WindowsMidiServicesInternal::GetFileNameFromCLSID(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v4; // rcx
  const WCHAR *v5; // rdx
  LSTATUS ValueW; // eax
  __int64 v7; // r8
  DWORD pcbData[4]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v11[32]; // [rsp+70h] [rbp-90h] BYREF
  _WORD pvData[264]; // [rsp+90h] [rbp-70h] BYREF

  *(_QWORD *)pcbData = a1;
  v4 = a2[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v4) < 6 )
    std::_Xlen_string();
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::wstring::wstring(v11, a2, a3, L"CLSID\\", 6, a2, v4);
  std::operator+<unsigned short>(lpSubKey, v11, L"\\InprocServer32");
  std::wstring::~wstring(v11);
  memset_0(pvData, 0, 0x208u);
  pcbData[0] = 520;
  v5 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v5 = lpSubKey[0];
  ValueW = RegGetValueW(HKEY_CLASSES_ROOT, v5, 0, 2u, 0, pvData, pcbData);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  if ( !ValueW )
  {
    v7 = -1;
    do
      ++v7;
    while ( pvData[v7] );
  }
  std::wstring::_Construct<1,unsigned short const *>(a1);
  std::wstring::~wstring(lpSubKey);
  return a1;
}

```

## disassembly

```asm
0x180043d40  mov     [rsp-8+arg_10], rbx
0x180043d45  mov     [rsp-8+arg_18], rsi
0x180043d4a  push    rbp
0x180043d4b  lea     rbp, [rsp-1B0h]
0x180043d53  sub     rsp, 2B0h
0x180043d5a  mov     rax, cs:__security_cookie
0x180043d61  xor     rax, rsp
0x180043d64  mov     [rbp+1B0h+var_10], rax
0x180043d6b  mov     rbx, rcx
0x180043d6e  mov     qword ptr [rsp+2B0h+var_270], rcx
0x180043d73  xor     esi, esi
0x180043d75  mov     rcx, [rdx+10h]
0x180043d79  mov     rax, 7FFFFFFFFFFFFFFEh
0x180043d83  sub     rax, rcx
0x180043d86  cmp     rax, 6
0x180043d8a  jb      loc_180043EA6
0x180043d90  cmp     qword ptr [rdx+18h], 7
0x180043d95  jbe     short loc_180043D9A
0x180043d97  mov     rdx, [rdx]
0x180043d9a  mov     [rsp+2B0h+pcbData], rcx
0x180043d9f  mov     [rsp+2B0h+pvData], rdx
0x180043da4  mov     [rsp+2B0h+pdwType], 6
0x180043dad  lea     r9, aClsid; "CLSID\\"
0x180043db4  lea     rcx, [rsp+2B0h+var_240]
0x180043db9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180043dbe  nop
0x180043dbf  lea     r8, aInprocserver32; "\\InprocServer32"
0x180043dc6  lea     rdx, [rsp+2B0h+var_240]
0x180043dcb  lea     rcx, [rsp+2B0h+lpSubKey]
0x180043dd0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180043dd5  nop
0x180043dd6  lea     rcx, [rsp+2B0h+var_240]; void *
0x180043ddb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043de0  xor     edx, edx; Val
0x180043de2  mov     r8d, 208h; Size
0x180043de8  lea     rcx, [rbp+1B0h+var_220]; void *
0x180043dec  call    memset_0
0x180043df1  mov     [rsp+2B0h+var_270], 208h
0x180043df9  lea     rdx, [rsp+2B0h+lpSubKey]
0x180043dfe  cmp     [rsp+2B0h+var_248], 7
0x180043e04  cmova   rdx, [rsp+2B0h+lpSubKey]; lpSubKey
0x180043e0a  lea     rax, [rsp+2B0h+var_270]
0x180043e0f  mov     [rsp+2B0h+pcbData], rax; pcbData
0x180043e14  lea     rax, [rbp+1B0h+var_220]
0x180043e18  mov     [rsp+2B0h+pvData], rax; pvData
0x180043e1d  mov     [rsp+2B0h+pdwType], rsi; pdwType
0x180043e22  mov     r9d, 2; dwFlags
0x180043e28  xor     r8d, r8d; lpValue
0x180043e2b  mov     rcx, 0FFFFFFFF80000000h; hkey
0x180043e32  call    cs:__imp_RegGetValueW
0x180043e38  xorps   xmm0, xmm0
0x180043e3b  movups  xmmword ptr [rbx], xmm0
0x180043e3e  mov     [rbx+10h], rsi
0x180043e42  mov     [rbx+18h], rsi
0x180043e46  test    eax, eax
0x180043e48  jz      short loc_180043E56
0x180043e4a  xor     r8d, r8d
0x180043e4d  lea     rdx, S1
0x180043e54  jmp     short loc_180043E6C
0x180043e56  lea     rax, [rbp+1B0h+var_220]
0x180043e5a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180043e5e  inc     r8
0x180043e61  cmp     [rax+r8*2], si
0x180043e66  jnz     short loc_180043E5E
0x180043e68  lea     rdx, [rbp+1B0h+var_220]
0x180043e6c  mov     rcx, rbx
0x180043e6f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180043e74  nop
0x180043e75  lea     rcx, [rsp+2B0h+lpSubKey]; void *
0x180043e7a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043e7f  mov     rax, rbx
0x180043e82  mov     rcx, [rbp+1B0h+var_10]
0x180043e89  xor     rcx, rsp; StackCookie
0x180043e8c  call    __security_check_cookie
0x180043e91  lea     r11, [rsp+2B0h+var_s0]
0x180043e99  mov     rbx, [r11+20h]
0x180043e9d  mov     rsi, [r11+28h]
0x180043ea1  mov     rsp, r11
0x180043ea4  pop     rbp
0x180043ea5  retn
0x180043ea6  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
