# CPhotoExtractImage::CPhotoExtractImage(void)

- ea: `0x180011780`
- end: `0x180011841`
- name: `??0CPhotoExtractImage@@QEAA@XZ`
- size: `193`
- prototype: `CPhotoExtractImage *__fastcall(CPhotoExtractImage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017b9c`

## callees

- `0x18000aad0`
- `0x180011780`
- `0x180017408`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800117e9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800117e9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001180e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001180e`

## pseudocode

```c
CPhotoExtractImage *__fastcall CPhotoExtractImage::CPhotoExtractImage(CPhotoExtractImage *this)
{
  struct IUnknown **ppv; // rdi

  ppv = (struct IUnknown **)((char *)this + 664);
  *((_DWORD *)this + 8) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *(_OWORD *)((char *)this + 56) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_BYTE *)this + 80) = 0;
  *((_DWORD *)this + 154) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 76) = 0;
  memset_0((char *)this + 88, 0, 0x208u);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
  if ( CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, (LPVOID *)ppv) < 0
    && *ppv )
  {
    ATL::AtlComPtrAssign(ppv, 0);
  }
  return this;
}

```

## disassembly

```asm
0x180011780  mov     [rsp+arg_0], rbx
0x180011785  mov     [rsp+arg_8], rsi
0x18001178a  push    rdi
0x18001178b  sub     rsp, 30h
0x18001178f  xor     esi, esi
0x180011791  lea     rdi, [rcx+298h]
0x180011798  mov     [rcx+20h], esi
0x18001179b  xorps   xmm0, xmm0
0x18001179e  movups  xmmword ptr [rcx+28h], xmm0
0x1800117a2  xor     eax, eax
0x1800117a4  mov     rbx, rcx
0x1800117a7  movups  xmmword ptr [rcx+38h], xmm0
0x1800117ab  mov     [rcx+48h], rax
0x1800117af  xor     edx, edx; Val
0x1800117b1  mov     [rcx+50h], sil
0x1800117b5  mov     r8d, 208h; Size
0x1800117bb  mov     [rcx+268h], esi
0x1800117c1  mov     [rdi], rsi
0x1800117c4  mov     [rcx+2A0h], rsi
0x1800117cb  mov     [rcx+2A8h], rsi
0x1800117d2  mov     [rcx+260h], rsi
0x1800117d9  add     rcx, 58h ; 'X'; void *
0x1800117dd  call    memset_0
0x1800117e2  lea     rcx, [rbx+270h]; lpCriticalSection
0x1800117e9  call    cs:__imp_InitializeCriticalSection
0x1800117f0  nop     dword ptr [rax+rax+00h]
0x1800117f5  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x1800117fc  mov     [rsp+38h+ppv], rdi; ppv
0x180011801  xor     edx, edx; pUnkOuter
0x180011803  lea     r8d, [rsi+1]; dwClsContext
0x180011807  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18001180e  call    cs:__imp_CoCreateInstance
0x180011815  nop     dword ptr [rax+rax+00h]
0x18001181a  test    eax, eax
0x18001181c  jns     short loc_18001182D
0x18001181e  cmp     [rdi], rsi
0x180011821  jz      short loc_18001182D
0x180011823  xor     edx, edx; struct IUnknown *
0x180011825  mov     rcx, rdi; struct IUnknown **
0x180011828  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001182d  mov     rsi, [rsp+38h+arg_8]
0x180011832  mov     rax, rbx
0x180011835  mov     rbx, [rsp+38h+arg_0]
0x18001183a  add     rsp, 30h
0x18001183e  pop     rdi
0x18001183f  retn
```
