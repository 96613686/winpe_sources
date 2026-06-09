# tson::output_archive::write_type(bool,tson::details::archive_marker)

- ea: `0x18000e924`
- end: `0x18000e957`
- name: `?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z`
- size: `51`
- prototype: `char __fastcall(tson::write_buffer **, char, char)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a5b4`
- `0x18000a60c`
- `0x18000a664`
- `0x18000a730`
- `0x18000a940`
- `0x18000a998`
- `0x18000a9f0`
- `0x18000aee8`
- `0x18000dd70`

## callees

- `0x18000ae94`
- `0x18000e734`
- `0x18000e924`

## pseudocode

```c
char __fastcall tson::output_archive::write_type(tson::write_buffer **a1, char a2, char a3)
{
  char v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = a3;
  if ( !tson::output_archive::write_name((tson::output_archive *)a1, a2) )
    return 0;
  tson::write_buffer::push_back<unsigned char>(a1[18], &v5);
  return 1;
}

```

## disassembly

```asm
0x18000e924  mov     [rsp+arg_10], r8b
0x18000e929  push    rbx
0x18000e92a  sub     rsp, 20h
0x18000e92e  mov     rbx, rcx
0x18000e931  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000e936  test    al, al
0x18000e938  jz      short loc_18000E94F
0x18000e93a  mov     rcx, [rbx+90h]
0x18000e941  lea     rdx, [rsp+28h+arg_10]
0x18000e946  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000e94b  mov     al, 1
0x18000e94d  jmp     short loc_18000E951
0x18000e94f  xor     al, al
0x18000e951  add     rsp, 20h
0x18000e955  pop     rbx
0x18000e956  retn
```
