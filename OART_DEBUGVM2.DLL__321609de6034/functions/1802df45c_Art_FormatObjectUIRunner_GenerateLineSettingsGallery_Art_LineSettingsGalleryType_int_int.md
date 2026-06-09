# Art::FormatObjectUIRunner::GenerateLineSettingsGallery(Art::LineSettingsGalleryType,int,int)

- ea: `0x1802df45c`
- end: `0x1802df787`
- name: `?GenerateLineSettingsGallery@FormatObjectUIRunner@Art@@IEAAXW4LineSettingsGalleryType@2@HH@Z`
- size: `811`
- prototype: `void __high(enum Art::LineSettingsGalleryType, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1802df23c`

## callees

- `0x18000e24c`
- `0x180019e80`
- `0x18002a690`
- `0x180144e90`
- `0x180279050`
- `0x1802a5d84`
- `0x1802d56d0`
- `0x1802df45c`
- `0x1802df788`
- `0x1802e001c`
- `0x1802e0374`
- `0x1805e46d4`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoHrCreateGalleryDataSource@@YAJAEAVGalleryDSSP@@PEAUIDataSource@OfficeSpace@@@Z` at `0x1802df4a9`
- `Mso98Win32Client!__imp_?MsoHrCreateGalleryDataSource@@YAJAEAVGalleryDSSP@@PEAUIDataSource@OfficeSpace@@@Z` at `0x1802df4a9`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1802df6c5`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1802df6c5`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1802df5f0`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1802df644`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1802df6f5`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1802df5f0`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1802df644`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1802df6f5`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1802df5c0`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1802df614`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1802df5c0`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1802df614`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1802df64a`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1802df65f`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1802df64a`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1802df65f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802df702`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802df767`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802df774`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802df702`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802df767`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802df774`

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
  unsigned int v17; // eax
  __int64 v18; // rdx
  NetUI::BaseValue *v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rbx
  HINSTANCE HinstIntl; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  HINSTANCE v25; // rax
  __int64 v26; // rbx
  __int64 v27; // rcx
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
      v13 = (void *)sub_1805E46D4((int)v13, (int)a1 + 24, a2, v10, (GalleryDSSP *)&v29);
    if ( *(void **)(v8 + 368) != v13 )
      Ofc::TCntPtr<Dr::GroupShapeMoniker>::Assign(v8 + 368, v13);
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(v8 + 368) + 176LL))(*(_QWORD *)(v8 + 368)) )
    {
      v27 = 591939402;
      goto LABEL_30;
    }
    v14 = *(_QWORD *)(v8 + 368);
    v15 = v29;
    if ( (_QWORD)v29 == v30 )
    {
      v16 = *((_QWORD *)&v29 + 1);
      if ( !*((_QWORD *)&v29 + 1) )
        goto LABEL_16;
    }
    else
    {
      if ( !(_QWORD)v29 )
      {
LABEL_16:
        v17 = Art::FormatObjectUIRunner::MapLineSettingsGalleryTypeToPropertyId(a2);
        Art::FormatObjectUIRunner::FSetDataSource<FlexUI::IDataSource *>(a1, v17, v15);
        if ( a2 - 1 <= 3 )
        {
          v20 = v29;
          if ( (_QWORD)v29 )
          {
            v31 = 0;
            FlexUI::FlexValue::CreateInt32(2, (struct FlexUI::FlexValueSP *)&v31);
            if ( v31 )
            {
              (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v20 + 48LL))(v20, 0, 131);
              if ( v31 )
                NetUI::BaseValue::Release(v31);
            }
          }
          else
          {
            MsoShipAssertTagProc(7997248);
          }
          v21 = v29;
          if ( (_QWORD)v29 )
          {
            v31 = 0;
            FlexUI::FlexValue::CreateInt32(3, (struct FlexUI::FlexValueSP *)&v31);
            if ( v31 )
            {
              (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v21 + 48LL))(v21, 0, 138);
              v19 = v31;
              if ( v31 )
                NetUI::BaseValue::Release(v31);
            }
          }
          else
          {
            MsoShipAssertTagProc(7997248);
          }
        }
        HinstIntl = (HINSTANCE)MsoGetHinstIntl(v19, v18);
        Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v28, HinstIntl, a3);
        v25 = (HINSTANCE)MsoGetHinstIntl(v24, v23);
        Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v31, v25, a3);
        Art::FormatObjectUIRunner::InitGalleryAnchor(
          (struct GalleryDSSP *)&v29,
          a4,
          (const struct Ofc::CVarStr *)&v31,
          (const struct Ofc::CVarStr *)&v28,
          0x10u);
        Ofc::XString::Release((NetUI::BaseValue *)((char *)v31 - 12));
        Ofc::XString::Release((Ofc::XString *)(v28 - 12));
        v26 = v29;
        if ( (_QWORD)v29 )
        {
          v31 = 0;
          FlexUI::FlexValue::CreateBoolean(0, (struct FlexUI::FlexValueSP *)&v31);
          if ( v31 )
          {
            (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v26 + 48LL))(v26, 0, 1098907681);
            if ( v31 )
              NetUI::BaseValue::Release(v31);
          }
          goto LABEL_31;
        }
        v27 = 7997248;
