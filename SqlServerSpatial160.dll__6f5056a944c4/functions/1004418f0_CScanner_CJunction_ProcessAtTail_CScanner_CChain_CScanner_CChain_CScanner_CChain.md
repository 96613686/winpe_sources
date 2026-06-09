# CScanner::CJunction::ProcessAtTail(CScanner::CChain *,CScanner::CChain *,CScanner::CChain *)

- ea: `0x1004418f0`
- end: `0x100441af4`
- name: `?ProcessAtTail@CJunction@CScanner@@QEAAJPEAVCChain@2@00@Z`
- size: `516`
- prototype: `__int64 __fastcall(CScanner::CJunction *__hidden this, struct CScanner::CChain *, struct CScanner::CChain *, struct CScanner::CChain *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x100442350`

## callees

- `0x10043ef20`
- `0x1004412e0`
- `0x1004415c0`
- `0x1004418f0`
- `0x100444130`

## pseudocode

```c
__int64 __fastcall CScanner::CJunction::ProcessAtTail(
        CScanner::CJunction *this,
        struct CScanner::CChain *a2,
        struct CScanner::CChain *a3,
        struct CScanner::CChain *a4)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdi
  __int64 v18; // r9
  __int64 v19; // rdx
  struct CScanner::CChain *v20; // rdi
  CScanner::CChainList *v21; // rsi
  __int64 v22; // rdx

  *((_QWORD *)this + 2) = a2;
  *((_QWORD *)this + 1) = a2;
  v6 = *((_QWORD *)a2 + 2);
  *(_QWORD *)this = v6;
  *((_QWORD *)this + 9) = *(_QWORD *)(v6 + 96);
  *(_WORD *)((char *)this + 89) = 0;
  *((_BYTE *)this + 88) = 0;
  for ( *((_QWORD *)this + 5) = a3; a3; *((_QWORD *)this + 5) = a3 )
  {
    if ( (unsigned int)CScanner::CVertex::CompareWith(*((_QWORD *)a3 + 2), *(_QWORD *)this) )
      break;
    v7 = *((_QWORD *)this + 5);
    v8 = *((_QWORD *)this + 9);
    *((_QWORD *)this + 1) = v7;
    v9 = *(_QWORD *)(v7 + 16);
    v10 = *(_QWORD *)(v9 + 96);
    if ( v10 != v8 )
    {
      v11 = *(_QWORD *)(*((_QWORD *)this + 7) + 112LL);
      if ( v10 == v11 )
      {
        *(_QWORD *)(v9 + 96) = v8;
      }
      else if ( v8 == v11 )
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
               *(_QWORD *)(v9 + 96)) )
        {
          *((_QWORD *)this + 9) = v11;
          *((_WORD *)this + 44) = 257;
        }
      }
    }
    a3 = *(struct CScanner::CChain **)(*((_QWORD *)this + 5) + 32LL);
  }
  for ( *((_QWORD *)this + 6) = a4; a4; *((_QWORD *)this + 6) = a4 )
  {
    if ( (unsigned int)CScanner::CVertex::CompareWith(*((_QWORD *)a4 + 2), *(_QWORD *)this) )
      break;
    v13 = *((_QWORD *)this + 6);
    v14 = *((_QWORD *)this + 9);
    *((_QWORD *)this + 2) = v13;
    v15 = *(_QWORD *)(v13 + 16);
    v16 = *(_QWORD *)(v15 + 96);
    if ( v16 != v14 )
    {
      v17 = *(_QWORD *)(*((_QWORD *)this + 7) + 112LL);
      if ( v16 == v17 )
      {
        *(_QWORD *)(v15 + 96) = v14;
      }
      else if ( v14 == v17 )
      {
        if ( !*((_BYTE *)this + 89) )
        {
          *((_QWORD *)this + 9) = v16;
          *((_BYTE *)this + 88) = 1;
        }
      }
      else
      {
        v18 = *((_QWORD *)this + 10);
        if ( !v18
          || (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v18 + 8LL))(
               *((_QWORD *)this + 10),
               *(_QWORD *)(v15 + 96)) )
        {
          *((_QWORD *)this + 9) = v17;
          *((_WORD *)this + 44) = 257;
        }
      }
    }
    a4 = *(struct CScanner::CChain **)(*((_QWORD *)this + 6) + 24LL);
  }
  v19 = *((_QWORD *)this + 7);
  v20 = 0;
  v21 = (CScanner::CChainList *)(v19 + 8);
  if ( *(_DWORD *)(v19 + 204) != 1 )
    v20 = *(struct CScanner::CChain **)(*(_QWORD *)(v19 + 208) + 8LL);
  while ( v20 && !(unsigned int)CScanner::CVertex::CompareWith(*(_QWORD *)this, *(_QWORD *)v20) )
  {
    CScanner::CChainList::Pop(v21);
    CScanner::CJunction::InsertHead(this, v20);
    v22 = *((_QWORD *)this + 7);
    v20 = 0;
    v21 = (CScanner::CChainList *)(v22 + 8);
    if ( *(_DWORD *)(v22 + 204) != 1 )
      v20 = *(struct CScanner::CChain **)(*(_QWORD *)(v22 + 208) + 8LL);
  }
  return CScanner::CJunction::Flush((__int64 **)this);
}

```

