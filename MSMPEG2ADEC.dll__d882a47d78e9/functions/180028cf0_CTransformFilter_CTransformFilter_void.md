# CTransformFilter::~CTransformFilter(void)

- ea: `0x180028cf0`
- end: `0x180028d68`
- name: `??1CTransformFilter@@UEAA@XZ`
- size: `120`
- prototype: `void __fastcall(CTransformFilter *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000aa40`
- `0x18000aca0`
- `0x180033760`

## callees

- `0x1800261f4`
- `0x180028cf0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028d3c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028d4f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028d3c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028d4f`

## pseudocode

```c
void __fastcall CTransformFilter::~CTransformFilter(CTransformFilter *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  v2 = *((_QWORD *)this + 27);
  if ( v2 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 24LL))(v2, 1);
  v3 = *((_QWORD *)this + 28);
  if ( v3 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 24LL))(v3, 1);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  CBaseFilter::~CBaseFilter(this);
}

```

## disassembly

```asm
0x180028cf0  push    rbx
0x180028cf2  sub     rsp, 20h
0x180028cf6  mov     rbx, rcx
0x180028cf9  mov     rcx, [rcx+0D8h]
0x180028d00  test    rcx, rcx
0x180028d03  jz      short loc_180028D17
0x180028d05  mov     rax, [rcx]
0x180028d08  mov     edx, 1
0x180028d0d  mov     rax, [rax+18h]
0x180028d11  call    cs:__guard_dispatch_icall_fptr
0x180028d17  mov     rcx, [rbx+0E0h]
0x180028d1e  test    rcx, rcx
0x180028d21  jz      short loc_180028D35
0x180028d23  mov     rax, [rcx]
0x180028d26  mov     edx, 1
0x180028d2b  mov     rax, [rax+18h]
0x180028d2f  call    cs:__guard_dispatch_icall_fptr
0x180028d35  lea     rcx, [rbx+0B0h]; lpCriticalSection
0x180028d3c  call    cs:__imp_DeleteCriticalSection
0x180028d43  nop     dword ptr [rax+rax+00h]
0x180028d48  lea     rcx, [rbx+88h]; lpCriticalSection
0x180028d4f  call    cs:__imp_DeleteCriticalSection
0x180028d56  nop     dword ptr [rax+rax+00h]
0x180028d5b  mov     rcx, rbx; this
0x180028d5e  add     rsp, 20h
0x180028d62  pop     rbx
0x180028d63  jmp     ??1CBaseFilter@@UEAA@XZ; CBaseFilter::~CBaseFilter(void)
```
