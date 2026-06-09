# DeleteNodeFromTree(_WX_AVL_TABLE *,_WX_BALANCED_LINKS *)

- ea: `0x180009f14`
- end: `0x18000a044`
- name: `?DeleteNodeFromTree@@YAXPEAU_WX_AVL_TABLE@@PEAU_WX_BALANCED_LINKS@@@Z`
- size: `304`
- prototype: `void __fastcall(struct _WX_AVL_TABLE *, struct _WX_BALANCED_LINKS *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a268`

## callees

- `0x180009f14`
- `0x18000a1ac`

## pseudocode

```c
void __fastcall DeleteNodeFromTree(struct _WX_AVL_TABLE *a1, struct _WX_BALANCED_LINKS *a2)
{
  struct _WX_BALANCED_LINKS *i; // rbx
  __int64 v5; // rcx
  char v6; // dl
  __int64 *v7; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rcx
  __int64 *v10; // rsi
  char v11; // al
  bool v12; // zf
  __int64 *v13; // rcx
  struct _WX_BALANCED_LINKS **v14; // rax
  struct _WX_BALANCED_LINKS **v15; // rax

  if ( *((_QWORD *)a2 + 1) && (i = (struct _WX_BALANCED_LINKS *)*((_QWORD *)a2 + 2)) != 0 )
  {
    if ( *((char *)a2 + 24) >= 0 )
    {
      while ( *((_QWORD *)i + 1) )
        i = (struct _WX_BALANCED_LINKS *)*((_QWORD *)i + 1);
    }
    else
    {
      for ( i = (struct _WX_BALANCED_LINKS *)*((_QWORD *)a2 + 1);
            *((_QWORD *)i + 2);
            i = (struct _WX_BALANCED_LINKS *)*((_QWORD *)i + 2) )
      {
        ;
      }
    }
  }
  else
  {
    i = a2;
  }
  v5 = *((_QWORD *)i + 1);
  v6 = -1;
  v7 = *(__int64 **)i;
  if ( v5 )
  {
    if ( (struct _WX_BALANCED_LINKS *)v7[1] == i )
    {
      v7[1] = v5;
    }
    else
    {
      v7[2] = v5;
      v6 = 1;
    }
    v9 = (_QWORD *)*((_QWORD *)i + 1);
  }
  else
  {
    v8 = *((_QWORD *)i + 2);
    if ( (struct _WX_BALANCED_LINKS *)v7[1] == i )
    {
      v7[1] = v8;
    }
    else
    {
      v7[2] = v8;
      v6 = 1;
    }
    v9 = (_QWORD *)*((_QWORD *)i + 2);
    if ( !v9 )
      goto LABEL_23;
  }
  *v9 = *(_QWORD *)i;
LABEL_23:
  *((_BYTE *)a1 + 24) = 0;
  v10 = *(__int64 **)i;
  while ( 1 )
  {
    v11 = *((_BYTE *)v10 + 24);
    if ( v11 == v6 )
    {
      *((_BYTE *)v10 + 24) = 0;
      goto LABEL_29;
    }
    if ( !v11 )
      break;
    if ( RebalanceNode((struct _WX_BALANCED_LINKS *)v10) )
      goto LABEL_34;
    v10 = (__int64 *)*v10;
LABEL_29:
    v6 = 1;
    v12 = *(_QWORD *)(*v10 + 16) == (_QWORD)v10;
    v10 = (__int64 *)*v10;
    if ( !v12 )
      v6 = -1;
  }
  *((_BYTE *)v10 + 24) = -v6;
  if ( *((_BYTE *)a1 + 24) )
    --*((_DWORD *)a1 + 12);
LABEL_34:
  if ( a2 != i )
  {
    *(_OWORD *)i = *(_OWORD *)a2;
    *((_OWORD *)i + 1) = *((_OWORD *)a2 + 1);
    v13 = *(__int64 **)i;
    if ( *(struct _WX_BALANCED_LINKS **)(*(_QWORD *)a2 + 8LL) == a2 )
      v13[1] = (__int64)i;
    else
      v13[2] = (__int64)i;
    v14 = (struct _WX_BALANCED_LINKS **)*((_QWORD *)i + 1);
    if ( v14 )
      *v14 = i;
    v15 = (struct _WX_BALANCED_LINKS **)*((_QWORD *)i + 2);
    if ( v15 )
      *v15 = i;
  }
}

```

## disassembly

