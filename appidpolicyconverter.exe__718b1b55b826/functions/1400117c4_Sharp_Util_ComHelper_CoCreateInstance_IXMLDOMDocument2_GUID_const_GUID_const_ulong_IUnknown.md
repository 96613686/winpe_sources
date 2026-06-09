# Sharp::Util::ComHelper::CoCreateInstance<IXMLDOMDocument2>(_GUID const &,_GUID const &,ulong,IUnknown *)

- ea: `0x1400117c4`
- end: `0x140011880`
- name: `??$CoCreateInstance@UIXMLDOMDocument2@@@ComHelper@Util@Sharp@@YA?AV?$CComPtr@UIXMLDOMDocument2@@@ATL@@AEBU_GUID@@0KPEAUIUnknown@@@Z`
- size: `188`
- prototype: `LPVOID *__fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400118bc`

## callees

- `0x140001d1c`
- `0x1400099b4`
- `0x140009d04`
- `0x1400117c4`
- `0x140013b10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001181a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001181a`

## pseudocode

```c
LPVOID *__fastcall Sharp::Util::ComHelper::CoCreateInstance<IXMLDOMDocument2>(LPVOID *ppv)
{
  HRESULT Instance; // edi
  _BYTE v4[32]; // [rsp+40h] [rbp-78h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+60h] [rbp-58h] BYREF

  *ppv = 0;
  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               1u,
               &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
               ppv);
  if ( Instance < 0 )
  {
    std::wstring::wstring(v4, &dword_140018714);
    Sharp::Util::standard_exception::standard_exception(pExceptionObject, (unsigned int)Instance, v4);
    throw (Sharp::Util::standard_exception *)pExceptionObject;
  }
  return ppv;
}

```

## disassembly

```asm
0x1400117c4  mov     [rsp+arg_8], rbx
0x1400117c9  push    rdi
0x1400117ca  sub     rsp, 0B0h
0x1400117d1  mov     rax, cs:__security_cookie
0x1400117d8  xor     rax, rsp
0x1400117db  mov     [rsp+0B8h+var_18], rax
0x1400117e3  mov     rbx, rcx
0x1400117e6  mov     [rsp+0B8h+var_80], rcx
0x1400117eb  mov     [rsp+0B8h+var_88], 0
0x1400117f3  mov     qword ptr [rcx], 0
0x1400117fa  mov     r8d, 1; dwClsContext
0x140011800  mov     [rsp+0B8h+var_88], r8d
0x140011805  mov     [rsp+0B8h+ppv], rcx; ppv
0x14001180a  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x140011811  xor     edx, edx; pUnkOuter
0x140011813  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x14001181a  call    cs:__imp_CoCreateInstance
0x140011820  mov     edi, eax
0x140011822  test    eax, eax
0x140011824  jns     short loc_14001185B
0x140011826  lea     rdx, dword_140018714
0x14001182d  lea     rcx, [rsp+0B8h+var_78]
0x140011832  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140011837  nop
0x140011838  lea     r8, [rsp+0B8h+var_78]
0x14001183d  mov     edx, edi
0x14001183f  lea     rcx, [rsp+0B8h+pExceptionObject]
0x140011844  call    ??0standard_exception@Util@Sharp@@QEAA@JAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::standard_exception::standard_exception(long,std::wstring const &)
0x140011849  lea     rdx, _TI2?AVstandard_exception@Util@Sharp@@; pThrowInfo
0x140011850  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x140011855  call    _CxxThrowException_0
0x14001185b  mov     rax, rbx
0x14001185e  mov     rcx, [rsp+0B8h+var_18]
0x140011866  xor     rcx, rsp; StackCookie
0x140011869  call    __security_check_cookie
0x14001186e  mov     rbx, [rsp+0B8h+arg_8]
0x140011876  add     rsp, 0B0h
0x14001187d  pop     rdi
0x14001187e  retn
```
