# xgc::CDeviceContext::CDeviceContext(xpsrdr::RenderState &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::shared_ptr<_devicemodeW> const &)

- ea: `0x1800244b0`
- end: `0x18002457c`
- name: `??0CDeviceContext@xgc@@QEAA@AEAURenderState@xpsrdr@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$shared_ptr@U_devicemodeW@@@5@@Z`
- size: `204`
- prototype: `__int64 __fastcall(xgc::CDeviceContext *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800176d4`

## callees

- `0x18000e15c`
- `0x180012704`
- `0x180013854`
- `0x18002421c`
- `0x180024280`
- `0x1800242e4`
- `0x1800272a0`
- `0x180027a3c`

## import_xrefs

- `GDI32!CreateDCW` at `0x1800244d3`
- `GDI32!CreateDCW` at `0x1800244d3`
- `GDI32!GetDeviceCaps` at `0x18002454f`
- `GDI32!GetDeviceCaps` at `0x180024561`
- `GDI32!GetDeviceCaps` at `0x18002454f`
- `GDI32!GetDeviceCaps` at `0x180024561`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
xgc::CDeviceContext *__fastcall xgc::CDeviceContext::CDeviceContext(xgc::CDeviceContext *this, __int64 a2, __int64 a3)
{
  const WCHAR *v4; // rax
  const DEVMODEW **v5; // r9

  *(_QWORD *)this = a2;
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
  *((_QWORD *)this + 4) = CreateDCW(0, v4, 0, *v5);
  std::deque<D2D_MATRIX_3X2_F>::deque<D2D_MATRIX_3X2_F>((char *)this + 64);
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>((char *)this + 120);
  *((_QWORD *)this + 17) = 0;
  xgc::GDIResources<HBRUSH__ *,unsigned long>::GDIResources<HBRUSH__ *,unsigned long>((char *)this + 144);
  xgc::GDIResources<HPEN__ *,KeyPen>::GDIResources<HPEN__ *,KeyPen>((char *)this + 200);
  xgc::GDIResources<HFONT__ *,tagLOGFONTW>::GDIResources<HFONT__ *,tagLOGFONTW>((char *)this + 256);
  *((_QWORD *)this + 39) = 0;
  xgc::CDeviceContext::init(this);
  *((_DWORD *)this + 2) = GetDeviceCaps(*((HDC *)this + 4), 88);
  *((_DWORD *)this + 3) = GetDeviceCaps(*((HDC *)this + 4), 90);
  xgc::CDeviceContext::SetupDeviceTransform(this);
  return this;
}

```

## disassembly

```asm
0x1800244b0  mov     [rsp+arg_0], rcx
0x1800244b5  push    rbx
0x1800244b6  sub     rsp, 20h
0x1800244ba  mov     rbx, rcx
0x1800244bd  mov     [rcx], rdx
0x1800244c0  mov     rcx, r8
0x1800244c3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800244c8  mov     r9, [r9]; pdm
0x1800244cb  xor     r8d, r8d; pszPort
0x1800244ce  mov     rdx, rax; pwszDevice
0x1800244d1  xor     ecx, ecx; pwszDriver
0x1800244d3  call    cs:__imp_CreateDCW
0x1800244d9  mov     [rbx+20h], rax
0x1800244dd  lea     rcx, [rbx+40h]
0x1800244e1  call    ??0?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@QEAA@XZ; std::deque<D2D_MATRIX_3X2_F>::deque<D2D_MATRIX_3X2_F>(void)
0x1800244e6  nop
0x1800244e7  mov     qword ptr [rbx+68h], 0
0x1800244ef  mov     qword ptr [rbx+70h], 0
0x1800244f7  lea     rcx, [rbx+78h]
0x1800244fb  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180024500  nop
0x180024501  mov     qword ptr [rbx+88h], 0
0x18002450c  lea     rcx, [rbx+90h]
0x180024513  call    ??0?$GDIResources@PEAUHBRUSH__@@K@xgc@@QEAA@XZ; xgc::GDIResources<HBRUSH__ *,ulong>::GDIResources<HBRUSH__ *,ulong>(void)
0x180024518  nop
0x180024519  lea     rcx, [rbx+0C8h]
0x180024520  call    ??0?$GDIResources@PEAUHPEN__@@UKeyPen@@@xgc@@QEAA@XZ; xgc::GDIResources<HPEN__ *,KeyPen>::GDIResources<HPEN__ *,KeyPen>(void)
0x180024525  nop
0x180024526  lea     rcx, [rbx+100h]
0x18002452d  call    ??0?$GDIResources@PEAUHFONT__@@UtagLOGFONTW@@@xgc@@QEAA@XZ; xgc::GDIResources<HFONT__ *,tagLOGFONTW>::GDIResources<HFONT__ *,tagLOGFONTW>(void)
0x180024532  nop
0x180024533  mov     qword ptr [rbx+138h], 0
0x18002453e  mov     rcx, rbx; this
0x180024541  call    ?init@CDeviceContext@xgc@@AEAAXXZ; xgc::CDeviceContext::init(void)
0x180024546  mov     edx, 58h ; 'X'; index
0x18002454b  mov     rcx, [rbx+20h]; hdc
0x18002454f  call    cs:__imp_GetDeviceCaps
0x180024555  mov     [rbx+8], eax
0x180024558  mov     edx, 5Ah ; 'Z'; index
0x18002455d  mov     rcx, [rbx+20h]; hdc
0x180024561  call    cs:__imp_GetDeviceCaps
0x180024567  mov     [rbx+0Ch], eax
0x18002456a  mov     rcx, rbx; this
0x18002456d  call    ?SetupDeviceTransform@CDeviceContext@xgc@@AEAAXXZ; xgc::CDeviceContext::SetupDeviceTransform(void)
0x180024572  nop
0x180024573  mov     rax, rbx
0x180024576  add     rsp, 20h
0x18002457a  pop     rbx
0x18002457b  retn
```