```asm
0x180009f14  push    rbx
0x180009f16  push    rbp
0x180009f17  push    rsi
0x180009f18  push    rdi
0x180009f19  push    r15
0x180009f1b  sub     rsp, 20h
0x180009f1f  cmp     qword ptr [rdx+8], 0
0x180009f24  mov     rdi, rdx
0x180009f27  mov     rbp, rcx
0x180009f2a  jz      short loc_180009F5B
0x180009f2c  mov     rbx, [rdx+10h]
0x180009f30  test    rbx, rbx
0x180009f33  jz      short loc_180009F5B
0x180009f35  cmp     byte ptr [rdx+18h], 0
0x180009f39  jge     short loc_180009F45
0x180009f3b  mov     rbx, [rdx+8]
0x180009f3f  jmp     short loc_180009F52
0x180009f41  mov     rbx, [rbx+8]
0x180009f45  cmp     qword ptr [rbx+8], 0
0x180009f4a  jnz     short loc_180009F41
0x180009f4c  jmp     short loc_180009F5E
0x180009f4e  mov     rbx, [rbx+10h]
0x180009f52  cmp     qword ptr [rbx+10h], 0
0x180009f57  jnz     short loc_180009F4E
0x180009f59  jmp     short loc_180009F5E
0x180009f5b  mov     rbx, rdi
0x180009f5e  mov     rcx, [rbx+8]
0x180009f62  mov     dl, 0FFh
0x180009f64  mov     rax, [rbx]
0x180009f67  test    rcx, rcx
0x180009f6a  jnz     short loc_180009F8D
0x180009f6c  mov     rcx, [rbx+10h]
0x180009f70  cmp     [rax+8], rbx
0x180009f74  jnz     short loc_180009F7C
0x180009f76  mov     [rax+8], rcx
0x180009f7a  jmp     short loc_180009F82
0x180009f7c  mov     [rax+10h], rcx
0x180009f80  mov     dl, 1
0x180009f82  mov     rcx, [rbx+10h]
0x180009f86  test    rcx, rcx
0x180009f89  jz      short loc_180009FA9
0x180009f8b  jmp     short loc_180009FA3
0x180009f8d  cmp     [rax+8], rbx
0x180009f91  jnz     short loc_180009F99
0x180009f93  mov     [rax+8], rcx
0x180009f97  jmp     short loc_180009F9F
0x180009f99  mov     [rax+10h], rcx
0x180009f9d  mov     dl, 1
0x180009f9f  mov     rcx, [rbx+8]
0x180009fa3  mov     rax, [rbx]
0x180009fa6  mov     [rcx], rax
0x180009fa9  mov     byte ptr [rbp+18h], 0
0x180009fad  or      r15d, 0FFFFFFFFh
0x180009fb1  mov     rsi, [rbx]
0x180009fb4  mov     al, [rsi+18h]
0x180009fb7  cmp     al, dl
0x180009fb9  jnz     short loc_180009FC1
0x180009fbb  mov     byte ptr [rsi+18h], 0
0x180009fbf  jmp     short loc_180009FD4
0x180009fc1  test    al, al
0x180009fc3  jz      short loc_180009FE9
0x180009fc5  mov     rcx, rsi; struct _WX_BALANCED_LINKS *
0x180009fc8  call    ?RebalanceNode@@YAKPEAU_WX_BALANCED_LINKS@@@Z; RebalanceNode(_WX_BALANCED_LINKS *)
0x180009fcd  test    eax, eax
0x180009fcf  jnz     short loc_180009FF8
0x180009fd1  mov     rsi, [rsi]
0x180009fd4  mov     rax, [rsi]
0x180009fd7  mov     edx, 1
0x180009fdc  cmp     [rax+10h], rsi
0x180009fe0  mov     rsi, rax
0x180009fe3  cmovnz  edx, r15d
0x180009fe7  jmp     short loc_180009FB4
0x180009fe9  neg     dl
0x180009feb  mov     [rsi+18h], dl
0x180009fee  cmp     byte ptr [rbp+18h], 0
0x180009ff2  jz      short loc_180009FF8
0x180009ff4  add     [rbp+30h], r15d
0x180009ff8  cmp     rdi, rbx
0x180009ffb  jz      short loc_18000A039
0x180009ffd  movups  xmm0, xmmword ptr [rdi]
0x18000a000  movups  xmmword ptr [rbx], xmm0
0x18000a003  movups  xmm1, xmmword ptr [rdi+10h]
0x18000a007  movups  xmmword ptr [rbx+10h], xmm1
0x18000a00b  mov     rax, [rdi]
0x18000a00e  mov     rcx, [rbx]
0x18000a011  cmp     [rax+8], rdi
0x18000a015  jnz     short loc_18000A01D
0x18000a017  mov     [rcx+8], rbx
0x18000a01b  jmp     short loc_18000A021
0x18000a01d  mov     [rcx+10h], rbx
0x18000a021  mov     rax, [rbx+8]
0x18000a025  test    rax, rax
0x18000a028  jz      short loc_18000A02D
0x18000a02a  mov     [rax], rbx
0x18000a02d  mov     rax, [rbx+10h]
0x18000a031  test    rax, rax
0x18000a034  jz      short loc_18000A039
0x18000a036  mov     [rax], rbx
0x18000a039  add     rsp, 20h
0x18000a03d  pop     r15
0x18000a03f  pop     rdi
0x18000a040  pop     rsi
0x18000a041  pop     rbp
0x18000a042  pop     rbx
0x18000a043  retn
```
