# CRegistry::CRegistry(CRegistry const &)

- ea: `0x140011ab0`
- end: `0x140011bcc`
- name: `??0CRegistry@@QEAA@AEBV0@@Z`
- size: `284`
- prototype: `CRegistry *__fastcall(CRegistry *__hidden this, const struct CRegistry *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000fc80`
- `0x140011ab0`

## pseudocode

```c
CRegistry *__fastcall CRegistry::CRegistry(CRegistry *this, const struct CRegistry *a2)
{
  _OWORD *v4; // rcx
  __int64 v5; // rdx
  _OWORD *v6; // rax
  __int128 v7; // xmm1

  *(_QWORD *)this = *(_QWORD *)a2;
  *((_QWORD *)this + 1) = *((_QWORD *)a2 + 1);
  *((_QWORD *)this + 2) = *((_QWORD *)a2 + 2);
  CHString::CHString((CRegistry *)((char *)this + 24), (unsigned __int16 **)a2 + 3);
  v4 = (_OWORD *)((char *)this + 38);
  *((_DWORD *)this + 8) = *((_DWORD *)a2 + 8);
  v5 = 4;
  *((_BYTE *)this + 36) = *((_BYTE *)a2 + 36);
  v6 = (_OWORD *)((char *)a2 + 38);
  do
  {
    *v4 = *v6;
    v4[1] = v6[1];
    v4[2] = v6[2];
    v4[3] = v6[3];
    v4[4] = v6[4];
    v4[5] = v6[5];
    v4[6] = v6[6];
    v7 = v6[7];
    v6 += 8;
    v4[7] = v7;
    v4 += 8;
    --v5;
  }
  while ( v5 );
  *(_QWORD *)v4 = *(_QWORD *)v6;
  *((_DWORD *)this + 140) = *((_DWORD *)a2 + 140);
  *((_DWORD *)this + 141) = *((_DWORD *)a2 + 141);
  *((_DWORD *)this + 142) = *((_DWORD *)a2 + 142);
  *((_DWORD *)this + 143) = *((_DWORD *)a2 + 143);
  *((_DWORD *)this + 144) = *((_DWORD *)a2 + 144);
  *((_DWORD *)this + 145) = *((_DWORD *)a2 + 145);
  *((_DWORD *)this + 146) = *((_DWORD *)a2 + 146);
  *((_DWORD *)this + 147) = *((_DWORD *)a2 + 147);
  *((_QWORD *)this + 74) = *((_QWORD *)a2 + 74);
  return this;
}

```

## disassembly

```asm
0x140011ab0  mov     [rsp+arg_0], rbx
0x140011ab5  push    rdi
0x140011ab6  sub     rsp, 20h
0x140011aba  mov     rax, [rdx]
0x140011abd  mov     rdi, rdx
0x140011ac0  mov     [rcx], rax
0x140011ac3  mov     rbx, rcx
0x140011ac6  mov     rax, [rdx+8]
0x140011aca  mov     [rcx+8], rax
0x140011ace  mov     rax, [rdx+10h]
0x140011ad2  add     rdx, 18h; struct CHString *
0x140011ad6  mov     [rcx+10h], rax
0x140011ada  add     rcx, 18h; this
0x140011ade  call    ??0CHString@@QEAA@AEBV0@@Z; CHString::CHString(CHString const &)
0x140011ae3  mov     eax, [rdi+20h]
0x140011ae6  lea     rcx, [rbx+26h]
0x140011aea  mov     [rbx+20h], eax
0x140011aed  mov     edx, 4
0x140011af2  mov     al, [rdi+24h]
0x140011af5  mov     [rbx+24h], al
0x140011af8  lea     rax, [rdi+26h]
0x140011afc  lea     r8d, [rdx+7Ch]
0x140011b00  movups  xmm0, xmmword ptr [rax]
0x140011b03  movups  xmmword ptr [rcx], xmm0
0x140011b06  movups  xmm1, xmmword ptr [rax+10h]
0x140011b0a  movups  xmmword ptr [rcx+10h], xmm1
0x140011b0e  movups  xmm0, xmmword ptr [rax+20h]
0x140011b12  movups  xmmword ptr [rcx+20h], xmm0
0x140011b16  movups  xmm1, xmmword ptr [rax+30h]
0x140011b1a  movups  xmmword ptr [rcx+30h], xmm1
0x140011b1e  movups  xmm0, xmmword ptr [rax+40h]
0x140011b22  movups  xmmword ptr [rcx+40h], xmm0
0x140011b26  movups  xmm1, xmmword ptr [rax+50h]
0x140011b2a  movups  xmmword ptr [rcx+50h], xmm1
0x140011b2e  movups  xmm0, xmmword ptr [rax+60h]
0x140011b32  movups  xmmword ptr [rcx+60h], xmm0
0x140011b36  movups  xmm1, xmmword ptr [rax+70h]
0x140011b3a  add     rax, r8
0x140011b3d  movups  xmmword ptr [rcx+70h], xmm1
0x140011b41  add     rcx, r8
0x140011b44  sub     rdx, 1
0x140011b48  jnz     short loc_140011B00
0x140011b4a  mov     rax, [rax]
0x140011b4d  mov     [rcx], rax
0x140011b50  mov     eax, [rdi+230h]
0x140011b56  mov     [rbx+230h], eax
0x140011b5c  mov     eax, [rdi+234h]
0x140011b62  mov     [rbx+234h], eax
0x140011b68  mov     eax, [rdi+238h]
0x140011b6e  mov     [rbx+238h], eax
0x140011b74  mov     eax, [rdi+23Ch]
0x140011b7a  mov     [rbx+23Ch], eax
0x140011b80  mov     eax, [rdi+240h]
0x140011b86  mov     [rbx+240h], eax
0x140011b8c  mov     eax, [rdi+244h]
0x140011b92  mov     [rbx+244h], eax
0x140011b98  mov     eax, [rdi+248h]
0x140011b9e  mov     [rbx+248h], eax
0x140011ba4  mov     eax, [rdi+24Ch]
0x140011baa  mov     [rbx+24Ch], eax
0x140011bb0  mov     rax, [rdi+250h]
0x140011bb7  mov     [rbx+250h], rax
0x140011bbe  mov     rax, rbx
0x140011bc1  mov     rbx, [rsp+28h+arg_0]
0x140011bc6  add     rsp, 20h
0x140011bca  pop     rdi
0x140011bcb  retn
```
