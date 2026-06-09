# SDK::Unit::EarlyCom::Reset(void)

- ea: `0x180016fc0`
- end: `0x1800171cb`
- name: `?Reset@EarlyCom@Unit@SDK@@QEAAXXZ`
- size: `523`
- prototype: `void __fastcall(void **ppIFactory)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180015e20`
- `0x180016730`

## callees

- `0x180003180`
- `0x180016fc0`
- `0x1800a0363`
- `0x1800a036f`
- `0x1800a037b`
- `0x1800bf3b0`

## pseudocode

```c
void __fastcall SDK::Unit::EarlyCom::Reset(void **ppIFactory)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void **v6; // r15
  void *v7; // rcx
  void *v8; // rcx
  D3D_FEATURE_LEVEL pFeatureLevel; // [rsp+50h] [rbp-58h] BYREF
  D3D_FEATURE_LEVEL pFeatureLevels[4]; // [rsp+58h] [rbp-50h] BYREF
  int v11; // [rsp+68h] [rbp-40h]
  int v12; // [rsp+6Ch] [rbp-3Ch]
  int v13; // [rsp+70h] [rbp-38h]

  v2 = ppIFactory[6];
  if ( v2 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v2 + 16LL))(v2);
  ppIFactory[6] = 0;
  v3 = ppIFactory[5];
  if ( v3 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v3 + 16LL))(v3);
  ppIFactory[5] = 0;
  v4 = ppIFactory[4];
  if ( v4 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
  ppIFactory[4] = 0;
  v5 = ppIFactory[1];
  if ( v5 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = ppIFactory + 2;
  ppIFactory[1] = 0;
  v7 = ppIFactory[2];
  if ( v7 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
  *v6 = 0;
  v8 = ppIFactory[3];
  if ( v8 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
  ppIFactory[3] = 0;
  if ( *ppIFactory )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*ppIFactory + 16LL))(*ppIFactory);
  *ppIFactory = 0;
  D2D1CreateFactory_0(D2D1_FACTORY_TYPE_MULTI_THREADED, &GUID_bb12d362_daee_4b9a_aa1d_14ba401cfa1f, 0, ppIFactory);
  *(__m128i *)pFeatureLevels = _mm_load_si128((const __m128i *)&_xmm);
  v11 = 37632;
  v12 = 37376;
  v13 = 37120;
  if ( !D3D11CreateDevice_0(
          0,
          D3D_DRIVER_TYPE_HARDWARE,
          0,
          0x20u,
          pFeatureLevels,
          7u,
          7u,
          (ID3D11Device **)ppIFactory + 2,
          &pFeatureLevel,
          (ID3D11DeviceContext **)ppIFactory + 3)
    && !(**(unsigned int (__fastcall ***)(void *, GUID *, void **))*v6)(
          *v6,
          &GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c,
          ppIFactory + 1)
    && *ppIFactory
    && !(*(unsigned int (__fastcall **)(_QWORD, void *, void **))(*(_QWORD *)*ppIFactory + 136LL))(
          *ppIFactory,
          ppIFactory[1],
          ppIFactory + 4)
    && !(*(unsigned int (__fastcall **)(void *, __int64, void **))(*(_QWORD *)ppIFactory[4] + 32LL))(
          ppIFactory[4],
          1,
          ppIFactory + 5) )
  {
    PdfCreateRenderer_0();
  }
}

```

## disassembly

