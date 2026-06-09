# AipSetServicePublisherInfoInCache

- ea: `0x140026fd0`
- end: `0x1400270eb`
- name: `AipSetServicePublisherInfoInCache`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140025560`

## callees

- `0x140006a20`
- `0x140006f40`
- `0x1400270f4`

## pseudocode

```c
__int64 __fastcall AipSetServicePublisherInfoInCache(__int64 a1, __int64 a2)
{
  _DWORD v5[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v6; // [rsp+38h] [rbp-C8h]
  _DWORD v7[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v8; // [rsp+48h] [rbp-B8h]
  _OWORD v9[3]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v10[3]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v11[13]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v12[13]; // [rsp+120h] [rbp+20h] BYREF

  v5[1] = 0;
  v7[1] = 0;
  v10[0] = 0;
  v10[1] = (unsigned __int64)v11;
  v10[2] = 0;
  LODWORD(v10[0]) = 48;
  memset(v11, 0, sizeof(v11));
  LODWORD(v11[0]) = 104;
  LODWORD(v11[2]) = 1;
  v11[1] = v5;
  v5[0] = *(_DWORD *)a2;
  v6 = *(_QWORD *)(a2 + 8);
  v9[0] = 0;
  LODWORD(v9[0]) = 48;
  v9[1] = (unsigned __int64)v12;
  v9[2] = 0;
  memset(v12, 0, sizeof(v12));
  LODWORD(v12[0]) = 104;
  v12[1] = v7;
  v7[0] = *(_DWORD *)(a2 + 16);
  v8 = *(_QWORD *)(a2 + 24);
  LODWORD(v12[2]) = 1;
  return AipSetTrustedPublisherNameInCache(a1, (__int64)v10, (_QWORD *)(a2 + 32), (__int64)v9, (_QWORD *)(a2 + 40));
}

```

## disassembly

```asm
0x140026fd0  push    rbp
0x140026fd2  push    rbx
0x140026fd3  push    rdi
0x140026fd4  push    r15
0x140026fd6  lea     rbp, [rsp-0A8h]
0x140026fde  sub     rsp, 1A8h
0x140026fe5  mov     rax, cs:__security_cookie
0x140026fec  xor     rax, rsp
0x140026fef  mov     [rbp+0C0h+var_30], rax
0x140026ff6  xor     eax, eax
0x140026ff8  xorps   xmm0, xmm0
0x140026ffb  mov     [rsp+1C0h+var_18C], eax
0x140026fff  mov     rbx, rdx
0x140027002  mov     [rsp+1C0h+var_17C], eax
0x140027006  mov     rdi, rcx
0x140027009  lea     rax, [rbp+0C0h+var_110]
0x14002700d  mov     r15d, 68h ; 'h'
0x140027013  movups  [rbp+0C0h+var_140], xmm0
0x140027017  mov     r8d, r15d; Size
0x14002701a  xor     edx, edx; Val
0x14002701c  movups  [rbp+0C0h+var_130], xmm0
0x140027020  lea     rcx, [rbp+0C0h+var_110]; void *
0x140027024  mov     qword ptr [rbp+0C0h+var_130], rax
0x140027028  movups  [rbp+0C0h+var_120], xmm0
0x14002702c  mov     dword ptr [rbp+0C0h+var_140], 30h ; '0'
0x140027033  call    memset
0x140027038  xorps   xmm0, xmm0
0x14002703b  mov     [rbp+0C0h+var_110], r15d
0x14002703f  lea     rax, [rsp+1C0h+var_190]
0x140027044  mov     [rbp+0C0h+var_100], 1
0x14002704b  mov     [rbp+0C0h+var_108], rax
0x14002704f  lea     rcx, [rbp+0C0h+var_A0]; void *
0x140027053  mov     eax, [rbx]
0x140027055  mov     r8d, r15d; Size
0x140027058  mov     [rsp+1C0h+var_190], eax
0x14002705c  xor     edx, edx; Val
0x14002705e  mov     rax, [rbx+8]
0x140027062  mov     [rsp+1C0h+var_188], rax
0x140027067  lea     rax, [rbp+0C0h+var_A0]
0x14002706b  movups  [rsp+1C0h+var_170], xmm0
0x140027070  mov     dword ptr [rsp+1C0h+var_170], 30h ; '0'
0x140027078  movups  [rsp+1C0h+var_160], xmm0
0x14002707d  mov     qword ptr [rsp+1C0h+var_160], rax
0x140027082  movups  [rsp+1C0h+var_150], xmm0
0x140027087  call    memset
0x14002708c  lea     rax, [rsp+1C0h+var_180]
0x140027091  mov     [rbp+0C0h+var_A0], r15d
0x140027095  mov     [rbp+0C0h+var_98], rax
0x140027099  lea     r8, [rbx+20h]
0x14002709d  mov     eax, [rbx+10h]
0x1400270a0  lea     r9, [rsp+1C0h+var_170]
0x1400270a5  mov     [rsp+1C0h+var_180], eax
0x1400270a9  lea     rdx, [rbp+0C0h+var_140]
0x1400270ad  mov     rax, [rbx+18h]
0x1400270b1  mov     rcx, rdi
0x1400270b4  mov     [rsp+1C0h+var_178], rax
0x1400270b9  lea     rax, [rbx+28h]
0x1400270bd  mov     [rsp+1C0h+var_1A0], rax
0x1400270c2  mov     [rbp+0C0h+var_90], 1
0x1400270c9  call    AipSetTrustedPublisherNameInCache
0x1400270ce  mov     rcx, [rbp+0C0h+var_30]
0x1400270d5  xor     rcx, rsp; StackCookie
0x1400270d8  call    __security_check_cookie
0x1400270dd  add     rsp, 1A8h
0x1400270e4  pop     r15
0x1400270e6  pop     rdi
0x1400270e7  pop     rbx
0x1400270e8  pop     rbp
0x1400270e9  retn
```
