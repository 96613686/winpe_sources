# std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal,std::allocator<WindowsMidiServicesInternal::GroupTerminalBlockInternal>>::~vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal,std::allocator<WindowsMidiServicesInternal::GroupTerminalBlockInternal>>(void)

- ea: `0x18001c81c`
- end: `0x18001c8cf`
- name: `??1?$vector@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@V?$allocator@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@std@@@std@@QEAA@XZ`
- size: `179`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18001d454`
- `0x18003176e`

## callees

- `0x1800041a4`
- `0x18000b740`
- `0x18001c81c`

## pseudocode

```c
void __fastcall std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>::~vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>(
        char **a1)
{
  char *v1; // rbx
  char *v3; // rsi
  char *v4; // rcx
  char *v5; // rax

  v1 = *a1;
  if ( *a1 )
  {
    v3 = a1[1];
    while ( v1 != v3 )
    {
      std::wstring::~wstring(v1 + 16);
      v1 += 48;
    }
    v4 = *a1;
    if ( (unsigned __int64)(16 * ((a1[2] - *a1) >> 4)) < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)(v4 - v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18001c81c  mov     [rsp+arg_0], rbx
0x18001c821  mov     [rsp+arg_8], rsi
0x18001c826  push    rdi
0x18001c827  sub     rsp, 20h
0x18001c82b  mov     rbx, [rcx]
0x18001c82e  mov     rdi, rcx
0x18001c831  test    rbx, rbx
0x18001c834  jz      loc_18001C8BF
0x18001c83a  mov     rsi, [rcx+8]
0x18001c83e  jmp     short loc_18001C84D
0x18001c840  lea     rcx, [rbx+10h]; void *
0x18001c844  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c849  add     rbx, 30h ; '0'
0x18001c84d  cmp     rbx, rsi
0x18001c850  jnz     short loc_18001C840
0x18001c852  mov     rcx, [rdi]
0x18001c855  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18001c85f  mov     rax, [rdi+10h]
0x18001c863  sub     rax, rcx
0x18001c866  sar     rax, 4
0x18001c86a  imul    rax, rdx
0x18001c86e  lea     rdx, [rax+rax*2]
0x18001c872  shl     rdx, 4
0x18001c876  cmp     rdx, 1000h
0x18001c87d  jb      short loc_18001C89D
0x18001c87f  mov     rax, [rcx-8]
0x18001c883  sub     rcx, rax
0x18001c886  sub     rcx, 8
0x18001c88a  cmp     rcx, 1Fh
0x18001c88e  ja      short loc_18001C896
0x18001c890  add     rdx, 27h ; '''
0x18001c894  jmp     short loc_18001C8A0
0x18001c896  mov     ecx, 5
0x18001c89b  int     29h; Win8: RtlFailFast(ecx)
0x18001c89d  mov     rax, rcx
0x18001c8a0  mov     rcx, rax; Block
0x18001c8a3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c8a8  mov     qword ptr [rdi], 0
0x18001c8af  mov     qword ptr [rdi+8], 0
0x18001c8b7  mov     qword ptr [rdi+10h], 0
0x18001c8bf  mov     rbx, [rsp+28h+arg_0]
0x18001c8c4  mov     rsi, [rsp+28h+arg_8]
0x18001c8c9  add     rsp, 20h
0x18001c8cd  pop     rdi
0x18001c8ce  retn
```
