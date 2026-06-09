# mkl_serv_memmove_s

- ea: `0x180453430`
- end: `0x180453540`
- name: `mkl_serv_memmove_s`
- size: `272`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18012b630`
- `0x18012b7b0`

## callees

- `0x180122170`
- `0x1801222c0`
- `0x180122520`
- `0x180453430`

## string_xrefs

- `0x180453522`: `memmove_s: dest is null`
- `0x180453504`: `memmove_s: dmax is 0`
- `0x1804534c8`: `memmove_s: smax is 0`
- `0x1804534a2`: `memmove_s: smax exceeds max`
- `0x18045347c`: `memmove_s: src is null`
- `0x1804534e6`: `memmove_s: dmax exceeds max`

## pseudocode

```c
__int64 __fastcall mkl_serv_memmove_s(__int64 a1, unsigned __int64 a2, __int64 a3, unsigned __int64 a4)
{
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a2 > 0x10000000 )
      {
        mkl_serv_invoke_safe_mem_constraint_handler("memmove_s: dmax exceeds max", 0, 403);
        return 403;
      }
      else if ( a4 )
      {
        if ( a4 > a2 )
        {
          mkl_serv_mem_prim_set(a1, a2, 0);
          mkl_serv_invoke_safe_mem_constraint_handler("memmove_s: smax exceeds max", 0, 403);
          return 403;
        }
        else if ( a3 )
        {
          mkl_serv_mem_prim_move(a1, a3, (unsigned int)a4);
          return 0;
        }
        else
        {
          mkl_serv_mem_prim_set(a1, a2, 0);
          mkl_serv_invoke_safe_mem_constraint_handler("memmove_s: src is null", 0, 400);
          return 400;
        }
      }
      else
      {
        mkl_serv_mem_prim_set(a1, a2, 0);
        mkl_serv_invoke_safe_mem_constraint_handler("memmove_s: smax is 0", 0, 401);
        return 401;
      }
    }
    else
    {
      mkl_serv_invoke_safe_mem_constraint_handler("memmove_s: dmax is 0", 0, 401);
      return 401;
    }
  }
  else
  {
    mkl_serv_invoke_safe_mem_constraint_handler("memmove_s: dest is null", 0, 400);
    return 400;
  }
}

```

## disassembly

```asm
0x180453430  sub     rsp, 28h
0x180453434  test    rcx, rcx
0x180453437  jz      loc_180453522
0x18045343d  test    rdx, rdx
0x180453440  jz      loc_180453504
0x180453446  cmp     rdx, 10000000h
0x18045344d  ja      loc_1804534E6
0x180453453  test    r9, r9
0x180453456  jz      short loc_1804534C0
0x180453458  cmp     r9, rdx
0x18045345b  ja      short loc_18045349A
0x18045345d  test    r8, r8
0x180453460  jz      short loc_180453474
0x180453462  mov     rdx, r8
0x180453465  mov     r8d, r9d
0x180453468  call    mkl_serv_mem_prim_move
0x18045346d  xor     eax, eax
0x18045346f  add     rsp, 28h
0x180453473  retn
0x180453474  xor     r8d, r8d
0x180453477  call    mkl_serv_mem_prim_set
0x18045347c  lea     rcx, aMemmoveSSrcIsN; "memmove_s: src is null"
0x180453483  xor     edx, edx
0x180453485  mov     r8d, 190h
0x18045348b  call    mkl_serv_invoke_safe_mem_constraint_handler
0x180453490  mov     eax, 190h
0x180453495  add     rsp, 28h
0x180453499  retn
0x18045349a  xor     r8d, r8d
0x18045349d  call    mkl_serv_mem_prim_set
0x1804534a2  lea     rcx, aMemmoveSSmaxEx; "memmove_s: smax exceeds max"
0x1804534a9  xor     edx, edx
0x1804534ab  mov     r8d, 193h
0x1804534b1  call    mkl_serv_invoke_safe_mem_constraint_handler
0x1804534b6  mov     eax, 193h
0x1804534bb  add     rsp, 28h
0x1804534bf  retn
0x1804534c0  xor     r8d, r8d
0x1804534c3  call    mkl_serv_mem_prim_set
0x1804534c8  lea     rcx, aMemmoveSSmaxIs; "memmove_s: smax is 0"
0x1804534cf  xor     edx, edx
0x1804534d1  mov     r8d, 191h
0x1804534d7  call    mkl_serv_invoke_safe_mem_constraint_handler
0x1804534dc  mov     eax, 191h
0x1804534e1  add     rsp, 28h
0x1804534e5  retn
0x1804534e6  lea     rcx, aMemmoveSDmaxEx; "memmove_s: dmax exceeds max"
0x1804534ed  xor     edx, edx
0x1804534ef  mov     r8d, 193h
0x1804534f5  call    mkl_serv_invoke_safe_mem_constraint_handler
0x1804534fa  mov     eax, 193h
0x1804534ff  add     rsp, 28h
0x180453503  retn
0x180453504  lea     rcx, aMemmoveSDmaxIs; "memmove_s: dmax is 0"
0x18045350b  xor     edx, edx
0x18045350d  mov     r8d, 191h
0x180453513  call    mkl_serv_invoke_safe_mem_constraint_handler
0x180453518  mov     eax, 191h
0x18045351d  add     rsp, 28h
0x180453521  retn
0x180453522  lea     rcx, aMemmoveSDestIs; "memmove_s: dest is null"
0x180453529  xor     edx, edx
0x18045352b  mov     r8d, 190h
0x180453531  call    mkl_serv_invoke_safe_mem_constraint_handler
0x180453536  mov     eax, 190h
0x18045353b  add     rsp, 28h
0x18045353f  retn
```
