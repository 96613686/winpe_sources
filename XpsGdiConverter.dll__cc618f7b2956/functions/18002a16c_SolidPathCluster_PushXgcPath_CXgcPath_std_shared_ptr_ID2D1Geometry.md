# SolidPathCluster::PushXgcPath(CXgcPath *,std::shared_ptr<ID2D1Geometry>)

- ea: `0x18002a16c`
- end: `0x18002a28b`
- name: `?PushXgcPath@SolidPathCluster@@QEAAXPEAVCXgcPath@@V?$shared_ptr@UID2D1Geometry@@@std@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(SolidPathCluster *this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800169f4`

## callees

- `0x18000e15c`
- `0x18000e934`
- `0x18000e990`
- `0x180011b0c`
- `0x180028acc`
- `0x18002a16c`
- `0x18002a518`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
double __fastcall SolidPathCluster::PushXgcPath(SolidPathCluster *this, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rdx
  int v9; // r8d
  __int64 SolidPath; // rax
  __int64 v11; // rax
  _BYTE v13[16]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v14[16]; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v15[24]; // [rsp+50h] [rbp-18h] BYREF

  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v14);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v13);
  v7 = (__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 4;
  if ( *((int *)this + 14) >= 0 )
  {
    if ( (unsigned __int8)std::operator!=<ID3D11Device>(v6 + 168) )
    {
      SolidPath = SolidPathCluster::CreateSolidPath(this, (__int64)v15, v8, v9, 1, v7);
      std::shared_ptr<_devicemodeW>::operator=(v14, SolidPath);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v15);
      if ( *((int *)this + 14) < 0 )
        goto LABEL_9;
      std::vector<std::shared_ptr<XgcSolidPath>>::push_back((char *)this + 8, v14);
      LODWORD(v7) = v7 + 1;
    }
    if ( *((int *)this + 14) >= 0 )
    {
      if ( (unsigned __int8)std::operator!=<ID3D11Device>(a2 + 184) )
      {
        v11 = SolidPathCluster::CreateSolidPath(this, (__int64)v15, a2, a3, 0, v7);
        std::shared_ptr<_devicemodeW>::operator=(v13, v11);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v15);
        if ( *((int *)this + 14) >= 0 )
          std::vector<std::shared_ptr<XgcSolidPath>>::push_back((char *)this + 8, v13);
      }
    }
  }
LABEL_9:
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v13);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v14);
  return std::_Ptr_base<ID2D1RenderTarget>::_Decref(a3);
}

