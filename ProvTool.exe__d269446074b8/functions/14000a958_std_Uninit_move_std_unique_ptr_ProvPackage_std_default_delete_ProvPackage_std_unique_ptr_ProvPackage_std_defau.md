# std::_Uninit_move<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>> *,std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>> *,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>,std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>(std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>> *,std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>> *,std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>> *,std::_Wrap_alloc<std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>> &,std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x14000a958`
- end: `0x14000a994`
- name: `??$_Uninit_move@PEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@PEAV12@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@V12@@std@@YAPEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `60`
- prototype: `_QWORD *__fastcall(__int64 *, __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bca4`

## callees

- `0x14000a958`

## pseudocode

```c
_QWORD *__fastcall std::_Uninit_move<std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::allocator<std::unique_ptr<ProvPackage>>,std::unique_ptr<ProvPackage>>(
        __int64 *a1,
        __int64 *a2,
        _QWORD *a3)
{
  __int64 v3; // rax

  while ( a1 != a2 )
  {
    v3 = *a1;
    *a1 = 0;
    *a3++ = v3;
    ++a1;
  }
  return a3;
}

```

## disassembly

```asm
0x14000a958  mov     [rsp+arg_18], r9
0x14000a95d  mov     [rsp+arg_10], r8
0x14000a962  sub     rsp, 28h
0x14000a966  mov     [rsp+28h+arg_18], r8
0x14000a96b  jmp     short loc_14000A987
0x14000a96d  mov     rax, [rcx]
0x14000a970  mov     qword ptr [rcx], 0
0x14000a977  mov     [r8], rax
0x14000a97a  add     r8, 8
0x14000a97e  mov     [rsp+28h+arg_10], r8
0x14000a983  add     rcx, 8
0x14000a987  cmp     rcx, rdx
0x14000a98a  jnz     short loc_14000A96D
0x14000a98c  mov     rax, r8
0x14000a98f  add     rsp, 28h
0x14000a993  retn
```
