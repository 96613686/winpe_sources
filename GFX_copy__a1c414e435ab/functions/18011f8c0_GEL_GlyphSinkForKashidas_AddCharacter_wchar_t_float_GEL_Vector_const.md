# GEL::GlyphSinkForKashidas::AddCharacter(wchar_t,float,GEL::Vector const &)

- ea: `0x18011f8c0`
- end: `0x18011fb8c`
- name: `?AddCharacter@GlyphSinkForKashidas@GEL@@UEAAX_WMAEBUVector@2@@Z`
- size: `716`
- prototype: `void __fastcall(GEL::GlyphSinkForKashidas *__hidden this, wchar_t, float, const struct GEL::Vector *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180056ee0`
- `0x1800573f0`
- `0x180064e30`
- `0x18011f8c0`
- `0x180189d30`

## import_xrefs

- `KERNEL32!LCIDToLocaleName` at `0x18011fa9d`
- `KERNEL32!LCIDToLocaleName` at `0x18011fa9d`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x18011f9c3`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x18011fa7c`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x18011f9c3`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x18011fa7c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18011fa35`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18011fa35`

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
  v8 = Mso::TCntPtr<IWICImagingFactory>::operator->((char *)this + 88);
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
    v18 = Mso::TCntPtr<IWICImagingFactory>::operator->(v7);
    v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 24LL))(v18);
    v10 = v17(v16, &v21, 1, v19, 0, 0, &v29, Name, 0, &v30, &v22, 1, 1, &v25, &v24, &v20, v23, &v28);
    goto LABEL_3;
  }
  v12 = Mso::TCntPtr<IWICImagingFactory>::operator->(v7);
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
0x18011f8c0  mov     rax, rsp
0x18011f8c3  push    rbp
0x18011f8c4  push    rbx
0x18011f8c5  push    rsi
0x18011f8c6  push    rdi
0x18011f8c7  push    r12
0x18011f8c9  push    r13
0x18011f8cb  push    r14
0x18011f8cd  push    r15
0x18011f8cf  lea     rbp, [rax-0F8h]
0x18011f8d6  sub     rsp, 1D8h
0x18011f8dd  movaps  xmmword ptr [rax-58h], xmm6
0x18011f8e1  mov     rax, cs:__security_cookie
0x18011f8e8  xor     rax, rsp
0x18011f8eb  mov     [rbp+0F0h+var_60], rax
0x18011f8f2  mov     r12, r9
0x18011f8f5  movaps  xmm6, xmm2
0x18011f8f8  mov     r14, rcx
0x18011f8fb  mov     [rbp+0F0h+var_168], dx
0x18011f8ff  xor     esi, esi
0x18011f901  mov     [rbp+0F0h+var_170], si
0x18011f905  movzx   eax, dx
0x18011f908  mov     [rbp+0F0h+var_140], eax
0x18011f90b  lea     r15, [rcx+58h]
0x18011f90f  mov     rcx, r15
0x18011f912  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x18011f917  mov     rdx, rax
0x18011f91a  mov     rcx, [rax]
0x18011f91d  mov     rax, [rcx+18h]
0x18011f921  mov     rcx, rdx
0x18011f924  call    cs:__guard_dispatch_icall_fptr
0x18011f92a  mov     r10, rax
0x18011f92d  mov     rcx, [rax]
0x18011f930  mov     rax, [rcx+58h]
0x18011f934  lea     r9, [rbp+0F0h+var_170]
0x18011f938  lea     r13d, [rsi+1]
0x18011f93c  mov     r8d, r13d
0x18011f93f  lea     rdx, [rbp+0F0h+var_140]
0x18011f943  mov     rcx, r10
0x18011f946  call    cs:__guard_dispatch_icall_fptr
0x18011f94c  mov     ebx, eax
0x18011f94e  test    eax, eax
0x18011f950  js      short loc_18011F959
0x18011f952  test    byte ptr [r14+60h], 4
0x18011f957  jnz     short loc_18011F9C3
0x18011f959  mov     ecx, 2800h
0x18011f95e  movzx   eax, [rbp+0F0h+var_168]
0x18011f962  add     ax, cx
0x18011f965  mov     ecx, 7FFh
0x18011f96a  cmp     ax, cx
0x18011f96d  jbe     loc_18011FB82
0x18011f973  test    ebx, ebx
0x18011f975  js      loc_18011FB82
0x18011f97b  movzx   esi, [rbp+0F0h+var_170]
0x18011f97f  mov     rax, [r14]
0x18011f982  mov     r9, r12
0x18011f985  movaps  xmm2, xmm6
0x18011f988  movzx   edx, si
0x18011f98b  mov     rcx, r14
0x18011f98e  mov     rax, [rax+10h]
0x18011f992  call    cs:__guard_dispatch_icall_fptr
0x18011f998  mov     rcx, [rbp+0F0h+var_60]
0x18011f99f  xor     rcx, rsp; StackCookie
0x18011f9a2  call    __security_check_cookie
0x18011f9a7  movaps  xmm6, [rsp+210h+var_58+8]
0x18011f9af  add     rsp, 1D8h
0x18011f9b6  pop     r15
0x18011f9b8  pop     r14
0x18011f9ba  pop     r13
0x18011f9bc  pop     r12
0x18011f9be  pop     rdi
0x18011f9bf  pop     rsi
0x18011f9c0  pop     rbx
0x18011f9c1  pop     rbp
0x18011f9c2  retn
0x18011f9c3  call    cs:__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ; Mso::DWriteAssistant::ResourceManager::GetInstance(void)
0x18011f9c9  cmp     [rax+70h], esi
0x18011f9cc  jle     loc_18011FA7C
0x18011f9d2  mov     rcx, r15
0x18011f9d5  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x18011f9da  mov     rdx, rax
0x18011f9dd  mov     rcx, [rax]
0x18011f9e0  mov     rax, [rcx+18h]
0x18011f9e4  mov     rcx, rdx
0x18011f9e7  call    cs:__guard_dispatch_icall_fptr
0x18011f9ed  mov     [rbp+0F0h+var_160], rsi
0x18011f9f1  mov     [rbp+0F0h+var_148], rax
0x18011f9f5  lea     rdx, [rbp+0F0h+var_148]
0x18011f9f9  lea     rcx, [rbp+0F0h+var_160]
0x18011f9fd  call    ??$HrQueryFrom@UIDWriteFontFace1@@PEAUIDWriteFontFace@@@ComUtil@Mso@@YAJAEAV?$TCntPtr@UIDWriteFontFace1@@@1@AEBQEAUIDWriteFontFace@@AEBU_GUID@@@Z; Mso::ComUtil::HrQueryFrom<IDWriteFontFace1,IDWriteFontFace *>(Mso::TCntPtr<IDWriteFontFace1> &,IDWriteFontFace * const &,_GUID const &)
0x18011fa02  mov     ebx, eax
0x18011fa04  test    eax, eax
0x18011fa06  js      short loc_18011FA59
0x18011fa08  mov     rcx, [rbp+0F0h+var_160]
0x18011fa0c  test    rcx, rcx
0x18011fa0f  jz      short loc_18011FA5D
0x18011fa11  mov     rax, [rcx]
0x18011fa14  mov     rax, [rax+0E8h]
0x18011fa1b  call    cs:__guard_dispatch_icall_fptr
0x18011fa21  test    eax, eax
0x18011fa23  jz      short loc_18011FA59
0x18011fa25  mov     rcx, [rbp+0F0h+var_160]
0x18011fa29  test    rcx, rcx
0x18011fa2c  jnz     short loc_18011FA3C
0x18011fa2e  xor     edx, edx
0x18011fa30  mov     ecx, 1E3C3840h
0x18011fa35  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18011fa3b  nop
0x18011fa3c  mov     rax, [rcx]
0x18011fa3f  lea     r9, [rbp+0F0h+var_170]
0x18011fa43  lea     r8, [rbp+0F0h+var_170]
0x18011fa47  mov     edx, r13d
0x18011fa4a  mov     rax, [rax+0E0h]
0x18011fa51  call    cs:__guard_dispatch_icall_fptr
0x18011fa57  mov     ebx, eax
0x18011fa59  mov     rcx, [rbp+0F0h+var_160]
0x18011fa5d  test    rcx, rcx
0x18011fa60  jz      loc_18011F959
0x18011fa66  mov     [rbp+0F0h+var_160], rsi
0x18011fa6a  mov     rax, [rcx]
0x18011fa6d  mov     rax, [rax+10h]
0x18011fa71  call    cs:__guard_dispatch_icall_fptr
0x18011fa77  jmp     loc_18011F959
0x18011fa7c  call    cs:__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ; Mso::DWriteAssistant::ResourceManager::GetInstance(void)
0x18011fa82  mov     rdi, [rax+48h]
0x18011fa86  mov     [rbp+0F0h+var_138], 21h ; '!'
0x18011fa8e  xor     r9d, r9d; dwFlags
0x18011fa91  lea     r8d, [r9+55h]; cchName
0x18011fa95  lea     rdx, [rbp+0F0h+Name]; lpName
0x18011fa99  mov     ecx, [r14+74h]; Locale
0x18011fa9d  call    cs:__imp_LCIDToLocaleName
0x18011faa3  mov     dword ptr [rbp+0F0h+var_148], 74726576h
0x18011faaa  mov     dword ptr [rbp+0F0h+var_148+4], r13d
0x18011faae  mov     dword ptr [rbp+0F0h+var_160], r13d
0x18011fab2  lea     rax, [rbp+0F0h+var_148]
0x18011fab6  mov     [rbp+0F0h+var_128], rax
0x18011faba  mov     [rbp+0F0h+var_120], r13
0x18011fabe  lea     rax, [rbp+0F0h+var_128]
0x18011fac2  mov     [rbp+0F0h+var_130], rax
0x18011fac6  mov     [rbp+0F0h+var_13C], esi
0x18011fac9  mov     [rbp+0F0h+var_150], si
0x18011facd  mov     [rbp+0F0h+var_154], si
0x18011fad1  mov     [rbp+0F0h+var_158], si
0x18011fad5  mov     rax, [rdi]
0x18011fad8  mov     rbx, [rax+38h]
0x18011fadc  mov     rcx, r15
0x18011fadf  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x18011fae4  mov     rdx, rax
0x18011fae7  mov     rcx, [rax]
0x18011faea  mov     rax, [rcx+18h]
0x18011faee  mov     rcx, rdx
0x18011faf1  call    cs:__guard_dispatch_icall_fptr
0x18011faf7  lea     rcx, [rbp+0F0h+var_13C]
0x18011fafb  mov     [rsp+88h], rcx
0x18011fb03  lea     rcx, [rbp+0F0h+var_158]
0x18011fb07  mov     [rsp+210h+var_190], rcx
0x18011fb0f  lea     rcx, [rbp+0F0h+var_170]
0x18011fb13  mov     [rsp+210h+var_198], rcx
0x18011fb18  lea     rcx, [rbp+0F0h+var_154]
0x18011fb1c  mov     [rsp+210h+var_1A0], rcx
0x18011fb21  lea     rcx, [rbp+0F0h+var_150]
0x18011fb25  mov     [rsp+210h+var_1A8], rcx
0x18011fb2a  mov     dword ptr [rsp+210h+var_1B0], r13d
0x18011fb2f  mov     [rsp+210h+var_1B8], r13d
0x18011fb34  lea     rcx, [rbp+0F0h+var_160]
0x18011fb38  mov     qword ptr [rsp+210h+var_1C0], rcx
0x18011fb3d  lea     rcx, [rbp+0F0h+var_130]
0x18011fb41  mov     [rsp+210h+var_1C8], rcx
0x18011fb46  mov     [rsp+210h+var_1D0], rsi
0x18011fb4b  lea     rcx, [rbp+0F0h+Name]
0x18011fb4f  mov     [rsp+210h+var_1D8], rcx
0x18011fb54  lea     rcx, [rbp+0F0h+var_138]
0x18011fb58  mov     [rsp+210h+var_1E0], rcx
0x18011fb5d  mov     dword ptr [rsp+210h+var_1E8], esi
0x18011fb61  mov     [rsp+210h+var_1F0], esi
0x18011fb65  mov     r9, rax
0x18011fb68  mov     r8d, r13d
0x18011fb6b  lea     rdx, [rbp+0F0h+var_168]
0x18011fb6f  mov     rcx, rdi
0x18011fb72  mov     rax, rbx
0x18011fb75  call    cs:__guard_dispatch_icall_fptr
0x18011fb7b  mov     ebx, eax
0x18011fb7d  jmp     loc_18011F959
0x18011fb82  mov     [rbp+0F0h+var_170], si
0x18011fb86  jmp     loc_18011F97F
```
