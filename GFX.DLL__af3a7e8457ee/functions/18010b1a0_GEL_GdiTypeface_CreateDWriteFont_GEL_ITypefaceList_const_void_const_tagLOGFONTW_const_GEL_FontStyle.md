# GEL::GdiTypeface::CreateDWriteFont(GEL::ITypefaceList const &,void const *,tagLOGFONTW const &,GEL::FontStyle)

- ea: `0x18010b1a0`
- end: `0x18010b36f`
- name: `?CreateDWriteFont@GdiTypeface@GEL@@UEBA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@Mso@@AEBUITypefaceList@2@PEBXAEBUtagLOGFONTW@@W4FontStyle@2@@Z`
- size: `463`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000f890`
- `0x180065ce0`
- `0x1800795a0`
- `0x180079d04`
- `0x180079e08`
- `0x180079e34`
- `0x18010b1a0`
- `0x18010b370`

## import_xrefs

- `MSVCP140!_Mtx_unlock` at `0x18010b348`
- `MSVCP140!_Mtx_unlock` at `0x18010b348`
- `mso40uiWin32Client!__imp_?CreateFromHdc@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@2@PEAUHDC__@@_N@Z` at `0x18010b293`
- `mso40uiWin32Client!__imp_?CreateFromHdc@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@2@PEAUHDC__@@_N@Z` at `0x18010b33e`
- `mso40uiWin32Client!__imp_?CreateFromHdc@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@2@PEAUHDC__@@_N@Z` at `0x18010b293`
- `mso40uiWin32Client!__imp_?CreateFromHdc@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@2@PEAUHDC__@@_N@Z` at `0x18010b33e`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18010b1e1`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18010b1e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall GEL::GdiTypeface::CreateDWriteFont(
        __int64 a1,
        void **a2,
        const struct GEL::ITypefaceList *a3,
        __int64 a4,
        struct tagLOGFONTW *a5,
        unsigned int a6)
{
  bool v10; // al
  struct _Mtx_internal_imp_t *v11; // r15
  struct _Mtx_internal_imp_t *v12; // rcx
  __int64 v13; // r8
  unsigned int v14; // edx
  __int64 v15; // rbx
  void *v16; // rax
  __int64 v17; // r8
  void *v19; // [rsp+20h] [rbp-20h] BYREF
  __int64 v20; // [rsp+28h] [rbp-18h] BYREF
  _QWORD *v21; // [rsp+30h] [rbp-10h]
  _Mtx_t v22; // [rsp+38h] [rbp-8h]

  if ( byte_18051FFE8 < 0 )
    v10 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_18051FFE8);
  else
    v10 = byte_18051FFE8 != 0;
  if ( !v10 )
  {
    GEL::SharedDeviceIC::SharedDeviceIC((GEL::SharedDeviceIC *)&v20, a3, a5);
    v17 = a6 >> 2;
    LOBYTE(v17) = (a6 & 4) != 0;
    Mso::DWriteAssistant::CreateFromHdc(a2, *v21, v17);
LABEL_15:
    v12 = v22;
    goto LABEL_16;
  }
  v20 = GEL::TInternalCast<GEL::ITypefaceList,GEL::GdiTypefaceList>::ToInternal(a3);
  v11 = (struct _Mtx_internal_imp_t *)(v20 + 144);
  v21 = (_QWORD *)(v20 + 136);
  v22 = (_Mtx_t)(v20 + 144);
  std::_Mutex_base::lock((std::_Mutex_base *)(v20 + 144));
  if ( !*(_BYTE *)(a1 + 392)
    || *(const struct GEL::ITypefaceList **)(a1 + 272) != a3
    || *(_QWORD *)(a1 + 280) != a4
    || !(unsigned __int8)sub_18010B370(a1 + 288, a5)
    || *(_DWORD *)(a1 + 380) != a6 )
  {
    GEL::SharedDeviceIC::SelectFont((GEL::SharedDeviceIC *)&v20, a5);
    v13 = a6 >> 2;
    LOBYTE(v13) = (a6 & 4) != 0;
    Mso::DWriteAssistant::CreateFromHdc(&v19, *v21, v13);
    v15 = a1 + 272;
    if ( *(_BYTE *)(v15 + 120) )
    {
      GEL::GdiTypeface::DWriteFontCache::`scalar deleting destructor'((GEL::GdiTypeface::DWriteFontCache *)v15, v14);
      *(_BYTE *)(v15 + 120) = 0;
    }
    *(_QWORD *)v15 = a3;
    *(_QWORD *)(v15 + 8) = a4;
    *(_OWORD *)(v15 + 16) = *(_OWORD *)&a5->lfHeight;
    *(_OWORD *)(v15 + 32) = *(_OWORD *)&a5->lfWeight;
    *(_OWORD *)(v15 + 48) = *(_OWORD *)&a5->lfFaceName[2];
    *(_OWORD *)(v15 + 64) = *(_OWORD *)&a5->lfFaceName[10];
    *(_OWORD *)(v15 + 80) = *(_OWORD *)&a5->lfFaceName[18];
    *(_QWORD *)(v15 + 96) = *(_QWORD *)&a5->lfFaceName[26];
    *(_DWORD *)(v15 + 104) = *(_DWORD *)&a5->lfFaceName[30];
    *(_DWORD *)(v15 + 108) = a6;
    *(_QWORD *)(v15 + 112) = v19;
    Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>((void *const *)(v15 + 112));
    *(_BYTE *)(v15 + 120) = 1;
    v16 = v19;
    v19 = 0;
    *a2 = v16;
    goto LABEL_15;
  }
  *a2 = *(void **)(a1 + 384);
  Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(a2);
  v12 = v11;
LABEL_16:
  _Mtx_unlock(v12);
  return a2;
}

```

## disassembly

```asm
0x18010b1a0  mov     [rsp-28h+arg_0], rbx
0x18010b1a5  mov     [rsp-28h+arg_8], rsi
0x18010b1aa  mov     [rsp-28h+arg_10], rdi
0x18010b1af  push    rbp
0x18010b1b0  push    r12
0x18010b1b2  push    r13
0x18010b1b4  push    r14
0x18010b1b6  push    r15
0x18010b1b8  mov     rbp, rsp
0x18010b1bb  sub     rsp, 40h
0x18010b1bf  mov     r13, r9
0x18010b1c2  mov     r14, r8
0x18010b1c5  mov     rdi, rdx
0x18010b1c8  mov     rbx, rcx
0x18010b1cb  mov     al, cs:byte_18051FFE8
0x18010b1d1  test    al, al
0x18010b1d3  js      short loc_18010B1DA
0x18010b1d5  setnz   al
0x18010b1d8  jmp     short loc_18010B1E7
0x18010b1da  lea     rcx, byte_18051FFE8
0x18010b1e1  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x18010b1e7  test    al, al
0x18010b1e9  jz      loc_18010B318
0x18010b1ef  mov     rcx, r14
0x18010b1f2  call    ?ToInternal@?$TInternalCast@UITypefaceList@GEL@@VGdiTypefaceList@2@@GEL@@SAAEBVGdiTypefaceList@2@AEBUITypefaceList@2@@Z; GEL::TInternalCast<GEL::ITypefaceList,GEL::GdiTypefaceList>::ToInternal(GEL::ITypefaceList const &)
0x18010b1f7  mov     [rbp+var_18], rax
0x18010b1fb  lea     r15, [rax+90h]
0x18010b202  add     rax, 88h
0x18010b208  mov     [rbp+var_10], rax
0x18010b20c  mov     [rbp+var_8], r15
0x18010b210  mov     rcx, r15; this
0x18010b213  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18010b218  mov     r12d, [rbp+arg_28]
0x18010b21c  mov     rsi, [rbp+arg_20]
0x18010b220  cmp     byte ptr [rbx+188h], 0
0x18010b227  jz      short loc_18010B271
0x18010b229  cmp     [rbx+110h], r14
0x18010b230  jnz     short loc_18010B271
0x18010b232  cmp     [rbx+118h], r13
0x18010b239  jnz     short loc_18010B271
0x18010b23b  lea     rcx, [rbx+120h]
0x18010b242  mov     rdx, rsi
0x18010b245  call    sub_18010B370
0x18010b24a  test    al, al
0x18010b24c  jz      short loc_18010B271
0x18010b24e  cmp     [rbx+17Ch], r12d
0x18010b255  jnz     short loc_18010B271
0x18010b257  mov     rax, [rbx+180h]
0x18010b25e  mov     [rdi], rax
0x18010b261  mov     rcx, rdi; void **
0x18010b264  call    ??$CheckedAddRefOnNewlyAssignedPtr@VWindow@GEL@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAVWindow@GEL@@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(GEL::Window * *)
0x18010b269  mov     rcx, r15
0x18010b26c  jmp     loc_18010B348
0x18010b271  mov     rdx, rsi; struct tagLOGFONTW *
0x18010b274  lea     rcx, [rbp+var_18]; this
0x18010b278  call    ?SelectFont@SharedDeviceIC@GEL@@QEAAXAEBUtagLOGFONTW@@@Z; GEL::SharedDeviceIC::SelectFont(tagLOGFONTW const &)
0x18010b27d  mov     r8d, r12d
0x18010b280  shr     r8d, 2
0x18010b284  and     r8b, 1
0x18010b288  mov     rdx, [rbp+var_10]
0x18010b28c  mov     rdx, [rdx]
0x18010b28f  lea     rcx, [rbp+var_20]
0x18010b293  call    cs:__imp_?CreateFromHdc@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@2@PEAUHDC__@@_N@Z; Mso::DWriteAssistant::CreateFromHdc(HDC__ *,bool)
0x18010b299  add     rbx, 110h
0x18010b2a0  xor     r15d, r15d
0x18010b2a3  cmp     [rbx+78h], r15b
0x18010b2a7  jz      short loc_18010B2B5
0x18010b2a9  mov     rcx, rbx; this
0x18010b2ac  call    ??_GDWriteFontCache@GdiTypeface@GEL@@QEAAPEAXI@Z; GEL::GdiTypeface::DWriteFontCache::`scalar deleting destructor'(uint)
0x18010b2b1  mov     [rbx+78h], r15b
0x18010b2b5  mov     [rbx], r14
0x18010b2b8  lea     rcx, [rbx+70h]; void **
0x18010b2bc  mov     [rbx+8], r13
0x18010b2c0  movups  xmm0, xmmword ptr [rsi]
0x18010b2c3  movups  xmmword ptr [rbx+10h], xmm0
0x18010b2c7  movups  xmm1, xmmword ptr [rsi+10h]
0x18010b2cb  movups  xmmword ptr [rbx+20h], xmm1
0x18010b2cf  movups  xmm0, xmmword ptr [rsi+20h]
0x18010b2d3  movups  xmmword ptr [rbx+30h], xmm0
0x18010b2d7  movups  xmm1, xmmword ptr [rsi+30h]
0x18010b2db  movups  xmmword ptr [rbx+40h], xmm1
0x18010b2df  movups  xmm0, xmmword ptr [rsi+40h]
0x18010b2e3  movups  xmmword ptr [rbx+50h], xmm0
0x18010b2e7  movsd   xmm1, qword ptr [rsi+50h]
0x18010b2ec  movsd   qword ptr [rbx+60h], xmm1
0x18010b2f1  mov     eax, [rsi+58h]
0x18010b2f4  mov     [rbx+68h], eax
0x18010b2f7  mov     [rbx+6Ch], r12d
0x18010b2fb  mov     rax, [rbp+var_20]
0x18010b2ff  mov     [rcx], rax
0x18010b302  call    ??$CheckedAddRefOnNewlyAssignedPtr@VWindow@GEL@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAVWindow@GEL@@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(GEL::Window * *)
0x18010b307  mov     byte ptr [rbx+78h], 1
0x18010b30b  mov     rax, [rbp+var_20]
0x18010b30f  mov     [rbp+var_20], r15
0x18010b313  mov     [rdi], rax
0x18010b316  jmp     short loc_18010B344
0x18010b318  mov     r8, [rbp+arg_20]; struct tagLOGFONTW *
0x18010b31c  mov     rdx, r14; struct GEL::ITypefaceList *
0x18010b31f  lea     rcx, [rbp+var_18]; this
0x18010b323  call    ??0SharedDeviceIC@GEL@@QEAA@AEBUITypefaceList@1@AEBUtagLOGFONTW@@@Z; GEL::SharedDeviceIC::SharedDeviceIC(GEL::ITypefaceList const &,tagLOGFONTW const &)
0x18010b328  mov     r8d, [rbp+arg_28]
0x18010b32c  shr     r8d, 2
0x18010b330  and     r8b, 1
0x18010b334  mov     rdx, [rbp+var_10]
0x18010b338  mov     rdx, [rdx]
0x18010b33b  mov     rcx, rdi
0x18010b33e  call    cs:__imp_?CreateFromHdc@DWriteAssistant@Mso@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@2@PEAUHDC__@@_N@Z; Mso::DWriteAssistant::CreateFromHdc(HDC__ *,bool)
0x18010b344  mov     rcx, [rbp+var_8]; _Mtx_t
0x18010b348  call    cs:__imp__Mtx_unlock
0x18010b34e  mov     rax, rdi
0x18010b351  lea     r11, [rsp+40h+var_s0]
0x18010b356  mov     rbx, [r11+30h]
0x18010b35a  mov     rsi, [r11+38h]
0x18010b35e  mov     rdi, [r11+40h]
0x18010b362  mov     rsp, r11
0x18010b365  pop     r15
0x18010b367  pop     r14
0x18010b369  pop     r13
0x18010b36b  pop     r12
0x18010b36d  pop     rbp
0x18010b36e  retn
```
