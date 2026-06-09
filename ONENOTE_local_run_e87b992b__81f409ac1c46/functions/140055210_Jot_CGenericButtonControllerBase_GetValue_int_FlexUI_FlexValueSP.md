# Jot::CGenericButtonControllerBase::GetValue(int,FlexUI::FlexValueSP &)

- ea: `0x140055210`
- end: `0x140055562`
- name: `?GetValue@CGenericButtonControllerBase@Jot@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z`
- size: `850`
- prototype: `bool __fastcall(Jot::CGenericButtonControllerBase *__hidden this, int, struct FlexUI::FlexValueSP *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1400532a0`
- `0x140055090`
- `0x140088700`
- `0x1400888c0`
- `0x140103510`

## callees

- `0x1400488d0`
- `0x140048a58`
- `0x140055210`
- `0x140056ac0`
- `0x140057580`

## import_xrefs

- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1400553cc`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140055413`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140055474`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1400553cc`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140055413`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140055474`
- `Mso98Win32Client!__imp_?GetValue@DataSourceBase@OfficeSpace@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z` at `0x140055334`
- `Mso98Win32Client!__imp_?GetValue@DataSourceBase@OfficeSpace@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z` at `0x140055334`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1400552b4`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1400552b4`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1400553d8`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x14005541f`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x140055480`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1400554f7`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1400553d8`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x14005541f`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x140055480`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1400554f7`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x14005536b`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x14005536b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140055319`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1400553b3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1400553f3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x14005543a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140055495`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1400554b2`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140055319`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1400553b3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1400553f3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x14005543a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140055495`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1400554b2`

## pseudocode

```c
bool __fastcall Jot::CGenericButtonControllerBase::GetValue(
        Jot::CGenericButtonControllerBase *this,
        int a2,
        struct FlexUI::FlexValueSP *a3)
{
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  __int64 (*v14)(void); // rax
  char v15; // al
  void *v17; // rdx
  _BYTE *v18; // rcx
  int v19; // ebx
  int v20; // ecx
  void *v21; // rdx
  const wchar_t *v22; // rax
  void *v23; // rdx
  bool String; // bl
  _BYTE *v25; // rcx
  const wchar_t *v26; // rax
  void *v27; // rdx
  void *v28; // rdx
  const wchar_t *v29; // rax
  void *v30; // rdx
  const wchar_t *v31; // rcx
  bool v32; // di
  bool v33; // zf
  int v34; // [rsp+20h] [rbp-E0h] BYREF
  char v35; // [rsp+24h] [rbp-DCh]
  _QWORD v36[4]; // [rsp+28h] [rbp-D8h] BYREF
  char v37; // [rsp+48h] [rbp-B8h]
  _BYTE v38[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v39[40]; // [rsp+70h] [rbp-90h] BYREF
  Mso::Memory *v40; // [rsp+98h] [rbp-68h]
  _BYTE v41[272]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v42[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v43[40]; // [rsp+1E0h] [rbp+E0h] BYREF
  Mso::Memory *v44; // [rsp+208h] [rbp+108h]
  _BYTE v45[272]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v46[32]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v47[40]; // [rsp+350h] [rbp+250h] BYREF
  Mso::Memory *v48; // [rsp+378h] [rbp+278h]
  _BYTE v49[272]; // [rsp+390h] [rbp+290h] BYREF

  v6 = a2 - 1;
  if ( !v6 )
  {
    Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v46);
    if ( (*(unsigned __int8 (__fastcall **)(Jot::CGenericButtonControllerBase *, _BYTE *))(*(_QWORD *)this + 168LL))(
           this,
           v46) )
    {
      v26 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v46);
      String = FlexUI::FlexValue::CreateString(v26, a3);
      if ( v48 != (Mso::Memory *)v49 )
        Mso::Memory::Free(v48, v27);
      v25 = v47;
      goto LABEL_29;
    }
    if ( v48 != (Mso::Memory *)v49 )
      Mso::Memory::Free(v48, v17);
    v18 = v47;
    goto LABEL_17;
  }
  v7 = v6 - 5;
  if ( !v7 )
  {
    Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v42);
    if ( (*(unsigned __int8 (__fastcall **)(Jot::CGenericButtonControllerBase *, _BYTE *))(*(_QWORD *)this + 176LL))(
           this,
           v42) )
    {
      v22 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v42);
      String = FlexUI::FlexValue::CreateString(v22, a3);
      if ( v44 != (Mso::Memory *)v45 )
        Mso::Memory::Free(v44, v23);
      v25 = v43;
      goto LABEL_29;
    }
    if ( v44 != (Mso::Memory *)v45 )
      Mso::Memory::Free(v44, v21);
    v18 = v43;
