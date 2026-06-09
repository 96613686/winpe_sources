# Mso::SVG::ShapeRenderer::GetEffectivePath(Mso::SVG::StyleResolveChain const &,Mso::Graphics::Path::FillMode)

- ea: `0x18010b9e8`
- end: `0x18010bc88`
- name: `?GetEffectivePath@ShapeRenderer@SVG@Mso@@AEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@W4FillMode@Path@Graphics@3@@Z`
- size: `672`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18010bcb0`
- `0x18010bee0`

## callees

- `0x180043594`
- `0x18004c058`
- `0x180101720`
- `0x1801017b8`
- `0x180103fe0`
- `0x18010406c`
- `0x18010b9e8`
- `0x18013e0c0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010bc81`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010bc81`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x18010bb8a`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x18010bb8a`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x18010bc33`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x18010bc33`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x18010bbe3`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x18010bbe3`

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
    JUMPOUT(0x18010BC87LL);
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
0x18010b9e8  mov     rax, rsp
0x18010b9eb  mov     [rax+8], rbx
0x18010b9ef  mov     [rax+10h], rsi
0x18010b9f3  mov     [rax+18h], rdi
0x18010b9f7  push    rbp
0x18010b9f8  push    r12
0x18010b9fa  push    r13
0x18010b9fc  push    r14
0x18010b9fe  push    r15
0x18010ba00  lea     rbp, [rax-5Fh]
0x18010ba04  sub     rsp, 0B0h
0x18010ba0b  mov     r12d, r9d
0x18010ba0e  mov     r14, r8
0x18010ba11  mov     rdi, rdx
0x18010ba14  mov     r15, rcx
0x18010ba17  xor     esi, esi
0x18010ba19  call    ?IsRenderingEnabled@RenderableRenderer@SVG@Mso@@QEBA_NXZ; Mso::SVG::RenderableRenderer::IsRenderingEnabled(void)
0x18010ba1e  test    al, al
0x18010ba20  jz      loc_18010BC53
0x18010ba26  mov     rcx, r14
0x18010ba29  call    ??$Get@$0BO@@StyleResolveChain@SVG@Mso@@QEBAAEB_NXZ; Mso::SVG::StyleResolveChain::Get<30>(void)
0x18010ba2e  cmp     [rax], sil
0x18010ba31  jz      loc_18010BC53
0x18010ba37  mov     rdx, [r14+8]
0x18010ba3b  mov     rcx, [rdx+10h]
0x18010ba3f  test    rcx, rcx
0x18010ba42  jz      short loc_18010BA4D
0x18010ba44  add     rcx, 228h
0x18010ba4b  jmp     short loc_18010BA61
0x18010ba4d  cmp     [rdx+8], rsi
0x18010ba51  lea     rcx, ?initial@?$StyleMetaData@$0BM@@SVG@Mso@@2V?$optional@_N@std@@B; std::optional<bool> const Mso::SVG::StyleMetaData<28>::initial
0x18010ba58  jz      short loc_18010BA61
0x18010ba5a  lea     rcx, ?inherit@?$StyleMetaData@$0BM@@SVG@Mso@@2V?$optional@_N@std@@B; std::optional<bool> const Mso::SVG::StyleMetaData<28>::inherit
0x18010ba61  mov     eax, 8
0x18010ba66  cmp     [rcx+1], sil
0x18010ba6a  jnz     short loc_18010BA8A
0x18010ba6c  mov     rcx, [r14]
0x18010ba6f  test    rcx, rcx
0x18010ba72  jz      short loc_18010BA7B
0x18010ba74  call    ??$Get@$0BM@@StyleResolveChain@SVG@Mso@@QEBAAEB_NXZ; Mso::SVG::StyleResolveChain::Get<28>(void)
0x18010ba79  jmp     short loc_18010BA87
0x18010ba7b  mov     rdx, [rax+rdx]
0x18010ba7f  mov     rcx, r14
0x18010ba82  call    ??$GetNormal@$0BM@@StyleResolveChain@SVG@Mso@@AEBAAEB_NAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<28>(Mso::SVG::Style const &)
0x18010ba87  mov     rcx, rax
0x18010ba8a  cmp     [rcx], sil
0x18010ba8d  jz      loc_18010BC53
0x18010ba93  mov     rbx, [r15+10h]
0x18010ba97  test    rbx, rbx
0x18010ba9a  jz      loc_18010BC7A
0x18010baa0  mov     edx, 0EB8h
0x18010baa5  mov     r8d, 0BD0h
0x18010baab  mov     rcx, [rbx]
0x18010baae  call    __castguard_slow_path_check_user_handled
0x18010bab3  lea     r13, [rbx+148h]
0x18010baba  mov     r8, r14
0x18010babd  lea     rdx, [rbp+57h+var_A0]
0x18010bac1  mov     rcx, r13
0x18010bac4  call    ?GetCached@PathCacher@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@@Z; Mso::SVG::PathCacher::GetCached(Mso::SVG::StyleResolveChain const &)
0x18010bac9  mov     rsi, [rbp+57h+var_A0]
0x18010bacd  test    rsi, rsi
0x18010bad0  jnz     short loc_18010BAD6
0x18010bad2  xor     ebx, ebx
0x18010bad4  jmp     short loc_18010BB0B
0x18010bad6  mov     rax, [rsi]
0x18010bad9  mov     rcx, rsi
0x18010badc  mov     rax, [rax+0C8h]
0x18010bae3  call    cs:__guard_dispatch_icall_fptr
0x18010bae9  cmp     eax, r12d
0x18010baec  jz      short loc_18010BB08
0x18010baee  xor     ebx, ebx
0x18010baf0  mov     [rbp+57h+var_90], rbx
0x18010baf4  mov     rax, [rsi]
0x18010baf7  mov     rcx, rsi
0x18010bafa  mov     rax, [rax+8]
0x18010bafe  call    cs:__guard_dispatch_icall_fptr
0x18010bb04  xor     esi, esi
0x18010bb06  jmp     short loc_18010BB0F
0x18010bb08  mov     rbx, rsi
0x18010bb0b  mov     [rbp+57h+var_90], rbx
0x18010bb0f  test    rsi, rsi
0x18010bb12  jnz     loc_18010BC4B
0x18010bb18  mov     [rbp+57h+var_98], esi
0x18010bb1b  mov     rax, [r15]
0x18010bb1e  lea     r9, [rbp+57h+var_98]
0x18010bb22  mov     r8, r14
0x18010bb25  lea     rdx, [rbp+57h+var_A0]
0x18010bb29  mov     rcx, r15
0x18010bb2c  mov     rax, [rax+30h]
0x18010bb30  call    cs:__guard_dispatch_icall_fptr
0x18010bb36  mov     rbx, [rax]
0x18010bb39  xor     r15d, r15d
0x18010bb3c  mov     [rax], r15
0x18010bb3f  mov     [rbp+57h+var_90], rbx
0x18010bb43  mov     rcx, [rbp+57h+var_A0]
0x18010bb47  test    rcx, rcx
0x18010bb4a  jz      short loc_18010BB5D
0x18010bb4c  mov     [rbp+57h+var_A0], r15
0x18010bb50  mov     rax, [rcx]
0x18010bb53  mov     rax, [rax+8]
0x18010bb57  call    cs:__guard_dispatch_icall_fptr
0x18010bb5d  test    rbx, rbx
0x18010bb60  jnz     short loc_18010BB6A
0x18010bb62  mov     [rdi], r15
0x18010bb65  jmp     loc_18010BC56
0x18010bb6a  mov     rax, [rbx]
0x18010bb6d  mov     rcx, rbx
0x18010bb70  mov     rax, [rax+0C8h]
0x18010bb77  call    cs:__guard_dispatch_icall_fptr
0x18010bb7d  cmp     r12d, eax
0x18010bb80  jz      loc_18010BC39
0x18010bb86  lea     rcx, [rbp+57h+var_60]
0x18010bb8a  call    cs:__imp_??0PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::PathBuilder(void)
0x18010bb90  lea     rax, [rbp+57h+var_60]
0x18010bb94  mov     [rbp+57h+var_78], rax
0x18010bb98  mov     [rbp+57h+var_70], r15d
0x18010bb9c  mov     [rbp+57h+var_68], r15
0x18010bba0  lea     rax, ??_7?$TValidatedPathSegmentSink@VPathBuilderPathSegmentSinkImpl@GEL@@@Path@Graphics@Mso@@6B@; const Mso::Graphics::Path::TValidatedPathSegmentSink<GEL::PathBuilderPathSegmentSinkImpl>::`vftable'
0x18010bba7  mov     [rbp+57h+var_80], rax
0x18010bbab  mov     rax, [rbx]
0x18010bbae  lea     rdx, [rbp+57h+var_80]
0x18010bbb2  mov     rcx, rbx
0x18010bbb5  mov     rax, [rax+0B0h]
0x18010bbbc  call    cs:__guard_dispatch_icall_fptr
0x18010bbc2  mov     rcx, [rbp+57h+var_68]
0x18010bbc6  test    rcx, rcx
0x18010bbc9  jz      short loc_18010BBD8
0x18010bbcb  mov     rax, [rcx]
0x18010bbce  mov     rax, [rax+8]
0x18010bbd2  call    cs:__guard_dispatch_icall_fptr
0x18010bbd8  mov     r8d, r12d
0x18010bbdb  lea     rdx, [rbp+57h+var_A0]
0x18010bbdf  lea     rcx, [rbp+57h+var_60]
0x18010bbe3  call    cs:__imp_?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z; GEL::PathBuilder::Finish(Mso::Graphics::Path::FillMode)
0x18010bbe9  mov     rsi, [rax]
0x18010bbec  test    rsi, rsi
0x18010bbef  jz      short loc_18010BC00
0x18010bbf1  mov     rax, [rsi]
0x18010bbf4  mov     rcx, rsi
0x18010bbf7  mov     rax, [rax]
0x18010bbfa  call    cs:__guard_dispatch_icall_fptr
0x18010bc00  mov     rcx, rbx
0x18010bc03  mov     rbx, rsi
0x18010bc06  test    rcx, rcx
0x18010bc09  jz      short loc_18010BC18
0x18010bc0b  mov     rax, [rcx]
0x18010bc0e  mov     rax, [rax+8]
0x18010bc12  call    cs:__guard_dispatch_icall_fptr
0x18010bc18  mov     rcx, [rbp+57h+var_A0]
0x18010bc1c  test    rcx, rcx
0x18010bc1f  jz      short loc_18010BC2F
0x18010bc21  mov     rax, [rcx]
0x18010bc24  mov     rax, [rax+8]
0x18010bc28  call    cs:__guard_dispatch_icall_fptr
0x18010bc2e  nop
0x18010bc2f  lea     rcx, [rbp+57h+var_60]
0x18010bc33  call    cs:__imp_??1PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::~PathBuilder(void)
0x18010bc39  mov     r9d, [rbp+57h+var_98]
0x18010bc3d  mov     r8, r14
0x18010bc40  mov     rdx, rbx
0x18010bc43  mov     rcx, r13
0x18010bc46  call    ?Cache@PathCacher@SVG@Mso@@QEAAXAEBUIPath@GEL@@AEBVStyleResolveChain@23@W4PathDependencyFlags@123@@Z; Mso::SVG::PathCacher::Cache(GEL::IPath const &,Mso::SVG::StyleResolveChain const &,Mso::SVG::PathCacher::PathDependencyFlags)
0x18010bc4b  mov     [rdi], rbx
0x18010bc4e  jmp     loc_18010BB65
0x18010bc53  mov     [rdi], rsi
0x18010bc56  mov     rax, rdi
0x18010bc59  lea     r11, [rsp+0D0h+var_20]
0x18010bc61  mov     rbx, [r11+30h]
0x18010bc65  mov     rsi, [r11+38h]
0x18010bc69  mov     rdi, [r11+40h]
0x18010bc6d  mov     rsp, r11
0x18010bc70  pop     r15
0x18010bc72  pop     r14
0x18010bc74  pop     r13
0x18010bc76  pop     r12
0x18010bc78  pop     rbp
0x18010bc79  retn
0x18010bc7a  xor     edx, edx
0x18010bc7c  mov     ecx, 1E3C3843h
0x18010bc81  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
