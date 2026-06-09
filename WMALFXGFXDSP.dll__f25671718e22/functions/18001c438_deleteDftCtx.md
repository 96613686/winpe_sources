# deleteDftCtx

- ea: `0x18001c438`
- end: `0x18001c525`
- name: `deleteDftCtx`
- size: `237`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c530`
- `0x18001c9d0`
- `0x18001cbe0`
- `0x18001d830`
- `0x18001da40`
- `0x18001e5c0`
- `0x18001e7d0`

## callees

- `0x180018970`
- `0x18001c438`
- `0x18001f8f0`

## pseudocode

```c
__int64 __fastcall deleteDftCtx(__int64 a1)
{
  __int64 v2; // rbp
  int v3; // esi
  _QWORD *v4; // rdi
  __int64 result; // rax

  if ( a1 )
  {
    if ( *(_QWORD *)(a1 + 48) )
      ((void (*)(void))m7_ippsFree)();
    if ( *(_QWORD *)(a1 + 56) )
      ((void (*)(void))m7_ippsFree)();
    if ( *(_QWORD *)(a1 + 64) )
      ((void (*)(void))m7_ippsFree)();
    if ( *(_QWORD *)(a1 + 72) )
      ((void (*)(void))m7_ippsFree)();
    if ( *(_QWORD *)(a1 + 80) )
      ((void (*)(void))m7_ippsFree)();
    if ( *(_QWORD *)(a1 + 112) )
      ((void (*)(void))m7_ippsFree)();
    if ( *(_QWORD *)(a1 + 96) )
      m7_ippsFFTFree_C_32fc();
    if ( *(_DWORD *)(a1 + 104) )
    {
      v2 = 0;
      v3 = 0;
      if ( *(_DWORD *)(a1 + 108) + 1 >= 0 )
      {
        v4 = (_QWORD *)(a1 + 136);
        do
        {
          if ( v4[1] )
            ((void (*)(void))m7_ippsFree)();
          if ( *v4 )
          {
            if ( *v4 != v2 )
            {
              v2 = *v4;
              m7_ippsFree(*v4);
            }
          }
          ++v3;
          v4 += 4;
        }
        while ( v3 <= *(_DWORD *)(a1 + 108) + 1 );
      }
    }
    *(_DWORD *)a1 = 0;
    return m7_ippsFree(a1);
  }
  return result;
}

```

## disassembly

```asm
0x18001c438  test    rcx, rcx
0x18001c43b  jz      locret_18001C524
0x18001c441  mov     [rsp+arg_0], rbx
0x18001c446  mov     [rsp+arg_8], rbp
0x18001c44b  mov     [rsp+arg_10], rsi
0x18001c450  push    rdi
0x18001c451  sub     rsp, 20h
0x18001c455  mov     rbx, rcx
0x18001c458  mov     rcx, [rcx+30h]
0x18001c45c  test    rcx, rcx
0x18001c45f  jz      short loc_18001C466
0x18001c461  call    m7_ippsFree
0x18001c466  mov     rcx, [rbx+38h]
0x18001c46a  test    rcx, rcx
0x18001c46d  jz      short loc_18001C474
0x18001c46f  call    m7_ippsFree
0x18001c474  mov     rcx, [rbx+40h]
0x18001c478  test    rcx, rcx
0x18001c47b  jz      short loc_18001C482
0x18001c47d  call    m7_ippsFree
0x18001c482  mov     rcx, [rbx+48h]
0x18001c486  test    rcx, rcx
0x18001c489  jz      short loc_18001C490
0x18001c48b  call    m7_ippsFree
0x18001c490  mov     rcx, [rbx+50h]
0x18001c494  test    rcx, rcx
0x18001c497  jz      short loc_18001C49E
0x18001c499  call    m7_ippsFree
0x18001c49e  mov     rcx, [rbx+70h]
0x18001c4a2  test    rcx, rcx
0x18001c4a5  jz      short loc_18001C4AC
0x18001c4a7  call    m7_ippsFree
0x18001c4ac  mov     rcx, [rbx+60h]
0x18001c4b0  test    rcx, rcx
0x18001c4b3  jz      short loc_18001C4BA
0x18001c4b5  call    m7_ippsFFTFree_C_32fc
0x18001c4ba  cmp     dword ptr [rbx+68h], 0
0x18001c4be  jz      short loc_18001C505
0x18001c4c0  mov     eax, [rbx+6Ch]
0x18001c4c3  xor     ebp, ebp
0x18001c4c5  xor     esi, esi
0x18001c4c7  inc     eax
0x18001c4c9  js      short loc_18001C505
0x18001c4cb  lea     rdi, [rbx+88h]
0x18001c4d2  mov     rcx, [rdi+8]
0x18001c4d6  test    rcx, rcx
0x18001c4d9  jz      short loc_18001C4E0
0x18001c4db  call    m7_ippsFree
0x18001c4e0  cmp     qword ptr [rdi], 0
0x18001c4e4  jz      short loc_18001C4F6
0x18001c4e6  cmp     [rdi], rbp
0x18001c4e9  jz      short loc_18001C4F6
0x18001c4eb  mov     rbp, [rdi]
0x18001c4ee  mov     rcx, rbp
0x18001c4f1  call    m7_ippsFree
0x18001c4f6  mov     eax, [rbx+6Ch]
0x18001c4f9  inc     esi
0x18001c4fb  add     rdi, 20h ; ' '
0x18001c4ff  inc     eax
0x18001c501  cmp     esi, eax
0x18001c503  jle     short loc_18001C4D2
0x18001c505  and     dword ptr [rbx], 0
0x18001c508  mov     rcx, rbx
0x18001c50b  call    m7_ippsFree
0x18001c510  mov     rbx, [rsp+28h+arg_0]
0x18001c515  mov     rbp, [rsp+28h+arg_8]
0x18001c51a  mov     rsi, [rsp+28h+arg_10]
0x18001c51f  add     rsp, 20h
0x18001c523  pop     rdi
0x18001c524  retn
```
