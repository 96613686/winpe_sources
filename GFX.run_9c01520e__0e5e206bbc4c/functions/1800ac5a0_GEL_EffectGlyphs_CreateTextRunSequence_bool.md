# GEL::EffectGlyphs::CreateTextRunSequence(bool)

- ea: `0x1800ac5a0`
- end: `0x1800ac86a`
- name: `?CreateTextRunSequence@EffectGlyphs@GEL@@MEBAX_N@Z`
- size: `714`
- prototype: `void __fastcall(GEL::EffectGlyphs *__hidden this, bool)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180009128`
- `0x180020198`
- `0x180037e60`
- `0x18005668c`
- `0x180057e70`
- `0x1800706ec`
- `0x1800ac5a0`

## import_xrefs

- `mso40uiWin32Client!__imp_?Create@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@2@_N@Z` at `0x1800ac6bd`
- `mso40uiWin32Client!__imp_?Create@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@2@_N@Z` at `0x1800ac6bd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800ac847`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800ac855`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800ac847`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800ac855`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800ac81a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800ac81a`

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
    Mso::TCntPtr<ARC::IPlatformBitmap const>::operator=(v4, v12);
    v13 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    }
    v26 = Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(v4);
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
0x1800ac5a0  mov     rax, rsp
0x1800ac5a3  mov     [rax+10h], rbx
0x1800ac5a7  mov     [rax+8], rcx
0x1800ac5ab  push    rbp
0x1800ac5ac  push    rsi
0x1800ac5ad  push    rdi
0x1800ac5ae  push    r12
0x1800ac5b0  push    r13
0x1800ac5b2  push    r14
0x1800ac5b4  push    r15
0x1800ac5b6  lea     rbp, [rax-5Fh]
0x1800ac5ba  sub     rsp, 0C0h
0x1800ac5c1  movaps  xmmword ptr [rax-48h], xmm6
0x1800ac5c5  mov     r15b, dl
0x1800ac5c8  mov     r14, rcx
0x1800ac5cb  lea     rsi, [rcx+30h]
0x1800ac5cf  xor     r12d, r12d
0x1800ac5d2  cmp     [rsi], r12
0x1800ac5d5  jnz     loc_1800AC820
0x1800ac5db  mov     rcx, [rcx+0D0h]
0x1800ac5e2  mov     rax, [rcx]
0x1800ac5e5  mov     rax, [rax+48h]
0x1800ac5e9  call    cs:__guard_dispatch_icall_fptr
0x1800ac5ef  mov     edi, eax
0x1800ac5f1  mov     [rbp+57h+arg_18], eax
0x1800ac5f4  mov     rcx, [r14+0D0h]
0x1800ac5fb  mov     rdx, [rcx]
0x1800ac5fe  mov     rax, [rdx+68h]
0x1800ac602  call    cs:__guard_dispatch_icall_fptr
0x1800ac608  mov     rbx, rax
0x1800ac60b  mov     [rbp+57h+var_58], r12
0x1800ac60f  mov     [rbp+57h+var_50], r12d
0x1800ac613  mov     [rbp+57h+var_4C], 80000000h
0x1800ac61a  call    ?Get@ITextTech@GEL@@SAAEAU12@XZ; GEL::ITextTech::Get(void)
0x1800ac61f  mov     r9, rax
0x1800ac622  mov     rcx, [rax]
0x1800ac625  mov     rax, [rcx+48h]
0x1800ac629  lea     r8, [rbp+57h+var_58]
0x1800ac62d  mov     rdx, r14
0x1800ac630  mov     rcx, r9
0x1800ac633  call    cs:__guard_dispatch_icall_fptr
0x1800ac639  test    al, al
0x1800ac63b  jnz     loc_1800AC85C
0x1800ac641  lea     rax, ?Do@?$TDefaultConstructRange@N$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<double,1,1>::Do(uchar *,ulong)
0x1800ac648  mov     [rsp+0F0h+var_C8], rax; void (*)(unsigned __int8 *, unsigned int)
0x1800ac64d  mov     [rsp+0F0h+var_D0], 1; bool
0x1800ac652  mov     r9d, edi; unsigned int
0x1800ac655  mov     r8d, edi; unsigned int
0x1800ac658  mov     edx, 8; unsigned int
0x1800ac65d  lea     rcx, [rbp+57h+var_68]; this
0x1800ac661  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x1800ac666  nop
0x1800ac667  mov     ecx, r12d
0x1800ac66a  test    edi, edi
0x1800ac66c  jz      short loc_1800AC6B6
0x1800ac66e  mov     r8d, ecx
0x1800ac671  mov     edx, ecx
0x1800ac673  add     rdx, rdx
0x1800ac676  movsd   xmm0, qword ptr [rbx+rdx*8]
0x1800ac67b  cvtpd2ps xmm0, xmm0
0x1800ac67f  cmp     ecx, [rbp+57h+var_60]
0x1800ac682  jnb     loc_1800AC84E
0x1800ac688  mov     rax, [rbp+57h+var_68]
0x1800ac68c  movss   dword ptr [rax+r8*8], xmm0
0x1800ac692  movsd   xmm0, qword ptr [rbx+rdx*8+8]
0x1800ac698  cvtpd2ps xmm0, xmm0
0x1800ac69c  cmp     ecx, [rbp+57h+var_60]
0x1800ac69f  jnb     loc_1800AC840
0x1800ac6a5  mov     rax, [rbp+57h+var_68]
0x1800ac6a9  movss   dword ptr [rax+r8*8+4], xmm0
0x1800ac6b0  inc     ecx
0x1800ac6b2  cmp     ecx, edi
0x1800ac6b4  jb      short loc_1800AC66E
0x1800ac6b6  mov     dl, r15b
0x1800ac6b9  lea     rcx, [rbp+57h+arg_10]
0x1800ac6bd  call    cs:__imp_?Create@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@2@_N@Z; Mso::DWriteAssistant::Create(bool)
0x1800ac6c3  mov     rdx, rax
0x1800ac6c6  mov     rcx, rsi
0x1800ac6c9  call    ??4?$TCntPtr@$$CBUIPlatformBitmap@ARC@@@Mso@@QEAAAEAV01@$$QEAV01@@Z; Mso::TCntPtr<ARC::IPlatformBitmap const>::operator=(Mso::TCntPtr<ARC::IPlatformBitmap const> &&)
0x1800ac6ce  mov     rcx, [rbp+57h+arg_10]
0x1800ac6d2  test    rcx, rcx
0x1800ac6d5  jz      short loc_1800AC6E8
0x1800ac6d7  mov     [rbp+57h+arg_10], r12
0x1800ac6db  mov     rax, [rcx]
0x1800ac6de  mov     rax, [rax+8]
0x1800ac6e2  call    cs:__guard_dispatch_icall_fptr
0x1800ac6e8  mov     rcx, rsi
0x1800ac6eb  call    ??C?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@Mso@@QEBAPEAUITextRunSequence@DWriteAssistant@1@XZ; Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(void)
0x1800ac6f0  mov     [rbp+57h+var_78], rax
0x1800ac6f4  mov     rcx, [rax]
0x1800ac6f7  mov     rax, [rcx+30h]
0x1800ac6fb  mov     [rbp+57h+var_70], rax
0x1800ac6ff  mov     rcx, [r14+0D0h]
0x1800ac706  mov     rdx, [rcx]
0x1800ac709  mov     rax, [rdx+70h]
0x1800ac70d  call    cs:__guard_dispatch_icall_fptr
0x1800ac713  mov     [rbp+57h+var_80], rax
0x1800ac717  mov     rcx, [r14+0D0h]
0x1800ac71e  mov     rdx, [rcx]
0x1800ac721  mov     rax, [rdx+20h]
0x1800ac725  call    cs:__guard_dispatch_icall_fptr
0x1800ac72b  mov     r13d, eax
0x1800ac72e  mov     al, [r14+78h]
0x1800ac732  and     al, 1
0x1800ac734  mov     byte ptr [rbp+57h+arg_10], al
0x1800ac737  mov     r12, [rbp+57h+var_68]
0x1800ac73b  mov     rcx, [r14+0D0h]
0x1800ac742  mov     rdx, [rcx]
0x1800ac745  mov     rax, [rdx+58h]
0x1800ac749  call    cs:__guard_dispatch_icall_fptr
0x1800ac74f  mov     r15, rax
0x1800ac752  mov     rcx, [r14+0D0h]
0x1800ac759  mov     rdx, [rcx]
0x1800ac75c  mov     rax, [rdx+60h]
0x1800ac760  call    cs:__guard_dispatch_icall_fptr
0x1800ac766  mov     rsi, rax
0x1800ac769  mov     r14, [r14+28h]
0x1800ac76d  mov     rbx, [rbp+57h+arg_0]
0x1800ac771  movss   xmm6, dword ptr [rbx+58h]
0x1800ac776  mov     rcx, [rbx+0D0h]
0x1800ac77d  mov     rdx, [rcx]
0x1800ac780  mov     rax, [rdx+50h]
0x1800ac784  call    cs:__guard_dispatch_icall_fptr
0x1800ac78a  mov     rdi, rax
0x1800ac78d  mov     rcx, [rbx+0D0h]
0x1800ac794  mov     rdx, [rcx]
0x1800ac797  mov     rax, [rdx+18h]
0x1800ac79b  call    cs:__guard_dispatch_icall_fptr
0x1800ac7a1  mov     rbx, rax
0x1800ac7a4  mov     rcx, [rbp+57h+arg_0]
0x1800ac7a8  mov     rcx, [rcx+0D0h]
0x1800ac7af  mov     rdx, [rcx]
0x1800ac7b2  mov     rax, [rdx+10h]
0x1800ac7b6  call    cs:__guard_dispatch_icall_fptr
0x1800ac7bc  mov     rcx, [rbp+57h+var_80]
0x1800ac7c0  mov     [rsp+0F0h+var_90], rcx
0x1800ac7c5  mov     dword ptr [rsp+0F0h+var_98], r13d
0x1800ac7ca  mov     cl, byte ptr [rbp+57h+arg_10]
0x1800ac7cd  mov     [rsp+0F0h+var_A0], cl
0x1800ac7d1  mov     qword ptr [rsp+0F0h+var_A8], r12
0x1800ac7d6  mov     [rsp+0F0h+var_B0], r15
0x1800ac7db  mov     [rsp+0F0h+var_B8], rsi
0x1800ac7e0  mov     [rsp+0F0h+var_C0], r14
0x1800ac7e5  movss   dword ptr [rsp+0F0h+var_C8], xmm6
0x1800ac7eb  mov     qword ptr [rsp+0F0h+var_D0], rdi
0x1800ac7f0  mov     r9d, [rbp+57h+arg_18]
0x1800ac7f4  mov     r8, rbx
0x1800ac7f7  mov     edx, eax
0x1800ac7f9  mov     rcx, [rbp+57h+var_78]
0x1800ac7fd  mov     rax, [rbp+57h+var_70]
0x1800ac801  call    cs:__guard_dispatch_icall_fptr
0x1800ac807  nop
0x1800ac808  mov     rcx, [rbp+57h+var_68]; void *
0x1800ac80c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ac811  mov     rcx, [rbp+57h+var_58]
0x1800ac815  test    rcx, rcx
0x1800ac818  jz      short loc_1800AC820
0x1800ac81a  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800ac820  lea     r11, [rsp+0F0h+var_30]
0x1800ac828  mov     rbx, [r11+48h]
0x1800ac82c  movaps  xmm6, xmmword ptr [r11-10h]
0x1800ac831  mov     rsp, r11
0x1800ac834  pop     r15
0x1800ac836  pop     r14
0x1800ac838  pop     r13
0x1800ac83a  pop     r12
0x1800ac83c  pop     rdi
0x1800ac83d  pop     rsi
0x1800ac83e  pop     rbp
0x1800ac83f  retn
0x1800ac840  xor     edx, edx
0x1800ac842  mov     ecx, 1E892496h
0x1800ac847  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800ac84d  nop
0x1800ac84e  xor     edx, edx
0x1800ac850  mov     ecx, 1E892496h
0x1800ac855  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800ac85b  nop
0x1800ac85c  cmp     [rbp+57h+var_50], edi
0x1800ac85f  cmovz   rbx, [rbp+57h+var_58]
0x1800ac864  jmp     loc_1800AC641
```
