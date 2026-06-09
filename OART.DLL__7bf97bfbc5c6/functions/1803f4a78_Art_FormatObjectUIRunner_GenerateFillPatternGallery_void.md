# Art::FormatObjectUIRunner::GenerateFillPatternGallery(void)

- ea: `0x1803f4a78`
- end: `0x1803f4dc1`
- name: `?GenerateFillPatternGallery@FormatObjectUIRunner@Art@@IEAAXXZ`
- size: `841`
- prototype: `void __fastcall(Art::FormatObjectUIRunner *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1803f3ed4`

## callees

- `0x1800659a0`
- `0x180071720`
- `0x1801b09dc`
- `0x180218294`
- `0x1803f4a78`
- `0x1803f5008`

## import_xrefs

- `MSO!__imp_??0CMsoPatternGalleryUser@@QEAA@PEAUIUnknown@@_N1@Z` at `0x1803f4bed`
- `MSO!__imp_??0CMsoPatternGalleryUser@@QEAA@PEAUIUnknown@@_N1@Z` at `0x1803f4bed`
- `Mso98Win32Client!__imp_?MsoHrCreateGalleryDataSource@@YAJAEAVGalleryDSSP@@PEAUIDataSource@OfficeSpace@@@Z` at `0x1803f4ab9`
- `Mso98Win32Client!__imp_?MsoHrCreateGalleryDataSource@@YAJAEAVGalleryDSSP@@PEAUIDataSource@OfficeSpace@@@Z` at `0x1803f4ab9`
- `Mso98Win32Client!__imp_?FInit@CMsoGalleryUserDefault@@UEAA_NXZ` at `0x1803f4c34`
- `Mso98Win32Client!__imp_?FInit@CMsoGalleryUserDefault@@UEAA_NXZ` at `0x1803f4c34`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1803f4b27`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1803f4b81`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1803f4d8f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1803f4b27`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1803f4b81`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1803f4d8f`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1803f4af7`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1803f4b51`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1803f4d5f`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1803f4af7`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1803f4b51`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1803f4d5f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803f4ade`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803f4b3b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803f4d46`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803f4ade`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803f4b3b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803f4d46`

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
0x1803f4a78  mov     [rsp-8+arg_8], rbx
0x1803f4a7d  mov     [rsp-8+arg_10], rsi
0x1803f4a82  mov     [rsp-8+arg_18], rdi
0x1803f4a87  push    rbp
0x1803f4a88  mov     rbp, rsp
0x1803f4a8b  sub     rsp, 50h
0x1803f4a8f  mov     rsi, rcx
0x1803f4a92  lea     rdi, [rcx+160h]
0x1803f4a99  cmp     qword ptr [rdi], 0
0x1803f4a9d  jnz     loc_1803F4DAC
0x1803f4aa3  xorps   xmm0, xmm0
0x1803f4aa6  movdqu  [rbp+var_20], xmm0
0x1803f4aab  mov     [rbp+var_10], 0
0x1803f4ab3  xor     edx, edx
0x1803f4ab5  lea     rcx, [rbp+var_20]
0x1803f4ab9  call    cs:__imp_?MsoHrCreateGalleryDataSource@@YAJAEAVGalleryDSSP@@PEAUIDataSource@OfficeSpace@@@Z; MsoHrCreateGalleryDataSource(GalleryDSSP &,OfficeSpace::IDataSource *)
0x1803f4abf  test    eax, eax
0x1803f4ac1  jns     short loc_1803F4AD0
0x1803f4ac3  mov     edx, 234847D9h; unsigned int
0x1803f4ac8  mov     ecx, eax; int
0x1803f4aca  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1803f4acf  int     3; Trap to Debugger
0x1803f4ad0  mov     rbx, qword ptr [rbp+var_20]
0x1803f4ad4  test    rbx, rbx
0x1803f4ad7  jnz     short loc_1803F4AE6
0x1803f4ad9  mov     ecx, 7A0740h
0x1803f4ade  call    cs:__imp_MsoShipAssertTagProc
0x1803f4ae4  jmp     short loc_1803F4B2D
0x1803f4ae6  mov     [rbp+arg_0], 0
0x1803f4aee  lea     rdx, [rbp+arg_0]
0x1803f4af2  mov     ecx, 2
0x1803f4af7  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1803f4afd  mov     r9, [rbp+arg_0]
0x1803f4b01  test    r9, r9
0x1803f4b04  jz      short loc_1803F4B2D
0x1803f4b06  mov     rax, [rbx]
0x1803f4b09  xor     edx, edx
0x1803f4b0b  mov     r8d, 83h
0x1803f4b11  mov     rcx, rbx
0x1803f4b14  mov     rax, [rax+30h]
0x1803f4b18  call    cs:__guard_dispatch_icall_fptr
0x1803f4b1e  mov     rcx, [rbp+arg_0]
0x1803f4b22  test    rcx, rcx
0x1803f4b25  jz      short loc_1803F4B2D
0x1803f4b27  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1803f4b2d  mov     rbx, qword ptr [rbp+var_20]
0x1803f4b31  test    rbx, rbx
0x1803f4b34  jnz     short loc_1803F4B43
0x1803f4b36  mov     ecx, 7A0740h
0x1803f4b3b  call    cs:__imp_MsoShipAssertTagProc
0x1803f4b41  jmp     short loc_1803F4B87
0x1803f4b43  mov     [rbp+arg_0], 0
0x1803f4b4b  lea     rdx, [rbp+arg_0]
0x1803f4b4f  xor     ecx, ecx
0x1803f4b51  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1803f4b57  mov     r9, [rbp+arg_0]
0x1803f4b5b  test    r9, r9
0x1803f4b5e  jz      short loc_1803F4B87
0x1803f4b60  mov     rax, [rbx]
0x1803f4b63  xor     edx, edx
0x1803f4b65  mov     r8d, 82h
0x1803f4b6b  mov     rcx, rbx
0x1803f4b6e  mov     rax, [rax+30h]
0x1803f4b72  call    cs:__guard_dispatch_icall_fptr
0x1803f4b78  mov     rcx, [rbp+arg_0]
0x1803f4b7c  test    rcx, rcx
0x1803f4b7f  jz      short loc_1803F4B87
0x1803f4b81  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1803f4b87  mov     ecx, 128h; this
0x1803f4b8c  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1803f4b91  mov     rbx, rax
0x1803f4b94  test    rax, rax
0x1803f4b97  jz      loc_1803F4C1F
0x1803f4b9d  mov     rcx, qword ptr [rbp+var_20]
0x1803f4ba1  cmp     rcx, [rbp+var_10]
0x1803f4ba5  jz      short loc_1803F4BE0
0x1803f4ba7  test    rcx, rcx
0x1803f4baa  jz      short loc_1803F4BE0
0x1803f4bac  mov     [rbp+var_10], rcx
0x1803f4bb0  mov     rax, [rcx]
0x1803f4bb3  lea     r8, [rbp+var_20+8]
0x1803f4bb7  lea     rdx, _GUID_000c012f_0000_0000_c000_000000000046
0x1803f4bbe  mov     rax, [rax]
0x1803f4bc1  call    cs:__guard_dispatch_icall_fptr
0x1803f4bc7  mov     rdx, qword ptr [rbp+var_20+8]
0x1803f4bcb  test    rdx, rdx
0x1803f4bce  jz      short loc_1803F4BE4
0x1803f4bd0  mov     rax, [rdx]
0x1803f4bd3  mov     rcx, rdx
0x1803f4bd6  mov     rax, [rax+10h]
0x1803f4bda  call    cs:__guard_dispatch_icall_fptr
0x1803f4be0  mov     rdx, qword ptr [rbp+var_20+8]
0x1803f4be4  xor     r9d, r9d
0x1803f4be7  mov     r8b, 1
0x1803f4bea  mov     rcx, rbx
0x1803f4bed  call    cs:__imp_??0CMsoPatternGalleryUser@@QEAA@PEAUIUnknown@@_N1@Z; CMsoPatternGalleryUser::CMsoPatternGalleryUser(IUnknown *,bool,bool)
0x1803f4bf3  lea     rax, ??_7FmtObjPatternGalleryControlUser@Art@@6BIGalleryDataSource@@@; const Art::FmtObjPatternGalleryControlUser::`vftable'{for `IGalleryDataSource'}
0x1803f4bfa  mov     [rbx], rax
0x1803f4bfd  lea     rax, ??_7FmtObjPatternGalleryControlUser@Art@@6BMsoReoccurringIdleTaskNoRefCountDeprecated@@@; const Art::FmtObjPatternGalleryControlUser::`vftable'{for `MsoReoccurringIdleTaskNoRefCountDeprecated'}
0x1803f4c04  mov     [rbx+20h], rax
0x1803f4c08  lea     rax, ??_7CrtDataLabelShapesGalleryControlUser@Art@@6BIMsoClipboardListener@@@; const Art::CrtDataLabelShapesGalleryControlUser::`vftable'{for `IMsoClipboardListener'}
0x1803f4c0f  mov     [rbx+88h], rax
0x1803f4c16  mov     [rbx+120h], rsi
0x1803f4c1d  jmp     short loc_1803F4C21
0x1803f4c1f  xor     ebx, ebx
0x1803f4c21  cmp     [rdi], rbx
0x1803f4c24  jz      short loc_1803F4C31
0x1803f4c26  mov     rdx, rbx
0x1803f4c29  mov     rcx, rdi
0x1803f4c2c  call    ?Assign@?$TCntPtr@VTextAlignGalleryUser@Art@@@Ofc@@AEAAXPEAVTextAlignGalleryUser@Art@@@Z; Ofc::TCntPtr<Art::TextAlignGalleryUser>::Assign(Art::TextAlignGalleryUser *)
0x1803f4c31  mov     rcx, [rdi]
0x1803f4c34  call    cs:__imp_?FInit@CMsoGalleryUserDefault@@UEAA_NXZ; CMsoGalleryUserDefault::FInit(void)
0x1803f4c3a  test    al, al
0x1803f4c3c  jnz     short loc_1803F4C48
0x1803f4c3e  mov     ecx, 234847D6h
0x1803f4c43  jmp     loc_1803F4D46
0x1803f4c48  mov     rcx, qword ptr [rbp+var_20]
0x1803f4c4c  cmp     rcx, [rbp+var_10]
0x1803f4c50  jnz     short loc_1803F4C5D
0x1803f4c52  mov     r8, qword ptr [rbp+var_20+8]
0x1803f4c56  test    r8, r8
0x1803f4c59  jnz     short loc_1803F4C9F
0x1803f4c5b  jmp     short loc_1803F4CBC
0x1803f4c5d  test    rcx, rcx
0x1803f4c60  jz      short loc_1803F4CB8
0x1803f4c62  mov     [rbp+var_10], rcx
0x1803f4c66  mov     rax, [rcx]
0x1803f4c69  lea     r8, [rbp+var_20+8]
0x1803f4c6d  lea     rdx, _GUID_000c012f_0000_0000_c000_000000000046
0x1803f4c74  mov     rax, [rax]
0x1803f4c77  call    cs:__guard_dispatch_icall_fptr
0x1803f4c7d  mov     r8, qword ptr [rbp+var_20+8]
0x1803f4c81  test    r8, r8
0x1803f4c84  jz      short loc_1803F4CCC
0x1803f4c86  mov     rax, [r8]
0x1803f4c89  mov     rcx, r8
0x1803f4c8c  mov     rax, [rax+10h]
0x1803f4c90  call    cs:__guard_dispatch_icall_fptr
0x1803f4c96  mov     r8, qword ptr [rbp+var_20+8]
0x1803f4c9a  test    r8, r8
0x1803f4c9d  jz      short loc_1803F4CCC
0x1803f4c9f  mov     rax, [r8]
0x1803f4ca2  xor     edx, edx
0x1803f4ca4  mov     rcx, r8
0x1803f4ca7  mov     rax, [rax+200h]
0x1803f4cae  call    cs:__guard_dispatch_icall_fptr
0x1803f4cb4  mov     rcx, qword ptr [rbp+var_20]
0x1803f4cb8  mov     r8, qword ptr [rbp+var_20+8]
0x1803f4cbc  mov     rbx, [rdi]
0x1803f4cbf  cmp     rcx, [rbp+var_10]
0x1803f4cc3  jnz     short loc_1803F4CD2
0x1803f4cc5  test    r8, r8
0x1803f4cc8  jnz     short loc_1803F4D11
0x1803f4cca  jmp     short loc_1803F4D28
0x1803f4ccc  mov     rcx, qword ptr [rbp+var_20]
0x1803f4cd0  jmp     short loc_1803F4CBC
0x1803f4cd2  test    rcx, rcx
0x1803f4cd5  jz      short loc_1803F4D28
0x1803f4cd7  mov     [rbp+var_10], rcx
0x1803f4cdb  mov     rax, [rcx]
0x1803f4cde  lea     r8, [rbp+var_20+8]
0x1803f4ce2  lea     rdx, _GUID_000c012f_0000_0000_c000_000000000046
0x1803f4ce9  mov     rax, [rax]
0x1803f4cec  call    cs:__guard_dispatch_icall_fptr
0x1803f4cf2  mov     rcx, qword ptr [rbp+var_20+8]
0x1803f4cf6  test    rcx, rcx
0x1803f4cf9  jz      short loc_1803F4D24
0x1803f4cfb  mov     rax, [rcx]
0x1803f4cfe  mov     rax, [rax+10h]
0x1803f4d02  call    cs:__guard_dispatch_icall_fptr
0x1803f4d08  mov     r8, qword ptr [rbp+var_20+8]
0x1803f4d0c  test    r8, r8
0x1803f4d0f  jz      short loc_1803F4D24
0x1803f4d11  mov     rax, [r8]
0x1803f4d14  mov     rdx, rbx
0x1803f4d17  mov     rcx, r8
0x1803f4d1a  mov     rax, [rax+78h]
0x1803f4d1e  call    cs:__guard_dispatch_icall_fptr
0x1803f4d24  mov     rcx, qword ptr [rbp+var_20]
0x1803f4d28  mov     r8, rcx
0x1803f4d2b  mov     edx, 0A4h
0x1803f4d30  mov     rcx, rsi
0x1803f4d33  call    ??$FSetDataSource@PEAUIDataSource@FlexUI@@@FormatObjectUIRunner@Art@@QEAA_NW4OartFormatObjectDlgParamsPropertyId@OartFormatObjectDlgParams@@PEAUIDataSource@FlexUI@@@Z; Art::FormatObjectUIRunner::FSetDataSource<FlexUI::IDataSource *>(OartFormatObjectDlgParams::OartFormatObjectDlgParamsPropertyId,FlexUI::IDataSource *)
0x1803f4d38  mov     rbx, qword ptr [rbp+var_20]
0x1803f4d3c  test    rbx, rbx
0x1803f4d3f  jnz     short loc_1803F4D4E
0x1803f4d41  mov     ecx, 7A0740h
0x1803f4d46  call    cs:__imp_MsoShipAssertTagProc
0x1803f4d4c  jmp     short loc_1803F4D96
0x1803f4d4e  mov     [rbp+arg_0], 0
0x1803f4d56  lea     rdx, [rbp+arg_0]
0x1803f4d5a  mov     ecx, 6
0x1803f4d5f  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1803f4d65  mov     r9, [rbp+arg_0]
0x1803f4d69  test    r9, r9
0x1803f4d6c  jz      short loc_1803F4D96
0x1803f4d6e  mov     rax, [rbx]
0x1803f4d71  xor     edx, edx
0x1803f4d73  mov     r8d, 8Ah
0x1803f4d79  mov     rcx, rbx
0x1803f4d7c  mov     rax, [rax+30h]
0x1803f4d80  call    cs:__guard_dispatch_icall_fptr
0x1803f4d86  mov     rcx, [rbp+arg_0]
0x1803f4d8a  test    rcx, rcx
0x1803f4d8d  jz      short loc_1803F4D96
0x1803f4d8f  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1803f4d95  nop
0x1803f4d96  mov     rcx, qword ptr [rbp+var_20]
0x1803f4d9a  test    rcx, rcx
0x1803f4d9d  jz      short loc_1803F4DAC
0x1803f4d9f  mov     rax, [rcx]
0x1803f4da2  mov     rax, [rax+10h]
0x1803f4da6  call    cs:__guard_dispatch_icall_fptr
0x1803f4dac  mov     rbx, [rsp+50h+arg_8]
0x1803f4db1  mov     rsi, [rsp+50h+arg_10]
0x1803f4db6  mov     rdi, [rsp+50h+arg_18]
0x1803f4dbb  add     rsp, 50h
0x1803f4dbf  pop     rbp
0x1803f4dc0  retn
```
