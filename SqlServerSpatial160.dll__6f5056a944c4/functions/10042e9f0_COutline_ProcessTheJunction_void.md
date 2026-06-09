# COutline::ProcessTheJunction(void)

- ea: `0x10042e9f0`
- end: `0x10042eba7`
- name: `?ProcessTheJunction@COutline@@UEAAJXZ`
- size: `439`
- prototype: `__int64 __fastcall(COutline *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path`

## callees

- `0x10042e9f0`
- `0x10042ebb0`

## pseudocode

```c
__int64 __fastcall COutline::ProcessTheJunction(COutline *this)
{
  struct CScanner::CChain *i; // rbx
  __int64 v3; // rdx
  struct CScanner::CChain *v4; // rdi
  bool v5; // r14
  bool v6; // si
  __int16 v7; // cx
  __int16 v8; // ax
  bool v10; // [rsp+60h] [rbp+8h] BYREF
  struct CScanner::CChain *j; // [rsp+68h] [rbp+10h] BYREF
  struct CScanner::CChain *v12; // [rsp+70h] [rbp+18h] BYREF

  for ( i = (struct CScanner::CChain *)*((_QWORD *)this + 38); i; i = (struct CScanner::CChain *)*((_QWORD *)i + 3) )
  {
    if ( (*((_BYTE *)i + 72) & 0x40) == 0 )
      break;
  }
  v3 = *((_QWORD *)this + 42);
  for ( j = i; v3; v3 = *(_QWORD *)(v3 + 32) )
  {
    if ( (*(_BYTE *)(v3 + 72) & 0x40) == 0 )
      break;
  }
  v4 = (struct CScanner::CChain *)*((_QWORD *)this + 40);
  v12 = (struct CScanner::CChain *)v3;
  v5 = v3
    && (((unsigned __int8)~HIBYTE(*(unsigned __int16 *)(v3 + 72))
       ^ (unsigned __int8)~(*(unsigned __int16 *)(v3 + 72) >> 12))
      & 1) == 0;
  v10 = v5;
  v6 = v5;
  while ( v4 )
  {
    v7 = *((_WORD *)v4 + 36);
    if ( (v7 & 0x20) != 0 )
    {
      v4 = COutline::ClassifyCoincidentBundle(v4, &j, &v12, &v10);
      i = j;
      v6 = v10;
    }
    else
    {
      if ( (v7 & 0x4840) != 0 )
      {
        if ( v6 )
          *((_WORD *)v4 + 36) = v7 | 0x2000;
      }
      else
      {
        if ( i )
        {
          (*((void (__fastcall **)(struct CScanner::CChain *, struct CScanner::CChain *))v4 + 11))(v4, i);
          i = 0;
          j = 0;
        }
        else
        {
          (*((void (__fastcall **)(struct CScanner::CChain *))v4 + 10))(v4);
        }
        v8 = *((_WORD *)v4 + 36) >> 9;
        v12 = v4;
        if ( (v8 & 1) == 0 )
        {
          v6 = !v6;
          v10 = v6;
        }
      }
      v4 = (struct CScanner::CChain *)*((_QWORD *)v4 + 3);
    }
  }
  if ( v5 || !*((_DWORD *)this + 90) || *((_QWORD *)this + 40) || *((_QWORD *)this + 38) )
    *((_BYTE *)this + 386) = 1;
  return (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 65) + 16LL))(
           *((_QWORD *)this + 65),
           (char *)this + 296);
}

```

## disassembly

