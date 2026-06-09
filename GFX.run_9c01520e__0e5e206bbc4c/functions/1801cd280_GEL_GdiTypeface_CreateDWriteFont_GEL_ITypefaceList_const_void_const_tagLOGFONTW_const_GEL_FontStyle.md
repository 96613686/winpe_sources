# GEL::GdiTypeface::CreateDWriteFont(GEL::ITypefaceList const &,void const *,tagLOGFONTW const &,GEL::FontStyle)

- ea: `0x1801cd280`
- end: `0x1801cd3d2`
- name: `?CreateDWriteFont@GdiTypeface@GEL@@UEBA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@Mso@@AEBUITypefaceList@2@PEBXAEBUtagLOGFONTW@@W4FontStyle@2@@Z`
- size: `338`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000f790`
- `0x180076bac`
- `0x180076c98`
- `0x180076e34`
- `0x18010b8f4`
- `0x180129e30`
- `0x1801cd280`

## import_xrefs

- `MSVCP140!_Mtx_unlock` at `0x1801cd3af`
- `MSVCP140!_Mtx_unlock` at `0x1801cd3af`
- `mso40uiWin32Client!__imp_?CreateFromHdc@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@2@PEAUHDC__@@_N@Z` at `0x1801cd345`
- `mso40uiWin32Client!__imp_?CreateFromHdc@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@2@PEAUHDC__@@_N@Z` at `0x1801cd3a5`
- `mso40uiWin32Client!__imp_?CreateFromHdc@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@2@PEAUHDC__@@_N@Z` at `0x1801cd345`
- `mso40uiWin32Client!__imp_?CreateFromHdc@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@2@PEAUHDC__@@_N@Z` at `0x1801cd3a5`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1801cd2c1`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1801cd2c1`

## pseudocode

```c
void **GEL::GdiTypeface::CreateDWriteFont(__int64 a1, void **a2, const struct GEL::ITypefaceList *a3, ...)
{
  __int64 v3; // r15
  bool v7; // al
  int v8; // r14d
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // r8
  void *v13; // [rsp+30h] [rbp-30h] BYREF
  const struct GEL::ITypefaceList *v14; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v15[8]; // [rsp+40h] [rbp-20h] BYREF
  _QWORD *v16; // [rsp+48h] [rbp-18h]
  _Mtx_t v17; // [rsp+50h] [rbp-10h]
  __int64 v18; // [rsp+98h] [rbp+38h] BYREF
  va_list va; // [rsp+98h] [rbp+38h]
  struct tagLOGFONTW *v20; // [rsp+A0h] [rbp+40h]
  __int64 v21; // [rsp+A8h] [rbp+48h] BYREF
  va_list va1; // [rsp+A8h] [rbp+48h]
  va_list va2; // [rsp+B0h] [rbp+50h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v18 = va_arg(va1, _QWORD);
  v20 = va_arg(va1, struct tagLOGFONTW *);
  va_copy(va2, va1);
  v21 = va_arg(va2, _QWORD);
  v3 = v18;
  if ( byte_180524030 < 0 )
    v7 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180524030);
  else
    v7 = byte_180524030 != 0;
  if ( v7 )
  {
    GEL::SharedDeviceIC::SharedDeviceIC((GEL::SharedDeviceIC *)v15, a3);
    v8 = v21;
    v9 = a1 + 272;
    if ( *(_BYTE *)(v9 + 120)
      && *(const struct GEL::ITypefaceList **)v9 == a3
      && *(_QWORD *)(v9 + 8) == v3
      && (unsigned __int8)sub_18010B8F4(v9 + 16, v20)
      && *(_DWORD *)(v9 + 108) == v8 )
    {
      *a2 = *(void **)(v9 + 112);
      Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(a2);
    }
    else
    {
      GEL::SharedDeviceIC::SelectFont((GEL::SharedDeviceIC *)v15, v20);
      LOBYTE(v10) = (v8 & 4) != 0;
      Mso::DWriteAssistant::CreateFromHdc(&v13, *v16, v10);
      v14 = a3;
      std::optional<GEL::GdiTypeface::DWriteFontCache>::emplace<GEL::ITypefaceList const *,void const * &,tagLOGFONTW const &,enum GEL::FontStyle &,Mso::TCntPtr<Mso::DWriteAssistant::IFont> &>(
        v9,
        (unsigned int)&v14,
        (unsigned int)va,
        (_DWORD)v20,
        (__int64)va1,
        (__int64)&v13);
      *a2 = v13;
      v13 = 0;
    }
  }
  else
  {
    GEL::SharedDeviceIC::SharedDeviceIC((GEL::SharedDeviceIC *)v15, a3, v20);
    v11 = (unsigned int)v21 >> 2;
    LOBYTE(v11) = (v21 & 4) != 0;
    Mso::DWriteAssistant::CreateFromHdc(a2, *v16, v11);
  }
  _Mtx_unlock(v17);
  return a2;
}