LABEL_17:
    std::wstring::~wstring(v18);
    return OfficeSpace::DataSourceBase::GetValue(this, a2, a3);
  }
  v8 = v7 - 5;
  if ( !v8 )
  {
    v34 = 0;
    v33 = (*(unsigned __int8 (__fastcall **)(Jot::CGenericButtonControllerBase *, int *))(*(_QWORD *)this + 208LL))(
            this,
            &v34) == 0;
    goto LABEL_48;
  }
  v9 = v8 - 23;
  if ( !v9 )
  {
    Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v38);
    if ( (*(unsigned __int8 (__fastcall **)(Jot::CGenericButtonControllerBase *, _BYTE *))(*(_QWORD *)this + 200LL))(
           this,
           v38) )
    {
      v29 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v38);
      String = FlexUI::FlexValue::CreateString(v29, a3);
      if ( v40 != (Mso::Memory *)v41 )
        Mso::Memory::Free(v40, v30);
      v25 = v39;
LABEL_29:
      std::wstring::~wstring(v25);
      return String;
    }
    if ( v40 != (Mso::Memory *)v41 )
      Mso::Memory::Free(v40, v28);
    v18 = v39;
    goto LABEL_17;
  }
  v10 = v9 - 22;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 67;
      if ( v12 )
      {
        v13 = v12 - 1077936011;
        if ( !v13 )
        {
          v14 = *(__int64 (**)(void))(*(_QWORD *)this + 144LL);
          goto LABEL_12;
        }
        if ( v13 == 4194305 )
        {
          v14 = *(__int64 (**)(void))(*(_QWORD *)this + 152LL);
LABEL_12:
          v15 = v14();
          return FlexUI::FlexValue::CreateBoolean(v15, a3);
        }
        return OfficeSpace::DataSourceBase::GetValue(this, a2, a3);
      }
      v19 = 0;
      v34 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(Jot::CGenericButtonControllerBase *, int *))(*(_QWORD *)this + 216LL))(
             this,
             &v34) )
      {
        LOBYTE(v19) = v34 == 1;
        v20 = v19;
        return FlexUI::FlexValue::CreateInt32(v20, a3);
      }
      return OfficeSpace::DataSourceBase::GetValue(this, a2, a3);
    }
    (*(void (__fastcall **)(Jot::CGenericButtonControllerBase *, int *))(*(_QWORD *)this + 192LL))(this, &v34);
    v33 = v35 == 0;
LABEL_48:
    if ( !v33 )
    {
      v20 = v34;
      return FlexUI::FlexValue::CreateInt32(v20, a3);
    }
    return OfficeSpace::DataSourceBase::GetValue(this, a2, a3);
  }
  (*(void (__fastcall **)(Jot::CGenericButtonControllerBase *, _QWORD *))(*(_QWORD *)this + 184LL))(this, v36);
  if ( !v37 )
    return OfficeSpace::DataSourceBase::GetValue(this, a2, a3);
  v31 = (const wchar_t *)v36;
  if ( v36[3] > 7u )
    v31 = (const wchar_t *)v36[0];
  v32 = FlexUI::FlexValue::CreateString(v31, a3);
  if ( v37 )
    std::wstring::~wstring(v36);
  return v32;
}

