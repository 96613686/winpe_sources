# CoEffectGraph::RenderToPixelStream(tagPOINT,tagSIZE,ChannelFormat,IPixelStream * *)

- ea: `0x18055b070`
- end: `0x18055bbb9`
- name: `?RenderToPixelStream@CoEffectGraph@@UEAAJUtagPOINT@@UtagSIZE@@W4ChannelFormat@@PEAPEAUIPixelStream@@@Z`
- size: `2889`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001397c`
- `0x18001db0c`
- `0x1801a31b8`
- `0x1801a9660`
- `0x1801cecd0`
- `0x1804c6944`
- `0x18055626c`
- `0x1805564d8`
- `0x18055b070`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x18055b8e5`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18055b8e5`
- `KERNEL32!GetLastError` at `0x18055bb51`
- `KERNEL32!GetLastError` at `0x18055bb51`
- `OLEAUT32!__imp_VariantClear` at `0x18055b85c`
- `OLEAUT32!__imp_VariantClear` at `0x18055b85c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18055b87f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18055b87f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18055b870`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18055b870`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18055b88f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18055b88f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18055b84d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18055b84d`
- `GDI32!CombineRgn` at `0x18055b40e`
- `GDI32!CombineRgn` at `0x18055b40e`
- `GDI32!GetRgnBox` at `0x18055b6c5`
- `GDI32!GetRgnBox` at `0x18055b6c5`
- `GDI32!DeleteObject` at `0x18055b41c`
- `GDI32!DeleteObject` at `0x18055ba2d`
- `GDI32!DeleteObject` at `0x18055b41c`
- `GDI32!DeleteObject` at `0x18055ba2d`
- `GDI32!CreateRectRgnIndirect` at `0x18055b17c`
- `GDI32!CreateRectRgnIndirect` at `0x18055b3f6`
- `GDI32!CreateRectRgnIndirect` at `0x18055b17c`
- `GDI32!CreateRectRgnIndirect` at `0x18055b3f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CoEffectGraph::RenderToPixelStream(
        __int64 a1,
        unsigned __int64 a2,
        SAFEARRAY *a3,
        unsigned int a4,
        char **a5)
{
  int v8; // r14d
  int v9; // eax
  unsigned int v10; // r13d
  HRGN v11; // rdi
  int v12; // eax
  int v13; // eax
  unsigned int i; // r15d
  int v15; // eax
  int v16; // eax
  int v17; // eax
  HRGN v18; // r14
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // r14
  unsigned __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  int v25; // eax
  unsigned __int64 v26; // rax
  int v27; // r15d
  int *v28; // rdx
  __int64 (__fastcall *v29)(unsigned __int64, _QWORD, unsigned __int64, RECT *); // r10
  __int64 v30; // r9
  __int64 v31; // r8
  int v32; // eax
  char *v33; // rax
  char *v34; // r14
  _QWORD *v35; // r15
  bool v36; // r13
  unsigned __int64 v37; // r15
  __int64 v38; // rcx
  int v39; // eax
  signed int LastError; // eax
  unsigned int v42; // ecx
  int v44; // [rsp+44h] [rbp-1B4h] BYREF
  unsigned __int64 v45; // [rsp+48h] [rbp-1B0h]
  SAFEARRAY *psa; // [rsp+50h] [rbp-1A8h] BYREF
  unsigned __int64 v47; // [rsp+58h] [rbp-1A0h] BYREF
  int v48; // [rsp+60h] [rbp-198h] BYREF
  char *v49; // [rsp+68h] [rbp-190h] BYREF
  __int64 v50; // [rsp+70h] [rbp-188h]
  char **v51; // [rsp+80h] [rbp-178h]
  VARIANTARG rc; // [rsp+98h] [rbp-160h] BYREF
  _DWORD v53[8]; // [rsp+B0h] [rbp-148h] BYREF
  void *Block; // [rsp+D0h] [rbp-128h] BYREF
  _BYTE v55[12]; // [rsp+D8h] [rbp-120h]
  int v56; // [rsp+E4h] [rbp-114h]
  int v57; // [rsp+E8h] [rbp-110h]
  RECT v58; // [rsp+F0h] [rbp-108h] BYREF
  IRecordInfo *pRecInfo; // [rsp+100h] [rbp-F8h]
  RECT rect; // [rsp+110h] [rbp-E8h] BYREF
  int v61; // [rsp+120h] [rbp-D8h] BYREF
  wchar_t v62[70]; // [rsp+124h] [rbp-D4h] BYREF

  v51 = a5;
  v45 = a2;
  psa = a3;
  v8 = 0;
  if ( (int)a3 <= 0 || SHIDWORD(a3) <= 0 )
    ATL::BaseAtlThrow(-2147024809);
  if ( a4 > 8 || (v9 = 278, !_bittest(&v9, a4)) )
    ATL::BaseAtlThrow(-2147024809);
  if ( !a5 )
    ATL::BaseAtlThrow(-2147467261);
  if ( !*(_QWORD *)(a1 + 136) )
    ATL::BaseAtlThrow(-2045378043);
  sub_1805564D8(*(struct IEffectHost **)(a1 + 128));
  v47 = 0;
  rect.left = a2;
  v10 = HIDWORD(v45);
  rect.top = HIDWORD(v45);
  if ( (unsigned __int64)((int)a3 + (__int64)(int)a2 + 0x80000000LL) > 0xFFFFFFFF
    || (rect.right = (_DWORD)a3 + a2,
        (unsigned __int64)(SHIDWORD(v45) + (__int64)SHIDWORD(psa) + 0x80000000LL) > 0xFFFFFFFF) )
  {
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  rect.bottom = HIDWORD(v45) + HIDWORD(psa);
  v11 = CreateRectRgnIndirect(&rect);
  *(_QWORD *)&rect.left = v11;
  v50 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, SAFEARRAY *))(*(_QWORD *)a1 + 224LL))(a1, a2, a3);
  if ( v12 == -2147024882 || v12 == -2045378032 || v12 == -2045312765 || v12 == -2045247216 )
    ATL::BaseAtlThrow(v12);
  if ( v12 < 0 )
    ATL::BaseAtlThrow(v12);
  v48 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v50 + 56LL))(v50, &v48);
  if ( v13 == -2147024882 || v13 == -2045378032 || v13 == -2045312765 || v13 == -2045247216 )
    ATL::BaseAtlThrow(v13);
  if ( v13 < 0 )
    ATL::BaseAtlThrow(v13);
  v44 = 1;
  for ( i = 0; (int)i < v48; ++i )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *, char **))(*(_QWORD *)v50 + 64LL))(v50, i, &rc, &v49);
    if ( v15 == -2147024882 || v15 == -2045378032 || v15 == -2045312765 || v15 == -2045247216 )
      ATL::BaseAtlThrow(v15);
    if ( v15 < 0 )
      ATL::BaseAtlThrow(v15);
    v45 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)a1 + 232LL))(a1, *(_QWORD *)&rc.vt, v49);
    if ( v16 == -2147024882 || v16 == -2045378032 || v16 == -2045312765 || v16 == -2045247216 )
      ATL::BaseAtlThrow(v16);
    if ( v16 < 0 )
      ATL::BaseAtlThrow(v16);
    memset(v53, 0, 28);
    v17 = (*(__int64 (__fastcall **)(unsigned __int64, _DWORD *))(*(_QWORD *)v45 + 56LL))(v45, v53);
    if ( v17 == -2147024882 || v17 == -2045378032 || v17 == -2045312765 || v17 == -2045247216 )
      ATL::BaseAtlThrow(v17);
    if ( v17 < 0 )
      ATL::BaseAtlThrow(v17);
    v58.left = v53[3];
    v58.top = v53[4];
    if ( (unsigned __int64)(v53[3] + (__int64)v53[5] + 0x80000000LL) > 0xFFFFFFFF
      || (v58.right = v53[3] + v53[5], (unsigned __int64)(v53[4] + (__int64)v53[6] + 0x80000000LL) > 0xFFFFFFFF) )
    {
      safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
    }
    v58.bottom = v53[4] + v53[6];
    v18 = CreateRectRgnIndirect(&v58);
    CombineRgn(v11, v11, v18, 4);
    if ( v18 )
      DeleteObject(v18);
    if ( v48 != 1
      || *(_OWORD *)&v53[3] != __PAIR128__(__PAIR64__(HIDWORD(psa), (unsigned int)a3), __PAIR64__(v10, a2))
      || v53[0] != a4 )
    {
      v22 = v47;
      v8 = 0;
      if ( !v47 )
      {
        Block = (void *)a4;
        *(_DWORD *)v55 = 4;
        *(_QWORD *)&v55[4] = a2;
        v56 = (int)a3;
        v57 = HIDWORD(psa);
        v61 = -1;
        StringCchCopyW(v62, 0x40u, L"RenderToPixelStream");
        if ( (*(int (__fastcall **)(_QWORD, void **, int *, __int64, unsigned __int64 *))(**(_QWORD **)(a1 + 136) + 64LL))(
               *(_QWORD *)(a1 + 136),
               &Block,
               &v61,
               1,
               &v47) < 0 )
        {
          HIDWORD(Block) = 1;
          v23 = (*(__int64 (__fastcall **)(_QWORD, void **, int *, __int64, unsigned __int64 *))(**(_QWORD **)(a1 + 136)
                                                                                               + 64LL))(
                  *(_QWORD *)(a1 + 136),
                  &Block,
                  &v61,
                  1,
                  &v47);
          if ( v23 == -2147024882 || v23 == -2045378032 || v23 == -2045312765 || v23 == -2045247216 )
            ATL::BaseAtlThrow(v23);
          if ( v23 < 0 )
            ATL::BaseAtlThrow(v23);
        }
        v22 = v47;
      }
      v24 = (*(__int64 (__fastcall **)(unsigned __int64, unsigned __int64, _QWORD, _QWORD))(*(_QWORD *)v22 + 112LL))(
              v22,
              v45,
              *(_QWORD *)&v53[3],
              *(_QWORD *)&v53[5]);
      if ( v24 == -2147024882 || v24 == -2045378032 || v24 == -2045312765 || v24 == -2045247216 )
        ATL::BaseAtlThrow(v24);
      if ( v24 < 0 )
        ATL::BaseAtlThrow(v24);
      goto LABEL_48;
    }
    v19 = v47;
    v20 = v45;
    if ( v47 == v45 )
    {
      v8 = 0;
    }
    else
    {
      v21 = v45;
      if ( v45 )
      {
        (*(void (**)(void))(*(_QWORD *)v45 + 8LL))();
        v19 = v47;
        v20 = v45;
      }
      v47 = v21;
      v8 = 0;
      if ( v19 )
      {
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_48:
        v20 = v45;
      }
    }
    if ( v44 )
    {
      v25 = (*(__int64 (__fastcall **)(unsigned __int64, int *))(*(_QWORD *)v20 + 72LL))(v20, &v44);
      if ( v25 == -2147024882 || v25 == -2045378032 || v25 == -2045312765 || v25 == -2045247216 )
        ATL::BaseAtlThrow(v25);
      if ( v25 < 0 )
        ATL::BaseAtlThrow(v25);
      v20 = v45;
    }
    if ( v20 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  *(_OWORD *)&rc.vt = 0u;
  GetRgnBox(v11, (LPRECT)&rc);
  if ( *(int *)&rc.vt < rc.lVal && (int)rc.decVal.Hi32 < rc.cyVal.Hi )
  {
    v58 = 0;
    SafeArrayFromArray<float>::SafeArrayFromArray<float>(&psa, &v58, 4);
    ATL::CComVariant::CComVariant(&rc.vt, psa);
    RegionRects::RegionRects(&Block, v11);
    v26 = *(_QWORD *)v55;
    v27 = *(_DWORD *)v55;
    while ( v8 < v27 )
    {
      if ( v8 < 0 )
        ATL::BaseAtlThrow(-2147024809);
      if ( v8 >= v26 )
        ATL::BaseAtlThrow(-2147024809);
      v28 = (int *)((char *)Block + 16 * v8);
      v29 = *(__int64 (__fastcall **)(unsigned __int64, _QWORD, unsigned __int64, RECT *))(*(_QWORD *)v47 + 96LL);
      v30 = v28[3] - (__int64)v28[1];
      if ( (unsigned __int64)(v30 + 0x80000000LL) > 0xFFFFFFFF
        || (v31 = v28[2] - (__int64)*v28, (unsigned __int64)(v31 + 0x80000000LL) > 0xFFFFFFFF) )
      {
        safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
      }
      v45 = __PAIR64__(v30, v31);
      v58 = *(RECT *)&rc.vt;
      pRecInfo = rc.pRecInfo;
      v32 = v29(v47, *(_QWORD *)v28, __PAIR64__(v30, v31), &v58);
      if ( v32 == -2147024882 || v32 == -2045378032 || v32 == -2045312765 || v32 == -2045247216 )
        ATL::BaseAtlThrow(v32);
      if ( v32 < 0 )
        ATL::BaseAtlThrow(v32);
      ++v8;
      v26 = *(_QWORD *)v55;
    }
    if ( Block )
      free(Block);
    VariantClear(&rc);
    if ( psa && SafeArrayUnlock(psa) >= 0 )
      SafeArrayDestroy(psa);
  }
  v33 = (char *)malloc(0x88u);
  v34 = v33;
  if ( !v33 )
    ThrowOOM();
  *(_QWORD *)&rc.vt = v33;
  *((_DWORD *)v33 + 14) = 0;
  *((_OWORD *)v33 + 4) = 0;
  *((_OWORD *)v33 + 5) = 0;
  *((_QWORD *)v33 + 12) = 0;
  v33[104] = 0;
  v35 = v33 + 8;
  *((_QWORD *)v33 + 1) = &SingleThreadingModel::`vftable';
  v49 = v33 + 16;
  if ( !InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v33 + 16), 0, 0) )
  {
    LastError = GetLastError();
    v42 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v42 = LastError;
    ATL::BaseAtlThrow(v42);
  }
  *((_QWORD *)v34 + 14) = 0;
  *((_QWORD *)v34 + 16) = 0;
  *(_QWORD *)v34 = &ATL::CComObject<PixelStream>::`vftable'{for `ATL::IDispatchImpl<IPixelStream,&__s_GUID const _GUID_2a2ce472_d718_47a0_a5ac_60b65fafda0d,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'};
  *v35 = &ATL::CComObject<PixelStream>::`vftable'{for `SingleThreadingModel'};
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  psa = (SAFEARRAY *)v34;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v34 + 8LL))(v34);
  v36 = v44 != 0;
  v37 = v47;
  *(_QWORD *)&rc.vt = a3;
  v49 = (char *)a2;
  if ( *((_QWORD *)v34 + 14) != v47 )
  {
    if ( v47 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v47 + 8LL))(v47);
    v38 = *((_QWORD *)v34 + 14);
    *((_QWORD *)v34 + 14) = v37;
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  v34[120] = v36;
  v39 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, char **, VARIANTARG *, char *))(**((_QWORD **)v34 + 14)
                                                                                                  + 88LL))(
          *((_QWORD *)v34 + 14),
          0,
          a4,
          1,
          &v49,
          &rc,
          v34 + 128);
  if ( v39 == -2147024882 || v39 == -2045378032 || v39 == -2045312765 || v39 == -2045247216 )
    ATL::BaseAtlThrow(v39);
  if ( v39 < 0 )
    ATL::BaseAtlThrow(v39);
  *v51 = v34;
  if ( v50 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  if ( v11 )
    DeleteObject(v11);
  if ( v47 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v47 + 16LL))(v47);
  return 0;
}

