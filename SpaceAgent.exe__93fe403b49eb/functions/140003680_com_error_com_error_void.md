# _com_error::~_com_error(void)

- ea: `0x140003680`
- end: `0x1400036bd`
- name: `??1_com_error@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400036d0`

## callees

- `0x140003680`
- `0x140020010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400036b1`
- `KERNEL32!LocalFree` at `0x1400036b1`

## pseudocode

```c
void __fastcall _com_error::~_com_error(_com_error *this)
{
  __int64 v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &_com_error::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    LocalFree(v3);
}

```

## disassembly

```asm
0x140003680  push    rbx
0x140003682  sub     rsp, 20h
0x140003686  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x14000368d  mov     rbx, rcx
0x140003690  mov     [rcx], rax
0x140003693  mov     rcx, [rcx+10h]
0x140003697  test    rcx, rcx
0x14000369a  jz      short loc_1400036A8
0x14000369c  mov     rax, [rcx]
0x14000369f  mov     rax, [rax+10h]
0x1400036a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036a8  mov     rcx, [rbx+18h]; hMem
0x1400036ac  test    rcx, rcx
0x1400036af  jz      short loc_1400036B7
0x1400036b1  call    cs:__imp_LocalFree
0x1400036b7  add     rsp, 20h
0x1400036bb  pop     rbx
0x1400036bc  retn
```
