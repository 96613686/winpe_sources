# SensorGroupId::InternalSerializeObject(void)

- ea: `0x18000c6d8`
- end: `0x18000c8a9`
- name: `?InternalSerializeObject@SensorGroupId@@IEAAJXZ`
- size: `465`
- prototype: `__int64 __fastcall(SensorGroupId *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050170`
- `0x180050380`

## callees

- `0x180005fa0`
- `0x180009b74`
- `0x18000c6d8`
- `0x18000d1c4`
- `0x18000ec30`
- `0x180028d5c`
- `0x180031920`
- `0x18003491c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c7e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c884`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c892`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c7e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c884`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c892`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c83c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c83c`

## pseudocode

```c
__int64 __fastcall SensorGroupId::InternalSerializeObject(SensorGroupId *this)
{
  unsigned int v2; // edi
  int v3; // eax
  __int64 v4; // rdx
  HKEY v5; // rbx
  HKEY v6; // rbx
  const WCHAR *v7; // rdx
  LSTATUS v8; // eax
  HKEY v9; // rcx
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF
  HKEY v12; // [rsp+90h] [rbp+40h] BYREF
  char v13; // [rsp+98h] [rbp+48h] BYREF

  if ( SensorGroupId::InternalIsEmpty(this) )
  {
    v2 = -1072875850;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        308,
        &WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
        this,
        -1072875850);
    return v2;
  }
  if ( *((_BYTE *)this + 248) )
    return 0;
  v12 = 0;
  hKey = 0;
  v3 = AutoSecurityAttributes::Set(
         (PSECURITY_DESCRIPTOR *)this + 18,
         L"D:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;LS)(A;;GRGX;;;WD)(A;;GRGX;;;S-1-15-3-3845273463-1331427702-1186551195-1148109977)");
  v2 = v3;
  if ( v3 < 0 )
  {
    if ( !g_wppLevels )
    {
LABEL_9:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v12);
      return v2;
    }
    v4 = 309;
LABEL_8:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, this, v3);
    goto LABEL_9;
  }
  v3 = OpenSensorGroupRegistryKey(0, 131334, 0, &v12);
  v2 = v3;
  if ( v3 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_9;
    v4 = 310;
    goto LABEL_8;
  }
  v5 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
    RegCloseKey(v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
  }
  v6 = v12;
  v7 = (const WCHAR *)*((_QWORD *)this + 141);
  hKey = 0;
  v8 = RegCreateKeyExW(v12, v7, 0, 0, 0, 0x20106u, (const LPSECURITY_ATTRIBUTES)((char *)this + 152), &hKey, 0);
  v2 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v2 = (unsigned __int16)v8 | 0x80070000;
    if ( (v2 & 0x80000000) != 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 311, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, this, v2);
      goto LABEL_9;
    }
  }
  else
  {
    v2 = 0;
  }
  v9 = hKey;
  *((_BYTE *)this + 248) = 1;
  if ( v9 )
    RegCloseKey(v9);
  if ( v6 )
    RegCloseKey(v6);
  return v2;
}

```

## disassembly

