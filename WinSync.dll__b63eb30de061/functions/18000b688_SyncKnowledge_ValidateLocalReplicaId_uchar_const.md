# SyncKnowledge::ValidateLocalReplicaId(uchar const *)

- ea: `0x18000b688`
- end: `0x18000b9f0`
- name: `?ValidateLocalReplicaId@SyncKnowledge@@AEAAJPEBE@Z`
- size: `872`
- prototype: `__int64 __fastcall(SyncKnowledge *__hidden this, const unsigned __int8 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bb40`
- `0x18000bfa0`

## callees

- `0x18000b5f0`
- `0x18000b688`
- `0x18000b9f8`
- `0x18000c270`
- `0x18000f810`
- `0x18001a038`
- `0x18001ae20`
- `0x180094010`

## string_xrefs

- `0x18000b98f`: `KnowledgeServices::ValidateIdBytes`
- `0x18000b9c1`: `KnowledgeServices::ValidateIdBytes`

## pseudocode

```c
__int64 __fastcall SyncKnowledge::ValidateLocalReplicaId(SyncKnowledge *this, unsigned __int8 *a2)
{
  PVOID *v4; // rbx
  _WORD *v5; // rsi
  unsigned int v6; // edi
  unsigned int v7; // r14d
  unsigned __int8 *v8; // r15
  int v9; // r14d
  unsigned int v10; // r15d
  unsigned __int8 *v11; // r14
  int v12; // r15d
  unsigned __int8 *v13; // r12
  __int16 v14; // ax
  int v15; // esi
  unsigned int v16; // esi
  __int64 v18; // rdx
  _BYTE v19[4]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v20; // [rsp+34h] [rbp-1Ch]
  const unsigned __int8 *v21; // [rsp+38h] [rbp-18h]
  _BYTE v22[4]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v23; // [rsp+44h] [rbp-Ch]
  const unsigned __int8 *v24; // [rsp+48h] [rbp-8h]
  int v26; // [rsp+A0h] [rbp+50h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids,
        "SyncKnowledge::ValidateLocalReplicaId");
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    {
      WPP_SF_s(v4[2], 10, WPP_e65626ae806d36e8966776faf765a664_Traceguids, "KnowledgeServices::ValidateIdBytes");
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v5 = (_WORD *)((char *)this + 60);
  if ( !a2 )
  {
    v6 = -2147467261;
    goto LABEL_13;
  }
  if ( *((_DWORD *)this + 14) )
  {
    if ( *v5 <= 2u || *(_WORD *)a2 <= 2u || *(_WORD *)a2 > *v5 )
      goto LABEL_8;
LABEL_12:
    v6 = 0;
    goto LABEL_13;
  }
  if ( *v5 )
    goto LABEL_12;
LABEL_8:
  v6 = -2147217408;
LABEL_13:
  v7 = 0;
  v8 = 0;
  v20 = 0;
  if ( !v6 )
  {
    v8 = a2;
    v9 = *((_DWORD *)this + 14);
    LOWORD(v20) = *v5;
    v7 = v20 & 0xFFFEFFFF | ((v9 & 1 | 2) << 16);
    v21 = a2;
    v20 = v7;
    if ( (unsigned int)SyncId::IsMaxId((SyncId *)v19) )
      v6 = -2147024809;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
  {
    WPP_SF_sD(
      (unsigned int)v4[2],
      11,
      (unsigned int)WPP_e65626ae806d36e8966776faf765a664_Traceguids,
      (unsigned int)"KnowledgeServices::ValidateIdBytes",
      v6);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (v7 & 0x20000) == 0 && v8 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
      SeFree(v8);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v6 )
  {
    v6 = SyncKnowledge::EnsureIdBuffer(this);
    if ( !v6 )
    {
      v18 = *((_QWORD *)this + 91);
      v26 = *((unsigned __int16 *)this + 30);
      v6 = (*(__int64 (__fastcall **)(SyncKnowledge *, __int64, int *))(*(_QWORD *)this + 24LL))(this, v18, &v26);
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = 0;
  v11 = 0;
  v20 = 0;
  v21 = 0;
  if ( !v6 )
  {
    v11 = (unsigned __int8 *)*((_QWORD *)this + 91);
    v12 = *((_DWORD *)this + 14) & 1;
    LOWORD(v20) = *v5;
    v10 = v20 & 0xFFFEFFFF | ((v12 | 2) << 16);
    v21 = v11;
    v20 = v10;
  }
  v13 = 0;
  v23 = 0;
  if ( v6 )
  {
    v16 = 0;
  }
  else
  {
    v14 = *v5;
    v13 = a2;
    v15 = *((_DWORD *)this + 14) & 1;
    LOWORD(v23) = v14;
    v16 = v23 & 0xFFFEFFFF | ((v15 | 2) << 16);
    v24 = a2;
    v23 = v16;
    if ( (unsigned int)SyncId::Compare((const struct SyncId *)v19, (const struct SyncId *)v22) )
      v6 = -2147024809;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      81,
      (unsigned int)WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids,
      (unsigned int)"SyncKnowledge::ValidateLocalReplicaId",
      v6);
  if ( (v16 & 0x20000) == 0 && v13 && _InterlockedExchangeAdd((volatile signed __int32 *)v13, 0xFFFFFFFF) == 1 )
    SeFree(v13);
  if ( (v10 & 0x20000) == 0 && v11 && _InterlockedExchangeAdd((volatile signed __int32 *)v11, 0xFFFFFFFF) == 1 )
    SeFree(v11);
  return v6;
}

```