## disassembly

```asm
0x1004418f0  mov     [rsp+arg_0], rbx
0x1004418f5  mov     [rsp+arg_8], rsi
0x1004418fa  push    rdi
0x1004418fb  sub     rsp, 20h
0x1004418ff  mov     [rcx+10h], rdx
0x100441903  mov     rsi, r9
0x100441906  mov     [rcx+8], rdx
0x10044190a  mov     rbx, rcx
0x10044190d  mov     rax, [rdx+10h]
0x100441911  mov     [rcx], rax
0x100441914  mov     rax, [rax+60h]
0x100441918  mov     [rcx+48h], rax
0x10044191c  mov     word ptr [rcx+59h], 0
0x100441922  mov     byte ptr [rcx+58h], 0
0x100441926  mov     [rcx+28h], r8
0x10044192a  test    r8, r8
0x10044192d  jz      loc_1004419BC
0x100441933  mov     rdx, [rbx]
0x100441936  mov     rcx, [r8+10h]
0x10044193a  call    ?CompareWith@CVertex@CScanner@@QEBA?AW4COMPARISON@RobustIntersections@@PEBV12@@Z; CScanner::CVertex::CompareWith(CScanner::CVertex const *)
0x10044193f  test    eax, eax
0x100441941  jnz     short loc_1004419BC
0x100441943  mov     rax, [rbx+28h]
0x100441947  mov     r8, [rbx+48h]
0x10044194b  mov     [rbx+8], rax
0x10044194f  mov     rdx, [rax+10h]
0x100441953  mov     rcx, [rdx+60h]
0x100441957  cmp     rcx, r8
0x10044195a  jz      short loc_1004419A7
0x10044195c  mov     rax, [rbx+38h]
0x100441960  mov     rdi, [rax+70h]
0x100441964  cmp     rcx, rdi
0x100441967  jnz     short loc_10044196F
0x100441969  mov     [rdx+60h], r8
0x10044196d  jmp     short loc_1004419A7
0x10044196f  cmp     r8, rdi
0x100441972  jz      short loc_100441999
0x100441974  mov     r9, [rbx+50h]
0x100441978  test    r9, r9
0x10044197b  jz      short loc_10044198D
0x10044197d  mov     rax, [r9]
0x100441980  mov     rdx, rcx
0x100441983  mov     rcx, r9
0x100441986  call    qword ptr [rax+8]
0x100441989  test    al, al
0x10044198b  jz      short loc_1004419A7
0x10044198d  mov     [rbx+48h], rdi
0x100441991  mov     word ptr [rbx+58h], 101h
0x100441997  jmp     short loc_1004419A7
0x100441999  cmp     byte ptr [rbx+59h], 0
0x10044199d  jnz     short loc_1004419A7
0x10044199f  mov     [rbx+48h], rcx
0x1004419a3  mov     byte ptr [rbx+58h], 1
0x1004419a7  mov     rax, [rbx+28h]
0x1004419ab  mov     r8, [rax+20h]
0x1004419af  mov     [rbx+28h], r8
0x1004419b3  test    r8, r8
0x1004419b6  jnz     loc_100441933
0x1004419bc  mov     [rbx+30h], rsi
0x1004419c0  test    rsi, rsi
0x1004419c3  jz      loc_100441A59
0x1004419c9  nop     dword ptr [rax+00000000h]
0x1004419d0  mov     rdx, [rbx]
0x1004419d3  mov     rcx, [rsi+10h]
0x1004419d7  call    ?CompareWith@CVertex@CScanner@@QEBA?AW4COMPARISON@RobustIntersections@@PEBV12@@Z; CScanner::CVertex::CompareWith(CScanner::CVertex const *)
0x1004419dc  test    eax, eax
0x1004419de  jnz     short loc_100441A59
0x1004419e0  mov     rax, [rbx+30h]
0x1004419e4  mov     r8, [rbx+48h]
0x1004419e8  mov     [rbx+10h], rax
0x1004419ec  mov     rdx, [rax+10h]
0x1004419f0  mov     rcx, [rdx+60h]
0x1004419f4  cmp     rcx, r8
0x1004419f7  jz      short loc_100441A44
0x1004419f9  mov     rax, [rbx+38h]
0x1004419fd  mov     rdi, [rax+70h]
0x100441a01  cmp     rcx, rdi
0x100441a04  jnz     short loc_100441A0C
0x100441a06  mov     [rdx+60h], r8
0x100441a0a  jmp     short loc_100441A44
0x100441a0c  cmp     r8, rdi
0x100441a0f  jz      short loc_100441A36
0x100441a11  mov     r9, [rbx+50h]
0x100441a15  test    r9, r9
0x100441a18  jz      short loc_100441A2A
0x100441a1a  mov     rax, [r9]
0x100441a1d  mov     rdx, rcx
0x100441a20  mov     rcx, r9
0x100441a23  call    qword ptr [rax+8]
0x100441a26  test    al, al
0x100441a28  jz      short loc_100441A44
0x100441a2a  mov     [rbx+48h], rdi
0x100441a2e  mov     word ptr [rbx+58h], 101h
0x100441a34  jmp     short loc_100441A44
0x100441a36  cmp     byte ptr [rbx+59h], 0
0x100441a3a  jnz     short loc_100441A44
0x100441a3c  mov     [rbx+48h], rcx
0x100441a40  mov     byte ptr [rbx+58h], 1
0x100441a44  mov     rax, [rbx+30h]
0x100441a48  mov     rsi, [rax+18h]
0x100441a4c  mov     [rbx+30h], rsi
0x100441a50  test    rsi, rsi
0x100441a53  jnz     loc_1004419D0
0x100441a59  mov     rdx, [rbx+38h]
0x100441a5d  xor     edi, edi
0x100441a5f  cmp     dword ptr [rdx+0CCh], 1
0x100441a66  lea     rsi, [rdx+8]
0x100441a6a  jz      short loc_100441A77
0x100441a6c  mov     rax, [rdx+0D0h]
0x100441a73  mov     rdi, [rax+8]
0x100441a77  test    rdi, rdi
0x100441a7a  jz      short loc_100441ADD
0x100441a7c  mov     rdx, [rdi]
0x100441a7f  mov     rcx, [rbx]
0x100441a82  call    ?CompareWith@CVertex@CScanner@@QEBA?AW4COMPARISON@RobustIntersections@@PEBV12@@Z; CScanner::CVertex::CompareWith(CScanner::CVertex const *)
0x100441a87  test    eax, eax
0x100441a89  jnz     short loc_100441ADD
0x100441a8b  mov     rcx, rsi; this
0x100441a8e  call    ?Pop@CChainList@CScanner@@QEAAXXZ; CScanner::CChainList::Pop(void)
0x100441a93  mov     rdx, rdi; struct CScanner::CChain *
0x100441a96  mov     rcx, rbx; this
0x100441a99  call    ?InsertHead@CJunction@CScanner@@QEAAXPEAVCChain@2@@Z; CScanner::CJunction::InsertHead(CScanner::CChain *)
0x100441a9e  mov     rdx, [rbx+38h]
0x100441aa2  xor     edi, edi
0x100441aa4  cmp     dword ptr [rdx+0CCh], 1
0x100441aab  lea     rsi, [rdx+8]
0x100441aaf  jz      short loc_100441ABC
0x100441ab1  mov     rax, [rdx+0D0h]
0x100441ab8  mov     rdi, [rax+8]
0x100441abc  test    rdi, rdi
0x100441abf  jz      short loc_100441ADD
0x100441ac1  mov     rdx, [rdi]
0x100441ac4  mov     rcx, [rbx]
0x100441ac7  call    ?CompareWith@CVertex@CScanner@@QEBA?AW4COMPARISON@RobustIntersections@@PEBV12@@Z; CScanner::CVertex::CompareWith(CScanner::CVertex const *)
0x100441acc  test    eax, eax
0x100441ace  jnz     short loc_100441ADD
0x100441ad0  mov     rcx, rsi; this
0x100441ad3  call    ?Pop@CChainList@CScanner@@QEAAXXZ; CScanner::CChainList::Pop(void)
0x100441ad8  test    rdi, rdi
0x100441adb  jnz     short loc_100441A93
0x100441add  mov     rcx, rbx; this
0x100441ae0  mov     rbx, [rsp+28h+arg_0]
0x100441ae5  mov     rsi, [rsp+28h+arg_8]
0x100441aea  add     rsp, 20h
0x100441aee  pop     rdi
0x100441aef  jmp     ?Flush@CJunction@CScanner@@QEAAJXZ; CScanner::CJunction::Flush(void)
```
