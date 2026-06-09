# CBaseAllocator::~CBaseAllocator(void)

- ea: `0x180002ff4`
- end: `0x18000303b`
- name: `??1CBaseAllocator@@UEAA@XZ`
- size: `71`
- prototype: `void __fastcall(CBaseAllocator *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000315c`
- `0x18000bb40`

## callees

- `0x180002ff4`
- `0x180034010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180003006`
- `KERNEL32!CloseHandle` at `0x180003006`
- `KERNEL32!DeleteCriticalSection` at `0x180003028`
- `KERNEL32!DeleteCriticalSection` at `0x180003028`

## pseudocode

```c
void __fastcall CBaseAllocator::~CBaseAllocator(CBaseAllocator *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
    CloseHandle(v2);
  v3 = *((_QWORD *)this + 17);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  _InterlockedDecrement(&CBaseObject::m_cObjects);
}

```

## disassembly

```asm
0x180002ff4  push    rbx
0x180002ff6  sub     rsp, 20h
0x180002ffa  mov     rbx, rcx
0x180002ffd  mov     rcx, [rcx+58h]; hObject
0x180003001  test    rcx, rcx
0x180003004  jz      short loc_18000300C
0x180003006  call    cs:__imp_CloseHandle
0x18000300c  mov     rcx, [rbx+88h]
0x180003013  test    rcx, rcx
0x180003016  jz      short loc_180003024
0x180003018  mov     rax, [rcx]
0x18000301b  mov     rax, [rax+10h]
0x18000301f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003024  lea     rcx, [rbx+20h]; lpCriticalSection
0x180003028  call    cs:__imp_DeleteCriticalSection
0x18000302e  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180003035  add     rsp, 20h
0x180003039  pop     rbx
0x18000303a  retn
```
