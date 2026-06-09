# tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>::deserialize(tson::input_archive &)

- ea: `0x180021d50`
- end: `0x180021dc6`
- name: `?deserialize@?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@EEAAXAEAVinput_archive@tson@@@Z`
- size: `118`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x180022c2c`
- `0x18002327c`
- `0x180024ac0`

## string_xrefs

- `0x180021d77`: `taskStatus`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>::deserialize(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rcx
  unsigned int v5; // [rsp+30h] [rbp+8h] BYREF

  *(_BYTE *)(a2 + 24) = 4;
  *(_QWORD *)(a2 + 16) = "test";
  tson::input_archive::startNode((tson::input_archive *)a2);
  *(_BYTE *)(a2 + 24) = 10;
  *(_QWORD *)(a2 + 16) = "taskStatus";
  v5 = 0;
  tson::input_archive::loadValue((tson::input_archive *)a2, &v5);
  v4 = a1 + 272;
  if ( !a1 )
    v4 = 16;
  *(_DWORD *)v4 = v5;
  tson::input_archive::finishNode((tson::input_archive *)a2);
}

```

## disassembly

```asm
0x180021d50  mov     [rsp+arg_8], rbx
0x180021d55  push    rdi
0x180021d56  sub     rsp, 20h
0x180021d5a  mov     rbx, rcx
0x180021d5d  mov     byte ptr [rdx+18h], 4
0x180021d61  lea     rax, aTest; "test"
0x180021d68  mov     rcx, rdx; this
0x180021d6b  mov     [rdx+10h], rax
0x180021d6f  mov     rdi, rdx
0x180021d72  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180021d77  lea     rax, aTaskstatus; "taskStatus"
0x180021d7e  mov     byte ptr [rdi+18h], 0Ah
0x180021d82  lea     rdx, [rsp+28h+arg_0]; unsigned int *
0x180021d87  mov     [rdi+10h], rax
0x180021d8b  mov     rcx, rdi; this
0x180021d8e  mov     [rsp+28h+arg_0], 0
0x180021d96  call    ?loadValue@input_archive@tson@@QEAAXAEAK@Z; tson::input_archive::loadValue(ulong &)
0x180021d9b  mov     eax, 10h
0x180021da0  lea     rcx, [rbx+110h]
0x180021da7  test    rbx, rbx
0x180021daa  cmovz   rcx, rax
0x180021dae  mov     eax, [rsp+28h+arg_0]
0x180021db2  mov     [rcx], eax
0x180021db4  mov     rcx, rdi; this
0x180021db7  mov     rbx, [rsp+28h+arg_8]
0x180021dbc  add     rsp, 20h
0x180021dc0  pop     rdi
0x180021dc1  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
