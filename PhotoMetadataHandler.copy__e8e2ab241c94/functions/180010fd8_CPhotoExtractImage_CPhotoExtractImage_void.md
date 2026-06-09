# CPhotoExtractImage::CPhotoExtractImage(void)

- ea: `0x180010fd8`
- end: `0x18001108c`
- name: `??0CPhotoExtractImage@@QEAA@XZ`
- size: `180`
- prototype: `CPhotoExtractImage *__fastcall(CPhotoExtractImage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017128`

## callees

- `0x18000a620`
- `0x180010fd8`
- `0x1800169b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011041`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011041`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011060`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011060`

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
0x180010fd8  mov     [rsp+arg_0], rbx
0x180010fdd  mov     [rsp+arg_8], rsi
0x180010fe2  push    rdi
0x180010fe3  sub     rsp, 30h
0x180010fe7  xor     esi, esi
0x180010fe9  lea     rdi, [rcx+298h]
0x180010ff0  mov     [rcx+20h], esi
0x180010ff3  xorps   xmm0, xmm0
0x180010ff6  movups  xmmword ptr [rcx+28h], xmm0
0x180010ffa  xor     eax, eax
0x180010ffc  mov     rbx, rcx
0x180010fff  movups  xmmword ptr [rcx+38h], xmm0
0x180011003  mov     [rcx+48h], rax
0x180011007  xor     edx, edx; Val
0x180011009  mov     [rcx+50h], sil
0x18001100d  mov     r8d, 208h; Size
0x180011013  mov     [rcx+268h], esi
0x180011019  mov     [rdi], rsi
0x18001101c  mov     [rcx+2A0h], rsi
0x180011023  mov     [rcx+2A8h], rsi
0x18001102a  mov     [rcx+260h], rsi
0x180011031  add     rcx, 58h ; 'X'; void *
0x180011035  call    memset_0
0x18001103a  lea     rcx, [rbx+270h]; lpCriticalSection
0x180011041  call    cs:__imp_InitializeCriticalSection
0x180011047  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18001104e  mov     [rsp+38h+ppv], rdi; ppv
0x180011053  xor     edx, edx; pUnkOuter
0x180011055  lea     r8d, [rsi+1]; dwClsContext
0x180011059  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180011060  call    cs:__imp_CoCreateInstance
0x180011066  test    eax, eax
0x180011068  jns     short loc_180011079
0x18001106a  cmp     [rdi], rsi
0x18001106d  jz      short loc_180011079
0x18001106f  xor     edx, edx; struct IUnknown *
0x180011071  mov     rcx, rdi; struct IUnknown **
0x180011074  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180011079  mov     rsi, [rsp+38h+arg_8]
0x18001107e  mov     rax, rbx
0x180011081  mov     rbx, [rsp+38h+arg_0]
0x180011086  add     rsp, 30h
0x18001108a  pop     rdi
0x18001108b  retn
```
