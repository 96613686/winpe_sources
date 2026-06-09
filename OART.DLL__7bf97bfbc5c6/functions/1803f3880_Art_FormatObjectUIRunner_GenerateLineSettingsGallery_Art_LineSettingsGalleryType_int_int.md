# Art::FormatObjectUIRunner::GenerateLineSettingsGallery(Art::LineSettingsGalleryType,int,int)

- ea: `0x1803f3880`
- end: `0x1803f3bb9`
- name: `?GenerateLineSettingsGallery@FormatObjectUIRunner@Art@@IEAAXW4LineSettingsGalleryType@2@HH@Z`
- size: `825`
- prototype: `void __high(enum Art::LineSettingsGalleryType, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1803f3654`

## callees

- `0x18001df74`
- `0x180038180`
- `0x1800659a0`
- `0x180071720`
- `0x1801b09dc`
- `0x1802f51ac`
- `0x1802fb58c`
- `0x1802fb8e0`
- `0x1803f3880`
- `0x1803f3bbc`
- `0x1803f5008`
- `0x1805c5134`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoHrCreateGalleryDataSource@@YAJAEAVGalleryDSSP@@PEAUIDataSource@OfficeSpace@@@Z` at `0x1803f38cd`
- `Mso98Win32Client!__imp_?MsoHrCreateGalleryDataSource@@YAJAEAVGalleryDSSP@@PEAUIDataSource@OfficeSpace@@@Z` at `0x1803f38cd`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1803f3b27`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1803f3b27`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1803f3a52`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1803f3aa6`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1803f3b5f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1803f3a52`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1803f3aa6`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1803f3b5f`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1803f3a22`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1803f3a76`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1803f3a22`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1803f3a76`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1803f3aac`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1803f3ac1`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1803f3aac`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1803f3ac1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803f3953`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803f3b99`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803f3ba6`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803f3953`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803f3b99`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803f3ba6`

## pseudocode

```c
void __fastcall Art::FormatObjectUIRunner::GenerateLineSettingsGallery(__int64 a1, unsigned int a2, int a3, int a4)
{
  __int64 v8; // rbx
  int GalleryDataSource; // eax
  int v10; // r14d
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  void *v13; // rax
  __int64 v14; // r14
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rdx
  NetUI::BaseValue *v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // rbx
  HINSTANCE HinstIntl; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  HINSTANCE v26; // rax
  __int64 v27; // rbx
  __int64 v28; // [rsp+30h] [rbp-20h] BYREF
  __int128 v29; // [rsp+38h] [rbp-18h] BYREF
  __int64 v30; // [rsp+48h] [rbp-8h]
  NetUI::BaseValue *v31; // [rsp+80h] [rbp+30h] BYREF

  v8 = a1 + 8LL * (int)a2;
  if ( !*(_QWORD *)(v8 + 368) )
  {
    v29 = 0;
    v30 = 0;
    GalleryDataSource = MsoHrCreateGalleryDataSource((struct GalleryDSSP *)&v29, 0);
    if ( GalleryDataSource < 0 )
    {
      Ofc::CHResultException::ThrowTag(GalleryDataSource, 0x23484509u);
      __debugbreak();
    }
    v10 = Art::LineSettingsGalleryUser::MapLineSettingsGalleryTypeToDgcid(a2);
    v13 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x108, v11, v12);
    if ( v13 )
      v13 = (void *)sub_1805C5134((int)v13, (int)a1 + 24, a2, v10, (GalleryDSSP *)&v29);
    if ( *(void **)(v8 + 368) != v13 )
      Ofc::TCntPtr<Dr::GroupShapeMoniker>::Assign(v8 + 368, v13);
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(v8 + 368) + 176LL))(*(_QWORD *)(v8 + 368)) )
    {
      v17 = 591939402;
      goto LABEL_12;
    }
    v14 = *(_QWORD *)(v8 + 368);
    v15 = v29;
    if ( (_QWORD)v29 == v30 )
    {
      v16 = *((_QWORD *)&v29 + 1);
      if ( !*((_QWORD *)&v29 + 1) )
        goto LABEL_21;
    }
    else
    {
      if ( !(_QWORD)v29 )
      {
LABEL_21:
        v18 = Art::FormatObjectUIRunner::MapLineSettingsGalleryTypeToPropertyId(a2);
        Art::FormatObjectUIRunner::FSetDataSource<FlexUI::IDataSource *>(a1, v18, v15);
        if ( a2 - 1 <= 3 )
        {
          v21 = v29;
          if ( (_QWORD)v29 )
          {
            v31 = 0;
            FlexUI::FlexValue::CreateInt32(2, (struct FlexUI::FlexValueSP *)&v31);
            if ( v31 )
            {
              (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v21 + 48LL))(v21, 0, 131);
              if ( v31 )
                NetUI::BaseValue::Release(v31);
            }
          }
          else
          {
            MsoShipAssertTagProc(7997248);
          }
          v22 = v29;
          if ( (_QWORD)v29 )
          {
            v31 = 0;
            FlexUI::FlexValue::CreateInt32(3, (struct FlexUI::FlexValueSP *)&v31);
            if ( v31 )
            {
              (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v22 + 48LL))(v22, 0, 138);
              v20 = v31;
              if ( v31 )
                NetUI::BaseValue::Release(v31);
            }
          }
          else
          {
            MsoShipAssertTagProc(7997248);
          }
        }
        HinstIntl = (HINSTANCE)MsoGetHinstIntl(v20, v19);
        Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v28, HinstIntl, a3);
        v26 = (HINSTANCE)MsoGetHinstIntl(v25, v24);
        Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v31, v26, a3);
        Art::FormatObjectUIRunner::InitGalleryAnchor(
          (struct GalleryDSSP *)&v29,
          a4,
          (const struct Ofc::CVarStr *)&v31,
          (const struct Ofc::CVarStr *)&v28,
          0x10u);
        Ofc::XString::Release((NetUI::BaseValue *)((char *)v31 - 12));
        Ofc::XString::Release((Ofc::XString *)(v28 - 12));
        v27 = v29;
        if ( (_QWORD)v29 )
        {
          v31 = 0;
          FlexUI::FlexValue::CreateBoolean(0, (struct FlexUI::FlexValueSP *)&v31);
          if ( v31 )
          {
            (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v27 + 48LL))(v27, 0, 1098907681);
            if ( v31 )
              NetUI::BaseValue::Release(v31);
          }
          goto LABEL_13;
        }
        v17 = 7997248;
