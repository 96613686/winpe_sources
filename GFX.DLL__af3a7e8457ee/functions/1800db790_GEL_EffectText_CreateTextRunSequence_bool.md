# GEL::EffectText::CreateTextRunSequence(bool)

- ea: `0x1800db790`
- end: `0x1800dba65`
- name: `?CreateTextRunSequence@EffectText@GEL@@MEBAX_N@Z`
- size: `725`
- prototype: `void __fastcall(GEL::EffectText *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800db410`

## callees

- `0x1800085c8`
- `0x18001ffb4`
- `0x1800573f0`
- `0x180064e30`
- `0x18009958c`
- `0x180099bc0`
- `0x1800db790`

## import_xrefs

- `mso40uiWin32Client!__imp_?Create@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@2@_N@Z` at `0x1800db875`
- `mso40uiWin32Client!__imp_?Create@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@2@_N@Z` at `0x1800db875`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800db9f1`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800db9f1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800db9a6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800db9b4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800db9c2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800db9a6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800db9b4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800db9c2`

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
  __int64 v15; // rdi
  void (__fastcall *v16)(__int64, _QWORD, _QWORD, _QWORD, void *, _DWORD, _QWORD, _QWORD, __int64, void *, char, int, _QWORD); // rbx
  int v17; // eax
  __int64 v18; // rdi
  void (__fastcall *v19)(__int64, _QWORD, __int64); // r15
  char v20; // [rsp+58h] [rbp-9h]
  void *v21; // [rsp+78h] [rbp+17h] BYREF
  unsigned int v22; // [rsp+80h] [rbp+1Fh]
  void *v23; // [rsp+88h] [rbp+27h] BYREF
  unsigned int v24; // [rsp+90h] [rbp+2Fh]
  __int64 v25; // [rsp+C8h] [rbp+67h] BYREF

  v4 = (char *)this + 48;
  if ( !*((_QWORD *)this + 6)
    || a2
    && (v5 = Mso::TCntPtr<IWICImagingFactory>::operator->((char *)this + 48),
        (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5))
    && (v6 = Mso::TCntPtr<IWICImagingFactory>::operator->(v4),
        v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 16LL))(v6, 0),
        !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 112LL))(v7)) )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 24LL))(*((_QWORD *)this + 26));
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 16LL))(*((_QWORD *)this + 26));
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 72LL))(*((_QWORD *)this + 26));
    LOBYTE(v11) = a2;
    v12 = Mso::DWriteAssistant::Create(&v25, v11);
    Mso::TCntPtr<ARC::IPlatformBitmap>::operator=(v4, v12);
    v13 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    }
    if ( (*((_BYTE *)this + 120) & 4) != 0 )
    {
      Ofc::TArray<DWRITE_GLYPH_OFFSET>::TArray<DWRITE_GLYPH_OFFSET>(&v21, v9);
      Ofc::TArray<unsigned short>::TArray<unsigned short>(&v23, v9);
      v14 = 0;
      if ( !v9 )
      {
LABEL_13:
        v15 = Mso::TCntPtr<IWICImagingFactory>::operator->(v4);
        v16 = *(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, void *, _DWORD, _QWORD, _QWORD, __int64, void *, char, int, _QWORD))(*(_QWORD *)v15 + 48LL);
        v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 32LL))(*((_QWORD *)this + 26));
        v20 = 0;
        v16(v15, 0, 0, v9, v23, *((_DWORD *)this + 22), *((_QWORD *)this + 5), 0, v10, v21, v20, v17, 0);
        operator delete(v23);
        operator delete(v21);
        return;
      }
      while ( v14 < v24 )
      {
        *((_WORD *)v23 + v14) = *(_WORD *)(v8 + 2LL * v14);
        if ( v14 >= v22 )
          goto LABEL_15;
        *((_DWORD *)v21 + 2 * v14) = 0;
        if ( v14 >= v22 )
        {
          CrashWithRecovery(0x1E892496u, 0);
LABEL_15:
          CrashWithRecovery(0x1E892496u, 0);
          break;
        }
        *((_DWORD *)v21 + 2 * v14++ + 1) = 0;
        if ( v14 >= v9 )
          goto LABEL_13;
      }
      CrashWithRecovery(0x1E892496u, 0);
    }
    v18 = Mso::TCntPtr<IWICImagingFactory>::operator->(v4);
    v19 = *(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v18 + 40LL);
    if ( byte_18051FEE0 < 0 )
      Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_18051FEE0);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 32LL))(*((_QWORD *)this + 26));
    v19(v18, v9, v8);
  }
}