## disassembly

```asm
0x18000b688  mov     [rsp-38h+arg_0], rbx
0x18000b68d  mov     [rsp-38h+arg_8], rdx
0x18000b692  push    rbp
0x18000b693  push    rsi
0x18000b694  push    rdi
0x18000b695  push    r12
0x18000b697  push    r13
0x18000b699  push    r14
0x18000b69b  push    r15
0x18000b69d  mov     rbp, rsp
0x18000b6a0  sub     rsp, 50h
0x18000b6a4  mov     r12, rdx
0x18000b6a7  mov     r13, rcx
0x18000b6aa  mov     rbx, cs:WPP_GLOBAL_Control
0x18000b6b1  lea     rdi, WPP_GLOBAL_Control
0x18000b6b8  cmp     rbx, rdi
0x18000b6bb  jz      short loc_18000B6D6
0x18000b6bd  test    byte ptr [rbx+1Ch], 40h
0x18000b6c1  jnz     loc_18000B94F
0x18000b6c7  cmp     rbx, rdi
0x18000b6ca  jz      short loc_18000B6D6
0x18000b6cc  test    byte ptr [rbx+1Ch], 1
0x18000b6d0  jnz     loc_18000B981
0x18000b6d6  lea     rsi, [r13+3Ch]
0x18000b6da  mov     ecx, 2
0x18000b6df  test    r12, r12
0x18000b6e2  jz      loc_18000B93B
0x18000b6e8  cmp     dword ptr [r13+38h], 0
0x18000b6ed  jnz     short loc_18000B6FD
0x18000b6ef  xor     eax, eax
0x18000b6f1  cmp     ax, [rsi]
0x18000b6f4  jnz     short loc_18000B711
0x18000b6f6  mov     edi, 80041000h
0x18000b6fb  jmp     short loc_18000B713
0x18000b6fd  cmp     [rsi], cx
0x18000b700  jbe     short loc_18000B6F6
0x18000b702  movzx   eax, word ptr [r12]
0x18000b707  cmp     ax, cx
0x18000b70a  jbe     short loc_18000B6F6
0x18000b70c  cmp     ax, [rsi]
0x18000b70f  ja      short loc_18000B6F6
0x18000b711  xor     edi, edi
0x18000b713  xor     r14d, r14d
0x18000b716  xor     r15d, r15d
0x18000b719  mov     [rbp+var_1C], r14d
0x18000b71d  test    edi, edi
0x18000b71f  jnz     short loc_18000B75D
0x18000b721  movzx   eax, word ptr [rsi]
0x18000b724  mov     r15, r12
0x18000b727  mov     r14d, [r13+38h]
0x18000b72b  mov     word ptr [rbp+var_1C], ax
0x18000b72f  and     r14d, 1
0x18000b733  mov     eax, [rbp+var_1C]
0x18000b736  or      r14d, ecx
0x18000b739  btr     eax, 10h
0x18000b73d  shl     r14d, 10h
0x18000b741  or      r14d, eax
0x18000b744  mov     [rbp+var_18], r12
0x18000b748  lea     rcx, [rbp+var_20]; this
0x18000b74c  mov     [rbp+var_1C], r14d
0x18000b750  call    ?IsMaxId@SyncId@@QEBAHXZ; SyncId::IsMaxId(void)
0x18000b755  test    eax, eax
0x18000b757  jnz     loc_18000B945
0x18000b75d  lea     rax, WPP_GLOBAL_Control
0x18000b764  cmp     rbx, rax
0x18000b767  jz      short loc_18000B773
0x18000b769  test    byte ptr [rbx+1Ch], 1
0x18000b76d  jnz     loc_18000B9B3
0x18000b773  bt      r14d, 11h
0x18000b778  jb      short loc_18000B797
0x18000b77a  test    r15, r15
0x18000b77d  jz      short loc_18000B797
0x18000b77f  or      eax, 0FFFFFFFFh
0x18000b782  lock xadd [r15], eax
0x18000b787  cmp     eax, 1
0x18000b78a  jz      loc_18000B914
0x18000b790  mov     rbx, cs:WPP_GLOBAL_Control
0x18000b797  test    edi, edi
0x18000b799  jz      loc_18000B892
0x18000b79f  xor     r15d, r15d
0x18000b7a2  xor     r14d, r14d
0x18000b7a5  mov     [rbp+var_1C], r15d
0x18000b7a9  mov     [rbp+var_18], r14
0x18000b7ad  test    edi, edi
0x18000b7af  jnz     short loc_18000B7E1
0x18000b7b1  movzx   eax, word ptr [rsi]
0x18000b7b4  mov     r15d, [r13+38h]
0x18000b7b8  mov     r14, [r13+2D8h]
0x18000b7bf  and     r15d, 1
0x18000b7c3  mov     word ptr [rbp+var_1C], ax
0x18000b7c7  or      r15d, 2
0x18000b7cb  mov     eax, [rbp+var_1C]
0x18000b7ce  shl     r15d, 10h
0x18000b7d2  btr     eax, 10h
0x18000b7d6  or      r15d, eax
0x18000b7d9  mov     [rbp+var_18], r14
0x18000b7dd  mov     [rbp+var_1C], r15d
0x18000b7e1  xor     eax, eax
0x18000b7e3  xor     r12d, r12d
0x18000b7e6  mov     [rbp+var_C], eax
0x18000b7e9  test    edi, edi
0x18000b7eb  jnz     loc_18000B9E9
0x18000b7f1  movzx   eax, word ptr [rsi]
0x18000b7f4  lea     rdx, [rbp+var_10]; struct SyncId *
0x18000b7f8  mov     esi, [r13+38h]
0x18000b7fc  lea     rcx, [rbp+var_20]; struct SyncId *
0x18000b800  mov     r12, [rbp+arg_8]
0x18000b804  and     esi, 1
0x18000b807  mov     word ptr [rbp+var_C], ax
0x18000b80b  or      esi, 2
0x18000b80e  mov     eax, [rbp+var_C]
0x18000b811  btr     eax, 10h
0x18000b815  shl     esi, 10h
0x18000b818  or      esi, eax
0x18000b81a  mov     [rbp+var_8], r12
0x18000b81e  mov     [rbp+var_C], esi
0x18000b821  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18000b826  test    eax, eax
0x18000b828  jnz     loc_18000B90A
0x18000b82e  lea     rax, WPP_GLOBAL_Control
0x18000b835  cmp     rbx, rax
0x18000b838  jnz     loc_18000B8D1
0x18000b83e  bt      esi, 11h
0x18000b842  jb      short loc_18000B85B
0x18000b844  test    r12, r12
0x18000b847  jz      short loc_18000B85B
0x18000b849  or      eax, 0FFFFFFFFh
0x18000b84c  lock xadd [r12], eax
0x18000b852  cmp     eax, 1
0x18000b855  jz      loc_18000B921
0x18000b85b  bt      r15d, 11h
0x18000b860  jb      short loc_18000B878
0x18000b862  test    r14, r14
0x18000b865  jz      short loc_18000B878
0x18000b867  or      eax, 0FFFFFFFFh
0x18000b86a  lock xadd [r14], eax
0x18000b86f  cmp     eax, 1
0x18000b872  jz      loc_18000B92E
0x18000b878  mov     rbx, [rsp+50h+arg_0]
0x18000b880  mov     eax, edi
0x18000b882  add     rsp, 50h
0x18000b886  pop     r15
0x18000b888  pop     r14
0x18000b88a  pop     r13
0x18000b88c  pop     r12
0x18000b88e  pop     rdi
0x18000b88f  pop     rsi
0x18000b890  pop     rbp
0x18000b891  retn
0x18000b892  mov     rcx, r13; this
0x18000b895  call    ?EnsureIdBuffer@SyncKnowledge@@AEBAJXZ; SyncKnowledge::EnsureIdBuffer(void)
0x18000b89a  mov     edi, eax
0x18000b89c  test    eax, eax
0x18000b89e  jnz     short loc_18000B8C5
0x18000b8a0  movzx   eax, word ptr [r13+3Ch]
0x18000b8a5  lea     r8, [rbp+arg_10]
0x18000b8a9  mov     rdx, [r13+2D8h]
0x18000b8b0  mov     rcx, r13
0x18000b8b3  mov     [rbp+arg_10], eax
0x18000b8b6  mov     rax, [r13+0]
0x18000b8ba  mov     rax, [rax+18h]
0x18000b8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8c3  mov     edi, eax
0x18000b8c5  mov     rbx, cs:WPP_GLOBAL_Control
0x18000b8cc  jmp     loc_18000B79F
0x18000b8d1  test    byte ptr [rbx+1Ch], 40h
0x18000b8d5  jz      loc_18000B83E
0x18000b8db  cmp     byte ptr [rbx+19h], 5
0x18000b8df  jb      loc_18000B83E
0x18000b8e5  mov     rcx, [rbx+10h]
0x18000b8e9  lea     r9, aSyncknowledgeV; "SyncKnowledge::ValidateLocalReplicaId"
0x18000b8f0  mov     edx, 51h ; 'Q'
0x18000b8f5  mov     [rsp+50h+var_30], edi
0x18000b8f9  lea     r8, WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids
0x18000b900  call    WPP_SF_sD
0x18000b905  jmp     loc_18000B83E
0x18000b90a  mov     edi, 80070057h
0x18000b90f  jmp     loc_18000B82E
0x18000b914  mov     rcx, r15; void *
0x18000b917  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x18000b91c  jmp     loc_18000B790
0x18000b921  mov     rcx, r12; void *
0x18000b924  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x18000b929  jmp     loc_18000B85B
0x18000b92e  mov     rcx, r14; void *
0x18000b931  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x18000b936  jmp     loc_18000B878
0x18000b93b  mov     edi, 80004003h
0x18000b940  jmp     loc_18000B713
0x18000b945  mov     edi, 80070057h
0x18000b94a  jmp     loc_18000B75D
0x18000b94f  cmp     byte ptr [rbx+19h], 5
0x18000b953  jb      loc_18000B6C7
0x18000b959  mov     rcx, [rbx+10h]
0x18000b95d  lea     r9, aSyncknowledgeV; "SyncKnowledge::ValidateLocalReplicaId"
0x18000b964  mov     edx, 50h ; 'P'
0x18000b969  lea     r8, WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids
0x18000b970  call    WPP_SF_s
0x18000b975  mov     rbx, cs:WPP_GLOBAL_Control
0x18000b97c  jmp     loc_18000B6C7
0x18000b981  cmp     byte ptr [rbx+19h], 5
0x18000b985  jb      loc_18000B6D6
0x18000b98b  mov     rcx, [rbx+10h]
0x18000b98f  lea     r9, aKnowledgeservi_4; "KnowledgeServices::ValidateIdBytes"
0x18000b996  mov     edx, 0Ah
0x18000b99b  lea     r8, WPP_e65626ae806d36e8966776faf765a664_Traceguids
0x18000b9a2  call    WPP_SF_s
0x18000b9a7  mov     rbx, cs:WPP_GLOBAL_Control
0x18000b9ae  jmp     loc_18000B6D6
0x18000b9b3  cmp     byte ptr [rbx+19h], 5
0x18000b9b7  jb      loc_18000B773
0x18000b9bd  mov     rcx, [rbx+10h]
0x18000b9c1  lea     r9, aKnowledgeservi_4; "KnowledgeServices::ValidateIdBytes"
0x18000b9c8  mov     edx, 0Bh
0x18000b9cd  mov     [rsp+50h+var_30], edi
0x18000b9d1  lea     r8, WPP_e65626ae806d36e8966776faf765a664_Traceguids
0x18000b9d8  call    WPP_SF_sD
0x18000b9dd  mov     rbx, cs:WPP_GLOBAL_Control
0x18000b9e4  jmp     loc_18000B773
0x18000b9e9  mov     esi, eax
0x18000b9eb  jmp     loc_18000B82E
```
