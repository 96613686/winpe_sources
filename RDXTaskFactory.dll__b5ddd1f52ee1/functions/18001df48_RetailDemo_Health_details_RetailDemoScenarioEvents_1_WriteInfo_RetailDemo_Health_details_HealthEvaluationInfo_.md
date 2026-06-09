# RetailDemo::Health::details::RetailDemoScenarioEvents<1>::WriteInfo<RetailDemo::Health::details::HealthEvaluationInfo>(RetailDemo::Health::details::HealthInfoHeader &,RetailDemo::Health::details::HealthEvaluationInfo &,bool &,bool &,ushort const *)

- ea: `0x18001df48`
- end: `0x18001e047`
- name: `??$WriteInfo@UHealthEvaluationInfo@details@Health@RetailDemo@@@?$RetailDemoScenarioEvents@$00@details@Health@RetailDemo@@AEAAXAEAUHealthInfoHeader@123@AEAUHealthEvaluationInfo@123@AEA_N2PEBG@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, const BYTE *, HKEY, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001e4f4`

## callees

- `0x18001092c`
- `0x18001df48`
- `0x18001e58c`
- `0x18001ffcc`
- `0x1800200b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e00e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e00e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001dfdb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001dfdb`

## pseudocode

```c
__int64 __fastcall RetailDemo::Health::details::RetailDemoScenarioEvents<1>::WriteInfo<RetailDemo::Health::details::HealthEvaluationInfo>(
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
      v10 = RegSetValueExW(hKey, L"HealthEvaluation", 0, 3u, a2, 0x14u);
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
0x18001df48  mov     r11, rsp
0x18001df4b  mov     [r11+8], rbx
0x18001df4f  mov     [r11+10h], rsi
0x18001df53  mov     [r11+18h], r8
0x18001df57  push    rdi
0x18001df58  sub     rsp, 50h
0x18001df5c  mov     rax, [rsp+58h+arg_20]
0x18001df64  mov     rbx, r9
0x18001df67  mov     rdi, rdx
0x18001df6a  mov     rsi, rcx
0x18001df6d  cmp     byte ptr [rax], 0
0x18001df70  jz      loc_18001E037
0x18001df76  cmp     byte ptr [r9], 0
0x18001df7a  jz      loc_18001E037
0x18001df80  xor     edx, edx
0x18001df82  mov     qword ptr [r11+18h], 0
0x18001df8a  lea     rcx, [r11+18h]
0x18001df8e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001df93  lea     rcx, [rsi+0D8h]
0x18001df9a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001df9f  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18001dfa8  lea     rcx, [rsp+58h+hKey]
0x18001dfad  mov     [rsp+58h+phkResult], rcx; phkResult
0x18001dfb2  xor     r9d, r9d; lpClass
0x18001dfb5  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001dfbe  xor     r8d, r8d; Reserved
0x18001dfc1  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18001dfc9  mov     rdx, rax; lpSubKey
0x18001dfcc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001dfd3  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001dfdb  call    cs:__imp_RegCreateKeyExW
0x18001dfe1  test    eax, eax
0x18001dfe3  jz      short loc_18001DFEC
0x18001dfe5  mov     edx, 247h
0x18001dfea  jmp     short loc_18001E01D
0x18001dfec  mov     rcx, [rsp+58h+hKey]; hKey
0x18001dff1  lea     rdx, ?c_retailDemoValueHealthEvaluation@@3QBGB; "HealthEvaluation"
0x18001dff8  mov     [rsp+58h+samDesired], 14h; cbData
0x18001e000  mov     r9d, 3; dwType
0x18001e006  xor     r8d, r8d; Reserved
0x18001e009  mov     qword ptr [rsp+58h+dwOptions], rdi; unsigned int
0x18001e00e  call    cs:__imp_RegSetValueExW
0x18001e014  test    eax, eax
0x18001e016  jz      short loc_18001E02A
0x18001e018  mov     edx, 24Ah; void *
0x18001e01d  mov     rcx, [rsp+58h]; this
0x18001e022  mov     r9d, eax; char *
0x18001e025  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18001e02a  lea     rcx, [rsp+58h+hKey]
0x18001e02f  mov     byte ptr [rbx], 0
0x18001e032  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001e037  mov     rbx, [rsp+58h+arg_0]
0x18001e03c  mov     rsi, [rsp+58h+arg_8]
0x18001e041  add     rsp, 50h
0x18001e045  pop     rdi
0x18001e046  retn
```
