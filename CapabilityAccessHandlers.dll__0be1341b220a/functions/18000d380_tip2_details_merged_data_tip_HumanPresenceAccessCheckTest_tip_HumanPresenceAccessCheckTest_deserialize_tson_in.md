# tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::deserialize(tson::input_archive &)

- ea: `0x18000d380`
- end: `0x18000d3d1`
- name: `?deserialize@?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@EEAAXAEAVinput_archive@tson@@@Z`
- size: `81`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000ad0c`
- `0x18000debc`
- `0x18000eed0`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::deserialize(
        __int64 a1,
        __int64 a2)
{
  *(_BYTE *)(a2 + 24) = 4;
  *(_QWORD *)(a2 + 16) = "test";
  tson::input_archive::startNode((tson::input_archive *)a2);
  _tip_HumanPresenceAccessCheckTest::serialize<tson::input_archive>((a1 + 256) & -(__int64)(a1 != 0), a2);
  tson::input_archive::finishNode((tson::input_archive *)a2);
}

```

## disassembly

```asm
0x18000d380  mov     [rsp+arg_0], rbx
0x18000d385  push    rdi
0x18000d386  sub     rsp, 20h
0x18000d38a  mov     rbx, rcx
0x18000d38d  mov     byte ptr [rdx+18h], 4
0x18000d391  lea     rax, aTest; "test"
0x18000d398  mov     rcx, rdx; this
0x18000d39b  mov     [rdx+10h], rax
0x18000d39f  mov     rdi, rdx
0x18000d3a2  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x18000d3a7  lea     rax, [rbx+100h]
0x18000d3ae  mov     rdx, rdi
0x18000d3b1  neg     rbx
0x18000d3b4  sbb     rcx, rcx
0x18000d3b7  and     rcx, rax
0x18000d3ba  call    ??$serialize@Vinput_archive@tson@@@_tip_HumanPresenceAccessCheckTest@@QEAAXAEAVinput_archive@tson@@@Z; _tip_HumanPresenceAccessCheckTest::serialize<tson::input_archive>(tson::input_archive &)
0x18000d3bf  mov     rcx, rdi; this
0x18000d3c2  mov     rbx, [rsp+28h+arg_0]
0x18000d3c7  add     rsp, 20h
0x18000d3cb  pop     rdi
0x18000d3cc  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
