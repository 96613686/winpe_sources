# SolidPathCluster::ProcessCluster(xgc::GDIExporter *)

- ea: `0x18002a000`
- end: `0x18002a164`
- name: `?ProcessCluster@SolidPathCluster@@QEAAJPEAVGDIExporter@xgc@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(SolidPathCluster *__hidden this, struct xgc::GDIExporter *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18000eee0`

## callees

- `0x18000da08`
- `0x18000e0d8`
- `0x18000e174`
- `0x180011de8`
- `0x180011f88`
- `0x180011fb8`
- `0x180015aac`
- `0x180028810`
- `0x180028f54`
- `0x18002990c`
- `0x18002a000`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SolidPathCluster::ProcessCluster(SolidPathCluster *this, struct xgc::GDIExporter *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  int v6; // eax
  _QWORD *v7; // rbx
  __int64 v8; // rcx
  _QWORD *v9; // rdi
  __int64 v10; // rcx
  _QWORD *v11; // r14
  __int64 v12; // r8
  _BYTE *v13; // r15
  _QWORD *v14; // rbx
  __int64 v15; // rcx
  _QWORD *v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rbx
  unsigned int v19; // ebx
  _QWORD v21[2]; // [rsp+20h] [rbp-40h] BYREF
  _BYTE v22[24]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v23[24]; // [rsp+48h] [rbp-18h] BYREF
  char v24; // [rsp+A0h] [rbp+40h] BYREF
  char v25; // [rsp+B0h] [rbp+50h] BYREF

  std::vector<CCoordinate>::vector<CCoordinate>(v23, a2);
  std::vector<CCoordinate>::vector<CCoordinate>(v22, v4);
  if ( *((int *)this + 14) >= 0 )
  {
    v6 = SolidPathCluster::CheckConstraints(this) ? *((_DWORD *)this + 14) : -2147467259;
    *((_DWORD *)this + 14) = v6;
    if ( v6 >= 0 )
    {
      v7 = *(_QWORD **)std::vector<tagRGBQUAD>::begin((char *)this + 8, &v24, v5);
      v9 = *(_QWORD **)std::vector<CCoordinate>::end(v8, &v25);
      while ( v7 != v9 )
      {
        std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v21);
        std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v21, v7);
        SolidPathCluster::DrawSolidPath(v10, a2, v21);
        v7 += 2;
      }
      v11 = v22;
      std::vector<std::shared_ptr<CXgcVisual>>::clear(v22);
      SolidPathCluster::NextVectorGroup(this, (__int64)this + 8, (__int64)v22);
      v13 = v23;
      do
      {
        if ( !((__int64)(v11[1] - *v11) >> 4) )
          break;
        v14 = *(_QWORD **)std::vector<tagRGBQUAD>::begin(v11, &v24, v12);
        v16 = *(_QWORD **)std::vector<CCoordinate>::end(v15, &v25);
        while ( v14 != v16 )
        {
          std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v21);
          std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v21, v14);
          SolidPathCluster::DrawSolidPath(v17, a2, v21);
          v14 += 2;
        }
        v18 = (__int64)v13;
        v13 = v11;
        v11 = (_QWORD *)v18;
        std::vector<std::shared_ptr<CXgcVisual>>::clear(v18);
        SolidPathCluster::NextVectorGroup(this, (__int64)v13, v18);
      }
      while ( v18 );
    }
  }
  v19 = *((_DWORD *)this + 14);
  std::vector<std::shared_ptr<IWICFormatConverter>>::_Tidy(v22);
  std::vector<std::shared_ptr<IWICFormatConverter>>::_Tidy(v23);
  return v19;
}

