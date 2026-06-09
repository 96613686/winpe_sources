# deleteDftCtx

- ea: `0x180047978`
- end: `0x180047a65`
- name: `deleteDftCtx`
- size: `237`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180047a70`
- `0x180047f10`
- `0x180048120`
- `0x180048d70`
- `0x180048f80`
- `0x180049b00`
- `0x180049d10`

## callees

- `0x18000d1f0`
- `0x180011020`
- `0x180047978`

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
0x180047978  test    rcx, rcx
0x18004797b  jz      locret_180047A64
0x180047981  mov     [rsp+arg_0], rbx
0x180047986  mov     [rsp+arg_8], rbp
0x18004798b  mov     [rsp+arg_10], rsi
0x180047990  push    rdi
0x180047991  sub     rsp, 20h
0x180047995  mov     rbx, rcx
0x180047998  mov     rcx, [rcx+30h]
0x18004799c  test    rcx, rcx
0x18004799f  jz      short loc_1800479A6
0x1800479a1  call    m7_ippsFree
0x1800479a6  mov     rcx, [rbx+38h]
0x1800479aa  test    rcx, rcx
0x1800479ad  jz      short loc_1800479B4
0x1800479af  call    m7_ippsFree
0x1800479b4  mov     rcx, [rbx+40h]
0x1800479b8  test    rcx, rcx
0x1800479bb  jz      short loc_1800479C2
0x1800479bd  call    m7_ippsFree
0x1800479c2  mov     rcx, [rbx+48h]
0x1800479c6  test    rcx, rcx
0x1800479c9  jz      short loc_1800479D0
0x1800479cb  call    m7_ippsFree
0x1800479d0  mov     rcx, [rbx+50h]
0x1800479d4  test    rcx, rcx
0x1800479d7  jz      short loc_1800479DE
0x1800479d9  call    m7_ippsFree
0x1800479de  mov     rcx, [rbx+70h]
0x1800479e2  test    rcx, rcx
0x1800479e5  jz      short loc_1800479EC
0x1800479e7  call    m7_ippsFree
0x1800479ec  mov     rcx, [rbx+60h]
0x1800479f0  test    rcx, rcx
0x1800479f3  jz      short loc_1800479FA
0x1800479f5  call    m7_ippsFFTFree_C_32fc
0x1800479fa  cmp     dword ptr [rbx+68h], 0
0x1800479fe  jz      short loc_180047A45
0x180047a00  mov     eax, [rbx+6Ch]
0x180047a03  xor     ebp, ebp
0x180047a05  xor     esi, esi
0x180047a07  inc     eax
0x180047a09  js      short loc_180047A45
0x180047a0b  lea     rdi, [rbx+88h]
0x180047a12  mov     rcx, [rdi+8]
0x180047a16  test    rcx, rcx
0x180047a19  jz      short loc_180047A20
0x180047a1b  call    m7_ippsFree
0x180047a20  cmp     qword ptr [rdi], 0
0x180047a24  jz      short loc_180047A36
0x180047a26  cmp     [rdi], rbp
0x180047a29  jz      short loc_180047A36
0x180047a2b  mov     rbp, [rdi]
0x180047a2e  mov     rcx, rbp
0x180047a31  call    m7_ippsFree
0x180047a36  mov     eax, [rbx+6Ch]
0x180047a39  inc     esi
0x180047a3b  add     rdi, 20h ; ' '
0x180047a3f  inc     eax
0x180047a41  cmp     esi, eax
0x180047a43  jle     short loc_180047A12
0x180047a45  and     dword ptr [rbx], 0
0x180047a48  mov     rcx, rbx
0x180047a4b  call    m7_ippsFree
0x180047a50  mov     rbx, [rsp+28h+arg_0]
0x180047a55  mov     rbp, [rsp+28h+arg_8]
0x180047a5a  mov     rsi, [rsp+28h+arg_10]
0x180047a5f  add     rsp, 20h
0x180047a63  pop     rdi
0x180047a64  retn
```