```asm
0x10042e9f0  push    rbp
0x10042e9f2  sub     rsp, 50h
0x10042e9f6  mov     [rsp+58h+var_10], rbx
0x10042e9fb  mov     rbp, rcx
0x10042e9fe  mov     rbx, [rcx+130h]
0x10042ea05  mov     [rsp+58h+var_18], rsi
0x10042ea0a  mov     [rsp+58h+var_20], rdi
0x10042ea0f  mov     [rsp+58h+var_30], r14
0x10042ea14  test    rbx, rbx
0x10042ea17  jz      short loc_10042EA34
0x10042ea19  nop     dword ptr [rax+00000000h]
0x10042ea20  movzx   eax, byte ptr [rbx+48h]
0x10042ea24  shr     al, 6
0x10042ea27  test    al, 1
0x10042ea29  jz      short loc_10042EA34
0x10042ea2b  mov     rbx, [rbx+18h]
0x10042ea2f  test    rbx, rbx
0x10042ea32  jnz     short loc_10042EA20
0x10042ea34  mov     rdx, [rcx+150h]
0x10042ea3b  mov     [rsp+58h+arg_8], rbx
0x10042ea40  test    rdx, rdx
0x10042ea43  jz      short loc_10042EA59
0x10042ea45  movzx   eax, byte ptr [rdx+48h]
0x10042ea49  shr     al, 6
0x10042ea4c  test    al, 1
0x10042ea4e  jz      short loc_10042EA59
0x10042ea50  mov     rdx, [rdx+20h]
0x10042ea54  test    rdx, rdx
0x10042ea57  jnz     short loc_10042EA45
0x10042ea59  mov     rdi, [rcx+140h]
0x10042ea60  mov     [rsp+58h+arg_10], rdx
0x10042ea65  test    rdx, rdx
0x10042ea68  jz      short loc_10042EA86
0x10042ea6a  movzx   eax, word ptr [rdx+48h]
0x10042ea6e  mov     ecx, eax
0x10042ea70  shr     eax, 8
0x10042ea73  shr     ecx, 0Ch
0x10042ea76  not     eax
0x10042ea78  not     ecx
0x10042ea7a  xor     ecx, eax
0x10042ea7c  test    cl, 1
0x10042ea7f  jnz     short loc_10042EA86
0x10042ea81  mov     r14b, 1
0x10042ea84  jmp     short loc_10042EA89
0x10042ea86  xor     r14b, r14b
0x10042ea89  mov     [rsp+58h+arg_0], r14b
0x10042ea8e  movzx   esi, r14b
0x10042ea92  test    rdi, rdi
0x10042ea95  jz      loc_10042EB50
0x10042ea9b  mov     [rsp+58h+var_28], r12
0x10042eaa0  mov     r12d, 2000h
0x10042eaa6  mov     [rsp+58h+var_38], r15
0x10042eaab  mov     r15d, 4840h
0x10042eab1  movzx   ecx, word ptr [rdi+48h]
0x10042eab5  movzx   eax, cl
0x10042eab8  shr     al, 5
0x10042eabb  test    al, 1
0x10042eabd  jz      short loc_10042EAEA
0x10042eabf  lea     r9, [rsp+58h+arg_0]; bool *
0x10042eac4  mov     rcx, rdi; struct CScanner::CChain *
0x10042eac7  lea     r8, [rsp+58h+arg_10]; struct CScanner::CChain **
0x10042eacc  lea     rdx, [rsp+58h+arg_8]; struct CScanner::CChain **
0x10042ead1  call    ?ClassifyCoincidentBundle@COutline@@KAPEAVCChain@CScanner@@PEAV23@PEAPEAV23@1PEA_N@Z; COutline::ClassifyCoincidentBundle(CScanner::CChain *,CScanner::CChain * *,CScanner::CChain * *,bool *)
0x10042ead6  mov     rdx, [rsp+58h+arg_10]
0x10042eadb  mov     rdi, rax
0x10042eade  mov     rbx, [rsp+58h+arg_8]
0x10042eae3  movzx   esi, [rsp+58h+arg_0]
0x10042eae8  jmp     short loc_10042EB3D
0x10042eaea  test    r15w, cx
0x10042eaee  jz      short loc_10042EAFF
0x10042eaf0  test    sil, sil
0x10042eaf3  jz      short loc_10042EB39
0x10042eaf5  or      cx, r12w
0x10042eaf9  mov     [rdi+48h], cx
0x10042eafd  jmp     short loc_10042EB39
0x10042eaff  mov     rcx, rdi
0x10042eb02  test    rbx, rbx
0x10042eb05  jz      short loc_10042EB16
0x10042eb07  mov     rdx, rbx
0x10042eb0a  call    qword ptr [rdi+58h]
0x10042eb0d  xor     ebx, ebx
0x10042eb0f  mov     [rsp+58h+arg_8], rbx
0x10042eb14  jmp     short loc_10042EB19
0x10042eb16  call    qword ptr [rdi+50h]
0x10042eb19  movzx   eax, word ptr [rdi+48h]
0x10042eb1d  mov     rdx, rdi
0x10042eb20  shr     ax, 9
0x10042eb24  mov     [rsp+58h+arg_10], rdx
0x10042eb29  test    al, 1
0x10042eb2b  jnz     short loc_10042EB39
0x10042eb2d  test    sil, sil
0x10042eb30  setz    sil
0x10042eb34  mov     [rsp+58h+arg_0], sil
0x10042eb39  mov     rdi, [rdi+18h]
0x10042eb3d  test    rdi, rdi
0x10042eb40  jnz     loc_10042EAB1
0x10042eb46  mov     r15, [rsp+58h+var_38]
0x10042eb4b  mov     r12, [rsp+58h+var_28]
0x10042eb50  mov     rdi, [rsp+58h+var_20]
0x10042eb55  test    r14b, r14b
0x10042eb58  mov     r14, [rsp+58h+var_30]
0x10042eb5d  mov     rsi, [rsp+58h+var_18]
0x10042eb62  mov     rbx, [rsp+58h+var_10]
0x10042eb67  jnz     short loc_10042EB86
0x10042eb69  cmp     dword ptr [rbp+168h], 0
0x10042eb70  jbe     short loc_10042EB86
0x10042eb72  cmp     qword ptr [rbp+140h], 0
0x10042eb7a  jnz     short loc_10042EB86
0x10042eb7c  cmp     qword ptr [rbp+130h], 0
0x10042eb84  jz      short loc_10042EB8D
0x10042eb86  mov     byte ptr [rbp+182h], 1
0x10042eb8d  mov     rcx, [rbp+208h]
0x10042eb94  lea     rdx, [rbp+128h]
0x10042eb9b  mov     rax, [rcx]
0x10042eb9e  add     rsp, 50h
0x10042eba2  pop     rbp
0x10042eba3  jmp     qword ptr [rax+10h]
```
