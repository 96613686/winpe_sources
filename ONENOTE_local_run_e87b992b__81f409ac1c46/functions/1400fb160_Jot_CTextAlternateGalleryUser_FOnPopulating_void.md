# Jot::CTextAlternateGalleryUser::FOnPopulating(void)

- ea: `0x1400fb160`
- end: `0x1400fb428`
- name: `?FOnPopulating@CTextAlternateGalleryUser@Jot@@UEAA_NXZ`
- size: `712`
- prototype: `bool __fastcall(Jot::CTextAlternateGalleryUser *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140057580`
- `0x140089d24`
- `0x140089de4`
- `0x1400f34e4`
- `0x1400fb160`

## import_xrefs

- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x1400fb1ad`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x1400fb211`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x1400fb2de`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x1400fb32f`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x1400fb1ad`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x1400fb211`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x1400fb2de`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x1400fb32f`
- `Mso98Win32Client!__imp_?FOnPopulating@CMsoGalleryUserDefault@@UEAA_NXZ` at `0x1400fb421`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1400fb28d`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1400fb3ad`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1400fb28d`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1400fb3ad`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1400fb25e`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1400fb37f`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1400fb25e`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1400fb37f`
- `Mso30Win32Client!__imp_MsoReplaceAllOfWzWithWz` at `0x1400fb201`
- `Mso30Win32Client!__imp_MsoReplaceAllOfWzWithWz` at `0x1400fb31f`
- `Mso30Win32Client!__imp_MsoReplaceAllOfWzWithWz` at `0x1400fb201`
- `Mso30Win32Client!__imp_MsoReplaceAllOfWzWithWz` at `0x1400fb31f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1400fb24c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1400fb36d`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1400fb24c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1400fb36d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1400fb2b9`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1400fb3d5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1400fb2b9`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1400fb3d5`

## pseudocode

```c
bool __fastcall Jot::CTextAlternateGalleryUser::FOnPopulating(Jot::CTextAlternateGalleryUser *this)
{
  void **v2; // rsi
  GalleryDSSP *GalleryDataSource; // rax
  struct FlexUI::FlexValue *v4; // r9
  char *v5; // r14
  _QWORD *v6; // rax
  __int64 v7; // rax
  wchar_t *v8; // rbx
  GalleryDSSP *v9; // rax
  __int64 v10; // r12
  void *v11; // rdx
  void **v12; // r14
  GalleryDSSP *v13; // rax
  struct FlexUI::FlexValue *v14; // r9
  _QWORD *v15; // rax
  __int64 v16; // rax
  wchar_t *v17; // rbx
  GalleryDSSP *v18; // rax
  __int64 v19; // rsi
  void *v20; // rdx
  struct FlexUI::FlexValue *v22; // [rsp+28h] [rbp-41h]
  unsigned int v23; // [rsp+30h] [rbp-39h]
  unsigned __int16 v24; // [rsp+38h] [rbp-31h]
  int v25; // [rsp+58h] [rbp-11h]
  const wchar_t *v26; // [rsp+60h] [rbp-9h]
  int v27; // [rsp+68h] [rbp-1h]
  _QWORD v28[10]; // [rsp+70h] [rbp+7h] BYREF
  NetUI::BaseValue *v29; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v30; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v32; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( *((_BYTE *)this + 280) )
  {
    if ( *((_BYTE *)this + 281) )
    {
      v2 = (void **)((char *)this + 272);
      if ( *((_QWORD *)this + 34) )
      {
        v28[0] = 0;
        GalleryDataSource = CMsoGalleryUserDefault::GetGalleryDataSource(this);
        GalleryDSSP::AddGalleryCategory(GalleryDataSource, (struct GalleryCategorySP *)v28, 0, v4);
        v5 = 0;
        if ( *v2 )
        {
          do
          {
            v6 = (_QWORD *)std::vector<std::wstring>::operator[]((char *)this + 248, v5);
            if ( v6[3] > 7u )
              v6 = (_QWORD *)*v6;
            v7 = MsoReplaceAllOfWzWithWz(v6, L"&", L"&&", 4);
            v30 = 0;
            v8 = (wchar_t *)v7;
            v9 = CMsoGalleryUserDefault::GetGalleryDataSource(this);
            GalleryDSSP::AddGalleryItem(
              v9,
              (struct GalleryItemSP *)&v30,
              (struct GalleryCategorySP *)v28,
              v8,
              0,
              v22,
              v23,
              v24,
              v5,
              0,
              0,
              v25,
              v26,
              v27);
            v10 = v30;
            if ( v30 )
            {
              v29 = 0;
              FlexUI::FlexValue::CreateString(0, (struct FlexUI::FlexValueSP *)&v29);
              if ( v29 )
              {
                (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v10 + 48LL))(v10, 0, 6);
                if ( v29 )
                  NetUI::BaseValue::Release(v29);
              }
              v29 = 0;
            }
            else
            {
              MsoShipAssertTagProc(7997248);
            }
            if ( v30 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            v30 = 0;
            if ( v8 )
              Mso::Memory::Free((Mso::Memory *)v8, v11);
            ++v5;
          }
          while ( v5 < *v2 );
          v12 = (void **)((char *)this + 272);
        }
        else
        {
          v12 = v2;
        }
        v32 = 0;
        v13 = CMsoGalleryUserDefault::GetGalleryDataSource(this);
        GalleryDSSP::AddGalleryCategory(v13, (struct GalleryCategorySP *)&v32, 0, v14);
        v15 = (_QWORD *)std::vector<std::wstring>::operator[]((char *)this + 248, *v2);
        if ( v15[3] > 7u )
          v15 = (_QWORD *)*v15;
        v16 = MsoReplaceAllOfWzWithWz(v15, L"&", L"&&", 4);
        v31 = 0;
        v17 = (wchar_t *)v16;
        v18 = CMsoGalleryUserDefault::GetGalleryDataSource(this);
        GalleryDSSP::AddGalleryItem(
          v18,
          (struct GalleryItemSP *)&v31,
          (struct GalleryCategorySP *)&v32,
          v17,
          0,
          v22,
          v23,
          v24,
          *v12,
          0,
          0,
          v25,
          v26,
          v27);
        v19 = v31;
        if ( v31 )
        {
          v29 = 0;
          FlexUI::FlexValue::CreateString(0, (struct FlexUI::FlexValueSP *)&v29);
          if ( v29 )
          {
            (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v19 + 48LL))(v19, 0, 6);
            if ( v29 )
              NetUI::BaseValue::Release(v29);
          }
        }
        else
        {
          MsoShipAssertTagProc(7997248);
        }
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        v31 = 0;
        if ( v17 )
          Mso::Memory::Free((Mso::Memory *)v17, v20);
        if ( v32 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        v32 = 0;
        if ( v28[0] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v28[0] + 16LL))(v28[0]);
      }
    }
  }
  return CMsoGalleryUserDefault::FOnPopulating(this);
}

