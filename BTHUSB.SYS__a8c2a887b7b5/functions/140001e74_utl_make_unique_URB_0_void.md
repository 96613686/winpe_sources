# utl::make_unique<_URB,,0>(void)

- ea: `0x140001e74`
- end: `0x140001ec9`
- name: `??$make_unique@U_URB@@$$V$0A@@utl@@YA?AV?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@0@XZ`
- size: `85`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a290`
- `0x140019764`

## callees

- `0x140001e74`
- `0x14000e1c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140001e8f`
- `ntoskrnl!ExAllocatePool2` at `0x140001e8f`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique<_URB,,0>(_QWORD *a1)
{
  void *Pool2; // rax
  void *v3; // rbx

  Pool2 = (void *)ExAllocatePool2(64, 152, 1111642965);
  v3 = Pool2;
  if ( Pool2 )
    memset(Pool2, 0, 0x98u);
  else
    v3 = 0;
  *a1 = v3;
  return a1;
}

```

## disassembly

```asm
0x140001e74  mov     [rsp+arg_0], rbx
0x140001e79  push    rdi
0x140001e7a  sub     rsp, 20h
0x140001e7e  mov     edx, 98h
0x140001e83  mov     rdi, rcx
0x140001e86  mov     r8d, 42425355h
0x140001e8c  lea     ecx, [rdx-58h]
0x140001e8f  call    cs:__imp_ExAllocatePool2
0x140001e96  nop     dword ptr [rax+rax+00h]
0x140001e9b  mov     rbx, rax
0x140001e9e  test    rax, rax
0x140001ea1  jz      short loc_140001EB5
0x140001ea3  xor     edx, edx; Val
0x140001ea5  mov     r8d, 98h; Size
0x140001eab  mov     rcx, rax; void *
0x140001eae  call    memset
0x140001eb3  jmp     short loc_140001EB7
0x140001eb5  xor     ebx, ebx
0x140001eb7  mov     [rdi], rbx
0x140001eba  mov     rax, rdi
0x140001ebd  mov     rbx, [rsp+28h+arg_0]
0x140001ec2  add     rsp, 20h
0x140001ec6  pop     rdi
0x140001ec7  retn
```