```

## disassembly

```asm
0x1801cd280  mov     rax, rsp
0x1801cd283  mov     [rax+8], rbx
0x1801cd287  mov     [rax+10h], rsi
0x1801cd28b  mov     [rax+18h], rdi
0x1801cd28f  mov     [rax+20h], r9
0x1801cd293  push    rbp
0x1801cd294  push    r14
0x1801cd296  push    r15
0x1801cd298  mov     rbp, rsp
0x1801cd29b  sub     rsp, 60h
0x1801cd29f  mov     al, cs:byte_180524030
0x1801cd2a5  mov     r15, r9
0x1801cd2a8  mov     rsi, r8
0x1801cd2ab  mov     rdi, rdx
0x1801cd2ae  mov     rbx, rcx
0x1801cd2b1  test    al, al
0x1801cd2b3  js      short loc_1801CD2BA
0x1801cd2b5  setnz   al
0x1801cd2b8  jmp     short loc_1801CD2C7
0x1801cd2ba  lea     rcx, byte_180524030
0x1801cd2c1  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1801cd2c7  lea     rcx, [rbp+var_20]; this
0x1801cd2cb  mov     rdx, rsi; struct GEL::ITypefaceList *
0x1801cd2ce  test    al, al
0x1801cd2d0  jz      loc_1801CD386
0x1801cd2d6  call    ??0SharedDeviceIC@GEL@@QEAA@AEBUITypefaceList@1@@Z; GEL::SharedDeviceIC::SharedDeviceIC(GEL::ITypefaceList const &)
0x1801cd2db  mov     r14d, dword ptr [rbp+arg_28]
0x1801cd2df  add     rbx, 110h
0x1801cd2e6  cmp     byte ptr [rbx+78h], 0
0x1801cd2ea  jz      short loc_1801CD322
0x1801cd2ec  cmp     [rbx], rsi
0x1801cd2ef  jnz     short loc_1801CD322
0x1801cd2f1  cmp     [rbx+8], r15
0x1801cd2f5  jnz     short loc_1801CD322
0x1801cd2f7  mov     rdx, [rbp+arg_20]
0x1801cd2fb  lea     rcx, [rbx+10h]
0x1801cd2ff  call    sub_18010B8F4
0x1801cd304  test    al, al
0x1801cd306  jz      short loc_1801CD322
0x1801cd308  cmp     [rbx+6Ch], r14d
0x1801cd30c  jnz     short loc_1801CD322
0x1801cd30e  mov     rax, [rbx+70h]
0x1801cd312  mov     rcx, rdi; void **
0x1801cd315  mov     [rdi], rax
0x1801cd318  call    ??$CheckedAddRefOnNewlyAssignedPtr@VWindow@GEL@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAVWindow@GEL@@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(GEL::Window * *)
0x1801cd31d  jmp     loc_1801CD3AB
0x1801cd322  mov     rdx, [rbp+arg_20]; struct tagLOGFONTW *
0x1801cd326  lea     rcx, [rbp+var_20]; this
0x1801cd32a  call    ?SelectFont@SharedDeviceIC@GEL@@QEAAXAEBUtagLOGFONTW@@@Z; GEL::SharedDeviceIC::SelectFont(tagLOGFONTW const &)
0x1801cd32f  mov     rdx, [rbp+var_18]
0x1801cd333  lea     rcx, [rbp+var_30]
0x1801cd337  shr     r14d, 2
0x1801cd33b  and     r14b, 1
0x1801cd33f  mov     r8b, r14b
0x1801cd342  mov     rdx, [rdx]
0x1801cd345  call    cs:__imp_?CreateFromHdc@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@2@PEAUHDC__@@_N@Z; Mso::DWriteAssistant::CreateFromHdc(HDC__ *,bool)
0x1801cd34b  mov     r9, [rbp+arg_20]
0x1801cd34f  lea     rax, [rbp+var_30]
0x1801cd353  mov     [rsp+60h+var_38], rax
0x1801cd358  lea     r8, [rbp+arg_18]
0x1801cd35c  lea     rax, [rbp+arg_28]
0x1801cd360  mov     [rbp+var_28], rsi
0x1801cd364  lea     rdx, [rbp+var_28]
0x1801cd368  mov     [rsp+60h+var_40], rax
0x1801cd36d  mov     rcx, rbx
0x1801cd370  call    ??$emplace@PEBUITypefaceList@GEL@@AEAPEBXAEBUtagLOGFONTW@@AEAW4FontStyle@2@AEAV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@Mso@@@?$optional@UDWriteFontCache@GdiTypeface@GEL@@@std@@QEAAAEAUDWriteFontCache@GdiTypeface@GEL@@$$QEAPEBUITypefaceList@4@AEAPEBXAEBUtagLOGFONTW@@AEAW4FontStyle@4@AEAV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@Mso@@@Z; std::optional<GEL::GdiTypeface::DWriteFontCache>::emplace<GEL::ITypefaceList const *,void const * &,tagLOGFONTW const &,GEL::FontStyle &,Mso::TCntPtr<Mso::DWriteAssistant::IFont> &>(GEL::ITypefaceList const * &&,void const * &,tagLOGFONTW const &,GEL::FontStyle &,Mso::TCntPtr<Mso::DWriteAssistant::IFont> &)
0x1801cd375  mov     rax, [rbp+var_30]
0x1801cd379  mov     [rdi], rax
0x1801cd37c  mov     [rbp+var_30], 0
0x1801cd384  jmp     short loc_1801CD3AB
0x1801cd386  mov     r8, [rbp+arg_20]; struct tagLOGFONTW *
0x1801cd38a  call    ??0SharedDeviceIC@GEL@@QEAA@AEBUITypefaceList@1@AEBUtagLOGFONTW@@@Z; GEL::SharedDeviceIC::SharedDeviceIC(GEL::ITypefaceList const &,tagLOGFONTW const &)
0x1801cd38f  mov     r8d, dword ptr [rbp+arg_28]
0x1801cd393  mov     rcx, rdi
0x1801cd396  mov     rdx, [rbp+var_18]
0x1801cd39a  shr     r8d, 2
0x1801cd39e  and     r8b, 1
0x1801cd3a2  mov     rdx, [rdx]
0x1801cd3a5  call    cs:__imp_?CreateFromHdc@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@2@PEAUHDC__@@_N@Z; Mso::DWriteAssistant::CreateFromHdc(HDC__ *,bool)
0x1801cd3ab  mov     rcx, [rbp+var_10]; _Mtx_t
0x1801cd3af  call    cs:__imp__Mtx_unlock
0x1801cd3b5  lea     r11, [rsp+60h+var_s0]
0x1801cd3ba  mov     rax, rdi
0x1801cd3bd  mov     rbx, [r11+20h]
0x1801cd3c1  mov     rsi, [r11+28h]
0x1801cd3c5  mov     rdi, [r11+30h]
0x1801cd3c9  mov     rsp, r11
0x1801cd3cc  pop     r15
0x1801cd3ce  pop     r14
0x1801cd3d0  pop     rbp
0x1801cd3d1  retn
```
