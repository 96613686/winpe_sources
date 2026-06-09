# Art::GroupFillHolder::GroupFillHolder(Art::FillStyle const &,Ofc::TBitset<ulong,1>,Ofc::TBitset<unsigned __int64,1>,MSOBWMODE,Math::TAffine3x3<double> const &)

- ea: `0x180133770`
- end: `0x180133b30`
- name: `??0GroupFillHolder@Art@@QEAA@AEBVFillStyle@1@V?$TBitset@K$00@Ofc@@V?$TBitset@_K$00@4@W4MSOBWMODE@@AEBU?$TAffine3x3@N@Math@@@Z`
- size: `960`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18013326c`

## callees

- `0x180043e40`
- `0x1800659a0`
- `0x180071720`
- `0x180133770`
- `0x180133b30`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x180133a96`
- `KERNEL32!EncodePointer` at `0x180133b17`
- `KERNEL32!EncodePointer` at `0x180133a96`
- `KERNEL32!EncodePointer` at `0x180133b17`
- `gfx!?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ` at `0x1801337cf`
- `gfx!?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ` at `0x1801337dc`
- `gfx!?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ` at `0x1801337e9`
- `gfx!?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ` at `0x1801337f6`
- `gfx!?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ` at `0x180133804`
- `gfx!?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ` at `0x1801337cf`
- `gfx!?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ` at `0x1801337dc`
- `gfx!?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ` at `0x1801337e9`
- `gfx!?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ` at `0x1801337f6`
- `gfx!?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ` at `0x180133804`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x180133932`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x180133a7b`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x180133932`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x180133a7b`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18013391b`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180133a63`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18013391b`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180133a63`

## pseudocode

