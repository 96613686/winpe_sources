# FindNodeOrParent(_WX_AVL_TABLE *,void *,_WX_BALANCED_LINKS * *)

- ea: `0x18000a04c`
- end: `0x18000a0c1`
- name: `?FindNodeOrParent@@YA?AW4_WX_TABLE_SEARCH_RESULT@@PEAU_WX_AVL_TABLE@@PEAXPEAPEAU_WX_BALANCED_LINKS@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000759c`
- `0x18000a268`
- `0x1800110b8`

## callees

- `0x18000a04c`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall FindNodeOrParent(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 i; // rbx
  int v7; // eax
  __int64 v8; // rax
  __int64 result; // rax

  if ( *(_DWORD *)(a1 + 44) )
  {
    for ( i = *(_QWORD *)(a1 + 16); ; i = v8 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(a1 + 72))(a1, a2, i + 32);
      if ( v7 )
      {
        if ( v7 != 1 )
        {
          *a3 = i;
          return 1;
        }
        v8 = *(_QWORD *)(i + 16);
        if ( !v8 )
        {
          result = 3;
          goto LABEL_10;
        }
      }
      else
      {
        v8 = *(_QWORD *)(i + 8);
        if ( !v8 )
        {
          result = 2;
LABEL_10:
          *a3 = i;
          return result;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a04c  push    rbx
0x18000a04e  push    rbp
0x18000a04f  push    rsi
0x18000a050  push    rdi
0x18000a051  sub     rsp, 28h
0x18000a055  cmp     dword ptr [rcx+2Ch], 0
0x18000a059  mov     rsi, r8
0x18000a05c  mov     rbp, rdx
0x18000a05f  mov     rdi, rcx
0x18000a062  jz      short loc_18000A0B6
0x18000a064  mov     rbx, [rcx+10h]
0x18000a068  mov     rax, [rdi+48h]
0x18000a06c  lea     r8, [rbx+20h]
0x18000a070  mov     rdx, rbp
0x18000a073  mov     rcx, rdi
0x18000a076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a07b  test    eax, eax
0x18000a07d  jnz     short loc_18000A08F
0x18000a07f  mov     rax, [rbx+8]
0x18000a083  test    rax, rax
0x18000a086  jnz     short loc_18000A09D
0x18000a088  mov     eax, 2
0x18000a08d  jmp     short loc_18000A0A7
0x18000a08f  cmp     eax, 1
0x18000a092  jnz     short loc_18000A0AC
0x18000a094  mov     rax, [rbx+10h]
0x18000a098  test    rax, rax
0x18000a09b  jz      short loc_18000A0A2
0x18000a09d  mov     rbx, rax
0x18000a0a0  jmp     short loc_18000A068
0x18000a0a2  mov     eax, 3
0x18000a0a7  mov     [rsi], rbx
0x18000a0aa  jmp     short loc_18000A0B8
0x18000a0ac  mov     [rsi], rbx
0x18000a0af  mov     eax, 1
0x18000a0b4  jmp     short loc_18000A0B8
0x18000a0b6  xor     eax, eax
0x18000a0b8  add     rsp, 28h
0x18000a0bc  pop     rdi
0x18000a0bd  pop     rsi
0x18000a0be  pop     rbp
0x18000a0bf  pop     rbx
0x18000a0c0  retn
```
