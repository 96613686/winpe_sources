# tson::output_archive::write_type(bool,tson::details::archive_marker)

- ea: `0x18000de10`
- end: `0x18000de7d`
- name: `?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z`
- size: `109`
- prototype: `char __fastcall(tson::output_archive *, char, char)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180009810`
- `0x18000aec0`
- `0x18000c820`
- `0x18000c990`
- `0x18000cbd0`
- `0x18000ccb0`
- `0x18000cd80`

## callees

- `0x18000dac0`
- `0x18000de10`
- `0x18000de80`

## pseudocode

```c
char __fastcall tson::output_archive::write_type(tson::output_archive *a1, char a2, char a3)
{
  tson::write_buffer *v5; // rbx

  if ( !tson::output_archive::write_name(a1, a2) )
    return 0;
  v5 = (tson::write_buffer *)*((_QWORD *)a1 + 18);
  if ( *((_QWORD *)v5 + 259) < *((_QWORD *)v5 + 260) || tson::write_buffer::reserve(v5, 1u) )
    *(_BYTE *)(*((_QWORD *)v5 + 259))++ = a3;
  return 1;
}

```

## disassembly

```asm
0x18000de10  mov     [rsp+arg_0], rbx
0x18000de15  push    rdi
0x18000de16  sub     rsp, 20h
0x18000de1a  movzx   edi, r8b
0x18000de1e  mov     rbx, rcx
0x18000de21  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000de26  test    al, al
0x18000de28  jz      short loc_18000DE70
0x18000de2a  mov     rbx, [rbx+90h]
0x18000de31  mov     rax, [rbx+820h]
0x18000de38  cmp     [rbx+818h], rax
0x18000de3f  jb      short loc_18000DE52
0x18000de41  mov     edx, 1; unsigned __int64
0x18000de46  mov     rcx, rbx; this
0x18000de49  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000de4e  test    al, al
0x18000de50  jz      short loc_18000DE63
0x18000de52  mov     rax, [rbx+818h]
0x18000de59  mov     [rax], dil
0x18000de5c  inc     qword ptr [rbx+818h]
0x18000de63  mov     al, 1
0x18000de65  mov     rbx, [rsp+28h+arg_0]
0x18000de6a  add     rsp, 20h
0x18000de6e  pop     rdi
0x18000de6f  retn
0x18000de70  mov     rbx, [rsp+28h+arg_0]
0x18000de75  xor     al, al
0x18000de77  add     rsp, 20h
0x18000de7b  pop     rdi
0x18000de7c  retn
```
