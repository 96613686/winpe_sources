# CWICBitmapToneMapper::EnsureD2DInitialized(ID3D11Device *)

- ea: `0x1800bfc7c`
- end: `0x1800bfea0`
- name: `?EnsureD2DInitialized@CWICBitmapToneMapper@@AEAAJPEAUID3D11Device@@@Z`
- size: `548`
- prototype: `__int64 __fastcall(CWICBitmapToneMapper *__hidden this, struct ID3D11Device *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bfad0`
- `0x1800bfec8`

## callees

- `0x180098f08`
- `0x1800bb784`
- `0x1800bfc7c`
- `0x1800e2f90`
- `0x1801ca010`

## import_xrefs

- `d2d1!__imp_D2D1CreateFactory` at `0x1800bfcd4`
- `d2d1!__imp_D2D1CreateFactory` at `0x1800bfcd4`
- `d3d11!D3D11CreateDevice` at `0x1800bfd90`
- `d3d11!D3D11CreateDevice` at `0x1800bfd90`

## pseudocode

```c
__int64 __fastcall CWICBitmapToneMapper::EnsureD2DInitialized(CWICBitmapToneMapper *this, struct ID3D11Device *a2)
{
  __int64 **v2; // r14
  unsigned int v5; // ebx
  HRESULT v6; // eax
  __int64 *v7; // rsi
  __m128i si128; // xmm0
  struct ID3D11Device **v9; // r15
  __int64 v10; // rcx
  HRESULT Device; // eax
  __int64 v12; // rcx
  struct ID3D11Device *v13; // rcx
  struct ID3D11DeviceVtbl *lpVtbl; // rax
  __int64 *v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 (__fastcall *v18)(__int64 *, __int64, char *); // r14
  __int64 *v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 (__fastcall *v22)(__int64 *, _QWORD, __int64 *); // rdi
  __int64 v24; // [rsp+50h] [rbp-9h] BYREF
  D2D1_FACTORY_OPTIONS pFactoryOptions; // [rsp+58h] [rbp-1h] BYREF
  D3D_FEATURE_LEVEL pFeatureLevels[4]; // [rsp+60h] [rbp+7h] BYREF
  int v27; // [rsp+70h] [rbp+17h]
  int v28; // [rsp+74h] [rbp+1Bh]
  int v29; // [rsp+78h] [rbp+1Fh]

  v2 = (__int64 **)((char *)this + 96);
  v5 = 0;
  if ( *((_QWORD *)this + 12)
    || (pFactoryOptions.debugLevel = D2D1_DEBUG_LEVEL_NONE,
        *v2 = 0,
        v6 = D2D1CreateFactory(
               D2D1_FACTORY_TYPE_SINGLE_THREADED,
               &GUID_f9976f46_f642_44c1_97ca_da32ea2a2635,
               &pFactoryOptions,
               (void **)this + 12),
        v5 = v6,
        v6 >= 0) )
  {
    v7 = (__int64 *)((char *)this + 120);
    if ( *((_QWORD *)this + 15) )
      return v5;
    v24 = 0;
    if ( a2 )
    {
      lpVtbl = a2->lpVtbl;
      v13 = a2;
    }
    else
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v9 = (struct ID3D11Device **)((char *)this + 112);
      v10 = *((_QWORD *)this + 14);
      v27 = 37632;
      v28 = 37376;
      v29 = 37120;
      pFactoryOptions.debugLevel = D2D1_DEBUG_LEVEL_NONE;
      *((_QWORD *)this + 14) = 0;
      *(__m128i *)pFeatureLevels = si128;
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      Device = D3D11CreateDevice(
                 0,
                 D3D_DRIVER_TYPE_WARP,
                 0,
                 0x20u,
                 pFeatureLevels,
                 7u,
                 7u,
                 (ID3D11Device **)this + 14,
                 (D3D_FEATURE_LEVEL *)&pFactoryOptions,
                 0);
      v5 = Device;
      if ( Device < 0 )
      {
LABEL_21:
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(Device);
LABEL_23:
        wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(&v24);
        return v5;
      }
      v12 = v24;
      v24 = 0;
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      v13 = *v9;
      lpVtbl = (*v9)->lpVtbl;
    }
    Device = ((__int64 (__fastcall *)(struct ID3D11Device *, GUID *, __int64 *))lpVtbl->QueryInterface)(
               v13,
               &GUID_6007896c_3244_4afd_bf18_a6d3beda5023,
               &v24);
    v5 = Device;
    if ( Device >= 0 )
    {
      v15 = *v2;
      v16 = *((_QWORD *)this + 13);
      v17 = **v2;
      *((_QWORD *)this + 13) = 0;
      v18 = *(__int64 (__fastcall **)(__int64 *, __int64, char *))(v17 + 248);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      Device = v18(v15, v24, (char *)this + 104);
      v5 = Device;
      if ( Device >= 0 )
      {
        v19 = (__int64 *)*((_QWORD *)this + 13);
        v20 = *v7;
        v21 = *v19;
        *v7 = 0;
        v22 = *(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v21 + 152);
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        Device = v22(v19, 0, v7);
        v5 = Device;
        if ( Device >= 0 )
          goto LABEL_23;
      }
    }
    goto LABEL_21;
  }
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(v6);
  return v5;
}

```

