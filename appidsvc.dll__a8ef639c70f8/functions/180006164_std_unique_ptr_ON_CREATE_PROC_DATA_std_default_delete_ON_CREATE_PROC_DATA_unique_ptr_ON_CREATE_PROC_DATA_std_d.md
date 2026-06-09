# std::unique_ptr<ON_CREATE_PROC_DATA,std::default_delete<ON_CREATE_PROC_DATA>>::~unique_ptr<ON_CREATE_PROC_DATA,std::default_delete<ON_CREATE_PROC_DATA>>(void)

- ea: `0x180006164`
- end: `0x180006189`
- name: `??1?$unique_ptr@VON_CREATE_PROC_DATA@@U?$default_delete@VON_CREATE_PROC_DATA@@@std@@@std@@QEAA@XZ`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000c77a`
- `0x18000ca08`

## callees

- `0x180006164`
- `0x180006228`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000617d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000617d`

## pseudocode

```c
void __fastcall std::unique_ptr<ON_CREATE_PROC_DATA>::~unique_ptr<ON_CREATE_PROC_DATA>(void ***a1)
{
  void **v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    ON_CREATE_PROC_DATA::~ON_CREATE_PROC_DATA(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x180006164  push    rbx
0x180006166  sub     rsp, 20h
0x18000616a  mov     rbx, [rcx]
0x18000616d  test    rbx, rbx
0x180006170  jz      short loc_180006183
0x180006172  mov     rcx, rbx; this
0x180006175  call    ??1ON_CREATE_PROC_DATA@@QEAA@XZ; ON_CREATE_PROC_DATA::~ON_CREATE_PROC_DATA(void)
0x18000617a  mov     rcx, rbx
0x18000617d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006183  add     rsp, 20h
0x180006187  pop     rbx
0x180006188  retn
```
