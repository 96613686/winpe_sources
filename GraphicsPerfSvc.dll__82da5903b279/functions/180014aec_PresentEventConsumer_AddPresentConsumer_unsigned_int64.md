# PresentEventConsumer::AddPresentConsumer(unsigned __int64)

- ea: `0x180014aec`
- end: `0x180014bb9`
- name: `?AddPresentConsumer@PresentEventConsumer@@AEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@std@@@std@@@std@@_K@Z`
- size: `205`
- prototype: `_QWORD *__fastcall(__int64 *, _QWORD *, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ba20`
- `0x180014e64`
- `0x1800152d0`

## callees

- `0x180003ebc`
- `0x18000b77c`
- `0x1800146b4`
- `0x180014aec`
- `0x18002384c`
- `0x180024944`
- `0x180031010`

## pseudocode

```c
_QWORD *__fastcall PresentEventConsumer::AddPresentConsumer(__int64 *a1, _QWORD *a2, __int64 a3)
{
  PresentConsumer *v6; // rax
  __int64 v7; // rbx
  __int64 *v8; // rax
  __int64 v9; // rcx
  __int64 v11; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+28h] [rbp-20h] BYREF
  _BYTE v13[24]; // [rsp+30h] [rbp-18h] BYREF
  PresentConsumer *v14; // [rsp+70h] [rbp+28h] BYREF

  if ( (*(unsigned int (__fastcall **)(__int64 *))(*a1 + 152))(a1) == 1 )
  {
    v14 = (PresentConsumer *)operator new(0x440u);
    v6 = PresentConsumer::PresentConsumer(v14, 1u);
    v11 = a3;
    v14 = 0;
    v12 = (__int64)v6;
  }
  else
  {
    v8 = (__int64 *)CreatePresentConsumer(&v14);
    v11 = a3;
    v9 = *v8;
    *v8 = 0;
    v12 = v9;
  }
  v7 = *(_QWORD *)std::_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPresentConsumer>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>,0>>::emplace<std::pair<unsigned __int64,std::unique_ptr<IPresentConsumer>>>(
                    a1 + 17,
                    (__int64)v13,
                    (__int64)&v11);
  std::unique_ptr<IPresentConsumer>::~unique_ptr<IPresentConsumer>(&v12);
  std::unique_ptr<IPresentConsumer>::~unique_ptr<IPresentConsumer>((__int64 *)&v14);
  *a2 = v7;
  return a2;
}

```

## disassembly

```asm
0x180014aec  push    rbp
0x180014aee  push    rbx
0x180014aef  push    rsi
0x180014af0  push    rdi
0x180014af1  mov     rbp, rsp
0x180014af4  sub     rsp, 48h
0x180014af8  mov     rsi, r8
0x180014afb  mov     rdi, rdx
0x180014afe  mov     rbx, rcx
0x180014b01  mov     rax, [rcx]
0x180014b04  mov     rax, [rax+98h]
0x180014b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b10  cmp     eax, 1
0x180014b13  jnz     short loc_180014B64
0x180014b15  mov     ecx, 440h; Size
0x180014b1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014b1f  mov     [rbp+arg_0], rax
0x180014b23  mov     edx, 1; unsigned int
0x180014b28  mov     rcx, rax; this
0x180014b2b  call    ??0PresentConsumer@@QEAA@I@Z; PresentConsumer::PresentConsumer(uint)
0x180014b30  nop
0x180014b31  mov     [rbp+var_28], rsi
0x180014b35  mov     [rbp+arg_0], 0
0x180014b3d  mov     [rbp+var_20], rax
0x180014b41  lea     r8, [rbp+var_28]
0x180014b45  lea     rdx, [rbp+var_18]
0x180014b49  lea     rcx, [rbx+88h]
0x180014b50  call    ??$emplace@U?$pair@_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPresentConsumer>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>,0>>::emplace<std::pair<unsigned __int64,std::unique_ptr<IPresentConsumer>>>(std::pair<unsigned __int64,std::unique_ptr<IPresentConsumer>> &&)
0x180014b55  mov     rbx, [rax]
0x180014b58  lea     rcx, [rbp+var_20]
0x180014b5c  call    ??1?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@QEAA@XZ; std::unique_ptr<IPresentConsumer>::~unique_ptr<IPresentConsumer>(void)
0x180014b61  nop
0x180014b62  jmp     short loc_180014BA1
0x180014b64  lea     rcx, [rbp+arg_0]
0x180014b68  call    ?CreatePresentConsumer@@YA?AV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@XZ; CreatePresentConsumer(void)
0x180014b6d  nop
0x180014b6e  mov     [rbp+var_28], rsi
0x180014b72  mov     rcx, [rax]
0x180014b75  mov     qword ptr [rax], 0
0x180014b7c  mov     [rbp+var_20], rcx
0x180014b80  lea     r8, [rbp+var_28]
0x180014b84  lea     rdx, [rbp+var_18]
0x180014b88  lea     rcx, [rbx+88h]
0x180014b8f  call    ??$emplace@U?$pair@_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPresentConsumer>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>,0>>::emplace<std::pair<unsigned __int64,std::unique_ptr<IPresentConsumer>>>(std::pair<unsigned __int64,std::unique_ptr<IPresentConsumer>> &&)
0x180014b94  mov     rbx, [rax]
0x180014b97  lea     rcx, [rbp+var_20]
0x180014b9b  call    ??1?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@QEAA@XZ; std::unique_ptr<IPresentConsumer>::~unique_ptr<IPresentConsumer>(void)
0x180014ba0  nop
0x180014ba1  lea     rcx, [rbp+arg_0]
0x180014ba5  call    ??1?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@QEAA@XZ; std::unique_ptr<IPresentConsumer>::~unique_ptr<IPresentConsumer>(void)
0x180014baa  mov     [rdi], rbx
0x180014bad  mov     rax, rdi
0x180014bb0  add     rsp, 48h
0x180014bb4  pop     rdi
0x180014bb5  pop     rsi
0x180014bb6  pop     rbx
0x180014bb7  pop     rbp
0x180014bb8  retn
```
