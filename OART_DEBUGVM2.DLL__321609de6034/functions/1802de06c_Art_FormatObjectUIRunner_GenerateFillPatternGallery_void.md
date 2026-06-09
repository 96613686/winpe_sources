# Art::FormatObjectUIRunner::GenerateFillPatternGallery(void)

- ea: `0x1802de06c`
- end: `0x1802de3b5`
- name: `?GenerateFillPatternGallery@FormatObjectUIRunner@Art@@IEAAXXZ`
- size: `841`
- prototype: `void __fastcall(Art::FormatObjectUIRunner *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1802dcb68`

## callees

- `0x18002a690`
- `0x180279050`
- `0x1802abdcc`
- `0x1802d56d0`
- `0x1802de06c`
- `0x1802e001c`

## import_xrefs

- `MSO!__imp_??0CMsoPatternGalleryUser@@QEAA@PEAUIUnknown@@_N1@Z` at `0x1802de1e1`
- `MSO!__imp_??0CMsoPatternGalleryUser@@QEAA@PEAUIUnknown@@_N1@Z` at `0x1802de1e1`
- `Mso98Win32Client!__imp_?MsoHrCreateGalleryDataSource@@YAJAEAVGalleryDSSP@@PEAUIDataSource@OfficeSpace@@@Z` at `0x1802de0ad`
- `Mso98Win32Client!__imp_?MsoHrCreateGalleryDataSource@@YAJAEAVGalleryDSSP@@PEAUIDataSource@OfficeSpace@@@Z` at `0x1802de0ad`
- `Mso98Win32Client!__imp_?FInit@CMsoGalleryUserDefault@@UEAA_NXZ` at `0x1802de228`
- `Mso98Win32Client!__imp_?FInit@CMsoGalleryUserDefault@@UEAA_NXZ` at `0x1802de228`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1802de11b`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1802de175`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1802de383`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1802de11b`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1802de175`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1802de383`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1802de0eb`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1802de145`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1802de353`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1802de0eb`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1802de145`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1802de353`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802de0d2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802de12f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802de33a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802de0d2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802de12f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802de33a`

## pseudocode

```c
void __fastcall Art::FormatObjectUIRunner::GenerateFillPatternGallery(Art::FormatObjectUIRunner *this)
{
  CMsoGalleryUserDefault **v2; // rdi
  int GalleryDataSource; // eax
  __int64 v4; // rbx
  __int64 v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned int v7; // r8d
  CMsoGalleryUserDefault *v8; // rbx
  struct IUnknown *v9; // rdx
  __int64 v10; // rcx
  void (__fastcall ***v11)(_QWORD, GUID *, char *); // rcx
  __int64 v12; // r8
  CMsoGalleryUserDefault *v13; // rbx
  __int64 v14; // rbx
  __int128 v15; // [rsp+30h] [rbp-20h] BYREF
  void (__fastcall ***v16)(_QWORD, GUID *, char *); // [rsp+40h] [rbp-10h]
  NetUI::BaseValue *v17; // [rsp+60h] [rbp+10h] BYREF

  v2 = (CMsoGalleryUserDefault **)((char *)this + 352);
  if ( !*((_QWORD *)this + 44) )
  {
    v15 = 0;
    v16 = 0;
    GalleryDataSource = MsoHrCreateGalleryDataSource((struct GalleryDSSP *)&v15, 0);
    if ( GalleryDataSource < 0 )
    {
      Ofc::CHResultException::ThrowTag(GalleryDataSource, 0x234847D9u);
      __debugbreak();
    }
    v4 = v15;
    if ( (_QWORD)v15 )
    {
      v17 = 0;
      FlexUI::FlexValue::CreateInt32(2, (struct FlexUI::FlexValueSP *)&v17);
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v4 + 48LL))(v4, 0, 131);
        if ( v17 )
          NetUI::BaseValue::Release(v17);
      }
    }
    else
    {
      MsoShipAssertTagProc(7997248);
    }
    v5 = v15;
    if ( (_QWORD)v15 )
    {
      v17 = 0;
      FlexUI::FlexValue::CreateInt32(0, (struct FlexUI::FlexValueSP *)&v17);
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v5 + 48LL))(v5, 0, 130);
        if ( v17 )
          NetUI::BaseValue::Release(v17);
      }
    }
    else
    {
      MsoShipAssertTagProc(7997248);
    }
    v8 = (CMsoGalleryUserDefault *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x128, v6, v7);
    if ( !v8 )
    {
      v8 = 0;
LABEL_22:
      if ( *v2 != v8 )
        Ofc::TCntPtr<Art::TextAlignGalleryUser>::Assign(v2, v8);
      if ( !CMsoGalleryUserDefault::FInit(*v2) )
      {
        v10 = 591939542;
        goto LABEL_45;
      }
      v11 = (void (__fastcall ***)(_QWORD, GUID *, char *))v15;
      if ( (void (__fastcall ***)(_QWORD, GUID *, char *))v15 == v16 )
      {
        v12 = *((_QWORD *)&v15 + 1);
        if ( !*((_QWORD *)&v15 + 1) )
        {
LABEL_34:
          v13 = *v2;
          if ( v11 == v16 )
          {
            if ( !v12 )
              goto LABEL_43;
          }
          else
          {
            if ( !v11 )
            {
LABEL_43:
              Art::FormatObjectUIRunner::FSetDataSource<FlexUI::IDataSource *>(this, 164, v11);
              v14 = v15;
              if ( (_QWORD)v15 )
              {
                v17 = 0;
                FlexUI::FlexValue::CreateInt32(6, (struct FlexUI::FlexValueSP *)&v17);
                if ( v17 )
                {
                  (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v14 + 48LL))(v14, 0, 138);
                  if ( v17 )
                    NetUI::BaseValue::Release(v17);
                }
                goto LABEL_49;
              }
              v10 = 7997248;
LABEL_45:
              MsoShipAssertTagProc(v10);
LABEL_49:
              if ( (_QWORD)v15 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15 + 16LL))(v15);
              return;
            }
            v16 = v11;
            (**v11)(v11, &GUID_000c012f_0000_0000_c000_000000000046, (char *)&v15 + 8);
            if ( !*((_QWORD *)&v15 + 1)
              || ((*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v15 + 1) + 16LL))(*((_QWORD *)&v15 + 1)),
                  (v12 = *((_QWORD *)&v15 + 1)) == 0) )
            {
LABEL_42:
              v11 = (void (__fastcall ***)(_QWORD, GUID *, char *))v15;
              goto LABEL_43;
            }
          }
          (*(void (__fastcall **)(__int64, CMsoGalleryUserDefault *))(*(_QWORD *)v12 + 120LL))(v12, v13);
          goto LABEL_42;
        }
      }
      else
      {
        if ( !(_QWORD)v15 )
        {
LABEL_33:
          v12 = *((_QWORD *)&v15 + 1);
          goto LABEL_34;
        }
        v16 = (void (__fastcall ***)(_QWORD, GUID *, char *))v15;
        (**(void (__fastcall ***)(_QWORD, GUID *, char *))v15)(
          v15,
          &GUID_000c012f_0000_0000_c000_000000000046,
          (char *)&v15 + 8);
        v12 = *((_QWORD *)&v15 + 1);
        if ( !*((_QWORD *)&v15 + 1)
          || ((*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v15 + 1) + 16LL))(*((_QWORD *)&v15 + 1)),
              (v12 = *((_QWORD *)&v15 + 1)) == 0) )
        {
          v11 = (void (__fastcall ***)(_QWORD, GUID *, char *))v15;
          goto LABEL_34;
        }
      }
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 512LL))(v12, 0);
      v11 = (void (__fastcall ***)(_QWORD, GUID *, char *))v15;
      goto LABEL_33;
    }
    if ( (void (__fastcall ***)(_QWORD, GUID *, char *))v15 != v16 && (_QWORD)v15 )
    {
      v16 = (void (__fastcall ***)(_QWORD, GUID *, char *))v15;
      (**(void (__fastcall ***)(_QWORD, GUID *, char *))v15)(
        v15,
        &GUID_000c012f_0000_0000_c000_000000000046,
        (char *)&v15 + 8);
      v9 = (struct IUnknown *)*((_QWORD *)&v15 + 1);
      if ( !*((_QWORD *)&v15 + 1) )
      {
LABEL_20:
        CMsoPatternGalleryUser::CMsoPatternGalleryUser(v8, v9, 1, 0);
        *(_QWORD *)v8 = &Art::FmtObjPatternGalleryControlUser::`vftable'{for `IGalleryDataSource'};
        *((_QWORD *)v8 + 4) = &Art::FmtObjPatternGalleryControlUser::`vftable'{for `MsoReoccurringIdleTaskNoRefCountDeprecated'};
        *((_QWORD *)v8 + 17) = &Art::CrtDataLabelShapesGalleryControlUser::`vftable'{for `IMsoClipboardListener'};
        *((_QWORD *)v8 + 36) = this;
        goto LABEL_22;
      }
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v15 + 1) + 16LL))(*((_QWORD *)&v15 + 1));
    }
    v9 = (struct IUnknown *)*((_QWORD *)&v15 + 1);
    goto LABEL_20;
  }
}

