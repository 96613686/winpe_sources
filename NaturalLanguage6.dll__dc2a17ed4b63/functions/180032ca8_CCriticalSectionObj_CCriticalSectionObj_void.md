# CCriticalSectionObj::~CCriticalSectionObj(void)

- ea: `0x180032ca8`
- end: `0x180032cd2`
- name: `??1CCriticalSectionObj@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(CCriticalSectionObj *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180032a68`
- `0x18004e110`
- `0x1800609bc`
- `0x18009f752`
- `0x1800a1f53`
- `0x1800a2c1f`
- `0x1800a8099`
- `0x1800a80af`
- `0x1800acfb1`
- `0x1800afcc0`
- `0x1800afdc0`

## callees

- `0x180032ca8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032cc3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032cc3`

## pseudocode

```c
void __fastcall CCriticalSectionObj::~CCriticalSectionObj(CCriticalSectionObj *this)
{
  if ( *(_BYTE *)this )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *(_BYTE *)this = 0;
}

```

## disassembly

```asm
0x180032ca8  push    rbx
0x180032caa  sub     rsp, 30h
0x180032cae  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180032cb7  mov     rbx, rcx
0x180032cba  cmp     byte ptr [rcx], 0
0x180032cbd  jz      short loc_180032CC9
0x180032cbf  add     rcx, 8; lpCriticalSection
0x180032cc3  call    cs:__imp_DeleteCriticalSection
0x180032cc9  mov     byte ptr [rbx], 0
0x180032ccc  add     rsp, 30h
0x180032cd0  pop     rbx
0x180032cd1  retn
```
