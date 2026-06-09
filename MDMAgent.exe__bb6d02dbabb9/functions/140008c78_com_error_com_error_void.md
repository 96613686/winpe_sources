# _com_error::~_com_error(void)

- ea: `0x140008c78`
- end: `0x140008cbd`
- name: `??1_com_error@@UEAA@XZ`
- size: `69`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008cd0`

## callees

- `0x140008c78`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140008ca9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140008ca9`

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
0x140008c78  push    rbx
0x140008c7a  sub     rsp, 20h
0x140008c7e  mov     rbx, rcx
0x140008c81  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x140008c88  mov     [rcx], rax
0x140008c8b  mov     rcx, [rcx+10h]
0x140008c8f  test    rcx, rcx
0x140008c92  jz      short loc_140008CA0
0x140008c94  mov     rax, [rcx]
0x140008c97  mov     rax, [rax+10h]
0x140008c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008ca0  mov     rcx, [rbx+18h]; hMem
0x140008ca4  test    rcx, rcx
0x140008ca7  jz      short loc_140008CB6
0x140008ca9  call    cs:__imp_LocalFree
0x140008cb0  nop     dword ptr [rax+rax+00h]
0x140008cb5  nop
0x140008cb6  add     rsp, 20h
0x140008cba  pop     rbx
0x140008cbb  retn
```
