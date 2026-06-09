# OnMosGetDataAsyncComplete

- ea: `0x18000ae60`
- end: `0x18000ae92`
- name: `OnMosGetDataAsyncComplete`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ae60`
- `0x180012010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000ae71`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000ae71`

## pseudocode

```c
__int64 __fastcall OnMosGetDataAsyncComplete(int a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rcx
  int v5; // [rsp+30h] [rbp+8h] BYREF

  v5 = a1;
  v3 = *(_QWORD *)(a3 + 56);
  if ( !v3 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  return (*(__int64 (__fastcall **)(__int64, int *, __int64))(*(_QWORD *)v3 + 16LL))(v3, &v5, a3 + 64);
}

```

## disassembly

```asm
0x18000ae60  sub     rsp, 28h
0x18000ae64  mov     [rsp+28h+arg_0], ecx
0x18000ae68  mov     rcx, [r8+38h]
0x18000ae6c  test    rcx, rcx
0x18000ae6f  jnz     short loc_18000AE78
0x18000ae71  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18000ae77  int     3; Trap to Debugger
0x18000ae78  mov     rax, [rcx]
0x18000ae7b  lea     rdx, [rsp+28h+arg_0]
0x18000ae80  add     r8, 40h ; '@'
0x18000ae84  mov     rax, [rax+10h]
0x18000ae88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae8d  add     rsp, 28h
0x18000ae91  retn
```
