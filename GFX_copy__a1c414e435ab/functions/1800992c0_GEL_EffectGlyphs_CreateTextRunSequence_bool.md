# GEL::EffectGlyphs::CreateTextRunSequence(bool)

- ea: `0x1800992c0`
- end: `0x18009958a`
- name: `?CreateTextRunSequence@EffectGlyphs@GEL@@MEBAX_N@Z`
- size: `714`
- prototype: `void __fastcall(GEL::EffectGlyphs *__hidden this, bool)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1800085c8`
- `0x18001ffb4`
- `0x18003c0d0`
- `0x180055cec`
- `0x1800573f0`
- `0x180064e30`
- `0x1800992c0`

## import_xrefs

- `mso40uiWin32Client!__imp_?Create@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@2@_N@Z` at `0x1800993dd`
- `mso40uiWin32Client!__imp_?Create@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@2@_N@Z` at `0x1800993dd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180099567`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180099575`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180099567`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180099575`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18009953a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18009953a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GEL::EffectGlyphs::CreateTextRunSequence(GEL::EffectGlyphs *this, char a2)
{
  char *v4; // rsi
  unsigned int v5; // edi
  Mso::Memory *v6; // rbx
  struct GEL::ITextTech *v7; // rax
  __int64 v8; // rdx
  unsigned int v9; // ecx
  float v10; // xmm0_4
  float v11; // xmm0_4
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // r13d
  void *v15; // r12
  __int64 v16; // r15
  __int64 v17; // rsi
  __int64 v18; // r14
  int v19; // xmm6_4
  __int64 v20; // rdi
  __int64 v21; // rbx
  unsigned int v22; // eax
  void *v23; // rdx
  char v24; // [rsp+58h] [rbp-49h]
  __int64 v25; // [rsp+78h] [rbp-29h]
  __int64 v26; // [rsp+80h] [rbp-21h]
  void (__fastcall *v27)(__int64, _QWORD, __int64, _QWORD, __int64, int, __int64, __int64, __int64, void *, char, int, __int64); // [rsp+88h] [rbp-19h]
  void *v28; // [rsp+90h] [rbp-11h] BYREF
  unsigned int v29; // [rsp+98h] [rbp-9h]
  Mso::Memory *v30; // [rsp+A0h] [rbp-1h] BYREF
  int v31; // [rsp+A8h] [rbp+7h]
  unsigned int v32; // [rsp+ACh] [rbp+Bh]
  __int64 v34; // [rsp+118h] [rbp+77h] BYREF
  unsigned int v35; // [rsp+120h] [rbp+7Fh]

  v4 = (char *)this + 48;
  if ( !*((_QWORD *)this + 6) )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 72LL))(*((_QWORD *)this + 26));
    v35 = v5;
    v6 = (Mso::Memory *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 104LL))(*((_QWORD *)this + 26));
    v30 = 0;
    v31 = 0;
    v32 = 0x80000000;
    v7 = GEL::ITextTech::Get();
    if ( (*(unsigned __int8 (__fastcall **)(struct GEL::ITextTech *, GEL::EffectGlyphs *, Mso::Memory **))(*(_QWORD *)v7 + 72LL))(
           v7,
           this,
           &v30) )
    {
      goto LABEL_14;
    }
    while ( 1 )
    {
      Ofc::CArrayImpl::CArrayImpl((Ofc::CArrayImpl *)&v28, 8u, v5, v5, 1, Ofc::TDefaultConstructRange<double,1,1>::Do);
      v9 = 0;
      if ( !v5 )
        break;
      while ( 1 )
      {
        v8 = 2LL * v9;
        if ( v9 >= v29 )
          break;
        v10 = *((double *)v6 + 2 * v9);
        *((float *)v28 + 2 * v9) = v10;
        if ( v9 >= v29 )
        {
          CrashWithRecovery(0x1E892496u, 0);
          break;
        }
        v11 = *((double *)v6 + 2 * v9 + 1);
        *((float *)v28 + 2 * v9++ + 1) = v11;
        if ( v9 >= v5 )
          goto LABEL_7;
      }
      CrashWithRecovery(0x1E892496u, 0);
LABEL_14:
      if ( v31 == v5 )
        v6 = v30;
    }
LABEL_7:
    LOBYTE(v8) = a2;
    v12 = Mso::DWriteAssistant::Create(&v34, v8);
    Mso::TCntPtr<ARC::IPlatformBitmap>::operator=(v4, v12);
    v13 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    }
    v26 = Mso::TCntPtr<IWICImagingFactory>::operator->(v4);
    v27 = *(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64, int, __int64, __int64, __int64, void *, char, int, __int64))(*(_QWORD *)v26 + 48LL);
    v25 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 112LL))(*((_QWORD *)this + 26));
    v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 32LL))(*((_QWORD *)this + 26));
    LOBYTE(v34) = *((_BYTE *)this + 120) & 1;
    v15 = v28;
    v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 88LL))(*((_QWORD *)this + 26));
    v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 96LL))(*((_QWORD *)this + 26));
    v18 = *((_QWORD *)this + 5);
    v19 = *((_DWORD *)this + 22);
    v20 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 80LL))(*((_QWORD *)this + 26));
    v21 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 24LL))(*((_QWORD *)this + 26));
    v22 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 16LL))(*((_QWORD *)this + 26));
    v24 = v34;
    v27(v26, v22, v21, v35, v20, v19, v18, v17, v16, v15, v24, v14, v25);
    operator delete(v28);
    if ( v30 )
      Mso::Memory::Free(v30, v23);
  }
}

```

