# FontCacheServiceConfiguration::OpenSystemFontProviderKey(void)

- ea: `0x1800a8ab4`
- end: `0x1800a8c53`
- name: `?OpenSystemFontProviderKey@FontCacheServiceConfiguration@@AEAA?AVRegistryKey@@XZ`
- size: `415`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b0b54`

## callees

- `0x18000e768`
- `0x18000f7bc`
- `0x180028c50`
- `0x180069da8`
- `0x18006ab6c`
- `0x18008e180`
- `0x1800a8ab4`
- `0x1800a98e0`
- `0x1800b8978`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a8ad1`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a8ad1`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x1800a8af0`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x1800a8af0`

## string_xrefs

- `0x1800a8b54`: `SYSTEM\CurrentControlSet\Services\FontCache\Parameters`
- `0x1800a8bde`: `FontCache`
- `0x1800a8b70`: `SystemFontProviderRegPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct DWrite::RefString::Data **__fastcall FontCacheServiceConfiguration::OpenSystemFontProviderKey(
        __int64 a1,
        struct DWrite::RefString::Data **a2)
{
  signed int ServiceRegistryStateKey; // r9d
  struct DWrite::RefString::Data *v5; // rbx
  unsigned int v6; // eax
  _QWORD v8[7]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v9; // [rsp+90h] [rbp+20h] BYREF
  struct DWrite::RefString::Data *v10; // [rsp+A0h] [rbp+30h] BYREF

  if ( !*(_QWORD *)(a1 + 32) || !(unsigned __int8)RtlIsStateSeparationEnabled() )
    goto LABEL_8;
  v10 = 0;
  ServiceRegistryStateKey = GetServiceRegistryStateKey(*(_QWORD *)(a1 + 32), 1, 131103, &v10);
  if ( ServiceRegistryStateKey )
  {
    if ( ServiceRegistryStateKey > 0 )
      ServiceRegistryStateKey = (unsigned __int16)ServiceRegistryStateKey | 0x80070000;
    EventLogger::LogEvent<long,EventTag,unsigned int>(
      a1 + 16,
      1718513475,
      1869771365,
      ServiceRegistryStateKey,
      0x79654B6E65704FLL,
      491);
LABEL_8:
    RegistryKey::RegistryKey(&v9, 2147483650LL, L"SYSTEM\\CurrentControlSet\\Services\\FontCache\\Parameters", 1);
    if ( v9 )
    {
      RegistryKey::TryGetString(&v9, &v10, L"SystemFontProviderRegPath");
      v5 = v10;
      if ( *((_DWORD *)v10 + 1) > 5u && *(_WORD *)DWrite::RefString::operator[](&v10, 4) == 92 )
      {
        v6 = RegistryKey::RegistryNameAcronymToRegistryHive((char *)v5 + 8);
        RegistryKey::RegistryKey(a2, v6, (char *)v5 + 18, 2);
LABEL_14:
        DWrite::RefString::DecrementRef(v5);
        RegistryKey::Close((RegistryKey *)&v9);
        return a2;
      }
      DWrite::RefString::DecrementRef(v5);
    }
    v8[0] = L"Software\\Microsoft\\Windows\\CurrentVersion\\";
    v8[1] = 42;
    v8[2] = L"FontCache";
    v8[3] = 9;
    v8[4] = L"\\SystemFontProvider";
    v8[5] = 19;
    DWrite::RefString::RefString(&v10, (__int64)v8);
    v5 = v10;
    RegistryKey::RegistryKey(a2, 2147483649LL, (char *)v10 + 8, 2);
    goto LABEL_14;
  }
  *a2 = v10;
  return a2;
}