```

## disassembly

```asm
0x140055210  push    rbp
0x140055212  push    rbx
0x140055213  push    rsi
0x140055214  push    rdi
0x140055215  push    r14
0x140055217  lea     rbp, [rsp-3B0h]
0x14005521f  sub     rsp, 4B0h
0x140055226  mov     rax, cs:__security_cookie
0x14005522d  xor     rax, rsp
0x140055230  mov     [rbp+3D0h+var_30], rax
0x140055237  mov     rsi, r8
0x14005523a  mov     r14d, edx
0x14005523d  mov     rdi, rcx
0x140055240  sub     edx, 1
0x140055243  jz      loc_1400552D8
0x140055249  sub     edx, 5
0x14005524c  jz      loc_140055376
0x140055252  sub     edx, 5
0x140055255  jz      loc_140055535
0x14005525b  sub     edx, 17h
0x14005525e  jz      loc_140055449
0x140055264  sub     edx, 16h
0x140055267  jz      loc_1400554C2
0x14005526d  sub     edx, 1
0x140055270  jz      loc_140055518
0x140055276  sub     edx, 43h ; 'C'
0x140055279  jz      loc_14005533F
0x14005527f  sub     edx, 403FFF8Bh
0x140055285  jz      short loc_14005529F
0x140055287  cmp     edx, 400001h
0x14005528d  jnz     loc_14005532B
0x140055293  mov     rax, [rcx]
0x140055296  mov     rax, [rax+98h]
0x14005529d  jmp     short loc_1400552A9
0x14005529f  mov     rax, [rcx]
0x1400552a2  mov     rax, [rax+90h]
0x1400552a9  call    cs:__guard_dispatch_icall_fptr
0x1400552af  mov     cl, al
0x1400552b1  mov     rdx, rsi
0x1400552b4  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x1400552ba  nop
0x1400552bb  mov     rcx, [rbp+3D0h+var_30]
0x1400552c2  xor     rcx, rsp; StackCookie
0x1400552c5  call    __security_check_cookie
0x1400552ca  add     rsp, 4B0h
0x1400552d1  pop     r14
0x1400552d3  pop     rdi
0x1400552d4  pop     rsi
0x1400552d5  pop     rbx
0x1400552d6  pop     rbp
0x1400552d7  retn
0x1400552d8  lea     rcx, [rbp+3D0h+var_1A0]
0x1400552df  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x1400552e4  mov     rax, [rdi]
0x1400552e7  lea     rdx, [rbp+3D0h+var_1A0]
0x1400552ee  mov     rcx, rdi
0x1400552f1  mov     rax, [rax+0A8h]
0x1400552f8  call    cs:__guard_dispatch_icall_fptr
0x1400552fe  test    al, al
0x140055300  jnz     loc_14005540C
0x140055306  lea     rax, [rbp+3D0h+var_140]
0x14005530d  mov     rcx, [rbp+3D0h+var_158]
0x140055314  cmp     rcx, rax
0x140055317  jz      short loc_14005531F
0x140055319  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x14005531f  lea     rcx, [rbp+3D0h+var_180]; void *
0x140055326  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005532b  mov     r8, rsi
0x14005532e  mov     edx, r14d
0x140055331  mov     rcx, rdi
0x140055334  call    cs:__imp_?GetValue@DataSourceBase@OfficeSpace@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z; OfficeSpace::DataSourceBase::GetValue(int,FlexUI::FlexValueSP &)
0x14005533a  jmp     loc_1400552BB
0x14005533f  xor     ebx, ebx
0x140055341  mov     [rsp+4D0h+var_4B0], ebx
0x140055345  mov     rax, [rcx]
0x140055348  lea     rdx, [rsp+4D0h+var_4B0]
0x14005534d  mov     rax, [rax+0D8h]
0x140055354  call    cs:__guard_dispatch_icall_fptr
0x14005535a  test    al, al
0x14005535c  jz      short loc_14005532B
0x14005535e  cmp     [rsp+4D0h+var_4B0], 1
0x140055363  setz    bl
0x140055366  mov     ecx, ebx
0x140055368  mov     rdx, rsi
0x14005536b  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x140055371  jmp     loc_1400552BB
0x140055376  lea     rcx, [rbp+3D0h+var_310]
0x14005537d  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x140055382  mov     rax, [rdi]
0x140055385  lea     rdx, [rbp+3D0h+var_310]
0x14005538c  mov     rcx, rdi
0x14005538f  mov     rax, [rax+0B0h]
0x140055396  call    cs:__guard_dispatch_icall_fptr
0x14005539c  test    al, al
0x14005539e  jnz     short loc_1400553C5
0x1400553a0  lea     rax, [rbp+3D0h+var_2B0]
0x1400553a7  mov     rcx, [rbp+3D0h+var_2C8]
0x1400553ae  cmp     rcx, rax
0x1400553b1  jz      short loc_1400553B9
0x1400553b3  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1400553b9  lea     rcx, [rbp+3D0h+var_2F0]
0x1400553c0  jmp     loc_140055326
0x1400553c5  lea     rcx, [rbp+3D0h+var_310]
0x1400553cc  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x1400553d2  mov     rcx, rax
0x1400553d5  mov     rdx, rsi
0x1400553d8  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x1400553de  mov     bl, al
0x1400553e0  lea     rax, [rbp+3D0h+var_2B0]
0x1400553e7  mov     rcx, [rbp+3D0h+var_2C8]
0x1400553ee  cmp     rcx, rax
0x1400553f1  jz      short loc_1400553F9
0x1400553f3  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1400553f9  lea     rcx, [rbp+3D0h+var_2F0]; void *
0x140055400  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140055405  mov     al, bl
0x140055407  jmp     loc_1400552BB
0x14005540c  lea     rcx, [rbp+3D0h+var_1A0]
0x140055413  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x140055419  mov     rcx, rax
0x14005541c  mov     rdx, rsi
0x14005541f  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x140055425  mov     bl, al
0x140055427  lea     rax, [rbp+3D0h+var_140]
0x14005542e  mov     rcx, [rbp+3D0h+var_158]
0x140055435  cmp     rcx, rax
0x140055438  jz      short loc_140055440
0x14005543a  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x140055440  lea     rcx, [rbp+3D0h+var_180]
0x140055447  jmp     short loc_140055400
0x140055449  lea     rcx, [rsp+4D0h+var_480]
0x14005544e  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x140055453  mov     rax, [rdi]
0x140055456  lea     rdx, [rsp+4D0h+var_480]
0x14005545b  mov     rcx, rdi
0x14005545e  mov     rax, [rax+0C8h]
0x140055465  call    cs:__guard_dispatch_icall_fptr
0x14005546b  test    al, al
0x14005546d  jz      short loc_1400554A5
0x14005546f  lea     rcx, [rsp+4D0h+var_480]
0x140055474  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x14005547a  mov     rcx, rax
0x14005547d  mov     rdx, rsi
0x140055480  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x140055486  mov     bl, al
0x140055488  lea     rax, [rbp+3D0h+var_420]
0x14005548c  mov     rcx, [rbp+3D0h+var_438]
0x140055490  cmp     rcx, rax
0x140055493  jz      short loc_14005549B
0x140055495  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x14005549b  lea     rcx, [rsp+4D0h+var_460]
0x1400554a0  jmp     loc_140055400
0x1400554a5  lea     rax, [rbp+3D0h+var_420]
0x1400554a9  mov     rcx, [rbp+3D0h+var_438]
0x1400554ad  cmp     rcx, rax
0x1400554b0  jz      short loc_1400554B8
0x1400554b2  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1400554b8  lea     rcx, [rsp+4D0h+var_460]
0x1400554bd  jmp     loc_140055326
0x1400554c2  mov     rax, [rcx]
0x1400554c5  lea     rdx, [rsp+4D0h+var_4A8]
0x1400554ca  mov     rax, [rax+0B8h]
0x1400554d1  call    cs:__guard_dispatch_icall_fptr
0x1400554d7  xor     ebx, ebx
0x1400554d9  cmp     [rsp+4D0h+var_488], bl
0x1400554dd  jz      loc_14005532B
0x1400554e3  lea     rcx, [rsp+4D0h+var_4A8]
0x1400554e8  cmp     [rsp+4D0h+var_490], 7
0x1400554ee  cmova   rcx, [rsp+4D0h+var_4A8]
0x1400554f4  mov     rdx, rsi
0x1400554f7  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x1400554fd  mov     dil, al
0x140055500  cmp     [rsp+4D0h+var_488], bl
0x140055504  jz      short loc_140055510
0x140055506  lea     rcx, [rsp+4D0h+var_4A8]; void *
0x14005550b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140055510  mov     al, dil
0x140055513  jmp     loc_1400552BB
0x140055518  mov     rax, [rcx]
0x14005551b  lea     rdx, [rsp+4D0h+var_4B0]
0x140055520  mov     rax, [rax+0C0h]
0x140055527  call    cs:__guard_dispatch_icall_fptr
0x14005552d  xor     ebx, ebx
0x14005552f  cmp     [rsp+4D0h+var_4AC], bl
0x140055533  jmp     short loc_140055552
0x140055535  xor     ebx, ebx
0x140055537  mov     [rsp+4D0h+var_4B0], ebx
0x14005553b  mov     rax, [rcx]
0x14005553e  lea     rdx, [rsp+4D0h+var_4B0]
0x140055543  mov     rax, [rax+0D0h]
0x14005554a  call    cs:__guard_dispatch_icall_fptr
0x140055550  test    al, al
0x140055552  jz      loc_14005532B
0x140055558  mov     ecx, [rsp+4D0h+var_4B0]
0x14005555c  jmp     loc_140055368
```