```c
Art::FillModeProps *__fastcall Art::GroupFillHolder::GroupFillHolder(
        Art::FillModeProps *a1,
        const struct Art::FillModeProps *a2,
        _DWORD *a3,
        _QWORD *a4,
        int a5,
        _OWORD *a6)
{
  Art::FillModeProps *v8; // rsi
  char v9; // r12
  void (__fastcall **v10)(_QWORD); // rbx
  void (__fastcall **v11)(_QWORD); // rdi
  void (__fastcall **v12)(_QWORD); // r14
  void (__fastcall **v13)(_QWORD); // r15
  unsigned __int64 v14; // rdx
  unsigned int v15; // r8d
  _QWORD *v16; // rax
  unsigned __int64 v17; // rdx
  unsigned int v18; // r8d
  int *v19; // r13
  _OWORD *v21; // rax
  unsigned int v22; // r8d
  int *v23; // rax
  int *v24; // rcx
  PVOID v25; // rax
  _QWORD *v26; // [rsp+20h] [rbp-60h]
  _OWORD *v27; // [rsp+28h] [rbp-58h]
  Art::FillModeProps *v28; // [rsp+30h] [rbp-50h]
  int *v29; // [rsp+30h] [rbp-50h]
  void (__fastcall **v30)(_QWORD); // [rsp+58h] [rbp-28h]
  void (__fastcall **v31)(_QWORD); // [rsp+60h] [rbp-20h]
  void (__fastcall **v32)(_QWORD); // [rsp+68h] [rbp-18h]
  void (__fastcall **v33)(_QWORD); // [rsp+70h] [rbp-10h]

  v8 = a1;
  v9 = 0;
  Art::FillModeProps::FillModeProps(a1, a2);
  *((_DWORD *)v8 + 4) = 0;
  *((_DWORD *)v8 + 4) = *a3;
  *((_QWORD *)v8 + 3) = 0;
  *((_QWORD *)v8 + 3) = *a4;
  *((_DWORD *)v8 + 8) = a5;
  v10 = (void (__fastcall **)(_QWORD))((char *)v8 + 40);
  GEL::IBrushIndirect::Create((char *)v8 + 40);
  v11 = (void (__fastcall **)(_QWORD))((char *)v8 + 48);
  GEL::IBrushIndirect::Create((char *)v8 + 48);
  v12 = (void (__fastcall **)(_QWORD))((char *)v8 + 56);
  GEL::IBrushIndirect::Create((char *)v8 + 56);
  v13 = (void (__fastcall **)(_QWORD))((char *)v8 + 64);
  GEL::IBrushIndirect::Create((char *)v8 + 64);
  GEL::IBrushIndirect::Create((char *)v8 + 72);
  v16 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x40, v14, v15);
  v26 = v16;
  v19 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  if ( v16 )
    goto LABEL_22;
  v26 = 0;
  v8 = v28;
  v13 = v30;
  v12 = v31;
  v11 = v32;
  v10 = v33;
  while ( v16 )
  {
    v19 = (int *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v18);
    if ( v19 )
      goto LABEL_37;
    CrashWithRecoveryOnOOM(0x1E000188u);
LABEL_22:
    v8 = (Art::FillModeProps *)*((_QWORD *)v8 + 9);
    if ( v8 )
      (**(void (__fastcall ***)(Art::FillModeProps *))v8)(v8);
    v13 = (void (__fastcall **)(_QWORD))*v13;
    if ( v13 )
      (*(void (__fastcall **)(_QWORD))*v13)(v13);
    v12 = (void (__fastcall **)(_QWORD))*v12;
    if ( v12 )
      (*(void (__fastcall **)(_QWORD))*v12)(v12);
    v11 = (void (__fastcall **)(_QWORD))*v11;
    if ( v11 )
      (*(void (__fastcall **)(_QWORD))*v11)(v11);
    v10 = (void (__fastcall **)(_QWORD))*v10;
    if ( v10 )
      (*(void (__fastcall **)(_QWORD))*v10)(v10);
    v9 = 31;
    *v26 = &Art::GelBrushCollection::`vftable';
    v26[1] = 0;
    v26[2] = 0;
    v26[3] = 0;
    v26[4] = 0;
    v26[5] = 0;
    *((_BYTE *)v26 + 48) = 0;
    v21 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x30, v17, v18);
    v27 = v21;
    if ( v21 )
    {
      *v21 = *a6;
      v21[1] = a6[1];
      v21[2] = a6[2];
    }
    else
    {
      v27 = 0;
    }
    if ( v21 )
    {
      v23 = (int *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v22);
      v29 = v23;
      if ( !v23 )
      {
        CrashWithRecoveryOnOOM(0x1E000188u);
LABEL_37:
        *v19 = 1;
        v19[1] = 1;
        *((_QWORD *)v19 + 1) = EncodePointer(Ofc::TDeleteFromProxy<Art::GelBrushCollection>);
        *((_QWORD *)v19 + 2) = v26;
        break;
      }
      *v23 = 1;
      v23[1] = 1;
      v25 = EncodePointer(Ofc::TDeleteFromProxy<Art::FormatObjectLineGradientVariationsGallerySite>);
      v24 = v29;
      *((_QWORD *)v29 + 1) = v25;
      *((_QWORD *)v29 + 2) = v27;
    }
    else
    {
      v24 = v19;
    }
    v26[7] = v24;
    Ofc::TCntPtr<Gfx::IFigureStyle>::operator=(v26 + 1, v10);
    Ofc::TCntPtr<Gfx::IFigureStyle>::operator=(v26 + 2, v11);
    Ofc::TCntPtr<Gfx::IFigureStyle>::operator=(v26 + 3, v12);
    Ofc::TCntPtr<Gfx::IFigureStyle>::operator=(v26 + 4, v13);
    Ofc::TCntPtr<Gfx::IFigureStyle>::operator=(v26 + 5, v8);
    v16 = v26;
  }
  *((_QWORD *)a1 + 10) = v19;
  if ( (v9 & 0x10) != 0 )
  {
    v9 &= ~0x10u;
    if ( v10 )
      (*((void (__fastcall **)(_QWORD))*v10 + 1))(v10);
  }
  if ( (v9 & 8) != 0 )
  {
    v9 &= ~8u;
    if ( v11 )
      (*((void (__fastcall **)(_QWORD))*v11 + 1))(v11);
  }
  if ( (v9 & 4) != 0 )
  {
    v9 &= ~4u;
    if ( v12 )
      (*((void (__fastcall **)(_QWORD))*v12 + 1))(v12);
  }
  if ( (v9 & 2) != 0 )
  {
    v9 &= ~2u;
    if ( v13 )
      (*((void (__fastcall **)(_QWORD))*v13 + 1))(v13);
  }
  if ( (v9 & 1) != 0 && v8 )
    (*(void (__fastcall **)(Art::FillModeProps *))(*(_QWORD *)v8 + 8LL))(v8);
  return a1;
}

