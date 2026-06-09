# CWICBitmapToneMapper::EnsureD2DInitialized(ID3D11Device *)

- ea: `0x1800c1f5c`
- end: `0x1800c218d`
- name: `?EnsureD2DInitialized@CWICBitmapToneMapper@@AEAAJPEAUID3D11Device@@@Z`
- size: `561`
- prototype: `__int64 __fastcall(CWICBitmapToneMapper *__hidden this, struct ID3D11Device *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c1db0`
- `0x1800c21b4`

## callees

- `0x18009a95c`
- `0x1800bd9d4`
- `0x1800c1f5c`
- `0x1800e5e60`
- `0x1801ce010`

## import_xrefs

- `d2d1!__imp_D2D1CreateFactory` at `0x1800c1fb4`
- `d2d1!__imp_D2D1CreateFactory` at `0x1800c1fb4`
- `d3d11!D3D11CreateDevice` at `0x1800c2076`
- `d3d11!D3D11CreateDevice` at `0x1800c2076`

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
0x1800c1f5c  mov     [rsp-8+arg_10], rbx
0x1800c1f61  mov     [rsp-8+arg_18], rsi
0x1800c1f66  push    rbp
0x1800c1f67  push    rdi
0x1800c1f68  push    r12
0x1800c1f6a  push    r14
0x1800c1f6c  push    r15
0x1800c1f6e  lea     rbp, [rsp-37h]
0x1800c1f73  sub     rsp, 90h
0x1800c1f7a  mov     rax, cs:__security_cookie
0x1800c1f81  xor     rax, rsp
0x1800c1f84  mov     [rbp+57h+var_30], rax
0x1800c1f88  xor     r12d, r12d
0x1800c1f8b  lea     r14, [rcx+60h]
0x1800c1f8f  mov     r15, rdx
0x1800c1f92  mov     rdi, rcx
0x1800c1f95  mov     ebx, r12d
0x1800c1f98  cmp     [r14], r12
0x1800c1f9b  jnz     short loc_1800C1FE3
0x1800c1f9d  mov     r9, r14; ppIFactory
0x1800c1fa0  mov     [rbp+57h+pFactoryOptions.debugLevel], r12d
0x1800c1fa4  lea     r8, [rbp+57h+pFactoryOptions]; pFactoryOptions
0x1800c1fa8  mov     [r14], r12
0x1800c1fab  lea     rdx, _GUID_f9976f46_f642_44c1_97ca_da32ea2a2635; riid
0x1800c1fb2  xor     ecx, ecx; factoryType
0x1800c1fb4  call    cs:__imp_D2D1CreateFactory
0x1800c1fbb  nop     dword ptr [rax+rax+00h]
0x1800c1fc0  mov     ebx, eax
0x1800c1fc2  test    eax, eax
0x1800c1fc4  jns     short loc_1800C1FE3
0x1800c1fc6  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800c1fcd  jz      short loc_1800C1FDB
0x1800c1fcf  mov     ecx, eax; int
0x1800c1fd1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800c1fd6  jmp     loc_1800C2157
0x1800c1fdb  test    eax, eax
0x1800c1fdd  js      loc_1800C2157
0x1800c1fe3  lea     rsi, [rdi+78h]
0x1800c1fe7  cmp     [rsi], r12
0x1800c1fea  jnz     loc_1800C2157
0x1800c1ff0  mov     [rbp+57h+var_60], r12
0x1800c1ff4  test    r15, r15
0x1800c1ff7  jnz     loc_1800C2182
0x1800c1ffd  movdqa  xmm0, cs:__xmm@0000a0000000a1000000b0000000b100
0x1800c2005  lea     r15, [rdi+70h]
0x1800c2009  mov     rcx, [r15]
0x1800c200c  mov     [rbp+57h+var_40], 9300h
0x1800c2013  mov     [rbp+57h+var_3C], 9200h
0x1800c201a  mov     [rbp+57h+var_38], 9100h
0x1800c2021  mov     [rbp+57h+pFactoryOptions.debugLevel], r12d
0x1800c2025  mov     [r15], r12
0x1800c2028  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x1800c202d  test    rcx, rcx
0x1800c2030  jz      short loc_1800C203E
0x1800c2032  mov     rax, [rcx]
0x1800c2035  mov     rax, [rax+10h]
0x1800c2039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c203e  mov     [rsp+0B0h+ppImmediateContext], r12; ppImmediateContext
0x1800c2043  lea     rax, [rbp+57h+pFactoryOptions]
0x1800c2047  mov     [rsp+0B0h+pFeatureLevel], rax; pFeatureLevel
0x1800c204c  mov     r9d, 20h ; ' '; Flags
0x1800c2052  mov     eax, 7
0x1800c2057  mov     [rsp+0B0h+ppDevice], r15; ppDevice
0x1800c205c  mov     [rsp+0B0h+SDKVersion], eax; SDKVersion
0x1800c2060  xor     r8d, r8d; Software
0x1800c2063  mov     [rsp+0B0h+FeatureLevels], eax; FeatureLevels
0x1800c2067  xor     ecx, ecx; pAdapter
0x1800c2069  lea     rax, [rbp+57h+var_50]
0x1800c206d  lea     edx, [r9-1Bh]; DriverType
0x1800c2071  mov     [rsp+0B0h+pFeatureLevels], rax; pFeatureLevels
0x1800c2076  call    cs:__imp_D3D11CreateDevice
0x1800c207d  nop     dword ptr [rax+rax+00h]
0x1800c2082  mov     ebx, eax
0x1800c2084  test    eax, eax
0x1800c2086  js      loc_1800C213E
0x1800c208c  mov     rcx, [rbp+57h+var_60]
0x1800c2090  mov     [rbp+57h+var_60], r12
0x1800c2094  test    rcx, rcx
0x1800c2097  jz      short loc_1800C20A5
0x1800c2099  mov     rax, [rcx]
0x1800c209c  mov     rax, [rax+10h]
0x1800c20a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c20a5  mov     rcx, [r15]
0x1800c20a8  mov     rax, [rcx]
0x1800c20ab  mov     rax, [rax]
0x1800c20ae  lea     rdx, _GUID_6007896c_3244_4afd_bf18_a6d3beda5023
0x1800c20b5  lea     r8, [rbp+57h+var_60]
0x1800c20b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c20be  mov     ebx, eax
0x1800c20c0  test    eax, eax
0x1800c20c2  js      short loc_1800C213E
0x1800c20c4  mov     rbx, [r14]
0x1800c20c7  mov     rcx, [rdi+68h]
0x1800c20cb  mov     rax, [rbx]
0x1800c20ce  mov     [rdi+68h], r12
0x1800c20d2  mov     r14, [rax+0F8h]
0x1800c20d9  test    rcx, rcx
0x1800c20dc  jz      short loc_1800C20EA
0x1800c20de  mov     rax, [rcx]
0x1800c20e1  mov     rax, [rax+10h]
0x1800c20e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c20ea  mov     rdx, [rbp+57h+var_60]
0x1800c20ee  lea     r8, [rdi+68h]
0x1800c20f2  mov     rcx, rbx
0x1800c20f5  mov     rax, r14
0x1800c20f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c20fd  mov     ebx, eax
0x1800c20ff  test    eax, eax
0x1800c2101  js      short loc_1800C213E
0x1800c2103  mov     rbx, [rdi+68h]
0x1800c2107  mov     rcx, [rsi]
0x1800c210a  mov     rax, [rbx]
0x1800c210d  mov     [rsi], r12
0x1800c2110  mov     rdi, [rax+98h]
0x1800c2117  test    rcx, rcx
0x1800c211a  jz      short loc_1800C2128
0x1800c211c  mov     rax, [rcx]
0x1800c211f  mov     rax, [rax+10h]
0x1800c2123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2128  mov     r8, rsi
0x1800c212b  xor     edx, edx
0x1800c212d  mov     rcx, rbx
0x1800c2130  mov     rax, rdi
0x1800c2133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2138  mov     ebx, eax
0x1800c213a  test    eax, eax
0x1800c213c  jns     short loc_1800C214E
0x1800c213e  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800c2145  jz      short loc_1800C214E
0x1800c2147  mov     ecx, eax; int
0x1800c2149  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800c214e  lea     rcx, [rbp+57h+var_60]
0x1800c2152  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x1800c2157  mov     eax, ebx
0x1800c2159  mov     rcx, [rbp+57h+var_30]
0x1800c215d  xor     rcx, rsp; StackCookie
0x1800c2160  call    __security_check_cookie
0x1800c2165  lea     r11, [rsp+0B0h+var_20]
0x1800c216d  mov     rbx, [r11+40h]
0x1800c2171  mov     rsi, [r11+48h]
0x1800c2175  mov     rsp, r11
0x1800c2178  pop     r15
0x1800c217a  pop     r14
0x1800c217c  pop     r12
0x1800c217e  pop     rdi
0x1800c217f  pop     rbp
0x1800c2180  retn
0x1800c2182  mov     rax, [r15]
0x1800c2185  mov     rcx, r15
0x1800c2188  jmp     loc_1800C20AB
```
