# wil::unique_winrt_event_token<Windows::System::IUserWatcher>::reset(void)

- ea: `0x18000d760`
- end: `0x18000d81e`
- name: `?reset@?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@wil@@QEAAXXZ`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180008b00`
- `0x18000be34`
- `0x180012eac`
- `0x180014c20`

## callees

- `0x18000c6bc`
- `0x18000d760`
- `0x180024010`

## string_xrefs

- `0x18000d80c`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::unique_winrt_event_token<Windows::System::IUserWatcher>::reset(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  if ( *(_QWORD *)a1 )
  {
    v2 = *(_QWORD *)(a1 + 8);
    v8 = 0;
    (*(void (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v2 + 24LL))(
      v2,
      &GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fbb,
      &v8);
    v3 = v8;
    if ( v8 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(a1 + 16))(v8, *(_QWORD *)a1);
      if ( v4 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x8B6,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
          (const char *)(unsigned int)v4,
          v6);
      v3 = v8;
    }
    *(_QWORD *)a1 = 0;
    v5 = *(_QWORD *)(a1 + 8);
    *(_QWORD *)(a1 + 8) = 0;
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      v3 = v8;
    }
    *(_QWORD *)(a1 + 16) = 0;
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
}

```

## disassembly

```asm
0x18000d760  push    rbx; int
0x18000d762  sub     rsp, 20h
0x18000d766  mov     rbx, rcx
0x18000d769  cmp     qword ptr [rcx], 0
0x18000d76d  jz      loc_18000D803
0x18000d773  mov     rcx, [rcx+8]
0x18000d777  mov     [rsp+28h+arg_0], 0
0x18000d780  mov     rax, [rcx]
0x18000d783  lea     r8, [rsp+28h+arg_0]
0x18000d788  lea     rdx, _GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fbb
0x18000d78f  mov     rax, [rax+18h]
0x18000d793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d798  nop
0x18000d799  mov     rcx, [rsp+28h+arg_0]
0x18000d79e  test    rcx, rcx
0x18000d7a1  jz      short loc_18000D7BD
0x18000d7a3  mov     rdx, [rbx]
0x18000d7a6  mov     rax, [rbx+10h]
0x18000d7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7af  mov     rcx, [rsp+28h]; this
0x18000d7b4  test    eax, eax
0x18000d7b6  js      short loc_18000D809
0x18000d7b8  mov     rcx, [rsp+28h+arg_0]
0x18000d7bd  mov     qword ptr [rbx], 0
0x18000d7c4  mov     rdx, [rbx+8]
0x18000d7c8  mov     qword ptr [rbx+8], 0
0x18000d7d0  test    rdx, rdx
0x18000d7d3  jz      short loc_18000D7E9
0x18000d7d5  mov     rax, [rdx]
0x18000d7d8  mov     rcx, rdx
0x18000d7db  mov     rax, [rax+10h]
0x18000d7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7e4  mov     rcx, [rsp+28h+arg_0]
0x18000d7e9  mov     qword ptr [rbx+10h], 0
0x18000d7f1  test    rcx, rcx
0x18000d7f4  jz      short loc_18000D803
0x18000d7f6  mov     rax, [rcx]
0x18000d7f9  mov     rax, [rax+10h]
0x18000d7fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d802  nop
0x18000d803  add     rsp, 20h
0x18000d807  pop     rbx
0x18000d808  retn
0x18000d809  mov     r9d, eax; char *
0x18000d80c  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d813  mov     edx, 8B6h; void *
0x18000d818  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
