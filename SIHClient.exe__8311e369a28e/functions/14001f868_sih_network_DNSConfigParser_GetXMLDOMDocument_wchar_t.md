# sih::network::DNSConfigParser::GetXMLDOMDocument(wchar_t *)

- ea: `0x14001f868`
- end: `0x14001fa71`
- name: `?GetXMLDOMDocument@DNSConfigParser@network@sih@@AEAAPEAUIXMLDOMDocument2@@PEA_W@Z`
- size: `521`
- prototype: `struct IXMLDOMDocument2 *__fastcall(sih::network::DNSConfigParser *__hidden this, wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001ee7c`
- `0x14001f0f8`

## callees

- `0x1400154b4`
- `0x14001f868`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001f8b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001f8b6`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f993`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f9e6`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f993`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f9e6`

## string_xrefs

- `0x14001fa27`: `sih::network::DNSConfigParser::GetXMLDOMDocument`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct IXMLDOMDocument2 *__fastcall sih::network::DNSConfigParser::GetXMLDOMDocument(
        sih::network::DNSConfigParser *this,
        wchar_t *a2)
{
  HRESULT v3; // ebx
  int v4; // eax
  LPVOID v5; // rbx
  LPVOID v6; // rcx
  __int64 v7; // rbx
  unsigned int (__fastcall *v8)(__int64, BSTR *); // rdi
  __int64 v10; // [rsp+20h] [rbp-50h]
  __int16 v11; // [rsp+40h] [rbp-30h] BYREF
  LPVOID v12; // [rsp+48h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-20h] BYREF
  __int64 v14; // [rsp+58h] [rbp-18h] BYREF

  v11 = 0;
  v12 = 0;
  v3 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &v12);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v12 + 504LL))(v12, 0);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v12 + 544LL))(v12, 0);
      if ( v3 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v12 + 560LL))(v12, 0);
        if ( v3 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(LPVOID, wchar_t *, __int16 *))(*(_QWORD *)v12 + 520LL))(v12, a2, &v11);
          v3 = v4;
          if ( !v11 || v4 == 1 )
          {
            v14 = 0;
            bstrString = 0;
            if ( !(*(unsigned int (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v12 + 480LL))(v12, &v14) )
            {
              v7 = v14;
              v8 = *(unsigned int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v14 + 72LL);
              SysFreeString(bstrString);
              bstrString = 0;
              if ( !v8(v7, &bstrString) )
                WUTrace(0, 0, 0x400000, 3, 0, L"Parse error reason %ws");
            }
            v3 = -2145103871;
            SysFreeString(bstrString);
            bstrString = 0;
            if ( v14 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          }
          else if ( v4 >= 0 )
          {
            v5 = v12;
            v6 = 0;
            v12 = 0;
            goto LABEL_15;
          }
        }
      }
    }
  }
  LODWORD(v10) = v3;
  WUTrace("sih::network::DNSConfigParser::GetXMLDOMDocument", 238, 0x400000, 1, v10, &OutputString);
  v5 = 0;
  v6 = v12;
LABEL_15:
  if ( v6 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  return (struct IXMLDOMDocument2 *)v5;
}

```

## disassembly