```

## disassembly

```asm
0x1400fb160  push    rbp
0x1400fb162  push    rbx
0x1400fb163  push    rsi
0x1400fb164  push    rdi
0x1400fb165  push    r12
0x1400fb167  push    r13
0x1400fb169  push    r14
0x1400fb16b  push    r15
0x1400fb16d  lea     rbp, [rsp-1Fh]
0x1400fb172  sub     rsp, 88h
0x1400fb179  xor     r13d, r13d
0x1400fb17c  mov     rdi, rcx
0x1400fb17f  cmp     [rcx+118h], r13b
0x1400fb186  jz      loc_1400FB40B
0x1400fb18c  cmp     [rcx+119h], r13b
0x1400fb193  jz      loc_1400FB40B
0x1400fb199  lea     rsi, [rcx+110h]
0x1400fb1a0  cmp     [rsi], r13
0x1400fb1a3  jbe     loc_1400FB40B
0x1400fb1a9  mov     [rbp+57h+var_50], r13
0x1400fb1ad  call    cs:__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ; CMsoGalleryUserDefault::GetGalleryDataSource(void)
0x1400fb1b3  xor     r8d, r8d; wchar_t *
0x1400fb1b6  lea     rdx, [rbp+57h+var_50]; struct GalleryCategorySP *
0x1400fb1ba  mov     rcx, rax; this
0x1400fb1bd  call    ?AddGalleryCategory@GalleryDSSP@@QEAA_NPEAVGalleryCategorySP@@PEB_WPEAVFlexValue@FlexUI@@@Z; GalleryDSSP::AddGalleryCategory(GalleryCategorySP *,wchar_t const *,FlexUI::FlexValue *)
0x1400fb1c2  lea     r15, [rdi+0F8h]
0x1400fb1c9  mov     r14d, r13d
0x1400fb1cc  cmp     [rsi], r13
0x1400fb1cf  jbe     loc_1400FB2D4
0x1400fb1d5  mov     rdx, r14
0x1400fb1d8  mov     rcx, r15
0x1400fb1db  call    ??A?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::vector<std::wstring>::operator[](unsigned __int64)
0x1400fb1e0  cmp     qword ptr [rax+18h], 7
0x1400fb1e5  jbe     short loc_1400FB1EA
0x1400fb1e7  mov     rax, [rax]
0x1400fb1ea  mov     r9d, 4
0x1400fb1f0  lea     r8, asc_140200614; "&&"
0x1400fb1f7  lea     rdx, asc_1401F91B4; "&"
0x1400fb1fe  mov     rcx, rax
0x1400fb201  call    cs:__imp_MsoReplaceAllOfWzWithWz
0x1400fb207  mov     rcx, rdi
0x1400fb20a  mov     [rbp+57h+arg_8], r13
0x1400fb20e  mov     rbx, rax
0x1400fb211  call    cs:__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ; CMsoGalleryUserDefault::GetGalleryDataSource(void)
0x1400fb217  mov     [rsp+0C0h+var_70], r13d; int
0x1400fb21c  lea     r8, [rbp+57h+var_50]; struct GalleryCategorySP *
0x1400fb220  mov     [rsp+0C0h+var_78], r13d; int
0x1400fb225  lea     rdx, [rbp+57h+arg_8]; struct GalleryItemSP *
0x1400fb229  mov     [rsp+0C0h+var_80], r14; void *
0x1400fb22e  mov     rcx, rax; this
0x1400fb231  mov     r9, rbx; wchar_t *
0x1400fb234  mov     [rsp+0C0h+var_A0], r13; struct FlexUI::FlexValue *
0x1400fb239  call    ?AddGalleryItem@GalleryDSSP@@QEAA_NPEAVGalleryItemSP@@AEAVGalleryCategorySP@@PEB_WPEAVFlexValue@FlexUI@@3KGPEAXHHH2H@Z; GalleryDSSP::AddGalleryItem(GalleryItemSP *,GalleryCategorySP &,wchar_t const *,FlexUI::FlexValue *,FlexUI::FlexValue *,ulong,ushort,void *,int,int,int,wchar_t const *,int)
0x1400fb23e  mov     r12, [rbp+57h+arg_8]
0x1400fb242  test    r12, r12
0x1400fb245  jnz     short loc_1400FB254
0x1400fb247  mov     ecx, 7A0740h
0x1400fb24c  call    cs:__imp_MsoShipAssertTagProc
0x1400fb252  jmp     short loc_1400FB297
0x1400fb254  lea     rdx, [rbp+57h+arg_0]
0x1400fb258  mov     [rbp+57h+arg_0], r13
0x1400fb25c  xor     ecx, ecx
0x1400fb25e  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x1400fb264  mov     r9, [rbp+57h+arg_0]
0x1400fb268  test    r9, r9
0x1400fb26b  jz      short loc_1400FB293
0x1400fb26d  mov     rax, [r12]
0x1400fb271  xor     edx, edx
0x1400fb273  mov     rcx, r12
0x1400fb276  mov     rax, [rax+30h]
0x1400fb27a  lea     r8d, [rdx+6]
0x1400fb27e  call    cs:__guard_dispatch_icall_fptr
0x1400fb284  mov     rcx, [rbp+57h+arg_0]
0x1400fb288  test    rcx, rcx
0x1400fb28b  jz      short loc_1400FB293
0x1400fb28d  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1400fb293  mov     [rbp+57h+arg_0], r13
0x1400fb297  mov     rcx, [rbp+57h+arg_8]
0x1400fb29b  test    rcx, rcx
0x1400fb29e  jz      short loc_1400FB2AD
0x1400fb2a0  mov     rax, [rcx]
0x1400fb2a3  mov     rax, [rax+10h]
0x1400fb2a7  call    cs:__guard_dispatch_icall_fptr
0x1400fb2ad  mov     [rbp+57h+arg_8], r13
0x1400fb2b1  test    rbx, rbx
0x1400fb2b4  jz      short loc_1400FB2BF
0x1400fb2b6  mov     rcx, rbx
0x1400fb2b9  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1400fb2bf  inc     r14
0x1400fb2c2  cmp     r14, [rsi]
0x1400fb2c5  jb      loc_1400FB1D5
0x1400fb2cb  lea     r14, [rdi+110h]
0x1400fb2d2  jmp     short loc_1400FB2D7
0x1400fb2d4  mov     r14, rsi
0x1400fb2d7  mov     rcx, rdi
0x1400fb2da  mov     [rbp+57h+arg_18], r13
0x1400fb2de  call    cs:__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ; CMsoGalleryUserDefault::GetGalleryDataSource(void)
0x1400fb2e4  xor     r8d, r8d; wchar_t *
0x1400fb2e7  lea     rdx, [rbp+57h+arg_18]; struct GalleryCategorySP *
0x1400fb2eb  mov     rcx, rax; this
0x1400fb2ee  call    ?AddGalleryCategory@GalleryDSSP@@QEAA_NPEAVGalleryCategorySP@@PEB_WPEAVFlexValue@FlexUI@@@Z; GalleryDSSP::AddGalleryCategory(GalleryCategorySP *,wchar_t const *,FlexUI::FlexValue *)
0x1400fb2f3  mov     rdx, [rsi]
0x1400fb2f6  mov     rcx, r15
0x1400fb2f9  call    ??A?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::vector<std::wstring>::operator[](unsigned __int64)
0x1400fb2fe  cmp     qword ptr [rax+18h], 7
0x1400fb303  jbe     short loc_1400FB308
0x1400fb305  mov     rax, [rax]
0x1400fb308  mov     r9d, 4
0x1400fb30e  lea     r8, asc_140200614; "&&"
0x1400fb315  lea     rdx, asc_1401F91B4; "&"
0x1400fb31c  mov     rcx, rax
0x1400fb31f  call    cs:__imp_MsoReplaceAllOfWzWithWz
0x1400fb325  mov     rcx, rdi
0x1400fb328  mov     [rbp+57h+arg_10], r13
0x1400fb32c  mov     rbx, rax
0x1400fb32f  call    cs:__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ; CMsoGalleryUserDefault::GetGalleryDataSource(void)
0x1400fb335  mov     rdx, [r14]
0x1400fb338  lea     r8, [rbp+57h+arg_18]; struct GalleryCategorySP *
0x1400fb33c  mov     [rsp+0C0h+var_70], r13d; int
0x1400fb341  mov     r9, rbx; wchar_t *
0x1400fb344  mov     [rsp+0C0h+var_78], r13d; int
0x1400fb349  mov     rcx, rax; this
0x1400fb34c  mov     [rsp+0C0h+var_80], rdx; void *
0x1400fb351  lea     rdx, [rbp+57h+arg_10]; struct GalleryItemSP *
0x1400fb355  mov     [rsp+0C0h+var_A0], r13; struct FlexUI::FlexValue *
0x1400fb35a  call    ?AddGalleryItem@GalleryDSSP@@QEAA_NPEAVGalleryItemSP@@AEAVGalleryCategorySP@@PEB_WPEAVFlexValue@FlexUI@@3KGPEAXHHH2H@Z; GalleryDSSP::AddGalleryItem(GalleryItemSP *,GalleryCategorySP &,wchar_t const *,FlexUI::FlexValue *,FlexUI::FlexValue *,ulong,ushort,void *,int,int,int,wchar_t const *,int)
0x1400fb35f  mov     rsi, [rbp+57h+arg_10]
0x1400fb363  test    rsi, rsi
0x1400fb366  jnz     short loc_1400FB375
0x1400fb368  mov     ecx, 7A0740h
0x1400fb36d  call    cs:__imp_MsoShipAssertTagProc
0x1400fb373  jmp     short loc_1400FB3B3
0x1400fb375  lea     rdx, [rbp+57h+arg_0]
0x1400fb379  mov     [rbp+57h+arg_0], r13
0x1400fb37d  xor     ecx, ecx
0x1400fb37f  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x1400fb385  mov     r9, [rbp+57h+arg_0]
0x1400fb389  test    r9, r9
0x1400fb38c  jz      short loc_1400FB3B3
0x1400fb38e  mov     rax, [rsi]
0x1400fb391  xor     edx, edx
0x1400fb393  mov     rcx, rsi
0x1400fb396  mov     rax, [rax+30h]
0x1400fb39a  lea     r8d, [rdx+6]
0x1400fb39e  call    cs:__guard_dispatch_icall_fptr
0x1400fb3a4  mov     rcx, [rbp+57h+arg_0]
0x1400fb3a8  test    rcx, rcx
0x1400fb3ab  jz      short loc_1400FB3B3
0x1400fb3ad  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1400fb3b3  mov     rcx, [rbp+57h+arg_10]
0x1400fb3b7  test    rcx, rcx
0x1400fb3ba  jz      short loc_1400FB3C9
0x1400fb3bc  mov     rax, [rcx]
0x1400fb3bf  mov     rax, [rax+10h]
0x1400fb3c3  call    cs:__guard_dispatch_icall_fptr
0x1400fb3c9  mov     [rbp+57h+arg_10], r13
0x1400fb3cd  test    rbx, rbx
0x1400fb3d0  jz      short loc_1400FB3DB
0x1400fb3d2  mov     rcx, rbx
0x1400fb3d5  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1400fb3db  mov     rcx, [rbp+57h+arg_18]
0x1400fb3df  test    rcx, rcx
0x1400fb3e2  jz      short loc_1400FB3F1
0x1400fb3e4  mov     rax, [rcx]
0x1400fb3e7  mov     rax, [rax+10h]
0x1400fb3eb  call    cs:__guard_dispatch_icall_fptr
0x1400fb3f1  mov     rcx, [rbp+57h+var_50]
0x1400fb3f5  mov     [rbp+57h+arg_18], r13
0x1400fb3f9  test    rcx, rcx
0x1400fb3fc  jz      short loc_1400FB40B
0x1400fb3fe  mov     rax, [rcx]
0x1400fb401  mov     rax, [rax+10h]
0x1400fb405  call    cs:__guard_dispatch_icall_fptr
0x1400fb40b  mov     rcx, rdi
0x1400fb40e  add     rsp, 88h
0x1400fb415  pop     r15
0x1400fb417  pop     r14
0x1400fb419  pop     r13
0x1400fb41b  pop     r12
0x1400fb41d  pop     rdi
0x1400fb41e  pop     rsi
0x1400fb41f  pop     rbx
0x1400fb420  pop     rbp
0x1400fb421  jmp     cs:__imp_?FOnPopulating@CMsoGalleryUserDefault@@UEAA_NXZ; CMsoGalleryUserDefault::FOnPopulating(void)
```
