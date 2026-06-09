# AIXPolicyHelper::IsLCUVersionChanged(void)

- ea: `0x18001cce4`
- end: `0x18001ce50`
- name: `?IsLCUVersionChanged@AIXPolicyHelper@@YA_NXZ`
- size: `364`
- prototype: `bool __fastcall(AIXPolicyHelper *__hidden this)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001bf24`
- `0x18001e518`
- `0x18002b864`
- `0x18002d050`

## callees

- `0x180002590`
- `0x18000f29c`
- `0x180013890`
- `0x18001a154`
- `0x18001cce4`
- `0x180023160`
- `0x1800233ec`
- `0x180025280`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cdcc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cdcc`

## string_xrefs

- `0x18001cd1e`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsAI\LastConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall AIXPolicyHelper::IsLCUVersionChanged(AIXPolicyHelper *this)
{
  void *v1; // rbx
  __int64 v2; // r8
  const wchar_t *v3; // rdx
  const wchar_t *v4; // rcx
  char v5; // bl
  HKEY hKey; // [rsp+20h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-58h]
  wchar_t *S2[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v10; // [rsp+40h] [rbp-40h]
  unsigned __int64 v11; // [rsp+48h] [rbp-38h]
  wchar_t *S1[2]; // [rsp+50h] [rbp-30h] BYREF
  size_t N; // [rsp+60h] [rbp-20h]
  unsigned __int64 v14; // [rsp+68h] [rbp-18h]

  AIXPolicyHelper::GetCurrentLCUVersion(S1);
  hKey = 0;
  if ( (int)wil::reg::open_unique_key_nothrow(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsAI\\LastConfiguration",
              &hKey) < 0 )
  {
LABEL_9:
    *(_OWORD *)S2 = 0;
    v10 = 0;
    v11 = 0;
    std::wstring::_Construct<1,unsigned short const *>(S2, byte_180035C10, 0);
    goto LABEL_10;
  }
  pv = 0;
  if ( (int)wil::reg::get_value_nothrow(hKey, 0, L"LastKnownLCUVersion") < 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_9;
  }
  v1 = pv;
  *(_OWORD *)S2 = 0;
  v10 = 0;
  v11 = 0;
  v2 = -1;
  do
    ++v2;
  while ( *((_WORD *)pv + v2) );
  std::wstring::_Construct<1,unsigned short const *>(S2, pv, v2);
  if ( v1 )
    CoTaskMemFree(v1);
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  if ( !v10 || !N )
    goto LABEL_21;
  v3 = (const wchar_t *)S2;
  if ( v11 > 7 )
    v3 = S2[0];
  v4 = (const wchar_t *)S1;
  if ( v14 > 7 )
    v4 = S1[0];
  if ( N == v10 && !wmemcmp(v4, v3, N) )
LABEL_21:
    v5 = 0;
  else
    v5 = 1;
  std::wstring::~wstring(S2);
  std::wstring::~wstring(S1);
  return v5;
}

```

## disassembly

