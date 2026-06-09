# CreateWicImageTile(ushort const *,uint,DirectUI::Element * *)

- ea: `0x1800d6f28`
- end: `0x1800d71e1`
- name: `?CreateWicImageTile@@YAJPEBGIPEAPEAVElement@DirectUI@@@Z`
- size: `697`
- prototype: `int(const unsigned __int16 *, unsigned int, struct DirectUI::Element **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800d6038`
- `0x1800d6348`

## callees

- `0x180013244`
- `0x18001527c`
- `0x180022480`
- `0x180050ba0`
- `0x18007a68c`
- `0x18008ce90`
- `0x1800d0858`
- `0x1800d6f28`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d6ffa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d6ffa`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x1800d6f78`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x1800d6f78`
- `DUI70!?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800d6fa4`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x1800d6f92`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x1800d6f92`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d71b3`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d71b3`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800d7198`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800d7198`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800d6fb9`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800d6fb9`

## pseudocode

```c
__int64 __fastcall CreateWicImageTile(const unsigned __int16 *a1, unsigned int a2, struct DirectUI::Element **a3)
{
  HRESULT Instance; // ebx
  struct DirectUI::Value *String; // rax
  DirectUI::Value *v8; // rsi
  bool v9; // cl
  unsigned int v10; // r9d
  struct IWICBitmapSource *v11; // rbx
  __int64 v12; // r8
  struct IWICBitmapSource *v14; // [rsp+30h] [rbp-D0h] BYREF
  struct IWICImagingFactory *ppv; // [rsp+38h] [rbp-C8h] BYREF
  HBITMAP v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+4Ch] [rbp-B4h] BYREF
  struct IWICBitmapSource *v19; // [rsp+50h] [rbp-B0h] BYREF
  struct DirectUI::Element *v20; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v21[264]; // [rsp+60h] [rbp-A0h] BYREF

  *a3 = 0;
  v20 = 0;
  Instance = DirectUI::Element::Create(0, 0, 0, &v20);
  if ( Instance >= 0 )
  {
    Instance = -2147024882;
    String = DirectUI::Value::CreateString(a1, 0);
    v8 = String;
    if ( !String )
      goto LABEL_22;
    Instance = DirectUI::Element::SetValue(
                 v20,
                 (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::CustomProp,
                 1,
                 String);
    if ( Instance < 0 )
    {
LABEL_20:
      DirectUI::Value::Release(v8);
      if ( Instance >= 0 )
      {
        *a3 = v20;
        return (unsigned int)Instance;
      }
LABEL_22:
      DirectUI::Element::Destroy(v20, 0);
      return (unsigned int)Instance;
    }
    ppv = 0;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
    Instance = CoCreateInstance(
                 &CLSID_WICImagingFactory2,
                 0,
                 1u,
                 &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                 (LPVOID *)&ppv);
    if ( Instance < 0 )
    {
LABEL_19:
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
      goto LABEL_20;
    }
    v14 = 0;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v14);
    if ( (int)LoadImageWithWIC(ppv, a1, 0, &v14) < 0
      && ((Instance = _GetDefaultUserPicturePathBySize(v9, a2, v21, v10), Instance < 0)
       || (Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v14),
           Instance = LoadImageWithWIC(ppv, v21, 0, &v14),
           Instance < 0))
      || (v17 = 0,
          v18 = 0,
          Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, int *, int *))v14->lpVtbl->GetSize)(
                       v14,
                       &v17,
                       &v18),
          Instance < 0) )
    {
LABEL_18:
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v14);
      goto LABEL_19;
    }
    v11 = 0;
    v19 = 0;
    if ( v17 == a2 && v18 == a2 )
    {
      if ( v14 )
      {
        v11 = v14;
        ((void (__fastcall *)(struct IWICBitmapSource *))v14->lpVtbl->AddRef)(v14);
        v16 = 0;
        v19 = v11;
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v16);
      }
    }
    else
    {
      LODWORD(v16) = a2;
      HIDWORD(v16) = a2;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v19);
      Instance = ScaleImageWithWIC(ppv, v14, (struct tagSIZE)v16, 1, &v19);
      if ( Instance < 0 )
      {
LABEL_17:
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v19);
        goto LABEL_18;
      }
      v11 = v19;
    }
    v16 = 0;
    Instance = ConvertWICBitmapToHBITMAP(ppv, v11, &v16);
    if ( Instance >= 0 )
    {
      LOBYTE(v12) = 1;
      Instance = DUI_SetElementBitmap(v20, v16, v12);
    }
    goto LABEL_17;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800d6f28  mov     [rsp-8+arg_18], rbx