```

## disassembly

```asm
0x18055b070  push    rbx
0x18055b072  push    rsi
0x18055b073  push    rdi
0x18055b074  push    r12
0x18055b076  push    r13
0x18055b078  push    r14
0x18055b07a  push    r15
0x18055b07c  sub     rsp, 1C0h
0x18055b083  mov     rax, cs:__security_cookie
0x18055b08a  xor     rax, rsp
0x18055b08d  mov     [rsp+1F8h+var_48], rax
0x18055b095  mov     [rsp+1F8h+var_1B8], r9d
0x18055b09a  mov     rbx, r8
0x18055b09d  mov     rsi, rdx
0x18055b0a0  mov     r12, rcx
0x18055b0a3  mov     rcx, [rsp+1F8h+arg_20]
0x18055b0ab  mov     [rsp+1F8h+var_178], rcx
0x18055b0b3  mov     [rsp+1F8h+var_1B0], rdx
0x18055b0b8  mov     [rsp+1F8h+psa], rbx
0x18055b0bd  xor     r14d, r14d
0x18055b0c0  test    ebx, ebx
0x18055b0c2  jle     loc_18055BBAD
0x18055b0c8  mov     rax, rbx
0x18055b0cb  shr     rax, 20h
0x18055b0cf  test    eax, eax
0x18055b0d1  jle     loc_18055BBAD
0x18055b0d7  cmp     r9d, 8
0x18055b0db  ja      loc_18055BBA3
0x18055b0e1  mov     eax, 116h
0x18055b0e6  bt      eax, r9d
0x18055b0ea  jnb     loc_18055BBA3
0x18055b0f0  test    rcx, rcx
0x18055b0f3  jz      loc_18055BA82
0x18055b0f9  mov     rdx, [r12+88h]
0x18055b101  test    rdx, rdx
0x18055b104  jz      loc_18055BA8C
0x18055b10a  mov     rcx, [r12+80h]
0x18055b112  call    sub_1805564D8
0x18055b117  mov     [rsp+1F8h+var_1A0], r14
0x18055b11c  mov     [rsp+1F8h+rect.left], esi
0x18055b123  movsxd  r13, dword ptr [rsp+1F8h+var_1B0+4]
0x18055b128  mov     [rsp+1F8h+rect.top], r13d
0x18055b130  movsxd  rcx, esi
0x18055b133  movsxd  rax, ebx
0x18055b136  add     rcx, rax
0x18055b139  mov     edx, 80000000h
0x18055b13e  lea     rax, [rcx+rdx]
0x18055b142  mov     r8d, 0FFFFFFFFh
0x18055b148  cmp     rax, r8
0x18055b14b  ja      loc_18055BB99
0x18055b151  mov     [rsp+1F8h+rect.right], ecx
0x18055b158  movsxd  rcx, dword ptr [rsp+1F8h+psa+4]
0x18055b15d  add     rcx, r13
0x18055b160  lea     rax, [rcx+rdx]
0x18055b164  cmp     rax, r8
0x18055b167  ja      loc_18055BB99
0x18055b16d  mov     [rsp+1F8h+rect.bottom], ecx
0x18055b174  lea     rcx, [rsp+1F8h+rect]; lprect
0x18055b17c  call    cs:__imp_CreateRectRgnIndirect
0x18055b182  mov     rdi, rax
0x18055b185  mov     qword ptr [rsp+1F8h+rect.left], rax
0x18055b18d  mov     [rsp+1F8h+var_188], r14
0x18055b192  mov     rax, [r12]
0x18055b196  lea     rcx, [rsp+1F8h+var_188]
0x18055b19b  mov     [rsp+1F8h+var_1D8], rcx
0x18055b1a0  movsd   xmm3, cs:__real@3ff0000000000000
0x18055b1a8  mov     r8, rbx
0x18055b1ab  mov     rdx, rsi
0x18055b1ae  mov     rcx, r12
0x18055b1b1  mov     rax, [rax+0E0h]
0x18055b1b8  call    cs:__guard_dispatch_icall_fptr
0x18055b1be  cmp     eax, 8007000Eh
0x18055b1c3  jz      loc_18055BB88
0x18055b1c9  cmp     eax, 86160210h
0x18055b1ce  jz      loc_18055BB88
0x18055b1d4  cmp     eax, 86170103h
0x18055b1d9  jz      loc_18055BB88
0x18055b1df  mov     r15d, 86180110h
0x18055b1e5  cmp     eax, r15d
0x18055b1e8  jz      loc_18055BB88
0x18055b1ee  test    eax, eax
0x18055b1f0  js      loc_18055BA9A
0x18055b1f6  mov     [rsp+1F8h+var_198], r14d
0x18055b1fb  mov     rcx, [rsp+1F8h+var_188]
0x18055b200  mov     rax, [rcx]
0x18055b203  lea     rdx, [rsp+1F8h+var_198]
0x18055b208  mov     rax, [rax+38h]
0x18055b20c  call    cs:__guard_dispatch_icall_fptr
0x18055b212  cmp     eax, 8007000Eh
0x18055b217  jz      loc_18055BB81
0x18055b21d  cmp     eax, 86160210h
0x18055b222  jz      loc_18055BB81
0x18055b228  cmp     eax, 86170103h
0x18055b22d  jz      loc_18055BB81
0x18055b233  cmp     eax, r15d
0x18055b236  jz      loc_18055BB81
0x18055b23c  test    eax, eax
0x18055b23e  js      loc_18055BAA1
0x18055b244  mov     [rsp+1F8h+var_1B4], 1
0x18055b24c  mov     r15d, r14d
0x18055b24f  cmp     r15d, [rsp+1F8h+var_198]
0x18055b254  jge     loc_18055B6A2
0x18055b25a  mov     rcx, [rsp+1F8h+var_188]
0x18055b25f  mov     rax, [rcx]
0x18055b262  lea     r9, [rsp+1F8h+var_190]
0x18055b267  lea     r8, [rsp+1F8h+rc]
0x18055b26f  mov     edx, r15d
0x18055b272  mov     rax, [rax+40h]
0x18055b276  call    cs:__guard_dispatch_icall_fptr
0x18055b27c  cmp     eax, 8007000Eh
0x18055b281  jz      loc_18055BB03
0x18055b287  cmp     eax, 86160210h
0x18055b28c  jz      loc_18055BB03
0x18055b292  cmp     eax, 86170103h
0x18055b297  jz      loc_18055BB03
0x18055b29d  cmp     eax, 86180110h
0x18055b2a2  jz      loc_18055BB03
0x18055b2a8  test    eax, eax
0x18055b2aa  js      loc_18055BAA8
0x18055b2b0  mov     [rsp+1F8h+var_1B0], r14
0x18055b2b5  mov     rax, [r12]
0x18055b2b9  lea     rcx, [rsp+1F8h+var_1B0]
0x18055b2be  mov     [rsp+1F8h+var_1D8], rcx
0x18055b2c3  movsd   xmm3, cs:__real@3ff0000000000000
0x18055b2cb  mov     r8, [rsp+1F8h+var_190]
0x18055b2d0  mov     rdx, qword ptr [rsp+1F8h+rc.left]
0x18055b2d8  mov     rcx, r12
0x18055b2db  mov     rax, [rax+0E8h]
0x18055b2e2  call    cs:__guard_dispatch_icall_fptr
0x18055b2e8  cmp     eax, 8007000Eh
0x18055b2ed  jz      loc_18055BAF8
0x18055b2f3  cmp     eax, 86160210h
0x18055b2f8  jz      loc_18055BAF8
0x18055b2fe  cmp     eax, 86170103h
0x18055b303  jz      loc_18055BAF8
0x18055b309  cmp     eax, 86180110h
0x18055b30e  jz      loc_18055BAF8
0x18055b314  test    eax, eax
0x18055b316  js      loc_18055BAB3
0x18055b31c  xorps   xmm0, xmm0
0x18055b31f  xor     eax, eax
0x18055b321  movups  xmmword ptr [rsp+1F8h+var_148], xmm0
0x18055b329  mov     qword ptr [rsp+1F8h+var_148+10h], rax
0x18055b331  mov     [rsp+1F8h+var_148+18h], eax
0x18055b338  mov     rcx, [rsp+1F8h+var_1B0]
0x18055b33d  mov     rax, [rcx]
0x18055b340  lea     rdx, [rsp+1F8h+var_148]
0x18055b348  mov     rax, [rax+38h]
0x18055b34c  call    cs:__guard_dispatch_icall_fptr
0x18055b352  cmp     eax, 8007000Eh
0x18055b357  jz      loc_18055BAF1
0x18055b35d  cmp     eax, 86160210h
0x18055b362  jz      loc_18055BAF1
0x18055b368  cmp     eax, 86170103h
0x18055b36d  jz      loc_18055BAF1
0x18055b373  cmp     eax, 86180110h
0x18055b378  jz      loc_18055BAF1
0x18055b37e  test    eax, eax
0x18055b380  js      loc_18055BABA
0x18055b386  movsxd  rax, [rsp+1F8h+var_148+0Ch]
0x18055b38e  mov     [rsp+1F8h+var_108.left], eax
0x18055b395  movsxd  rdx, [rsp+1F8h+var_148+10h]
0x18055b39d  mov     [rsp+1F8h+var_108.top], edx
0x18055b3a4  movsxd  rcx, [rsp+1F8h+var_148+14h]
0x18055b3ac  add     rcx, rax
0x18055b3af  mov     r8d, 80000000h
0x18055b3b5  lea     rax, [r8+rcx]
0x18055b3b9  mov     r9d, 0FFFFFFFFh
0x18055b3bf  cmp     rax, r9
0x18055b3c2  ja      loc_18055BAEB
0x18055b3c8  mov     [rsp+1F8h+var_108.right], ecx
0x18055b3cf  movsxd  rcx, [rsp+1F8h+var_148+18h]
0x18055b3d7  add     rcx, rdx
0x18055b3da  lea     rax, [r8+rcx]
0x18055b3de  cmp     rax, r9
0x18055b3e1  ja      loc_18055BAEB
0x18055b3e7  mov     [rsp+1F8h+var_108.bottom], ecx
0x18055b3ee  lea     rcx, [rsp+1F8h+var_108]; lprect
0x18055b3f6  call    cs:__imp_CreateRectRgnIndirect
0x18055b3fc  mov     r14, rax
0x18055b3ff  mov     r9d, 4; iMode
0x18055b405  mov     r8, rax; hrgnSrc2
0x18055b408  mov     rdx, rdi; hrgnSrc1
0x18055b40b  mov     rcx, rdi; hrgnDst
0x18055b40e  call    cs:__imp_CombineRgn
0x18055b414  test    r14, r14
0x18055b417  jz      short loc_18055B422
0x18055b419  mov     rcx, r14; ho
0x18055b41c  call    cs:__imp_DeleteObject
0x18055b422  mov     eax, dword ptr [rsp+1F8h+psa+4]
0x18055b426  mov     edx, [rsp+1F8h+var_1B8]
0x18055b42a  cmp     [rsp+1F8h+var_198], 1
0x18055b42f  jnz     loc_18055B4C7
0x18055b435  cmp     [rsp+1F8h+var_148+0Ch], esi
0x18055b43c  jnz     loc_18055B4C7
0x18055b442  cmp     [rsp+1F8h+var_148+10h], r13d
0x18055b44a  jnz     short loc_18055B4C7
0x18055b44c  cmp     [rsp+1F8h+var_148+14h], ebx
0x18055b453  jnz     short loc_18055B4C7
0x18055b455  cmp     [rsp+1F8h+var_148+18h], eax
0x18055b45c  jnz     short loc_18055B4C7
0x18055b45e  cmp     [rsp+1F8h+var_148], edx
0x18055b465  jnz     short loc_18055B4C7
0x18055b467  mov     rax, [rsp+1F8h+var_1A0]
0x18055b46c  mov     rcx, [rsp+1F8h+var_1B0]
0x18055b471  cmp     rax, rcx
0x18055b474  jz      loc_18055B633
0x18055b47a  mov     r14, rcx
0x18055b47d  test    rcx, rcx
0x18055b480  jz      short loc_18055B499
0x18055b482  mov     rax, [rcx]
0x18055b485  mov     rax, [rax+8]
0x18055b489  call    cs:__guard_dispatch_icall_fptr
0x18055b48f  mov     rax, [rsp+1F8h+var_1A0]
0x18055b494  mov     rcx, [rsp+1F8h+var_1B0]
0x18055b499  mov     [rsp+1F8h+var_1A0], r14
0x18055b49e  xor     r14d, r14d
0x18055b4a1  test    rax, rax
0x18055b4a4  jz      loc_18055B636
0x18055b4aa  mov     rcx, [rax]
0x18055b4ad  mov     rdx, [rcx+10h]
0x18055b4b1  mov     rcx, rax
0x18055b4b4  mov     rax, rdx
0x18055b4b7  call    cs:__guard_dispatch_icall_fptr
0x18055b4bd  mov     rcx, [rsp+1F8h+var_1B0]
0x18055b4c2  jmp     loc_18055B636
0x18055b4c7  mov     rcx, [rsp+1F8h+var_1A0]
0x18055b4cc  xor     r14d, r14d
0x18055b4cf  test    rcx, rcx
0x18055b4d2  jnz     loc_18055B5D8
0x18055b4d8  mov     dword ptr [rsp+1F8h+Block], edx
0x18055b4df  mov     dword ptr [rsp+1F8h+Block+4], r14d
0x18055b4e7  mov     dword ptr [rsp+1F8h+var_120], 4
0x18055b4f2  mov     qword ptr [rsp+1F8h+var_120+4], rsi
0x18055b4fa  mov     [rsp+1F8h+var_114], ebx
0x18055b501  mov     [rsp+1F8h+var_110], eax
0x18055b508  mov     [rsp+1F8h+var_D8], 0FFFFFFFFh
0x18055b513  lea     r8, aRendertopixels; "RenderToPixelStream"
0x18055b51a  lea     edx, [rcx+40h]; unsigned __int64
0x18055b51d  lea     rcx, [rsp+1F8h+var_D4]; wchar_t *
0x18055b525  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18055b52a  mov     rcx, [r12+88h]
0x18055b532  mov     rax, [rcx]
0x18055b535  lea     rdx, [rsp+1F8h+var_1A0]
0x18055b53a  mov     [rsp+1F8h+var_1D8], rdx
0x18055b53f  lea     r9d, [r14+1]
0x18055b543  lea     r8, [rsp+1F8h+var_D8]
0x18055b54b  lea     rdx, [rsp+1F8h+Block]
0x18055b553  mov     rax, [rax+40h]
0x18055b557  call    cs:__guard_dispatch_icall_fptr
0x18055b55d  test    eax, eax
0x18055b55f  jns     short loc_18055B5D3
0x18055b561  lea     r8d, [r14+1]
0x18055b565  mov     dword ptr [rsp+1F8h+Block+4], r8d
0x18055b56d  mov     rcx, [r12+88h]
0x18055b575  mov     rax, [rcx]
0x18055b578  lea     rdx, [rsp+1F8h+var_1A0]
0x18055b57d  mov     [rsp+1F8h+var_1D8], rdx
0x18055b582  mov     r9d, r8d
0x18055b585  lea     r8, [rsp+1F8h+var_D8]
0x18055b58d  lea     rdx, [rsp+1F8h+Block]
0x18055b595  mov     rax, [rax+40h]
0x18055b599  call    cs:__guard_dispatch_icall_fptr
0x18055b59f  cmp     eax, 8007000Eh
0x18055b5a4  jz      loc_18055BAC8
0x18055b5aa  cmp     eax, 86160210h
0x18055b5af  jz      loc_18055BAC8
0x18055b5b5  cmp     eax, 86170103h
0x18055b5ba  jz      loc_18055BAC8
0x18055b5c0  cmp     eax, 86180110h
0x18055b5c5  jz      loc_18055BAC8
0x18055b5cb  test    eax, eax
0x18055b5cd  js      loc_18055BAC1
0x18055b5d3  mov     rcx, [rsp+1F8h+var_1A0]
0x18055b5d8  mov     rax, [rcx]
0x18055b5db  mov     r9, qword ptr [rsp+1F8h+var_148+14h]
0x18055b5e3  mov     r8, qword ptr [rsp+1F8h+var_148+0Ch]
0x18055b5eb  mov     rdx, [rsp+1F8h+var_1B0]
0x18055b5f0  mov     rax, [rax+70h]
0x18055b5f4  call    cs:__guard_dispatch_icall_fptr
0x18055b5fa  cmp     eax, 8007000Eh
0x18055b5ff  jz      loc_18055BAE4
0x18055b605  cmp     eax, 86160210h
0x18055b60a  jz      loc_18055BAE4
0x18055b610  cmp     eax, 86170103h
0x18055b615  jz      loc_18055BAE4
0x18055b61b  cmp     eax, 86180110h
0x18055b620  jz      loc_18055BAE4
0x18055b626  test    eax, eax
0x18055b628  js      loc_18055BACF
0x18055b62e  jmp     loc_18055B4BD
0x18055b633  xor     r14d, r14d
0x18055b636  cmp     [rsp+1F8h+var_1B4], r14d
0x18055b63b  jz      short loc_18055B688
0x18055b63d  mov     rax, [rcx]
0x18055b640  lea     rdx, [rsp+1F8h+var_1B4]
0x18055b645  mov     rax, [rax+48h]
0x18055b649  call    cs:__guard_dispatch_icall_fptr
0x18055b64f  cmp     eax, 8007000Eh
0x18055b654  jz      loc_18055BADD
  ... truncated ...
```