```asm
0x14001f868  mov     r11, rsp
0x14001f86b  mov     [r11+8], rbx
0x14001f86f  mov     [r11+18h], rsi
0x14001f873  mov     [r11+20h], rdi
0x14001f877  push    rbp
0x14001f878  mov     rbp, rsp
0x14001f87b  sub     rsp, 70h
0x14001f87f  mov     rax, cs:__security_cookie
0x14001f886  xor     rax, rsp
0x14001f889  mov     [rbp+var_10], rax
0x14001f88d  mov     rdi, rdx
0x14001f890  xor     esi, esi
0x14001f892  mov     [rbp+var_30], si
0x14001f896  mov     [rbp+var_28], rsi
0x14001f89a  lea     rax, [rbp+var_28]
0x14001f89e  mov     [r11-58h], rax
0x14001f8a2  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x14001f8a9  xor     edx, edx; pUnkOuter
0x14001f8ab  lea     r8d, [rsi+1]; dwClsContext
0x14001f8af  lea     rcx, CLSID_DOMDocument60; rclsid
0x14001f8b6  call    cs:__imp_CoCreateInstance
0x14001f8bc  mov     ebx, eax
0x14001f8be  test    eax, eax
0x14001f8c0  js      loc_14001FA06
0x14001f8c6  xor     edx, edx
0x14001f8c8  mov     rcx, [rbp+var_28]
0x14001f8cc  mov     rax, [rcx]
0x14001f8cf  mov     rax, [rax+1F8h]
0x14001f8d6  call    _guard_dispatch_icall
0x14001f8db  mov     ebx, eax
0x14001f8dd  test    eax, eax
0x14001f8df  js      loc_14001FA06
0x14001f8e5  xor     edx, edx
0x14001f8e7  mov     rcx, [rbp+var_28]
0x14001f8eb  mov     rax, [rcx]
0x14001f8ee  mov     rax, [rax+220h]
0x14001f8f5  call    _guard_dispatch_icall
0x14001f8fa  mov     ebx, eax
0x14001f8fc  test    eax, eax
0x14001f8fe  js      loc_14001FA06
0x14001f904  xor     edx, edx
0x14001f906  mov     rcx, [rbp+var_28]
0x14001f90a  mov     rax, [rcx]
0x14001f90d  mov     rax, [rax+230h]
0x14001f914  call    _guard_dispatch_icall
0x14001f919  mov     ebx, eax
0x14001f91b  test    eax, eax
0x14001f91d  js      loc_14001FA06
0x14001f923  mov     rcx, [rbp+var_28]
0x14001f927  mov     rax, [rcx]
0x14001f92a  lea     r8, [rbp+var_30]
0x14001f92e  mov     rdx, rdi
0x14001f931  mov     rax, [rax+208h]
0x14001f938  call    _guard_dispatch_icall
0x14001f93d  mov     ebx, eax
0x14001f93f  cmp     [rbp+var_30], si
0x14001f943  jz      short loc_14001F961
0x14001f945  cmp     eax, 1
0x14001f948  jz      short loc_14001F961
0x14001f94a  test    eax, eax
0x14001f94c  js      loc_14001FA06
0x14001f952  mov     rbx, [rbp+var_28]
0x14001f956  mov     ecx, esi
0x14001f958  mov     [rbp+var_28], rcx
0x14001f95c  jmp     loc_14001FA3A
0x14001f961  mov     [rbp+var_18], rsi
0x14001f965  mov     [rbp+bstrString], rsi
0x14001f969  mov     rcx, [rbp+var_28]
0x14001f96d  mov     rax, [rcx]
0x14001f970  lea     rdx, [rbp+var_18]
0x14001f974  mov     rax, [rax+1E0h]
0x14001f97b  call    _guard_dispatch_icall
0x14001f980  test    eax, eax
0x14001f982  jnz     short loc_14001F9DD
0x14001f984  mov     rbx, [rbp+var_18]
0x14001f988  mov     rax, [rbx]
0x14001f98b  mov     rdi, [rax+48h]
0x14001f98f  mov     rcx, [rbp+bstrString]; bstrString
0x14001f993  call    cs:__imp_SysFreeString
0x14001f999  mov     [rbp+bstrString], rsi
0x14001f99d  lea     rdx, [rbp+bstrString]
0x14001f9a1  mov     rcx, rbx
0x14001f9a4  mov     rax, rdi
0x14001f9a7  call    _guard_dispatch_icall
0x14001f9ac  test    eax, eax
0x14001f9ae  jnz     short loc_14001F9DD
0x14001f9b0  mov     rax, [rbp+bstrString]
0x14001f9b4  mov     [rsp+70h+var_40], rax
0x14001f9b9  lea     rax, aParseErrorReas; "Parse error reason %ws"
0x14001f9c0  mov     [rsp+70h+var_48], rax
0x14001f9c5  mov     [rsp+70h+var_50], rsi
0x14001f9ca  xor     edx, edx
0x14001f9cc  xor     ecx, ecx
0x14001f9ce  lea     r9d, [rdx+3]
0x14001f9d2  mov     r8d, 400000h
0x14001f9d8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001f9dd  mov     ebx, 80245001h
0x14001f9e2  mov     rcx, [rbp+bstrString]; bstrString
0x14001f9e6  call    cs:__imp_SysFreeString
0x14001f9ec  mov     [rbp+bstrString], rsi
0x14001f9f0  mov     rcx, [rbp+var_18]
0x14001f9f4  test    rcx, rcx
0x14001f9f7  jz      short loc_14001FA06
0x14001f9f9  mov     rax, [rcx]
0x14001f9fc  mov     rax, [rax+10h]
0x14001fa00  call    _guard_dispatch_icall
0x14001fa05  nop
0x14001fa06  lea     rax, OutputString
0x14001fa0d  mov     [rsp+70h+var_48], rax
0x14001fa12  mov     dword ptr [rsp+70h+var_50], ebx
0x14001fa16  mov     edx, 0EEh
0x14001fa1b  mov     r9d, 1
0x14001fa21  mov     r8d, 400000h
0x14001fa27  lea     rcx, aSihNetworkDnsc_3; "sih::network::DNSConfigParser::GetXMLDO"...
0x14001fa2e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001fa33  mov     rbx, rsi
0x14001fa36  mov     rcx, [rbp+var_28]
0x14001fa3a  test    rcx, rcx
0x14001fa3d  jz      short loc_14001FA4C
0x14001fa3f  mov     rdx, [rcx]
0x14001fa42  mov     rax, [rdx+10h]
0x14001fa46  call    _guard_dispatch_icall
0x14001fa4b  nop
0x14001fa4c  mov     rax, rbx
0x14001fa4f  mov     rcx, [rbp+var_10]
0x14001fa53  xor     rcx, rsp; StackCookie
0x14001fa56  call    __security_check_cookie
0x14001fa5b  lea     r11, [rsp+70h+var_s0]
0x14001fa60  mov     rbx, [r11+10h]
0x14001fa64  mov     rsi, [r11+20h]
0x14001fa68  mov     rdi, [r11+28h]
0x14001fa6c  mov     rsp, r11
0x14001fa6f  pop     rbp
0x14001fa70  retn
```
