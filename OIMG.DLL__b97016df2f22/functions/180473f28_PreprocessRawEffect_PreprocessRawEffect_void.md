# PreprocessRawEffect::PreprocessRawEffect(void)

- ea: `0x180473f28`
- end: `0x18047423e`
- name: `??0PreprocessRawEffect@@IEAA@XZ`
- size: `790`
- prototype: `PreprocessRawEffect *__fastcall(PreprocessRawEffect *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180466aa0`
- `0x180468140`
- `0x180468300`

## callees

- `0x18019a570`
- `0x1803ea758`
- `0x180473f28`
- `0x1804c6944`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x180473f80`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180473f80`
- `KERNEL32!GetLastError` at `0x180474215`
- `KERNEL32!GetLastError` at `0x180474215`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180474072`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804740a5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180474072`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804740a5`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180474087`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804740ba`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804741ab`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804741e9`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180474087`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804740ba`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804741ab`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804741e9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180474189`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804741c7`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180474189`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804741c7`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18047419e`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1804741dc`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18047419e`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1804741dc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180474142`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180474142`

## string_xrefs

- `0x180473fd1`: `PreprocessRawEffect.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
PreprocessRawEffect *__fastcall PreprocessRawEffect::PreprocessRawEffect(PreprocessRawEffect *this)
{
  _QWORD *v2; // rsi
  __int64 v3; // rcx
  int v4; // eax
  SAFEARRAY *v5; // rax
  __int64 v6; // rcx
  SAFEARRAY *v7; // rax
  __int64 v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // rdi
  void *v11; // rcx
  int v12; // ecx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  signed int LastError; // eax
  unsigned int v18; // ecx
  SAFEARRAYBOUND rgsabound; // [rsp+68h] [rbp+28h] BYREF

  *((_DWORD *)this + 14) = 0;
  *((_OWORD *)this + 4) = 0;
  *((_OWORD *)this + 5) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_BYTE *)this + 104) = 0;
  v2 = (_QWORD *)((char *)this + 8);
  *((_QWORD *)this + 1) = &SingleThreadingModel::`vftable';
  rgsabound = (SAFEARRAYBOUND)((char *)this + 16);
  if ( !InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 16), 0, 0) )
  {
    LastError = GetLastError();
    v18 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v18 = LastError;
    ATL::BaseAtlThrow(v18);
  }
  *(_QWORD *)this = &EffectBase<PreprocessRawEffect,1204,1,&__s_GUID const _GUID_ec431fb9_c51b_4d1a_be26_d1c3316a366f>::`vftable'{for `IEffectRender'};
  *v2 = &EffectBase<PreprocessRawEffect,1204,1,&__s_GUID const _GUID_ec431fb9_c51b_4d1a_be26_d1c3316a366f>::`vftable'{for `SingleThreadingModel'};
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 16) = 0;
  v4 = DaVinciObjectFactory::CreateInstance<IEffectImpl>(v3, (char *)this + 136);
  *((_DWORD *)this + 30) = v4;
  if ( v4 >= 0 )
    *((_DWORD *)this + 30) = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64, _QWORD, const WCHAR *, const wchar_t *, _QWORD))(**((_QWORD **)this + 17) + 232LL))(
                               *((_QWORD *)this + 17),
                               &GUID_ec431fb9_c51b_4d1a_be26_d1c3316a366f,
                               2,
                               0,
                               &psz,
                               L"PreprocessRawEffect.xml",
                               0);
  *(_QWORD *)this = &PreprocessRawEffect::`vftable'{for `IEffectRender'};
  *v2 = &PreprocessRawEffect::`vftable'{for `SingleThreadingModel'};
  *((_QWORD *)this + 18) = 0;
  *((_BYTE *)this + 152) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_DWORD *)this + 46) = 0;
  *((_DWORD *)this + 47) = 1199570688;
  *((_DWORD *)this + 48) = 1065353216;
  *((_BYTE *)this + 196) = 0;
  rgsabound = 0;
  v5 = SafeArrayCreate(4u, 1u, &rgsabound);
  *((_QWORD *)this + 20) = v5;
  if ( v5 )
    SafeArrayLock(v5);
  rgsabound = 0;
  if ( !*((_QWORD *)this + 21) )
  {
    v7 = SafeArrayCreate(4u, 1u, &rgsabound);
    *((_QWORD *)this + 21) = v7;
    if ( v7 )
      SafeArrayLock(v7);
  }
  v8 = LargeAllocationNew<unsigned short>(v6, L"LinearizationTable");
  v9 = *((_QWORD *)this + 18);
  if ( v9 != v8 )
  {
    if ( v9 )
    {
      if ( ImagingEngine::s_singleton )
        v10 = *((_QWORD *)ImagingEngine::s_singleton + 10);
      else
        v10 = 0;
      if ( v10 )
      {
        rgsabound.cElements = 0;
        (*(void (__fastcall **)(__int64, __int64, SAFEARRAYBOUND *))(*(_QWORD *)v10 + 112LL))(v10, v9, &rgsabound);
        if ( rgsabound.cElements )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 88LL))(v10, *((_QWORD *)this + 18));
          goto LABEL_21;
        }
        v11 = (void *)*((_QWORD *)this + 18);
        if ( !v11 )
          goto LABEL_21;
      }
      else
      {
        v11 = (void *)*((_QWORD *)this + 18);
      }
      free(v11);
    }
