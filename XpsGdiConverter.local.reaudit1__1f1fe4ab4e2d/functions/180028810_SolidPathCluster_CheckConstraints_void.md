# SolidPathCluster::CheckConstraints(void)

- ea: `0x180028810`
- end: `0x180028a5a`
- name: `?CheckConstraints@SolidPathCluster@@AEAA_NXZ`
- size: `586`
- prototype: `bool __fastcall(SolidPathCluster *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002a000`

## callees

- `0x18000da08`
- `0x18000e0d8`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x180028810`
- `0x18002919c`
- `0x180029334`
- `0x18002944c`
- `0x18002a4e8`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_BOOL8 __fastcall SolidPathCluster::CheckConstraints(SolidPathCluster *this)
{
  int v2; // esi
  char *v3; // r15
  __int64 v4; // rax
  bool v5; // bl
  int i; // edi
  _QWORD *v7; // rdx
  __int64 *v8; // r12
  __int64 v9; // rcx
  int v10; // r14d
  _QWORD *v11; // rdx
  __int64 v12; // rcx
  _BOOL8 result; // rax
  _QWORD v14[2]; // [rsp+30h] [rbp-89h] BYREF
  _QWORD v15[2]; // [rsp+40h] [rbp-79h] BYREF
  _QWORD v16[2]; // [rsp+50h] [rbp-69h] BYREF
  _QWORD v17[2]; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v18[2]; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v19[2]; // [rsp+80h] [rbp-39h] BYREF
  _QWORD v20[2]; // [rsp+90h] [rbp-29h] BYREF
  _QWORD v21[2]; // [rsp+A0h] [rbp-19h] BYREF
  _QWORD v22[12]; // [rsp+B0h] [rbp-9h] BYREF
  int v23; // [rsp+128h] [rbp+6Fh] BYREF
  _QWORD *v24; // [rsp+130h] [rbp+77h]

  v2 = 0;
  v3 = (char *)this + 8;
  v4 = (__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 4;
  v5 = (int)v4 < 9;
  i = v4 - 1;
  while ( i > 0 && v5 && v2 >= 0 )
  {
    std::vector<std::shared_ptr<XgcSolidPath>>::at(v3, (unsigned int)i);
    std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v21);
    std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v21, v7);
    if ( *(_BYTE *)(v21[0] + 48LL)
      || *(_BYTE *)(v21[0] + 49LL)
      || (v8 = (__int64 *)(v21[0] + 16LL),
          std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v14),
          std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v14, v8),
          (unsigned __int8)SolidPathCluster::IsRectangle(v9, v14)) )
    {
      --i;
    }
    else
    {
      v10 = i - 1;
      for ( i = v10; v10 >= 0; --v10 )
      {
        if ( !v5 || v2 < 0 )
          break;
        std::vector<std::shared_ptr<XgcSolidPath>>::at(v3, (unsigned int)v10);
        std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v20);
        std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v20, v11);
        v12 = *v8;
        v24 = (_QWORD *)(v20[0] + 16LL);
        v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v12 + 64LL))(
               v12,
               *(_QWORD *)(v20[0] + 16LL),
               0);
        if ( v2 >= 0 )
        {
          v5 = 0;
          v23 = 0;
          std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v19);
          v22[0] = 0;
          v22[1] = &v23;
          v22[2] = v19;
          std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v15);
          std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v15, v24);
          std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v16);
          std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v16, v8);
          v2 = SolidPathCluster::Intersection(this, v16, v15, v22);
          detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v22);
          if ( v2 >= 0 && v23 >= 0 )
          {
            std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v17);
            std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v17, v8);
            std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v18);
            std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v18, v19);
            v5 = (unsigned __int8)SolidPathCluster::IsIntersectBoundContained(this, v18, v17) != 0;
          }
          std::_Ptr_base<ID2D1RenderTarget>::_Decref(v19);
        }
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v20);
      }
    }
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v21);
  }
  result = 0;
  if ( v2 >= 0 )
    return v5;
  return result;
}

```

## disassembly

