# GEL::GlyphSinkForKashidas::AddCharacter(wchar_t,float,GEL::Vector const &)

- ea: `0x180142280`
- end: `0x18014254c`
- name: `?AddCharacter@GlyphSinkForKashidas@GEL@@UEAAX_WMAEBUVector@2@@Z`
- size: `716`
- prototype: `void __fastcall(GEL::GlyphSinkForKashidas *__hidden this, wchar_t, float, const struct GEL::Vector *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800578b0`
- `0x180057e70`
- `0x1800706ec`
- `0x180142280`
- `0x18018d800`

## import_xrefs

- `KERNEL32!LCIDToLocaleName` at `0x18014245d`
- `KERNEL32!LCIDToLocaleName` at `0x18014245d`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x180142383`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x18014243c`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x180142383`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x18014243c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801423f5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801423f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall GEL::GlyphSinkForKashidas::AddCharacter(
        GEL::GlyphSinkForKashidas *this,
        unsigned __int16 a2,
        float a3,
        const struct GEL::Vector *a4)
{
  unsigned __int16 v6; // si
  char *v7; // r15
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, unsigned __int16 *, __int64, __int64, _DWORD, _DWORD, __int64 *, WCHAR *, _QWORD, _QWORD **, __int64 *, int, int, __int16 *, __int16 *, unsigned __int16 *, _WORD *, int *); // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned __int16 v20; // [rsp+A8h] [rbp-80h] BYREF
  unsigned __int16 v21; // [rsp+B0h] [rbp-78h] BYREF
  __int64 v22; // [rsp+B8h] [rbp-70h] BYREF
  _WORD v23[2]; // [rsp+C0h] [rbp-68h] BYREF
  __int16 v24; // [rsp+C4h] [rbp-64h] BYREF
  __int16 v25; // [rsp+C8h] [rbp-60h] BYREF
  __int64 v26; // [rsp+D0h] [rbp-58h] BYREF
  int v27; // [rsp+D8h] [rbp-50h] BYREF
  int v28; // [rsp+DCh] [rbp-4Ch] BYREF
  __int64 v29; // [rsp+E0h] [rbp-48h] BYREF
  _QWORD *v30; // [rsp+E8h] [rbp-40h] BYREF
  _QWORD v31[3]; // [rsp+F0h] [rbp-38h] BYREF
  WCHAR Name[88]; // [rsp+108h] [rbp-20h] BYREF

  v21 = a2;
  v6 = 0;
  v20 = 0;
  v27 = a2;
  v7 = (char *)this + 88;
  v8 = Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->((char *)this + 88);
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
  v10 = (*(__int64 (__fastcall **)(__int64, int *, __int64, unsigned __int16 *))(*(_QWORD *)v9 + 88LL))(
          v9,
          &v27,
          1,
          &v20);
  if ( v10 < 0 || (*((_BYTE *)this + 96) & 4) == 0 )
    goto LABEL_3;
  if ( *(int *)(Mso::DWriteAssistant::ResourceManager::GetInstance() + 112) <= 0 )
  {
    v16 = *(_QWORD *)(Mso::DWriteAssistant::ResourceManager::GetInstance() + 72);
    v29 = 33;
    LCIDToLocaleName(*((_DWORD *)this + 29), Name, 85, 0);
    v26 = 0x174726576LL;
    LODWORD(v22) = 1;
    v31[0] = &v26;
    v31[1] = 1;
    v30 = v31;
    v28 = 0;
    v25 = 0;
    v24 = 0;
    v23[0] = 0;
    v17 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64, __int64, _DWORD, _DWORD, __int64 *, WCHAR *, _QWORD, _QWORD **, __int64 *, int, int, __int16 *, __int16 *, unsigned __int16 *, _WORD *, int *))(*(_QWORD *)v16 + 56LL);
    v18 = Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(v7);
    v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 24LL))(v18);
    v10 = v17(v16, &v21, 1, v19, 0, 0, &v29, Name, 0, &v30, &v22, 1, 1, &v25, &v24, &v20, v23, &v28);
    goto LABEL_3;
  }
  v12 = Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(v7);
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 24LL))(v12);
  v22 = 0;
  v26 = v13;
  v10 = Mso::ComUtil::HrQueryFrom<IDWriteFontFace1,IDWriteFontFace *>(&v22, &v26);
  if ( v10 >= 0 )
  {
    v14 = v22;
    if ( !v22 )
      goto LABEL_15;
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v22 + 232LL))(v22) )
    {
      v15 = v22;
      if ( !v22 )
        CrashWithRecovery(0x1E3C3840u, 0);
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)v15 + 224LL))(
              v15,
              1,
              &v20,
              &v20);
    }
  }
  v14 = v22;
LABEL_15:
  if ( v14 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
LABEL_3:
  if ( (unsigned __int16)(v21 + 10240) <= 0x7FFu || v10 < 0 )
    v20 = 0;
  else
    v6 = v20;
  (*(void (__fastcall **)(GEL::GlyphSinkForKashidas *, _QWORD, __int64, const struct GEL::Vector *))(*(_QWORD *)this + 16LL))(
    this,
    v6,
    v11,
    a4);
}

```