```

## disassembly

```asm
0x18002a16c  mov     [rsp-30h+arg_10], r8
0x18002a171  push    rbp
0x18002a172  push    rbx
0x18002a173  push    rsi
0x18002a174  push    rdi
0x18002a175  push    r14
0x18002a177  push    r15
0x18002a179  mov     rbp, rsp
0x18002a17c  sub     rsp, 68h
0x18002a180  mov     r15, r8
0x18002a183  mov     r14, rdx
0x18002a186  mov     rdi, rcx
0x18002a189  lea     rcx, [rbp+var_28]
0x18002a18d  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002a192  nop
0x18002a193  lea     rcx, [rbp+var_38]
0x18002a197  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002a19c  nop
0x18002a19d  lea     rsi, [rdi+8]
0x18002a1a1  mov     rbx, [rsi+8]
0x18002a1a5  sub     rbx, [rsi]
0x18002a1a8  sar     rbx, 4
0x18002a1ac  cmp     dword ptr [rdi+38h], 0
0x18002a1b0  jl      loc_18002A263
0x18002a1b6  lea     rcx, [rdx+0A8h]
0x18002a1bd  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18002a1c2  test    al, al
0x18002a1c4  jz      short loc_18002A20A
0x18002a1c6  mov     [rsp+68h+var_40], ebx; int
0x18002a1ca  mov     [rsp+68h+var_48], 1; char
0x18002a1cf  mov     r9, r8
0x18002a1d2  mov     r8, rdx
0x18002a1d5  lea     rdx, [rbp+var_18]
0x18002a1d9  mov     rcx, rdi; this
0x18002a1dc  call    ?CreateSolidPath@SolidPathCluster@@AEAA?AV?$shared_ptr@VXgcSolidPath@@@std@@PEAVCXgcPath@@AEAV?$shared_ptr@UID2D1Geometry@@@3@_NH@Z; SolidPathCluster::CreateSolidPath(CXgcPath *,std::shared_ptr<ID2D1Geometry> &,bool,int)
0x18002a1e1  mov     rdx, rax
0x18002a1e4  lea     rcx, [rbp+var_28]
0x18002a1e8  call    ??4?$shared_ptr@U_devicemodeW@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_devicemodeW>::operator=(std::shared_ptr<_devicemodeW> &&)
0x18002a1ed  lea     rcx, [rbp+var_18]
0x18002a1f1  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002a1f6  cmp     dword ptr [rdi+38h], 0
0x18002a1fa  jl      short loc_18002A263
0x18002a1fc  lea     rdx, [rbp+var_28]
0x18002a200  mov     rcx, rsi
0x18002a203  call    ?push_back@?$vector@V?$shared_ptr@VXgcSolidPath@@@std@@V?$allocator@V?$shared_ptr@VXgcSolidPath@@@std@@@2@@std@@QEAAXAEBV?$shared_ptr@VXgcSolidPath@@@2@@Z; std::vector<std::shared_ptr<XgcSolidPath>>::push_back(std::shared_ptr<XgcSolidPath> const &)
0x18002a208  inc     ebx
0x18002a20a  cmp     dword ptr [rdi+38h], 0
0x18002a20e  jl      short loc_18002A263
0x18002a210  lea     rcx, [r14+0B8h]
0x18002a217  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18002a21c  test    al, al
0x18002a21e  jz      short loc_18002A263
0x18002a220  mov     [rsp+68h+var_40], ebx; int
0x18002a224  mov     [rsp+68h+var_48], 0; char
0x18002a229  mov     r9, r15
0x18002a22c  mov     r8, r14
0x18002a22f  lea     rdx, [rbp+var_18]
0x18002a233  mov     rcx, rdi; this
0x18002a236  call    ?CreateSolidPath@SolidPathCluster@@AEAA?AV?$shared_ptr@VXgcSolidPath@@@std@@PEAVCXgcPath@@AEAV?$shared_ptr@UID2D1Geometry@@@3@_NH@Z; SolidPathCluster::CreateSolidPath(CXgcPath *,std::shared_ptr<ID2D1Geometry> &,bool,int)
0x18002a23b  mov     rdx, rax
0x18002a23e  lea     rcx, [rbp+var_38]
0x18002a242  call    ??4?$shared_ptr@U_devicemodeW@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_devicemodeW>::operator=(std::shared_ptr<_devicemodeW> &&)
0x18002a247  lea     rcx, [rbp+var_18]
0x18002a24b  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002a250  cmp     dword ptr [rdi+38h], 0
0x18002a254  jl      short loc_18002A263
0x18002a256  lea     rdx, [rbp+var_38]
0x18002a25a  mov     rcx, rsi
0x18002a25d  call    ?push_back@?$vector@V?$shared_ptr@VXgcSolidPath@@@std@@V?$allocator@V?$shared_ptr@VXgcSolidPath@@@std@@@2@@std@@QEAAXAEBV?$shared_ptr@VXgcSolidPath@@@2@@Z; std::vector<std::shared_ptr<XgcSolidPath>>::push_back(std::shared_ptr<XgcSolidPath> const &)
0x18002a262  nop
0x18002a263  lea     rcx, [rbp+var_38]
0x18002a267  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002a26c  nop
0x18002a26d  lea     rcx, [rbp+var_28]
0x18002a271  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002a276  nop
0x18002a277  mov     rcx, r15
0x18002a27a  add     rsp, 68h
0x18002a27e  pop     r15
0x18002a280  pop     r14
0x18002a282  pop     rdi
0x18002a283  pop     rsi
0x18002a284  pop     rbx
0x18002a285  pop     rbp
0x18002a286  jmp     ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
```
