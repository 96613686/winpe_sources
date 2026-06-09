# CScanner::CJunction::InsertHead(CScanner::CChain *)

- ea: `0x1004415c0`
- end: `0x1004416ef`
- name: `?InsertHead@CJunction@CScanner@@QEAAXPEAVCChain@2@@Z`
- size: `303`
- prototype: `void __fastcall(CScanner::CJunction *__hidden this, struct CScanner::CChain *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x100441700`
- `0x1004418f0`

## callees

- `0x10043efe0`
- `0x1004415c0`

## pseudocode

```c
void __fastcall CScanner::CJunction::InsertHead(CScanner::CJunction *this, struct CScanner::CChain *a2)
{
  __int64 v4; // rax
  __int64 *v5; // rdi
  __int64 *v6; // rbp
  __int64 v7; // r14
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int64 v12; // r9

  if ( *(_QWORD *)a2 == *((_QWORD *)a2 + 2) )
  {
    v4 = *((_WORD *)a2 + 36) & 1;
    ++*((_DWORD *)this + v4 + 16);
  }
  else
  {
    v5 = (__int64 *)*((_QWORD *)this + 3);
    if ( v5 )
    {
      v6 = 0;
      v7 = *(_QWORD *)(*((_QWORD *)a2 + 1) + 24LL);
      if ( *((_QWORD *)this + 4) )
      {
        do
        {
          if ( (unsigned int)CScanner::CVertex::LocateVertex(v5[1], v7) != 1 )
            break;
          v6 = v5;
          v5 = (__int64 *)v5[3];
        }
        while ( v6 != *((__int64 **)this + 4) );
      }
      *((_QWORD *)a2 + 4) = v6;
      *((_QWORD *)a2 + 3) = v5;
      if ( v6 )
        v6[3] = (__int64)a2;
      if ( v5 )
        v5[4] = (__int64)a2;
      if ( v5 == *((__int64 **)this + 3) )
      {
        *((_QWORD *)this + 3) = a2;
      }
      else if ( v6 == *((__int64 **)this + 4) )
      {
        *((_QWORD *)this + 4) = a2;
      }
    }
    else
    {
      *((_QWORD *)this + 4) = a2;
      *((_QWORD *)this + 3) = a2;
    }
  }
  v8 = *(_QWORD *)a2;
  v9 = *((_QWORD *)this + 9);
  v10 = *(_QWORD *)(*(_QWORD *)a2 + 96LL);
  if ( v10 != v9 )
  {
    v11 = *(_QWORD *)(*((_QWORD *)this + 7) + 112LL);
    if ( v10 == v11 )
    {
      *(_QWORD *)(v8 + 96) = v9;
    }
    else if ( v9 == v11 )
    {
      if ( !*((_BYTE *)this + 89) )
      {
        *((_QWORD *)this + 9) = v10;
        *((_BYTE *)this + 88) = 1;
      }
    }
    else
    {
      v12 = *((_QWORD *)this + 10);
      if ( !v12
        || (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v12 + 8LL))(
             *((_QWORD *)this + 10),
             *(_QWORD *)(v8 + 96)) )
      {
        *((_QWORD *)this + 9) = v11;
        *((_WORD *)this + 44) = 257;
      }
    }
  }
}

```

## disassembly