0x1800d6f2d  push    rbp
0x1800d6f2e  push    rsi
0x1800d6f2f  push    rdi
0x1800d6f30  push    r14
0x1800d6f32  push    r15
0x1800d6f34  lea     rbp, [rsp-180h]
0x1800d6f3c  sub     rsp, 280h
0x1800d6f43  mov     rax, cs:__security_cookie
0x1800d6f4a  xor     rax, rsp
0x1800d6f4d  mov     [rbp+1A0h+var_30], rax
0x1800d6f54  mov     r15, r8
0x1800d6f57  mov     qword ptr [r8], 0
0x1800d6f5e  mov     edi, edx
0x1800d6f60  mov     [rsp+2A0h+var_248], 0
0x1800d6f69  mov     r14, rcx
0x1800d6f6c  lea     r9, [rsp+2A0h+var_248]
0x1800d6f71  xor     r8d, r8d
0x1800d6f74  xor     edx, edx
0x1800d6f76  xor     ecx, ecx
0x1800d6f78  call    cs:__imp_?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z; DirectUI::Element::Create(uint,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1800d6f7e  mov     ebx, eax
0x1800d6f80  test    eax, eax
0x1800d6f82  js      loc_1800D71B9
0x1800d6f88  xor     edx, edx
0x1800d6f8a  mov     rcx, r14
0x1800d6f8d  mov     ebx, 8007000Eh
0x1800d6f92  call    cs:__imp_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z; DirectUI::Value::CreateString(ushort const *,HINSTANCE__ *)
0x1800d6f98  mov     rsi, rax
0x1800d6f9b  test    rax, rax
0x1800d6f9e  jz      loc_1800D71AC
0x1800d6fa4  mov     rdx, cs:__imp_?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::CustomProp(void)
0x1800d6fab  mov     r9, rax
0x1800d6fae  mov     rcx, [rsp+2A0h+var_248]
0x1800d6fb3  mov     r8d, 1
0x1800d6fb9  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800d6fbf  mov     ebx, eax
0x1800d6fc1  test    eax, eax
0x1800d6fc3  js      loc_1800D7195
0x1800d6fc9  lea     rcx, [rsp+2A0h+var_268]
0x1800d6fce  mov     [rsp+2A0h+var_268], 0
0x1800d6fd7  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800d6fdc  xor     edx, edx; pUnkOuter
0x1800d6fde  lea     rax, [rsp+2A0h+var_268]
0x1800d6fe3  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x1800d6fea  mov     [rsp+2A0h+ppv], rax; ppv
0x1800d6fef  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x1800d6ff6  lea     r8d, [rdx+1]; dwClsContext
0x1800d6ffa  call    cs:__imp_CoCreateInstance
0x1800d7000  mov     ebx, eax
0x1800d7002  test    eax, eax
0x1800d7004  js      loc_1800D718B
0x1800d700a  lea     rcx, [rsp+2A0h+var_270]
0x1800d700f  mov     [rsp+2A0h+var_270], 0
0x1800d7018  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800d701d  mov     rcx, [rsp+2A0h+var_268]
0x1800d7022  lea     r9, [rsp+2A0h+var_270]
0x1800d7027  xor     r8d, r8d
0x1800d702a  mov     [rsp+2A0h+ppv], 0
0x1800d7033  mov     rdx, r14
0x1800d7036  call    ?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEBGW4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAU_GUID@@PEAPEAUIWICBitmapFrameDecode@@@Z; LoadImageWithWIC(IWICImagingFactory *,ushort const *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,_GUID *,IWICBitmapFrameDecode * *)
0x1800d703b  test    eax, eax
0x1800d703d  jns     short loc_1800D7089
0x1800d703f  lea     r8, [rsp+2A0h+var_240]; unsigned __int16 *
0x1800d7044  mov     edx, edi; unsigned int
0x1800d7046  call    ?_GetDefaultUserPicturePathBySize@@YAJ_NIPEAGK@Z; _GetDefaultUserPicturePathBySize(bool,uint,ushort *,ulong)
0x1800d704b  mov     ebx, eax
0x1800d704d  test    eax, eax
0x1800d704f  js      loc_1800D7181
0x1800d7055  lea     rcx, [rsp+2A0h+var_270]
0x1800d705a  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800d705f  mov     rcx, [rsp+2A0h+var_268]
0x1800d7064  lea     r9, [rsp+2A0h+var_270]
0x1800d7069  xor     r8d, r8d
0x1800d706c  mov     [rsp+2A0h+ppv], 0
0x1800d7075  lea     rdx, [rsp+2A0h+var_240]
0x1800d707a  call    ?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEBGW4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAU_GUID@@PEAPEAUIWICBitmapFrameDecode@@@Z; LoadImageWithWIC(IWICImagingFactory *,ushort const *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,_GUID *,IWICBitmapFrameDecode * *)
0x1800d707f  mov     ebx, eax
0x1800d7081  test    eax, eax
0x1800d7083  js      loc_1800D7181
0x1800d7089  mov     rcx, [rsp+2A0h+var_270]
0x1800d708e  lea     r8, [rsp+2A0h+var_254]
0x1800d7093  mov     [rsp+2A0h+var_258], 0
0x1800d709b  lea     rdx, [rsp+2A0h+var_258]
0x1800d70a0  mov     [rsp+2A0h+var_254], 0
0x1800d70a8  mov     rax, [rcx]
0x1800d70ab  mov     rax, [rax+18h]
0x1800d70af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d70b4  mov     ebx, eax
0x1800d70b6  test    eax, eax
0x1800d70b8  js      loc_1800D7181
0x1800d70be  xor     ebx, ebx
0x1800d70c0  mov     [rsp+2A0h+var_250], rbx
0x1800d70c5  cmp     [rsp+2A0h+var_258], edi
0x1800d70c9  jnz     short loc_1800D7104
0x1800d70cb  cmp     [rsp+2A0h+var_254], edi
0x1800d70cf  jnz     short loc_1800D7104
0x1800d70d1  mov     rcx, [rsp+2A0h+var_270]
0x1800d70d6  test    rcx, rcx
0x1800d70d9  jz      short loc_1800D7142
0x1800d70db  mov     rax, [rcx]
0x1800d70de  mov     rbx, rcx
0x1800d70e1  mov     rax, [rax+8]
0x1800d70e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d70ea  lea     rcx, [rsp+2A0h+var_260]
0x1800d70ef  mov     [rsp+2A0h+var_260], 0
0x1800d70f8  mov     [rsp+2A0h+var_250], rbx
0x1800d70fd  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800d7102  jmp     short loc_1800D7142
0x1800d7104  lea     rcx, [rsp+2A0h+var_250]
0x1800d7109  mov     dword ptr [rsp+2A0h+var_260], edi
0x1800d710d  mov     dword ptr [rsp+2A0h+var_260+4], edi
0x1800d7111  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800d7116  mov     r8, [rsp+2A0h+var_260]; struct tagSIZE
0x1800d711b  lea     rax, [rsp+2A0h+var_250]
0x1800d7120  mov     rdx, [rsp+2A0h+var_270]; struct IWICBitmapSource *
0x1800d7125  mov     r9b, 1; bool
0x1800d7128  mov     rcx, [rsp+2A0h+var_268]; struct IWICImagingFactory *
0x1800d712d  mov     [rsp+2A0h+ppv], rax; struct IWICBitmapSource **
0x1800d7132  call    ?ScaleImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@UtagSIZE@@_NPEAPEAU2@@Z; ScaleImageWithWIC(IWICImagingFactory *,IWICBitmapSource *,tagSIZE,bool,IWICBitmapSource * *)
0x1800d7137  mov     ebx, eax
0x1800d7139  test    eax, eax
0x1800d713b  js      short loc_1800D7177
0x1800d713d  mov     rbx, [rsp+2A0h+var_250]
0x1800d7142  mov     rcx, [rsp+2A0h+var_268]; struct IWICImagingFactory *
0x1800d7147  lea     r8, [rsp+2A0h+var_260]; HBITMAP *
0x1800d714c  mov     rdx, rbx; struct IWICBitmapSource *
0x1800d714f  mov     [rsp+2A0h+var_260], 0
0x1800d7158  call    ?ConvertWICBitmapToHBITMAP@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z; ConvertWICBitmapToHBITMAP(IWICImagingFactory *,IWICBitmapSource *,HBITMAP__ * *)
0x1800d715d  mov     ebx, eax
0x1800d715f  test    eax, eax
0x1800d7161  js      short loc_1800D7177
0x1800d7163  mov     rdx, [rsp+2A0h+var_260]
0x1800d7168  mov     r8b, 1
0x1800d716b  mov     rcx, [rsp+2A0h+var_248]
0x1800d7170  call    ?DUI_SetElementBitmap@@YAJPEAVElement@DirectUI@@PEAUHBITMAP__@@EIW4ImageRtlMode@@_N@Z; DUI_SetElementBitmap(DirectUI::Element *,HBITMAP__ *,uchar,uint,ImageRtlMode,bool)
0x1800d7175  mov     ebx, eax
0x1800d7177  lea     rcx, [rsp+2A0h+var_250]
0x1800d717c  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800d7181  lea     rcx, [rsp+2A0h+var_270]
0x1800d7186  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800d718b  lea     rcx, [rsp+2A0h+var_268]
0x1800d7190  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800d7195  mov     rcx, rsi
0x1800d7198  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800d719e  test    ebx, ebx
0x1800d71a0  js      short loc_1800D71AC
0x1800d71a2  mov     rax, [rsp+2A0h+var_248]
0x1800d71a7  mov     [r15], rax
0x1800d71aa  jmp     short loc_1800D71B9
0x1800d71ac  mov     rcx, [rsp+2A0h+var_248]
0x1800d71b1  xor     edx, edx
0x1800d71b3  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800d71b9  mov     eax, ebx
0x1800d71bb  mov     rcx, [rbp+1A0h+var_30]
0x1800d71c2  xor     rcx, rsp; StackCookie
0x1800d71c5  call    __security_check_cookie
0x1800d71ca  mov     rbx, [rsp+2A0h+arg_18]
0x1800d71d2  add     rsp, 280h
0x1800d71d9  pop     r15
0x1800d71db  pop     r14
0x1800d71dd  pop     rdi
0x1800d71de  pop     rsi
0x1800d71df  pop     rbp
0x1800d71e0  retn
```
