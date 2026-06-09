# std::list<std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>::~list<std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>(void)

- ea: `0x18000c954`
- end: `0x18000c9bc`
- name: `??1?$list@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAA@XZ`
- size: `104`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000db7c`
- `0x18001eddc`

## callees

- `0x18000c954`
- `0x18000db20`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c995`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c995`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c9b5`

## pseudocode

```c
void __fastcall std::list<std::unique_ptr<std::wstring>>::~list<std::unique_ptr<std::wstring>>(__int64 a1)
{
  _QWORD *v2; // rsi
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  v2 = **(_QWORD ***)a1;
  **(_QWORD **)a1 = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *(_QWORD *)a1;
  *(_QWORD *)(a1 + 8) = 0;
  v3 = *(_QWORD **)a1;
  if ( v2 != v3 )
  {
    do
    {
      v4 = (_QWORD *)*v2;
      std::unique_ptr<std::wstring>::_Delete(v2 + 2);
      operator delete(v2);
      v3 = *(_QWORD **)a1;
      v2 = v4;
    }
    while ( v4 != *(_QWORD **)a1 );
  }
  operator delete(v3);
}

```

## disassembly

```asm
0x18000c954  mov     [rsp+arg_0], rbx
0x18000c959  mov     [rsp+arg_8], rsi
0x18000c95e  push    rdi
0x18000c95f  sub     rsp, 20h
0x18000c963  mov     rax, [rcx]
0x18000c966  mov     rdi, rcx
0x18000c969  mov     rsi, [rax]
0x18000c96c  mov     [rax], rax
0x18000c96f  mov     rax, [rcx]
0x18000c972  mov     [rax+8], rax
0x18000c976  mov     qword ptr [rcx+8], 0
0x18000c97e  mov     rcx, [rcx]
0x18000c981  cmp     rsi, rcx
0x18000c984  jz      short loc_18000C9A6
0x18000c986  mov     rbx, [rsi]
0x18000c989  lea     rcx, [rsi+10h]
0x18000c98d  call    ?_Delete@?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::wstring>::_Delete(void)
0x18000c992  mov     rcx, rsi
0x18000c995  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c99b  mov     rcx, [rdi]
0x18000c99e  mov     rsi, rbx
0x18000c9a1  cmp     rbx, rcx
0x18000c9a4  jnz     short loc_18000C986
0x18000c9a6  mov     rbx, [rsp+28h+arg_0]
0x18000c9ab  mov     rsi, [rsp+28h+arg_8]
0x18000c9b0  add     rsp, 20h
0x18000c9b4  pop     rdi
0x18000c9b5  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
