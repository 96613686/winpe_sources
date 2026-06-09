# WinRegion::GetInverseRects(xvector<XRECT_WH> *,XRECT_RB const *)

- ea: `0x1804c2790`
- end: `0x1804c2975`
- name: `?GetInverseRects@WinRegion@@UEAAJPEAV?$xvector@UXRECT_WH@@@@PEBUXRECT_RB@@@Z`
- size: `485`
- prototype: `HRESULT __fastcall(WinRegion *this, xvector<XRECT_WH> *pArray, const XRECT_RB *pBounds)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004bc0`
- `0x18001c368`
- `0x180131190`
- `0x180146914`
- `0x1803ce230`
- `0x1804c2790`
- `0x1806877a8`
- `0x180687890`
- `0x18069f6ac`
- `0x1806c4ccc`

## import_xrefs

- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1804c2893`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1804c28cd`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1804c2893`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1804c28cd`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1804c2854`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1804c285f`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1804c2854`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1804c285f`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgn` at `0x1804c27c7`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgn` at `0x1804c27ec`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgn` at `0x1804c27c7`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgn` at `0x1804c27ec`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CombineRgn` at `0x1804c280e`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CombineRgn` at `0x1804c280e`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!GetRegionData` at `0x1804c28e2`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!GetRegionData` at `0x1804c2904`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!GetRegionData` at `0x1804c28e2`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!GetRegionData` at `0x1804c2904`

## pseudocode

```c
__int64 __fastcall WinRegion::GetInverseRects(
        WinRegion *this,
        _xvector_base<SnapPointData> *pArray,
        const XRECT_RB *pBounds)
{
  _RGNDATA *FailFast; // r14
  HRESULT v7; // ecx
  HRGN RectRgn; // rdi
  HRESULT v9; // ecx
  HRGN v10; // r15
  HRESULT v11; // ecx
  unsigned int v12; // ebx
  DWORD RegionData; // eax
  DWORD v15; // esi
  unsigned int i; // esi
  int v17; // edx
  int v18; // eax
  int v19; // eax
  HRESULT v20; // eax
  XRECT_WH rect; // [rsp+20h] [rbp-10h] BYREF
  unsigned int cStowedExceptions; // [rsp+60h] [rbp+30h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+70h] [rbp+40h] BYREF

  FailFast = 0;
  _xvector_base<HWCompNode *>::clear(pArray);
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  if ( !RectRgn )
  {
    OnFailure_2976_(v7);
    ppStowedExceptions = 0;
    cStowedExceptions = 0;
    TraceForFailFast(-2147024882);
    GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
    RoFailFastWithErrorContextInternal2(-2147024882, cStowedExceptions, ppStowedExceptions);
  }
  v10 = CreateRectRgn(pBounds->left, pBounds->top, pBounds->right, pBounds->bottom);
  if ( !v10 )
  {
    OnFailure_2976_(v9);
    ppStowedExceptions = 0;
    cStowedExceptions = 0;
    TraceForFailFast(-2147024882);
    GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
    RoFailFastWithErrorContextInternal2(-2147024882, cStowedExceptions, ppStowedExceptions);
  }
  if ( !CombineRgn(RectRgn, v10, this->m_rgn, 4) )
    goto LABEL_6;
  v12 = 0;
  RegionData = GetRegionData(RectRgn, 0, 0);
  v15 = RegionData;
  if ( RegionData )
  {
    FailFast = (_RGNDATA *)XcpAllocation::OSMemoryAllocateFailFast(RegionData);
    if ( GetRegionData(RectRgn, v15, FailFast) != v15 )
    {
LABEL_6:
      v12 = -2147418113;
      OnNewFailure_2955_(v11);
      goto $Cleanup_3515;
    }
    for ( i = 0; i < FailFast->rdh.nCount; ++i )
    {
      v17 = *(&FailFast[1].rdh.dwSize + 4 * i);
      v18 = *(&FailFast[1].rdh.iType + 4 * i) - *(_DWORD *)&FailFast->Buffer[16 * i];
      rect.X = *(_DWORD *)&FailFast->Buffer[16 * i];
      rect.Width = v18;
      v19 = *(&FailFast[1].rdh.nCount + 4 * i) - v17;
      rect.Y = v17;
      rect.Height = v19;
      v20 = _xvector_base<XRECT_WH>::push_back((_xvector_base<XRECT_WH> *)pArray, &rect);
      v12 = v20;
      if ( v20 < 0 )
      {
        OnFailure_2990_(v20);
        break;
      }
    }
  }
$Cleanup_3515:
  operator delete(FailFast);
  if ( v10 )
    DeleteObject(v10);
  if ( RectRgn )
    DeleteObject(RectRgn);
  return v12;
}

```

