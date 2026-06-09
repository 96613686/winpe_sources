# Art::ColorSchemeDlg::InitColorSwatch(Art::ColorSwatchSite &,Art::ColorSchemeIndex)

- ea: `0x180477d38`
- end: `0x1804781be`
- name: `?InitColorSwatch@ColorSchemeDlg@Art@@AEAAXAEAVColorSwatchSite@2@W4ColorSchemeIndex@2@@Z`
- size: `1158`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180477b60`

## callees

- `0x18000d920`
- `0x18001daf0`
- `0x180071720`
- `0x1801b09dc`
- `0x1802fb8e0`
- `0x1803f5024`
- `0x18047750c`
- `0x180477d38`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoCreateColorGalleryAndUser@@YAXAEAPEAVIMsoColorGallerySite@@HAEAVGalleryDSSP@@AEAPEAVCMsoGalleryUserDefault@@@Z` at `0x180477d7d`
- `Mso98Win32Client!__imp_?MsoCreateColorGalleryAndUser@@YAXAEAPEAVIMsoColorGallerySite@@HAEAVGalleryDSSP@@AEAPEAVCMsoGalleryUserDefault@@@Z` at `0x180477d7d`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x180477e04`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x180477e04`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180477dd9`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180477e34`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180478142`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180477dd9`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180477e34`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180478142`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x180478115`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x180478115`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180477da9`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180477da9`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180477f1a`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180477f41`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180477f68`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180477f8f`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180477fb6`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180477fda`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180478001`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18047804b`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180478072`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180478096`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1804780ba`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1804780de`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180477f1a`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180477f41`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180477f68`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180477f8f`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180477fb6`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180477fda`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180478001`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18047804b`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180478072`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180478096`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1804780ba`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1804780de`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180477df1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180478105`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180477df1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180478105`

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
0x180477d38  mov     [rsp-38h+arg_0], rbx
0x180477d3d  push    rbp
0x180477d3e  push    rsi
0x180477d3f  push    rdi
0x180477d40  push    r12
0x180477d42  push    r13
0x180477d44  push    r14
0x180477d46  push    r15
0x180477d48  mov     rbp, rsp
0x180477d4b  sub     rsp, 60h
0x180477d4f  mov     ebx, r8d
0x180477d52  mov     r14, rdx
0x180477d55  mov     rdi, rcx
0x180477d58  xorps   xmm0, xmm0
0x180477d5b  movdqu  [rbp+var_18], xmm0
0x180477d60  xor     r15d, r15d
0x180477d63  mov     [rbp+var_8], r15
0x180477d67  mov     [rbp+var_28], rdx
0x180477d6b  mov     [rbp+arg_18], r15
0x180477d6f  lea     r9, [rbp+arg_18]
0x180477d73  lea     r8, [rbp+var_18]
0x180477d77  xor     edx, edx
0x180477d79  lea     rcx, [rbp+var_28]
0x180477d7d  call    cs:__imp_?MsoCreateColorGalleryAndUser@@YAXAEAPEAVIMsoColorGallerySite@@HAEAVGalleryDSSP@@AEAPEAVCMsoGalleryUserDefault@@@Z; MsoCreateColorGalleryAndUser(IMsoColorGallerySite * &,int,GalleryDSSP &,CMsoGalleryUserDefault * &)
0x180477d83  mov     rsi, qword ptr [rbp+var_18]
0x180477d87  test    rsi, rsi
0x180477d8a  jz      loc_1804781AE
0x180477d90  cmp     [rbp+arg_18], r15
0x180477d94  jz      loc_1804781AE
0x180477d9a  mov     [rbp+var_30], r15
0x180477d9e  lea     rdx, [rbp+var_30]
0x180477da2  lea     r13d, [r15+1]
0x180477da6  mov     ecx, r13d
0x180477da9  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x180477daf  mov     r9, [rbp+var_30]
0x180477db3  test    r9, r9
0x180477db6  jz      short loc_180477DDF
0x180477db8  mov     rax, [rsi]
0x180477dbb  xor     edx, edx
0x180477dbd  mov     r8d, 82h
0x180477dc3  mov     rcx, rsi
0x180477dc6  mov     rax, [rax+30h]
0x180477dca  call    cs:__guard_dispatch_icall_fptr
0x180477dd0  mov     rcx, [rbp+var_30]
0x180477dd4  test    rcx, rcx
0x180477dd7  jz      short loc_180477DDF
0x180477dd9  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180477ddf  mov     rsi, qword ptr [rbp+var_18]
0x180477de3  mov     r12d, 7A0740h
0x180477de9  test    rsi, rsi
0x180477dec  jnz     short loc_180477DF9
0x180477dee  mov     ecx, r12d
0x180477df1  call    cs:__imp_MsoShipAssertTagProc
0x180477df7  jmp     short loc_180477E3A
0x180477df9  mov     [rbp+var_30], r15
0x180477dfd  lea     rdx, [rbp+var_30]
0x180477e01  mov     cl, r13b
0x180477e04  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x180477e0a  mov     r9, [rbp+var_30]
0x180477e0e  test    r9, r9
0x180477e11  jz      short loc_180477E3A
0x180477e13  mov     rax, [rsi]
0x180477e16  xor     edx, edx
0x180477e18  mov     r8d, 41800021h
0x180477e1e  mov     rcx, rsi
0x180477e21  mov     rax, [rax+30h]
0x180477e25  call    cs:__guard_dispatch_icall_fptr
0x180477e2b  mov     rcx, [rbp+var_30]
0x180477e2f  test    rcx, rcx
0x180477e32  jz      short loc_180477E3A
0x180477e34  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180477e3a  mov     [rbp+arg_8], r15
0x180477e3e  mov     rcx, qword ptr [rbp+var_18]
0x180477e42  mov     rax, [rcx]
0x180477e45  mov     [rbp+arg_8], r15
0x180477e49  lea     r8, [rbp+arg_8]
0x180477e4d  lea     rdx, _GUID_4d1d2ad5_5e40_4b17_b505_2efcc8764b05
0x180477e54  mov     rax, [rax]
0x180477e57  call    cs:__guard_dispatch_icall_fptr
0x180477e5d  test    eax, eax
0x180477e5f  jns     short loc_180477E6E
0x180477e61  mov     edx, 23485084h; unsigned int
0x180477e66  mov     ecx, eax; int
0x180477e68  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180477e6d  int     3; Trap to Debugger
0x180477e6e  mov     rax, rdi
0x180477e71  lea     rdx, [rdi+28h]
0x180477e75  neg     rax
0x180477e78  sbb     rcx, rcx
0x180477e7b  and     rcx, rdx
0x180477e7e  mov     [r14+18h], rcx
0x180477e82  mov     [r14+10h], ebx
0x180477e86  lea     rcx, [r14+20h]
0x180477e8a  lea     rdx, [rbp+var_18]
0x180477e8e  call    ??4GalleryDSSP@@QEAAAEBV0@AEBV0@@Z; GalleryDSSP::operator=(GalleryDSSP const &)
0x180477e93  lea     rcx, [r14+38h]
0x180477e97  mov     rdx, [rbp+arg_18]
0x180477e9b  call    ??4?$TCntPtr@VInkInputLayerNode@Dr@@@Ofc@@QEAAAEAV01@PEAVInkInputLayerNode@Dr@@@Z; Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(Dr::InkInputLayerNode *)
0x180477ea0  mov     rcx, [rbp+arg_18]
0x180477ea4  mov     rax, [rcx]
0x180477ea7  mov     rax, [rax+0B8h]
0x180477eae  call    cs:__guard_dispatch_icall_fptr
0x180477eb4  mov     rcx, [rbp+arg_18]
0x180477eb8  mov     rax, [rcx]
0x180477ebb  mov     rax, [rax+0E8h]
0x180477ec2  call    cs:__guard_dispatch_icall_fptr
0x180477ec8  mov     r8d, 6
0x180477ece  cmp     ebx, r8d
0x180477ed1  jg      loc_180478012
0x180477ed7  jz      loc_180477FEB
0x180477edd  test    ebx, ebx
0x180477edf  jz      loc_180477FC7
0x180477ee5  sub     ebx, 1
0x180477ee8  jz      loc_180477FA0
0x180477eee  sub     ebx, 1
0x180477ef1  jz      loc_180477F79
0x180477ef7  sub     ebx, 1
0x180477efa  jz      short loc_180477F52
0x180477efc  sub     ebx, 1
0x180477eff  jz      short loc_180477F2B
0x180477f01  cmp     ebx, 1
0x180477f04  jnz     loc_180478152
0x180477f0a  mov     r9, [rbp+arg_8]
0x180477f0e  mov     rcx, [rdi+3B8h]
0x180477f15  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x180477f1a  call    cs:__imp_MsoGetHinstIntl
0x180477f20  mov     r8d, 0A60CC912h
0x180477f26  jmp     loc_1804780EA
0x180477f2b  mov     r9, [rbp+arg_8]
0x180477f2f  mov     r8d, 5
0x180477f35  mov     rcx, [rdi+3B8h]
0x180477f3c  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x180477f41  call    cs:__imp_MsoGetHinstIntl
0x180477f47  mov     r8d, 0A60D0AD9h
0x180477f4d  jmp     loc_1804780EA
0x180477f52  mov     r9, [rbp+arg_8]
0x180477f56  mov     r8d, 4
0x180477f5c  mov     rcx, [rdi+3B8h]
0x180477f63  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x180477f68  call    cs:__imp_MsoGetHinstIntl
0x180477f6e  mov     r8d, 0C5F7B403h
0x180477f74  jmp     loc_1804780EA
0x180477f79  mov     r9, [rbp+arg_8]
0x180477f7d  mov     r8d, 3
0x180477f83  mov     rcx, [rdi+3B8h]
0x180477f8a  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x180477f8f  call    cs:__imp_MsoGetHinstIntl
0x180477f95  mov     r8d, 9C5A98F1h
0x180477f9b  jmp     loc_1804780EA
0x180477fa0  mov     r9, [rbp+arg_8]
0x180477fa4  mov     r8d, 2
0x180477faa  mov     rcx, [rdi+3B8h]
0x180477fb1  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x180477fb6  call    cs:__imp_MsoGetHinstIntl
0x180477fbc  mov     r8d, 0F3145F12h
0x180477fc2  jmp     loc_1804780EA
0x180477fc7  mov     r9, [rbp+arg_8]
0x180477fcb  mov     r8d, r13d
0x180477fce  mov     rcx, [rdi+3B8h]
0x180477fd5  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x180477fda  call    cs:__imp_MsoGetHinstIntl
0x180477fe0  mov     r8d, 0DC17BF81h
0x180477fe6  jmp     loc_1804780EA
0x180477feb  mov     r9, [rbp+arg_8]
0x180477fef  mov     r8d, 7
0x180477ff5  mov     rcx, [rdi+3B8h]
0x180477ffc  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x180478001  call    cs:__imp_MsoGetHinstIntl
0x180478007  mov     r8d, 0A60B874Ch
0x18047800d  jmp     loc_1804780EA
0x180478012  sub     ebx, 7
0x180478015  jz      loc_1804780C8
0x18047801b  sub     ebx, 1
0x18047801e  jz      loc_1804780A4
0x180478024  sub     ebx, 1
0x180478027  jz      short loc_180478080
0x180478029  sub     ebx, 1
0x18047802c  jz      short loc_18047805C
0x18047802e  cmp     ebx, 1
0x180478031  jnz     loc_180478152
0x180478037  mov     r9, [rbp+arg_8]
0x18047803b  lea     r8d, [rbx+0Bh]
0x18047803f  mov     rcx, [rdi+3B8h]
0x180478046  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x18047804b  call    cs:__imp_MsoGetHinstIntl
0x180478051  mov     r8d, 31DCA489h
0x180478057  jmp     loc_1804780EA
0x18047805c  mov     r9, [rbp+arg_8]
0x180478060  mov     r8d, 0Bh
0x180478066  mov     rcx, [rdi+3B8h]
0x18047806d  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x180478072  call    cs:__imp_MsoGetHinstIntl
0x180478078  mov     r8d, 0DCFB0467h
0x18047807e  jmp     short loc_1804780EA
0x180478080  mov     r9, [rbp+arg_8]
0x180478084  mov     r8d, 0Ah
0x18047808a  mov     rcx, [rdi+3B8h]
0x180478091  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x180478096  call    cs:__imp_MsoGetHinstIntl
0x18047809c  mov     r8d, 0A610D02Bh
0x1804780a2  jmp     short loc_1804780EA
0x1804780a4  mov     r9, [rbp+arg_8]
0x1804780a8  mov     r8d, 9
0x1804780ae  mov     rcx, [rdi+3B8h]
0x1804780b5  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x1804780ba  call    cs:__imp_MsoGetHinstIntl
0x1804780c0  mov     r8d, 0A61111F2h
0x1804780c6  jmp     short loc_1804780EA
0x1804780c8  mov     r9, [rbp+arg_8]
0x1804780cc  mov     r8d, 8
0x1804780d2  mov     rcx, [rdi+3B8h]
0x1804780d9  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIDataSource@FlexUI@@@FlexUI@@PEAUIDataSource@2@@FlexUI@@YA_NPEAUIDataSource@0@IH0PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IDataSource *>,FlexUI::IDataSource *>(FlexUI::IDataSource *,uint,int,FlexUI::IDataSource *,void *)
0x1804780de  call    cs:__imp_MsoGetHinstIntl
0x1804780e4  mov     r8d, 0A61253B8h; int
0x1804780ea  mov     rdx, rax; HINSTANCE
0x1804780ed  lea     rcx, [rbp+var_20]; this
0x1804780f1  call    ??0CVarStr@Ofc@@QEAA@PEAUHINSTANCE__@@H@Z; Ofc::CVarStr::CVarStr(HINSTANCE__ *,int)
0x1804780f6  mov     rbx, qword ptr [rbp+var_18]
0x1804780fa  test    rbx, rbx
0x1804780fd  mov     rcx, [rax]
0x180478100  jnz     short loc_18047810D
0x180478102  mov     ecx, r12d
0x180478105  call    cs:__imp_MsoShipAssertTagProc
0x18047810b  jmp     short loc_180478148
0x18047810d  mov     [rbp+var_30], r15
0x180478111  lea     rdx, [rbp+var_30]
0x180478115  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x18047811b  mov     r9, [rbp+var_30]
0x18047811f  test    r9, r9
0x180478122  jz      short loc_180478148
0x180478124  mov     rax, [rbx]
0x180478127  mov     r8d, r13d
0x18047812a  xor     edx, edx
0x18047812c  mov     rcx, rbx
0x18047812f  mov     rax, [rax+30h]
0x180478133  call    cs:__guard_dispatch_icall_fptr
0x180478139  mov     rcx, [rbp+var_30]
0x18047813d  test    rcx, rcx
0x180478140  jz      short loc_180478148
0x180478142  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180478148  lea     rcx, [rbp+var_20]; this
0x18047814c  call    ?ReleaseBuffer@CVarStr@Ofc@@AEAAXXZ; Ofc::CVarStr::ReleaseBuffer(void)
0x180478151  nop
0x180478152  mov     rcx, [rbp+arg_8]
0x180478156  test    rcx, rcx
0x180478159  jz      short loc_180478169
0x18047815b  mov     rax, [rcx]
0x18047815e  mov     rax, [rax+10h]
0x180478162  call    cs:__guard_dispatch_icall_fptr
0x180478168  nop
0x180478169  mov     rcx, [rbp+arg_18]
0x18047816d  test    rcx, rcx
0x180478170  jz      short loc_180478180
0x180478172  mov     rax, [rcx]
0x180478175  mov     rax, [rax+10h]
0x180478179  call    cs:__guard_dispatch_icall_fptr
0x18047817f  nop
0x180478180  mov     rcx, qword ptr [rbp+var_18]
0x180478184  test    rcx, rcx
0x180478187  jz      short loc_180478196
0x180478189  mov     rax, [rcx]
0x18047818c  mov     rax, [rax+10h]
0x180478190  call    cs:__guard_dispatch_icall_fptr
0x180478196  mov     rbx, [rsp+60h+arg_0]
0x18047819e  add     rsp, 60h
0x1804781a2  pop     r15
0x1804781a4  pop     r14
0x1804781a6  pop     r13
0x1804781a8  pop     r12
0x1804781aa  pop     rdi
0x1804781ab  pop     rsi
0x1804781ac  pop     rbp
0x1804781ad  retn
0x1804781ae  mov     edx, 23485087h; unsigned int
0x1804781b3  mov     ecx, 8007000Eh; int
0x1804781b8  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1804781bd  int     3; Trap to Debugger
```
