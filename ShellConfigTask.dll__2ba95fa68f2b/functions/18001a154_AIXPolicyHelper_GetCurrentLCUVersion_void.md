# AIXPolicyHelper::GetCurrentLCUVersion(void)

- ea: `0x18001a154`
- end: `0x18001a23d`
- name: `?GetCurrentLCUVersion@AIXPolicyHelper@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001cce4`
- `0x18002cf54`

## callees

- `0x18000f29c`
- `0x18001a154`
- `0x180023160`
- `0x1800233ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a224`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a224`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AIXPolicyHelper::GetCurrentLCUVersion(__int64 a1)
{
  _WORD *v2; // rdi
  __int64 v3; // r8
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+50h] [rbp+18h]

  hKey = 0;
  if ( (int)wil::reg::open_unique_key_nothrow(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
              &hKey) < 0 )
  {
LABEL_9:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    std::wstring::_Construct<1,unsigned short const *>(a1, byte_180035C10, 0);
    goto LABEL_10;
  }
  pv = 0;
  if ( (int)wil::reg::get_value_nothrow(hKey, 0, L"LCUVer") < 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_9;
  }
  v2 = pv;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v3 = -1;
  do
    ++v3;
  while ( v2[v3] );
  std::wstring::_Construct<1,unsigned short const *>(a1, v2, v3);
  if ( v2 )
    CoTaskMemFree(v2);
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x18001a154  mov     rax, rsp
0x18001a157  mov     [rax+8], rbx
0x18001a15b  mov     [rax+20h], rsi
0x18001a15f  push    rdi
0x18001a160  sub     rsp, 30h
0x18001a164  mov     rbx, rcx
0x18001a167  xor     esi, esi
0x18001a169  mov     [rax+10h], rsi
0x18001a16d  xor     r9d, r9d
0x18001a170  lea     r8, [rax+10h]; phkResult
0x18001a174  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001a17b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a182  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18001a187  test    eax, eax
0x18001a189  js      short loc_18001A1F9
0x18001a18b  mov     [rsp+38h+pv], rsi
0x18001a190  lea     r9, [rsp+38h+pv]
0x18001a195  lea     r8, aLcuver; "LCUVer"
0x18001a19c  xor     edx, edx; lpSubKey
0x18001a19e  mov     rcx, [rsp+38h+hKey]; hkey
0x18001a1a3  call    ?get_value_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBG1AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@@Z; wil::reg::get_value_nothrow(HKEY__ *,ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18001a1a8  test    eax, eax
0x18001a1aa  js      short loc_18001A1E9
0x18001a1ac  mov     rdi, [rsp+38h+pv]
0x18001a1b1  xorps   xmm0, xmm0
0x18001a1b4  movups  xmmword ptr [rbx], xmm0
0x18001a1b7  mov     [rbx+10h], rsi
0x18001a1bb  mov     [rbx+18h], rsi
0x18001a1bf  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a1c3  inc     r8
0x18001a1c6  cmp     [rdi+r8*2], si
0x18001a1cb  jnz     short loc_18001A1C3
0x18001a1cd  mov     rdx, rdi
0x18001a1d0  mov     rcx, rbx
0x18001a1d3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001a1d8  nop
0x18001a1d9  test    rdi, rdi
0x18001a1dc  jz      short loc_18001A21A
0x18001a1de  mov     rcx, rdi; pv
0x18001a1e1  call    cs:__imp_CoTaskMemFree
0x18001a1e7  jmp     short loc_18001A21A
0x18001a1e9  mov     rcx, [rsp+38h+pv]; pv
0x18001a1ee  test    rcx, rcx
0x18001a1f1  jz      short loc_18001A1F9
0x18001a1f3  call    cs:__imp_CoTaskMemFree
0x18001a1f9  xorps   xmm0, xmm0
0x18001a1fc  movups  xmmword ptr [rbx], xmm0
0x18001a1ff  mov     [rbx+10h], rsi
0x18001a203  mov     [rbx+18h], rsi
0x18001a207  xor     r8d, r8d
0x18001a20a  lea     rdx, byte_180035C10
0x18001a211  mov     rcx, rbx
0x18001a214  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001a219  nop
0x18001a21a  mov     rcx, [rsp+38h+hKey]; hKey
0x18001a21f  test    rcx, rcx
0x18001a222  jz      short loc_18001A22A
0x18001a224  call    cs:__imp_RegCloseKey
0x18001a22a  mov     rax, rbx
0x18001a22d  mov     rbx, [rsp+38h+arg_0]
0x18001a232  mov     rsi, [rsp+38h+arg_18]
0x18001a237  add     rsp, 30h
0x18001a23b  pop     rdi
0x18001a23c  retn
```