## disassembly

```asm
0x1800992c0  mov     rax, rsp
0x1800992c3  mov     [rax+10h], rbx
0x1800992c7  mov     [rax+8], rcx
0x1800992cb  push    rbp
0x1800992cc  push    rsi
0x1800992cd  push    rdi
0x1800992ce  push    r12
0x1800992d0  push    r13
0x1800992d2  push    r14
0x1800992d4  push    r15
0x1800992d6  lea     rbp, [rax-5Fh]
0x1800992da  sub     rsp, 0C0h
0x1800992e1  movaps  xmmword ptr [rax-48h], xmm6
0x1800992e5  mov     r15b, dl
0x1800992e8  mov     r14, rcx
0x1800992eb  lea     rsi, [rcx+30h]
0x1800992ef  xor     r12d, r12d
0x1800992f2  cmp     [rsi], r12
0x1800992f5  jnz     loc_180099540
0x1800992fb  mov     rcx, [rcx+0D0h]
0x180099302  mov     rax, [rcx]
0x180099305  mov     rax, [rax+48h]
0x180099309  call    cs:__guard_dispatch_icall_fptr
0x18009930f  mov     edi, eax
0x180099311  mov     [rbp+57h+arg_18], eax
0x180099314  mov     rcx, [r14+0D0h]
0x18009931b  mov     rdx, [rcx]
0x18009931e  mov     rax, [rdx+68h]
0x180099322  call    cs:__guard_dispatch_icall_fptr
0x180099328  mov     rbx, rax
0x18009932b  mov     [rbp+57h+var_58], r12
0x18009932f  mov     [rbp+57h+var_50], r12d
0x180099333  mov     [rbp+57h+var_4C], 80000000h
0x18009933a  call    ?Get@ITextTech@GEL@@SAAEAU12@XZ; GEL::ITextTech::Get(void)
0x18009933f  mov     r9, rax
0x180099342  mov     rcx, [rax]
0x180099345  mov     rax, [rcx+48h]
0x180099349  lea     r8, [rbp+57h+var_58]
0x18009934d  mov     rdx, r14
0x180099350  mov     rcx, r9
0x180099353  call    cs:__guard_dispatch_icall_fptr
0x180099359  test    al, al
0x18009935b  jnz     loc_18009957C
0x180099361  lea     rax, ?Do@?$TDefaultConstructRange@N$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<double,1,1>::Do(uchar *,ulong)
0x180099368  mov     [rsp+0F0h+var_C8], rax; void (*)(unsigned __int8 *, unsigned int)
0x18009936d  mov     [rsp+0F0h+var_D0], 1; bool
0x180099372  mov     r9d, edi; unsigned int
0x180099375  mov     r8d, edi; unsigned int
0x180099378  mov     edx, 8; unsigned int
0x18009937d  lea     rcx, [rbp+57h+var_68]; this
0x180099381  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x180099386  nop
0x180099387  mov     ecx, r12d
0x18009938a  test    edi, edi
0x18009938c  jz      short loc_1800993D6
0x18009938e  mov     r8d, ecx
0x180099391  mov     edx, ecx
0x180099393  add     rdx, rdx
0x180099396  movsd   xmm0, qword ptr [rbx+rdx*8]
0x18009939b  cvtpd2ps xmm0, xmm0
0x18009939f  cmp     ecx, [rbp+57h+var_60]
0x1800993a2  jnb     loc_18009956E
0x1800993a8  mov     rax, [rbp+57h+var_68]
0x1800993ac  movss   dword ptr [rax+r8*8], xmm0
0x1800993b2  movsd   xmm0, qword ptr [rbx+rdx*8+8]
0x1800993b8  cvtpd2ps xmm0, xmm0
0x1800993bc  cmp     ecx, [rbp+57h+var_60]
0x1800993bf  jnb     loc_180099560
0x1800993c5  mov     rax, [rbp+57h+var_68]
0x1800993c9  movss   dword ptr [rax+r8*8+4], xmm0
0x1800993d0  inc     ecx
0x1800993d2  cmp     ecx, edi
0x1800993d4  jb      short loc_18009938E
0x1800993d6  mov     dl, r15b
0x1800993d9  lea     rcx, [rbp+57h+arg_10]
0x1800993dd  call    cs:__imp_?Create@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@2@_N@Z; Mso::DWriteAssistant::Create(bool)
0x1800993e3  mov     rdx, rax
0x1800993e6  mov     rcx, rsi
0x1800993e9  call    ??4?$TCntPtr@UIPlatformBitmap@ARC@@@Mso@@QEAAAEAV01@$$QEAV01@@Z; Mso::TCntPtr<ARC::IPlatformBitmap>::operator=(Mso::TCntPtr<ARC::IPlatformBitmap> &&)
0x1800993ee  mov     rcx, [rbp+57h+arg_10]
0x1800993f2  test    rcx, rcx
0x1800993f5  jz      short loc_180099408
0x1800993f7  mov     [rbp+57h+arg_10], r12
0x1800993fb  mov     rax, [rcx]
0x1800993fe  mov     rax, [rax+8]
0x180099402  call    cs:__guard_dispatch_icall_fptr
0x180099408  mov     rcx, rsi
0x18009940b  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x180099410  mov     [rbp+57h+var_78], rax
0x180099414  mov     rcx, [rax]
0x180099417  mov     rax, [rcx+30h]
0x18009941b  mov     [rbp+57h+var_70], rax
0x18009941f  mov     rcx, [r14+0D0h]
0x180099426  mov     rdx, [rcx]
0x180099429  mov     rax, [rdx+70h]
0x18009942d  call    cs:__guard_dispatch_icall_fptr
0x180099433  mov     [rbp+57h+var_80], rax
0x180099437  mov     rcx, [r14+0D0h]
0x18009943e  mov     rdx, [rcx]
0x180099441  mov     rax, [rdx+20h]
0x180099445  call    cs:__guard_dispatch_icall_fptr
0x18009944b  mov     r13d, eax
0x18009944e  mov     al, [r14+78h]
0x180099452  and     al, 1
0x180099454  mov     byte ptr [rbp+57h+arg_10], al
0x180099457  mov     r12, [rbp+57h+var_68]
0x18009945b  mov     rcx, [r14+0D0h]
0x180099462  mov     rdx, [rcx]
0x180099465  mov     rax, [rdx+58h]
0x180099469  call    cs:__guard_dispatch_icall_fptr
0x18009946f  mov     r15, rax
0x180099472  mov     rcx, [r14+0D0h]
0x180099479  mov     rdx, [rcx]
0x18009947c  mov     rax, [rdx+60h]
0x180099480  call    cs:__guard_dispatch_icall_fptr
0x180099486  mov     rsi, rax
0x180099489  mov     r14, [r14+28h]
0x18009948d  mov     rbx, [rbp+57h+arg_0]
0x180099491  movss   xmm6, dword ptr [rbx+58h]
0x180099496  mov     rcx, [rbx+0D0h]
0x18009949d  mov     rdx, [rcx]
0x1800994a0  mov     rax, [rdx+50h]
0x1800994a4  call    cs:__guard_dispatch_icall_fptr
0x1800994aa  mov     rdi, rax
0x1800994ad  mov     rcx, [rbx+0D0h]
0x1800994b4  mov     rdx, [rcx]
0x1800994b7  mov     rax, [rdx+18h]
0x1800994bb  call    cs:__guard_dispatch_icall_fptr
0x1800994c1  mov     rbx, rax
0x1800994c4  mov     rcx, [rbp+57h+arg_0]
0x1800994c8  mov     rcx, [rcx+0D0h]
0x1800994cf  mov     rdx, [rcx]
0x1800994d2  mov     rax, [rdx+10h]
0x1800994d6  call    cs:__guard_dispatch_icall_fptr
0x1800994dc  mov     rcx, [rbp+57h+var_80]
0x1800994e0  mov     [rsp+0F0h+var_90], rcx
0x1800994e5  mov     dword ptr [rsp+0F0h+var_98], r13d
0x1800994ea  mov     cl, byte ptr [rbp+57h+arg_10]
0x1800994ed  mov     [rsp+0F0h+var_A0], cl
0x1800994f1  mov     qword ptr [rsp+0F0h+var_A8], r12
0x1800994f6  mov     [rsp+0F0h+var_B0], r15
0x1800994fb  mov     [rsp+0F0h+var_B8], rsi
0x180099500  mov     [rsp+0F0h+var_C0], r14
0x180099505  movss   dword ptr [rsp+0F0h+var_C8], xmm6
0x18009950b  mov     qword ptr [rsp+0F0h+var_D0], rdi
0x180099510  mov     r9d, [rbp+57h+arg_18]
0x180099514  mov     r8, rbx
0x180099517  mov     edx, eax
0x180099519  mov     rcx, [rbp+57h+var_78]
0x18009951d  mov     rax, [rbp+57h+var_70]
0x180099521  call    cs:__guard_dispatch_icall_fptr
0x180099527  nop
0x180099528  mov     rcx, [rbp+57h+var_68]; void *
0x18009952c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180099531  mov     rcx, [rbp+57h+var_58]
0x180099535  test    rcx, rcx
0x180099538  jz      short loc_180099540
0x18009953a  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180099540  lea     r11, [rsp+0F0h+var_30]
0x180099548  mov     rbx, [r11+48h]
0x18009954c  movaps  xmm6, xmmword ptr [r11-10h]
0x180099551  mov     rsp, r11
0x180099554  pop     r15
0x180099556  pop     r14
0x180099558  pop     r13
0x18009955a  pop     r12
0x18009955c  pop     rdi
0x18009955d  pop     rsi
0x18009955e  pop     rbp
0x18009955f  retn
0x180099560  xor     edx, edx
0x180099562  mov     ecx, 1E892496h
0x180099567  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18009956d  nop
0x18009956e  xor     edx, edx
0x180099570  mov     ecx, 1E892496h
0x180099575  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18009957b  nop
0x18009957c  cmp     [rbp+57h+var_50], edi
0x18009957f  cmovz   rbx, [rbp+57h+var_58]
0x180099584  jmp     loc_180099361
```