```asm
0x18000c6d8  push    rbp
0x18000c6da  push    rbx
0x18000c6db  push    rsi
0x18000c6dc  push    rdi
0x18000c6dd  push    r14
0x18000c6df  mov     rbp, rsp
0x18000c6e2  sub     rsp, 50h
0x18000c6e6  mov     rsi, rcx
0x18000c6e9  call    ?InternalIsEmpty@SensorGroupId@@IEAA_NXZ; SensorGroupId::InternalIsEmpty(void)
0x18000c6ee  test    al, al
0x18000c6f0  jz      short loc_18000C72C
0x18000c6f2  mov     edi, 0C00D36B6h
0x18000c6f7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c6fe  jb      loc_18000C89C
0x18000c704  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c70b  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18000c712  mov     edx, 134h
0x18000c717  mov     [rsp+50h+dwOptions], edi
0x18000c71b  mov     r9, rsi
0x18000c71e  mov     rcx, [rcx+10h]
0x18000c722  call    WPP_SF_qD
0x18000c727  jmp     loc_18000C89C
0x18000c72c  cmp     byte ptr [rsi+0F8h], 0
0x18000c733  jnz     loc_18000C89A
0x18000c739  lea     r14, [rsi+90h]
0x18000c740  mov     [rbp+arg_10], 0
0x18000c748  mov     rcx, r14; this
0x18000c74b  mov     [rbp+hKey], 0
0x18000c753  lea     rdx, StringSecurityDescriptor; "D:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;LS)("...
0x18000c75a  call    ?Set@AutoSecurityAttributes@@QEAAJPEBG@Z; AutoSecurityAttributes::Set(ushort const *)
0x18000c75f  mov     edi, eax
0x18000c761  test    eax, eax
0x18000c763  jns     short loc_18000C7A8
0x18000c765  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c76c  jb      short loc_18000C791
0x18000c76e  mov     edx, 135h
0x18000c773  mov     [rsp+50h+dwOptions], eax
0x18000c777  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c77e  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18000c785  mov     r9, rsi
0x18000c788  mov     rcx, [rcx+10h]
0x18000c78c  call    WPP_SF_qD
0x18000c791  lea     rcx, [rbp+hKey]
0x18000c795  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000c79a  lea     rcx, [rbp+arg_10]
0x18000c79e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000c7a3  jmp     loc_18000C89C
0x18000c7a8  lea     r9, [rbp+arg_10]; HKEY *
0x18000c7ac  xor     r8d, r8d; bool *
0x18000c7af  mov     edx, 20106h; unsigned int
0x18000c7b4  xor     ecx, ecx; unsigned __int16 *
0x18000c7b6  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x18000c7bb  mov     edi, eax
0x18000c7bd  test    eax, eax
0x18000c7bf  jns     short loc_18000C7D1
0x18000c7c1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c7c8  jb      short loc_18000C791
0x18000c7ca  mov     edx, 136h
0x18000c7cf  jmp     short loc_18000C773
0x18000c7d1  mov     rbx, [rbp+hKey]
0x18000c7d5  test    rbx, rbx
0x18000c7d8  jz      short loc_18000C7F5
0x18000c7da  lea     rcx, [rbp+arg_18]; this
0x18000c7de  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000c7e3  mov     rcx, rbx; hKey
0x18000c7e6  call    cs:__imp_RegCloseKey
0x18000c7ec  lea     rcx, [rbp+arg_18]; this
0x18000c7f0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000c7f5  mov     rbx, [rbp+arg_10]
0x18000c7f9  lea     rcx, [rbp+hKey]
0x18000c7fd  mov     rdx, [rsi+468h]; lpSubKey
0x18000c804  lea     rax, [r14+8]
0x18000c808  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x18000c811  xor     r9d, r9d; lpClass
0x18000c814  mov     [rsp+50h+phkResult], rcx; phkResult
0x18000c819  xor     r8d, r8d; Reserved
0x18000c81c  mov     [rsp+50h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18000c821  mov     rcx, rbx; hKey
0x18000c824  mov     [rsp+50h+samDesired], 20106h; samDesired
0x18000c82c  mov     [rsp+50h+dwOptions], 0; dwOptions
0x18000c834  mov     [rbp+hKey], 0
0x18000c83c  call    cs:__imp_RegCreateKeyExW
0x18000c842  mov     edi, eax
0x18000c844  test    eax, eax
0x18000c846  jz      short loc_18000C872
0x18000c848  jle     short loc_18000C853
0x18000c84a  movzx   edi, ax
0x18000c84d  or      edi, 80070000h
0x18000c853  test    edi, edi
0x18000c855  jns     short loc_18000C874
0x18000c857  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c85e  jb      loc_18000C791
0x18000c864  mov     edx, 137h
0x18000c869  mov     [rsp+50h+dwOptions], edi
0x18000c86d  jmp     loc_18000C777
0x18000c872  xor     edi, edi
0x18000c874  mov     rcx, [rbp+hKey]; hKey
0x18000c878  mov     byte ptr [rsi+0F8h], 1
0x18000c87f  test    rcx, rcx
0x18000c882  jz      short loc_18000C88A
0x18000c884  call    cs:__imp_RegCloseKey
0x18000c88a  test    rbx, rbx
0x18000c88d  jz      short loc_18000C89C
0x18000c88f  mov     rcx, rbx; hKey
0x18000c892  call    cs:__imp_RegCloseKey
0x18000c898  jmp     short loc_18000C89C
0x18000c89a  xor     edi, edi
0x18000c89c  mov     eax, edi
0x18000c89e  add     rsp, 50h
0x18000c8a2  pop     r14
0x18000c8a4  pop     rdi
0x18000c8a5  pop     rsi
0x18000c8a6  pop     rbx
0x18000c8a7  pop     rbp
0x18000c8a8  retn
```
