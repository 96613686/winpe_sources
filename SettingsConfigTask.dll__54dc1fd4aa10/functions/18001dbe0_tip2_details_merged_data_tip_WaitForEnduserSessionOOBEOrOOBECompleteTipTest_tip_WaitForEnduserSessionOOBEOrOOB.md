# tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::deserialize(tson::input_archive &)

- ea: `0x18001dbe0`
- end: `0x18001dc7e`
- name: `?deserialize@?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@EEAAXAEAVinput_archive@tson@@@Z`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001d768`
- `0x18001d7a0`
- `0x18001dbe0`
- `0x18001eb78`
- `0x180020778`
- `0x1800210fc`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::deserialize(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rsi
  int v5; // ebx
  __int64 v6; // rdx
  int v7; // [rsp+30h] [rbp+8h] BYREF

  *(_BYTE *)(a2 + 24) = 4;
  *(_QWORD *)(a2 + 16) = "test";
  tson::input_archive::startNode((tson::input_archive *)a2);
  *(_BYTE *)(a2 + 24) = 6;
  v4 = a1 + 272;
  if ( !a1 )
    v4 = 16;
  v5 = 0;
  *(_QWORD *)(a2 + 16) = "status";
  v7 = 0;
  if ( tson::input_archive::search((tson::input_archive *)a2) )
  {
    LOBYTE(v6) = 18;
    tson::input_archive::consume_expected_marker(a2, v6, 2147944029LL);
    tson::read_buffer::consume_n(*(tson::read_buffer **)a2, &v7, 4u);
    v5 = v7;
  }
  *(_DWORD *)v4 = v5;
  tson::input_archive::finishNode((tson::input_archive *)a2);
}

```

## disassembly

```asm
0x18001dbe0  mov     [rsp+arg_8], rbx
0x18001dbe5  mov     [rsp+arg_10], rsi
0x18001dbea  push    rdi
0x18001dbeb  sub     rsp, 20h
0x18001dbef  mov     rbx, rcx
0x18001dbf2  mov     byte ptr [rdx+18h], 4
0x18001dbf6  lea     rax, aTest; "test"
0x18001dbfd  mov     rcx, rdx; this
0x18001dc00  mov     [rdx+10h], rax
0x18001dc04  mov     rdi, rdx
0x18001dc07  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x18001dc0c  test    rbx, rbx
0x18001dc0f  mov     byte ptr [rdi+18h], 6
0x18001dc13  lea     rsi, [rbx+110h]
0x18001dc1a  mov     eax, 10h
0x18001dc1f  cmovz   rsi, rax
0x18001dc23  mov     rcx, rdi; this
0x18001dc26  lea     rax, aStatus; "status"
0x18001dc2d  xor     ebx, ebx
0x18001dc2f  mov     [rdi+10h], rax
0x18001dc33  mov     [rsp+28h+arg_0], ebx
0x18001dc37  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x18001dc3c  test    al, al
0x18001dc3e  jz      short loc_18001DC65
0x18001dc40  mov     r8d, 8007065Dh
0x18001dc46  mov     dl, 12h
0x18001dc48  mov     rcx, rdi
0x18001dc4b  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x18001dc50  mov     rcx, [rdi]; this
0x18001dc53  lea     rdx, [rsp+28h+arg_0]; void *
0x18001dc58  lea     r8d, [rbx+4]; unsigned __int64
0x18001dc5c  call    ?consume_n@read_buffer@tson@@QEAA_NPEAX_K@Z; tson::read_buffer::consume_n(void *,unsigned __int64)
0x18001dc61  mov     ebx, [rsp+28h+arg_0]
0x18001dc65  mov     rcx, rdi; this
0x18001dc68  mov     [rsi], ebx
0x18001dc6a  mov     rbx, [rsp+28h+arg_8]
0x18001dc6f  mov     rsi, [rsp+28h+arg_10]
0x18001dc74  add     rsp, 20h
0x18001dc78  pop     rdi
0x18001dc79  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
