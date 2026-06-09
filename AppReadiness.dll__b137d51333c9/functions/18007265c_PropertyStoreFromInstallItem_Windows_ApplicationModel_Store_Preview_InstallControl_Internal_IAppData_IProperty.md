# PropertyStoreFromInstallItem(Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *,IPropertyStore * * *,uint *)

- ea: `0x18007265c`
- end: `0x1800728ec`
- name: `?PropertyStoreFromInstallItem@@YAJPEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAPEAPEAUIPropertyStore@@PEAI@Z`
- size: `656`
- prototype: `__int64 __fastcall(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *, struct IPropertyStore ***, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800720c0`

## callees

- `0x180002958`
- `0x18001ffd0`
- `0x180020458`
- `0x18006f510`
- `0x1800703c8`
- `0x18007265c`
- `0x1800733d8`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800726a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800726c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800726d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072817`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072852`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800728ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800728bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800728c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800726a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800726c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800726d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072817`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072852`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800728ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800728bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800728c9`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800727a6`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800727a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PropertyStoreFromInstallItem(
        struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *a1,
        struct IPropertyStore ***a2,
        unsigned int *a3)
{
  __int64 (__fastcall *v6)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *, HSTRING *); // rbx
  HRESULT ImageColors; // ebx
  __int64 (__fastcall *v8)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *, __int64 *); // rbx
  struct IPropertyStore **v9; // rsi
  void *v10; // rcx
  unsigned int i; // r14d
  unsigned int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, HSTRING *); // rbx
  struct IPropertyStore *v15; // rcx
  HSTRING v17; // [rsp+20h] [rbp-28h] BYREF
  __int64 v18; // [rsp+28h] [rbp-20h] BYREF
  HSTRING v19[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v20; // [rsp+90h] [rbp+48h] BYREF
  void *ppv; // [rsp+98h] [rbp+50h] BYREF
  HSTRING string; // [rsp+A0h] [rbp+58h] BYREF
  HSTRING v23; // [rsp+A8h] [rbp+60h] BYREF

  *a2 = 0;
  *a3 = 0;
  v19[0] = 0;
  v23 = 0;
  string = 0;
  v18 = 0;
  v20 = 0;
  v6 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *, HSTRING *))(*(_QWORD *)a1 + 128LL);
  WindowsDeleteString(0);
  v19[0] = 0;
  ImageColors = v6(a1, v19);
  if ( ImageColors >= 0 )
  {
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v23);
    v23 = 0;
    ImageColors = GetImageColors(a1, &v23, &string);
    if ( ImageColors >= 0 )
    {
      v8 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *, __int64 *))(*(_QWORD *)a1 + 96LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
      ImageColors = v8(a1, &v18);
      if ( ImageColors >= 0 )
      {
        ImageColors = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v18 + 56LL))(v18, &v20);
        if ( ImageColors >= 0 )
        {
          v9 = 0;
          v17 = 0;
          ppv = 0;
          ImageColors = ULongLongMult(v20, 8u, (unsigned __int64 *)&ppv);
          if ( ImageColors >= 0 )
          {
            ImageColors = CTCoAllocPolicy::Alloc(v10, 1u, (unsigned __int64)ppv, (void **)&v17);
            v9 = (struct IPropertyStore **)v17;
          }
          for ( i = 0; ; ++i )
          {
            if ( ImageColors < 0 )
            {
              ReleasePropertyStore(v9, v20);
              goto LABEL_17;
            }
            v12 = v20;
            if ( i >= v20 )
              break;
            ppv = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
            ImageColors = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
            if ( ImageColors >= 0 )
            {
              AddStringToPropertyStore((struct IPropertyStore *)ppv, &PKEY_ItemNameDisplay, v19[0]);
              AddStringToPropertyStore((struct IPropertyStore *)ppv, &PKEY_Tile_LongDisplayName, v19[0]);
              AddStringToPropertyStore((struct IPropertyStore *)ppv, &PKEY_Tile_Background, v23);
              AddStringToPropertyStore((struct IPropertyStore *)ppv, &PKEY_Tile_Foreground, string);
              v17 = 0;
              v13 = v18;
              v14 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v18 + 48LL);
              WindowsDeleteString(0);
              v17 = 0;
              ImageColors = v14(v13, i, &v17);
              if ( ImageColors >= 0 )
                AddStringToPropertyStore(
                  (struct IPropertyStore *)ppv,
                  &PKEY_AppUserModel_PackageRelativeApplicationID,
                  v17);
              WindowsDeleteString(v17);
              v17 = 0;
              if ( ImageColors >= 0 )
              {
                (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 56LL))(ppv);
                v15 = (struct IPropertyStore *)ppv;
                ppv = 0;
                v9[i] = v15;
              }
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
          }
          *a2 = v9;
          *a3 = v12;
        }
      }
    }
  }
LABEL_17:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v23);
  v23 = 0;
  WindowsDeleteString(v19[0]);
  return (unsigned int)ImageColors;
}

