# std::unique_ptr<ipx::mtf::CClientDataSource,std::default_delete<ipx::mtf::CClientDataSource>>::~unique_ptr<ipx::mtf::CClientDataSource,std::default_delete<ipx::mtf::CClientDataSource>>(void)

- ea: `0x1800144c0`
- end: `0x1800144e7`
- name: `??1?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@QEAA@XZ`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002ced6`

## callees

- `0x1800144c0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800144d2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800144d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800144db`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800144db`

## pseudocode

```c
void __fastcall std::unique_ptr<ipx::mtf::CClientDataSource>::~unique_ptr<ipx::mtf::CClientDataSource>(void ***a1)
{
  void **v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    operator delete[](v1[2]);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x1800144c0  push    rbx
0x1800144c2  sub     rsp, 20h
0x1800144c6  mov     rbx, [rcx]
0x1800144c9  test    rbx, rbx
0x1800144cc  jz      short loc_1800144E1
0x1800144ce  mov     rcx, [rbx+10h]
0x1800144d2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800144d8  mov     rcx, rbx
0x1800144db  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800144e1  add     rsp, 20h
0x1800144e5  pop     rbx
0x1800144e6  retn
```
