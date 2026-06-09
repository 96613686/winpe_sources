# tson::output_archive::write_type(bool,tson::details::archive_marker)

- ea: `0x1800263e8`
- end: `0x18002641b`
- name: `?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z`
- size: `51`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x18000940c`
- `0x1800094cc`
- `0x180009524`
- `0x180009660`
- `0x18000974c`
- `0x18000986c`
- `0x180009928`
- `0x1800099e8`
- `0x180016934`
- `0x1800169f0`
- `0x180016b0c`
- `0x180017998`
- `0x18002522c`

## callees

- `0x180016d5c`
- `0x180026204`
- `0x1800263e8`

## pseudocode

```c
char __fastcall tson::output_archive::write_type(tson::write_buffer **a1, bool a2, char a3)
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
0x1800263e8  mov     [rsp+arg_10], r8b
0x1800263ed  push    rbx
0x1800263ee  sub     rsp, 20h
0x1800263f2  mov     rbx, rcx
0x1800263f5  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x1800263fa  test    al, al
0x1800263fc  jz      short loc_180026413
0x1800263fe  mov     rcx, [rbx+90h]
0x180026405  lea     rdx, [rsp+28h+arg_10]
0x18002640a  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18002640f  mov     al, 1
0x180026411  jmp     short loc_180026415
0x180026413  xor     al, al
0x180026415  add     rsp, 20h
0x180026419  pop     rbx
0x18002641a  retn
```
