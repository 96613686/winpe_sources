# std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal,std::allocator<WindowsMidiServicesInternal::GroupTerminalBlockInternal>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x18001cc2c`
- end: `0x18001ccb3`
- name: `??1_Reallocation_guard@?$vector@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@V?$allocator@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@std@@@std@@QEAA@XZ`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18001bd50`
- `0x18003155c`

## callees

- `0x1800041a4`
- `0x18000b740`
- `0x18001cc2c`

## pseudocode

```c
void __fastcall std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  __int64 v2; // rsi
  __int64 i; // rdi
  __int64 v4; // rcx
  void *v5; // rax

  if ( a1[1] )
  {
    v2 = a1[4];
    for ( i = a1[3]; i != v2; i += 48 )
      std::wstring::~wstring((void *)(i + 16));
    v4 = a1[1];
    if ( (unsigned __int64)(48LL * a1[2]) < 0x1000 )
    {
      v5 = (void *)a1[1];
    }
    else
    {
      v5 = *(void **)(v4 - 8);
      if ( (unsigned __int64)(v4 - (_QWORD)v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
  }
}

```

## disassembly

```asm
0x18001cc2c  mov     [rsp+arg_0], rbx
0x18001cc31  mov     [rsp+arg_8], rsi
0x18001cc36  push    rdi
0x18001cc37  sub     rsp, 20h
0x18001cc3b  cmp     qword ptr [rcx+8], 0
0x18001cc40  mov     rbx, rcx
0x18001cc43  jz      short loc_18001CCA3
0x18001cc45  mov     rsi, [rcx+20h]
0x18001cc49  mov     rdi, [rcx+18h]
0x18001cc4d  jmp     short loc_18001CC5C
0x18001cc4f  lea     rcx, [rdi+10h]; void *
0x18001cc53  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cc58  add     rdi, 30h ; '0'
0x18001cc5c  cmp     rdi, rsi
0x18001cc5f  jnz     short loc_18001CC4F
0x18001cc61  mov     rax, [rbx+10h]
0x18001cc65  mov     rcx, [rbx+8]
0x18001cc69  lea     rdx, [rax+rax*2]
0x18001cc6d  shl     rdx, 4
0x18001cc71  cmp     rdx, 1000h
0x18001cc78  jb      short loc_18001CC98
0x18001cc7a  mov     rax, [rcx-8]
0x18001cc7e  sub     rcx, rax
0x18001cc81  sub     rcx, 8
0x18001cc85  cmp     rcx, 1Fh
0x18001cc89  ja      short loc_18001CC91
0x18001cc8b  add     rdx, 27h ; '''
0x18001cc8f  jmp     short loc_18001CC9B
0x18001cc91  mov     ecx, 5
0x18001cc96  int     29h; Win8: RtlFailFast(ecx)
0x18001cc98  mov     rax, rcx
0x18001cc9b  mov     rcx, rax; Block
0x18001cc9e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cca3  mov     rbx, [rsp+28h+arg_0]
0x18001cca8  mov     rsi, [rsp+28h+arg_8]
0x18001ccad  add     rsp, 20h
0x18001ccb1  pop     rdi
0x18001ccb2  retn
```
