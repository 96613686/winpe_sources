# tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::~merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>(void)

- ea: `0x18000b2ac`
- end: `0x18000b2d5`
- name: `??1?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@QEAA@XZ`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000c8fc`

## callees

- `0x18000b2dc`
- `0x18000e090`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::~merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>(
        _QWORD *a1)
{
  _QWORD *v1; // rbx

  v1 = a1 + 1;
  *a1 = &tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::`vftable';
  tip2::details::shared_data<0,0,0>::on_destroy(a1 + 1);
  return tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(v1);
}

```

## disassembly

```asm
0x18000b2ac  push    rbx
0x18000b2ae  sub     rsp, 20h
0x18000b2b2  lea     rax, ??_7?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::`vftable'
0x18000b2b9  lea     rbx, [rcx+8]
0x18000b2bd  mov     [rcx], rax
0x18000b2c0  mov     rcx, rbx
0x18000b2c3  call    ?on_destroy@?$shared_data@$0A@$0A@$0A@@details@tip2@@IEAAXXZ; tip2::details::shared_data<0,0,0>::on_destroy(void)
0x18000b2c8  mov     rcx, rbx
0x18000b2cb  add     rsp, 20h
0x18000b2cf  pop     rbx
0x18000b2d0  jmp     ??1?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@XZ; tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(void)
```
