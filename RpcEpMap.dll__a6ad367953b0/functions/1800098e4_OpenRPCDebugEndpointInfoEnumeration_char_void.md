# OpenRPCDebugEndpointInfoEnumeration(char *,void * *)

- ea: `0x1800098e4`
- end: `0x180009989`
- name: `?OpenRPCDebugEndpointInfoEnumeration@@YAJPEADPEAPEAX@Z`
- size: `165`
- prototype: `__int64 __fastcall(char *Src, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180007c50`

## callees

- `0x180002a00`
- `0x180005f48`
- `0x1800098e4`
- `0x18000a404`
- `0x18000a8a8`

## pseudocode

```c
__int64 __fastcall OpenRPCDebugEndpointInfoEnumeration(char *Src, void ****a2)
{
  void ***v4; // rax
  void ***v5; // rbx
  __int64 v7; // rax
  size_t v8; // rbp
  void **v9; // rax
  unsigned int v10; // edi

  *a2 = 0;
  v4 = (void ***)operator new(0x10u);
  v5 = v4;
  if ( !v4 )
    return 14;
  if ( Src )
  {
    v7 = -1;
    do
      ++v7;
    while ( Src[v7] );
    v8 = v7 + 1;
    v9 = (void **)operator new(v7 + 1);
    *v5 = v9;
    if ( !v9 )
    {
      v10 = 14;
LABEL_13:
      operator delete(v5);
      return v10;
    }
    memcpy_0(v9, Src, v8);
  }
  else
  {
    *v4 = 0;
  }
  v10 = OpenRPCSystemWideCellEnumeration(v5 + 1);
  if ( v10 )
  {
    if ( *v5 )
      operator delete(*v5);
    goto LABEL_13;
  }
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800098e4  push    rbx
0x1800098e6  push    rbp
0x1800098e7  push    rsi
0x1800098e8  push    rdi
0x1800098e9  sub     rsp, 28h
0x1800098ed  mov     rdi, rcx
0x1800098f0  mov     qword ptr [rdx], 0
0x1800098f7  mov     ecx, 10h; unsigned __int64
0x1800098fc  mov     rsi, rdx
0x1800098ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009904  mov     rbx, rax
0x180009907  test    rax, rax
0x18000990a  jnz     short loc_180009911
0x18000990c  lea     eax, [rbx+0Eh]
0x18000990f  jmp     short loc_180009980
0x180009911  test    rdi, rdi
0x180009914  jz      short loc_18000994C
0x180009916  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000991a  inc     rax
0x18000991d  cmp     byte ptr [rdi+rax], 0
0x180009921  jnz     short loc_18000991A
0x180009923  lea     rbp, [rax+1]
0x180009927  mov     rcx, rbp; unsigned __int64
0x18000992a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000992f  mov     [rbx], rax
0x180009932  test    rax, rax
0x180009935  jnz     short loc_18000993C
0x180009937  lea     edi, [rax+0Eh]
0x18000993a  jmp     short loc_18000996F
0x18000993c  mov     r8, rbp; Size
0x18000993f  mov     rdx, rdi; Src
0x180009942  mov     rcx, rax; void *
0x180009945  call    memcpy_0
0x18000994a  jmp     short loc_180009953
0x18000994c  mov     qword ptr [rax], 0
0x180009953  lea     rcx, [rbx+8]; void **
0x180009957  call    ?OpenRPCSystemWideCellEnumeration@@YAJPEAPEAX@Z; OpenRPCSystemWideCellEnumeration(void * *)
0x18000995c  mov     edi, eax
0x18000995e  test    eax, eax
0x180009960  jz      short loc_18000997B
0x180009962  mov     rcx, [rbx]; void *
0x180009965  test    rcx, rcx
0x180009968  jz      short loc_18000996F
0x18000996a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000996f  mov     rcx, rbx; void *
0x180009972  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009977  mov     eax, edi
0x180009979  jmp     short loc_180009980
0x18000997b  mov     [rsi], rbx
0x18000997e  xor     eax, eax
0x180009980  add     rsp, 28h
0x180009984  pop     rdi
0x180009985  pop     rsi
0x180009986  pop     rbp
0x180009987  pop     rbx
0x180009988  retn
```