LABEL_21:
    *((_QWORD *)this + 18) = v8;
  }
  v12 = 0;
  v13 = 0;
  do
  {
    *(_WORD *)(v13 + *((_QWORD *)this + 18)) = v12++;
    v13 += 2;
  }
  while ( v12 < 0x10000 );
  rgsabound = 0;
  v14 = *((_QWORD *)this + 20);
  if ( !v14 )
    ATL::BaseAtlThrow(-2147467259);
  if ( (*(_BYTE *)(v14 + 2) & 0x10) == 0 && SafeArrayUnlock((SAFEARRAY *)v14) >= 0 )
  {
    SafeArrayRedim(*((SAFEARRAY **)this + 20), &rgsabound);
    SafeArrayLock(*((SAFEARRAY **)this + 20));
  }
  rgsabound = 0;
  v15 = *((_QWORD *)this + 21);
  if ( !v15 )
    ATL::BaseAtlThrow(-2147467259);
  if ( (*(_BYTE *)(v15 + 2) & 0x10) == 0 && SafeArrayUnlock((SAFEARRAY *)v15) >= 0 )
  {
    SafeArrayRedim(*((SAFEARRAY **)this + 21), &rgsabound);
    SafeArrayLock(*((SAFEARRAY **)this + 21));
  }
  return this;
}