LABEL_12:
        MsoShipAssertTagProc(v17);
LABEL_13:
        if ( (_QWORD)v29 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v29 + 16LL))(v29);
        return;
      }
      v30 = v29;
      (**(void (__fastcall ***)(_QWORD, GUID *, char *))v29)(
        v29,
        &GUID_000c012f_0000_0000_c000_000000000046,
        (char *)&v29 + 8);
      if ( !*((_QWORD *)&v29 + 1)
        || ((*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v29 + 1) + 16LL))(*((_QWORD *)&v29 + 1)),
            (v16 = *((_QWORD *)&v29 + 1)) == 0) )
      {
LABEL_20:
        v15 = v29;
        goto LABEL_21;
      }
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 120LL))(v16, v14);
    goto LABEL_20;
  }
}

```

## disassembly

```asm
0x1803f3880  mov     [rsp-28h+arg_8], rbx
0x1803f3885  mov     [rsp-28h+arg_10], rsi
0x1803f388a  push    rbp
0x1803f388b  push    rdi
0x1803f388c  push    r12
0x1803f388e  push    r14
0x1803f3890  push    r15
0x1803f3892  mov     rbp, rsp
0x1803f3895  sub     rsp, 50h
0x1803f3899  mov     r12d, r9d
0x1803f389c  mov     r15d, r8d
0x1803f389f  movsxd  rdi, edx
0x1803f38a2  mov     rsi, rcx
0x1803f38a5  lea     rbx, [rcx+rdi*8]
0x1803f38a9  cmp     qword ptr [rbx+170h], 0
0x1803f38b1  jnz     loc_1803F3970
0x1803f38b7  xorps   xmm0, xmm0
0x1803f38ba  movdqu  [rbp+var_18], xmm0
0x1803f38bf  mov     [rbp+var_8], 0
0x1803f38c7  xor     edx, edx
0x1803f38c9  lea     rcx, [rbp+var_18]
0x1803f38cd  call    cs:__imp_?MsoHrCreateGalleryDataSource@@YAJAEAVGalleryDSSP@@PEAUIDataSource@OfficeSpace@@@Z; MsoHrCreateGalleryDataSource(GalleryDSSP &,OfficeSpace::IDataSource *)
0x1803f38d3  test    eax, eax
0x1803f38d5  js      loc_1803F3B6A
0x1803f38db  mov     ecx, edi
0x1803f38dd  call    ?MapLineSettingsGalleryTypeToDgcid@LineSettingsGalleryUser@Art@@SA?AW4MSODGCID@@W4LineSettingsGalleryType@2@@Z; Art::LineSettingsGalleryUser::MapLineSettingsGalleryTypeToDgcid(Art::LineSettingsGalleryType)
0x1803f38e2  mov     r14d, eax
0x1803f38e5  mov     ecx, 108h; this
0x1803f38ea  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1803f38ef  test    rax, rax
0x1803f38f2  jnz     loc_1803F3B77
0x1803f38f8  cmp     [rbx+170h], rax
0x1803f38ff  jz      short loc_1803F3910
0x1803f3901  mov     rdx, rax
0x1803f3904  lea     rcx, [rbx+170h]
0x1803f390b  call    ?Assign@?$TCntPtr@VGroupShapeMoniker@Dr@@@Ofc@@AEAAXPEAVGroupShapeMoniker@Dr@@@Z; Ofc::TCntPtr<Dr::GroupShapeMoniker>::Assign(Dr::GroupShapeMoniker *)
0x1803f3910  mov     rcx, [rbx+170h]
0x1803f3917  mov     rax, [rcx]
0x1803f391a  mov     rax, [rax+0B0h]
0x1803f3921  call    cs:__guard_dispatch_icall_fptr
0x1803f3927  test    al, al
0x1803f3929  jz      short loc_1803F394E
0x1803f392b  mov     r14, [rbx+170h]
0x1803f3932  mov     rbx, qword ptr [rbp+var_18]
0x1803f3936  cmp     rbx, [rbp+var_8]
0x1803f393a  jnz     short loc_1803F3989
0x1803f393c  mov     rcx, qword ptr [rbp+var_18+8]
0x1803f3940  test    rcx, rcx
0x1803f3943  jnz     loc_1803F39CB
0x1803f3949  jmp     loc_1803F39DF
0x1803f394e  mov     ecx, 2348474Ah
0x1803f3953  call    cs:__imp_MsoShipAssertTagProc
0x1803f3959  nop
0x1803f395a  mov     rcx, qword ptr [rbp+var_18]
0x1803f395e  test    rcx, rcx
0x1803f3961  jz      short loc_1803F3970
0x1803f3963  mov     rax, [rcx]
0x1803f3966  mov     rax, [rax+10h]
0x1803f396a  call    cs:__guard_dispatch_icall_fptr
0x1803f3970  lea     r11, [rsp+50h+var_s0]
0x1803f3975  mov     rbx, [r11+38h]
0x1803f3979  mov     rsi, [r11+40h]
0x1803f397d  mov     rsp, r11
0x1803f3980  pop     r15
0x1803f3982  pop     r14
0x1803f3984  pop     r12
0x1803f3986  pop     rdi
0x1803f3987  pop     rbp
0x1803f3988  retn
0x1803f3989  test    rbx, rbx
0x1803f398c  jz      short loc_1803F39DF
0x1803f398e  mov     [rbp+var_8], rbx
0x1803f3992  mov     rax, [rbx]
0x1803f3995  lea     r8, [rbp+var_18+8]
0x1803f3999  lea     rdx, _GUID_000c012f_0000_0000_c000_000000000046
0x1803f39a0  mov     rcx, rbx
0x1803f39a3  mov     rax, [rax]
0x1803f39a6  call    cs:__guard_dispatch_icall_fptr
0x1803f39ac  mov     rcx, qword ptr [rbp+var_18+8]
0x1803f39b0  test    rcx, rcx
0x1803f39b3  jz      short loc_1803F39DB
0x1803f39b5  mov     rax, [rcx]
0x1803f39b8  mov     rax, [rax+10h]
0x1803f39bc  call    cs:__guard_dispatch_icall_fptr
0x1803f39c2  mov     rcx, qword ptr [rbp+var_18+8]
0x1803f39c6  test    rcx, rcx
0x1803f39c9  jz      short loc_1803F39DB
0x1803f39cb  mov     rax, [rcx]
0x1803f39ce  mov     rdx, r14
0x1803f39d1  mov     rax, [rax+78h]
0x1803f39d5  call    cs:__guard_dispatch_icall_fptr
0x1803f39db  mov     rbx, qword ptr [rbp+var_18]
0x1803f39df  mov     ecx, edi
0x1803f39e1  call    ?MapLineSettingsGalleryTypeToPropertyId@FormatObjectUIRunner@Art@@KA?AW4OartFormatObjectDlgParamsPropertyId@OartFormatObjectDlgParams@@W4LineSettingsGalleryType@2@@Z; Art::FormatObjectUIRunner::MapLineSettingsGalleryTypeToPropertyId(Art::LineSettingsGalleryType)
0x1803f39e6  mov     r8, rbx
0x1803f39e9  mov     edx, eax
0x1803f39eb  mov     rcx, rsi
0x1803f39ee  call    ??$FSetDataSource@PEAUIDataSource@FlexUI@@@FormatObjectUIRunner@Art@@QEAA_NW4OartFormatObjectDlgParamsPropertyId@OartFormatObjectDlgParams@@PEAUIDataSource@FlexUI@@@Z; Art::FormatObjectUIRunner::FSetDataSource<FlexUI::IDataSource *>(OartFormatObjectDlgParams::OartFormatObjectDlgParamsPropertyId,FlexUI::IDataSource *)
0x1803f39f3  lea     eax, [rdi-1]
0x1803f39f6  mov     edi, 7A0740h
0x1803f39fb  cmp     eax, 3
0x1803f39fe  ja      loc_1803F3AAC
0x1803f3a04  mov     rbx, qword ptr [rbp+var_18]
0x1803f3a08  test    rbx, rbx
0x1803f3a0b  jz      loc_1803F3B97
0x1803f3a11  mov     [rbp+arg_0], 0
0x1803f3a19  lea     rdx, [rbp+arg_0]
0x1803f3a1d  mov     ecx, 2
0x1803f3a22  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1803f3a28  mov     r9, [rbp+arg_0]
0x1803f3a2c  test    r9, r9
0x1803f3a2f  jz      short loc_1803F3A58
0x1803f3a31  mov     rax, [rbx]
0x1803f3a34  xor     edx, edx
0x1803f3a36  mov     r8d, 83h
0x1803f3a3c  mov     rcx, rbx
0x1803f3a3f  mov     rax, [rax+30h]
0x1803f3a43  call    cs:__guard_dispatch_icall_fptr
0x1803f3a49  mov     rcx, [rbp+arg_0]
0x1803f3a4d  test    rcx, rcx
0x1803f3a50  jz      short loc_1803F3A58
0x1803f3a52  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1803f3a58  mov     rbx, qword ptr [rbp+var_18]
0x1803f3a5c  test    rbx, rbx
0x1803f3a5f  jz      loc_1803F3BA4
0x1803f3a65  mov     [rbp+arg_0], 0
0x1803f3a6d  lea     rdx, [rbp+arg_0]
0x1803f3a71  mov     ecx, 3
0x1803f3a76  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1803f3a7c  mov     r9, [rbp+arg_0]
0x1803f3a80  test    r9, r9
0x1803f3a83  jz      short loc_1803F3AAC
0x1803f3a85  mov     rax, [rbx]
0x1803f3a88  xor     edx, edx
0x1803f3a8a  mov     r8d, 8Ah
0x1803f3a90  mov     rcx, rbx
0x1803f3a93  mov     rax, [rax+30h]
0x1803f3a97  call    cs:__guard_dispatch_icall_fptr
0x1803f3a9d  mov     rcx, [rbp+arg_0]
0x1803f3aa1  test    rcx, rcx
0x1803f3aa4  jz      short loc_1803F3AAC
0x1803f3aa6  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1803f3aac  call    cs:__imp_MsoGetHinstIntl
0x1803f3ab2  mov     rdx, rax; HINSTANCE
0x1803f3ab5  mov     r8d, r15d; int
0x1803f3ab8  lea     rcx, [rbp+var_20]; this
0x1803f3abc  call    ??0CVarStr@Ofc@@QEAA@PEAUHINSTANCE__@@H@Z; Ofc::CVarStr::CVarStr(HINSTANCE__ *,int)
0x1803f3ac1  call    cs:__imp_MsoGetHinstIntl
0x1803f3ac7  mov     rdx, rax; HINSTANCE
0x1803f3aca  mov     r8d, r15d; int
0x1803f3acd  lea     rcx, [rbp+arg_0]; this
0x1803f3ad1  call    ??0CVarStr@Ofc@@QEAA@PEAUHINSTANCE__@@H@Z; Ofc::CVarStr::CVarStr(HINSTANCE__ *,int)
0x1803f3ad6  mov     dword ptr [rsp+50h+var_30], 10h; unsigned int
0x1803f3ade  lea     r9, [rbp+var_20]; struct Ofc::CVarStr *
0x1803f3ae2  lea     r8, [rbp+arg_0]; struct Ofc::CVarStr *
0x1803f3ae6  mov     edx, r12d; int
0x1803f3ae9  lea     rcx, [rbp+var_18]; struct GalleryDSSP *
0x1803f3aed  call    ?InitGalleryAnchor@FormatObjectUIRunner@Art@@SA_NAEAVGalleryDSSP@@HAEBVCVarStr@Ofc@@1I@Z; Art::FormatObjectUIRunner::InitGalleryAnchor(GalleryDSSP &,int,Ofc::CVarStr const &,Ofc::CVarStr const &,uint)
0x1803f3af2  mov     rcx, [rbp+arg_0]
0x1803f3af6  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x1803f3afa  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x1803f3aff  mov     rcx, [rbp+var_20]
0x1803f3b03  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x1803f3b07  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x1803f3b0c  mov     rbx, qword ptr [rbp+var_18]
0x1803f3b10  test    rbx, rbx
0x1803f3b13  jz      loc_1803F3BB1
0x1803f3b19  mov     [rbp+arg_0], 0
0x1803f3b21  lea     rdx, [rbp+arg_0]
0x1803f3b25  xor     ecx, ecx
0x1803f3b27  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x1803f3b2d  mov     r9, [rbp+arg_0]
0x1803f3b31  test    r9, r9
0x1803f3b34  jz      loc_1803F395A
0x1803f3b3a  mov     rax, [rbx]
0x1803f3b3d  xor     edx, edx
0x1803f3b3f  mov     r8d, 41800021h
0x1803f3b45  mov     rcx, rbx
0x1803f3b48  mov     rax, [rax+30h]
0x1803f3b4c  call    cs:__guard_dispatch_icall_fptr
0x1803f3b52  mov     rcx, [rbp+arg_0]
0x1803f3b56  test    rcx, rcx
0x1803f3b59  jz      loc_1803F395A
0x1803f3b5f  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1803f3b65  jmp     loc_1803F395A
0x1803f3b6a  mov     edx, 23484509h; unsigned int
0x1803f3b6f  mov     ecx, eax; int
0x1803f3b71  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1803f3b76  int     3; Trap to Debugger
0x1803f3b77  lea     rdx, [rsi+18h]; int
0x1803f3b7b  lea     rcx, [rbp+var_18]
0x1803f3b7f  mov     [rsp+50h+var_30], rcx; GalleryDSSP *
0x1803f3b84  mov     r9d, r14d; int
0x1803f3b87  mov     r8d, edi; int
0x1803f3b8a  mov     rcx, rax; int
0x1803f3b8d  call    sub_1805C5134
0x1803f3b92  jmp     loc_1803F38F8
0x1803f3b97  mov     ecx, edi
0x1803f3b99  call    cs:__imp_MsoShipAssertTagProc
0x1803f3b9f  jmp     loc_1803F3A58
0x1803f3ba4  mov     ecx, edi
0x1803f3ba6  call    cs:__imp_MsoShipAssertTagProc
0x1803f3bac  jmp     loc_1803F3AAC
0x1803f3bb1  mov     ecx, edi
0x1803f3bb3  jmp     loc_1803F3953
```
