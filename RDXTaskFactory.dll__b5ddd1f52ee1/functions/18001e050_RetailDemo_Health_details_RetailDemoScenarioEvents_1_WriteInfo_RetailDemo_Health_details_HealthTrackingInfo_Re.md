# RetailDemo::Health::details::RetailDemoScenarioEvents<1>::WriteInfo<RetailDemo::Health::details::HealthTrackingInfo>(RetailDemo::Health::details::HealthInfoHeader &,RetailDemo::Health::details::HealthTrackingInfo &,bool &,bool &,ushort const *)

- ea: `0x18001e050`
- end: `0x18001e14a`
- name: `??$WriteInfo@UHealthTrackingInfo@details@Health@RetailDemo@@@?$RetailDemoScenarioEvents@$00@details@Health@RetailDemo@@AEAAXAEAUHealthInfoHeader@123@AEAUHealthTrackingInfo@123@AEA_N2PEBG@Z`
- size: `250`
- prototype: `__int64 __fastcall(__int64, const BYTE *, HKEY, _BYTE *, _BYTE *)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001ddb8`
- `0x18001de80`
- `0x18001e4f4`
- `0x1800212d4`

## callees

- `0x18001092c`
- `0x18001e050`
- `0x18001e58c`
- `0x18001ffcc`
- `0x1800200b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e111`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e111`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e0e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e0e3`

## pseudocode

```c
__int64 __fastcall RetailDemo::Health::details::RetailDemoScenarioEvents<1>::WriteInfo<RetailDemo::Health::details::HealthTrackingInfo>(
        __int64 a1,
        const BYTE *a2,
        HKEY a3,
        _BYTE *a4,
        _BYTE *a5)
{
  __int64 result; // rax
  const WCHAR *v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // r8d
  __int64 v12; // rdx
  unsigned int dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = a3;
  result = (__int64)a5;
  if ( *a5 && *a4 )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 216);
    v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v10 )
    {
      v12 = 583;
    }
    else
    {
      v10 = RegSetValueExW(hKey, 0, 0, 3u, a2, 0xB4u);
      if ( !v10 )
      {
LABEL_8:
        *a4 = 0;
        return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      }
      v12 = 586;
    }
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)v12, v11, (const char *)v10, dwOptions);
    goto LABEL_8;
  }
  return result;
}

```

## disassembly

```asm
0x18001e050  mov     r11, rsp
0x18001e053  mov     [r11+8], rbx
0x18001e057  mov     [r11+10h], rsi
0x18001e05b  mov     [r11+18h], r8
0x18001e05f  push    rdi
0x18001e060  sub     rsp, 50h
0x18001e064  mov     rax, [rsp+58h+arg_20]
0x18001e06c  mov     rbx, r9
0x18001e06f  mov     rdi, rdx
0x18001e072  mov     rsi, rcx
0x18001e075  cmp     byte ptr [rax], 0
0x18001e078  jz      loc_18001E13A
0x18001e07e  cmp     byte ptr [r9], 0
0x18001e082  jz      loc_18001E13A
0x18001e088  xor     edx, edx
0x18001e08a  mov     qword ptr [r11+18h], 0
0x18001e092  lea     rcx, [r11+18h]
0x18001e096  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001e09b  lea     rcx, [rsi+0D8h]
0x18001e0a2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e0a7  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18001e0b0  lea     rcx, [rsp+58h+hKey]
0x18001e0b5  mov     [rsp+58h+phkResult], rcx; phkResult
0x18001e0ba  xor     r9d, r9d; lpClass
0x18001e0bd  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001e0c6  xor     r8d, r8d; Reserved
0x18001e0c9  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18001e0d1  mov     rdx, rax; lpSubKey
0x18001e0d4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e0db  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001e0e3  call    cs:__imp_RegCreateKeyExW
0x18001e0e9  test    eax, eax
0x18001e0eb  jz      short loc_18001E0F4
0x18001e0ed  mov     edx, 247h
0x18001e0f2  jmp     short loc_18001E120
0x18001e0f4  mov     rcx, [rsp+58h+hKey]; hKey
0x18001e0f9  mov     r9d, 3; dwType
0x18001e0ff  mov     [rsp+58h+samDesired], 0B4h; cbData
0x18001e107  xor     r8d, r8d; Reserved
0x18001e10a  xor     edx, edx; lpValueName
0x18001e10c  mov     qword ptr [rsp+58h+dwOptions], rdi; unsigned int
0x18001e111  call    cs:__imp_RegSetValueExW
0x18001e117  test    eax, eax
0x18001e119  jz      short loc_18001E12D
0x18001e11b  mov     edx, 24Ah; void *
0x18001e120  mov     rcx, [rsp+58h]; this
0x18001e125  mov     r9d, eax; char *
0x18001e128  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18001e12d  lea     rcx, [rsp+58h+hKey]
0x18001e132  mov     byte ptr [rbx], 0
0x18001e135  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001e13a  mov     rbx, [rsp+58h+arg_0]
0x18001e13f  mov     rsi, [rsp+58h+arg_8]
0x18001e144  add     rsp, 50h
0x18001e148  pop     rdi
0x18001e149  retn
```