```

## disassembly

```asm
0x180473f28  mov     [rsp-18h+arg_10], rbx
0x180473f2d  mov     [rsp-18h+arg_18], rsi
0x180473f32  mov     [rsp-18h+arg_0], rcx
0x180473f37  push    rbp
0x180473f38  push    rdi
0x180473f39  push    r14
0x180473f3b  mov     rbp, rsp
0x180473f3e  sub     rsp, 40h
0x180473f42  mov     rbx, rcx
0x180473f45  xor     r14d, r14d
0x180473f48  mov     [rcx+38h], r14d
0x180473f4c  xorps   xmm0, xmm0
0x180473f4f  xor     eax, eax
0x180473f51  movups  xmmword ptr [rcx+40h], xmm0
0x180473f55  movups  xmmword ptr [rcx+50h], xmm0
0x180473f59  mov     [rcx+60h], rax
0x180473f5d  mov     [rcx+68h], r14b
0x180473f61  lea     rsi, [rcx+8]
0x180473f65  mov     qword ptr [rbp+rgsabound.cElements], rsi
0x180473f69  lea     rax, ??_7SingleThreadingModel@@6B@; const SingleThreadingModel::`vftable'
0x180473f70  mov     [rsi], rax
0x180473f73  lea     rcx, [rsi+8]; lpCriticalSection
0x180473f77  mov     qword ptr [rbp+rgsabound.cElements], rcx
0x180473f7b  xor     r8d, r8d; Flags
0x180473f7e  xor     edx, edx; dwSpinCount
0x180473f80  call    cs:__imp_InitializeCriticalSectionEx
0x180473f86  test    eax, eax
0x180473f88  jz      loc_180474215
0x180473f8e  lea     rax, ??_7?$EffectBase@VPreprocessRawEffect@@$0ELE@$00$1?_GUID_ec431fb9_c51b_4d1a_be26_d1c3316a366f@@3U__s_GUID@@B@@6BIEffectRender@@@; const EffectBase<PreprocessRawEffect,1204,1,&__s_GUID const _GUID_ec431fb9_c51b_4d1a_be26_d1c3316a366f>::`vftable'{for `IEffectRender'}
0x180473f95  mov     [rbx], rax
0x180473f98  lea     rax, ??_7?$EffectBase@VPreprocessRawEffect@@$0ELE@$00$1?_GUID_ec431fb9_c51b_4d1a_be26_d1c3316a366f@@3U__s_GUID@@B@@6BSingleThreadingModel@@@; const EffectBase<PreprocessRawEffect,1204,1,&__s_GUID const _GUID_ec431fb9_c51b_4d1a_be26_d1c3316a366f>::`vftable'{for `SingleThreadingModel'}
0x180473f9f  mov     [rsi], rax
0x180473fa2  mov     [rbx+70h], r14
0x180473fa6  lea     rdi, [rbx+88h]
0x180473fad  mov     [rdi], r14
0x180473fb0  mov     [rbx+80h], r14
0x180473fb7  mov     rdx, rdi
0x180473fba  call    ??$CreateInstance@UIEffectImpl@@@DaVinciObjectFactory@@SAJAEBU_GUID@@PEAPEAUIEffectImpl@@PEAUIUnknown@@@Z; DaVinciObjectFactory::CreateInstance<IEffectImpl>(_GUID const &,IEffectImpl * *,IUnknown *)
0x180473fbf  mov     [rbx+78h], eax
0x180473fc2  test    eax, eax
0x180473fc4  js      short loc_180474007
0x180473fc6  mov     rcx, [rdi]
0x180473fc9  mov     rax, [rcx]
0x180473fcc  mov     [rsp+40h+var_10], r14
0x180473fd1  lea     rdx, aPreprocessrawe; "PreprocessRawEffect.xml"
0x180473fd8  mov     [rsp+40h+var_18], rdx
0x180473fdd  lea     rdx, psz
0x180473fe4  mov     [rsp+40h+var_20], rdx
0x180473fe9  xor     r9d, r9d
0x180473fec  lea     r8d, [r14+2]
0x180473ff0  lea     rdx, _GUID_ec431fb9_c51b_4d1a_be26_d1c3316a366f
0x180473ff7  mov     rax, [rax+0E8h]
0x180473ffe  call    cs:__guard_dispatch_icall_fptr
0x180474004  mov     [rbx+78h], eax
0x180474007  lea     rax, ??_7PreprocessRawEffect@@6BIEffectRender@@@; const PreprocessRawEffect::`vftable'{for `IEffectRender'}
0x18047400e  mov     [rbx], rax
0x180474011  lea     rax, ??_7PreprocessRawEffect@@6BSingleThreadingModel@@@; const PreprocessRawEffect::`vftable'{for `SingleThreadingModel'}
0x180474018  mov     [rsi], rax
0x18047401b  mov     [rbx+90h], r14
0x180474022  mov     [rbx+98h], r14b
0x180474029  mov     [rbx+0A0h], r14
0x180474030  mov     [rbx+0A8h], r14
0x180474037  mov     [rbx+0B0h], r14
0x18047403e  mov     [rbx+0B8h], r14d
0x180474045  mov     dword ptr [rbx+0BCh], 477FFF00h
0x18047404f  mov     dword ptr [rbx+0C0h], 3F800000h
0x180474059  mov     [rbx+0C4h], r14b
0x180474060  mov     qword ptr [rbp+rgsabound.cElements], r14
0x180474064  mov     edi, 4
0x180474069  mov     ecx, edi; vt
0x18047406b  lea     r8, [rbp+rgsabound]; rgsabound
0x18047406f  lea     edx, [rdi-3]; cDims
0x180474072  call    cs:__imp_SafeArrayCreate
0x180474078  mov     [rbx+0A0h], rax
0x18047407f  test    rax, rax
0x180474082  jz      short loc_18047408D
0x180474084  mov     rcx, rax; psa
0x180474087  call    cs:__imp_SafeArrayLock
0x18047408d  mov     qword ptr [rbp+rgsabound.cElements], r14
0x180474091  cmp     [rbx+0A8h], r14
0x180474098  jnz     short loc_1804740C0
0x18047409a  mov     ecx, edi; vt
0x18047409c  lea     r8, [rbp+rgsabound]; rgsabound
0x1804740a0  mov     edx, 1; cDims
0x1804740a5  call    cs:__imp_SafeArrayCreate
0x1804740ab  mov     [rbx+0A8h], rax
0x1804740b2  test    rax, rax
0x1804740b5  jz      short loc_1804740C0
0x1804740b7  mov     rcx, rax; psa
0x1804740ba  call    cs:__imp_SafeArrayLock
0x1804740c0  lea     rdx, aLinearizationt; "LinearizationTable"
0x1804740c7  call    ??$LargeAllocationNew@G@@YAPEAG_KPEB_W@Z; LargeAllocationNew<ushort>(unsigned __int64,wchar_t const *)
0x1804740cc  mov     rsi, rax
0x1804740cf  mov     rdx, [rbx+90h]
0x1804740d6  cmp     rdx, rax
0x1804740d9  jz      short loc_180474150
0x1804740db  test    rdx, rdx
0x1804740de  jz      short loc_180474149
0x1804740e0  mov     rcx, cs:?s_singleton@ImagingEngine@@2USingleton@1@A; ImagingEngine::Singleton ImagingEngine::s_singleton
0x1804740e7  test    rcx, rcx
0x1804740ea  jz      short loc_1804740F2
0x1804740ec  mov     rdi, [rcx+50h]
0x1804740f0  jmp     short loc_1804740F5
0x1804740f2  mov     rdi, r14
0x1804740f5  test    rdi, rdi
0x1804740f8  jz      short loc_18047413F
0x1804740fa  mov     [rbp+rgsabound.cElements], r14d
0x1804740fe  mov     rax, [rdi]
0x180474101  lea     r8, [rbp+rgsabound]
0x180474105  mov     rcx, rdi
0x180474108  mov     rax, [rax+70h]
0x18047410c  call    cs:__guard_dispatch_icall_fptr
0x180474112  cmp     [rbp+rgsabound.cElements], r14d
0x180474116  jz      short loc_180474131
0x180474118  mov     rax, [rdi]
0x18047411b  mov     rdx, [rbx+90h]
0x180474122  mov     rcx, rdi
0x180474125  mov     rax, [rax+58h]
0x180474129  call    cs:__guard_dispatch_icall_fptr
0x18047412f  jmp     short loc_180474149
0x180474131  mov     rcx, [rbx+90h]
0x180474138  test    rcx, rcx
0x18047413b  jz      short loc_180474149
0x18047413d  jmp     short loc_180474142
0x18047413f  mov     rcx, rdx; Block
0x180474142  call    cs:__imp_free
0x180474148  nop
0x180474149  mov     [rbx+90h], rsi
0x180474150  mov     ecx, r14d
0x180474153  mov     rdx, r14
0x180474156  mov     rax, [rbx+90h]
0x18047415d  mov     [rdx+rax], cx
0x180474161  inc     ecx
0x180474163  lea     rdx, [rdx+2]
0x180474167  cmp     ecx, 10000h
0x18047416d  jl      short loc_180474156
0x18047416f  mov     qword ptr [rbp+rgsabound.cElements], r14
0x180474173  mov     rcx, [rbx+0A0h]; psa
0x18047417a  test    rcx, rcx
0x18047417d  jz      loc_180474233
0x180474183  test    byte ptr [rcx+2], 10h
0x180474187  jnz     short loc_1804741B1
0x180474189  call    cs:__imp_SafeArrayUnlock
0x18047418f  test    eax, eax
0x180474191  js      short loc_1804741B1
0x180474193  lea     rdx, [rbp+rgsabound]; psaboundNew
0x180474197  mov     rcx, [rbx+0A0h]; psa
0x18047419e  call    cs:__imp_SafeArrayRedim
0x1804741a4  mov     rcx, [rbx+0A0h]; psa
0x1804741ab  call    cs:__imp_SafeArrayLock
0x1804741b1  mov     qword ptr [rbp+rgsabound.cElements], r14
0x1804741b5  mov     rcx, [rbx+0A8h]; psa
0x1804741bc  test    rcx, rcx
0x1804741bf  jz      short loc_180474206
0x1804741c1  test    byte ptr [rcx+2], 10h
0x1804741c5  jnz     short loc_1804741F0
0x1804741c7  call    cs:__imp_SafeArrayUnlock
0x1804741cd  test    eax, eax
0x1804741cf  js      short loc_1804741F0
0x1804741d1  lea     rdx, [rbp+rgsabound]; psaboundNew
0x1804741d5  mov     rcx, [rbx+0A8h]; psa
0x1804741dc  call    cs:__imp_SafeArrayRedim
0x1804741e2  mov     rcx, [rbx+0A8h]; psa
0x1804741e9  call    cs:__imp_SafeArrayLock
0x1804741ef  nop
0x1804741f0  mov     rax, rbx
0x1804741f3  mov     rbx, [rsp+40h+arg_10]
0x1804741f8  mov     rsi, [rsp+40h+arg_18]
0x1804741fd  add     rsp, 40h
0x180474201  pop     r14
0x180474203  pop     rdi
0x180474204  pop     rbp
0x180474205  retn
0x180474206  mov     ecx, 80004005h; int
0x18047420b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180474211  jmp     short loc_180474214
0x180474214  nop
0x180474215  call    cs:__imp_GetLastError
0x18047421b  movzx   ecx, ax
0x18047421e  or      ecx, 80070000h
0x180474224  test    eax, eax
0x180474226  cmovle  ecx, eax; int
0x180474229  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047422f  jmp     short loc_180474232
0x180474232  nop
0x180474233  mov     ecx, 80004005h; int
0x180474238  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