## disassembly

```asm
0x180142280  mov     rax, rsp
0x180142283  push    rbp
0x180142284  push    rbx
0x180142285  push    rsi
0x180142286  push    rdi
0x180142287  push    r12
0x180142289  push    r13
0x18014228b  push    r14
0x18014228d  push    r15
0x18014228f  lea     rbp, [rax-0F8h]
0x180142296  sub     rsp, 1D8h
0x18014229d  movaps  xmmword ptr [rax-58h], xmm6
0x1801422a1  mov     rax, cs:__security_cookie
0x1801422a8  xor     rax, rsp
0x1801422ab  mov     [rbp+0F0h+var_60], rax
0x1801422b2  mov     r12, r9
0x1801422b5  movaps  xmm6, xmm2
0x1801422b8  mov     r14, rcx
0x1801422bb  mov     [rbp+0F0h+var_168], dx
0x1801422bf  xor     esi, esi
0x1801422c1  mov     [rbp+0F0h+var_170], si
0x1801422c5  movzx   eax, dx
0x1801422c8  mov     [rbp+0F0h+var_140], eax
0x1801422cb  lea     r15, [rcx+58h]
0x1801422cf  mov     rcx, r15
0x1801422d2  call    ??C?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@Mso@@QEBAPEAUITextRunSequence@DWriteAssistant@1@XZ; Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(void)
0x1801422d7  mov     rdx, rax
0x1801422da  mov     rcx, [rax]
0x1801422dd  mov     rax, [rcx+18h]
0x1801422e1  mov     rcx, rdx
0x1801422e4  call    cs:__guard_dispatch_icall_fptr
0x1801422ea  mov     r10, rax
0x1801422ed  mov     rcx, [rax]
0x1801422f0  mov     rax, [rcx+58h]
0x1801422f4  lea     r9, [rbp+0F0h+var_170]
0x1801422f8  lea     r13d, [rsi+1]
0x1801422fc  mov     r8d, r13d
0x1801422ff  lea     rdx, [rbp+0F0h+var_140]
0x180142303  mov     rcx, r10
0x180142306  call    cs:__guard_dispatch_icall_fptr
0x18014230c  mov     ebx, eax
0x18014230e  test    eax, eax
0x180142310  js      short loc_180142319
0x180142312  test    byte ptr [r14+60h], 4
0x180142317  jnz     short loc_180142383
0x180142319  mov     ecx, 2800h
0x18014231e  movzx   eax, [rbp+0F0h+var_168]
0x180142322  add     ax, cx
0x180142325  mov     ecx, 7FFh
0x18014232a  cmp     ax, cx
0x18014232d  jbe     loc_180142542
0x180142333  test    ebx, ebx
0x180142335  js      loc_180142542
0x18014233b  movzx   esi, [rbp+0F0h+var_170]
0x18014233f  mov     rax, [r14]
0x180142342  mov     r9, r12
0x180142345  movaps  xmm2, xmm6
0x180142348  movzx   edx, si
0x18014234b  mov     rcx, r14
0x18014234e  mov     rax, [rax+10h]
0x180142352  call    cs:__guard_dispatch_icall_fptr
0x180142358  mov     rcx, [rbp+0F0h+var_60]
0x18014235f  xor     rcx, rsp; StackCookie
0x180142362  call    __security_check_cookie
0x180142367  movaps  xmm6, [rsp+210h+var_58+8]
0x18014236f  add     rsp, 1D8h
0x180142376  pop     r15
0x180142378  pop     r14
0x18014237a  pop     r13
0x18014237c  pop     r12
0x18014237e  pop     rdi
0x18014237f  pop     rsi
0x180142380  pop     rbx
0x180142381  pop     rbp
0x180142382  retn
0x180142383  call    cs:__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ; Mso::DWriteAssistant::ResourceManager::GetInstance(void)
0x180142389  cmp     [rax+70h], esi
0x18014238c  jle     loc_18014243C
0x180142392  mov     rcx, r15
0x180142395  call    ??C?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@Mso@@QEBAPEAUITextRunSequence@DWriteAssistant@1@XZ; Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(void)
0x18014239a  mov     rdx, rax
0x18014239d  mov     rcx, [rax]
0x1801423a0  mov     rax, [rcx+18h]
0x1801423a4  mov     rcx, rdx
0x1801423a7  call    cs:__guard_dispatch_icall_fptr
0x1801423ad  mov     [rbp+0F0h+var_160], rsi
0x1801423b1  mov     [rbp+0F0h+var_148], rax
0x1801423b5  lea     rdx, [rbp+0F0h+var_148]
0x1801423b9  lea     rcx, [rbp+0F0h+var_160]
0x1801423bd  call    ??$HrQueryFrom@UIDWriteFontFace1@@PEAUIDWriteFontFace@@@ComUtil@Mso@@YAJAEAV?$TCntPtr@UIDWriteFontFace1@@@1@AEBQEAUIDWriteFontFace@@AEBU_GUID@@@Z; Mso::ComUtil::HrQueryFrom<IDWriteFontFace1,IDWriteFontFace *>(Mso::TCntPtr<IDWriteFontFace1> &,IDWriteFontFace * const &,_GUID const &)
0x1801423c2  mov     ebx, eax
0x1801423c4  test    eax, eax
0x1801423c6  js      short loc_180142419
0x1801423c8  mov     rcx, [rbp+0F0h+var_160]
0x1801423cc  test    rcx, rcx
0x1801423cf  jz      short loc_18014241D
0x1801423d1  mov     rax, [rcx]
0x1801423d4  mov     rax, [rax+0E8h]
0x1801423db  call    cs:__guard_dispatch_icall_fptr
0x1801423e1  test    eax, eax
0x1801423e3  jz      short loc_180142419
0x1801423e5  mov     rcx, [rbp+0F0h+var_160]
0x1801423e9  test    rcx, rcx
0x1801423ec  jnz     short loc_1801423FC
0x1801423ee  xor     edx, edx
0x1801423f0  mov     ecx, 1E3C3840h
0x1801423f5  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801423fb  nop
0x1801423fc  mov     rax, [rcx]
0x1801423ff  lea     r9, [rbp+0F0h+var_170]
0x180142403  lea     r8, [rbp+0F0h+var_170]
0x180142407  mov     edx, r13d
0x18014240a  mov     rax, [rax+0E0h]
0x180142411  call    cs:__guard_dispatch_icall_fptr
0x180142417  mov     ebx, eax
0x180142419  mov     rcx, [rbp+0F0h+var_160]
0x18014241d  test    rcx, rcx
0x180142420  jz      loc_180142319
0x180142426  mov     [rbp+0F0h+var_160], rsi
0x18014242a  mov     rax, [rcx]
0x18014242d  mov     rax, [rax+10h]
0x180142431  call    cs:__guard_dispatch_icall_fptr
0x180142437  jmp     loc_180142319
0x18014243c  call    cs:__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ; Mso::DWriteAssistant::ResourceManager::GetInstance(void)
0x180142442  mov     rdi, [rax+48h]
0x180142446  mov     [rbp+0F0h+var_138], 21h ; '!'
0x18014244e  xor     r9d, r9d; dwFlags
0x180142451  lea     r8d, [r9+55h]; cchName
0x180142455  lea     rdx, [rbp+0F0h+Name]; lpName
0x180142459  mov     ecx, [r14+74h]; Locale
0x18014245d  call    cs:__imp_LCIDToLocaleName
0x180142463  mov     dword ptr [rbp+0F0h+var_148], 74726576h
0x18014246a  mov     dword ptr [rbp+0F0h+var_148+4], r13d
0x18014246e  mov     dword ptr [rbp+0F0h+var_160], r13d
0x180142472  lea     rax, [rbp+0F0h+var_148]
0x180142476  mov     [rbp+0F0h+var_128], rax
0x18014247a  mov     [rbp+0F0h+var_120], r13
0x18014247e  lea     rax, [rbp+0F0h+var_128]
0x180142482  mov     [rbp+0F0h+var_130], rax
0x180142486  mov     [rbp+0F0h+var_13C], esi
0x180142489  mov     [rbp+0F0h+var_150], si
0x18014248d  mov     [rbp+0F0h+var_154], si
0x180142491  mov     [rbp+0F0h+var_158], si
0x180142495  mov     rax, [rdi]
0x180142498  mov     rbx, [rax+38h]
0x18014249c  mov     rcx, r15
0x18014249f  call    ??C?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@Mso@@QEBAPEAUITextRunSequence@DWriteAssistant@1@XZ; Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(void)
0x1801424a4  mov     rdx, rax
0x1801424a7  mov     rcx, [rax]
0x1801424aa  mov     rax, [rcx+18h]
0x1801424ae  mov     rcx, rdx
0x1801424b1  call    cs:__guard_dispatch_icall_fptr
0x1801424b7  lea     rcx, [rbp+0F0h+var_13C]
0x1801424bb  mov     [rsp+88h], rcx
0x1801424c3  lea     rcx, [rbp+0F0h+var_158]
0x1801424c7  mov     [rsp+210h+var_190], rcx
0x1801424cf  lea     rcx, [rbp+0F0h+var_170]
0x1801424d3  mov     [rsp+210h+var_198], rcx
0x1801424d8  lea     rcx, [rbp+0F0h+var_154]
0x1801424dc  mov     [rsp+210h+var_1A0], rcx
0x1801424e1  lea     rcx, [rbp+0F0h+var_150]
0x1801424e5  mov     [rsp+210h+var_1A8], rcx
0x1801424ea  mov     dword ptr [rsp+210h+var_1B0], r13d
0x1801424ef  mov     [rsp+210h+var_1B8], r13d
0x1801424f4  lea     rcx, [rbp+0F0h+var_160]
0x1801424f8  mov     qword ptr [rsp+210h+var_1C0], rcx
0x1801424fd  lea     rcx, [rbp+0F0h+var_130]
0x180142501  mov     [rsp+210h+var_1C8], rcx
0x180142506  mov     [rsp+210h+var_1D0], rsi
0x18014250b  lea     rcx, [rbp+0F0h+Name]
0x18014250f  mov     [rsp+210h+var_1D8], rcx
0x180142514  lea     rcx, [rbp+0F0h+var_138]
0x180142518  mov     [rsp+210h+var_1E0], rcx
0x18014251d  mov     dword ptr [rsp+210h+var_1E8], esi
0x180142521  mov     [rsp+210h+var_1F0], esi
0x180142525  mov     r9, rax
0x180142528  mov     r8d, r13d
0x18014252b  lea     rdx, [rbp+0F0h+var_168]
0x18014252f  mov     rcx, rdi
0x180142532  mov     rax, rbx
0x180142535  call    cs:__guard_dispatch_icall_fptr
0x18014253b  mov     ebx, eax
0x18014253d  jmp     loc_180142319
0x180142542  mov     [rbp+0F0h+var_170], si
0x180142546  jmp     loc_18014233F
```
