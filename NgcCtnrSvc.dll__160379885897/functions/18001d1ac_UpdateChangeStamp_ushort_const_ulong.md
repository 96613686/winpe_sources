# UpdateChangeStamp(ushort const *,ulong)

- ea: `0x18001d1ac`
- end: `0x18001d2d9`
- name: `?UpdateChangeStamp@@YAJPEBGK@Z`
- size: `301`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800352d0`
- `0x180036370`

## callees

- `0x180018194`
- `0x180019c94`
- `0x18001d1ac`
- `0x180035940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d293`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d293`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d21d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d21d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UpdateChangeStamp(LPCWSTR lpValueName, int a2)
{
  LSTATUS v3; // ebx
  __int16 *v4; // rdx
  void **v6; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  int Data; // [rsp+88h] [rbp+28h] BYREF
  LSTATUS v9; // [rsp+90h] [rbp+30h] BYREF

  Data = a2;
  hKey = 0;
  v6 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v6);
  v3 = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Cryptography\\NGC", 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v3 )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
    {
LABEL_5:
      v6 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v6);
      return HResultToNtStatus(v3);
    }
    v4 = word_1800A8392;
LABEL_4:
    v9 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BE0B8,
      (_DWORD)v4,
      0,
      0,
      (__int64)&v9);
    goto LABEL_5;
  }
  v3 = RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
  if ( v3 )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_5;
    v4 = &word_1800A8366;
    goto LABEL_4;
  }
  v6 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v6);
  return 0;
}

```

## disassembly

```asm
0x18001d1ac  mov     [rsp-18h+arg_0], rbx
0x18001d1b1  mov     [rsp-18h+Data], edx
0x18001d1b5  push    rbp
0x18001d1b6  push    rsi
0x18001d1b7  push    rdi
0x18001d1b8  mov     rbp, rsp
0x18001d1bb  sub     rsp, 60h
0x18001d1bf  mov     rdi, rcx
0x18001d1c2  mov     [rbp+hKey], 0
0x18001d1ca  lea     rsi, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x18001d1d1  lea     rcx, [rbp+var_10]
0x18001d1d5  mov     [rbp+var_10], rsi
0x18001d1d9  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001d1de  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18001d1e7  lea     rax, [rbp+hKey]
0x18001d1eb  mov     [rsp+60h+phkResult], rax; phkResult
0x18001d1f0  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Cryptography\\NGC"
0x18001d1f7  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001d200  xor     r9d, r9d; lpClass
0x18001d203  mov     [rsp+60h+samDesired], 20006h; samDesired
0x18001d20b  xor     r8d, r8d; Reserved
0x18001d20e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001d215  mov     [rsp+60h+dwOptions], 0; dwOptions
0x18001d21d  call    cs:__imp_RegCreateKeyExW
0x18001d224  nop     dword ptr [rax+rax+00h]
0x18001d229  mov     ebx, eax
0x18001d22b  test    eax, eax
0x18001d22d  jz      short loc_18001D275
0x18001d22f  mov     ecx, cs:dword_1800BE0B8
0x18001d235  cmp     ecx, 2
0x18001d238  jbe     short loc_18001D25F
0x18001d23a  lea     rdx, word_1800A8392
0x18001d241  xor     r9d, r9d
0x18001d244  lea     rax, [rbp+arg_10]
0x18001d248  xor     r8d, r8d
0x18001d24b  mov     qword ptr [rsp+60h+dwOptions], rax
0x18001d250  lea     rcx, dword_1800BE0B8
0x18001d257  mov     [rbp+arg_10], ebx
0x18001d25a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001d25f  lea     rcx, [rbp+var_10]
0x18001d263  mov     [rbp+var_10], rsi
0x18001d267  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001d26c  mov     ecx, ebx; int
0x18001d26e  call    ?HResultToNtStatus@@YAJJ@Z; HResultToNtStatus(long)
0x18001d273  jmp     short loc_18001D2C8
0x18001d275  mov     rcx, [rbp+hKey]; hKey
0x18001d279  lea     rax, [rbp+Data]
0x18001d27d  mov     r9d, 4; dwType
0x18001d283  xor     r8d, r8d; Reserved
0x18001d286  mov     [rsp+60h+samDesired], r9d; cbData
0x18001d28b  mov     rdx, rdi; lpValueName
0x18001d28e  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18001d293  call    cs:__imp_RegSetValueExW
0x18001d29a  nop     dword ptr [rax+rax+00h]
0x18001d29f  mov     ebx, eax
0x18001d2a1  test    eax, eax
0x18001d2a3  jz      short loc_18001D2B9
0x18001d2a5  mov     ecx, cs:dword_1800BE0B8
0x18001d2ab  cmp     ecx, 2
0x18001d2ae  jbe     short loc_18001D25F
0x18001d2b0  lea     rdx, word_1800A8366
0x18001d2b7  jmp     short loc_18001D241
0x18001d2b9  lea     rcx, [rbp+var_10]
0x18001d2bd  mov     [rbp+var_10], rsi
0x18001d2c1  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001d2c6  xor     eax, eax
0x18001d2c8  mov     rbx, [rsp+60h+arg_0]
0x18001d2d0  add     rsp, 60h
0x18001d2d4  pop     rdi
0x18001d2d5  pop     rsi
0x18001d2d6  pop     rbp
0x18001d2d7  retn
```
