# xpsrdr::CreateWICImageFactory(void)

- ea: `0x180033c88`
- end: `0x180033d27`
- name: `?CreateWICImageFactory@xpsrdr@@YA?AV?$shared_ptr@UIWICImagingFactory@@@std@@XZ`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e25c`

## callees

- `0x18000e15c`
- `0x18000e4c4`
- `0x180033c88`
- `0x180037278`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180033cec`
- `ole32!CoCreateInstance` at `0x180033cec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall xpsrdr::CreateWICImageFactory(__int64 a1)
{
  void *v2; // rcx
  HRESULT Instance; // ebx
  int v4; // edx
  const char *v5; // r8
  int v6; // r9d
  LPVOID ppv[4]; // [rsp+38h] [rbp-20h] BYREF
  xpsrdr *v9; // [rsp+68h] [rbp+10h] BYREF

  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(a1);
  LODWORD(v9) = 0;
  ppv[0] = 0;
  ppv[1] = &v9;
  ppv[2] = v2;
  Instance = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, ppv);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(ppv);
  if ( (int)v9 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v9, v4, v5, v6);
  if ( Instance < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)Instance, v4, v5, v6);
  return a1;
}

```

## disassembly

```asm
0x180033c88  mov     [rsp+arg_10], rbx
0x180033c8d  mov     [rsp+arg_0], rcx
0x180033c92  push    rdi
0x180033c93  sub     rsp, 50h
0x180033c97  mov     rdi, rcx
0x180033c9a  mov     [rsp+58h+var_28], 0
0x180033ca2  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180033ca7  mov     r8d, 1; dwClsContext
0x180033cad  mov     [rsp+58h+var_28], r8d
0x180033cb2  mov     dword ptr [rsp+58h+arg_8], 0
0x180033cba  mov     [rsp+58h+var_20], 0
0x180033cc3  lea     rax, [rsp+58h+arg_8]
0x180033cc8  mov     [rsp+58h+var_18], rax
0x180033ccd  mov     [rsp+58h+var_10], rcx
0x180033cd2  lea     rax, [rsp+58h+var_20]
0x180033cd7  mov     [rsp+58h+ppv], rax; ppv
0x180033cdc  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180033ce3  xor     edx, edx; pUnkOuter
0x180033ce5  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180033cec  call    cs:__imp_CoCreateInstance
0x180033cf2  mov     ebx, eax
0x180033cf4  lea     rcx, [rsp+58h+var_20]
0x180033cf9  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180033cfe  mov     ecx, dword ptr [rsp+58h+arg_8]; this
0x180033d02  test    ecx, ecx
0x180033d04  jns     short loc_180033D0C
0x180033d06  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180033d0c  test    ebx, ebx
0x180033d0e  jns     short loc_180033D18
0x180033d10  mov     ecx, ebx; this
0x180033d12  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180033d18  mov     rax, rdi
0x180033d1b  mov     rbx, [rsp+58h+arg_10]
0x180033d20  add     rsp, 50h
0x180033d24  pop     rdi
0x180033d25  retn
```