## disassembly

```asm
0x1800bfc7c  mov     [rsp-8+arg_10], rbx
0x1800bfc81  mov     [rsp-8+arg_18], rsi
0x1800bfc86  push    rbp
0x1800bfc87  push    rdi
0x1800bfc88  push    r12
0x1800bfc8a  push    r14
0x1800bfc8c  push    r15
0x1800bfc8e  lea     rbp, [rsp-37h]
0x1800bfc93  sub     rsp, 90h
0x1800bfc9a  mov     rax, cs:__security_cookie
0x1800bfca1  xor     rax, rsp
0x1800bfca4  mov     [rbp+57h+var_30], rax
0x1800bfca8  xor     r12d, r12d
0x1800bfcab  lea     r14, [rcx+60h]
0x1800bfcaf  mov     r15, rdx
0x1800bfcb2  mov     rdi, rcx
0x1800bfcb5  mov     ebx, r12d
0x1800bfcb8  cmp     [r14], r12
0x1800bfcbb  jnz     short loc_1800BFCFD
0x1800bfcbd  mov     r9, r14; ppIFactory
0x1800bfcc0  mov     [rbp+57h+pFactoryOptions.debugLevel], r12d
0x1800bfcc4  lea     r8, [rbp+57h+pFactoryOptions]; pFactoryOptions
0x1800bfcc8  mov     [r14], r12
0x1800bfccb  lea     rdx, _GUID_f9976f46_f642_44c1_97ca_da32ea2a2635; riid
0x1800bfcd2  xor     ecx, ecx; factoryType
0x1800bfcd4  call    cs:__imp_D2D1CreateFactory
0x1800bfcda  mov     ebx, eax
0x1800bfcdc  test    eax, eax
0x1800bfcde  jns     short loc_1800BFCFD
0x1800bfce0  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bfce7  jz      short loc_1800BFCF5
0x1800bfce9  mov     ecx, eax; int
0x1800bfceb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800bfcf0  jmp     loc_1800BFE6B
0x1800bfcf5  test    eax, eax
0x1800bfcf7  js      loc_1800BFE6B
0x1800bfcfd  lea     rsi, [rdi+78h]
0x1800bfd01  cmp     [rsi], r12
0x1800bfd04  jnz     loc_1800BFE6B
0x1800bfd0a  mov     [rbp+57h+var_60], r12
0x1800bfd0e  test    r15, r15
0x1800bfd11  jnz     loc_1800BFE95
0x1800bfd17  movdqa  xmm0, cs:__xmm@0000a0000000a1000000b0000000b100
0x1800bfd1f  lea     r15, [rdi+70h]
0x1800bfd23  mov     rcx, [r15]
0x1800bfd26  mov     [rbp+57h+var_40], 9300h
0x1800bfd2d  mov     [rbp+57h+var_3C], 9200h
0x1800bfd34  mov     [rbp+57h+var_38], 9100h
0x1800bfd3b  mov     [rbp+57h+pFactoryOptions.debugLevel], r12d
0x1800bfd3f  mov     [r15], r12
0x1800bfd42  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x1800bfd47  test    rcx, rcx
0x1800bfd4a  jz      short loc_1800BFD58
0x1800bfd4c  mov     rax, [rcx]
0x1800bfd4f  mov     rax, [rax+10h]
0x1800bfd53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfd58  mov     [rsp+0B0h+ppImmediateContext], r12; ppImmediateContext
0x1800bfd5d  lea     rax, [rbp+57h+pFactoryOptions]
0x1800bfd61  mov     [rsp+0B0h+pFeatureLevel], rax; pFeatureLevel
0x1800bfd66  mov     r9d, 20h ; ' '; Flags
0x1800bfd6c  mov     eax, 7
0x1800bfd71  mov     [rsp+0B0h+ppDevice], r15; ppDevice
0x1800bfd76  mov     [rsp+0B0h+SDKVersion], eax; SDKVersion
0x1800bfd7a  xor     r8d, r8d; Software
0x1800bfd7d  mov     [rsp+0B0h+FeatureLevels], eax; FeatureLevels
0x1800bfd81  xor     ecx, ecx; pAdapter
0x1800bfd83  lea     rax, [rbp+57h+var_50]
0x1800bfd87  lea     edx, [r9-1Bh]; DriverType
0x1800bfd8b  mov     [rsp+0B0h+pFeatureLevels], rax; pFeatureLevels
0x1800bfd90  call    cs:__imp_D3D11CreateDevice
0x1800bfd96  mov     ebx, eax
0x1800bfd98  test    eax, eax
0x1800bfd9a  js      loc_1800BFE52
0x1800bfda0  mov     rcx, [rbp+57h+var_60]
0x1800bfda4  mov     [rbp+57h+var_60], r12
0x1800bfda8  test    rcx, rcx
0x1800bfdab  jz      short loc_1800BFDB9
0x1800bfdad  mov     rax, [rcx]
0x1800bfdb0  mov     rax, [rax+10h]
0x1800bfdb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfdb9  mov     rcx, [r15]
0x1800bfdbc  mov     rax, [rcx]
0x1800bfdbf  mov     rax, [rax]
0x1800bfdc2  lea     rdx, _GUID_6007896c_3244_4afd_bf18_a6d3beda5023
0x1800bfdc9  lea     r8, [rbp+57h+var_60]
0x1800bfdcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfdd2  mov     ebx, eax
0x1800bfdd4  test    eax, eax
0x1800bfdd6  js      short loc_1800BFE52
0x1800bfdd8  mov     rbx, [r14]
0x1800bfddb  mov     rcx, [rdi+68h]
0x1800bfddf  mov     rax, [rbx]
0x1800bfde2  mov     [rdi+68h], r12
0x1800bfde6  mov     r14, [rax+0F8h]
0x1800bfded  test    rcx, rcx
0x1800bfdf0  jz      short loc_1800BFDFE
0x1800bfdf2  mov     rax, [rcx]
0x1800bfdf5  mov     rax, [rax+10h]
0x1800bfdf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfdfe  mov     rdx, [rbp+57h+var_60]
0x1800bfe02  lea     r8, [rdi+68h]
0x1800bfe06  mov     rcx, rbx
0x1800bfe09  mov     rax, r14
0x1800bfe0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfe11  mov     ebx, eax
0x1800bfe13  test    eax, eax
0x1800bfe15  js      short loc_1800BFE52
0x1800bfe17  mov     rbx, [rdi+68h]
0x1800bfe1b  mov     rcx, [rsi]
0x1800bfe1e  mov     rax, [rbx]
0x1800bfe21  mov     [rsi], r12
0x1800bfe24  mov     rdi, [rax+98h]
0x1800bfe2b  test    rcx, rcx
0x1800bfe2e  jz      short loc_1800BFE3C
0x1800bfe30  mov     rax, [rcx]
0x1800bfe33  mov     rax, [rax+10h]
0x1800bfe37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfe3c  mov     r8, rsi
0x1800bfe3f  xor     edx, edx
0x1800bfe41  mov     rcx, rbx
0x1800bfe44  mov     rax, rdi
0x1800bfe47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfe4c  mov     ebx, eax
0x1800bfe4e  test    eax, eax
0x1800bfe50  jns     short loc_1800BFE62
0x1800bfe52  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bfe59  jz      short loc_1800BFE62
0x1800bfe5b  mov     ecx, eax; int
0x1800bfe5d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800bfe62  lea     rcx, [rbp+57h+var_60]
0x1800bfe66  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x1800bfe6b  mov     eax, ebx
0x1800bfe6d  mov     rcx, [rbp+57h+var_30]
0x1800bfe71  xor     rcx, rsp; StackCookie
0x1800bfe74  call    __security_check_cookie
0x1800bfe79  lea     r11, [rsp+0B0h+var_20]
0x1800bfe81  mov     rbx, [r11+40h]
0x1800bfe85  mov     rsi, [r11+48h]
0x1800bfe89  mov     rsp, r11
0x1800bfe8c  pop     r15
0x1800bfe8e  pop     r14
0x1800bfe90  pop     r12
0x1800bfe92  pop     rdi
0x1800bfe93  pop     rbp
0x1800bfe94  retn
0x1800bfe95  mov     rax, [r15]
0x1800bfe98  mov     rcx, r15
0x1800bfe9b  jmp     loc_1800BFDBF
```
