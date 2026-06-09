# RunToggleAdaptiveMode(_WHESVC_ACTION_CONFIG * const)

- ea: `0x1800453dc`
- end: `0x180045502`
- name: `?RunToggleAdaptiveMode@@YAJQEAU_WHESVC_ACTION_CONFIG@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(struct _WHESVC_ACTION_CONFIG *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012c90`

## callees

- `0x18000eacc`
- `0x18003459c`
- `0x1800394c4`
- `0x1800453dc`
- `0x180047554`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045468`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045468`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800454ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800454ba`

## pseudocode

```c
__int64 __fastcall RunToggleAdaptiveMode(struct _WHESVC_ACTION_CONFIG *const a1)
{
  signed int v1; // ebx
  __int64 v2; // rdx
  HKEY *v3; // rax
  LSTATUS v4; // eax
  __int64 v5; // rdx
  LSTATUS v6; // eax
  int phkResult; // [rsp+20h] [rbp-38h]
  int phkResulta; // [rsp+20h] [rbp-38h]
  __int128 v10; // [rsp+30h] [rbp-28h] BYREF
  __int64 v11; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  BOOL Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  v10 = 0;
  v11 = 0;
  v1 = WhesvcConfigLookupValue(a1, L"enable", &v10);
  if ( v1 >= 0 )
  {
    if ( (_DWORD)v10 != 1 )
    {
      v1 = -2147024809;
      v2 = 67;
      goto LABEL_3;
    }
    hKey = 0;
    v3 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\whesvc", 0, 0x20106u, v3);
    v1 = v4;
    if ( v4 > 0 )
      v1 = (unsigned __int16)v4 | 0x80070000;
    if ( v1 >= 0 )
    {
      Data = DWORD2(v10) != 1;
      v6 = RegSetValueExW(hKey, L"ECP_WhatIf", 0, 4u, (const BYTE *)&Data, 4u);
      v1 = v6;
      if ( v6 > 0 )
        v1 = (unsigned __int16)v6 | 0x80070000;
      if ( v1 >= 0 )
      {
        v1 = 0;
        goto LABEL_16;
      }
      v5 = 91;
    }
    else
    {
      v5 = 79;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\whesvcactions.cpp",
      (const char *)(unsigned int)v1,
      phkResulta);
LABEL_16:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return (unsigned int)v1;
  }
  v2 = 62;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v2,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\whesvcactions.cpp",
    (const char *)(unsigned int)v1,
    phkResult);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800453dc  push    rbx
0x1800453de  sub     rsp, 50h
0x1800453e2  xorps   xmm0, xmm0
0x1800453e5  lea     r8, [rsp+58h+var_28]
0x1800453ea  xor     eax, eax
0x1800453ec  lea     rdx, aEnable; "enable"
0x1800453f3  movups  [rsp+58h+var_28], xmm0
0x1800453f8  mov     [rsp+58h+var_18], rax
0x1800453fd  call    WhesvcConfigLookupValue
0x180045402  mov     ebx, eax
0x180045404  test    eax, eax
0x180045406  jns     short loc_180045426
0x180045408  mov     edx, 3Eh ; '>'; void *
0x18004540d  mov     rcx, [rsp+58h]; this
0x180045412  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\coresettinghandlers"...
0x180045419  mov     r9d, ebx; char *
0x18004541c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045421  jmp     loc_1800454FA
0x180045426  cmp     dword ptr [rsp+58h+var_28], 1
0x18004542b  jz      short loc_180045439
0x18004542d  mov     ebx, 80070057h
0x180045432  mov     edx, 43h ; 'C'
0x180045437  jmp     short loc_18004540D
0x180045439  lea     rcx, [rsp+58h+hKey]
0x18004543e  mov     [rsp+58h+hKey], 0
0x180045447  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18004544c  mov     r9d, 20106h; samDesired
0x180045452  mov     [rsp+58h+phkResult], rax; phkResult
0x180045457  xor     r8d, r8d; ulOptions
0x18004545a  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180045461  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180045468  call    cs:__imp_RegOpenKeyExW
0x18004546e  mov     ebx, eax
0x180045470  test    eax, eax
0x180045472  jle     short loc_18004547D
0x180045474  movzx   ebx, ax
0x180045477  or      ebx, 80070000h
0x18004547d  test    ebx, ebx
0x18004547f  jns     short loc_180045488
0x180045481  mov     edx, 4Fh ; 'O'
0x180045486  jmp     short loc_1800454D8
0x180045488  mov     rcx, [rsp+58h+hKey]; hKey
0x18004548d  lea     rdx, aEcpWhatif; "ECP_WhatIf"
0x180045494  xor     eax, eax
0x180045496  mov     r9d, 4; dwType
0x18004549c  cmp     dword ptr [rsp+58h+var_28+8], 1
0x1800454a1  mov     [rsp+58h+cbData], r9d; cbData
0x1800454a6  setnz   al
0x1800454a9  xor     r8d, r8d; Reserved
0x1800454ac  mov     [rsp+58h+Data], eax
0x1800454b0  lea     rax, [rsp+58h+Data]
0x1800454b5  mov     [rsp+58h+phkResult], rax; int
0x1800454ba  call    cs:__imp_RegSetValueExW
0x1800454c0  mov     ebx, eax
0x1800454c2  test    eax, eax
0x1800454c4  jle     short loc_1800454CF
0x1800454c6  movzx   ebx, ax
0x1800454c9  or      ebx, 80070000h
0x1800454cf  test    ebx, ebx
0x1800454d1  jns     short loc_1800454EE
0x1800454d3  mov     edx, 5Bh ; '['; void *
0x1800454d8  mov     rcx, [rsp+58h]; this
0x1800454dd  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\coresettinghandlers"...
0x1800454e4  mov     r9d, ebx; char *
0x1800454e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800454ec  jmp     short loc_1800454F0
0x1800454ee  xor     ebx, ebx
0x1800454f0  lea     rcx, [rsp+58h+hKey]
0x1800454f5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800454fa  mov     eax, ebx
0x1800454fc  add     rsp, 50h
0x180045500  pop     rbx
0x180045501  retn
```
