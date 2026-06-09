# RebalanceNode(_WX_BALANCED_LINKS *)

- ea: `0x18000a1ac`
- end: `0x18000a25f`
- name: `?RebalanceNode@@YAKPEAU_WX_BALANCED_LINKS@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(struct _WX_BALANCED_LINKS *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009f14`
- `0x18000a360`

## callees

- `0x18000a0c8`
- `0x18000a1ac`

## pseudocode

```c
__int64 __fastcall RebalanceNode(struct _WX_BALANCED_LINKS *a1)
{
  int v1; // r9d
  __int64 v2; // rax
  __int64 v3; // rdi
  __int64 v4; // r10
  __int64 v5; // r10
  __int64 v6; // r11
  __int64 result; // rax
  int v8; // ebx
  __int64 v9; // rdi
  __int64 **v10; // rcx
  char v11; // r9
  __int64 v12; // r10
  __int64 v13; // r11
  char v14; // r9
  __int64 v15; // r10

  v1 = *((char *)a1 + 24);
  v2 = 16;
  v3 = 8;
  if ( (_BYTE)v1 != 1 )
    v2 = 8;
  v4 = *(_QWORD *)((char *)a1 + v2);
  if ( *(_BYTE *)(v4 + 24) == (_BYTE)v1 )
  {
    PromoteNode(*(__int64 ***)((char *)a1 + v2));
    *(_BYTE *)(v5 + 24) = 0;
    *(_BYTE *)(v6 + 24) = 0;
    return 0;
  }
  v8 = -v1;
  if ( *(char *)(v4 + 24) == -v1 )
  {
    if ( (_BYTE)v1 != 1 )
      v3 = 16;
    v9 = *(_QWORD *)(v3 + v4);
    PromoteNode((__int64 **)v9);
    PromoteNode(v10);
    *(_BYTE *)(v13 + 24) = 0;
    *(_BYTE *)(v12 + 24) = 0;
    if ( *(_BYTE *)(v9 + 24) == v11 )
    {
      *(_BYTE *)(v13 + 24) = -v11;
    }
    else if ( *(char *)(v9 + 24) == v8 )
    {
      *(_BYTE *)(v12 + 24) = v11;
    }
    *(_BYTE *)(v9 + 24) = 0;
    return 0;
  }
  PromoteNode((__int64 **)v4);
  result = 1;
  *(_BYTE *)(v15 + 24) = -v14;
  return result;
}

```

## disassembly

```asm
0x18000a1ac  mov     [rsp+arg_0], rbx
0x18000a1b1  push    rdi
0x18000a1b2  sub     rsp, 20h
0x18000a1b6  movsx   r9d, byte ptr [rcx+18h]
0x18000a1bb  mov     r11, rcx
0x18000a1be  mov     ecx, 10h
0x18000a1c3  cmp     r9b, 1
0x18000a1c7  mov     eax, ecx
0x18000a1c9  lea     edi, [rcx-8]
0x18000a1cc  cmovnz  eax, edi
0x18000a1cf  mov     r10, [rax+r11]
0x18000a1d3  cmp     [r10+18h], r9b
0x18000a1d7  jnz     short loc_18000A1EF
0x18000a1d9  mov     rcx, r10; struct _WX_BALANCED_LINKS *
0x18000a1dc  call    ?PromoteNode@@YAXPEAU_WX_BALANCED_LINKS@@@Z; PromoteNode(_WX_BALANCED_LINKS *)
0x18000a1e1  xor     ecx, ecx
0x18000a1e3  mov     [r10+18h], cl
0x18000a1e7  mov     [r11+18h], cl
0x18000a1eb  xor     eax, eax
0x18000a1ed  jmp     short loc_18000A254
0x18000a1ef  movsx   eax, byte ptr [r10+18h]
0x18000a1f4  mov     ebx, r9d
0x18000a1f7  neg     ebx
0x18000a1f9  cmp     eax, ebx
0x18000a1fb  jnz     short loc_18000A240
0x18000a1fd  cmp     r9b, 1
0x18000a201  cmovnz  rdi, rcx
0x18000a205  mov     rdi, [rdi+r10]
0x18000a209  mov     rcx, rdi; struct _WX_BALANCED_LINKS *
0x18000a20c  call    ?PromoteNode@@YAXPEAU_WX_BALANCED_LINKS@@@Z; PromoteNode(_WX_BALANCED_LINKS *)
0x18000a211  call    ?PromoteNode@@YAXPEAU_WX_BALANCED_LINKS@@@Z; PromoteNode(_WX_BALANCED_LINKS *)
0x18000a216  xor     cl, cl
0x18000a218  mov     [r11+18h], cl
0x18000a21c  mov     [r10+18h], cl
0x18000a220  cmp     [rdi+18h], r9b
0x18000a224  jnz     short loc_18000A22F
0x18000a226  neg     r9b
0x18000a229  mov     [r11+18h], r9b
0x18000a22d  jmp     short loc_18000A23B
0x18000a22f  movsx   eax, byte ptr [rdi+18h]
0x18000a233  cmp     eax, ebx
0x18000a235  jnz     short loc_18000A23B
0x18000a237  mov     [r10+18h], r9b
0x18000a23b  mov     [rdi+18h], cl
0x18000a23e  jmp     short loc_18000A1EB
0x18000a240  mov     rcx, r10; struct _WX_BALANCED_LINKS *
0x18000a243  call    ?PromoteNode@@YAXPEAU_WX_BALANCED_LINKS@@@Z; PromoteNode(_WX_BALANCED_LINKS *)
0x18000a248  neg     r9b
0x18000a24b  mov     eax, 1
0x18000a250  mov     [r10+18h], r9b
0x18000a254  mov     rbx, [rsp+28h+arg_0]
0x18000a259  add     rsp, 20h
0x18000a25d  pop     rdi
0x18000a25e  retn
```
