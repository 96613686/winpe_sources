# VfsCreateScb

- ea: `0x14000d3b4`
- end: `0x14000d611`
- name: `VfsCreateScb`
- size: `605`
- prototype: `__int64 __fastcall(__int64, void *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000db50`
- `0x14000dfe8`

## callees

- `0x14000d3b4`
- `0x140014000`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000d5d7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001538f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000d5d7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001538f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000d42d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000d42d`
- `ntoskrnl!KeInitializeEvent` at `0x14000d466`
- `ntoskrnl!KeInitializeEvent` at `0x14000d466`
- `ntoskrnl!RtlCopySid` at `0x14000d4bd`
- `ntoskrnl!RtlCopySid` at `0x14000d4bd`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000d476`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000d476`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000d5c1`
- `ntoskrnl!ExDeleteResourceLite` at `0x140015378`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000d5c1`
- `ntoskrnl!ExDeleteResourceLite` at `0x140015378`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000d5f2`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400153ab`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000d5f2`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400153ab`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000d3ef`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000d3ef`
- `FLTMGR!FltReferenceContext` at `0x14000d4fa`
- `FLTMGR!FltReferenceContext` at `0x14000d4fa`
- `FLTMGR!FltReleaseContext` at `0x14000d5a8`
- `FLTMGR!FltReleaseContext` at `0x14001535c`
- `FLTMGR!FltReleaseContext` at `0x14000d5a8`
- `FLTMGR!FltReleaseContext` at `0x14001535c`

## pseudocode

```c
__int64 __fastcall VfsCreateScb(__int64 a1, void *a2, __int64 a3, _QWORD *a4)
{
  char *v8; // rsi
  char *v9; // rax
  char *v10; // rbx
  NTSTATUS v11; // edi
  char *v12; // rax
  _OWORD *v13; // rcx
  volatile signed __int32 *v14; // rax
  _OWORD *v15; // rax
  void *v16; // rcx
  __int64 v17; // rcx

  v8 = 0;
  v9 = (char *)ExAllocateFromPagedLookasideList(&stru_14001F680);
  v10 = v9;
  if ( v9 && (memset(v9, 0, 0x198u), v12 = (char *)ExAllocateFromNPagedLookasideList(&stru_14001F700), (v8 = v12) != 0) )
  {
    memset(v12, 0, 0xA0u);
    *(_DWORD *)v8 = 1;
    KeInitializeEvent((PRKEVENT)v8 + 1, SynchronizationEvent, 0);
    v11 = ExInitializeResourceLite((PERESOURCE)(v8 + 56));
    if ( v11 >= 0 )
    {
      *((_QWORD *)v10 + 15) = v8;
      v13 = *(_OWORD **)(a3 + 16);
      *(_OWORD *)(v10 + 220) = *v13;
      *(_OWORD *)(v10 + 236) = v13[1];
      RtlCopySid(0x44u, v10 + 152, *(PSID *)(a3 + 8));
      *((_QWORD *)v10 + 17) = *(_QWORD *)(a3 + 24);
      v14 = *(volatile signed __int32 **)(a3 + 32);
      if ( v14 )
      {
        *((_QWORD *)v10 + 18) = v14;
        _InterlockedIncrement(v14);
      }
      *((_DWORD *)v10 + 68) = *(_DWORD *)a3;
      *((_QWORD *)v10 + 16) = a2;
      FltReferenceContext(a2);
      *((_QWORD *)v10 + 33) = v10 + 256;
      *((_QWORD *)v10 + 32) = v10 + 256;
      *(_QWORD *)(v10 + 276) = 1;
      v15 = *(_OWORD **)(a1 + 24);
      *(_OWORD *)v10 = *v15;
      *((_OWORD *)v10 + 1) = v15[1];
      *((_OWORD *)v10 + 2) = v15[2];
      *(_DWORD *)v10 = 26744454;
      v10[4] |= 0x40u;
      v10[6] |= 2u;
      v10[7] = v10[7] & 0xF | 0x50;
      *((_QWORD *)v10 + 8) = v10 + 56;
      *((_QWORD *)v10 + 7) = v10 + 56;
      *((_QWORD *)v10 + 6) = v8;
      *((_QWORD *)v10 + 9) = 0;
      *((_QWORD *)v10 + 10) = 0;
      *((_QWORD *)v10 + 11) = 0;
      *((_QWORD *)v10 + 12) = 0;
      *((_DWORD *)v10 + 26) = 0;
      *((_QWORD *)v10 + 14) = 0;
      *a4 = v10;
    }
  }
  else
  {
    v11 = -1073741670;
  }
  if ( v11 < 0 )
  {
    if ( v8 )
    {
      v16 = (void *)*((_QWORD *)v10 + 16);
      if ( v16 )
        FltReleaseContext(v16);
      v17 = *((_QWORD *)v10 + 15);
      if ( v17 )
        ExDeleteResourceLite((PERESOURCE)(v17 + 56));
      ExFreeToNPagedLookasideList(&stru_14001F700, v8);
    }
    if ( v10 )
      ExFreeToPagedLookasideList(&stru_14001F680, v10);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000d3b4  push    rbx
0x14000d3b6  push    rsi
0x14000d3b7  push    rdi
0x14000d3b8  push    r12
0x14000d3ba  push    r13
0x14000d3bc  push    r14
0x14000d3be  push    r15
0x14000d3c0  sub     rsp, 40h
0x14000d3c4  mov     r12, r9
0x14000d3c7  mov     r14, r8
0x14000d3ca  mov     r15, rdx
0x14000d3cd  mov     r13, rcx
0x14000d3d0  mov     [rsp+78h+var_58], 0
0x14000d3d8  mov     [rsp+78h+var_50], 0
0x14000d3e1  xor     esi, esi
0x14000d3e3  mov     [rsp+78h+var_48], rsi
0x14000d3e8  lea     rcx, stru_14001F680; Lookaside
0x14000d3ef  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14000d3f6  nop     dword ptr [rax+rax+00h]
0x14000d3fb  mov     rbx, rax
0x14000d3fe  mov     [rsp+78h+var_50], rax
0x14000d403  test    rax, rax
0x14000d406  jnz     short loc_14000D416
0x14000d408  mov     edi, 0C000009Ah
0x14000d40d  mov     [rsp+78h+var_58], edi
0x14000d411  jmp     loc_14000D593
0x14000d416  xor     edx, edx; Val
0x14000d418  mov     r8d, 198h; Size
0x14000d41e  mov     rcx, rbx; void *
0x14000d421  call    memset
0x14000d426  lea     rcx, stru_14001F700; Lookaside
0x14000d42d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000d434  nop     dword ptr [rax+rax+00h]
0x14000d439  mov     rsi, rax
0x14000d43c  mov     [rsp+78h+var_48], rax
0x14000d441  test    rax, rax
0x14000d444  jz      short loc_14000D408
0x14000d446  xor     edx, edx; Val
0x14000d448  mov     r8d, 0A0h; Size
0x14000d44e  mov     rcx, rax; void *
0x14000d451  call    memset
0x14000d456  mov     eax, 1
0x14000d45b  mov     [rsi], eax
0x14000d45d  lea     rcx, [rsi+18h]; Event
0x14000d461  xor     r8d, r8d; State
0x14000d464  mov     edx, eax; Type
0x14000d466  call    cs:__imp_KeInitializeEvent
0x14000d46d  nop     dword ptr [rax+rax+00h]
0x14000d472  lea     rcx, [rsi+38h]; Resource
0x14000d476  call    cs:__imp_ExInitializeResourceLite
0x14000d47d  nop     dword ptr [rax+rax+00h]
0x14000d482  mov     edi, eax
0x14000d484  mov     [rsp+78h+var_58], eax
0x14000d488  test    eax, eax
0x14000d48a  js      loc_14000D593
0x14000d490  mov     [rbx+78h], rsi
0x14000d494  mov     rcx, [r14+10h]
0x14000d498  movups  xmm0, xmmword ptr [rcx]
0x14000d49b  movups  xmmword ptr [rbx+0DCh], xmm0
0x14000d4a2  movups  xmm1, xmmword ptr [rcx+10h]
0x14000d4a6  movups  xmmword ptr [rbx+0ECh], xmm1
0x14000d4ad  lea     rdx, [rbx+98h]; DestinationSid
0x14000d4b4  mov     r8, [r14+8]; SourceSid
0x14000d4b8  mov     ecx, 44h ; 'D'; DestinationSidLength
0x14000d4bd  call    cs:__imp_RtlCopySid
0x14000d4c4  nop     dword ptr [rax+rax+00h]
0x14000d4c9  mov     rax, [r14+18h]
0x14000d4cd  mov     [rbx+88h], rax
0x14000d4d4  mov     rax, [r14+20h]
0x14000d4d8  test    rax, rax
0x14000d4db  jz      short loc_14000D4E7
0x14000d4dd  mov     [rbx+90h], rax
0x14000d4e4  lock inc dword ptr [rax]
0x14000d4e7  mov     eax, [r14]
0x14000d4ea  mov     [rbx+110h], eax
0x14000d4f0  mov     [rbx+80h], r15
0x14000d4f7  mov     rcx, r15; Context
0x14000d4fa  call    cs:__imp_FltReferenceContext
0x14000d501  nop     dword ptr [rax+rax+00h]
0x14000d506  lea     rax, [rbx+100h]
0x14000d50d  mov     [rax+8], rax
0x14000d511  mov     [rax], rax
0x14000d514  mov     qword ptr [rbx+114h], 1
0x14000d51f  mov     rax, [r13+18h]
0x14000d523  movups  xmm0, xmmword ptr [rax]
0x14000d526  movups  xmmword ptr [rbx], xmm0
0x14000d529  movups  xmm1, xmmword ptr [rax+10h]
0x14000d52d  movups  xmmword ptr [rbx+10h], xmm1
0x14000d531  movups  xmm0, xmmword ptr [rax+20h]
0x14000d535  movups  xmmword ptr [rbx+20h], xmm0
0x14000d539  mov     dword ptr [rbx], 1981686h
0x14000d53f  or      byte ptr [rbx+4], 40h
0x14000d543  or      byte ptr [rbx+6], 2
0x14000d547  mov     al, [rbx+7]
0x14000d54a  and     al, 0Fh
0x14000d54c  or      al, 50h
0x14000d54e  mov     [rbx+7], al
0x14000d551  lea     rax, [rbx+38h]
0x14000d555  mov     [rax+8], rax
0x14000d559  mov     [rax], rax
0x14000d55c  mov     [rbx+30h], rsi
0x14000d560  mov     qword ptr [rbx+48h], 0
0x14000d568  mov     qword ptr [rbx+50h], 0
0x14000d570  mov     qword ptr [rbx+58h], 0
0x14000d578  mov     qword ptr [rbx+60h], 0
0x14000d580  mov     dword ptr [rbx+68h], 0
0x14000d587  mov     qword ptr [rbx+70h], 0
0x14000d58f  mov     [r12], rbx
0x14000d593  test    edi, edi
0x14000d595  jns     short loc_14000D5FE
0x14000d597  test    rsi, rsi
0x14000d59a  jz      short loc_14000D5E3
0x14000d59c  mov     rcx, [rbx+80h]; Context
0x14000d5a3  test    rcx, rcx
0x14000d5a6  jz      short loc_14000D5B4
0x14000d5a8  call    cs:__imp_FltReleaseContext
0x14000d5af  nop     dword ptr [rax+rax+00h]
0x14000d5b4  mov     rcx, [rbx+78h]
0x14000d5b8  test    rcx, rcx
0x14000d5bb  jz      short loc_14000D5CD
0x14000d5bd  add     rcx, 38h ; '8'; Resource
0x14000d5c1  call    cs:__imp_ExDeleteResourceLite
0x14000d5c8  nop     dword ptr [rax+rax+00h]
0x14000d5cd  mov     rdx, rsi; Entry
0x14000d5d0  lea     rcx, stru_14001F700; Lookaside
0x14000d5d7  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000d5de  nop     dword ptr [rax+rax+00h]
0x14000d5e3  test    rbx, rbx
0x14000d5e6  jz      short loc_14000D5FE
0x14000d5e8  mov     rdx, rbx; Entry
0x14000d5eb  lea     rcx, stru_14001F680; Lookaside
0x14000d5f2  call    cs:__imp_ExFreeToPagedLookasideList
0x14000d5f9  nop     dword ptr [rax+rax+00h]
0x14000d5fe  mov     eax, edi
0x14000d600  add     rsp, 40h
0x14000d604  pop     r15
0x14000d606  pop     r14
0x14000d608  pop     r13
0x14000d60a  pop     r12
0x14000d60c  pop     rdi
0x14000d60d  pop     rsi
0x14000d60e  pop     rbx
0x14000d60f  retn
0x14001532d  push    rbx
0x14001532f  push    rbp
0x140015330  push    rdi
0x140015331  sub     rsp, 20h
0x140015335  mov     rbp, rdx
0x140015338  cmp     dword ptr [rbp+20h], 0
0x14001533c  jge     short loc_1400153B8
0x14001533e  mov     rdi, [rbp+30h]
0x140015342  mov     rbx, [rbp+28h]
0x140015346  test    rdi, rdi
0x140015349  jz      short loc_14001539C
0x14001534b  cmp     qword ptr [rbx+80h], 0
0x140015353  jz      short loc_140015369
0x140015355  mov     rcx, [rbx+80h]; Context
0x14001535c  call    cs:__imp_FltReleaseContext
0x140015363  nop     dword ptr [rax+rax+00h]
0x140015368  nop
0x140015369  cmp     qword ptr [rbx+78h], 0
0x14001536e  jz      short loc_140015385
0x140015370  mov     rcx, [rbx+78h]
0x140015374  add     rcx, 38h ; '8'; Resource
0x140015378  call    cs:__imp_ExDeleteResourceLite
0x14001537f  nop     dword ptr [rax+rax+00h]
0x140015384  nop
0x140015385  mov     rdx, rdi; Entry
0x140015388  lea     rcx, stru_14001F700; Lookaside
0x14001538f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140015396  nop     dword ptr [rax+rax+00h]
0x14001539b  nop
0x14001539c  test    rbx, rbx
0x14001539f  jz      short loc_1400153B8
0x1400153a1  mov     rdx, rbx; Entry
0x1400153a4  lea     rcx, stru_14001F680; Lookaside
0x1400153ab  call    cs:__imp_ExFreeToPagedLookasideList
0x1400153b2  nop     dword ptr [rax+rax+00h]
0x1400153b7  nop
0x1400153b8  add     rsp, 20h
0x1400153bc  pop     rdi
0x1400153bd  pop     rbp
0x1400153be  pop     rbx
0x1400153bf  retn
```
