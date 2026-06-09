# CBcdWmiWrapper::InitializeNamespace(void)

- ea: `0x18000bd50`
- end: `0x18000be83`
- name: `?InitializeNamespace@CBcdWmiWrapper@@AEAAJXZ`
- size: `307`
- prototype: `__int64 __fastcall(CBcdWmiWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bae0`

## callees

- `0x18000bd50`
- `0x180015010`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x18000be3a`
- `ole32!CoSetProxyBlanket` at `0x18000be3a`
- `ole32!CoCreateInstance` at `0x18000bd8d`
- `ole32!CoCreateInstance` at `0x18000bd8d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bda4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bda4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000be69`
- `OLEAUT32!__imp_SysFreeString` at `0x180013e47`
- `OLEAUT32!__imp_SysFreeString` at `0x18000be69`
- `OLEAUT32!__imp_SysFreeString` at `0x180013e47`

## pseudocode

```c
__int64 __fastcall CBcdWmiWrapper::InitializeNamespace(CBcdWmiWrapper *this)
{
  OLECHAR *v2; // rbx
  HRESULT v3; // edi
  IUnknown **v4; // rsi
  LPVOID v6; // [rsp+78h] [rbp+10h] BYREF

  v6 = 0;
  v2 = 0;
  v3 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &v6);
  if ( v3 >= 0 )
  {
    v2 = SysAllocString(L"\\\\.\\Root\\WMI");
    if ( v2 )
    {
      v4 = (IUnknown **)((char *)this + 16);
      v3 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD, _QWORD, _QWORD, int, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)v6 + 24LL))(
             v6,
             v2,
             0,
             0,
             0,
             128,
             0,
             0,
             v4);
      if ( v3 >= 0 )
        v3 = CoSetProxyBlanket(*v4, 0xFFFFFFFF, 0, 0, 6u, 3u, 0, 0);
    }
    else
    {
      v3 = -2147024882;
    }
  }
  if ( v6 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
    v6 = 0;
  }
  if ( v2 )
    SysFreeString(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000bd50  mov     r11, rsp
0x18000bd53  mov     [r11+8], rbx
0x18000bd57  mov     [r11+18h], rsi
0x18000bd5b  push    rdi
0x18000bd5c  sub     rsp, 60h
0x18000bd60  mov     rsi, rcx
0x18000bd63  mov     qword ptr [r11+10h], 0
0x18000bd6b  xor     ebx, ebx
0x18000bd6d  mov     [r11-18h], rbx
0x18000bd71  lea     rax, [r11+10h]
0x18000bd75  mov     [r11-48h], rax
0x18000bd79  lea     r9, IID_IWbemLocator; riid
0x18000bd80  xor     edx, edx; pUnkOuter
0x18000bd82  lea     r8d, [rbx+1]; dwClsContext
0x18000bd86  lea     rcx, CLSID_WbemLocator; rclsid
0x18000bd8d  call    cs:__imp_CoCreateInstance
0x18000bd93  mov     edi, eax
0x18000bd95  test    eax, eax
0x18000bd97  js      loc_18000BE42
0x18000bd9d  lea     rcx, aRootWmi; "\\\\.\\Root\\WMI"
0x18000bda4  call    cs:__imp_SysAllocString
0x18000bdaa  mov     rbx, rax
0x18000bdad  mov     [rsp+68h+var_18], rax
0x18000bdb2  test    rax, rax
0x18000bdb5  jnz     short loc_18000BDC1
0x18000bdb7  mov     edi, 8007000Eh
0x18000bdbc  jmp     loc_18000BE42
0x18000bdc1  add     rsi, 10h
0x18000bdc5  mov     rcx, [rsp+68h+arg_8]
0x18000bdca  mov     rax, [rcx]
0x18000bdcd  mov     [rsp+68h+var_28], rsi
0x18000bdd2  mov     qword ptr [rsp+68h+dwCapabilities], 0
0x18000bddb  mov     [rsp+68h+pAuthInfo], 0
0x18000bde4  mov     [rsp+68h+dwImpLevel], 80h
0x18000bdec  mov     qword ptr [rsp+68h+dwAuthnLevel], 0
0x18000bdf5  xor     r9d, r9d
0x18000bdf8  xor     r8d, r8d
0x18000bdfb  mov     rdx, rbx
0x18000bdfe  mov     rax, [rax+18h]
0x18000be02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be07  mov     edi, eax
0x18000be09  test    eax, eax
0x18000be0b  js      short loc_18000BE42
0x18000be0d  mov     [rsp+68h+dwCapabilities], 0; dwCapabilities
0x18000be15  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x18000be1e  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x18000be26  mov     [rsp+68h+dwAuthnLevel], 6; dwAuthnLevel
0x18000be2e  xor     r9d, r9d; pServerPrincName
0x18000be31  xor     r8d, r8d; dwAuthzSvc
0x18000be34  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000be37  mov     rcx, [rsi]; pProxy
0x18000be3a  call    cs:__imp_CoSetProxyBlanket
0x18000be40  mov     edi, eax
0x18000be42  mov     rcx, [rsp+68h+arg_8]
0x18000be47  test    rcx, rcx
0x18000be4a  jz      short loc_18000BE61
0x18000be4c  mov     rax, [rcx]
0x18000be4f  mov     rax, [rax+10h]
0x18000be53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be58  mov     [rsp+68h+arg_8], 0
0x18000be61  test    rbx, rbx
0x18000be64  jz      short loc_18000BE6F
0x18000be66  mov     rcx, rbx; bstrString
0x18000be69  call    cs:__imp_SysFreeString
0x18000be6f  mov     eax, edi
0x18000be71  lea     r11, [rsp+68h+var_8]
0x18000be76  mov     rbx, [r11+10h]
0x18000be7a  mov     rsi, [r11+20h]
0x18000be7e  mov     rsp, r11
0x18000be81  pop     rdi
0x18000be82  retn
0x180013e18  push    rbp
0x180013e1a  sub     rsp, 50h
0x180013e1e  mov     rbp, rdx
0x180013e21  mov     rcx, [rbp+78h]
0x180013e25  test    rcx, rcx
0x180013e28  jz      short loc_180013E3E
0x180013e2a  mov     rax, [rcx]
0x180013e2d  mov     rax, [rax+10h]
0x180013e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e36  mov     qword ptr [rbp+78h], 0
0x180013e3e  mov     rcx, [rbp+50h]; bstrString
0x180013e42  test    rcx, rcx
0x180013e45  jz      short loc_180013E55
0x180013e47  call    cs:__imp_SysFreeString
0x180013e4d  mov     qword ptr [rbp+50h], 0
0x180013e55  add     rsp, 50h
0x180013e59  pop     rbp
0x180013e5a  retn
```