```

## disassembly

```asm
0x1802de06c  mov     [rsp-8+arg_8], rbx
0x1802de071  mov     [rsp-8+arg_10], rsi
0x1802de076  mov     [rsp-8+arg_18], rdi
0x1802de07b  push    rbp
0x1802de07c  mov     rbp, rsp
0x1802de07f  sub     rsp, 50h
0x1802de083  mov     rsi, rcx
0x1802de086  lea     rdi, [rcx+160h]
0x1802de08d  cmp     qword ptr [rdi], 0
0x1802de091  jnz     loc_1802DE3A0
0x1802de097  xorps   xmm0, xmm0
0x1802de09a  movdqu  [rbp+var_20], xmm0
0x1802de09f  mov     [rbp+var_10], 0
0x1802de0a7  xor     edx, edx
0x1802de0a9  lea     rcx, [rbp+var_20]
0x1802de0ad  call    cs:__imp_?MsoHrCreateGalleryDataSource@@YAJAEAVGalleryDSSP@@PEAUIDataSource@OfficeSpace@@@Z; MsoHrCreateGalleryDataSource(GalleryDSSP &,OfficeSpace::IDataSource *)
0x1802de0b3  test    eax, eax
0x1802de0b5  jns     short loc_1802DE0C4
0x1802de0b7  mov     edx, 234847D9h; unsigned int
0x1802de0bc  mov     ecx, eax; int
0x1802de0be  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1802de0c3  int     3; Trap to Debugger
0x1802de0c4  mov     rbx, qword ptr [rbp+var_20]
0x1802de0c8  test    rbx, rbx
0x1802de0cb  jnz     short loc_1802DE0DA
0x1802de0cd  mov     ecx, 7A0740h
0x1802de0d2  call    cs:__imp_MsoShipAssertTagProc
0x1802de0d8  jmp     short loc_1802DE121
0x1802de0da  mov     [rbp+arg_0], 0
0x1802de0e2  lea     rdx, [rbp+arg_0]
0x1802de0e6  mov     ecx, 2
0x1802de0eb  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1802de0f1  mov     r9, [rbp+arg_0]
0x1802de0f5  test    r9, r9
0x1802de0f8  jz      short loc_1802DE121
0x1802de0fa  mov     rax, [rbx]
0x1802de0fd  xor     edx, edx
0x1802de0ff  mov     r8d, 83h
0x1802de105  mov     rcx, rbx
0x1802de108  mov     rax, [rax+30h]
0x1802de10c  call    cs:__guard_dispatch_icall_fptr
0x1802de112  mov     rcx, [rbp+arg_0]
0x1802de116  test    rcx, rcx
0x1802de119  jz      short loc_1802DE121
0x1802de11b  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1802de121  mov     rbx, qword ptr [rbp+var_20]
0x1802de125  test    rbx, rbx
0x1802de128  jnz     short loc_1802DE137
0x1802de12a  mov     ecx, 7A0740h
0x1802de12f  call    cs:__imp_MsoShipAssertTagProc
0x1802de135  jmp     short loc_1802DE17B
0x1802de137  mov     [rbp+arg_0], 0
0x1802de13f  lea     rdx, [rbp+arg_0]
0x1802de143  xor     ecx, ecx
0x1802de145  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1802de14b  mov     r9, [rbp+arg_0]
0x1802de14f  test    r9, r9
0x1802de152  jz      short loc_1802DE17B
0x1802de154  mov     rax, [rbx]
0x1802de157  xor     edx, edx
0x1802de159  mov     r8d, 82h
0x1802de15f  mov     rcx, rbx
0x1802de162  mov     rax, [rax+30h]
0x1802de166  call    cs:__guard_dispatch_icall_fptr
0x1802de16c  mov     rcx, [rbp+arg_0]
0x1802de170  test    rcx, rcx
0x1802de173  jz      short loc_1802DE17B
0x1802de175  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1802de17b  mov     ecx, 128h; this
0x1802de180  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1802de185  mov     rbx, rax
0x1802de188  test    rax, rax
0x1802de18b  jz      loc_1802DE213
0x1802de191  mov     rcx, qword ptr [rbp+var_20]
0x1802de195  cmp     rcx, [rbp+var_10]
0x1802de199  jz      short loc_1802DE1D4
0x1802de19b  test    rcx, rcx
0x1802de19e  jz      short loc_1802DE1D4
0x1802de1a0  mov     [rbp+var_10], rcx
0x1802de1a4  mov     rax, [rcx]
0x1802de1a7  lea     r8, [rbp+var_20+8]
0x1802de1ab  lea     rdx, _GUID_000c012f_0000_0000_c000_000000000046
0x1802de1b2  mov     rax, [rax]
0x1802de1b5  call    cs:__guard_dispatch_icall_fptr
0x1802de1bb  mov     rdx, qword ptr [rbp+var_20+8]
0x1802de1bf  test    rdx, rdx
0x1802de1c2  jz      short loc_1802DE1D8
0x1802de1c4  mov     rax, [rdx]
0x1802de1c7  mov     rcx, rdx
0x1802de1ca  mov     rax, [rax+10h]
0x1802de1ce  call    cs:__guard_dispatch_icall_fptr
0x1802de1d4  mov     rdx, qword ptr [rbp+var_20+8]
0x1802de1d8  xor     r9d, r9d
0x1802de1db  mov     r8b, 1
0x1802de1de  mov     rcx, rbx
0x1802de1e1  call    cs:__imp_??0CMsoPatternGalleryUser@@QEAA@PEAUIUnknown@@_N1@Z; CMsoPatternGalleryUser::CMsoPatternGalleryUser(IUnknown *,bool,bool)
0x1802de1e7  lea     rax, ??_7FmtObjPatternGalleryControlUser@Art@@6BIGalleryDataSource@@@; const Art::FmtObjPatternGalleryControlUser::`vftable'{for `IGalleryDataSource'}
0x1802de1ee  mov     [rbx], rax
0x1802de1f1  lea     rax, ??_7FmtObjPatternGalleryControlUser@Art@@6BMsoReoccurringIdleTaskNoRefCountDeprecated@@@; const Art::FmtObjPatternGalleryControlUser::`vftable'{for `MsoReoccurringIdleTaskNoRefCountDeprecated'}
0x1802de1f8  mov     [rbx+20h], rax
0x1802de1fc  lea     rax, ??_7CrtDataLabelShapesGalleryControlUser@Art@@6BIMsoClipboardListener@@@; const Art::CrtDataLabelShapesGalleryControlUser::`vftable'{for `IMsoClipboardListener'}
0x1802de203  mov     [rbx+88h], rax
0x1802de20a  mov     [rbx+120h], rsi
0x1802de211  jmp     short loc_1802DE215
0x1802de213  xor     ebx, ebx
0x1802de215  cmp     [rdi], rbx
0x1802de218  jz      short loc_1802DE225
0x1802de21a  mov     rdx, rbx
0x1802de21d  mov     rcx, rdi
0x1802de220  call    ?Assign@?$TCntPtr@VTextAlignGalleryUser@Art@@@Ofc@@AEAAXPEAVTextAlignGalleryUser@Art@@@Z; Ofc::TCntPtr<Art::TextAlignGalleryUser>::Assign(Art::TextAlignGalleryUser *)
0x1802de225  mov     rcx, [rdi]
0x1802de228  call    cs:__imp_?FInit@CMsoGalleryUserDefault@@UEAA_NXZ; CMsoGalleryUserDefault::FInit(void)
0x1802de22e  test    al, al
0x1802de230  jnz     short loc_1802DE23C
0x1802de232  mov     ecx, 234847D6h
0x1802de237  jmp     loc_1802DE33A
0x1802de23c  mov     rcx, qword ptr [rbp+var_20]
0x1802de240  cmp     rcx, [rbp+var_10]
0x1802de244  jnz     short loc_1802DE251
0x1802de246  mov     r8, qword ptr [rbp+var_20+8]
0x1802de24a  test    r8, r8
0x1802de24d  jnz     short loc_1802DE293
0x1802de24f  jmp     short loc_1802DE2B0
0x1802de251  test    rcx, rcx
0x1802de254  jz      short loc_1802DE2AC
0x1802de256  mov     [rbp+var_10], rcx
0x1802de25a  mov     rax, [rcx]
0x1802de25d  lea     r8, [rbp+var_20+8]
0x1802de261  lea     rdx, _GUID_000c012f_0000_0000_c000_000000000046
0x1802de268  mov     rax, [rax]
0x1802de26b  call    cs:__guard_dispatch_icall_fptr
0x1802de271  mov     r8, qword ptr [rbp+var_20+8]
0x1802de275  test    r8, r8
0x1802de278  jz      short loc_1802DE2C0
0x1802de27a  mov     rax, [r8]
0x1802de27d  mov     rcx, r8
0x1802de280  mov     rax, [rax+10h]
0x1802de284  call    cs:__guard_dispatch_icall_fptr
0x1802de28a  mov     r8, qword ptr [rbp+var_20+8]
0x1802de28e  test    r8, r8
0x1802de291  jz      short loc_1802DE2C0
0x1802de293  mov     rax, [r8]
0x1802de296  xor     edx, edx
0x1802de298  mov     rcx, r8
0x1802de29b  mov     rax, [rax+200h]
0x1802de2a2  call    cs:__guard_dispatch_icall_fptr
0x1802de2a8  mov     rcx, qword ptr [rbp+var_20]
0x1802de2ac  mov     r8, qword ptr [rbp+var_20+8]
0x1802de2b0  mov     rbx, [rdi]
0x1802de2b3  cmp     rcx, [rbp+var_10]
0x1802de2b7  jnz     short loc_1802DE2C6
0x1802de2b9  test    r8, r8
0x1802de2bc  jnz     short loc_1802DE305
0x1802de2be  jmp     short loc_1802DE31C
0x1802de2c0  mov     rcx, qword ptr [rbp+var_20]
0x1802de2c4  jmp     short loc_1802DE2B0
0x1802de2c6  test    rcx, rcx
0x1802de2c9  jz      short loc_1802DE31C
0x1802de2cb  mov     [rbp+var_10], rcx
0x1802de2cf  mov     rax, [rcx]
0x1802de2d2  lea     r8, [rbp+var_20+8]
0x1802de2d6  lea     rdx, _GUID_000c012f_0000_0000_c000_000000000046
0x1802de2dd  mov     rax, [rax]
0x1802de2e0  call    cs:__guard_dispatch_icall_fptr
0x1802de2e6  mov     rcx, qword ptr [rbp+var_20+8]
0x1802de2ea  test    rcx, rcx
0x1802de2ed  jz      short loc_1802DE318
0x1802de2ef  mov     rax, [rcx]
0x1802de2f2  mov     rax, [rax+10h]
0x1802de2f6  call    cs:__guard_dispatch_icall_fptr
0x1802de2fc  mov     r8, qword ptr [rbp+var_20+8]
0x1802de300  test    r8, r8
0x1802de303  jz      short loc_1802DE318
0x1802de305  mov     rax, [r8]
0x1802de308  mov     rdx, rbx
0x1802de30b  mov     rcx, r8
0x1802de30e  mov     rax, [rax+78h]
0x1802de312  call    cs:__guard_dispatch_icall_fptr
0x1802de318  mov     rcx, qword ptr [rbp+var_20]
0x1802de31c  mov     r8, rcx
0x1802de31f  mov     edx, 0A4h
0x1802de324  mov     rcx, rsi
0x1802de327  call    ??$FSetDataSource@PEAUIDataSource@FlexUI@@@FormatObjectUIRunner@Art@@QEAA_NW4OartFormatObjectDlgParamsPropertyId@OartFormatObjectDlgParams@@PEAUIDataSource@FlexUI@@@Z; Art::FormatObjectUIRunner::FSetDataSource<FlexUI::IDataSource *>(OartFormatObjectDlgParams::OartFormatObjectDlgParamsPropertyId,FlexUI::IDataSource *)
0x1802de32c  mov     rbx, qword ptr [rbp+var_20]
0x1802de330  test    rbx, rbx
0x1802de333  jnz     short loc_1802DE342
0x1802de335  mov     ecx, 7A0740h
0x1802de33a  call    cs:__imp_MsoShipAssertTagProc
0x1802de340  jmp     short loc_1802DE38A
0x1802de342  mov     [rbp+arg_0], 0
0x1802de34a  lea     rdx, [rbp+arg_0]
0x1802de34e  mov     ecx, 6
0x1802de353  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1802de359  mov     r9, [rbp+arg_0]
0x1802de35d  test    r9, r9
0x1802de360  jz      short loc_1802DE38A
0x1802de362  mov     rax, [rbx]
0x1802de365  xor     edx, edx
0x1802de367  mov     r8d, 8Ah
0x1802de36d  mov     rcx, rbx
0x1802de370  mov     rax, [rax+30h]
0x1802de374  call    cs:__guard_dispatch_icall_fptr
0x1802de37a  mov     rcx, [rbp+arg_0]
0x1802de37e  test    rcx, rcx
0x1802de381  jz      short loc_1802DE38A
0x1802de383  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1802de389  nop
0x1802de38a  mov     rcx, qword ptr [rbp+var_20]
0x1802de38e  test    rcx, rcx
0x1802de391  jz      short loc_1802DE3A0
0x1802de393  mov     rax, [rcx]
0x1802de396  mov     rax, [rax+10h]
0x1802de39a  call    cs:__guard_dispatch_icall_fptr
0x1802de3a0  mov     rbx, [rsp+50h+arg_8]
0x1802de3a5  mov     rsi, [rsp+50h+arg_10]
0x1802de3aa  mov     rdi, [rsp+50h+arg_18]
0x1802de3af  add     rsp, 50h
0x1802de3b3  pop     rbp
0x1802de3b4  retn
```
