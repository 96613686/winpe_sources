# GEL::EffectText::CreateTextRunSequence(bool)

- ea: `0x180071670`
- end: `0x180071951`
- name: `?CreateTextRunSequence@EffectText@GEL@@MEBAX_N@Z`
- size: `737`
- prototype: `void __fastcall(GEL::EffectText *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180070474`

## callees

- `0x180009128`
- `0x180020198`
- `0x180057e70`
- `0x1800706ec`
- `0x180071670`
- `0x1800ac870`
- `0x1800aecb0`

## import_xrefs

- `mso40uiWin32Client!__imp_?Create@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@2@_N@Z` at `0x180071755`
- `mso40uiWin32Client!__imp_?Create@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@2@_N@Z` at `0x180071755`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800718dd`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800718dd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180071892`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800718a0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800718ae`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180071892`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800718a0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800718ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GEL::EffectText::CreateTextRunSequence(GEL::EffectText *this, char a2)
{
  char *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // r12
  unsigned int v9; // r14d
  __int64 v10; // r13
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // ecx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rdi
  void (__fastcall *v18)(__int64, _QWORD, _QWORD, _QWORD, void *, _DWORD, _QWORD, _QWORD, __int64, void *, char, int, _QWORD); // rbx
  int v19; // eax
  __int64 v20; // rdi
  void (__fastcall *v21)(__int64, _QWORD, __int64); // r15
  char v22; // [rsp+58h] [rbp-9h]
  void *v23; // [rsp+78h] [rbp+17h] BYREF
  unsigned int v24; // [rsp+80h] [rbp+1Fh]
  void *v25; // [rsp+88h] [rbp+27h] BYREF
  unsigned int v26; // [rsp+90h] [rbp+2Fh]
  __int64 v27; // [rsp+C8h] [rbp+67h] BYREF

  v4 = (char *)this + 48;
  if ( !*((_QWORD *)this + 6)
    || a2
    && (v5 = Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->((char *)this + 48),
        (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5))
    && (v6 = Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(v4),
        v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 16LL))(v6, 0),
        !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 112LL))(v7)) )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 24LL))(*((_QWORD *)this + 26));
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 16LL))(*((_QWORD *)this + 26));
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 72LL))(*((_QWORD *)this + 26));
    LOBYTE(v11) = a2;
    v12 = Mso::DWriteAssistant::Create(&v27, v11);
    Mso::TCntPtr<ARC::IPlatformBitmap const>::operator=(v4, v12);
    v13 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    }
    if ( (*((_BYTE *)this + 120) & 4) != 0 )
    {
      Ofc::TArray<DWRITE_GLYPH_OFFSET>::TArray<DWRITE_GLYPH_OFFSET>(&v23, v9);
      Ofc::TArray<unsigned short>::TArray<unsigned short>(&v25, v9);
      v14 = 0;
      if ( !v9 )
      {
LABEL_14:
        v17 = Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(v4);
        v18 = *(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, void *, _DWORD, _QWORD, _QWORD, __int64, void *, char, int, _QWORD))(*(_QWORD *)v17 + 48LL);
        v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 32LL))(*((_QWORD *)this + 26));
        v22 = 0;
        v18(v17, 0, 0, v9, v25, *((_DWORD *)this + 22), *((_QWORD *)this + 5), 0, v10, v23, v22, v19, 0);
        operator delete(v25);
        operator delete(v23);
        return;
      }
      v15 = 0;
      v16 = 0;
      while ( v14 < v26 )
      {
        *(_WORD *)((char *)v25 + v16) = *(_WORD *)(v16 + v8);
        if ( v14 >= v24 )
          goto LABEL_16;
        *(_DWORD *)((char *)v23 + v15) = 0;
        if ( v14 >= v24 )
        {
          CrashWithRecovery(0x1E892496u, 0);
LABEL_16:
          CrashWithRecovery(0x1E892496u, 0);
          break;
        }
        *(_DWORD *)((char *)v23 + v15 + 4) = 0;
        ++v14;
        v16 += 2;
        v15 += 8;
        if ( v14 >= v9 )
          goto LABEL_14;
      }
      CrashWithRecovery(0x1E892496u, 0);
    }
    v20 = Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(v4);
    v21 = *(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v20 + 40LL);
    if ( byte_180523F48 < 0 )
      Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180523F48);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 32LL))(*((_QWORD *)this + 26));
    v21(v20, v9, v8);
  }
}

