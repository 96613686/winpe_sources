# CChangeApplier::GetDestinationKnowledgeWithTemporaryConflicts(IEnumLoggedConflicts *,ISyncKnowledge * *)

- ea: `0x18003baa8`
- end: `0x18003bc7a`
- name: `?GetDestinationKnowledgeWithTemporaryConflicts@CChangeApplier@@AEAAJPEAUIEnumLoggedConflicts@@PEAPEAUISyncKnowledge@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this, struct IEnumLoggedConflicts *, struct ISyncKnowledge **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180022014`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18003baa8`
- `0x180094010`

## string_xrefs

- `0x18003bae7`: `CChangeApplier::GetDestinationKnowledgeWithTemporaryConflicts`
- `0x18003bc4b`: `CChangeApplier::GetDestinationKnowledgeWithTemporaryConflicts`

## pseudocode

```c
__int64 __fastcall CChangeApplier::GetDestinationKnowledgeWithTemporaryConflicts(
        CChangeApplier *this,
        struct IEnumLoggedConflicts *a2,
        struct ISyncKnowledge **a3)
{
  PVOID *v6; // rcx
  int v7; // ebx
  __int64 v8; // rcx
  struct ISyncKnowledge *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  __int64 v12; // [rsp+38h] [rbp-8h] BYREF
  int v13; // [rsp+78h] [rbp+38h] BYREF
  struct ISyncKnowledge *v14; // [rsp+88h] [rbp+48h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      170,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::GetDestinationKnowledgeWithTemporaryConflicts");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = -2147467261;
  if ( a2 && a3 )
  {
    v8 = *((_QWORD *)this + 64);
    v14 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge **))(*(_QWORD *)v8 + 80LL))(v8, &v14);
    if ( v7 >= 0 )
      v7 = (*(__int64 (__fastcall **)(struct IEnumLoggedConflicts *))(*(_QWORD *)a2 + 40LL))(a2);
    v11 = 0;
    v13 = 0;
    if ( v7 < 0 )
      goto LABEL_17;
    do
    {
      v7 = (*(__int64 (__fastcall **)(struct IEnumLoggedConflicts *, __int64, __int64 *, int *))(*(_QWORD *)a2 + 24LL))(
             a2,
             1,
             &v11,
             &v13);
      if ( v7 )
        break;
      v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 120LL))(v11);
      if ( !v7 )
      {
        v12 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 96LL))(v11, &v12);
        if ( v7 >= 0 )
        {
          v7 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, __int64))v14->lpVtbl->Union)(v14, v12);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    while ( v7 >= 0 );
    if ( v7 < 0 )
    {
LABEL_17:
      v9 = v14;
    }
    else
    {
      ((void (__fastcall *)(struct ISyncKnowledge *))v14->lpVtbl->AddRef)(v14);
      v9 = v14;
      *a3 = v14;
    }
    ((void (__fastcall *)(struct ISyncKnowledge *))v9->lpVtbl->Release)(v9);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      171,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::GetDestinationKnowledgeWithTemporaryConflicts",
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003baa8  mov     [rsp-28h+arg_0], rbx
0x18003baad  push    rbp
0x18003baae  push    rsi
0x18003baaf  push    rdi
0x18003bab0  push    r12
0x18003bab2  push    r14
0x18003bab4  mov     rbp, rsp
0x18003bab7  sub     rsp, 40h
0x18003babb  mov     rsi, r8
0x18003babe  mov     rdi, rdx
0x18003bac1  mov     r14, rcx
0x18003bac4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bacb  lea     r12, WPP_GLOBAL_Control
0x18003bad2  cmp     rcx, r12
0x18003bad5  jz      short loc_18003BB06
0x18003bad7  test    byte ptr [rcx+1Ch], 8
0x18003badb  jz      short loc_18003BB06
0x18003badd  cmp     byte ptr [rcx+19h], 5
0x18003bae1  jb      short loc_18003BB06
0x18003bae3  mov     rcx, [rcx+10h]
0x18003bae7  lea     r9, aCchangeapplier_45; "CChangeApplier::GetDestinationKnowledge"...
0x18003baee  mov     edx, 0AAh
0x18003baf3  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003bafa  call    WPP_SF_s
0x18003baff  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bb06  mov     ebx, 80004003h
0x18003bb0b  test    rdi, rdi
0x18003bb0e  jz      loc_18003BC36
0x18003bb14  test    rsi, rsi
0x18003bb17  jz      loc_18003BC36
0x18003bb1d  mov     rcx, [r14+200h]
0x18003bb24  lea     rdx, [rbp+arg_18]
0x18003bb28  mov     [rbp+arg_18], 0
0x18003bb30  mov     rax, [rcx]
0x18003bb33  mov     rax, [rax+50h]
0x18003bb37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb3c  mov     ebx, eax
0x18003bb3e  test    eax, eax
0x18003bb40  js      short loc_18003BB53
0x18003bb42  mov     rax, [rdi]
0x18003bb45  mov     rcx, rdi
0x18003bb48  mov     rax, [rax+28h]
0x18003bb4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb51  mov     ebx, eax
0x18003bb53  mov     [rbp+var_10], 0
0x18003bb5b  mov     [rbp+arg_8], 0
0x18003bb62  test    ebx, ebx
0x18003bb64  js      loc_18003BC1F
0x18003bb6a  mov     rax, [rdi]
0x18003bb6d  lea     r9, [rbp+arg_8]
0x18003bb71  lea     r8, [rbp+var_10]
0x18003bb75  mov     edx, 1
0x18003bb7a  mov     rcx, rdi
0x18003bb7d  mov     rax, [rax+18h]
0x18003bb81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb86  mov     ebx, eax
0x18003bb88  test    eax, eax
0x18003bb8a  jnz     short loc_18003BC02
0x18003bb8c  mov     rcx, [rbp+var_10]
0x18003bb90  mov     rax, [rcx]
0x18003bb93  mov     rax, [rax+78h]
0x18003bb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb9c  mov     ebx, eax
0x18003bb9e  test    eax, eax
0x18003bba0  jnz     short loc_18003BBEA
0x18003bba2  mov     rcx, [rbp+var_10]
0x18003bba6  lea     rdx, [rbp+var_8]
0x18003bbaa  mov     [rbp+var_8], 0
0x18003bbb2  mov     rax, [rcx]
0x18003bbb5  mov     rax, [rax+60h]
0x18003bbb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbbe  mov     ebx, eax
0x18003bbc0  test    eax, eax
0x18003bbc2  js      short loc_18003BBEA
0x18003bbc4  mov     rcx, [rbp+arg_18]
0x18003bbc8  mov     rdx, [rbp+var_8]
0x18003bbcc  mov     rax, [rcx]
0x18003bbcf  mov     rax, [rax+68h]
0x18003bbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbd8  mov     rcx, [rbp+var_8]
0x18003bbdc  mov     ebx, eax
0x18003bbde  mov     rax, [rcx]
0x18003bbe1  mov     rax, [rax+10h]
0x18003bbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbea  mov     rcx, [rbp+var_10]
0x18003bbee  mov     rax, [rcx]
0x18003bbf1  mov     rax, [rax+10h]
0x18003bbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbfa  test    ebx, ebx
0x18003bbfc  jns     loc_18003BB6A
0x18003bc02  test    ebx, ebx
0x18003bc04  js      short loc_18003BC1F
0x18003bc06  mov     rcx, [rbp+arg_18]
0x18003bc0a  mov     rax, [rcx]
0x18003bc0d  mov     rax, [rax+8]
0x18003bc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc16  mov     rcx, [rbp+arg_18]
0x18003bc1a  mov     [rsi], rcx
0x18003bc1d  jmp     short loc_18003BC23
0x18003bc1f  mov     rcx, [rbp+arg_18]
0x18003bc23  mov     rax, [rcx]
0x18003bc26  mov     rax, [rax+10h]
0x18003bc2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bc36  cmp     rcx, r12
0x18003bc39  jz      short loc_18003BC67
0x18003bc3b  test    byte ptr [rcx+1Ch], 8
0x18003bc3f  jz      short loc_18003BC67
0x18003bc41  cmp     byte ptr [rcx+19h], 5
0x18003bc45  jb      short loc_18003BC67
0x18003bc47  mov     rcx, [rcx+10h]
0x18003bc4b  lea     r9, aCchangeapplier_45; "CChangeApplier::GetDestinationKnowledge"...
0x18003bc52  mov     edx, 0ABh
0x18003bc57  mov     [rsp+40h+var_20], ebx
0x18003bc5b  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003bc62  call    WPP_SF_sD
0x18003bc67  mov     eax, ebx
0x18003bc69  mov     rbx, [rsp+40h+arg_0]
0x18003bc6e  add     rsp, 40h
0x18003bc72  pop     r14
0x18003bc74  pop     r12
0x18003bc76  pop     rdi
0x18003bc77  pop     rsi
0x18003bc78  pop     rbp
0x18003bc79  retn
```