```asm
0x18001cce4  mov     [rsp-8+arg_0], rbx
0x18001cce9  mov     [rsp-8+arg_8], rdi
0x18001ccee  push    rbp
0x18001ccef  mov     rbp, rsp
0x18001ccf2  sub     rsp, 80h
0x18001ccf9  mov     rax, cs:__security_cookie
0x18001cd00  xor     rax, rsp
0x18001cd03  mov     [rbp+var_10], rax
0x18001cd07  xor     edi, edi
0x18001cd09  lea     rcx, [rbp+S1]
0x18001cd0d  call    ?GetCurrentLCUVersion@AIXPolicyHelper@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; AIXPolicyHelper::GetCurrentLCUVersion(void)
0x18001cd12  nop
0x18001cd13  mov     [rbp+hKey], rdi
0x18001cd17  xor     r9d, r9d
0x18001cd1a  lea     r8, [rbp+hKey]; phkResult
0x18001cd1e  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001cd25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cd2c  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18001cd31  test    eax, eax
0x18001cd33  js      short loc_18001CDA0
0x18001cd35  mov     [rbp+pv], rdi
0x18001cd39  lea     r9, [rbp+pv]
0x18001cd3d  lea     r8, aLastknownlcuve; "LastKnownLCUVersion"
0x18001cd44  xor     edx, edx; lpSubKey
0x18001cd46  mov     rcx, [rbp+hKey]; hkey
0x18001cd4a  call    ?get_value_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBG1AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@@Z; wil::reg::get_value_nothrow(HKEY__ *,ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18001cd4f  test    eax, eax
0x18001cd51  js      short loc_18001CD91
0x18001cd53  mov     rbx, [rbp+pv]
0x18001cd57  xorps   xmm0, xmm0
0x18001cd5a  movups  xmmword ptr [rbp+S2], xmm0
0x18001cd5e  mov     [rbp+var_40], rdi
0x18001cd62  mov     [rbp+var_38], rdi
0x18001cd66  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001cd6a  inc     r8
0x18001cd6d  cmp     [rbx+r8*2], di
0x18001cd72  jnz     short loc_18001CD6A
0x18001cd74  mov     rdx, rbx
0x18001cd77  lea     rcx, [rbp+S2]
0x18001cd7b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001cd80  nop
0x18001cd81  test    rbx, rbx
0x18001cd84  jz      short loc_18001CDC3
0x18001cd86  mov     rcx, rbx; pv
0x18001cd89  call    cs:__imp_CoTaskMemFree
0x18001cd8f  jmp     short loc_18001CDC3
0x18001cd91  mov     rcx, [rbp+pv]; pv
0x18001cd95  test    rcx, rcx
0x18001cd98  jz      short loc_18001CDA0
0x18001cd9a  call    cs:__imp_CoTaskMemFree
0x18001cda0  xorps   xmm0, xmm0
0x18001cda3  movups  xmmword ptr [rbp+S2], xmm0
0x18001cda7  mov     [rbp+var_40], rdi
0x18001cdab  mov     [rbp+var_38], rdi
0x18001cdaf  xor     r8d, r8d
0x18001cdb2  lea     rdx, byte_180035C10
0x18001cdb9  lea     rcx, [rbp+S2]
0x18001cdbd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001cdc2  nop
0x18001cdc3  mov     rcx, [rbp+hKey]; hKey
0x18001cdc7  test    rcx, rcx
0x18001cdca  jz      short loc_18001CDD2
0x18001cdcc  call    cs:__imp_RegCloseKey
0x18001cdd2  mov     rax, [rbp+var_40]
0x18001cdd6  test    rax, rax
0x18001cdd9  jz      short loc_18001CE17
0x18001cddb  mov     r8, [rbp+N]; N
0x18001cddf  test    r8, r8
0x18001cde2  jz      short loc_18001CE17
0x18001cde4  lea     rdx, [rbp+S2]
0x18001cde8  cmp     [rbp+var_38], 7
0x18001cded  cmova   rdx, [rbp+S2]; S2
0x18001cdf2  lea     rcx, [rbp+S1]
0x18001cdf6  cmp     [rbp+var_18], 7
0x18001cdfb  cmova   rcx, [rbp+S1]; S1
0x18001ce00  cmp     r8, rax
0x18001ce03  jnz     short loc_18001CE13
0x18001ce05  test    r8, r8
0x18001ce08  jz      short loc_18001CE17
0x18001ce0a  call    wmemcmp
0x18001ce0f  test    eax, eax
0x18001ce11  jz      short loc_18001CE17
0x18001ce13  mov     bl, 1
0x18001ce15  jmp     short loc_18001CE1A
0x18001ce17  mov     bl, dil
0x18001ce1a  lea     rcx, [rbp+S2]
0x18001ce1e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ce23  nop
0x18001ce24  lea     rcx, [rbp+S1]
0x18001ce28  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ce2d  mov     al, bl
0x18001ce2f  mov     rcx, [rbp+var_10]
0x18001ce33  xor     rcx, rsp; StackCookie
0x18001ce36  call    __security_check_cookie
0x18001ce3b  lea     r11, [rsp+80h+var_s0]
0x18001ce43  mov     rbx, [r11+10h]
0x18001ce47  mov     rdi, [r11+18h]
0x18001ce4b  mov     rsp, r11
0x18001ce4e  pop     rbp
0x18001ce4f  retn
```