```asm
0x1004415c0  mov     [rsp+arg_18], rbx
0x1004415c5  push    rdi
0x1004415c6  sub     rsp, 20h
0x1004415ca  mov     rax, [rdx+10h]
0x1004415ce  mov     rbx, rcx
0x1004415d1  mov     [rsp+28h+arg_0], rbp
0x1004415d6  mov     [rsp+28h+arg_8], rsi
0x1004415db  mov     rsi, rdx
0x1004415de  cmp     [rdx], rax
0x1004415e1  jnz     short loc_1004415F0
0x1004415e3  movzx   eax, word ptr [rdx+48h]
0x1004415e7  and     eax, 1
0x1004415ea  inc     dword ptr [rcx+rax*4+40h]
0x1004415ee  jmp     short loc_10044166D
0x1004415f0  mov     rdi, [rcx+18h]
0x1004415f4  test    rdi, rdi
0x1004415f7  jz      short loc_100441665
0x1004415f9  mov     rax, [rdx+8]
0x1004415fd  xor     ebp, ebp
0x1004415ff  mov     [rsp+28h+arg_10], r14
0x100441604  mov     r14, [rax+18h]
0x100441608  cmp     [rcx+20h], rbp
0x10044160c  jz      short loc_10044162E
0x10044160e  xchg    ax, ax
0x100441610  mov     rcx, [rdi+8]
0x100441614  mov     rdx, r14
0x100441617  call    ?LocateVertex@CVertex@CScanner@@QEBA?AW4SIDEINDICATOR@CLineSegmentIntersection@RobustIntersections@@PEBV12@@Z; CScanner::CVertex::LocateVertex(CScanner::CVertex const *)
0x10044161c  cmp     eax, 1
0x10044161f  jnz     short loc_10044162E
0x100441621  mov     rbp, rdi
0x100441624  mov     rdi, [rdi+18h]
0x100441628  cmp     rbp, [rbx+20h]
0x10044162c  jnz     short loc_100441610
0x10044162e  mov     r14, [rsp+28h+arg_10]
0x100441633  mov     [rsi+20h], rbp
0x100441637  mov     [rsi+18h], rdi
0x10044163b  test    rbp, rbp
0x10044163e  jz      short loc_100441644
0x100441640  mov     [rbp+18h], rsi
0x100441644  test    rdi, rdi
0x100441647  jz      short loc_10044164D
0x100441649  mov     [rdi+20h], rsi
0x10044164d  cmp     rdi, [rbx+18h]
0x100441651  jnz     short loc_100441659
0x100441653  mov     [rbx+18h], rsi
0x100441657  jmp     short loc_10044166D
0x100441659  cmp     rbp, [rbx+20h]
0x10044165d  jnz     short loc_10044166D
0x10044165f  mov     [rbx+20h], rsi
0x100441663  jmp     short loc_10044166D
0x100441665  mov     [rcx+20h], rsi
0x100441669  mov     [rcx+18h], rsi
0x10044166d  mov     rdx, [rsi]
0x100441670  mov     r8, [rbx+48h]
0x100441674  mov     rsi, [rsp+28h+arg_8]
0x100441679  mov     rbp, [rsp+28h+arg_0]
0x10044167e  mov     rcx, [rdx+60h]
0x100441682  cmp     rcx, r8
0x100441685  jz      short loc_1004416E4
0x100441687  mov     rax, [rbx+38h]
0x10044168b  mov     rdi, [rax+70h]
0x10044168f  cmp     rcx, rdi
0x100441692  jnz     short loc_1004416A3
0x100441694  mov     [rdx+60h], r8
0x100441698  mov     rbx, [rsp+28h+arg_18]
0x10044169d  add     rsp, 20h
0x1004416a1  pop     rdi
0x1004416a2  retn
0x1004416a3  cmp     r8, rdi
0x1004416a6  jz      short loc_1004416D6
0x1004416a8  mov     r9, [rbx+50h]
0x1004416ac  test    r9, r9
0x1004416af  jz      short loc_1004416C1
0x1004416b1  mov     rax, [r9]
0x1004416b4  mov     rdx, rcx
0x1004416b7  mov     rcx, r9
0x1004416ba  call    qword ptr [rax+8]
0x1004416bd  test    al, al
0x1004416bf  jz      short loc_1004416E4
0x1004416c1  mov     [rbx+48h], rdi
0x1004416c5  mov     word ptr [rbx+58h], 101h
0x1004416cb  mov     rbx, [rsp+28h+arg_18]
0x1004416d0  add     rsp, 20h
0x1004416d4  pop     rdi
0x1004416d5  retn
0x1004416d6  cmp     byte ptr [rbx+59h], 0
0x1004416da  jnz     short loc_1004416E4
0x1004416dc  mov     [rbx+48h], rcx
0x1004416e0  mov     byte ptr [rbx+58h], 1
0x1004416e4  mov     rbx, [rsp+28h+arg_18]
0x1004416e9  add     rsp, 20h
0x1004416ed  pop     rdi
0x1004416ee  retn
```
