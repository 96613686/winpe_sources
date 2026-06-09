# CBaseAllocator::CBaseAllocator(ushort const *,IUnknown *,long *,int,int)

- ea: `0x180002c50`
- end: `0x180002cf2`
- name: `??0CBaseAllocator@@QEAA@PEBGPEAUIUnknown@@PEAJHH@Z`
- size: `162`
- prototype: `CBaseAllocator *__fastcall(CBaseAllocator *__hidden this, const unsigned __int16 *, struct IUnknown *, int *, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c170`
- `0x18000cfc0`

## callees

- `0x180002c50`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x180002cca`
- `KERNEL32!CreateSemaphoreExW` at `0x180002cca`
- `KERNEL32!InitializeCriticalSection` at `0x180002c79`
- `KERNEL32!InitializeCriticalSection` at `0x180002c79`

## pseudocode

```c
CBaseAllocator *__fastcall CBaseAllocator::CBaseAllocator(
        CBaseAllocator *this,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        int *a4,
        int a5,
        int a6)
{
  HANDLE Semaphore; // rax

  _InterlockedIncrement(&CBaseObject::m_cObjects);
  *((_QWORD *)this + 1) = this;
  *((_DWORD *)this + 4) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_DWORD *)this + 36) = a6;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 32) = 0;
  *((_QWORD *)this + 17) = 0;
  Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
  *((_QWORD *)this + 11) = Semaphore;
  if ( !Semaphore )
    *a4 = -2147024882;
  return this;
}

```

## disassembly

```asm
0x180002c50  mov     [rsp+arg_0], rbx
0x180002c55  mov     [rsp+arg_8], rsi
0x180002c5a  push    rdi
0x180002c5b  sub     rsp, 30h
0x180002c5f  mov     rdi, r9
0x180002c62  mov     rbx, rcx
0x180002c65  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180002c6c  mov     [rcx+8], rcx
0x180002c70  xor     esi, esi
0x180002c72  mov     [rcx+10h], esi
0x180002c75  add     rcx, 20h ; ' '; lpCriticalSection
0x180002c79  call    cs:__imp_InitializeCriticalSection
0x180002c7f  mov     eax, [rsp+38h+arg_28]
0x180002c83  xor     r9d, r9d; lpName
0x180002c86  mov     [rbx+48h], rsi
0x180002c8a  xor     edx, edx; lInitialCount
0x180002c8c  mov     [rbx+50h], esi
0x180002c8f  xor     ecx, ecx; lpSemaphoreAttributes
0x180002c91  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180002c97  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180002c9f  mov     [rbx+90h], eax
0x180002ca5  mov     [rbx+58h], rsi
0x180002ca9  mov     [rbx+60h], rsi
0x180002cad  mov     [rbx+68h], rsi
0x180002cb1  mov     [rbx+70h], rsi
0x180002cb5  mov     [rbx+78h], rsi
0x180002cb9  mov     [rbx+80h], esi
0x180002cbf  mov     [rbx+88h], rsi
0x180002cc6  mov     [rsp+38h+dwFlags], esi; dwFlags
0x180002cca  call    cs:__imp_CreateSemaphoreExW
0x180002cd0  mov     [rbx+58h], rax
0x180002cd4  test    rax, rax
0x180002cd7  jnz     short loc_180002CDF
0x180002cd9  mov     dword ptr [rdi], 8007000Eh
0x180002cdf  mov     rsi, [rsp+38h+arg_8]
0x180002ce4  mov     rax, rbx
0x180002ce7  mov     rbx, [rsp+38h+arg_0]
0x180002cec  add     rsp, 30h
0x180002cf0  pop     rdi
0x180002cf1  retn
```
