# tson::output_archive::write_type(bool,tson::details::archive_marker)

- ea: `0x18002188c`
- end: `0x1800218bf`
- name: `?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z`
- size: `51`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c3c0`
- `0x18000c494`
- `0x18000c4ec`
- `0x18000c6c0`
- `0x180010574`
- `0x180010630`
- `0x18001074c`
- `0x180011000`
- `0x1800201d4`
- `0x180020218`

## callees

- `0x180010b74`
- `0x18002169c`
- `0x18002188c`

## pseudocode

```c
char __fastcall tson::output_archive::write_type(tson::output_archive *a1, bool a2, char a3)
{
  char v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = a3;
  if ( !tson::output_archive::write_name(a1, a2) )
    return 0;
  tson::write_buffer::push_back<unsigned char>(*((_QWORD *)a1 + 18), &v5);
  return 1;
}

```

## disassembly

```asm
0x18002188c  mov     [rsp+arg_10], r8b
0x180021891  push    rbx
0x180021892  sub     rsp, 20h
0x180021896  mov     rbx, rcx
0x180021899  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18002189e  test    al, al
0x1800218a0  jz      short loc_1800218B7
0x1800218a2  mov     rcx, [rbx+90h]
0x1800218a9  lea     rdx, [rsp+28h+arg_10]
0x1800218ae  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x1800218b3  mov     al, 1
0x1800218b5  jmp     short loc_1800218B9
0x1800218b7  xor     al, al
0x1800218b9  add     rsp, 20h
0x1800218bd  pop     rbx
0x1800218be  retn
```
