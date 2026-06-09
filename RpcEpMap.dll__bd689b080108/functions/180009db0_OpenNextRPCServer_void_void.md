# OpenNextRPCServer(void *,void * *)

- ea: `0x180009db0`
- end: `0x180009def`
- name: `?OpenNextRPCServer@@YAJPEAXPEAPEAX@Z`
- size: `63`
- prototype: `__int64 __fastcall(_DWORD *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009ca4`
- `0x18000a404`

## callees

- `0x180009db0`
- `0x180009df8`

## pseudocode

```c
__int64 __fastcall OpenNextRPCServer(_DWORD *a1, void **a2)
{
  __int64 v4; // rcx
  __int64 result; // rax

  while ( 1 )
  {
    v4 = (unsigned int)*a1;
    if ( (unsigned int)v4 >= a1[1] )
      break;
    *a1 = v4 + 1;
    result = OpenRPCServerDebugInfo(a1[v4 + 2], a2);
    if ( (_DWORD)result != 2 )
      return result;
  }
  return 1734;
}

```

## disassembly

```asm
0x180009db0  mov     [rsp+arg_0], rbx
0x180009db5  push    rdi
0x180009db6  sub     rsp, 20h
0x180009dba  mov     rdi, rdx
0x180009dbd  mov     rbx, rcx
0x180009dc0  mov     ecx, [rbx]
0x180009dc2  cmp     ecx, [rbx+4]
0x180009dc5  jnb     short loc_180009DDF
0x180009dc7  lea     eax, [rcx+1]
0x180009dca  mov     rdx, rdi; void **
0x180009dcd  mov     [rbx], eax
0x180009dcf  mov     ecx, [rbx+rcx*4+8]; unsigned int
0x180009dd3  call    ?OpenRPCServerDebugInfo@@YAJKPEAPEAX@Z; OpenRPCServerDebugInfo(ulong,void * *)
0x180009dd8  cmp     eax, 2
0x180009ddb  jz      short loc_180009DC0
0x180009ddd  jmp     short loc_180009DE4
0x180009ddf  mov     eax, 6C6h
0x180009de4  mov     rbx, [rsp+28h+arg_0]
0x180009de9  add     rsp, 20h
0x180009ded  pop     rdi
0x180009dee  retn
```