## disassembly

```asm
0x1804c2790  mov     [rsp-28h+arg_8], rbx
0x1804c2795  mov     [rsp-28h+arg_18], rsi
0x1804c279a  push    rbp
0x1804c279b  push    rdi
0x1804c279c  push    r12
0x1804c279e  push    r14
0x1804c27a0  push    r15
0x1804c27a2  mov     rbp, rsp
0x1804c27a5  sub     rsp, 30h
0x1804c27a9  mov     rsi, this
0x1804c27ac  mov     rbx, pBounds
0x1804c27af  mov     this, pArray; this
0x1804c27b2  mov     r12, pArray
0x1804c27b5  xor     r14d, r14d
0x1804c27b8  call    ?clear@?$_xvector_base@PEAVHWCompNode@@@@QEAAXXZ; _xvector_base<HWCompNode *>::clear(void)
0x1804c27bd  xor     r9d, r9d; y2
0x1804c27c0  xor     r8d, r8d; x2
0x1804c27c3  xor     edx, edx; y1
0x1804c27c5  xor     ecx, ecx; x1
0x1804c27c7  call    cs:__imp_CreateRectRgn
0x1804c27cd  mov     rdi, rax
0x1804c27d0  mov     r15d, 8007000Eh
0x1804c27d6  test    rax, rax
0x1804c27d9  jz      loc_1804C2867
0x1804c27df  mov     r9d, [rbx+0Ch]; y2
0x1804c27e3  mov     r8d, [rbx+8]; x2
0x1804c27e7  mov     edx, [rbx+4]; y1
0x1804c27ea  mov     ecx, [rbx]; x1
0x1804c27ec  call    cs:__imp_CreateRectRgn
0x1804c27f2  mov     r15, rax
0x1804c27f5  test    rax, rax
0x1804c27f8  jz      loc_1804C289E
0x1804c27fe  mov     pBounds, [rsi+10h]; hrgnSrc2
0x1804c2802  mov     r9d, 4; iMode
0x1804c2808  mov     pArray, r15; hrgnSrc1
0x1804c280b  mov     this, rdi; hrgnDst
0x1804c280e  call    cs:__imp_CombineRgn
0x1804c2814  test    eax, eax
0x1804c2816  jnz     loc_1804C28D8
0x1804c281c  mov     ebx, 8000FFFFh
0x1804c2821  call    OnNewFailure_2955_
0x1804c2826  mov     this, r14; pAddress
0x1804c2829  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1804c282e  test    r15, r15
0x1804c2831  jnz     short loc_1804C2851
0x1804c2833  test    rdi, rdi
0x1804c2836  jnz     short loc_1804C285C
0x1804c2838  mov     rsi, [rsp+30h+arg_18]
0x1804c283d  mov     eax, ebx
0x1804c283f  mov     rbx, [rsp+30h+arg_8]
0x1804c2844  add     rsp, 30h
0x1804c2848  pop     r15
0x1804c284a  pop     r14
0x1804c284c  pop     r12
0x1804c284e  pop     rdi
0x1804c284f  pop     rbp
0x1804c2850  retn
0x1804c2851  mov     this, r15; ho
0x1804c2854  call    cs:__imp_DeleteObject
0x1804c285a  jmp     short loc_1804C2833
0x1804c285c  mov     this, rdi; ho
0x1804c285f  call    cs:__imp_DeleteObject
0x1804c2865  jmp     short loc_1804C2838
0x1804c2867  call    OnFailure_2976_
0x1804c286c  mov     ecx, r15d; errorCode
0x1804c286f  mov     [rbp+ppStowedExceptions], r14
0x1804c2873  mov     [rbp+cStowedExceptions], r14d
0x1804c2877  call    TraceForFailFast
0x1804c287c  lea     pArray, [rbp+cStowedExceptions]; pcStowedExceptions
0x1804c2880  lea     this, [rbp+ppStowedExceptions]; pppStowedExceptions
0x1804c2884  call    GetStowedExceptionsForFailFast
0x1804c2889  mov     pBounds, [rbp+ppStowedExceptions]
0x1804c288d  mov     ecx, r15d
0x1804c2890  mov     edx, [rbp+cStowedExceptions]
0x1804c2893  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1804c2899  jmp     loc_1804C27DF
0x1804c289e  call    OnFailure_2976_
0x1804c28a3  mov     ebx, 8007000Eh
0x1804c28a8  mov     [rbp+ppStowedExceptions], r14
0x1804c28ac  mov     ecx, ebx; errorCode
0x1804c28ae  mov     [rbp+cStowedExceptions], r14d
0x1804c28b2  call    TraceForFailFast
0x1804c28b7  lea     pArray, [rbp+cStowedExceptions]; pcStowedExceptions
0x1804c28bb  lea     this, [rbp+ppStowedExceptions]; pppStowedExceptions
0x1804c28bf  call    GetStowedExceptionsForFailFast
0x1804c28c4  mov     pBounds, [rbp+ppStowedExceptions]
0x1804c28c8  mov     ecx, ebx
0x1804c28ca  mov     edx, [rbp+cStowedExceptions]
0x1804c28cd  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1804c28d3  jmp     loc_1804C27FE
0x1804c28d8  xor     r8d, r8d; lpRgnData
0x1804c28db  xor     edx, edx; nCount
0x1804c28dd  mov     this, rdi; hrgn
0x1804c28e0  xor     ebx, ebx
0x1804c28e2  call    cs:__imp_GetRegionData
0x1804c28e8  mov     esi, eax
0x1804c28ea  test    eax, eax
0x1804c28ec  jz      $Cleanup_3515
0x1804c28f2  mov     ecx, esi; cSize
0x1804c28f4  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x1804c28f9  mov     pBounds, rax; lpRgnData
0x1804c28fc  mov     edx, esi; nCount
0x1804c28fe  mov     this, rdi; hrgn
0x1804c2901  mov     r14, rax
0x1804c2904  call    cs:__imp_GetRegionData
0x1804c290a  cmp     eax, esi
0x1804c290c  jnz     short loc_1804C2966
0x1804c290e  xor     esi, esi
0x1804c2910  cmp     esi, [r14+8]
0x1804c2914  jnb     $Cleanup_3515
0x1804c291a  mov     r8d, esi
0x1804c291d  add     pBounds, pBounds
0x1804c2920  mov     ecx, [r14+pBounds*8+20h]
0x1804c2925  mov     edx, [r14+pBounds*8+24h]
0x1804c292a  mov     eax, [r14+pBounds*8+28h]
0x1804c292f  sub     eax, ecx
0x1804c2931  mov     [rbp+rect.X], ecx
0x1804c2934  mov     [rbp+rect.Width], eax
0x1804c2937  mov     this, r12; this
0x1804c293a  mov     eax, [r14+pBounds*8+2Ch]
0x1804c293f  sub     eax, edx
0x1804c2941  mov     [rbp+rect.Y], edx
0x1804c2944  lea     pArray, [rbp+rect]; val
0x1804c2948  mov     [rbp+rect.Height], eax
0x1804c294b  call    ?push_back@?$_xvector_base@UXRECT_WH@@@@QEAAJAEBUXRECT_WH@@@Z; _xvector_base<XRECT_WH>::push_back(XRECT_WH const &)
0x1804c2950  mov     ebx, eax
0x1804c2952  test    eax, eax
0x1804c2954  js      short loc_1804C295A
0x1804c2956  inc     esi
0x1804c2958  jmp     short loc_1804C2910
0x1804c295a  mov     ecx, eax; failedFrameHR
0x1804c295c  call    OnFailure_2990_
0x1804c2961  jmp     $Cleanup_3515
0x1804c2966  mov     ebx, 8000FFFFh
0x1804c296b  call    OnNewFailure_2955_
0x1804c2970  jmp     $Cleanup_3515
```
