# D3DPresentEngine::D3DPresentEngine(CSampleSinkInputPinCallback *,long &)

- ea: `0x1800c06a4`
- end: `0x1800c0765`
- name: `??0D3DPresentEngine@@QEAA@PEAUCSampleSinkInputPinCallback@@AEAJ@Z`
- size: `193`
- prototype: `D3DPresentEngine *__fastcall(D3DPresentEngine *__hidden this, struct CSampleSinkInputPinCallback *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800bd358`

## callees

- `0x1800c06a4`
- `0x1800c09cc`
- `0x1800c0fa8`
- `0x1800c1184`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800c0703`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800c0703`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!SetRectEmpty` at `0x1800c0713`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!SetRectEmpty` at `0x1800c0713`
- `ext-ms-win-ntuser-window-l1-1-0!GetDesktopWindow` at `0x1800c071f`
- `ext-ms-win-ntuser-window-l1-1-0!GetDesktopWindow` at `0x1800c071f`

## pseudocode

```c
D3DPresentEngine *__fastcall D3DPresentEngine::D3DPresentEngine(
        D3DPresentEngine *this,
        struct CSampleSinkInputPinCallback *a2,
        int *a3)
{
  int v5; // eax

  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &D3DPresentEngine::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = a2;
  *((_QWORD *)this + 17) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  SetRectEmpty((LPRECT)((char *)this + 24));
  *((_QWORD *)this + 2) = GetDesktopWindow();
  D3DPresentEngine::UpdateDestRect(this);
  *(_OWORD *)((char *)this + 40) = 0;
  v5 = D3DPresentEngine::InitializeD3D(this);
  *a3 = v5;
  if ( v5 >= 0 )
    *a3 = D3DPresentEngine::CreateD3DDevice(this);
  return this;
}

```

## disassembly

```asm
0x1800c06a4  mov     [rsp+arg_0], rbx
0x1800c06a9  push    rdi
0x1800c06aa  sub     rsp, 20h
0x1800c06ae  lea     rax, ??_7D3DPresentEngine@@6B@; const D3DPresentEngine::`vftable'
0x1800c06b5  mov     dword ptr [rcx+8], 0
0x1800c06bc  mov     [rcx], rax
0x1800c06bf  mov     rbx, rcx
0x1800c06c2  mov     qword ptr [rcx+10h], 0
0x1800c06ca  mov     rdi, r8
0x1800c06cd  mov     qword ptr [rcx+60h], 0
0x1800c06d5  mov     qword ptr [rcx+68h], 0
0x1800c06dd  mov     qword ptr [rcx+70h], 0
0x1800c06e5  mov     qword ptr [rcx+78h], 0
0x1800c06ed  mov     [rcx+80h], rdx
0x1800c06f4  mov     qword ptr [rcx+88h], 0
0x1800c06ff  add     rcx, 38h ; '8'; lpCriticalSection
0x1800c0703  call    cs:__imp_InitializeCriticalSection
0x1800c070a  nop     dword ptr [rax+rax+00h]
0x1800c070f  lea     rcx, [rbx+18h]; lprc
0x1800c0713  call    cs:__imp_SetRectEmpty
0x1800c071a  nop     dword ptr [rax+rax+00h]
0x1800c071f  call    cs:__imp_GetDesktopWindow
0x1800c0726  nop     dword ptr [rax+rax+00h]
0x1800c072b  mov     rcx, rbx; this
0x1800c072e  mov     [rbx+10h], rax
0x1800c0732  call    ?UpdateDestRect@D3DPresentEngine@@IEAAJXZ; D3DPresentEngine::UpdateDestRect(void)
0x1800c0737  xorps   xmm0, xmm0
0x1800c073a  mov     rcx, rbx; this
0x1800c073d  movups  xmmword ptr [rbx+28h], xmm0
0x1800c0741  call    ?InitializeD3D@D3DPresentEngine@@IEAAJXZ; D3DPresentEngine::InitializeD3D(void)
0x1800c0746  mov     [rdi], eax
0x1800c0748  test    eax, eax
0x1800c074a  js      short loc_1800C0756
0x1800c074c  mov     rcx, rbx; this
0x1800c074f  call    ?CreateD3DDevice@D3DPresentEngine@@IEAAJXZ; D3DPresentEngine::CreateD3DDevice(void)
0x1800c0754  mov     [rdi], eax
0x1800c0756  mov     rax, rbx
0x1800c0759  mov     rbx, [rsp+28h+arg_0]
0x1800c075e  add     rsp, 20h
0x1800c0762  pop     rdi
0x1800c0763  retn
```
