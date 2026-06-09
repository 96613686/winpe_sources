# TpmObject::~TpmObject(void)

- ea: `0x1800524d8`
- end: `0x180052513`
- name: `??1TpmObject@@UEAA@XZ`
- size: `59`
- prototype: `void __fastcall(TpmObject *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180070f34`
- `0x180081ac0`
- `0x180084d00`
- `0x180090600`
- `0x180090648`
- `0x1800c4c71`

## callees

- `0x1800524d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800524f6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800524f6`

## pseudocode

```c
void __fastcall TpmObject::~TpmObject(TpmObject *this)
{
  *(_QWORD *)this = &TpmObject::`vftable';
  if ( (*((_DWORD *)this + 3) & 1) == 0 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &ObjectWithProperties::`vftable';
}

```

## disassembly

```asm
0x1800524d8  push    rbx
0x1800524da  sub     rsp, 20h
0x1800524de  lea     rax, ??_7TpmObject@@6B@; const TpmObject::`vftable'
0x1800524e5  mov     rbx, rcx
0x1800524e8  mov     [rcx], rax
0x1800524eb  mov     eax, [rcx+0Ch]
0x1800524ee  test    al, 1
0x1800524f0  jnz     short loc_180052502
0x1800524f2  add     rcx, 10h; lpCriticalSection
0x1800524f6  call    cs:__imp_DeleteCriticalSection
0x1800524fd  nop     dword ptr [rax+rax+00h]
0x180052502  lea     rax, ??_7ObjectWithProperties@@6B@; const ObjectWithProperties::`vftable'
0x180052509  mov     [rbx], rax
0x18005250c  add     rsp, 20h
0x180052510  pop     rbx
0x180052511  retn
```