```

## disassembly

```asm
0x1800db790  mov     rax, rsp
0x1800db793  mov     [rax+10h], rbx
0x1800db797  mov     [rax+18h], rsi
0x1800db79b  mov     [rax+20h], rdi
0x1800db79f  push    rbp
0x1800db7a0  push    r12
0x1800db7a2  push    r13
0x1800db7a4  push    r14
0x1800db7a6  push    r15
0x1800db7a8  lea     rbp, [rax-5Fh]
0x1800db7ac  sub     rsp, 90h
0x1800db7b3  mov     dil, dl
0x1800db7b6  mov     rsi, rcx
0x1800db7b9  lea     rbx, [rcx+30h]
0x1800db7bd  xor     r15d, r15d
0x1800db7c0  cmp     [rbx], r15
0x1800db7c3  jz      short loc_1800DB829
0x1800db7c5  test    dl, dl
0x1800db7c7  jz      loc_1800DBA44
0x1800db7cd  mov     rcx, rbx
0x1800db7d0  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800db7d5  mov     rdx, rax
0x1800db7d8  mov     rcx, [rax]
0x1800db7db  mov     rax, [rcx+18h]
0x1800db7df  mov     rcx, rdx
0x1800db7e2  call    cs:__guard_dispatch_icall_fptr
0x1800db7e8  test    eax, eax
0x1800db7ea  jz      loc_1800DBA44
0x1800db7f0  mov     rcx, rbx
0x1800db7f3  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800db7f8  mov     r8, rax
0x1800db7fb  mov     rcx, [rax]
0x1800db7fe  mov     rax, [rcx+10h]
0x1800db802  xor     edx, edx
0x1800db804  mov     rcx, r8
0x1800db807  call    cs:__guard_dispatch_icall_fptr
0x1800db80d  mov     rdx, rax
0x1800db810  mov     rcx, [rax]
0x1800db813  mov     rax, [rcx+70h]
0x1800db817  mov     rcx, rdx
0x1800db81a  call    cs:__guard_dispatch_icall_fptr
0x1800db820  test    rax, rax
0x1800db823  jnz     loc_1800DBA44
0x1800db829  mov     rcx, [rsi+0D0h]
0x1800db830  mov     rax, [rcx]
0x1800db833  mov     rax, [rax+18h]
0x1800db837  call    cs:__guard_dispatch_icall_fptr
0x1800db83d  mov     r12, rax
0x1800db840  mov     rcx, [rsi+0D0h]
0x1800db847  mov     rdx, [rcx]
0x1800db84a  mov     rax, [rdx+10h]
0x1800db84e  call    cs:__guard_dispatch_icall_fptr
0x1800db854  mov     r14d, eax
0x1800db857  mov     rcx, [rsi+0D0h]
0x1800db85e  mov     rdx, [rcx]
0x1800db861  mov     rax, [rdx+48h]
0x1800db865  call    cs:__guard_dispatch_icall_fptr
0x1800db86b  mov     r13, rax
0x1800db86e  mov     dl, dil
0x1800db871  lea     rcx, [rbp+57h+arg_0]
0x1800db875  call    cs:__imp_?Create@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@2@_N@Z; Mso::DWriteAssistant::Create(bool)
0x1800db87b  mov     rdx, rax
0x1800db87e  mov     rcx, rbx
0x1800db881  call    ??4?$TCntPtr@UIPlatformBitmap@ARC@@@Mso@@QEAAAEAV01@$$QEAV01@@Z; Mso::TCntPtr<ARC::IPlatformBitmap>::operator=(Mso::TCntPtr<ARC::IPlatformBitmap> &&)
0x1800db886  mov     rcx, [rbp+57h+arg_0]
0x1800db88a  test    rcx, rcx
0x1800db88d  jz      short loc_1800DB8A0
0x1800db88f  mov     [rbp+57h+arg_0], r15
0x1800db893  mov     rdx, [rcx]
0x1800db896  mov     rax, [rdx+8]
0x1800db89a  call    cs:__guard_dispatch_icall_fptr
0x1800db8a0  test    byte ptr [rsi+78h], 4
0x1800db8a4  jz      loc_1800DB9C9
0x1800db8aa  mov     edx, r14d
0x1800db8ad  lea     rcx, [rbp+57h+var_40]
0x1800db8b1  call    ??0?$TArray@UDWRITE_GLYPH_OFFSET@@@Ofc@@QEAA@K@Z; Ofc::TArray<DWRITE_GLYPH_OFFSET>::TArray<DWRITE_GLYPH_OFFSET>(ulong)
0x1800db8b6  nop
0x1800db8b7  mov     edx, r14d
0x1800db8ba  lea     rcx, [rbp+57h+var_30]
0x1800db8be  call    ??0?$TArray@G@Ofc@@QEAA@K@Z; Ofc::TArray<ushort>::TArray<ushort>(ulong)
0x1800db8c3  nop
0x1800db8c4  mov     ecx, r15d
0x1800db8c7  test    r14d, r14d
0x1800db8ca  jz      short loc_1800DB90F
0x1800db8cc  mov     edx, ecx
0x1800db8ce  movzx   r8d, word ptr [r12+rdx*2]
0x1800db8d3  cmp     ecx, [rbp+57h+var_28]
0x1800db8d6  jnb     loc_1800DB9BB
0x1800db8dc  mov     rax, [rbp+57h+var_30]
0x1800db8e0  mov     [rax+rdx*2], r8w
0x1800db8e5  cmp     ecx, [rbp+57h+var_38]
0x1800db8e8  jnb     loc_1800DB9AD
0x1800db8ee  mov     rax, [rbp+57h+var_40]
0x1800db8f2  mov     [rax+rdx*8], r15d
0x1800db8f6  cmp     ecx, [rbp+57h+var_38]
0x1800db8f9  jnb     loc_1800DB99F
0x1800db8ff  mov     rax, [rbp+57h+var_40]
0x1800db903  mov     [rax+rdx*8+4], r15d
0x1800db908  inc     ecx
0x1800db90a  cmp     ecx, r14d
0x1800db90d  jb      short loc_1800DB8CC
0x1800db90f  mov     rcx, rbx
0x1800db912  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800db917  mov     rdi, rax
0x1800db91a  mov     rcx, [rax]
0x1800db91d  mov     rbx, [rcx+30h]
0x1800db921  mov     rcx, [rsi+0D0h]
0x1800db928  mov     rdx, [rcx]
0x1800db92b  mov     rax, [rdx+20h]
0x1800db92f  call    cs:__guard_dispatch_icall_fptr
0x1800db935  mov     rdx, [rsi+28h]
0x1800db939  movss   xmm0, dword ptr [rsi+58h]
0x1800db93e  mov     [rsp+0B0h+var_50], r15
0x1800db943  mov     dword ptr [rsp+0B0h+var_58], eax
0x1800db947  mov     [rsp+0B0h+var_60], r15b
0x1800db94c  mov     rcx, [rbp+57h+var_40]
0x1800db950  mov     qword ptr [rsp+0B0h+var_68], rcx
0x1800db955  mov     [rsp+0B0h+var_70], r13
0x1800db95a  mov     [rsp+0B0h+var_78], r15
0x1800db95f  mov     [rsp+0B0h+var_80], rdx
0x1800db964  movss   dword ptr [rsp+0B0h+var_88], xmm0
0x1800db96a  mov     rcx, [rbp+57h+var_30]
0x1800db96e  mov     qword ptr [rsp+0B0h+var_90], rcx
0x1800db973  mov     r9d, r14d
0x1800db976  xor     r8d, r8d
0x1800db979  xor     edx, edx
0x1800db97b  mov     rcx, rdi
0x1800db97e  mov     rax, rbx
0x1800db981  call    cs:__guard_dispatch_icall_fptr
0x1800db987  nop
0x1800db988  mov     rcx, [rbp+57h+var_30]; void *
0x1800db98c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800db991  mov     rcx, [rbp+57h+var_40]; void *
0x1800db995  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800db99a  jmp     loc_1800DBA44
0x1800db99f  xor     edx, edx
0x1800db9a1  mov     ecx, 1E892496h
0x1800db9a6  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800db9ac  nop
0x1800db9ad  xor     edx, edx
0x1800db9af  mov     ecx, 1E892496h
0x1800db9b4  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800db9ba  nop
0x1800db9bb  xor     edx, edx
0x1800db9bd  mov     ecx, 1E892496h
0x1800db9c2  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800db9c8  nop
0x1800db9c9  mov     rcx, rbx
0x1800db9cc  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800db9d1  mov     rdi, rax
0x1800db9d4  mov     rcx, [rax]
0x1800db9d7  mov     r15, [rcx+28h]
0x1800db9db  mov     cl, cs:byte_18051FEE0
0x1800db9e1  test    cl, cl
0x1800db9e3  js      short loc_1800DB9EA
0x1800db9e5  setnz   bl
0x1800db9e8  jmp     short loc_1800DB9F9
0x1800db9ea  lea     rcx, byte_18051FEE0
0x1800db9f1  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1800db9f7  mov     bl, al
0x1800db9f9  mov     rcx, [rsi+0D0h]
0x1800dba00  mov     rdx, [rcx]
0x1800dba03  mov     rax, [rdx+20h]
0x1800dba07  call    cs:__guard_dispatch_icall_fptr
0x1800dba0d  mov     [rsp+0B0h+var_68], bl
0x1800dba11  mov     dword ptr [rsp+0B0h+var_70], r14d
0x1800dba16  mov     [rsp+0B0h+var_78], r13
0x1800dba1b  mov     dword ptr [rsp+0B0h+var_80], eax
0x1800dba1f  mov     byte ptr [rsp+0B0h+var_88], 0
0x1800dba24  mov     rcx, [rsi+28h]
0x1800dba28  mov     qword ptr [rsp+0B0h+var_90], rcx
0x1800dba2d  movss   xmm3, dword ptr [rsi+58h]
0x1800dba32  mov     r8, r12
0x1800dba35  mov     edx, r14d
0x1800dba38  mov     rcx, rdi
0x1800dba3b  mov     rax, r15
0x1800dba3e  call    cs:__guard_dispatch_icall_fptr
0x1800dba44  lea     r11, [rsp+0B0h+var_20]
0x1800dba4c  mov     rbx, [r11+38h]
0x1800dba50  mov     rsi, [r11+40h]
0x1800dba54  mov     rdi, [r11+48h]
0x1800dba58  mov     rsp, r11
0x1800dba5b  pop     r15
0x1800dba5d  pop     r14
0x1800dba5f  pop     r13
0x1800dba61  pop     r12
0x1800dba63  pop     rbp
0x1800dba64  retn
```
