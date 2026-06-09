# PolicyModel::CFilePathCondition::Serialize(Sharp::Util::Xml::CNode &)

- ea: `0x14000d9a0`
- end: `0x14000d9fb`
- name: `?Serialize@CFilePathCondition@PolicyModel@@MEBAXAEAVCNode@Xml@Util@Sharp@@@Z`
- size: `91`
- prototype: `void __fastcall(PolicyModel::CFilePathCondition *__hidden this, struct Sharp::Util::Xml::CNode *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x14000d9a0`
- `0x140016010`

## pseudocode

```c
void __fastcall PolicyModel::CFilePathCondition::Serialize(
        PolicyModel::CFilePathCondition *this,
        struct Sharp::Util::Xml::CNode *a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a1a8c93a76de3b7ee012ad1e7d3a4a88_Traceguids);
  (*(void (__fastcall **)(char *, struct Sharp::Util::Xml::CNode *))(*((_QWORD *)this + 2) + 8LL))(
    (char *)this + 16,
    a2);
}

```

## disassembly

```asm
0x14000d9a0  mov     [rsp+arg_0], rbx
0x14000d9a5  push    rdi
0x14000d9a6  sub     rsp, 20h
0x14000d9aa  mov     rbx, rdx
0x14000d9ad  mov     rdi, rcx
0x14000d9b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d9b7  lea     rax, WPP_GLOBAL_Control
0x14000d9be  cmp     rcx, rax
0x14000d9c1  jz      short loc_14000D9DE
0x14000d9c3  test    byte ptr [rcx+1Ch], 8
0x14000d9c7  jz      short loc_14000D9DE
0x14000d9c9  mov     rcx, [rcx+10h]
0x14000d9cd  lea     r8, WPP_a1a8c93a76de3b7ee012ad1e7d3a4a88_Traceguids
0x14000d9d4  mov     edx, 0Ch
0x14000d9d9  call    WPP_SF_
0x14000d9de  lea     rcx, [rdi+10h]
0x14000d9e2  mov     rdx, rbx
0x14000d9e5  mov     rax, [rcx]
0x14000d9e8  mov     rax, [rax+8]
0x14000d9ec  mov     rbx, [rsp+28h+arg_0]
0x14000d9f1  add     rsp, 20h
0x14000d9f5  pop     rdi
0x14000d9f6  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