```

## disassembly

```asm
0x1800a8ab4  mov     [rsp-18h+arg_8], rbx
0x1800a8ab9  push    rbp
0x1800a8aba  push    rsi
0x1800a8abb  push    rdi
0x1800a8abc  mov     rbp, rsp
0x1800a8abf  sub     rsp, 70h
0x1800a8ac3  mov     rsi, rdx
0x1800a8ac6  mov     rbx, rcx
0x1800a8ac9  xor     edi, edi
0x1800a8acb  cmp     [rcx+20h], rdi
0x1800a8acf  jz      short loc_1800A8B4E
0x1800a8ad1  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800a8ad7  test    al, al
0x1800a8ad9  jz      short loc_1800A8B4E
0x1800a8adb  mov     [rbp+arg_10], rdi
0x1800a8adf  lea     r9, [rbp+arg_10]
0x1800a8ae3  lea     edx, [rdi+1]
0x1800a8ae6  mov     r8d, 2001Fh
0x1800a8aec  mov     rcx, [rbx+20h]
0x1800a8af0  call    cs:__imp_GetServiceRegistryStateKey
0x1800a8af6  mov     r9d, eax
0x1800a8af9  test    eax, eax
0x1800a8afb  jnz     short loc_1800A8B09
0x1800a8afd  mov     rax, [rbp+arg_10]
0x1800a8b01  mov     [rsi], rax
0x1800a8b04  jmp     loc_1800A8C40
0x1800a8b09  mov     rax, 79654B6E65704Fh
0x1800a8b13  test    r9d, r9d
0x1800a8b16  jle     short loc_1800A8B23
0x1800a8b18  movzx   r9d, r9w
0x1800a8b1c  or      r9d, 80070000h
0x1800a8b23  mov     rdx, 6769666E6F43h
0x1800a8b2d  mov     r8, 726F727265h
0x1800a8b37  lea     rcx, [rbx+10h]
0x1800a8b3b  mov     [rsp+70h+var_48], 1EBh
0x1800a8b43  mov     [rsp+70h+var_50], rax
0x1800a8b48  call    ??$LogEvent@JVEventTag@@I@EventLogger@@QEBAXVEventTag@@0J0I@Z; EventLogger::LogEvent<long,EventTag,uint>(EventTag,EventTag,long,EventTag,uint)
0x1800a8b4d  nop
0x1800a8b4e  mov     r9d, 1
0x1800a8b54  lea     r8, ?FontCacheServiceConfigurationKey@@3QB_WB; "SYSTEM\\CurrentControlSet\\Services\\Fo"...
0x1800a8b5b  mov     edx, 80000002h
0x1800a8b60  lea     rcx, [rbp+arg_0]
0x1800a8b64  call    ??0RegistryKey@@QEAA@W4RegistryHive@@PEB_WW4Allow@0@@Z; RegistryKey::RegistryKey(RegistryHive,wchar_t const *,RegistryKey::Allow)
0x1800a8b69  nop
0x1800a8b6a  cmp     [rbp+arg_0], rdi
0x1800a8b6e  jz      short loc_1800A8BCB
0x1800a8b70  lea     r8, aSystemfontprov; "SystemFontProviderRegPath"
0x1800a8b77  lea     rdx, [rbp+arg_10]
0x1800a8b7b  lea     rcx, [rbp+arg_0]
0x1800a8b7f  call    ?TryGetString@RegistryKey@@QEBA?AVRefString@DWrite@@PEB_W@Z; RegistryKey::TryGetString(wchar_t const *)
0x1800a8b84  nop
0x1800a8b85  mov     rbx, [rbp+arg_10]
0x1800a8b89  cmp     dword ptr [rbx+4], 5
0x1800a8b8d  jbe     short loc_1800A8BC3
0x1800a8b8f  mov     edx, 4
0x1800a8b94  lea     rcx, [rbp+arg_10]
0x1800a8b98  call    ??ARefString@DWrite@@QEBAAEB_WI@Z; DWrite::RefString::operator[](uint)
0x1800a8b9d  cmp     word ptr [rax], 5Ch ; '\'
0x1800a8ba1  jnz     short loc_1800A8BC3
0x1800a8ba3  lea     rcx, [rbx+8]
0x1800a8ba7  call    ?RegistryNameAcronymToRegistryHive@RegistryKey@@SA?AW4RegistryHive@@PEB_W@Z; RegistryKey::RegistryNameAcronymToRegistryHive(wchar_t const *)
0x1800a8bac  lea     r8, [rbx+12h]
0x1800a8bb0  mov     r9d, 2
0x1800a8bb6  mov     edx, eax
0x1800a8bb8  mov     rcx, rsi
0x1800a8bbb  call    ??0RegistryKey@@QEAA@W4RegistryHive@@PEB_WW4Allow@0@@Z; RegistryKey::RegistryKey(RegistryHive,wchar_t const *,RegistryKey::Allow)
0x1800a8bc0  nop
0x1800a8bc1  jmp     short loc_1800A8C2E
0x1800a8bc3  mov     rcx, rbx; struct DWrite::RefString::Data *
0x1800a8bc6  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a8bcb  lea     rax, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800a8bd2  mov     [rbp+var_38], rax
0x1800a8bd6  mov     [rbp+var_30], 2Ah ; '*'
0x1800a8bde  lea     rax, ?FontCacheServiceName@@3QB_WB; "FontCache"
0x1800a8be5  mov     [rbp+var_28], rax
0x1800a8be9  mov     [rbp+var_20], 9
0x1800a8bf1  lea     rax, aSystemfontprov_0; "\\SystemFontProvider"
0x1800a8bf8  mov     [rbp+var_18], rax
0x1800a8bfc  mov     [rbp+var_10], 13h
0x1800a8c04  lea     rdx, [rbp+var_38]
0x1800a8c08  lea     rcx, [rbp+arg_10]
0x1800a8c0c  call    ??$?0V?$StringSum@V?$StringSum@PEB_WPEB_W@@PEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@V?$StringSum@PEB_WPEB_W@@PEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<StringSum<wchar_t const *,wchar_t const *>,wchar_t const *>> const &)
0x1800a8c11  nop
0x1800a8c12  mov     rbx, [rbp+arg_10]
0x1800a8c16  lea     r8, [rbx+8]
0x1800a8c1a  mov     edx, 80000001h
0x1800a8c1f  mov     r9d, 2
0x1800a8c25  mov     rcx, rsi
0x1800a8c28  call    ??0RegistryKey@@QEAA@W4RegistryHive@@PEB_WW4Allow@0@@Z; RegistryKey::RegistryKey(RegistryHive,wchar_t const *,RegistryKey::Allow)
0x1800a8c2d  nop
0x1800a8c2e  mov     rcx, rbx; struct DWrite::RefString::Data *
0x1800a8c31  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a8c36  nop
0x1800a8c37  lea     rcx, [rbp+arg_0]; this
0x1800a8c3b  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x1800a8c40  mov     rax, rsi
0x1800a8c43  mov     rbx, [rsp+70h+arg_8]
0x1800a8c4b  add     rsp, 70h
0x1800a8c4f  pop     rdi
0x1800a8c50  pop     rsi
0x1800a8c51  pop     rbp
0x1800a8c52  retn
```
