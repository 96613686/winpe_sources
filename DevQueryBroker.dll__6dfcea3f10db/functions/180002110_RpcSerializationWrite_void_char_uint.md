# RpcSerializationWrite(void *,char *,uint)

- ea: `0x180002110`
- end: `0x180002150`
- name: `?RpcSerializationWrite@@YAXPEAXPEADI@Z`
- size: `64`
- prototype: `void __fastcall(_DWORD *state, char *buffer, unsigned int size)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002110`
- `0x18000a192`

## pseudocode

```c
void __fastcall RpcSerializationWrite(_DWORD *state, char *buffer, unsigned int size)
{
  if ( state[2] - state[3] < size )
  {
    state[7] = 1;
  }
  else
  {
    memcpy_0((void *)(*(_QWORD *)state + (unsigned int)state[3]), buffer, size);
    state[3] += size;
  }
}

```

## disassembly

```asm
0x180002110  mov     [rsp+arg_0], rbx
0x180002115  push    rdi
0x180002116  sub     rsp, 20h
0x18000211a  mov     eax, [rcx+8]
0x18000211d  mov     rbx, rcx
0x180002120  sub     eax, [rcx+0Ch]
0x180002123  mov     edi, r8d
0x180002126  cmp     eax, r8d
0x180002129  jb      short loc_18000213E
0x18000212b  mov     ecx, [rcx+0Ch]
0x18000212e  mov     r8d, edi; Size
0x180002131  add     rcx, [rbx]; void *
0x180002134  call    memcpy_0
0x180002139  add     [rbx+0Ch], edi
0x18000213c  jmp     short loc_180002145
0x18000213e  mov     dword ptr [rcx+1Ch], 1
0x180002145  mov     rbx, [rsp+28h+arg_0]
0x18000214a  add     rsp, 20h
0x18000214e  pop     rdi
0x18000214f  retn
```
