# tson::output_archive::write_type(bool,tson::details::archive_marker)

- ea: `0x18000f358`
- end: `0x18000f38b`
- name: `?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z`
- size: `51`
- prototype: `char __fastcall(tson::write_buffer **, char, char)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a54c`
- `0x18000a5a4`
- `0x18000a64c`
- `0x18000a810`
- `0x18000a868`
- `0x18000a8c0`
- `0x18000aad0`
- `0x18000ac78`
- `0x18000e324`
- `0x18000e368`

## callees

- `0x18000ab88`
- `0x18000f168`
- `0x18000f358`

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
0x18000f358  mov     [rsp+arg_10], r8b
0x18000f35d  push    rbx
0x18000f35e  sub     rsp, 20h
0x18000f362  mov     rbx, rcx
0x18000f365  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000f36a  test    al, al
0x18000f36c  jz      short loc_18000F383
0x18000f36e  mov     rcx, [rbx+90h]
0x18000f375  lea     rdx, [rsp+28h+arg_10]
0x18000f37a  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000f37f  mov     al, 1
0x18000f381  jmp     short loc_18000F385
0x18000f383  xor     al, al
0x18000f385  add     rsp, 20h
0x18000f389  pop     rbx
0x18000f38a  retn
```