```

## disassembly

```asm
0x18002a000  push    rbp
0x18002a002  push    rbx
0x18002a003  push    rsi
0x18002a004  push    rdi
0x18002a005  push    r12
0x18002a007  push    r14
0x18002a009  push    r15
0x18002a00b  mov     rbp, rsp
0x18002a00e  sub     rsp, 60h
0x18002a012  mov     r12, rdx
0x18002a015  mov     rsi, rcx
0x18002a018  lea     rcx, [rbp+var_18]
0x18002a01c  call    ??0?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA@XZ; std::vector<CCoordinate>::vector<CCoordinate>(void)
0x18002a021  nop
0x18002a022  lea     rcx, [rbp+var_30]
0x18002a026  call    ??0?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA@XZ; std::vector<CCoordinate>::vector<CCoordinate>(void)
0x18002a02b  nop
0x18002a02c  cmp     dword ptr [rsi+38h], 0
0x18002a030  jl      loc_18002A13D
0x18002a036  mov     rcx, rsi; this
0x18002a039  call    ?CheckConstraints@SolidPathCluster@@AEAA_NXZ; SolidPathCluster::CheckConstraints(void)
0x18002a03e  test    al, al
0x18002a040  jz      short loc_18002A047
0x18002a042  mov     eax, [rsi+38h]
0x18002a045  jmp     short loc_18002A04C
0x18002a047  mov     eax, 80004005h
0x18002a04c  mov     [rsi+38h], eax
0x18002a04f  test    eax, eax
0x18002a051  js      loc_18002A13D
0x18002a057  lea     r15, [rsi+8]
0x18002a05b  lea     rdx, [rbp+arg_0]
0x18002a05f  mov     rcx, r15
0x18002a062  call    ?begin@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UtagRGBQUAD@@@std@@@std@@@2@XZ; std::vector<tagRGBQUAD>::begin(void)
0x18002a067  mov     rbx, [rax]
0x18002a06a  lea     rdx, [rbp+arg_10]
0x18002a06e  call    ?end@?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCCoordinate@@@std@@@std@@@2@XZ; std::vector<CCoordinate>::end(void)
0x18002a073  mov     rdi, [rax]
0x18002a076  cmp     rbx, rdi
0x18002a079  jz      short loc_18002A0A2
0x18002a07b  lea     rcx, [rbp+var_40]
0x18002a07f  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18002a084  mov     rdx, rbx
0x18002a087  lea     rcx, [rbp+var_40]
0x18002a08b  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x18002a090  lea     r8, [rbp+var_40]
0x18002a094  mov     rdx, r12
0x18002a097  call    ?DrawSolidPath@SolidPathCluster@@QEAAXPEAVGDIExporter@xgc@@V?$shared_ptr@VXgcSolidPath@@@std@@@Z; SolidPathCluster::DrawSolidPath(xgc::GDIExporter *,std::shared_ptr<XgcSolidPath>)
0x18002a09c  add     rbx, 10h
0x18002a0a0  jmp     short loc_18002A076
0x18002a0a2  lea     r14, [rbp+var_30]
0x18002a0a6  lea     rcx, [rbp+var_30]
0x18002a0aa  call    ?clear@?$vector@V?$shared_ptr@VCXgcVisual@@@std@@V?$allocator@V?$shared_ptr@VCXgcVisual@@@std@@@2@@std@@QEAAXXZ; std::vector<std::shared_ptr<CXgcVisual>>::clear(void)
0x18002a0af  lea     r8, [rbp+var_30]
0x18002a0b3  mov     rdx, r15
0x18002a0b6  mov     rcx, rsi; this
0x18002a0b9  call    ?NextVectorGroup@SolidPathCluster@@AEAAXPEAV?$vector@V?$shared_ptr@VXgcSolidPath@@@std@@V?$allocator@V?$shared_ptr@VXgcSolidPath@@@std@@@2@@std@@0@Z; SolidPathCluster::NextVectorGroup(std::vector<std::shared_ptr<XgcSolidPath>> *,std::vector<std::shared_ptr<XgcSolidPath>> *)
0x18002a0be  lea     r15, [rbp+var_18]
0x18002a0c2  mov     rax, [r14+8]
0x18002a0c6  sub     rax, [r14]
0x18002a0c9  sar     rax, 4
0x18002a0cd  test    rax, rax
0x18002a0d0  jz      short loc_18002A13D
0x18002a0d2  lea     rdx, [rbp+arg_0]
0x18002a0d6  mov     rcx, r14
0x18002a0d9  call    ?begin@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UtagRGBQUAD@@@std@@@std@@@2@XZ; std::vector<tagRGBQUAD>::begin(void)
0x18002a0de  mov     rbx, [rax]
0x18002a0e1  lea     rdx, [rbp+arg_10]
0x18002a0e5  call    ?end@?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCCoordinate@@@std@@@std@@@2@XZ; std::vector<CCoordinate>::end(void)
0x18002a0ea  mov     rdi, [rax]
0x18002a0ed  cmp     rbx, rdi
0x18002a0f0  jz      short loc_18002A119
0x18002a0f2  lea     rcx, [rbp+var_40]
0x18002a0f6  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18002a0fb  mov     rdx, rbx
0x18002a0fe  lea     rcx, [rbp+var_40]
0x18002a102  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x18002a107  lea     r8, [rbp+var_40]
0x18002a10b  mov     rdx, r12
0x18002a10e  call    ?DrawSolidPath@SolidPathCluster@@QEAAXPEAVGDIExporter@xgc@@V?$shared_ptr@VXgcSolidPath@@@std@@@Z; SolidPathCluster::DrawSolidPath(xgc::GDIExporter *,std::shared_ptr<XgcSolidPath>)
0x18002a113  add     rbx, 10h
0x18002a117  jmp     short loc_18002A0ED
0x18002a119  mov     rbx, r15
0x18002a11c  mov     r15, r14
0x18002a11f  mov     r14, rbx
0x18002a122  mov     rcx, rbx
0x18002a125  call    ?clear@?$vector@V?$shared_ptr@VCXgcVisual@@@std@@V?$allocator@V?$shared_ptr@VCXgcVisual@@@std@@@2@@std@@QEAAXXZ; std::vector<std::shared_ptr<CXgcVisual>>::clear(void)
0x18002a12a  mov     r8, rbx
0x18002a12d  mov     rdx, r15
0x18002a130  mov     rcx, rsi; this
0x18002a133  call    ?NextVectorGroup@SolidPathCluster@@AEAAXPEAV?$vector@V?$shared_ptr@VXgcSolidPath@@@std@@V?$allocator@V?$shared_ptr@VXgcSolidPath@@@std@@@2@@std@@0@Z; SolidPathCluster::NextVectorGroup(std::vector<std::shared_ptr<XgcSolidPath>> *,std::vector<std::shared_ptr<XgcSolidPath>> *)
0x18002a138  test    rbx, rbx
0x18002a13b  jnz     short loc_18002A0C2
0x18002a13d  mov     ebx, [rsi+38h]
0x18002a140  lea     rcx, [rbp+var_30]
0x18002a144  call    ?_Tidy@?$vector@V?$shared_ptr@UIWICFormatConverter@@@std@@V?$allocator@V?$shared_ptr@UIWICFormatConverter@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<IWICFormatConverter>>::_Tidy(void)
0x18002a149  nop
0x18002a14a  lea     rcx, [rbp+var_18]
0x18002a14e  call    ?_Tidy@?$vector@V?$shared_ptr@UIWICFormatConverter@@@std@@V?$allocator@V?$shared_ptr@UIWICFormatConverter@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<IWICFormatConverter>>::_Tidy(void)
0x18002a153  mov     eax, ebx
0x18002a155  add     rsp, 60h
0x18002a159  pop     r15
0x18002a15b  pop     r14
0x18002a15d  pop     r12
0x18002a15f  pop     rdi
0x18002a160  pop     rsi
0x18002a161  pop     rbx
0x18002a162  pop     rbp
0x18002a163  retn
```
