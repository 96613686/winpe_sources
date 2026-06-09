# DnsZtRuleNode::CreateInstance(ulong,unsigned __int64,ushort * const,ushort * const,_DNS_ZT_SUBNET const *,ulong,DnsZtRuleNode * *)

- ea: `0x180012838`
- end: `0x1800129e4`
- name: `?CreateInstance@DnsZtRuleNode@@SAJK_KQEAG1PEBU_DNS_ZT_SUBNET@@KPEAPEAV1@@Z`
- size: `428`
- prototype: `__int64 __fastcall(int, __int64, unsigned __int16 *const, unsigned __int16 *const, const struct _DNS_ZT_SUBNET *Src, unsigned int, struct DnsZtRuleNode **)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1800076b8`
- `0x1800111cc`
- `0x180011548`

## callees

- `0x180007674`
- `0x18000e3c8`
- `0x180012564`
- `0x1800125d4`
- `0x180012838`
- `0x1800129ec`
- `0x180013f19`

## pseudocode

```c
__int64 __fastcall DnsZtRuleNode::CreateInstance(
        int a1,
        __int64 a2,
        unsigned __int16 *const a3,
        unsigned __int16 *const a4,
        const struct _DNS_ZT_SUBNET *Src,
        unsigned int a6,
        struct DnsZtRuleNode **a7)
{
  void *StringCopy_W; // rbp
  void *v10; // rsi
  int v11; // ebx
  void *v12; // rbx
  void *v13; // rax
  DnsZtRuleNode *v14; // rax
  DnsZtRuleNode *v16; // [rsp+28h] [rbp-40h] BYREF

  StringCopy_W = 0;
  *a7 = 0;
  v10 = 0;
  v16 = 0;
  if ( a1 != 1 || a2 || !a3 || !a4 || (a6 != 0) != (Src != 0) )
  {
    v11 = -2147024809;
    goto LABEL_15;
  }
  v11 = DnsZtRuleNode::CreateInstance(&v16);
  if ( v11 >= 0 )
  {
    StringCopy_W = (void *)Dns_CreateStringCopy_W(a3);
    if ( StringCopy_W )
    {
      v10 = (void *)Dns_CreateStringCopy_W(a4);
      if ( v10 )
      {
        v12 = 0;
        if ( !a6 )
        {
LABEL_14:
          v14 = v16;
          *((_DWORD *)v16 + 1) = 1;
          *((_QWORD *)v14 + 1) = 0;
          *((_QWORD *)v14 + 2) = StringCopy_W;
          StringCopy_W = 0;
          *((_QWORD *)v14 + 3) = v10;
          v10 = 0;
          *((_QWORD *)v14 + 4) = v12;
          v11 = 0;
          *((_DWORD *)v14 + 10) = a6;
          *a7 = v14;
          v16 = 0;
          goto LABEL_15;
        }
        v13 = (void *)Dns_Allocate(32LL * a6);
        v12 = v13;
        if ( v13 )
        {
          memcpy_0(v13, Src, 32LL * a6);
          goto LABEL_14;
        }
      }
    }
    v11 = -2147024882;
  }
LABEL_15:
  Dns_Free(StringCopy_W);
  Dns_Free(v10);
  Dns_Free(0);
  if ( v16 )
    DnsZtRuleNode::Release(v16);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180012838  mov     [rsp+arg_0], rbx
0x18001283d  push    rbp
0x18001283e  push    rsi
0x18001283f  push    rdi
0x180012840  push    r12
0x180012842  push    r13
0x180012844  push    r14
0x180012846  push    r15
0x180012848  sub     rsp, 30h
0x18001284c  mov     r13, [rsp+68h+arg_30]
0x180012854  mov     rdi, r8
0x180012857  mov     r12, [rsp+68h+Src]
0x18001285f  xor     r8d, r8d
0x180012862  mov     r14d, [rsp+68h+arg_28]
0x18001286a  mov     r15, r9
0x18001286d  mov     [rsp+68h+var_44], r8d
0x180012872  mov     ebp, r8d
0x180012875  mov     [r13+0], r8
0x180012879  mov     esi, r8d
0x18001287c  mov     [rsp+68h+var_40], r8
0x180012881  cmp     ecx, 1
0x180012884  jz      short loc_180012898
0x180012886  mov     [rsp+68h+var_44], 37h ; '7'
0x18001288e  mov     ebx, 80070057h
0x180012893  jmp     loc_1800129A7
0x180012898  test    rdx, rdx
0x18001289b  jz      short loc_1800128A7
0x18001289d  mov     [rsp+68h+var_44], 38h ; '8'
0x1800128a5  jmp     short loc_18001288E
0x1800128a7  test    rdi, rdi
0x1800128aa  jnz     short loc_1800128B6
0x1800128ac  mov     [rsp+68h+var_44], 39h ; '9'
0x1800128b4  jmp     short loc_18001288E
0x1800128b6  test    r15, r15
0x1800128b9  jnz     short loc_1800128C5
0x1800128bb  mov     [rsp+68h+var_44], 3Ah ; ':'
0x1800128c3  jmp     short loc_18001288E
0x1800128c5  test    r14d, r14d
0x1800128c8  mov     ecx, r8d
0x1800128cb  mov     eax, r8d
0x1800128ce  setnz   cl
0x1800128d1  test    r12, r12
0x1800128d4  setnz   al
0x1800128d7  cmp     ecx, eax
0x1800128d9  jz      short loc_1800128E5
0x1800128db  mov     [rsp+68h+var_44], 3Bh ; ';'
0x1800128e3  jmp     short loc_18001288E
0x1800128e5  lea     rcx, [rsp+68h+var_40]; struct DnsZtRuleNode **
0x1800128ea  call    ?CreateInstance@DnsZtRuleNode@@SAJPEAPEAV1@@Z; DnsZtRuleNode::CreateInstance(DnsZtRuleNode * *)
0x1800128ef  mov     ebx, eax
0x1800128f1  test    eax, eax
0x1800128f3  jns     short loc_180012902
0x1800128f5  mov     [rsp+68h+var_44], 3Dh ; '='
0x1800128fd  jmp     loc_1800129A7
0x180012902  mov     rcx, rdi; Src
0x180012905  call    Dns_CreateStringCopy_W
0x18001290a  mov     rbp, rax
0x18001290d  test    rax, rax
0x180012910  jnz     short loc_180012924
0x180012912  mov     [rsp+68h+var_44], 40h ; '@'
0x18001291a  mov     ebx, 8007000Eh
0x18001291f  jmp     loc_1800129A7
0x180012924  mov     rcx, r15; Src
0x180012927  call    Dns_CreateStringCopy_W
0x18001292c  mov     rsi, rax
0x18001292f  test    rax, rax
0x180012932  jnz     short loc_18001293E
0x180012934  mov     [rsp+68h+var_44], 43h ; 'C'
0x18001293c  jmp     short loc_18001291A
0x18001293e  xor     ebx, ebx
0x180012940  test    r14d, r14d
0x180012943  jz      short loc_180012974
0x180012945  mov     rdi, r14
0x180012948  shl     rdi, 5
0x18001294c  mov     rcx, rdi
0x18001294f  call    Dns_Allocate
0x180012954  mov     rbx, rax
0x180012957  test    rax, rax
0x18001295a  jnz     short loc_180012966
0x18001295c  mov     [rsp+68h+var_44], 48h ; 'H'
0x180012964  jmp     short loc_18001291A
0x180012966  mov     r8, rdi; Size
0x180012969  mov     rdx, r12; Src
0x18001296c  mov     rcx, rax; void *
0x18001296f  call    memcpy_0
0x180012974  mov     rax, [rsp+68h+var_40]
0x180012979  mov     dword ptr [rax+4], 1
0x180012980  mov     qword ptr [rax+8], 0
0x180012988  mov     [rax+10h], rbp
0x18001298c  xor     ebp, ebp
0x18001298e  mov     [rax+18h], rsi
0x180012992  xor     esi, esi
0x180012994  mov     [rax+20h], rbx
0x180012998  xor     ebx, ebx
0x18001299a  mov     [rax+28h], r14d
0x18001299e  mov     [r13+0], rax
0x1800129a2  mov     [rsp+68h+var_40], rsi
0x1800129a7  mov     rcx, rbp; lpMem
0x1800129aa  call    Dns_Free
0x1800129af  mov     rcx, rsi; lpMem
0x1800129b2  call    Dns_Free
0x1800129b7  xor     ecx, ecx; lpMem
0x1800129b9  call    Dns_Free
0x1800129be  mov     rcx, [rsp+68h+var_40]; this
0x1800129c3  test    rcx, rcx
0x1800129c6  jz      short loc_1800129CD
0x1800129c8  call    ?Release@DnsZtRuleNode@@QEAAKXZ; DnsZtRuleNode::Release(void)
0x1800129cd  mov     eax, ebx
0x1800129cf  mov     rbx, [rsp+68h+arg_0]
0x1800129d4  add     rsp, 30h
0x1800129d8  pop     r15
0x1800129da  pop     r14
0x1800129dc  pop     r13
0x1800129de  pop     r12
0x1800129e0  pop     rdi
0x1800129e1  pop     rsi
0x1800129e2  pop     rbp
0x1800129e3  retn
```