```asm
0x180016fc0  mov     [rsp+arg_8], rbx
0x180016fc5  mov     [rsp+arg_10], rbp
0x180016fca  mov     [rsp+arg_18], rsi
0x180016fcf  push    rdi
0x180016fd0  push    r12
0x180016fd2  push    r13
0x180016fd4  push    r14
0x180016fd6  push    r15
0x180016fd8  sub     rsp, 80h
0x180016fdf  mov     rax, cs:__security_cookie
0x180016fe6  xor     rax, rsp
0x180016fe9  mov     [rsp+0A8h+var_30], rax
0x180016fee  mov     rbx, rcx
0x180016ff1  mov     rcx, [rcx+30h]
0x180016ff5  test    rcx, rcx
0x180016ff8  jz      short loc_180017007
0x180016ffa  mov     rax, [rcx]
0x180016ffd  mov     rax, [rax+10h]
0x180017001  call    cs:__guard_dispatch_icall_fptr
0x180017007  xor     r13d, r13d
0x18001700a  mov     [rbx+30h], r13
0x18001700e  mov     rcx, [rbx+28h]
0x180017012  test    rcx, rcx
0x180017015  jz      short loc_180017024
0x180017017  mov     rax, [rcx]
0x18001701a  mov     rax, [rax+10h]
0x18001701e  call    cs:__guard_dispatch_icall_fptr
0x180017024  mov     [rbx+28h], r13
0x180017028  mov     rcx, [rbx+20h]
0x18001702c  test    rcx, rcx
0x18001702f  jz      short loc_18001703E
0x180017031  mov     rax, [rcx]
0x180017034  mov     rax, [rax+10h]
0x180017038  call    cs:__guard_dispatch_icall_fptr
0x18001703e  mov     [rbx+20h], r13
0x180017042  mov     rcx, [rbx+8]
0x180017046  test    rcx, rcx
0x180017049  jz      short loc_180017058
0x18001704b  mov     rax, [rcx]
0x18001704e  mov     rax, [rax+10h]
0x180017052  call    cs:__guard_dispatch_icall_fptr
0x180017058  lea     r15, [rbx+10h]
0x18001705c  mov     [rbx+8], r13
0x180017060  mov     rcx, [r15]
0x180017063  test    rcx, rcx
0x180017066  jz      short loc_180017075
0x180017068  mov     rax, [rcx]
0x18001706b  mov     rax, [rax+10h]
0x18001706f  call    cs:__guard_dispatch_icall_fptr
0x180017075  lea     r12, [rbx+18h]
0x180017079  mov     [r15], r13
0x18001707c  mov     rcx, [r12]
0x180017080  test    rcx, rcx
0x180017083  jz      short loc_180017092
0x180017085  mov     rax, [rcx]
0x180017088  mov     rax, [rax+10h]
0x18001708c  call    cs:__guard_dispatch_icall_fptr
0x180017092  mov     [r12], r13
0x180017096  mov     rcx, [rbx]
0x180017099  test    rcx, rcx
0x18001709c  jz      short loc_1800170AB
0x18001709e  mov     rax, [rcx]
0x1800170a1  mov     rax, [rax+10h]
0x1800170a5  call    cs:__guard_dispatch_icall_fptr
0x1800170ab  xor     r8d, r8d; pFactoryOptions
0x1800170ae  mov     [rbx], r13
0x1800170b1  mov     r9, rbx; ppIFactory
0x1800170b4  lea     rdx, _GUID_bb12d362_daee_4b9a_aa1d_14ba401cfa1f; riid
0x1800170bb  lea     ecx, [r8+1]; factoryType
0x1800170bf  call    D2D1CreateFactory_0
0x1800170c4  movdqa  xmm0, cs:__xmm@0000a0000000a1000000b0000000b100
0x1800170cc  lea     rax, [rsp+0A8h+var_58]
0x1800170d1  mov     [rsp+0A8h+ppImmediateContext], r12; ppImmediateContext
0x1800170d6  mov     r9d, 20h ; ' '; Flags
0x1800170dc  mov     [rsp+0A8h+pFeatureLevel], rax; pFeatureLevel
0x1800170e1  xor     r8d, r8d; Software
0x1800170e4  mov     [rsp+0A8h+ppDevice], r15; ppDevice
0x1800170e9  lea     rax, [rsp+0A8h+var_50]
0x1800170ee  mov     [rsp+0A8h+SDKVersion], 7; SDKVersion
0x1800170f6  xor     ecx, ecx; pAdapter
0x1800170f8  mov     [rsp+0A8h+FeatureLevels], 7; FeatureLevels
0x180017100  lea     edx, [r9-1Fh]; DriverType
0x180017104  mov     [rsp+0A8h+pFeatureLevels], rax; pFeatureLevels
0x180017109  movdqu  xmmword ptr [rsp+0A8h+var_50], xmm0
0x18001710f  mov     [rsp+0A8h+var_40], 9300h
0x180017117  mov     [rsp+0A8h+var_3C], 9200h
0x18001711f  mov     [rsp+0A8h+var_38], 9100h
0x180017127  call    D3D11CreateDevice_0
0x18001712c  test    eax, eax
0x18001712e  jnz     short loc_18001719D
0x180017130  mov     rcx, [r15]
0x180017133  lea     r8, [rbx+8]
0x180017137  lea     rdx, _GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c
0x18001713e  mov     rax, [rcx]
0x180017141  mov     rax, [rax]
0x180017144  call    cs:__guard_dispatch_icall_fptr
0x18001714a  test    eax, eax
0x18001714c  jnz     short loc_18001719D
0x18001714e  mov     rcx, [rbx]
0x180017151  test    rcx, rcx
0x180017154  jz      short loc_18001719D
0x180017156  mov     rax, [rcx]
0x180017159  lea     r8, [rbx+20h]
0x18001715d  mov     rdx, [rbx+8]
0x180017161  mov     rax, [rax+88h]
0x180017168  call    cs:__guard_dispatch_icall_fptr
0x18001716e  test    eax, eax
0x180017170  jnz     short loc_18001719D
0x180017172  mov     rcx, [rbx+20h]
0x180017176  lea     r8, [rbx+28h]
0x18001717a  mov     edx, 1
0x18001717f  mov     rax, [rcx]
0x180017182  mov     rax, [rax+20h]
0x180017186  call    cs:__guard_dispatch_icall_fptr
0x18001718c  test    eax, eax
0x18001718e  jnz     short loc_18001719D
0x180017190  mov     rcx, [rbx+8]
0x180017194  lea     rdx, [rbx+30h]
0x180017198  call    PdfCreateRenderer_0
0x18001719d  mov     rcx, [rsp+0A8h+var_30]
0x1800171a2  xor     rcx, rsp; StackCookie
0x1800171a5  call    __security_check_cookie
0x1800171aa  lea     r11, [rsp+0A8h+var_28]
0x1800171b2  mov     rbx, [r11+38h]
0x1800171b6  mov     rbp, [r11+40h]
0x1800171ba  mov     rsi, [r11+48h]
0x1800171be  mov     rsp, r11
0x1800171c1  pop     r15
0x1800171c3  pop     r14
0x1800171c5  pop     r13
0x1800171c7  pop     r12
0x1800171c9  pop     rdi
0x1800171ca  retn
```
