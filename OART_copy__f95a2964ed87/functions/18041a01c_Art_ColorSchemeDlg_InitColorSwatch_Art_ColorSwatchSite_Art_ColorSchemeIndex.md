# Art::ColorSchemeDlg::InitColorSwatch(Art::ColorSwatchSite &,Art::ColorSchemeIndex)

- ea: `0x18041a01c`
- end: `0x18041a4a2`
- name: `?InitColorSwatch@ColorSchemeDlg@Art@@AEAAXAEAVColorSwatchSite@2@W4ColorSchemeIndex@2@@Z`
- size: `1158`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180419e38`

## callees

- `0x18000e80c`
- `0x180028b00`
- `0x180144e90`
- `0x180279050`
- `0x1802d56d0`
- `0x1802e0038`
- `0x18041a01c`
- `0x1804747dc`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoCreateColorGalleryAndUser@@YAXAEAPEAVIMsoColorGallerySite@@HAEAVGalleryDSSP@@AEAPEAVCMsoGalleryUserDefault@@@Z` at `0x18041a061`
- `Mso98Win32Client!__imp_?MsoCreateColorGalleryAndUser@@YAXAEAPEAVIMsoColorGallerySite@@HAEAVGalleryDSSP@@AEAPEAVCMsoGalleryUserDefault@@@Z` at `0x18041a061`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x18041a0e8`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x18041a0e8`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18041a0bd`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18041a118`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18041a426`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18041a0bd`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18041a118`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18041a426`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x18041a3f9`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x18041a3f9`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x18041a08d`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x18041a08d`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a1fe`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a225`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a24c`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a273`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a29a`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a2be`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a2e5`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a32f`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a356`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a37a`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a39e`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a3c2`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a1fe`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a225`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a24c`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a273`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a29a`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a2be`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a2e5`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a32f`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a356`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a37a`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a39e`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18041a3c2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18041a0d5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18041a3e9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18041a0d5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18041a3e9`

## pseudocode

