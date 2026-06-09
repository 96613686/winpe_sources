# xpsrdr::CreateWICImageFactory(void)

- ea: `0x1800aa594`
- end: `0x1800aa637`
- name: `?CreateWICImageFactory@xpsrdr@@YA?AV?$shared_ptr@UIWICImagingFactory@@@std@@XZ`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a8334`
- `0x1800a848c`

## callees

- `0x1800a2c1c`
- `0x1800aa594`
- `0x1800b20e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800aa5fc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800aa5fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall xpsrdr::CreateWICImageFactory(_QWORD *a1)
{
  HRESULT Instance; // edi
  int v3; // edx
  const char *v4; // r8
  int v5; // r9d
  LPVOID v7[4]; // [rsp+38h] [rbp-20h] BYREF
  xpsrdr *v8; // [rsp+68h] [rbp+10h] BYREF

  *a1 = 0;
  a1[1] = 0;
  LODWORD(v8) = 0;
  v7[0] = 0;
  v7[1] = &v8;
  v7[2] = a1;
  Instance = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, v7);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v7);
  if ( (int)v8 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v8, v3, v4, v5);
  if ( Instance < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)Instance, v3, v4, v5);
  return a1;
}

```

## disassembly

```asm
0x1800aa594  mov     r11, rsp
0x1800aa597  mov     [r11+18h], rbx
0x1800aa59b  mov     [r11+8], rcx
0x1800aa59f  push    rdi
0x1800aa5a0  sub     rsp, 50h
0x1800aa5a4  mov     rbx, rcx
0x1800aa5a7  mov     [rsp+58h+var_28], 0
0x1800aa5af  mov     qword ptr [rcx], 0
0x1800aa5b6  mov     qword ptr [rcx+8], 0
0x1800aa5be  mov     r8d, 1; dwClsContext
0x1800aa5c4  mov     [r11-28h], r8d
0x1800aa5c8  mov     dword ptr [rsp+58h+arg_8], 0
0x1800aa5d0  mov     qword ptr [r11-20h], 0
0x1800aa5d8  lea     rax, [r11+10h]
0x1800aa5dc  mov     [r11-18h], rax
0x1800aa5e0  mov     [r11-10h], rcx
0x1800aa5e4  lea     rax, [r11-20h]
0x1800aa5e8  mov     [r11-38h], rax
0x1800aa5ec  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x1800aa5f3  xor     edx, edx; pUnkOuter
0x1800aa5f5  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x1800aa5fc  call    cs:__imp_CoCreateInstance
0x1800aa602  mov     edi, eax
0x1800aa604  lea     rcx, [rsp+58h+var_20]
0x1800aa609  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800aa60e  mov     ecx, dword ptr [rsp+58h+arg_8]; this
0x1800aa612  test    ecx, ecx
0x1800aa614  jns     short loc_1800AA61C
0x1800aa616  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800aa61c  test    edi, edi
0x1800aa61e  jns     short loc_1800AA628
0x1800aa620  mov     ecx, edi; this
0x1800aa622  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800aa628  mov     rax, rbx
0x1800aa62b  mov     rbx, [rsp+58h+arg_10]
0x1800aa630  add     rsp, 50h
0x1800aa634  pop     rdi
0x1800aa635  retn
```
