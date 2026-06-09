# DnsZtRuleNode::CreateCopy(DnsZtRuleNode * *)

- ea: `0x1800126d8`
- end: `0x180012831`
- name: `?CreateCopy@DnsZtRuleNode@@QEAAJPEAPEAV1@@Z`
- size: `345`
- prototype: `__int64 __fastcall(DnsZtRuleNode *__hidden this, struct DnsZtRuleNode **)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800111cc`
- `0x180011548`

## callees

- `0x180007674`
- `0x18000e3c8`
- `0x180012564`
- `0x1800125d4`
- `0x1800126d8`
- `0x1800129ec`
- `0x180013f19`

## pseudocode

```c
__int64 __fastcall DnsZtRuleNode::CreateCopy(DnsZtRuleNode *this, struct DnsZtRuleNode **a2)
{
  void *StringCopy_W; // rbp
  void *v3; // r14
  int v6; // ebx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rax
  void *v10; // rsi
  DnsZtRuleNode *v11; // rax
  DnsZtRuleNode *v13; // [rsp+28h] [rbp-30h] BYREF

  StringCopy_W = 0;
  v3 = 0;
  v13 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v6 = DnsZtRuleNode::CreateInstance(&v13);
    if ( v6 < 0 )
      goto LABEL_16;
    v7 = (void *)*((_QWORD *)this + 2);
    if ( v7 )
    {
      StringCopy_W = (void *)Dns_CreateStringCopy_W(v7);
      if ( !StringCopy_W )
      {
LABEL_5:
        v6 = -2147024882;
        goto LABEL_16;
      }
      v6 = 0;
    }
    v8 = (void *)*((_QWORD *)this + 3);
    if ( v8 )
    {
      v3 = (void *)Dns_CreateStringCopy_W(v8);
      if ( !v3 )
        goto LABEL_5;
      v6 = 0;
    }
    if ( *((_DWORD *)this + 10) )
    {
      v9 = (void *)Dns_Allocate(32LL * *((unsigned int *)this + 10));
      v10 = v9;
      if ( !v9 )
        goto LABEL_5;
      memcpy_0(v9, *((const void **)this + 4), 32LL * *((unsigned int *)this + 10));
      v6 = 0;
    }
    else
    {
      v10 = 0;
    }
    v11 = v13;
    *((_DWORD *)v13 + 1) = *((_DWORD *)this + 1);
    *((_QWORD *)v11 + 1) = *((_QWORD *)this + 1);
    *((_QWORD *)v11 + 2) = StringCopy_W;
    StringCopy_W = 0;
    *((_QWORD *)v11 + 3) = v3;
    v3 = 0;
    *((_QWORD *)v11 + 4) = v10;
    *((_DWORD *)v11 + 10) = *((_DWORD *)this + 10);
    *a2 = v11;
    v13 = 0;
  }
  else
  {
    v6 = -2147024809;
  }
LABEL_16:
  Dns_Free(StringCopy_W);
  Dns_Free(v3);
  Dns_Free(0);
  if ( v13 )
    DnsZtRuleNode::Release(v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800126d8  mov     [rsp+arg_10], rbx
0x1800126dd  push    rbp
0x1800126de  push    rsi
0x1800126df  push    rdi
0x1800126e0  push    r14
0x1800126e2  push    r15
0x1800126e4  sub     rsp, 30h
0x1800126e8  xor     ebp, ebp
0x1800126ea  mov     [rsp+58h+var_34], 0
0x1800126f2  xor     r14d, r14d
0x1800126f5  mov     [rsp+58h+var_30], 0
0x1800126fe  mov     r15, rdx
0x180012701  mov     rdi, rcx
0x180012704  test    rdx, rdx
0x180012707  jz      loc_1800127EB
0x18001270d  lea     rcx, [rsp+58h+var_30]; struct DnsZtRuleNode **
0x180012712  mov     [rdx], rbp
0x180012715  call    ?CreateInstance@DnsZtRuleNode@@SAJPEAPEAV1@@Z; DnsZtRuleNode::CreateInstance(DnsZtRuleNode * *)
0x18001271a  mov     ebx, eax
0x18001271c  test    eax, eax
0x18001271e  jns     short loc_18001272D
0x180012720  mov     [rsp+58h+var_34], 79h ; 'y'
0x180012728  jmp     loc_1800127F8
0x18001272d  mov     rcx, [rdi+10h]; Src
0x180012731  test    rcx, rcx
0x180012734  jz      short loc_180012757
0x180012736  call    Dns_CreateStringCopy_W
0x18001273b  mov     rbp, rax
0x18001273e  test    rax, rax
0x180012741  jnz     short loc_180012755
0x180012743  mov     [rsp+58h+var_34], 7Eh ; '~'
0x18001274b  mov     ebx, 8007000Eh
0x180012750  jmp     loc_1800127F8
0x180012755  xor     ebx, ebx
0x180012757  mov     rcx, [rdi+18h]; Src
0x18001275b  test    rcx, rcx
0x18001275e  jz      short loc_180012779
0x180012760  call    Dns_CreateStringCopy_W
0x180012765  mov     r14, rax
0x180012768  test    rax, rax
0x18001276b  jnz     short loc_180012777
0x18001276d  mov     [rsp+58h+var_34], 84h
0x180012775  jmp     short loc_18001274B
0x180012777  xor     ebx, ebx
0x180012779  cmp     dword ptr [rdi+28h], 0
0x18001277d  jz      short loc_1800127B5
0x18001277f  mov     ecx, [rdi+28h]
0x180012782  shl     rcx, 5
0x180012786  call    Dns_Allocate
0x18001278b  mov     rsi, rax
0x18001278e  test    rax, rax
0x180012791  jnz     short loc_18001279D
0x180012793  mov     [rsp+58h+var_34], 8Ah
0x18001279b  jmp     short loc_18001274B
0x18001279d  mov     r8d, [rdi+28h]
0x1800127a1  mov     rcx, rax; void *
0x1800127a4  mov     rdx, [rdi+20h]; Src
0x1800127a8  shl     r8, 5; Size
0x1800127ac  call    memcpy_0
0x1800127b1  xor     ebx, ebx
0x1800127b3  jmp     short loc_1800127B7
0x1800127b5  xor     esi, esi
0x1800127b7  mov     rax, [rsp+58h+var_30]
0x1800127bc  mov     ecx, [rdi+4]
0x1800127bf  mov     [rax+4], ecx
0x1800127c2  mov     rcx, [rdi+8]
0x1800127c6  mov     [rax+8], rcx
0x1800127ca  mov     [rax+10h], rbp
0x1800127ce  xor     ebp, ebp
0x1800127d0  mov     [rax+18h], r14
0x1800127d4  xor     r14d, r14d
0x1800127d7  mov     [rax+20h], rsi
0x1800127db  mov     ecx, [rdi+28h]
0x1800127de  mov     [rax+28h], ecx
0x1800127e1  mov     [r15], rax
0x1800127e4  mov     [rsp+58h+var_30], rbp
0x1800127e9  jmp     short loc_1800127F8
0x1800127eb  mov     [rsp+58h+var_34], 77h ; 'w'
0x1800127f3  mov     ebx, 80070057h
0x1800127f8  mov     rcx, rbp; lpMem
0x1800127fb  call    Dns_Free
0x180012800  mov     rcx, r14; lpMem
0x180012803  call    Dns_Free
0x180012808  xor     ecx, ecx; lpMem
0x18001280a  call    Dns_Free
0x18001280f  mov     rcx, [rsp+58h+var_30]; this
0x180012814  test    rcx, rcx
0x180012817  jz      short loc_18001281E
0x180012819  call    ?Release@DnsZtRuleNode@@QEAAKXZ; DnsZtRuleNode::Release(void)
0x18001281e  mov     eax, ebx
0x180012820  mov     rbx, [rsp+58h+arg_10]
0x180012825  add     rsp, 30h
0x180012829  pop     r15
0x18001282b  pop     r14
0x18001282d  pop     rdi
0x18001282e  pop     rsi
0x18001282f  pop     rbp
0x180012830  retn
```