LABEL_30:
        MsoShipAssertTagProc(v27);
LABEL_31:
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
LABEL_15:
        v15 = v29;
        goto LABEL_16;
      }
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 120LL))(v16, v14);
    goto LABEL_15;
  }
}

```

## disassembly

```asm
0x1802df45c  mov     [rsp-28h+arg_8], rbx
0x1802df461  mov     [rsp-28h+arg_10], rsi
0x1802df466  push    rbp
0x1802df467  push    rdi
0x1802df468  push    r12
0x1802df46a  push    r14
0x1802df46c  push    r15
0x1802df46e  mov     rbp, rsp
0x1802df471  sub     rsp, 50h
0x1802df475  mov     r12d, r9d
0x1802df478  mov     r15d, r8d
0x1802df47b  movsxd  rdi, edx
0x1802df47e  mov     rsi, rcx
0x1802df481  lea     rbx, [rcx+rdi*8]
0x1802df485  cmp     qword ptr [rbx+170h], 0
0x1802df48d  jnz     loc_1802DF71F
0x1802df493  xorps   xmm0, xmm0
0x1802df496  movdqu  [rbp+var_18], xmm0
0x1802df49b  mov     [rbp+var_8], 0
0x1802df4a3  xor     edx, edx
0x1802df4a5  lea     rcx, [rbp+var_18]
0x1802df4a9  call    cs:__imp_?MsoHrCreateGalleryDataSource@@YAJAEAVGalleryDSSP@@PEAUIDataSource@OfficeSpace@@@Z; MsoHrCreateGalleryDataSource(GalleryDSSP &,OfficeSpace::IDataSource *)
0x1802df4af  test    eax, eax
0x1802df4b1  js      loc_1802DF738
0x1802df4b7  mov     ecx, edi
0x1802df4b9  call    ?MapLineSettingsGalleryTypeToDgcid@LineSettingsGalleryUser@Art@@SA?AW4MSODGCID@@W4LineSettingsGalleryType@2@@Z; Art::LineSettingsGalleryUser::MapLineSettingsGalleryTypeToDgcid(Art::LineSettingsGalleryType)
0x1802df4be  mov     r14d, eax
0x1802df4c1  mov     ecx, 108h; this
0x1802df4c6  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1802df4cb  test    rax, rax
0x1802df4ce  jnz     loc_1802DF745
0x1802df4d4  cmp     [rbx+170h], rax
0x1802df4db  jz      short loc_1802DF4EC
0x1802df4dd  mov     rdx, rax
0x1802df4e0  lea     rcx, [rbx+170h]
0x1802df4e7  call    ?Assign@?$TCntPtr@VGroupShapeMoniker@Dr@@@Ofc@@AEAAXPEAVGroupShapeMoniker@Dr@@@Z; Ofc::TCntPtr<Dr::GroupShapeMoniker>::Assign(Dr::GroupShapeMoniker *)
0x1802df4ec  mov     rcx, [rbx+170h]
0x1802df4f3  mov     rax, [rcx]
0x1802df4f6  mov     rax, [rax+0B0h]
0x1802df4fd  call    cs:__guard_dispatch_icall_fptr
0x1802df503  test    al, al
0x1802df505  jz      loc_1802DF6FD
0x1802df50b  mov     r14, [rbx+170h]
0x1802df512  mov     rbx, qword ptr [rbp+var_18]
0x1802df516  cmp     rbx, [rbp+var_8]
0x1802df51a  jnz     short loc_1802DF527
0x1802df51c  mov     rcx, qword ptr [rbp+var_18+8]
0x1802df520  test    rcx, rcx
0x1802df523  jnz     short loc_1802DF569
0x1802df525  jmp     short loc_1802DF57D
0x1802df527  test    rbx, rbx
0x1802df52a  jz      short loc_1802DF57D
0x1802df52c  mov     [rbp+var_8], rbx
0x1802df530  mov     rax, [rbx]
0x1802df533  lea     r8, [rbp+var_18+8]
0x1802df537  lea     rdx, _GUID_000c012f_0000_0000_c000_000000000046
0x1802df53e  mov     rcx, rbx
0x1802df541  mov     rax, [rax]
0x1802df544  call    cs:__guard_dispatch_icall_fptr
0x1802df54a  mov     rcx, qword ptr [rbp+var_18+8]
0x1802df54e  test    rcx, rcx
0x1802df551  jz      short loc_1802DF579
0x1802df553  mov     rax, [rcx]
0x1802df556  mov     rax, [rax+10h]
0x1802df55a  call    cs:__guard_dispatch_icall_fptr
0x1802df560  mov     rcx, qword ptr [rbp+var_18+8]
0x1802df564  test    rcx, rcx
0x1802df567  jz      short loc_1802DF579
0x1802df569  mov     rax, [rcx]
0x1802df56c  mov     rdx, r14
0x1802df56f  mov     rax, [rax+78h]
0x1802df573  call    cs:__guard_dispatch_icall_fptr
0x1802df579  mov     rbx, qword ptr [rbp+var_18]
0x1802df57d  mov     ecx, edi
0x1802df57f  call    ?MapLineSettingsGalleryTypeToPropertyId@FormatObjectUIRunner@Art@@KA?AW4OartFormatObjectDlgParamsPropertyId@OartFormatObjectDlgParams@@W4LineSettingsGalleryType@2@@Z; Art::FormatObjectUIRunner::MapLineSettingsGalleryTypeToPropertyId(Art::LineSettingsGalleryType)
0x1802df584  mov     r8, rbx
0x1802df587  mov     edx, eax
0x1802df589  mov     rcx, rsi
0x1802df58c  call    ??$FSetDataSource@PEAUIDataSource@FlexUI@@@FormatObjectUIRunner@Art@@QEAA_NW4OartFormatObjectDlgParamsPropertyId@OartFormatObjectDlgParams@@PEAUIDataSource@FlexUI@@@Z; Art::FormatObjectUIRunner::FSetDataSource<FlexUI::IDataSource *>(OartFormatObjectDlgParams::OartFormatObjectDlgParamsPropertyId,FlexUI::IDataSource *)
0x1802df591  lea     eax, [rdi-1]
0x1802df594  mov     edi, 7A0740h
0x1802df599  cmp     eax, 3
0x1802df59c  ja      loc_1802DF64A
0x1802df5a2  mov     rbx, qword ptr [rbp+var_18]
0x1802df5a6  test    rbx, rbx
0x1802df5a9  jz      loc_1802DF765
0x1802df5af  mov     [rbp+arg_0], 0
0x1802df5b7  lea     rdx, [rbp+arg_0]
0x1802df5bb  mov     ecx, 2
0x1802df5c0  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1802df5c6  mov     r9, [rbp+arg_0]
0x1802df5ca  test    r9, r9
0x1802df5cd  jz      short loc_1802DF5F6
0x1802df5cf  mov     rax, [rbx]
0x1802df5d2  xor     edx, edx
0x1802df5d4  mov     r8d, 83h
0x1802df5da  mov     rcx, rbx
0x1802df5dd  mov     rax, [rax+30h]
0x1802df5e1  call    cs:__guard_dispatch_icall_fptr
0x1802df5e7  mov     rcx, [rbp+arg_0]
0x1802df5eb  test    rcx, rcx
0x1802df5ee  jz      short loc_1802DF5F6
0x1802df5f0  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1802df5f6  mov     rbx, qword ptr [rbp+var_18]
0x1802df5fa  test    rbx, rbx
0x1802df5fd  jz      loc_1802DF772
0x1802df603  mov     [rbp+arg_0], 0
0x1802df60b  lea     rdx, [rbp+arg_0]
0x1802df60f  mov     ecx, 3
0x1802df614  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1802df61a  mov     r9, [rbp+arg_0]
0x1802df61e  test    r9, r9
0x1802df621  jz      short loc_1802DF64A
0x1802df623  mov     rax, [rbx]
0x1802df626  xor     edx, edx
0x1802df628  mov     r8d, 8Ah
0x1802df62e  mov     rcx, rbx
0x1802df631  mov     rax, [rax+30h]
0x1802df635  call    cs:__guard_dispatch_icall_fptr
0x1802df63b  mov     rcx, [rbp+arg_0]
0x1802df63f  test    rcx, rcx
0x1802df642  jz      short loc_1802DF64A
0x1802df644  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1802df64a  call    cs:__imp_MsoGetHinstIntl
0x1802df650  mov     rdx, rax; HINSTANCE
0x1802df653  mov     r8d, r15d; int
0x1802df656  lea     rcx, [rbp+var_20]; this
0x1802df65a  call    ??0CVarStr@Ofc@@QEAA@PEAUHINSTANCE__@@H@Z; Ofc::CVarStr::CVarStr(HINSTANCE__ *,int)
0x1802df65f  call    cs:__imp_MsoGetHinstIntl
0x1802df665  mov     rdx, rax; HINSTANCE
0x1802df668  mov     r8d, r15d; int
0x1802df66b  lea     rcx, [rbp+arg_0]; this
0x1802df66f  call    ??0CVarStr@Ofc@@QEAA@PEAUHINSTANCE__@@H@Z; Ofc::CVarStr::CVarStr(HINSTANCE__ *,int)
0x1802df674  mov     dword ptr [rsp+50h+var_30], 10h; unsigned int
0x1802df67c  lea     r9, [rbp+var_20]; struct Ofc::CVarStr *
0x1802df680  lea     r8, [rbp+arg_0]; struct Ofc::CVarStr *
0x1802df684  mov     edx, r12d; int
0x1802df687  lea     rcx, [rbp+var_18]; struct GalleryDSSP *
0x1802df68b  call    ?InitGalleryAnchor@FormatObjectUIRunner@Art@@SA_NAEAVGalleryDSSP@@HAEBVCVarStr@Ofc@@1I@Z; Art::FormatObjectUIRunner::InitGalleryAnchor(GalleryDSSP &,int,Ofc::CVarStr const &,Ofc::CVarStr const &,uint)
0x1802df690  mov     rcx, [rbp+arg_0]
0x1802df694  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x1802df698  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x1802df69d  mov     rcx, [rbp+var_20]
0x1802df6a1  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x1802df6a5  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x1802df6aa  mov     rbx, qword ptr [rbp+var_18]
0x1802df6ae  test    rbx, rbx
0x1802df6b1  jz      loc_1802DF77F
0x1802df6b7  mov     [rbp+arg_0], 0
0x1802df6bf  lea     rdx, [rbp+arg_0]
0x1802df6c3  xor     ecx, ecx
0x1802df6c5  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x1802df6cb  mov     r9, [rbp+arg_0]
0x1802df6cf  test    r9, r9
0x1802df6d2  jz      short loc_1802DF709
0x1802df6d4  mov     rax, [rbx]
0x1802df6d7  xor     edx, edx
0x1802df6d9  mov     r8d, 41800021h
0x1802df6df  mov     rcx, rbx
0x1802df6e2  mov     rax, [rax+30h]
0x1802df6e6  call    cs:__guard_dispatch_icall_fptr
0x1802df6ec  mov     rcx, [rbp+arg_0]
0x1802df6f0  test    rcx, rcx
0x1802df6f3  jz      short loc_1802DF709
0x1802df6f5  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1802df6fb  jmp     short loc_1802DF709
0x1802df6fd  mov     ecx, 2348474Ah
0x1802df702  call    cs:__imp_MsoShipAssertTagProc
0x1802df708  nop
0x1802df709  mov     rcx, qword ptr [rbp+var_18]
0x1802df70d  test    rcx, rcx
0x1802df710  jz      short loc_1802DF71F
0x1802df712  mov     rax, [rcx]
0x1802df715  mov     rax, [rax+10h]
0x1802df719  call    cs:__guard_dispatch_icall_fptr
0x1802df71f  lea     r11, [rsp+50h+var_s0]
0x1802df724  mov     rbx, [r11+38h]
0x1802df728  mov     rsi, [r11+40h]
0x1802df72c  mov     rsp, r11
0x1802df72f  pop     r15
0x1802df731  pop     r14
0x1802df733  pop     r12
0x1802df735  pop     rdi
0x1802df736  pop     rbp
0x1802df737  retn
0x1802df738  mov     edx, 23484509h; unsigned int
0x1802df73d  mov     ecx, eax; int
0x1802df73f  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1802df744  int     3; Trap to Debugger
0x1802df745  lea     rdx, [rsi+18h]; int
0x1802df749  lea     rcx, [rbp+var_18]
0x1802df74d  mov     [rsp+50h+var_30], rcx; GalleryDSSP *
0x1802df752  mov     r9d, r14d; int
0x1802df755  mov     r8d, edi; int
0x1802df758  mov     rcx, rax; int
0x1802df75b  call    sub_1805E46D4
0x1802df760  jmp     loc_1802DF4D4
0x1802df765  mov     ecx, edi
0x1802df767  call    cs:__imp_MsoShipAssertTagProc
0x1802df76d  jmp     loc_1802DF5F6
0x1802df772  mov     ecx, edi
0x1802df774  call    cs:__imp_MsoShipAssertTagProc
0x1802df77a  jmp     loc_1802DF64A
0x1802df77f  mov     ecx, edi
0x1802df781  jmp     loc_1802DF702
```
