# CMidi2VirtualMidiBidi::LinkAssociatedCallback(wil::com_ptr_t<IMidiCallback,wil::err_returncode_policy>)

- ea: `0x180016450`
- end: `0x1800164de`
- name: `?LinkAssociatedCallback@CMidi2VirtualMidiBidi@@QEAAJV?$com_ptr_t@UIMidiCallback@@Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016740`

## callees

- `0x180016450`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall CMidi2VirtualMidiBidi::LinkAssociatedCallback(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rcx

  v4 = *(_QWORD *)(a1 + 32);
  if ( v4 )
  {
    *(_QWORD *)(a1 + 32) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    v5 = *(_QWORD *)(a1 + 32);
  }
  else
  {
    v5 = 0;
  }
  v6 = *a2;
  *(_QWORD *)(a1 + 32) = *a2;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( *a2 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  return 0;
}

```

## disassembly

```asm
0x180016450  mov     [rsp+arg_0], rbx
0x180016455  mov     [rsp+arg_8], rsi
0x18001645a  push    rdi
0x18001645b  sub     rsp, 20h
0x18001645f  mov     rsi, rdx
0x180016462  mov     rdi, rcx
0x180016465  mov     rcx, [rcx+20h]
0x180016469  test    rcx, rcx
0x18001646c  jz      short loc_180016488
0x18001646e  mov     qword ptr [rdi+20h], 0
0x180016476  mov     rax, [rcx]
0x180016479  mov     rax, [rax+10h]
0x18001647d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016482  mov     rbx, [rdi+20h]
0x180016486  jmp     short loc_18001648A
0x180016488  xor     ebx, ebx
0x18001648a  mov     rcx, [rsi]
0x18001648d  mov     [rdi+20h], rcx
0x180016491  test    rcx, rcx
0x180016494  jz      short loc_1800164A2
0x180016496  mov     rax, [rcx]
0x180016499  mov     rax, [rax+8]
0x18001649d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164a2  test    rbx, rbx
0x1800164a5  jz      short loc_1800164B7
0x1800164a7  mov     rax, [rbx]
0x1800164aa  mov     rcx, rbx
0x1800164ad  mov     rax, [rax+10h]
0x1800164b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164b6  nop
0x1800164b7  mov     rcx, [rsi]
0x1800164ba  test    rcx, rcx
0x1800164bd  jz      short loc_1800164CC
0x1800164bf  mov     rax, [rcx]
0x1800164c2  mov     rax, [rax+10h]
0x1800164c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164cb  nop
0x1800164cc  xor     eax, eax
0x1800164ce  mov     rbx, [rsp+28h+arg_0]
0x1800164d3  mov     rsi, [rsp+28h+arg_8]
0x1800164d8  add     rsp, 20h
0x1800164dc  pop     rdi
0x1800164dd  retn
```
