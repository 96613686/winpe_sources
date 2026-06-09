# KerbIumClearKey::KerbIumClearKey(_KERB_ENCRYPTION_KEY *,KerbIumClearKey::AllowUnencryptedInput const &)

- ea: `0x140014370`
- end: `0x140014450`
- name: `??0KerbIumClearKey@@QEAA@PEAU_KERB_ENCRYPTION_KEY@@AEBUAllowUnencryptedInput@0@@Z`
- size: `224`
- prototype: `KerbIumClearKey *__fastcall(KerbIumClearKey *__hidden this, struct _KERB_ENCRYPTION_KEY *, const struct KerbIumClearKey::AllowUnencryptedInput *)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x140015410`
- `0x140015740`
- `0x1400158c0`
- `0x140016310`
- `0x140016ac0`
- `0x140017450`
- `0x1400186e0`
- `0x140019890`
- `0x140019dd0`

## callees

- `0x140003ad6`
- `0x140014370`
- `0x140014524`

## import_xrefs

- `KerbClientShared!KerbClientAlloc` at `0x140014402`
- `KerbClientShared!KerbClientAlloc` at `0x140014402`

## pseudocode

```c
KerbIumClearKey *__fastcall KerbIumClearKey::KerbIumClearKey(
        KerbIumClearKey *this,
        struct _KERB_ENCRYPTION_KEY *a2,
        const struct KerbIumClearKey::AllowUnencryptedInput *a3)
{
  int v5; // ecx
  void *v6; // rax

  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  if ( a2 )
  {
    if ( *((_DWORD *)a2 + 2) == 3 )
      KerbIumClearKey::Decrypt(this, a2);
    else
      *((_DWORD *)this + 10) = -1073741811;
    v5 = *((_DWORD *)this + 10);
    if ( (int)(v5 + 0x80000000) < 0 || v5 == -1073741801 )
    {
      *((_DWORD *)this + 12) = v5 >= 0;
    }
    else
    {
      *(_OWORD *)this = *(_OWORD *)a2;
      *((_OWORD *)this + 1) = *((_OWORD *)a2 + 1);
      *((_QWORD *)this + 4) = *((_QWORD *)a2 + 4);
      *((_DWORD *)this + 2) = 1;
      *((_DWORD *)this + 10) = 0;
      if ( *((_DWORD *)a2 + 4) )
      {
        v6 = KerbClientAlloc(*((unsigned int *)this + 4));
        *((_QWORD *)this + 3) = v6;
        if ( v6 )
        {
          memcpy_0(v6, *((const void **)a2 + 3), *((unsigned int *)this + 4));
        }
        else
        {
          *((_DWORD *)this + 10) = -1073741801;
          *(_OWORD *)this = 0;
          *((_OWORD *)this + 1) = 0;
          *((_QWORD *)this + 4) = 0;
        }
      }
    }
  }
  else
  {
    *((_DWORD *)this + 10) = -1073741811;
  }
  return this;
}

```

## disassembly

```asm
0x140014370  mov     [rsp+arg_0], rbx
0x140014375  push    rdi
0x140014376  sub     rsp, 20h
0x14001437a  xor     eax, eax
0x14001437c  xorps   xmm0, xmm0
0x14001437f  mov     rdi, rdx
0x140014382  mov     rbx, rcx
0x140014385  movups  xmmword ptr [rcx], xmm0
0x140014388  movups  xmmword ptr [rcx+10h], xmm0
0x14001438c  mov     [rcx+20h], rax
0x140014390  mov     [rcx+28h], rax
0x140014394  mov     [rcx+30h], eax
0x140014397  test    rdx, rdx
0x14001439a  jnz     short loc_1400143A8
0x14001439c  mov     dword ptr [rcx+28h], 0C000000Dh
0x1400143a3  jmp     loc_140014442
0x1400143a8  cmp     dword ptr [rdx+8], 3
0x1400143ac  jnz     short loc_1400143B5
0x1400143ae  call    ?Decrypt@KerbIumClearKey@@AEAAXPEAU_KERB_ENCRYPTION_KEY@@@Z; KerbIumClearKey::Decrypt(_KERB_ENCRYPTION_KEY *)
0x1400143b3  jmp     short loc_1400143BC
0x1400143b5  mov     dword ptr [rcx+28h], 0C000000Dh
0x1400143bc  mov     ecx, [rbx+28h]
0x1400143bf  mov     edx, 80000000h
0x1400143c4  lea     eax, [rcx+rdx]
0x1400143c7  test    edx, eax
0x1400143c9  jnz     short loc_14001443A
0x1400143cb  cmp     ecx, 0C0000017h
0x1400143d1  jz      short loc_14001443A
0x1400143d3  movups  xmm0, xmmword ptr [rdi]
0x1400143d6  movups  xmmword ptr [rbx], xmm0
0x1400143d9  movups  xmm1, xmmword ptr [rdi+10h]
0x1400143dd  movups  xmmword ptr [rbx+10h], xmm1
0x1400143e1  movsd   xmm0, qword ptr [rdi+20h]
0x1400143e6  movsd   qword ptr [rbx+20h], xmm0
0x1400143eb  mov     dword ptr [rbx+8], 1
0x1400143f2  mov     dword ptr [rbx+28h], 0
0x1400143f9  cmp     dword ptr [rdi+10h], 0
0x1400143fd  jbe     short loc_140014442
0x1400143ff  mov     ecx, [rbx+10h]
0x140014402  call    cs:__imp_?KerbClientAlloc@@YAPEAX_K@Z; KerbClientAlloc(unsigned __int64)
0x140014408  mov     [rbx+18h], rax
0x14001440c  test    rax, rax
0x14001440f  jnz     short loc_140014428
0x140014411  xorps   xmm0, xmm0
0x140014414  mov     dword ptr [rbx+28h], 0C0000017h
0x14001441b  movups  xmmword ptr [rbx], xmm0
0x14001441e  movups  xmmword ptr [rbx+10h], xmm0
0x140014422  mov     [rbx+20h], rax
0x140014426  jmp     short loc_140014442
0x140014428  mov     r8d, [rbx+10h]; Size
0x14001442c  mov     rcx, rax; void *
0x14001442f  mov     rdx, [rdi+18h]; Src
0x140014433  call    memcpy_0
0x140014438  jmp     short loc_140014442
0x14001443a  not     ecx
0x14001443c  shr     ecx, 1Fh
0x14001443f  mov     [rbx+30h], ecx
0x140014442  mov     rax, rbx
0x140014445  mov     rbx, [rsp+28h+arg_0]
0x14001444a  add     rsp, 20h
0x14001444e  pop     rdi
0x14001444f  retn
```
