# std::unique_ptr<std::shared_ptr<CSession>,std::default_delete<std::shared_ptr<CSession>>>::_Delete(void)

- ea: `0x18000bedc`
- end: `0x18000bf08`
- name: `?_Delete@?$unique_ptr@V?$shared_ptr@VCSession@@@std@@U?$default_delete@V?$shared_ptr@VCSession@@@std@@@2@@std@@AEAAXXZ`
- size: `44`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ace4`
- `0x18000aedc`
- `0x18000b1f8`
- `0x18000b4a0`
- `0x18000bb00`
- `0x18000c498`

## callees

- `0x18000be90`
- `0x18000bedc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000befc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000befc`

## pseudocode

```c
void __fastcall std::unique_ptr<std::shared_ptr<CSession>>::_Delete(_QWORD **a1)
{
  _QWORD *v1; // rbx
  std::_Ref_count_base *v2; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v2 = (std::_Ref_count_base *)v1[1];
    if ( v2 )
      std::_Ref_count_base::_Decref(v2);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000bedc  push    rbx
0x18000bede  sub     rsp, 20h
0x18000bee2  mov     rbx, [rcx]
0x18000bee5  test    rbx, rbx
0x18000bee8  jz      short loc_18000BF02
0x18000beea  mov     rcx, [rbx+8]; this
0x18000beee  test    rcx, rcx
0x18000bef1  jz      short loc_18000BEF9
0x18000bef3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bef8  nop
0x18000bef9  mov     rcx, rbx
0x18000befc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bf02  add     rsp, 20h
0x18000bf06  pop     rbx
0x18000bf07  retn
```