```

## disassembly

```asm
0x18007265c  push    rbp
0x18007265e  push    rbx
0x18007265f  push    rsi
0x180072660  push    rdi
0x180072661  push    r12
0x180072663  push    r13
0x180072665  push    r14
0x180072667  push    r15
0x180072669  mov     rbp, rsp
0x18007266c  sub     rsp, 48h
0x180072670  mov     r15, r8
0x180072673  mov     r12, rdx
0x180072676  mov     rdi, rcx
0x180072679  xor     r13d, r13d
0x18007267c  mov     [rdx], r13
0x18007267f  mov     [r8], r13d
0x180072682  mov     [rbp+var_18], r13
0x180072686  mov     [rbp+arg_18], r13
0x18007268a  mov     [rbp+string], r13
0x18007268e  mov     [rbp+var_20], r13
0x180072692  mov     [rbp+arg_0], r13d
0x180072696  mov     rax, [rcx]
0x180072699  mov     rbx, [rax+80h]
0x1800726a0  xor     ecx, ecx; string
0x1800726a2  call    cs:__imp_WindowsDeleteString
0x1800726a8  mov     [rbp+var_18], r13
0x1800726ac  lea     rdx, [rbp+var_18]
0x1800726b0  mov     rcx, rdi
0x1800726b3  mov     rax, rbx
0x1800726b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800726bb  mov     ebx, eax
0x1800726bd  test    eax, eax
0x1800726bf  js      loc_18007289F
0x1800726c5  mov     rcx, [rbp+string]; string
0x1800726c9  call    cs:__imp_WindowsDeleteString
0x1800726cf  mov     [rbp+string], r13
0x1800726d3  mov     rcx, [rbp+arg_18]; string
0x1800726d7  call    cs:__imp_WindowsDeleteString
0x1800726dd  mov     [rbp+arg_18], r13
0x1800726e1  lea     r8, [rbp+string]; HSTRING *
0x1800726e5  lea     rdx, [rbp+arg_18]; HSTRING *
0x1800726e9  mov     rcx, rdi; struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *
0x1800726ec  call    ?GetImageColors@@YAJPEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAPEAUHSTRING__@@1@Z; GetImageColors(Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *,HSTRING__ * *,HSTRING__ * *)
0x1800726f1  mov     ebx, eax
0x1800726f3  test    eax, eax
0x1800726f5  js      loc_18007289F
0x1800726fb  mov     rax, [rdi]
0x1800726fe  mov     rbx, [rax+60h]
0x180072702  lea     rcx, [rbp+var_20]
0x180072706  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007270b  lea     rdx, [rbp+var_20]
0x18007270f  mov     rcx, rdi
0x180072712  mov     rax, rbx
0x180072715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007271a  mov     ebx, eax
0x18007271c  test    eax, eax
0x18007271e  js      loc_18007289F
0x180072724  mov     rcx, [rbp+var_20]
0x180072728  mov     rax, [rcx]
0x18007272b  lea     rdx, [rbp+arg_0]
0x18007272f  mov     rax, [rax+38h]
0x180072733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072738  mov     ebx, eax
0x18007273a  test    eax, eax
0x18007273c  js      loc_18007289F
0x180072742  mov     esi, r13d
0x180072745  mov     [rbp+var_28], r13
0x180072749  mov     [rbp+ppv], r13
0x18007274d  mov     ecx, [rbp+arg_0]; unsigned __int64
0x180072750  lea     r8, [rbp+ppv]; unsigned __int64 *
0x180072754  lea     edx, [r13+8]; unsigned __int64
0x180072758  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18007275d  mov     ebx, eax
0x18007275f  test    eax, eax
0x180072761  js      short loc_18007277A
0x180072763  lea     r9, [rbp+var_28]; void **
0x180072767  mov     r8, [rbp+ppv]; unsigned __int64
0x18007276b  lea     edx, [r13+1]; unsigned int
0x18007276f  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180072774  mov     ebx, eax
0x180072776  mov     rsi, [rbp+var_28]
0x18007277a  mov     r14d, r13d
0x18007277d  jmp     loc_18007288B
0x180072782  mov     eax, [rbp+arg_0]
0x180072785  cmp     r14d, eax
0x180072788  jnb     loc_1800728E2
0x18007278e  mov     [rbp+ppv], r13
0x180072792  lea     rcx, [rbp+ppv]
0x180072796  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007279b  lea     rdx, [rbp+ppv]; ppv
0x18007279f  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1800727a6  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800727ac  mov     ebx, eax
0x1800727ae  test    eax, eax
0x1800727b0  js      loc_18007287F
0x1800727b6  mov     r8, [rbp+var_18]; HSTRING
0x1800727ba  lea     rdx, PKEY_ItemNameDisplay; struct _tagpropertykey *
0x1800727c1  mov     rcx, [rbp+ppv]; struct IPropertyStore *
0x1800727c5  call    ?AddStringToPropertyStore@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAUHSTRING__@@@Z; AddStringToPropertyStore(IPropertyStore *,_tagpropertykey const &,HSTRING__ *)
0x1800727ca  mov     r8, [rbp+var_18]; HSTRING
0x1800727ce  lea     rdx, PKEY_Tile_LongDisplayName; struct _tagpropertykey *
0x1800727d5  mov     rcx, [rbp+ppv]; struct IPropertyStore *
0x1800727d9  call    ?AddStringToPropertyStore@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAUHSTRING__@@@Z; AddStringToPropertyStore(IPropertyStore *,_tagpropertykey const &,HSTRING__ *)
0x1800727de  mov     r8, [rbp+arg_18]; HSTRING
0x1800727e2  lea     rdx, PKEY_Tile_Background; struct _tagpropertykey *
0x1800727e9  mov     rcx, [rbp+ppv]; struct IPropertyStore *
0x1800727ed  call    ?AddStringToPropertyStore@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAUHSTRING__@@@Z; AddStringToPropertyStore(IPropertyStore *,_tagpropertykey const &,HSTRING__ *)
0x1800727f2  mov     r8, [rbp+string]; HSTRING
0x1800727f6  lea     rdx, PKEY_Tile_Foreground; struct _tagpropertykey *
0x1800727fd  mov     rcx, [rbp+ppv]; struct IPropertyStore *
0x180072801  call    ?AddStringToPropertyStore@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAUHSTRING__@@@Z; AddStringToPropertyStore(IPropertyStore *,_tagpropertykey const &,HSTRING__ *)
0x180072806  mov     [rbp+var_28], r13
0x18007280a  mov     rdi, [rbp+var_20]
0x18007280e  mov     rax, [rdi]
0x180072811  mov     rbx, [rax+30h]
0x180072815  xor     ecx, ecx; string
0x180072817  call    cs:__imp_WindowsDeleteString
0x18007281d  mov     [rbp+var_28], r13
0x180072821  lea     r8, [rbp+var_28]
0x180072825  mov     edx, r14d
0x180072828  mov     rcx, rdi
0x18007282b  mov     rax, rbx
0x18007282e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072833  mov     ebx, eax
0x180072835  test    eax, eax
0x180072837  js      short loc_18007284E
0x180072839  mov     r8, [rbp+var_28]; HSTRING
0x18007283d  lea     rdx, PKEY_AppUserModel_PackageRelativeApplicationID; struct _tagpropertykey *
0x180072844  mov     rcx, [rbp+ppv]; struct IPropertyStore *
0x180072848  call    ?AddStringToPropertyStore@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAUHSTRING__@@@Z; AddStringToPropertyStore(IPropertyStore *,_tagpropertykey const &,HSTRING__ *)
0x18007284d  nop
0x18007284e  mov     rcx, [rbp+var_28]; string
0x180072852  call    cs:__imp_WindowsDeleteString
0x180072858  mov     [rbp+var_28], r13
0x18007285c  test    ebx, ebx
0x18007285e  js      short loc_18007287F
0x180072860  mov     rcx, [rbp+ppv]
0x180072864  mov     rax, [rcx]
0x180072867  mov     rax, [rax+38h]
0x18007286b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072870  mov     rcx, [rbp+ppv]
0x180072874  mov     [rbp+ppv], r13
0x180072878  mov     eax, r14d
0x18007287b  mov     [rsi+rax*8], rcx
0x18007287f  lea     rcx, [rbp+ppv]
0x180072883  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072888  inc     r14d
0x18007288b  test    ebx, ebx
0x18007288d  jns     loc_180072782
0x180072893  mov     edx, [rbp+arg_0]; unsigned int
0x180072896  mov     rcx, rsi; struct IPropertyStore **
0x180072899  call    ?ReleasePropertyStore@@YAXPEAPEAUIPropertyStore@@I@Z; ReleasePropertyStore(IPropertyStore * *,uint)
0x18007289e  nop
0x18007289f  lea     rcx, [rbp+var_20]
0x1800728a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800728a8  nop
0x1800728a9  mov     rcx, [rbp+string]; string
0x1800728ad  call    cs:__imp_WindowsDeleteString
0x1800728b3  mov     [rbp+string], r13
0x1800728b7  mov     rcx, [rbp+arg_18]; string
0x1800728bb  call    cs:__imp_WindowsDeleteString
0x1800728c1  mov     [rbp+arg_18], r13
0x1800728c5  mov     rcx, [rbp+var_18]; string
0x1800728c9  call    cs:__imp_WindowsDeleteString
0x1800728cf  mov     eax, ebx
0x1800728d1  add     rsp, 48h
0x1800728d5  pop     r15
0x1800728d7  pop     r14
0x1800728d9  pop     r13
0x1800728db  pop     r12
0x1800728dd  pop     rdi
0x1800728de  pop     rsi
0x1800728df  pop     rbx
0x1800728e0  pop     rbp
0x1800728e1  retn
0x1800728e2  mov     [r12], rsi
0x1800728e6  mov     [r15], eax
0x1800728e9  jmp     short loc_18007289F
```
