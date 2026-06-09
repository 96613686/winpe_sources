# std::basic_ostringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_ostringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x1400081fc`
- end: `0x140008271`
- name: `??1?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ`
- size: `117`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140007210`
- `0x1400095ec`
- `0x1400096ac`
- `0x14000b5b4`
- `0x14000eb60`

## callees

- `0x14000b08c`

## import_xrefs

- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000826a`
- `msvcp_win!??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140008256`
- `msvcp_win!??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140008256`

## pseudocode

```c
__int64 __fastcall std::basic_ostringstream<unsigned short>::~basic_ostringstream<unsigned short>(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rdx

  v1 = a1 - 128;
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 - 136) + 4LL) + a1 - 136) = &std::basic_ostringstream<unsigned short>::`vftable';
  v3 = *(int *)(*(_QWORD *)(a1 - 136) + 4LL);
  *(_DWORD *)(v3 + a1 - 140) = v3 - 136;
  *(_QWORD *)(a1 - 128) = &std::basic_stringbuf<unsigned short>::`vftable';
  std::basic_stringbuf<unsigned short>::_Tidy(a1 - 128);
  std::basic_streambuf<unsigned short>::~basic_streambuf<unsigned short,std::char_traits<unsigned short>>(v1);
  return std::basic_ostream<unsigned short>::~basic_ostream<unsigned short,std::char_traits<unsigned short>>(a1 - 120);
}

```

## disassembly

```asm
0x1400081fc  mov     [rsp+arg_0], rbx
0x140008201  push    rdi
0x140008202  sub     rsp, 20h
0x140008206  mov     rax, [rcx-88h]
0x14000820d  lea     rbx, [rcx-80h]
0x140008211  mov     rdi, rcx
0x140008214  movsxd  rdx, dword ptr [rax+4]
0x140008218  lea     rax, ??_7?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_ostringstream<ushort>::`vftable'
0x14000821f  mov     [rdx+rcx-88h], rax
0x140008227  mov     rax, [rcx-88h]
0x14000822e  movsxd  rdx, dword ptr [rax+4]
0x140008232  lea     rax, ??_7?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringbuf<ushort>::`vftable'
0x140008239  lea     r8d, [rdx-88h]
0x140008240  mov     [rdx+rcx-8Ch], r8d
0x140008248  mov     rcx, rbx
0x14000824b  mov     [rbx], rax
0x14000824e  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x140008253  mov     rcx, rbx
0x140008256  call    cs:__imp_??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_streambuf<ushort>::~basic_streambuf<ushort,std::char_traits<ushort>>(void)
0x14000825c  lea     rcx, [rdi-78h]
0x140008260  mov     rbx, [rsp+28h+arg_0]
0x140008265  add     rsp, 20h
0x140008269  pop     rdi
0x14000826a  jmp     cs:__imp_??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ostream<ushort>::~basic_ostream<ushort,std::char_traits<ushort>>(void)
```