```

## disassembly

```asm
0x180071670  mov     rax, rsp
0x180071673  mov     [rax+10h], rbx
0x180071677  mov     [rax+18h], rsi
0x18007167b  mov     [rax+20h], rdi
0x18007167f  push    rbp
0x180071680  push    r12
0x180071682  push    r13
0x180071684  push    r14
0x180071686  push    r15
0x180071688  lea     rbp, [rax-5Fh]
0x18007168c  sub     rsp, 90h
0x180071693  mov     dil, dl
0x180071696  mov     rsi, rcx
0x180071699  lea     rbx, [rcx+30h]
0x18007169d  xor     r15d, r15d
0x1800716a0  cmp     [rbx], r15
0x1800716a3  jz      short loc_180071709
0x1800716a5  test    dl, dl
0x1800716a7  jz      loc_180071930
0x1800716ad  mov     rcx, rbx
0x1800716b0  call    ??C?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@Mso@@QEBAPEAUITextRunSequence@DWriteAssistant@1@XZ; Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(void)
0x1800716b5  mov     rdx, rax
0x1800716b8  mov     rcx, [rax]
0x1800716bb  mov     rax, [rcx+18h]
0x1800716bf  mov     rcx, rdx
0x1800716c2  call    cs:__guard_dispatch_icall_fptr
0x1800716c8  test    eax, eax
0x1800716ca  jz      loc_180071930
0x1800716d0  mov     rcx, rbx
0x1800716d3  call    ??C?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@Mso@@QEBAPEAUITextRunSequence@DWriteAssistant@1@XZ; Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(void)
0x1800716d8  mov     r8, rax
0x1800716db  mov     rcx, [rax]
0x1800716de  mov     rax, [rcx+10h]
0x1800716e2  xor     edx, edx
0x1800716e4  mov     rcx, r8
0x1800716e7  call    cs:__guard_dispatch_icall_fptr
0x1800716ed  mov     rdx, rax
0x1800716f0  mov     rcx, [rax]
0x1800716f3  mov     rax, [rcx+70h]
0x1800716f7  mov     rcx, rdx
0x1800716fa  call    cs:__guard_dispatch_icall_fptr
0x180071700  test    rax, rax
0x180071703  jnz     loc_180071930
0x180071709  mov     rcx, [rsi+0D0h]
0x180071710  mov     rax, [rcx]
0x180071713  mov     rax, [rax+18h]
0x180071717  call    cs:__guard_dispatch_icall_fptr
0x18007171d  mov     r12, rax
0x180071720  mov     rcx, [rsi+0D0h]
0x180071727  mov     rdx, [rcx]
0x18007172a  mov     rax, [rdx+10h]
0x18007172e  call    cs:__guard_dispatch_icall_fptr
0x180071734  mov     r14d, eax
0x180071737  mov     rcx, [rsi+0D0h]
0x18007173e  mov     rdx, [rcx]
0x180071741  mov     rax, [rdx+48h]
0x180071745  call    cs:__guard_dispatch_icall_fptr
0x18007174b  mov     r13, rax
0x18007174e  mov     dl, dil
0x180071751  lea     rcx, [rbp+57h+arg_0]
0x180071755  call    cs:__imp_?Create@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@2@_N@Z; Mso::DWriteAssistant::Create(bool)
0x18007175b  mov     rdx, rax
0x18007175e  mov     rcx, rbx
0x180071761  call    ??4?$TCntPtr@$$CBUIPlatformBitmap@ARC@@@Mso@@QEAAAEAV01@$$QEAV01@@Z; Mso::TCntPtr<ARC::IPlatformBitmap const>::operator=(Mso::TCntPtr<ARC::IPlatformBitmap const> &&)
0x180071766  mov     rcx, [rbp+57h+arg_0]
0x18007176a  test    rcx, rcx
0x18007176d  jz      short loc_180071780
0x18007176f  mov     [rbp+57h+arg_0], r15
0x180071773  mov     rdx, [rcx]
0x180071776  mov     rax, [rdx+8]
0x18007177a  call    cs:__guard_dispatch_icall_fptr
0x180071780  test    byte ptr [rsi+78h], 4
0x180071784  jz      loc_1800718B5
0x18007178a  mov     edx, r14d
0x18007178d  lea     rcx, [rbp+57h+var_40]
0x180071791  call    ??0?$TArray@UDWRITE_GLYPH_OFFSET@@@Ofc@@QEAA@K@Z; Ofc::TArray<DWRITE_GLYPH_OFFSET>::TArray<DWRITE_GLYPH_OFFSET>(ulong)
0x180071796  nop
0x180071797  mov     edx, r14d
0x18007179a  lea     rcx, [rbp+57h+var_30]
0x18007179e  call    ??0?$TArray@G@Ofc@@QEAA@K@Z; Ofc::TArray<ushort>::TArray<ushort>(ulong)
0x1800717a3  nop
0x1800717a4  mov     ecx, r15d
0x1800717a7  test    r14d, r14d
0x1800717aa  jz      short loc_1800717FB
0x1800717ac  mov     r8, r15
0x1800717af  mov     rdx, r15
0x1800717b2  movzx   r9d, word ptr [rdx+r12]
0x1800717b7  cmp     ecx, [rbp+57h+var_28]
0x1800717ba  jnb     loc_1800718A7
0x1800717c0  mov     rax, [rbp+57h+var_30]
0x1800717c4  mov     [rdx+rax], r9w
0x1800717c9  cmp     ecx, [rbp+57h+var_38]
0x1800717cc  jnb     loc_180071899
0x1800717d2  mov     rax, [rbp+57h+var_40]
0x1800717d6  mov     [r8+rax], r15d
0x1800717da  cmp     ecx, [rbp+57h+var_38]
0x1800717dd  jnb     loc_18007188B
0x1800717e3  mov     rax, [rbp+57h+var_40]
0x1800717e7  mov     [r8+rax+4], r15d
0x1800717ec  inc     ecx
0x1800717ee  add     rdx, 2
0x1800717f2  add     r8, 8
0x1800717f6  cmp     ecx, r14d
0x1800717f9  jb      short loc_1800717B2
0x1800717fb  mov     rcx, rbx
0x1800717fe  call    ??C?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@Mso@@QEBAPEAUITextRunSequence@DWriteAssistant@1@XZ; Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(void)
0x180071803  mov     rdi, rax
0x180071806  mov     rcx, [rax]
0x180071809  mov     rbx, [rcx+30h]
0x18007180d  mov     rcx, [rsi+0D0h]
0x180071814  mov     rdx, [rcx]
0x180071817  mov     rax, [rdx+20h]
0x18007181b  call    cs:__guard_dispatch_icall_fptr
0x180071821  mov     rdx, [rsi+28h]
0x180071825  movss   xmm0, dword ptr [rsi+58h]
0x18007182a  mov     [rsp+0B0h+var_50], r15
0x18007182f  mov     dword ptr [rsp+0B0h+var_58], eax
0x180071833  mov     [rsp+0B0h+var_60], r15b
0x180071838  mov     rcx, [rbp+57h+var_40]
0x18007183c  mov     qword ptr [rsp+0B0h+var_68], rcx
0x180071841  mov     [rsp+0B0h+var_70], r13
0x180071846  mov     [rsp+0B0h+var_78], r15
0x18007184b  mov     [rsp+0B0h+var_80], rdx
0x180071850  movss   dword ptr [rsp+0B0h+var_88], xmm0
0x180071856  mov     rcx, [rbp+57h+var_30]
0x18007185a  mov     qword ptr [rsp+0B0h+var_90], rcx
0x18007185f  mov     r9d, r14d
0x180071862  xor     r8d, r8d
0x180071865  xor     edx, edx
0x180071867  mov     rcx, rdi
0x18007186a  mov     rax, rbx
0x18007186d  call    cs:__guard_dispatch_icall_fptr
0x180071873  nop
0x180071874  mov     rcx, [rbp+57h+var_30]; void *
0x180071878  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007187d  mov     rcx, [rbp+57h+var_40]; void *
0x180071881  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180071886  jmp     loc_180071930
0x18007188b  xor     edx, edx
0x18007188d  mov     ecx, 1E892496h
0x180071892  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180071898  nop
0x180071899  xor     edx, edx
0x18007189b  mov     ecx, 1E892496h
0x1800718a0  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800718a6  nop
0x1800718a7  xor     edx, edx
0x1800718a9  mov     ecx, 1E892496h
0x1800718ae  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800718b4  nop
0x1800718b5  mov     rcx, rbx
0x1800718b8  call    ??C?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@Mso@@QEBAPEAUITextRunSequence@DWriteAssistant@1@XZ; Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(void)
0x1800718bd  mov     rdi, rax
0x1800718c0  mov     rcx, [rax]
0x1800718c3  mov     r15, [rcx+28h]
0x1800718c7  mov     cl, cs:byte_180523F48
0x1800718cd  test    cl, cl
0x1800718cf  js      short loc_1800718D6
0x1800718d1  setnz   bl
0x1800718d4  jmp     short loc_1800718E5
0x1800718d6  lea     rcx, byte_180523F48
0x1800718dd  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1800718e3  mov     bl, al
0x1800718e5  mov     rcx, [rsi+0D0h]
0x1800718ec  mov     rdx, [rcx]
0x1800718ef  mov     rax, [rdx+20h]
0x1800718f3  call    cs:__guard_dispatch_icall_fptr
0x1800718f9  mov     [rsp+0B0h+var_68], bl
0x1800718fd  mov     dword ptr [rsp+0B0h+var_70], r14d
0x180071902  mov     [rsp+0B0h+var_78], r13
0x180071907  mov     dword ptr [rsp+0B0h+var_80], eax
0x18007190b  mov     byte ptr [rsp+0B0h+var_88], 0
0x180071910  mov     rcx, [rsi+28h]
0x180071914  mov     qword ptr [rsp+0B0h+var_90], rcx
0x180071919  movss   xmm3, dword ptr [rsi+58h]
0x18007191e  mov     r8, r12
0x180071921  mov     edx, r14d
0x180071924  mov     rcx, rdi
0x180071927  mov     rax, r15
0x18007192a  call    cs:__guard_dispatch_icall_fptr
0x180071930  lea     r11, [rsp+0B0h+var_20]
0x180071938  mov     rbx, [r11+38h]
0x18007193c  mov     rsi, [r11+40h]
0x180071940  mov     rdi, [r11+48h]
0x180071944  mov     rsp, r11
0x180071947  pop     r15
0x180071949  pop     r14
0x18007194b  pop     r13
0x18007194d  pop     r12
0x18007194f  pop     rbp
0x180071950  retn
```