```

## disassembly

```asm
0x180133770  mov     rax, rsp
0x180133773  mov     [rax+10h], rbx
0x180133777  mov     [rax+18h], rsi
0x18013377b  mov     [rax+20h], rdi
0x18013377f  mov     [rax+8], rcx
0x180133783  push    rbp
0x180133784  push    r12
0x180133786  push    r13
0x180133788  push    r14
0x18013378a  push    r15
0x18013378c  mov     rbp, rsp
0x18013378f  sub     rsp, 80h
0x180133796  mov     rdi, r9
0x180133799  mov     rbx, r8
0x18013379c  mov     rsi, rcx
0x18013379f  xor     r12d, r12d
0x1801337a2  mov     dword ptr [rbp+var_58], r12d
0x1801337a6  call    ??0FillModeProps@Art@@QEAA@AEBV01@@Z; Art::FillModeProps::FillModeProps(Art::FillModeProps const &)
0x1801337ab  xor     eax, eax
0x1801337ad  mov     [rsi+10h], eax
0x1801337b0  mov     eax, [rbx]
0x1801337b2  mov     [rsi+10h], eax
0x1801337b5  xor     eax, eax
0x1801337b7  mov     [rsi+18h], rax
0x1801337bb  mov     rax, [rdi]
0x1801337be  mov     [rsi+18h], rax
0x1801337c2  mov     eax, [rbp+arg_20]
0x1801337c5  mov     [rsi+20h], eax
0x1801337c8  lea     rbx, [rsi+28h]
0x1801337cc  mov     rcx, rbx
0x1801337cf  call    cs:__imp_?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ; GEL::IBrushIndirect::Create(void)
0x1801337d5  lea     rdi, [rsi+30h]
0x1801337d9  mov     rcx, rdi
0x1801337dc  call    cs:__imp_?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ; GEL::IBrushIndirect::Create(void)
0x1801337e2  lea     r14, [rsi+38h]
0x1801337e6  mov     rcx, r14
0x1801337e9  call    cs:__imp_?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ; GEL::IBrushIndirect::Create(void)
0x1801337ef  lea     r15, [rsi+40h]
0x1801337f3  mov     rcx, r15
0x1801337f6  call    cs:__imp_?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ; GEL::IBrushIndirect::Create(void)
0x1801337fc  nop     dword ptr [rax+00h]
0x180133800  lea     rcx, [rsi+48h]
0x180133804  call    cs:__imp_?Create@IBrushIndirect@GEL@@SA?AV?$TCntPtr@UIBrushIndirect@GEL@@@Ofc@@XZ; GEL::IBrushIndirect::Create(void)
0x18013380a  lea     ecx, [r12+40h]; this
0x18013380f  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180133814  mov     [rbp+var_60], rax
0x180133818  mov     [rbp+var_8], rax
0x18013381c  lea     r13, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x180133823  test    rax, rax
0x180133826  jnz     loc_180133939
0x18013382c  mov     [rbp+var_60], rax
0x180133830  mov     rsi, [rbp+var_50]
0x180133834  mov     r15, [rbp+var_28]
0x180133838  mov     r14, [rbp+var_20]
0x18013383c  mov     rdi, [rbp+var_18]
0x180133840  mov     rbx, [rbp+var_10]
0x180133844  test    rax, rax
0x180133847  jnz     loc_180133916
0x18013384d  mov     rax, [rbp+arg_0]
0x180133851  mov     [rax+50h], r13
0x180133855  test    r12b, 10h
0x180133859  jz      short loc_180133875
0x18013385b  and     r12d, 0FFFFFFEFh
0x18013385f  test    rbx, rbx
0x180133862  jz      short loc_180133875
0x180133864  mov     rax, [rbx]
0x180133867  mov     rcx, rbx
0x18013386a  mov     rax, [rax+8]
0x18013386e  call    cs:__guard_dispatch_icall_fptr
0x180133874  nop
0x180133875  test    r12b, 8
0x180133879  jz      short loc_180133895
0x18013387b  and     r12d, 0FFFFFFF7h
0x18013387f  test    rdi, rdi
0x180133882  jz      short loc_180133895
0x180133884  mov     rax, [rdi]
0x180133887  mov     rcx, rdi
0x18013388a  mov     rax, [rax+8]
0x18013388e  call    cs:__guard_dispatch_icall_fptr
0x180133894  nop
0x180133895  test    r12b, 4
0x180133899  jz      short loc_1801338B5
0x18013389b  and     r12d, 0FFFFFFFBh
0x18013389f  test    r14, r14
0x1801338a2  jz      short loc_1801338B5
0x1801338a4  mov     rax, [r14]
0x1801338a7  mov     rcx, r14
0x1801338aa  mov     rax, [rax+8]
0x1801338ae  call    cs:__guard_dispatch_icall_fptr
0x1801338b4  nop
0x1801338b5  test    r12b, 2
0x1801338b9  jz      short loc_1801338D5
0x1801338bb  and     r12d, 0FFFFFFFDh
0x1801338bf  test    r15, r15
0x1801338c2  jz      short loc_1801338D5
0x1801338c4  mov     rax, [r15]
0x1801338c7  mov     rcx, r15
0x1801338ca  mov     rax, [rax+8]
0x1801338ce  call    cs:__guard_dispatch_icall_fptr
0x1801338d4  nop
0x1801338d5  test    r12b, 1
0x1801338d9  jz      short loc_1801338F1
0x1801338db  test    rsi, rsi
0x1801338de  jz      short loc_1801338F1
0x1801338e0  mov     rax, [rsi]
0x1801338e3  mov     rcx, rsi
0x1801338e6  mov     rax, [rax+8]
0x1801338ea  call    cs:__guard_dispatch_icall_fptr
0x1801338f0  nop
0x1801338f1  mov     rax, [rbp+arg_0]
0x1801338f5  lea     r11, [rsp+80h+var_s0]
0x1801338fd  mov     rbx, [r11+38h]
0x180133901  mov     rsi, [r11+40h]
0x180133905  mov     rdi, [r11+48h]
0x180133909  mov     rsp, r11
0x18013390c  pop     r15
0x18013390e  pop     r14
0x180133910  pop     r13
0x180133912  pop     r12
0x180133914  pop     rbp
0x180133915  retn
0x180133916  xor     edx, edx
0x180133918  lea     ecx, [rdx+18h]
0x18013391b  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x180133921  mov     r13, rax
0x180133924  test    rax, rax
0x180133927  jnz     loc_180133A82
0x18013392d  mov     ecx, 1E000188h
0x180133932  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x180133938  nop
0x180133939  mov     rsi, [rsi+48h]
0x18013393d  mov     [rbp+var_50], rsi
0x180133941  test    rsi, rsi
0x180133944  jz      short loc_180133956
0x180133946  mov     rax, [rsi]
0x180133949  mov     rcx, rsi
0x18013394c  mov     rax, [rax]
0x18013394f  call    cs:__guard_dispatch_icall_fptr
0x180133955  nop
0x180133956  mov     r15, [r15]
0x180133959  mov     [rbp+var_28], r15
0x18013395d  test    r15, r15
0x180133960  jz      short loc_180133972
0x180133962  mov     rax, [r15]
0x180133965  mov     rcx, r15
0x180133968  mov     rax, [rax]
0x18013396b  call    cs:__guard_dispatch_icall_fptr
0x180133971  nop
0x180133972  mov     r14, [r14]
0x180133975  mov     [rbp+var_20], r14
0x180133979  test    r14, r14
0x18013397c  jz      short loc_180133990
0x18013397e  mov     rax, [r14]
0x180133981  mov     rcx, r14
0x180133984  mov     rax, [rax]
0x180133987  call    cs:__guard_dispatch_icall_fptr
0x18013398d  nop
0x18013398e  xchg    ax, ax
0x180133990  mov     rdi, [rdi]
0x180133993  mov     [rbp+var_18], rdi
0x180133997  test    rdi, rdi
0x18013399a  jz      short loc_1801339AC
0x18013399c  mov     rax, [rdi]
0x18013399f  mov     rcx, rdi
0x1801339a2  mov     rax, [rax]
0x1801339a5  call    cs:__guard_dispatch_icall_fptr
0x1801339ab  nop
0x1801339ac  mov     rbx, [rbx]
0x1801339af  mov     [rbp+var_10], rbx
0x1801339b3  test    rbx, rbx
0x1801339b6  jz      short loc_1801339C8
0x1801339b8  mov     rax, [rbx]
0x1801339bb  mov     rcx, rbx
0x1801339be  mov     rax, [rax]
0x1801339c1  call    cs:__guard_dispatch_icall_fptr
0x1801339c7  nop
0x1801339c8  mov     r12d, 1Fh
0x1801339ce  mov     dword ptr [rbp+var_58], r12d
0x1801339d2  lea     rcx, ??_7GelBrushCollection@Art@@6B@; const Art::GelBrushCollection::`vftable'
0x1801339d9  mov     rax, [rbp+var_60]
0x1801339dd  mov     [rax], rcx
0x1801339e0  mov     qword ptr [rax+8], 0
0x1801339e8  lea     rcx, [rax+10h]
0x1801339ec  mov     [rbp+var_48], rcx
0x1801339f0  mov     qword ptr [rcx], 0
0x1801339f7  lea     rcx, [rax+18h]
0x1801339fb  mov     [rbp+var_40], rcx
0x1801339ff  mov     qword ptr [rcx], 0
0x180133a06  lea     rcx, [rax+20h]
0x180133a0a  mov     [rbp+var_38], rcx
0x180133a0e  mov     qword ptr [rcx], 0
0x180133a15  lea     rcx, [rax+28h]
0x180133a19  mov     [rbp+var_30], rcx
0x180133a1d  mov     qword ptr [rcx], 0
0x180133a24  mov     byte ptr [rax+30h], 0
0x180133a28  lea     ecx, [r12+11h]; this
0x180133a2d  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180133a32  mov     [rbp+var_58], rax
0x180133a36  test    rax, rax
0x180133a39  jz      loc_180133AFD
0x180133a3f  mov     rcx, [rbp+arg_28]
0x180133a43  movups  xmm0, xmmword ptr [rcx]
0x180133a46  movups  xmmword ptr [rax], xmm0
0x180133a49  movups  xmm1, xmmword ptr [rcx+10h]
0x180133a4d  movups  xmmword ptr [rax+10h], xmm1
0x180133a51  movups  xmm0, xmmword ptr [rcx+20h]
0x180133a55  movups  xmmword ptr [rax+20h], xmm0
0x180133a59  test    rax, rax
0x180133a5c  jz      short loc_180133AAD
0x180133a5e  xor     edx, edx
0x180133a60  lea     ecx, [rdx+18h]
0x180133a63  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x180133a69  mov     [rbp+var_50], rax
0x180133a6d  test    rax, rax
0x180133a70  jnz     loc_180133B06
0x180133a76  mov     ecx, 1E000188h
0x180133a7b  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x180133a81  nop
0x180133a82  mov     eax, 1
0x180133a87  mov     [r13+0], eax
0x180133a8b  mov     [r13+4], eax
0x180133a8f  lea     rcx, ??$TDeleteFromProxy@VGelBrushCollection@Art@@@Ofc@@YAXPEAX@Z; Ptr
0x180133a96  call    cs:__imp_EncodePointer
0x180133a9c  mov     [r13+8], rax
0x180133aa0  mov     rax, [rbp+var_60]
0x180133aa4  mov     [r13+10h], rax
0x180133aa8  jmp     loc_18013384D
0x180133aad  mov     rcx, r13
0x180133ab0  mov     rax, [rbp+var_60]
0x180133ab4  mov     [rax+38h], rcx
0x180133ab8  mov     rdx, rbx
0x180133abb  lea     rcx, [rax+8]
0x180133abf  call    ??4?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@QEAAAEAV01@PEAUIFigureStyle@Gfx@@@Z; Ofc::TCntPtr<Gfx::IFigureStyle>::operator=(Gfx::IFigureStyle *)
0x180133ac4  mov     rdx, rdi
0x180133ac7  mov     rcx, [rbp+var_48]
0x180133acb  call    ??4?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@QEAAAEAV01@PEAUIFigureStyle@Gfx@@@Z; Ofc::TCntPtr<Gfx::IFigureStyle>::operator=(Gfx::IFigureStyle *)
0x180133ad0  mov     rdx, r14
0x180133ad3  mov     rcx, [rbp+var_40]
0x180133ad7  call    ??4?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@QEAAAEAV01@PEAUIFigureStyle@Gfx@@@Z; Ofc::TCntPtr<Gfx::IFigureStyle>::operator=(Gfx::IFigureStyle *)
0x180133adc  mov     rdx, r15
0x180133adf  mov     rcx, [rbp+var_38]
0x180133ae3  call    ??4?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@QEAAAEAV01@PEAUIFigureStyle@Gfx@@@Z; Ofc::TCntPtr<Gfx::IFigureStyle>::operator=(Gfx::IFigureStyle *)
0x180133ae8  mov     rdx, rsi
0x180133aeb  mov     rcx, [rbp+var_30]
0x180133aef  call    ??4?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@QEAAAEAV01@PEAUIFigureStyle@Gfx@@@Z; Ofc::TCntPtr<Gfx::IFigureStyle>::operator=(Gfx::IFigureStyle *)
0x180133af4  mov     rax, [rbp+var_60]
0x180133af8  jmp     loc_180133844
0x180133afd  mov     [rbp+var_58], rax
0x180133b01  jmp     loc_180133A59
0x180133b06  mov     ecx, 1
0x180133b0b  mov     [rax], ecx
0x180133b0d  mov     [rax+4], ecx
0x180133b10  lea     rcx, ??$TDeleteFromProxy@VFormatObjectLineGradientVariationsGallerySite@Art@@@Ofc@@YAXPEAX@Z; Ptr
0x180133b17  call    cs:__imp_EncodePointer
0x180133b1d  mov     rcx, [rbp+var_50]
0x180133b21  mov     [rcx+8], rax
0x180133b25  mov     rax, [rbp+var_58]
0x180133b29  mov     [rcx+10h], rax
0x180133b2d  jmp     short loc_180133AB0
```
