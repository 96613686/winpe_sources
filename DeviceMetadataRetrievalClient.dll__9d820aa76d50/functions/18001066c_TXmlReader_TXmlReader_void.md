# TXmlReader::~TXmlReader(void)

- ea: `0x18001066c`
- end: `0x1800106ad`
- name: `??1TXmlReader@@QEAA@XZ`
- size: `65`
- prototype: `void __fastcall(TXmlReader *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006904`
- `0x180008544`
- `0x18000a4c4`
- `0x18000dabc`

## callees

- `0x18001066c`
- `0x180014010`

## import_xrefs

- `msvcrt!free` at `0x180010699`
- `msvcrt!free` at `0x180010699`

## pseudocode

```c
void __fastcall TXmlReader::~TXmlReader(TXmlReader *this)
{
  __int64 v2; // rcx
  void *v3; // rcx

  v2 = *(_QWORD *)this;
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *(_QWORD *)this = 0;
  }
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    free(v3);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18001066c  push    rbx
0x18001066e  sub     rsp, 20h
0x180010672  mov     rbx, rcx
0x180010675  mov     rcx, [rcx]
0x180010678  test    rcx, rcx
0x18001067b  jz      short loc_180010690
0x18001067d  mov     rax, [rcx]
0x180010680  mov     rax, [rax+10h]
0x180010684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010689  mov     qword ptr [rbx], 0
0x180010690  mov     rcx, [rbx+8]; Block
0x180010694  test    rcx, rcx
0x180010697  jz      short loc_1800106A7
0x180010699  call    cs:__imp_free
0x18001069f  mov     qword ptr [rbx+8], 0
0x1800106a7  add     rsp, 20h
0x1800106ab  pop     rbx
0x1800106ac  retn
```
