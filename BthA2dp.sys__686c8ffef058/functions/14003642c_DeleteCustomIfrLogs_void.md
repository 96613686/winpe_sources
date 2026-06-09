# DeleteCustomIfrLogs(void)

- ea: `0x14003642c`
- end: `0x14003648b`
- name: `?DeleteCustomIfrLogs@@YAXXZ`
- size: `95`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140036310`
- `0x14003baa0`

## callees

- `0x14003642c`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogDelete` at `0x140036461`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140036461`

## pseudocode

```c
void DeleteCustomIfrLogs(void)
{
  __int64 v0; // rbx

  v0 = 3;
  do
  {
    --v0;
    if ( qword_14006F228[4 * v0] )
    {
      imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
      qword_14006F228[4 * v0] = 0;
    }
  }
  while ( v0 );
}

```

## disassembly

```asm
0x14003642c  mov     [rsp+arg_0], rbx
0x140036431  mov     [rsp+arg_8], rsi
0x140036436  push    rdi
0x140036437  sub     rsp, 20h
0x14003643b  mov     ebx, 3
0x140036440  dec     rbx
0x140036443  lea     rsi, qword_14006F228
0x14003644a  mov     rdi, rbx
0x14003644d  shl     rdi, 5
0x140036451  mov     rdx, [rdi+rsi]
0x140036455  test    rdx, rdx
0x140036458  jz      short loc_140036475
0x14003645a  mov     rcx, cs:WPP_GLOBAL_Control
0x140036461  call    cs:__imp_imp_WppRecorderLogDelete
0x140036468  nop     dword ptr [rax+rax+00h]
0x14003646d  mov     qword ptr [rdi+rsi], 0
0x140036475  test    rbx, rbx
0x140036478  jnz     short loc_140036440
0x14003647a  mov     rbx, [rsp+28h+arg_0]
0x14003647f  mov     rsi, [rsp+28h+arg_8]
0x140036484  add     rsp, 20h
0x140036488  pop     rdi
0x140036489  retn
```
