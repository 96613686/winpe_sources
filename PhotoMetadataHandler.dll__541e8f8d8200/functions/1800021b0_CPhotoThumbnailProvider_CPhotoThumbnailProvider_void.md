# CPhotoThumbnailProvider::CPhotoThumbnailProvider(void)

- ea: `0x1800021b0`
- end: `0x180002240`
- name: `??0CPhotoThumbnailProvider@@QEAA@XZ`
- size: `144`
- prototype: `CPhotoThumbnailProvider *__fastcall(CPhotoThumbnailProvider *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002098`

## callees

- `0x1800021b0`
- `0x18000a620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800021f7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800021f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002216`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002216`

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
0x1800021b0  mov     [rsp+arg_0], rbx
0x1800021b5  push    rdi
0x1800021b6  sub     rsp, 30h
0x1800021ba  mov     dword ptr [rcx+18h], 0
0x1800021c1  lea     rdi, [rcx+80h]
0x1800021c8  xor     eax, eax
0x1800021ca  xorps   xmm0, xmm0
0x1800021cd  movups  xmmword ptr [rcx+20h], xmm0
0x1800021d1  mov     rbx, rcx
0x1800021d4  movups  xmmword ptr [rcx+30h], xmm0
0x1800021d8  mov     [rcx+40h], rax
0x1800021dc  mov     [rcx+48h], al
0x1800021df  mov     [rcx+50h], eax
0x1800021e2  mov     [rdi], rax
0x1800021e5  mov     [rcx+88h], rax
0x1800021ec  mov     [rcx+90h], rax
0x1800021f3  add     rcx, 58h ; 'X'; lpCriticalSection
0x1800021f7  call    cs:__imp_InitializeCriticalSection
0x1800021fd  xor     edx, edx; pUnkOuter
0x1800021ff  mov     [rsp+38h+ppv], rdi; ppv
0x180002204  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18000220b  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180002212  lea     r8d, [rdx+1]; dwClsContext
0x180002216  call    cs:__imp_CoCreateInstance
0x18000221c  test    eax, eax
0x18000221e  js      short loc_18000222E
0x180002220  mov     rax, rbx
0x180002223  mov     rbx, [rsp+38h+arg_0]
0x180002228  add     rsp, 30h
0x18000222c  pop     rdi
0x18000222d  retn
0x18000222e  cmp     qword ptr [rdi], 0
0x180002232  jz      short loc_180002220
0x180002234  xor     edx, edx; struct IUnknown *
0x180002236  mov     rcx, rdi; struct IUnknown **
0x180002239  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000223e  jmp     short loc_180002220
```