```c
void __fastcall Art::ColorSchemeDlg::InitColorSwatch(__int64 a1, __int64 a2, int a3)
{
  __int64 v6; // rsi
  __int64 v7; // rsi
  __int64 (__fastcall **v8)(_QWORD, GUID *, __int64 *); // rax
  int v9; // eax
  __int64 v10; // rdx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rcx
  HINSTANCE HinstIntl; // rax
  int v18; // r8d
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rcx
  int v31; // ebx
  int v32; // ebx
  int v33; // ebx
  int v34; // ebx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rcx
  const wchar_t **v45; // rax
  __int64 v46; // rbx
  const wchar_t *v47; // rcx
  NetUI::BaseValue *v48; // [rsp+30h] [rbp-30h] BYREF
  struct IMsoColorGallerySite *v49; // [rsp+38h] [rbp-28h] BYREF
  char v50[8]; // [rsp+40h] [rbp-20h] BYREF
  __int128 v51; // [rsp+48h] [rbp-18h] BYREF
  __int64 v52; // [rsp+58h] [rbp-8h]
  __int64 v53; // [rsp+A8h] [rbp+48h] BYREF
  struct CMsoGalleryUserDefault *v54; // [rsp+B8h] [rbp+58h] BYREF

  v51 = 0;
  v52 = 0;
  v49 = (struct IMsoColorGallerySite *)a2;
  v54 = 0;
  MsoCreateColorGalleryAndUser(&v49, 0, (struct GalleryDSSP *)&v51, &v54);
  v6 = v51;
  if ( !(_QWORD)v51 || !v54 )
  {
    Ofc::CHResultException::ThrowTag(-2147024882, 0x23485087u);
    __debugbreak();
  }
  v48 = 0;
  FlexUI::FlexValue::CreateInt32(1, (struct FlexUI::FlexValueSP *)&v48);
  if ( v48 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v6 + 48LL))(v6, 0, 130);
    if ( v48 )
      NetUI::BaseValue::Release(v48);
  }
  v7 = v51;
  if ( (_QWORD)v51 )
  {
    v48 = 0;
    FlexUI::FlexValue::CreateBoolean(1, (struct FlexUI::FlexValueSP *)&v48);
    if ( v48 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v7 + 48LL))(v7, 0, 1098907681);
      if ( v48 )
        NetUI::BaseValue::Release(v48);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  v53 = 0;
  v8 = *(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v51;
  v53 = 0;
  v9 = (*v8)(v51, &GUID_4d1d2ad5_5e40_4b17_b505_2efcc8764b05, &v53);
  if ( v9 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v9, 0x23485084u);
    __debugbreak();
  }
  *(_QWORD *)(a2 + 24) = (a1 + 40) & -(__int64)(a1 != 0);
  *(_DWORD *)(a2 + 16) = a3;
  GalleryDSSP::operator=(a2 + 32, &v51);
  Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(a2 + 56, v54);
  (*(void (__fastcall **)(struct CMsoGalleryUserDefault *))(*(_QWORD *)v54 + 184LL))(v54);
  (*(void (__fastcall **)(struct CMsoGalleryUserDefault *))(*(_QWORD *)v54 + 232LL))(v54);
  if ( a3 > 6 )
  {
    v31 = a3 - 7;
    if ( v31 )
    {
      v32 = v31 - 1;
      if ( v32 )
      {
        v33 = v32 - 1;
        if ( v33 )
        {
          v34 = v33 - 1;
          if ( v34 )
          {
            if ( v34 != 1 )
              goto LABEL_44;
            FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(
              *(_QWORD *)(a1 + 952),
              v10,
              12,
              v53);
            HinstIntl = (HINSTANCE)MsoGetHinstIntl(v36, v35);
            v18 = 836543625;
          }
          else
          {
            FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(
              *(_QWORD *)(a1 + 952),
              v10,
              11,
              v53);
            HinstIntl = (HINSTANCE)MsoGetHinstIntl(v38, v37);
            v18 = -587529113;
          }
        }
        else
        {
          FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(
            *(_QWORD *)(a1 + 952),
            v10,
            10,
            v53);
          HinstIntl = (HINSTANCE)MsoGetHinstIntl(v40, v39);
          v18 = -1508847573;
        }
      }
      else
      {
        FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(
          *(_QWORD *)(a1 + 952),
          v10,
          9,
          v53);
        HinstIntl = (HINSTANCE)MsoGetHinstIntl(v42, v41);
        v18 = -1508830734;
      }
    }
    else
    {
      FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(
        *(_QWORD *)(a1 + 952),
        v10,
        8,
        v53);
      HinstIntl = (HINSTANCE)MsoGetHinstIntl(v44, v43);
      v18 = -1508748360;
    }
  }
  else if ( a3 == 6 )
  {
    FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(
      *(_QWORD *)(a1 + 952),
      v10,
      7,
      v53);
    HinstIntl = (HINSTANCE)MsoGetHinstIntl(v30, v29);
    v18 = -1509193908;
  }
  else if ( a3 )
  {
    v11 = a3 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            if ( v14 != 1 )
              goto LABEL_44;
            FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(
              *(_QWORD *)(a1 + 952),
              v10,
              6,
              v53);
            HinstIntl = (HINSTANCE)MsoGetHinstIntl(v16, v15);
            v18 = -1509111534;
          }
          else
          {
            FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(
              *(_QWORD *)(a1 + 952),
              v10,
              5,
              v53);
            HinstIntl = (HINSTANCE)MsoGetHinstIntl(v20, v19);
            v18 = -1509094695;
          }
        }
        else
        {
          FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(
            *(_QWORD *)(a1 + 952),
            v10,
            4,
            v53);
          HinstIntl = (HINSTANCE)MsoGetHinstIntl(v22, v21);
          v18 = -973622269;
        }
      }
      else
      {
        FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(
          *(_QWORD *)(a1 + 952),
          v10,
          3,
          v53);
        HinstIntl = (HINSTANCE)MsoGetHinstIntl(v24, v23);
        v18 = -1671784207;
      }
    }
    else
    {
      FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(
        *(_QWORD *)(a1 + 952),
        v10,
        2,
        v53);
      HinstIntl = (HINSTANCE)MsoGetHinstIntl(v26, v25);
      v18 = -216768750;
    }
  }
  else
  {
    FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(
      *(_QWORD *)(a1 + 952),
      v10,
      1,
      v53);
    HinstIntl = (HINSTANCE)MsoGetHinstIntl(v28, v27);
    v18 = -602423423;
  }
  v45 = (const wchar_t **)Ofc::CVarStr::CVarStr((Ofc::CVarStr *)v50, HinstIntl, v18);
  v46 = v51;
  v47 = *v45;
  if ( (_QWORD)v51 )
  {
    v48 = 0;
    FlexUI::FlexValue::CreateString(v47, (struct FlexUI::FlexValueSP *)&v48);
    if ( v48 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v46 + 48LL))(v46, 0, 1);
      if ( v48 )
        NetUI::BaseValue::Release(v48);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  Ofc::CVarStr::ReleaseBuffer((Ofc::CVarStr *)v50);
LABEL_44:
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  if ( v54 )
    (*(void (__fastcall **)(struct CMsoGalleryUserDefault *))(*(_QWORD *)v54 + 16LL))(v54);
  if ( (_QWORD)v51 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v51 + 16LL))(v51);
}

```

