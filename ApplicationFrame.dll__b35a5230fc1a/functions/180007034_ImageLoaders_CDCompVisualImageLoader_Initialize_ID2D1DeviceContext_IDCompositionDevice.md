# ImageLoaders::CDCompVisualImageLoader::Initialize(ID2D1DeviceContext *,IDCompositionDevice *)

- ea: `0x180007034`
- end: `0x1800070f0`
- name: `?Initialize@CDCompVisualImageLoader@ImageLoaders@@QEAAJPEAUID2D1DeviceContext@@PEAUIDCompositionDevice@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(ImageLoaders::CDCompVisualImageLoader *__hidden this, struct ID2D1DeviceContext *, struct IDCompositionDevice *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800067e8`

## callees

- `0x180003e30`
- `0x180004c98`
- `0x180007034`
- `0x180040270`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007064`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007064`

## string_xrefs

- `0x1800070d8`: `onecoreuap\shell\onecore\libs\imageloaders\dcompvisualimageloader.cpp`

## pseudocode

```c
__int64 __fastcall ImageLoaders::CDCompVisualImageLoader::Initialize(
        LPVOID *this,
        struct ID2D1DeviceContext *a2,
        struct IDCompositionDevice *a3)
{
  HRESULT Instance; // eax
  unsigned int v7; // ebp
  int ppv; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  struct ID2D1DeviceContext *v11; // [rsp+60h] [rbp+8h] BYREF

  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(this);
  Instance = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, this);
  v7 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecoreuap\\shell\\onecore\\libs\\imageloaders\\dcompvisualimageloader.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    return v7;
  }
  else
  {
    if ( this[1] != a2 )
    {
      v11 = a2;
      Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(&v11);
      v11 = (struct ID2D1DeviceContext *)this[1];
      this[1] = a2;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v11);
    }
    if ( this[2] != a3 )
    {
      v11 = a3;
      Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(&v11);
      v11 = (struct ID2D1DeviceContext *)this[2];
      this[2] = a3;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v11);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180007034  push    rbx
0x180007036  push    rbp
0x180007037  push    rsi
0x180007038  push    rdi
0x180007039  sub     rsp, 38h
0x18000703d  mov     rdi, r8
0x180007040  mov     rsi, rdx
0x180007043  mov     rbx, rcx
0x180007046  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000704b  xor     edx, edx; pUnkOuter
0x18000704d  mov     qword ptr [rsp+58h+ppv], rbx; int
0x180007052  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180007059  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180007060  lea     r8d, [rdx+1]; dwClsContext
0x180007064  call    cs:__imp_CoCreateInstance
0x18000706a  mov     ebp, eax
0x18000706c  test    eax, eax
0x18000706e  js      short loc_1800070D3
0x180007070  cmp     [rbx+8], rsi
0x180007074  jz      short loc_18000709C
0x180007076  lea     rcx, [rsp+58h+arg_0]
0x18000707b  mov     [rsp+58h+arg_0], rsi
0x180007080  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x180007085  mov     rax, [rbx+8]
0x180007089  lea     rcx, [rsp+58h+arg_0]
0x18000708e  mov     [rsp+58h+arg_0], rax
0x180007093  mov     [rbx+8], rsi
0x180007097  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000709c  cmp     [rbx+10h], rdi
0x1800070a0  jz      short loc_1800070C8
0x1800070a2  lea     rcx, [rsp+58h+arg_0]
0x1800070a7  mov     [rsp+58h+arg_0], rdi
0x1800070ac  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x1800070b1  mov     rax, [rbx+10h]
0x1800070b5  lea     rcx, [rsp+58h+arg_0]
0x1800070ba  mov     [rsp+58h+arg_0], rax
0x1800070bf  mov     [rbx+10h], rdi
0x1800070c3  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800070c8  xor     eax, eax
0x1800070ca  add     rsp, 38h
0x1800070ce  pop     rdi
0x1800070cf  pop     rsi
0x1800070d0  pop     rbp
0x1800070d1  pop     rbx
0x1800070d2  retn
0x1800070d3  mov     rcx, [rsp+58h]; this
0x1800070d8  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\onecore\\libs\\image"...
0x1800070df  mov     r9d, ebp; char *
0x1800070e2  mov     edx, 14h; void *
0x1800070e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070ec  mov     eax, ebp
0x1800070ee  jmp     short loc_1800070CA
```
