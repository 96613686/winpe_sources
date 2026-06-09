# std::list<std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>>,std::allocator<std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>>>>::push_back(std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>> &&)

- ea: `0x18000f75c`
- end: `0x18000f7bf`
- name: `?push_back@?$list@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@V?$allocator@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@2@@Z`
- size: `99`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cf60`
- `0x18000e228`

## callees

- `0x180001610`
- `0x18000c558`
- `0x18000f75c`

## pseudocode

```c
__int64 *__fastcall std::list<std::unique_ptr<CInformationNode>>::push_back(__int64 *a1, __int64 *a2)
{
  __int64 v2; // rdi
  __int64 v4; // r8
  __int64 v5; // rax
  __int64 *result; // rax

  v2 = *a1;
  v4 = std::_List_buy<std::unique_ptr<std::wstring>>::_Buynode<std::unique_ptr<std::wstring>>(
         (__int64)a1,
         *a1,
         *(_QWORD *)(*a1 + 8),
         a2);
  v5 = a1[1];
  if ( v5 == 0xAAAAAAAAAAAAAA9LL )
    std::_Xlength_error("list<T> too long");
  a1[1] = v5 + 1;
  *(_QWORD *)(v2 + 8) = v4;
  result = *(__int64 **)(v4 + 8);
  *result = v4;
  return result;
}

```

## disassembly

```asm
0x18000f75c  mov     [rsp+arg_0], rbx
0x18000f761  push    rdi
0x18000f762  sub     rsp, 20h
0x18000f766  mov     rdi, [rcx]
0x18000f769  mov     r9, rdx
0x18000f76c  mov     rdx, rdi
0x18000f76f  mov     rbx, rcx
0x18000f772  mov     r8, [rdi+8]
0x18000f776  call    ??$_Buynode@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@?$_List_buy@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAX@1@PEAU21@0$$QEAV?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@1@@Z; std::_List_buy<std::unique_ptr<std::wstring>>::_Buynode<std::unique_ptr<std::wstring>>(std::_List_node<std::unique_ptr<std::wstring>,void *> *,std::_List_node<std::unique_ptr<std::wstring>,void *> *,std::unique_ptr<std::wstring> &&)
0x18000f77b  mov     r8, rax
0x18000f77e  mov     rdx, 0AAAAAAAAAAAAAA9h
0x18000f788  mov     rax, [rbx+8]
0x18000f78c  sub     rdx, rax
0x18000f78f  cmp     rdx, 1
0x18000f793  jnb     short loc_18000F7A2
0x18000f795  lea     rcx, aListTTooLong; "list<T> too long"
0x18000f79c  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000f7a2  inc     rax
0x18000f7a5  mov     [rbx+8], rax
0x18000f7a9  mov     rbx, [rsp+28h+arg_0]
0x18000f7ae  mov     [rdi+8], r8
0x18000f7b2  mov     rax, [r8+8]
0x18000f7b6  mov     [rax], r8
0x18000f7b9  add     rsp, 20h
0x18000f7bd  pop     rdi
0x18000f7be  retn
```