## disassembly

```asm
0x18041a01c  mov     [rsp-38h+arg_0], rbx
0x18041a021  push    rbp
0x18041a022  push    rsi
0x18041a023  push    rdi
0x18041a024  push    r12
0x18041a026  push    r13
0x18041a028  push    r14
0x18041a02a  push    r15
0x18041a02c  mov     rbp, rsp
0x18041a02f  sub     rsp, 60h
0x18041a033  mov     ebx, r8d
0x18041a036  mov     r14, rdx
0x18041a039  mov     rdi, rcx
0x18041a03c  xorps   xmm0, xmm0
0x18041a03f  movdqu  [rbp+var_18], xmm0
0x18041a044  xor     r15d, r15d
0x18041a047  mov     [rbp+var_8], r15
0x18041a04b  mov     [rbp+var_28], rdx
0x18041a04f  mov     [rbp+arg_18], r15
0x18041a053  lea     r9, [rbp+arg_18]
0x18041a057  lea     r8, [rbp+var_18]
0x18041a05b  xor     edx, edx
0x18041a05d  lea     rcx, [rbp+var_28]
0x18041a061  call    cs:__imp_?MsoCreateColorGalleryAndUser@@YAXAEAPEAVIMsoColorGallerySite@@HAEAVGalleryDSSP@@AEAPEAVCMsoGalleryUserDefault@@@Z; MsoCreateColorGalleryAndUser(IMsoColorGallerySite * &,int,GalleryDSSP &,CMsoGalleryUserDefault * &)
0x18041a067  mov     rsi, qword ptr [rbp+var_18]
0x18041a06b  test    rsi, rsi
0x18041a06e  jz      loc_18041A492
0x18041a074  cmp     [rbp+arg_18], r15
0x18041a078  jz      loc_18041A492
0x18041a07e  mov     [rbp+var_30], r15
0x18041a082  lea     rdx, [rbp+var_30]
0x18041a086  lea     r13d, [r15+1]
0x18041a08a  mov     ecx, r13d
0x18041a08d  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x18041a093  mov     r9, [rbp+var_30]
0x18041a097  test    r9, r9
0x18041a09a  jz      short loc_18041A0C3
0x18041a09c  mov     rax, [rsi]
0x18041a09f  xor     edx, edx
0x18041a0a1  mov     r8d, 82h
0x18041a0a7  mov     rcx, rsi
0x18041a0aa  mov     rax, [rax+30h]
0x18041a0ae  call    cs:__guard_dispatch_icall_fptr
0x18041a0b4  mov     rcx, [rbp+var_30]
0x18041a0b8  test    rcx, rcx
0x18041a0bb  jz      short loc_18041A0C3
0x18041a0bd  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x18041a0c3  mov     rsi, qword ptr [rbp+var_18]
0x18041a0c7  mov     r12d, 7A0740h
0x18041a0cd  test    rsi, rsi
0x18041a0d0  jnz     short loc_18041A0DD
0x18041a0d2  mov     ecx, r12d
0x18041a0d5  call    cs:__imp_MsoShipAssertTagProc
0x18041a0db  jmp     short loc_18041A11E
0x18041a0dd  mov     [rbp+var_30], r15
0x18041a0e1  lea     rdx, [rbp+var_30]
0x18041a0e5  mov     cl, r13b
0x18041a0e8  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x18041a0ee  mov     r9, [rbp+var_30]
0x18041a0f2  test    r9, r9
0x18041a0f5  jz      short loc_18041A11E
0x18041a0f7  mov     rax, [rsi]
0x18041a0fa  xor     edx, edx
0x18041a0fc  mov     r8d, 41800021h
0x18041a102  mov     rcx, rsi
0x18041a105  mov     rax, [rax+30h]
0x18041a109  call    cs:__guard_dispatch_icall_fptr
0x18041a10f  mov     rcx, [rbp+var_30]
0x18041a113  test    rcx, rcx
0x18041a116  jz      short loc_18041A11E
0x18041a118  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x18041a11e  mov     [rbp+arg_8], r15
0x18041a122  mov     rcx, qword ptr [rbp+var_18]
0x18041a126  mov     rax, [rcx]
0x18041a129  mov     [rbp+arg_8], r15
0x18041a12d  lea     r8, [rbp+arg_8]
0x18041a131  lea     rdx, _GUID_4d1d2ad5_5e40_4b17_b505_2efcc8764b05
0x18041a138  mov     rax, [rax]
0x18041a13b  call    cs:__guard_dispatch_icall_fptr
0x18041a141  test    eax, eax
0x18041a143  jns     short loc_18041A152
0x18041a145  mov     edx, 23485084h; unsigned int
0x18041a14a  mov     ecx, eax; int
0x18041a14c  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18041a151  int     3; Trap to Debugger
0x18041a152  mov     rax, rdi
0x18041a155  lea     rdx, [rdi+28h]
0x18041a159  neg     rax
0x18041a15c  sbb     rcx, rcx
0x18041a15f  and     rcx, rdx
0x18041a162  mov     [r14+18h], rcx
0x18041a166  mov     [r14+10h], ebx
0x18041a16a  lea     rcx, [r14+20h]
0x18041a16e  lea     rdx, [rbp+var_18]
0x18041a172  call    ??4GalleryDSSP@@QEAAAEBV0@AEBV0@@Z; GalleryDSSP::operator=(GalleryDSSP const &)
0x18041a177  lea     rcx, [r14+38h]
0x18041a17b  mov     rdx, [rbp+arg_18]
0x18041a17f  call    ??4?$TCntPtr@VInkInputLayerNode@Dr@@@Ofc@@QEAAAEAV01@PEAVInkInputLayerNode@Dr@@@Z; Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(Dr::InkInputLayerNode *)
0x18041a184  mov     rcx, [rbp+arg_18]
0x18041a188  mov     rax, [rcx]
0x18041a18b  mov     rax, [rax+0B8h]
0x18041a192  call    cs:__guard_dispatch_icall_fptr
0x18041a198  mov     rcx, [rbp+arg_18]
0x18041a19c  mov     rax, [rcx]
0x18041a19f  mov     rax, [rax+0E8h]
0x18041a1a6  call    cs:__guard_dispatch_icall_fptr
0x18041a1ac  mov     r8d, 6
0x18041a1b2  cmp     ebx, r8d
0x18041a1b5  jg      loc_18041A2F6
0x18041a1bb  jz      loc_18041A2CF
0x18041a1c1  test    ebx, ebx
0x18041a1c3  jz      loc_18041A2AB
0x18041a1c9  sub     ebx, 1
0x18041a1cc  jz      loc_18041A284
0x18041a1d2  sub     ebx, 1
0x18041a1d5  jz      loc_18041A25D
0x18041a1db  sub     ebx, 1
0x18041a1de  jz      short loc_18041A236
0x18041a1e0  sub     ebx, 1
0x18041a1e3  jz      short loc_18041A20F
0x18041a1e5  cmp     ebx, 1
0x18041a1e8  jnz     loc_18041A436
0x18041a1ee  mov     r9, [rbp+arg_8]
0x18041a1f2  mov     rcx, [rdi+3B8h]
0x18041a1f9  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x18041a1fe  call    cs:__imp_MsoGetHinstIntl
0x18041a204  mov     r8d, 0A60CC912h
0x18041a20a  jmp     loc_18041A3CE
0x18041a20f  mov     r9, [rbp+arg_8]
0x18041a213  mov     r8d, 5
0x18041a219  mov     rcx, [rdi+3B8h]
0x18041a220  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x18041a225  call    cs:__imp_MsoGetHinstIntl
0x18041a22b  mov     r8d, 0A60D0AD9h
0x18041a231  jmp     loc_18041A3CE
0x18041a236  mov     r9, [rbp+arg_8]
0x18041a23a  mov     r8d, 4
0x18041a240  mov     rcx, [rdi+3B8h]
0x18041a247  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x18041a24c  call    cs:__imp_MsoGetHinstIntl
0x18041a252  mov     r8d, 0C5F7B403h
0x18041a258  jmp     loc_18041A3CE
0x18041a25d  mov     r9, [rbp+arg_8]
0x18041a261  mov     r8d, 3
0x18041a267  mov     rcx, [rdi+3B8h]
0x18041a26e  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x18041a273  call    cs:__imp_MsoGetHinstIntl
0x18041a279  mov     r8d, 9C5A98F1h
0x18041a27f  jmp     loc_18041A3CE
0x18041a284  mov     r9, [rbp+arg_8]
0x18041a288  mov     r8d, 2
0x18041a28e  mov     rcx, [rdi+3B8h]
0x18041a295  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x18041a29a  call    cs:__imp_MsoGetHinstIntl
0x18041a2a0  mov     r8d, 0F3145F12h
0x18041a2a6  jmp     loc_18041A3CE
0x18041a2ab  mov     r9, [rbp+arg_8]
0x18041a2af  mov     r8d, r13d
0x18041a2b2  mov     rcx, [rdi+3B8h]
0x18041a2b9  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x18041a2be  call    cs:__imp_MsoGetHinstIntl
0x18041a2c4  mov     r8d, 0DC17BF81h
0x18041a2ca  jmp     loc_18041A3CE
0x18041a2cf  mov     r9, [rbp+arg_8]
0x18041a2d3  mov     r8d, 7
0x18041a2d9  mov     rcx, [rdi+3B8h]
0x18041a2e0  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x18041a2e5  call    cs:__imp_MsoGetHinstIntl
0x18041a2eb  mov     r8d, 0A60B874Ch
0x18041a2f1  jmp     loc_18041A3CE
0x18041a2f6  sub     ebx, 7
0x18041a2f9  jz      loc_18041A3AC
0x18041a2ff  sub     ebx, 1
0x18041a302  jz      loc_18041A388
0x18041a308  sub     ebx, 1
0x18041a30b  jz      short loc_18041A364
0x18041a30d  sub     ebx, 1
0x18041a310  jz      short loc_18041A340
0x18041a312  cmp     ebx, 1
0x18041a315  jnz     loc_18041A436
0x18041a31b  mov     r9, [rbp+arg_8]
0x18041a31f  lea     r8d, [rbx+0Bh]
0x18041a323  mov     rcx, [rdi+3B8h]
0x18041a32a  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x18041a32f  call    cs:__imp_MsoGetHinstIntl
0x18041a335  mov     r8d, 31DCA489h
0x18041a33b  jmp     loc_18041A3CE
0x18041a340  mov     r9, [rbp+arg_8]
0x18041a344  mov     r8d, 0Bh
0x18041a34a  mov     rcx, [rdi+3B8h]
0x18041a351  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x18041a356  call    cs:__imp_MsoGetHinstIntl
0x18041a35c  mov     r8d, 0DCFB0467h
0x18041a362  jmp     short loc_18041A3CE
0x18041a364  mov     r9, [rbp+arg_8]
0x18041a368  mov     r8d, 0Ah
0x18041a36e  mov     rcx, [rdi+3B8h]
0x18041a375  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x18041a37a  call    cs:__imp_MsoGetHinstIntl
0x18041a380  mov     r8d, 0A610D02Bh
0x18041a386  jmp     short loc_18041A3CE
0x18041a388  mov     r9, [rbp+arg_8]
0x18041a38c  mov     r8d, 9
0x18041a392  mov     rcx, [rdi+3B8h]
0x18041a399  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x18041a39e  call    cs:__imp_MsoGetHinstIntl
0x18041a3a4  mov     r8d, 0A61111F2h
0x18041a3aa  jmp     short loc_18041A3CE
0x18041a3ac  mov     r9, [rbp+arg_8]
0x18041a3b0  mov     r8d, 8
0x18041a3b6  mov     rcx, [rdi+3B8h]
0x18041a3bd  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x18041a3c2  call    cs:__imp_MsoGetHinstIntl
0x18041a3c8  mov     r8d, 0A61253B8h; int
0x18041a3ce  mov     rdx, rax; HINSTANCE
0x18041a3d1  lea     rcx, [rbp+var_20]; this
0x18041a3d5  call    ??0CVarStr@Ofc@@QEAA@PEAUHINSTANCE__@@H@Z; Ofc::CVarStr::CVarStr(HINSTANCE__ *,int)
0x18041a3da  mov     rbx, qword ptr [rbp+var_18]
0x18041a3de  test    rbx, rbx
0x18041a3e1  mov     rcx, [rax]
0x18041a3e4  jnz     short loc_18041A3F1
0x18041a3e6  mov     ecx, r12d
0x18041a3e9  call    cs:__imp_MsoShipAssertTagProc
0x18041a3ef  jmp     short loc_18041A42C
0x18041a3f1  mov     [rbp+var_30], r15
0x18041a3f5  lea     rdx, [rbp+var_30]
0x18041a3f9  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x18041a3ff  mov     r9, [rbp+var_30]
0x18041a403  test    r9, r9
0x18041a406  jz      short loc_18041A42C
0x18041a408  mov     rax, [rbx]
0x18041a40b  mov     r8d, r13d
0x18041a40e  xor     edx, edx
0x18041a410  mov     rcx, rbx
0x18041a413  mov     rax, [rax+30h]
0x18041a417  call    cs:__guard_dispatch_icall_fptr
0x18041a41d  mov     rcx, [rbp+var_30]
0x18041a421  test    rcx, rcx
0x18041a424  jz      short loc_18041A42C
0x18041a426  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x18041a42c  lea     rcx, [rbp+var_20]; this
0x18041a430  call    ?ReleaseBuffer@CVarStr@Ofc@@AEAAXXZ; Ofc::CVarStr::ReleaseBuffer(void)
0x18041a435  nop
0x18041a436  mov     rcx, [rbp+arg_8]
0x18041a43a  test    rcx, rcx
0x18041a43d  jz      short loc_18041A44D
0x18041a43f  mov     rax, [rcx]
0x18041a442  mov     rax, [rax+10h]
0x18041a446  call    cs:__guard_dispatch_icall_fptr
0x18041a44c  nop
0x18041a44d  mov     rcx, [rbp+arg_18]
0x18041a451  test    rcx, rcx
0x18041a454  jz      short loc_18041A464
0x18041a456  mov     rax, [rcx]
0x18041a459  mov     rax, [rax+10h]
0x18041a45d  call    cs:__guard_dispatch_icall_fptr
0x18041a463  nop
0x18041a464  mov     rcx, qword ptr [rbp+var_18]
0x18041a468  test    rcx, rcx
0x18041a46b  jz      short loc_18041A47A
0x18041a46d  mov     rax, [rcx]
0x18041a470  mov     rax, [rax+10h]
0x18041a474  call    cs:__guard_dispatch_icall_fptr
0x18041a47a  mov     rbx, [rsp+60h+arg_0]
0x18041a482  add     rsp, 60h
0x18041a486  pop     r15
0x18041a488  pop     r14
0x18041a48a  pop     r13
0x18041a48c  pop     r12
0x18041a48e  pop     rdi
0x18041a48f  pop     rsi
0x18041a490  pop     rbp
0x18041a491  retn
0x18041a492  mov     edx, 23485087h; unsigned int
0x18041a497  mov     ecx, 8007000Eh; int
0x18041a49c  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18041a4a1  int     3; Trap to Debugger
```
