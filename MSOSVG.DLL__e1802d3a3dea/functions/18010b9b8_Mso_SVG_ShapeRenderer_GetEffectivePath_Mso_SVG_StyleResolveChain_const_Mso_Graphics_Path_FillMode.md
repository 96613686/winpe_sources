# Mso::SVG::ShapeRenderer::GetEffectivePath(Mso::SVG::StyleResolveChain const &,Mso::Graphics::Path::FillMode)

- ea: `0x18010b9b8`
- end: `0x18010bc58`
- name: `?GetEffectivePath@ShapeRenderer@SVG@Mso@@AEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@W4FillMode@Path@Graphics@3@@Z`
- size: `672`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18010bc80`
- `0x18010beb0`

## callees

- `0x180043578`
- `0x18004c038`
- `0x180101700`
- `0x180101798`
- `0x180103fb8`
- `0x180104044`
- `0x18010b9b8`
- `0x18013e010`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010bc51`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010bc51`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x18010bb5a`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x18010bb5a`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x18010bc03`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x18010bc03`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x18010bbb3`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x18010bbb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall Mso::SVG::ShapeRenderer::GetEffectivePath(
        Mso::SVG::RenderableRenderer *a1,
        _QWORD *a2,
        _QWORD *a3,
        unsigned int a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int16 *v10; // rcx
  __int64 v11; // rax
  _QWORD *v12; // rbx
  _QWORD *v13; // r13
  void (__fastcall ***v14)(_QWORD); // rsi
  void (__fastcall ***v15)(_QWORD); // rbx
  _QWORD *v16; // rax
  void (__fastcall ***v17)(_QWORD); // rcx
  _QWORD *v18; // rax
  void (__fastcall ***v19)(_QWORD); // rsi
  void (__fastcall ***v20)(_QWORD); // rcx
  void (__fastcall ***v22)(_QWORD); // [rsp+38h] [rbp-49h] BYREF
  unsigned int v23; // [rsp+40h] [rbp-41h] BYREF
  void (__fastcall ***v24)(_QWORD); // [rsp+48h] [rbp-39h]
  _QWORD v25[2]; // [rsp+58h] [rbp-29h] BYREF
  int v26; // [rsp+68h] [rbp-19h]
  __int64 v27; // [rsp+70h] [rbp-11h]
  _BYTE v28[64]; // [rsp+78h] [rbp-9h] BYREF

  if ( !Mso::SVG::RenderableRenderer::IsRenderingEnabled(a1) || !*(_BYTE *)Mso::SVG::StyleResolveChain::Get<30>(a3) )
    goto LABEL_37;
  v8 = a3[1];
  v9 = *(_QWORD *)(v8 + 16);
  if ( v9 )
  {
    v10 = (__int16 *)(v9 + 552);
  }
  else
  {
    v10 = &Mso::SVG::StyleMetaData<28>::initial;
    if ( *(_QWORD *)(v8 + 8) )
      v10 = (__int16 *)&Mso::SVG::StyleMetaData<28>::inherit;
  }
  if ( !*((_BYTE *)v10 + 1) )
  {
    if ( *a3 )
      v11 = Mso::SVG::StyleResolveChain::Get<28>();
    else
      v11 = Mso::SVG::StyleResolveChain::GetNormal<28>(a3, *(_QWORD *)(v8 + 8));
    v10 = (__int16 *)v11;
  }
  if ( !*(_BYTE *)v10 )
  {
LABEL_37:
    *a2 = 0;
    return a2;
  }
  v12 = (_QWORD *)*((_QWORD *)a1 + 2);
  if ( !v12 )
  {
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x18010BC57LL);
  }
  _castguard_slow_path_check_user_handled(*v12, 3768, 3024);
  v13 = v12 + 41;
  Mso::SVG::PathCacher::GetCached(v12 + 41, &v22, a3);
  v14 = v22;
  if ( v22 )
  {
    if ( ((unsigned int (__fastcall *)(_QWORD))(*v22)[25])(v22) != a4 )
    {
      v15 = 0;
      v24 = 0;
      (*v14)[1](v14);
      v14 = 0;
      goto LABEL_20;
    }
    v15 = v14;
  }
  else
  {
    v15 = 0;
  }
  v24 = v15;
