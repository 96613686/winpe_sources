# CPhotoThumbnailProvider::CPhotoThumbnailProvider(void)

- ea: `0x18000226c`
- end: `0x180002309`
- name: `??0CPhotoThumbnailProvider@@QEAA@XZ`
- size: `157`
- prototype: `CPhotoThumbnailProvider *__fastcall(CPhotoThumbnailProvider *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000214c`

## callees

- `0x18000226c`
- `0x18000aad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800022b3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800022b3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800022d8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800022d8`

## pseudocode

```c
CPhotoThumbnailProvider *__fastcall CPhotoThumbnailProvider::CPhotoThumbnailProvider(CPhotoThumbnailProvider *this)
{
  struct IUnknown **ppv; // rdi

  *((_DWORD *)this + 6) = 0;
  ppv = (struct IUnknown **)((char *)this + 128);
  *((_OWORD *)this + 2) = 0;
  *((_OWORD *)this + 3) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_BYTE *)this + 72) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
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
0x18000226c  mov     [rsp+arg_0], rbx
0x180002271  push    rdi
0x180002272  sub     rsp, 30h
0x180002276  mov     dword ptr [rcx+18h], 0
0x18000227d  lea     rdi, [rcx+80h]
0x180002284  xor     eax, eax
0x180002286  xorps   xmm0, xmm0
0x180002289  movups  xmmword ptr [rcx+20h], xmm0
0x18000228d  mov     rbx, rcx
0x180002290  movups  xmmword ptr [rcx+30h], xmm0
0x180002294  mov     [rcx+40h], rax
0x180002298  mov     [rcx+48h], al
0x18000229b  mov     [rcx+50h], eax
0x18000229e  mov     [rdi], rax
0x1800022a1  mov     [rcx+88h], rax
0x1800022a8  mov     [rcx+90h], rax
0x1800022af  add     rcx, 58h ; 'X'; lpCriticalSection
0x1800022b3  call    cs:__imp_InitializeCriticalSection
0x1800022ba  nop     dword ptr [rax+rax+00h]
0x1800022bf  xor     edx, edx; pUnkOuter
0x1800022c1  mov     [rsp+38h+ppv], rdi; ppv
0x1800022c6  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x1800022cd  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x1800022d4  lea     r8d, [rdx+1]; dwClsContext
0x1800022d8  call    cs:__imp_CoCreateInstance
0x1800022df  nop     dword ptr [rax+rax+00h]
0x1800022e4  test    eax, eax
0x1800022e6  js      short loc_1800022F7
0x1800022e8  mov     rax, rbx
0x1800022eb  mov     rbx, [rsp+38h+arg_0]
0x1800022f0  add     rsp, 30h
0x1800022f4  pop     rdi
0x1800022f5  retn
0x1800022f7  cmp     qword ptr [rdi], 0
0x1800022fb  jz      short loc_1800022E8
0x1800022fd  xor     edx, edx; struct IUnknown *
0x1800022ff  mov     rcx, rdi; struct IUnknown **
0x180002302  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180002307  jmp     short loc_1800022E8
```
