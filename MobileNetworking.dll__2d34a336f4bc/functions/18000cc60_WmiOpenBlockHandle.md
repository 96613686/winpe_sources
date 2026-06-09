# WmiOpenBlockHandle

- ea: `0x18000cc60`
- end: `0x18000cc98`
- name: `WmiOpenBlockHandle`
- size: `56`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000cca0`
- `0x18000cf08`

## callees

- `0x18000cc60`

## import_xrefs

- `WMICLNT!WmiOpenBlock` at `0x18000cc89`
- `WMICLNT!WmiOpenBlock` at `0x18000cc89`

## pseudocode

```c
__int64 __fastcall WmiOpenBlockHandle(int a1)
{
  unsigned int v1; // edx
  __int64 v2; // rcx

  v1 = 0;
  v2 = 3LL * a1;
  if ( !qword_18001B020[v2] )
    return (unsigned int)WmiOpenBlock(*(&WmiOps + v2), *((unsigned int *)&WmiOps + 2 * v2 + 2));
  return v1;
}

```

## disassembly

```asm
0x18000cc60  sub     rsp, 28h
0x18000cc64  movsxd  rax, ecx
0x18000cc67  xor     edx, edx
0x18000cc69  lea     rcx, [rax+rax*2]
0x18000cc6d  lea     rax, WmiOps
0x18000cc74  lea     r8, [rax+10h]
0x18000cc78  lea     r8, [r8+rcx*8]
0x18000cc7c  cmp     [r8], rdx
0x18000cc7f  jnz     short loc_18000CC91
0x18000cc81  mov     edx, [rax+rcx*8+8]
0x18000cc85  mov     rcx, [rax+rcx*8]
0x18000cc89  call    cs:__imp_WmiOpenBlock
0x18000cc8f  mov     edx, eax
0x18000cc91  mov     eax, edx
0x18000cc93  add     rsp, 28h
0x18000cc97  retn
```