LABEL_20:
  if ( v14 )
  {
LABEL_36:
    *a2 = v15;
    return a2;
  }
  v23 = 0;
  v16 = (_QWORD *)(*(__int64 (__fastcall **)(Mso::SVG::RenderableRenderer *, void (__fastcall ****)(_QWORD), _QWORD *, unsigned int *))(*(_QWORD *)a1 + 48LL))(
                    a1,
                    &v22,
                    a3,
                    &v23);
  v15 = (void (__fastcall ***)(_QWORD))*v16;
  *v16 = 0;
  v24 = v15;
  v17 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*v17)[1](v17);
  }
  if ( v15 )
  {
    if ( a4 != ((unsigned int (__fastcall *)(_QWORD))(*v15)[25])(v15) )
    {
      GEL::PathBuilder::PathBuilder((GEL::PathBuilder *)v28);
      v25[1] = v28;
      v26 = 0;
      v27 = 0;
      v25[0] = &Mso::Graphics::Path::TValidatedPathSegmentSink<GEL::PathBuilderPathSegmentSinkImpl>::`vftable';
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD), _QWORD *))(*v15)[22])(v15, v25);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
      v18 = (_QWORD *)GEL::PathBuilder::Finish(v28, &v22, a4);
      v19 = (void (__fastcall ***)(_QWORD))*v18;
      if ( *v18 )
        (**v19)(*v18);
      v20 = v15;
      v15 = v19;
      (*v20)[1](v20);
      if ( v22 )
        (*v22)[1](v22);
      GEL::PathBuilder::~PathBuilder((GEL::PathBuilder *)v28);
    }
    Mso::SVG::PathCacher::Cache(v13, v15, a3, v23);
    goto LABEL_36;
  }
  *a2 = 0;
  return a2;
}

```

## disassembly

```asm
0x18010b9b8  mov     rax, rsp
0x18010b9bb  mov     [rax+8], rbx
0x18010b9bf  mov     [rax+10h], rsi
0x18010b9c3  mov     [rax+18h], rdi
0x18010b9c7  push    rbp
0x18010b9c8  push    r12
0x18010b9ca  push    r13
0x18010b9cc  push    r14
0x18010b9ce  push    r15
0x18010b9d0  lea     rbp, [rax-5Fh]
0x18010b9d4  sub     rsp, 0B0h
0x18010b9db  mov     r12d, r9d
0x18010b9de  mov     r14, r8
0x18010b9e1  mov     rdi, rdx
0x18010b9e4  mov     r15, rcx
0x18010b9e7  xor     esi, esi
0x18010b9e9  call    ?IsRenderingEnabled@RenderableRenderer@SVG@Mso@@QEBA_NXZ; Mso::SVG::RenderableRenderer::IsRenderingEnabled(void)
0x18010b9ee  test    al, al
0x18010b9f0  jz      loc_18010BC23
0x18010b9f6  mov     rcx, r14
0x18010b9f9  call    ??$Get@$0BO@@StyleResolveChain@SVG@Mso@@QEBAAEB_NXZ; Mso::SVG::StyleResolveChain::Get<30>(void)
0x18010b9fe  cmp     [rax], sil
0x18010ba01  jz      loc_18010BC23
0x18010ba07  mov     rdx, [r14+8]
0x18010ba0b  mov     rcx, [rdx+10h]
0x18010ba0f  test    rcx, rcx
0x18010ba12  jz      short loc_18010BA1D
0x18010ba14  add     rcx, 228h
0x18010ba1b  jmp     short loc_18010BA31
0x18010ba1d  cmp     [rdx+8], rsi
0x18010ba21  lea     rcx, ?initial@?$StyleMetaData@$0BM@@SVG@Mso@@2V?$optional@_N@std@@B; std::optional<bool> const Mso::SVG::StyleMetaData<28>::initial
0x18010ba28  jz      short loc_18010BA31
0x18010ba2a  lea     rcx, ?inherit@?$StyleMetaData@$0BM@@SVG@Mso@@2V?$optional@_N@std@@B; std::optional<bool> const Mso::SVG::StyleMetaData<28>::inherit
0x18010ba31  mov     eax, 8
0x18010ba36  cmp     [rcx+1], sil
0x18010ba3a  jnz     short loc_18010BA5A
0x18010ba3c  mov     rcx, [r14]
0x18010ba3f  test    rcx, rcx
0x18010ba42  jz      short loc_18010BA4B
0x18010ba44  call    ??$Get@$0BM@@StyleResolveChain@SVG@Mso@@QEBAAEB_NXZ; Mso::SVG::StyleResolveChain::Get<28>(void)
0x18010ba49  jmp     short loc_18010BA57
0x18010ba4b  mov     rdx, [rax+rdx]
0x18010ba4f  mov     rcx, r14
0x18010ba52  call    ??$GetNormal@$0BM@@StyleResolveChain@SVG@Mso@@AEBAAEB_NAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<28>(Mso::SVG::Style const &)
0x18010ba57  mov     rcx, rax
0x18010ba5a  cmp     [rcx], sil
0x18010ba5d  jz      loc_18010BC23
0x18010ba63  mov     rbx, [r15+10h]
0x18010ba67  test    rbx, rbx
0x18010ba6a  jz      loc_18010BC4A
0x18010ba70  mov     edx, 0EB8h
0x18010ba75  mov     r8d, 0BD0h
0x18010ba7b  mov     rcx, [rbx]
0x18010ba7e  call    __castguard_slow_path_check_user_handled
0x18010ba83  lea     r13, [rbx+148h]
0x18010ba8a  mov     r8, r14
0x18010ba8d  lea     rdx, [rbp+57h+var_A0]
0x18010ba91  mov     rcx, r13
0x18010ba94  call    ?GetCached@PathCacher@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@@Z; Mso::SVG::PathCacher::GetCached(Mso::SVG::StyleResolveChain const &)
0x18010ba99  mov     rsi, [rbp+57h+var_A0]
0x18010ba9d  test    rsi, rsi
0x18010baa0  jnz     short loc_18010BAA6
0x18010baa2  xor     ebx, ebx
0x18010baa4  jmp     short loc_18010BADB
0x18010baa6  mov     rax, [rsi]
0x18010baa9  mov     rcx, rsi
0x18010baac  mov     rax, [rax+0C8h]
0x18010bab3  call    cs:__guard_dispatch_icall_fptr
0x18010bab9  cmp     eax, r12d
0x18010babc  jz      short loc_18010BAD8
0x18010babe  xor     ebx, ebx
0x18010bac0  mov     [rbp+57h+var_90], rbx
0x18010bac4  mov     rax, [rsi]
0x18010bac7  mov     rcx, rsi
0x18010baca  mov     rax, [rax+8]
0x18010bace  call    cs:__guard_dispatch_icall_fptr
0x18010bad4  xor     esi, esi
0x18010bad6  jmp     short loc_18010BADF
0x18010bad8  mov     rbx, rsi
0x18010badb  mov     [rbp+57h+var_90], rbx
0x18010badf  test    rsi, rsi
0x18010bae2  jnz     loc_18010BC1B
0x18010bae8  mov     [rbp+57h+var_98], esi
0x18010baeb  mov     rax, [r15]
0x18010baee  lea     r9, [rbp+57h+var_98]
0x18010baf2  mov     r8, r14
0x18010baf5  lea     rdx, [rbp+57h+var_A0]
0x18010baf9  mov     rcx, r15
0x18010bafc  mov     rax, [rax+30h]
0x18010bb00  call    cs:__guard_dispatch_icall_fptr
0x18010bb06  mov     rbx, [rax]
0x18010bb09  xor     r15d, r15d
0x18010bb0c  mov     [rax], r15
0x18010bb0f  mov     [rbp+57h+var_90], rbx
0x18010bb13  mov     rcx, [rbp+57h+var_A0]
0x18010bb17  test    rcx, rcx
0x18010bb1a  jz      short loc_18010BB2D
0x18010bb1c  mov     [rbp+57h+var_A0], r15
0x18010bb20  mov     rax, [rcx]
0x18010bb23  mov     rax, [rax+8]
0x18010bb27  call    cs:__guard_dispatch_icall_fptr
0x18010bb2d  test    rbx, rbx
0x18010bb30  jnz     short loc_18010BB3A
0x18010bb32  mov     [rdi], r15
0x18010bb35  jmp     loc_18010BC26
0x18010bb3a  mov     rax, [rbx]
0x18010bb3d  mov     rcx, rbx
0x18010bb40  mov     rax, [rax+0C8h]
0x18010bb47  call    cs:__guard_dispatch_icall_fptr
0x18010bb4d  cmp     r12d, eax
0x18010bb50  jz      loc_18010BC09
0x18010bb56  lea     rcx, [rbp+57h+var_60]
0x18010bb5a  call    cs:__imp_??0PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::PathBuilder(void)
0x18010bb60  lea     rax, [rbp+57h+var_60]
0x18010bb64  mov     [rbp+57h+var_78], rax
0x18010bb68  mov     [rbp+57h+var_70], r15d
0x18010bb6c  mov     [rbp+57h+var_68], r15
0x18010bb70  lea     rax, ??_7?$TValidatedPathSegmentSink@VPathBuilderPathSegmentSinkImpl@GEL@@@Path@Graphics@Mso@@6B@; const Mso::Graphics::Path::TValidatedPathSegmentSink<GEL::PathBuilderPathSegmentSinkImpl>::`vftable'
0x18010bb77  mov     [rbp+57h+var_80], rax
0x18010bb7b  mov     rax, [rbx]
0x18010bb7e  lea     rdx, [rbp+57h+var_80]
0x18010bb82  mov     rcx, rbx
0x18010bb85  mov     rax, [rax+0B0h]
0x18010bb8c  call    cs:__guard_dispatch_icall_fptr
0x18010bb92  mov     rcx, [rbp+57h+var_68]
0x18010bb96  test    rcx, rcx
0x18010bb99  jz      short loc_18010BBA8
0x18010bb9b  mov     rax, [rcx]
0x18010bb9e  mov     rax, [rax+8]
0x18010bba2  call    cs:__guard_dispatch_icall_fptr
0x18010bba8  mov     r8d, r12d
0x18010bbab  lea     rdx, [rbp+57h+var_A0]
0x18010bbaf  lea     rcx, [rbp+57h+var_60]
0x18010bbb3  call    cs:__imp_?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z; GEL::PathBuilder::Finish(Mso::Graphics::Path::FillMode)
0x18010bbb9  mov     rsi, [rax]
0x18010bbbc  test    rsi, rsi
0x18010bbbf  jz      short loc_18010BBD0
0x18010bbc1  mov     rax, [rsi]
0x18010bbc4  mov     rcx, rsi
0x18010bbc7  mov     rax, [rax]
0x18010bbca  call    cs:__guard_dispatch_icall_fptr
0x18010bbd0  mov     rcx, rbx
0x18010bbd3  mov     rbx, rsi
0x18010bbd6  test    rcx, rcx
0x18010bbd9  jz      short loc_18010BBE8
0x18010bbdb  mov     rax, [rcx]
0x18010bbde  mov     rax, [rax+8]
0x18010bbe2  call    cs:__guard_dispatch_icall_fptr
0x18010bbe8  mov     rcx, [rbp+57h+var_A0]
0x18010bbec  test    rcx, rcx
0x18010bbef  jz      short loc_18010BBFF
0x18010bbf1  mov     rax, [rcx]
0x18010bbf4  mov     rax, [rax+8]
0x18010bbf8  call    cs:__guard_dispatch_icall_fptr
0x18010bbfe  nop
0x18010bbff  lea     rcx, [rbp+57h+var_60]
0x18010bc03  call    cs:__imp_??1PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::~PathBuilder(void)
0x18010bc09  mov     r9d, [rbp+57h+var_98]
0x18010bc0d  mov     r8, r14
0x18010bc10  mov     rdx, rbx
0x18010bc13  mov     rcx, r13
0x18010bc16  call    ?Cache@PathCacher@SVG@Mso@@QEAAXAEBUIPath@GEL@@AEBVStyleResolveChain@23@W4PathDependencyFlags@123@@Z; Mso::SVG::PathCacher::Cache(GEL::IPath const &,Mso::SVG::StyleResolveChain const &,Mso::SVG::PathCacher::PathDependencyFlags)
0x18010bc1b  mov     [rdi], rbx
0x18010bc1e  jmp     loc_18010BB35
0x18010bc23  mov     [rdi], rsi
0x18010bc26  mov     rax, rdi
0x18010bc29  lea     r11, [rsp+0D0h+var_20]
0x18010bc31  mov     rbx, [r11+30h]
0x18010bc35  mov     rsi, [r11+38h]
0x18010bc39  mov     rdi, [r11+40h]
0x18010bc3d  mov     rsp, r11
0x18010bc40  pop     r15
0x18010bc42  pop     r14
0x18010bc44  pop     r13
0x18010bc46  pop     r12
0x18010bc48  pop     rbp
0x18010bc49  retn
0x18010bc4a  xor     edx, edx
0x18010bc4c  mov     ecx, 1E3C3843h
0x18010bc51  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