```asm
0x180028810  push    rbp
0x180028812  push    rbx
0x180028813  push    rsi
0x180028814  push    rdi
0x180028815  push    r12
0x180028817  push    r13
0x180028819  push    r14
0x18002881b  push    r15
0x18002881d  lea     rbp, [rsp-1Fh]
0x180028822  sub     rsp, 0D8h
0x180028829  mov     r13, rcx
0x18002882c  xor     esi, esi
0x18002882e  lea     r15, [rcx+8]
0x180028832  mov     rax, [r15+8]
0x180028836  sub     rax, [r15]
0x180028839  sar     rax, 4
0x18002883d  cmp     eax, 9
0x180028840  setl    bl
0x180028843  lea     edi, [rax-1]
0x180028846  jmp     loc_180028A34
0x18002884b  test    bl, bl
0x18002884d  jz      loc_180028A3C
0x180028853  test    esi, esi
0x180028855  js      loc_180028A3C
0x18002885b  mov     edx, edi
0x18002885d  mov     rcx, r15
0x180028860  call    ?at@?$vector@V?$shared_ptr@VXgcSolidPath@@@std@@V?$allocator@V?$shared_ptr@VXgcSolidPath@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VXgcSolidPath@@@2@_K@Z; std::vector<std::shared_ptr<XgcSolidPath>>::at(unsigned __int64)
0x180028865  mov     rdx, rax
0x180028868  lea     rcx, [rbp+57h+var_70]
0x18002886c  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180028871  lea     rcx, [rbp+57h+var_70]
0x180028875  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x18002887a  nop
0x18002887b  mov     rax, [rbp+57h+var_70]
0x18002887f  cmp     byte ptr [rax+30h], 0
0x180028883  jnz     loc_180028A29
0x180028889  cmp     byte ptr [rax+31h], 0
0x18002888d  jnz     loc_180028A29
0x180028893  lea     r12, [rax+10h]
0x180028897  lea     rcx, [rsp+110h+var_E0]
0x18002889c  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x1800288a1  mov     rdx, r12
0x1800288a4  lea     rcx, [rsp+110h+var_E0]
0x1800288a9  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x1800288ae  lea     rdx, [rsp+110h+var_E0]
0x1800288b3  call    ?IsRectangle@SolidPathCluster@@AEAA_NV?$shared_ptr@UID2D1Geometry@@@std@@@Z; SolidPathCluster::IsRectangle(std::shared_ptr<ID2D1Geometry>)
0x1800288b8  test    al, al
0x1800288ba  jnz     loc_180028A29
0x1800288c0  lea     r14d, [rdi-1]
0x1800288c4  mov     edi, r14d
0x1800288c7  test    r14d, r14d
0x1800288ca  js      loc_180028A27
0x1800288d0  test    bl, bl
0x1800288d2  jz      loc_180028A27
0x1800288d8  test    esi, esi
0x1800288da  js      loc_180028A27
0x1800288e0  mov     edx, r14d
0x1800288e3  mov     rcx, r15
0x1800288e6  call    ?at@?$vector@V?$shared_ptr@VXgcSolidPath@@@std@@V?$allocator@V?$shared_ptr@VXgcSolidPath@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VXgcSolidPath@@@2@_K@Z; std::vector<std::shared_ptr<XgcSolidPath>>::at(unsigned __int64)
0x1800288eb  mov     rdx, rax
0x1800288ee  lea     rcx, [rbp+57h+var_80]
0x1800288f2  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x1800288f7  lea     rcx, [rbp+57h+var_80]
0x1800288fb  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180028900  nop
0x180028901  mov     [rbp+57h+arg_0], 0
0x180028908  mov     rcx, [r12]
0x18002890c  mov     rdx, [rbp+57h+var_80]
0x180028910  add     rdx, 10h
0x180028914  mov     [rbp+57h+arg_10], rdx
0x180028918  mov     rax, [rcx]
0x18002891b  lea     r8, [rbp+57h+arg_0]
0x18002891f  mov     [rsp+110h+var_F0], r8
0x180028924  movss   xmm3, cs:__real@3d4ccccd
0x18002892c  xor     r8d, r8d
0x18002892f  mov     rdx, [rdx]
0x180028932  mov     rax, [rax+40h]
0x180028936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002893b  mov     esi, eax
0x18002893d  mov     ecx, [rbp+57h+arg_0]
0x180028940  dec     ecx
0x180028942  cmp     ecx, 2
0x180028945  jbe     loc_180028A14
0x18002894b  test    eax, eax
0x18002894d  js      loc_180028A14
0x180028953  xor     ebx, ebx
0x180028955  mov     [rbp+57h+arg_8], ebx
0x180028958  lea     rcx, [rbp+57h+var_90]
0x18002895c  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180028961  nop
0x180028962  mov     [rbp+57h+var_60], rbx
0x180028966  lea     rax, [rbp+57h+arg_8]
0x18002896a  mov     [rbp+57h+var_58], rax
0x18002896e  lea     rax, [rbp+57h+var_90]
0x180028972  mov     [rbp+57h+var_50], rax
0x180028976  lea     rcx, [rbp+57h+var_D0]
0x18002897a  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18002897f  mov     rdx, [rbp+57h+arg_10]
0x180028983  lea     rcx, [rbp+57h+var_D0]
0x180028987  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x18002898c  lea     rcx, [rbp+57h+var_C0]
0x180028990  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180028995  mov     rdx, r12
0x180028998  lea     rcx, [rbp+57h+var_C0]
0x18002899c  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x1800289a1  lea     r9, [rbp+57h+var_60]
0x1800289a5  lea     r8, [rbp+57h+var_D0]
0x1800289a9  lea     rdx, [rbp+57h+var_C0]
0x1800289ad  mov     rcx, r13
0x1800289b0  call    ?Intersection@SolidPathCluster@@AEAAJV?$shared_ptr@UID2D1Geometry@@@std@@0PEAPEAUID2D1Geometry@@@Z; SolidPathCluster::Intersection(std::shared_ptr<ID2D1Geometry>,std::shared_ptr<ID2D1Geometry>,ID2D1Geometry * *)
0x1800289b5  mov     esi, eax
0x1800289b7  lea     rcx, [rbp+57h+var_60]
0x1800289bb  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800289c0  test    esi, esi
0x1800289c2  js      short loc_180028A0A
0x1800289c4  cmp     [rbp+57h+arg_8], ebx
0x1800289c7  jl      short loc_180028A0A
0x1800289c9  lea     rcx, [rbp+57h+var_B0]
0x1800289cd  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x1800289d2  mov     rdx, r12
0x1800289d5  lea     rcx, [rbp+57h+var_B0]
0x1800289d9  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x1800289de  lea     rcx, [rbp+57h+var_A0]
0x1800289e2  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x1800289e7  lea     rdx, [rbp+57h+var_90]
0x1800289eb  lea     rcx, [rbp+57h+var_A0]
0x1800289ef  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x1800289f4  lea     r8, [rbp+57h+var_B0]
0x1800289f8  lea     rdx, [rbp+57h+var_A0]
0x1800289fc  mov     rcx, r13
0x1800289ff  call    ?IsIntersectBoundContained@SolidPathCluster@@AEAA_NV?$shared_ptr@UID2D1Geometry@@@std@@0@Z; SolidPathCluster::IsIntersectBoundContained(std::shared_ptr<ID2D1Geometry>,std::shared_ptr<ID2D1Geometry>)
0x180028a04  test    al, al
0x180028a06  jz      short loc_180028A0A
0x180028a08  mov     bl, 1
0x180028a0a  lea     rcx, [rbp+57h+var_90]
0x180028a0e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180028a13  nop
0x180028a14  lea     rcx, [rbp+57h+var_80]
0x180028a18  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180028a1d  sub     r14d, 1
0x180028a21  jns     loc_1800288D0
0x180028a27  jmp     short loc_180028A2B
0x180028a29  dec     edi
0x180028a2b  lea     rcx, [rbp+57h+var_70]
0x180028a2f  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180028a34  test    edi, edi
0x180028a36  jg      loc_18002884B
0x180028a3c  xor     eax, eax
0x180028a3e  movzx   ecx, bl
0x180028a41  test    esi, esi
0x180028a43  cmovns  eax, ecx
0x180028a46  add     rsp, 0D8h
0x180028a4d  pop     r15
0x180028a4f  pop     r14
0x180028a51  pop     r13
0x180028a53  pop     r12
0x180028a55  pop     rdi
0x180028a56  pop     rsi
0x180028a57  pop     rbx
0x180028a58  pop     rbp
0x180028a59  retn
```
