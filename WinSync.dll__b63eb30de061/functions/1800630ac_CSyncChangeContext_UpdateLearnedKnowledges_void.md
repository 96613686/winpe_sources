# CSyncChangeContext::UpdateLearnedKnowledges(void)

- ea: `0x1800630ac`
- end: `0x180063396`
- name: `?UpdateLearnedKnowledges@CSyncChangeContext@@AEAAJXZ`
- size: `746`
- prototype: `__int64 __fastcall(CSyncChangeContext *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800229e0`
- `0x180061e80`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18001fc38`
- `0x180021bec`
- `0x1800227b0`
- `0x1800630ac`
- `0x18006339c`
- `0x180094010`

## string_xrefs

- `0x1800630e5`: `CSyncChangeContext::UpdateLearnedKnowledges`
- `0x180063367`: `CSyncChangeContext::UpdateLearnedKnowledges`

## pseudocode

```c
__int64 __fastcall CSyncChangeContext::UpdateLearnedKnowledges(CSyncChangeContext *this)
{
  CSyncChangeWrapper *v2; // rcx
  int TransferFilters; // ebx
  int updated; // eax
  _QWORD *v5; // rsi
  __int64 v6; // rcx
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rcx
  unsigned __int8 *v8; // r14
  int RootItemIdInternal; // eax
  __int64 v10; // rsi
  __int64 v11; // rax
  _QWORD *v12; // rdx
  __int64 v13; // rcx
  __int64 (*v14)(void); // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v18; // [rsp+60h] [rbp+30h] BYREF
  __int64 v19; // [rsp+68h] [rbp+38h] BYREF
  unsigned __int8 *v20; // [rsp+70h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids,
      "CSyncChangeContext::UpdateLearnedKnowledges");
  }
  v2 = (CSyncChangeWrapper *)*((_QWORD *)this + 6);
  v19 = 0;
  LODWORD(v18) = 0;
  TransferFilters = CSyncChangeWrapper::GetTransferFilters(v2, (enum SYNC_TRANSFER_FILTER *)&v18);
  if ( TransferFilters < 0 )
    goto LABEL_24;
  if ( (v18 & 0x80000) == 0 || *((_DWORD *)this + 20) )
  {
    TransferFilters = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 14) + 80LL))(
                        *((_QWORD *)this + 14),
                        &v19);
    if ( TransferFilters < 0 )
      goto LABEL_24;
    v5 = (_QWORD *)((char *)this + 104);
    TransferFilters = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 104LL))(v19, *((_QWORD *)this + 13));
    if ( TransferFilters < 0 )
      goto LABEL_24;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 16LL))(*v5);
    v6 = *((_QWORD *)this + 15);
    *v5 = v19;
    v19 = 0;
    if ( !v6 )
      goto LABEL_14;
    updated = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 104LL))(v6, *((_QWORD *)this + 16));
  }
  else
  {
    updated = CSyncChangeContext::UpdateLearnedKnowledgesWithAdjustment(this);
    v5 = (_QWORD *)((char *)this + 104);
  }
  TransferFilters = updated;
  if ( updated >= 0 )
  {
LABEL_14:
    if ( *((_DWORD *)this + 40) )
    {
      v7 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v5;
      v8 = 0;
      v18 = 0;
      v20 = 0;
      TransferFilters = (**v7)(v7, &GUID_9b783db4_b705_4639_838e_b30451702c2b, &v18);
      if ( !TransferFilters )
      {
        RootItemIdInternal = CSyncChangeWrapper::GetRootItemIdInternal(*((CSyncChangeWrapper **)this + 6), &v20);
        v8 = v20;
        TransferFilters = RootItemIdInternal;
        if ( !RootItemIdInternal )
        {
          TransferFilters = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v18 + 40LL))(v18, v20);
          if ( TransferFilters )
          {
            if ( TransferFilters == 1 )
              TransferFilters = 0;
          }
          else
          {
            TransferFilters = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v18 + 56LL))(v18, v8);
          }
        }
      }
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      IdParameters::FreeId(v8);
    }
  }
LABEL_24:
  v10 = 0;
  while ( TransferFilters >= 0 )
  {
    if ( (unsigned int)v10 >= *((_DWORD *)this + 41) )
    {
      *((_DWORD *)this + 18) = 0;
      break;
    }
    v11 = *((_QWORD *)this + 21);
    v18 = 0;
    v12 = (_QWORD *)(v11 + 8 * v10);
    v13 = *(_QWORD *)(*((_QWORD *)this + 22) + 8 * v10);
    v14 = *(__int64 (**)(void))(*(_QWORD *)v13 + 80LL);
    if ( *v12 )
    {
      TransferFilters = ((__int64 (__fastcall *)(__int64, __int64 *))v14)(v13, &v18);
      if ( !TransferFilters
        && (!*(_QWORD *)(*((_QWORD *)this + 21) + 8 * v10)
         || (TransferFilters = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 104LL))(v18)) == 0) )
      {
        v15 = *(_QWORD *)(*((_QWORD *)this + 21) + 8 * v10);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        *(_QWORD *)(*((_QWORD *)this + 21) + 8 * v10) = v18;
        v16 = 0;
        v18 = 0;
        goto LABEL_33;
      }
    }
    else
    {
      TransferFilters = v14();
    }
    v16 = v18;
LABEL_33:
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v10 = (unsigned int)(v10 + 1);
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids,
      (unsigned int)"CSyncChangeContext::UpdateLearnedKnowledges",
      TransferFilters);
  }
  return (unsigned int)TransferFilters;
}

```

## disassembly

```asm
0x1800630ac  mov     [rsp-28h+arg_18], rbx
0x1800630b1  push    rbp
0x1800630b2  push    rsi
0x1800630b3  push    rdi
0x1800630b4  push    r12
0x1800630b6  push    r14
0x1800630b8  mov     rbp, rsp
0x1800630bb  sub     rsp, 30h
0x1800630bf  mov     rdi, rcx
0x1800630c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800630c9  lea     r12, WPP_GLOBAL_Control
0x1800630d0  cmp     rcx, r12
0x1800630d3  jz      short loc_1800630FD
0x1800630d5  test    byte ptr [rcx+1Ch], 8
0x1800630d9  jz      short loc_1800630FD
0x1800630db  cmp     byte ptr [rcx+19h], 5
0x1800630df  jb      short loc_1800630FD
0x1800630e1  mov     rcx, [rcx+10h]
0x1800630e5  lea     r9, aCsyncchangecon_3; "CSyncChangeContext::UpdateLearnedKnowle"...
0x1800630ec  mov     edx, 13h
0x1800630f1  lea     r8, WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids
0x1800630f8  call    WPP_SF_s
0x1800630fd  mov     rcx, [rdi+30h]; this
0x180063101  lea     rdx, [rbp+arg_0]; enum SYNC_TRANSFER_FILTER *
0x180063105  mov     [rbp+arg_8], 0
0x18006310d  mov     dword ptr [rbp+arg_0], 0
0x180063114  call    ?GetTransferFilters@CSyncChangeWrapper@@QEAAJPEAW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeWrapper::GetTransferFilters(SYNC_TRANSFER_FILTER *)
0x180063119  mov     ebx, eax
0x18006311b  test    eax, eax
0x18006311d  js      loc_180063266
0x180063123  test    dword ptr [rbp+arg_0], 80000h
0x18006312a  jz      short loc_180063140
0x18006312c  cmp     dword ptr [rdi+50h], 0
0x180063130  jnz     short loc_180063140
0x180063132  mov     rcx, rdi; this
0x180063135  call    ?UpdateLearnedKnowledgesWithAdjustment@CSyncChangeContext@@AEAAJXZ; CSyncChangeContext::UpdateLearnedKnowledgesWithAdjustment(void)
0x18006313a  lea     rsi, [rdi+68h]
0x18006313e  jmp     short loc_1800631B9
0x180063140  mov     rcx, [rdi+70h]
0x180063144  lea     rdx, [rbp+arg_8]
0x180063148  mov     rax, [rcx]
0x18006314b  mov     rax, [rax+50h]
0x18006314f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063154  mov     ebx, eax
0x180063156  test    eax, eax
0x180063158  js      loc_180063266
0x18006315e  mov     rcx, [rbp+arg_8]
0x180063162  lea     rsi, [rdi+68h]
0x180063166  mov     rdx, [rsi]
0x180063169  mov     rax, [rcx]
0x18006316c  mov     rax, [rax+68h]
0x180063170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063175  mov     ebx, eax
0x180063177  test    eax, eax
0x180063179  js      loc_180063266
0x18006317f  mov     rcx, [rsi]
0x180063182  mov     rax, [rcx]
0x180063185  mov     rax, [rax+10h]
0x180063189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006318e  mov     rax, [rbp+arg_8]
0x180063192  mov     rcx, [rdi+78h]
0x180063196  mov     [rsi], rax
0x180063199  mov     [rbp+arg_8], 0
0x1800631a1  test    rcx, rcx
0x1800631a4  jz      short loc_1800631C3
0x1800631a6  mov     rax, [rcx]
0x1800631a9  mov     rdx, [rdi+80h]
0x1800631b0  mov     rax, [rax+68h]
0x1800631b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631b9  mov     ebx, eax
0x1800631bb  test    eax, eax
0x1800631bd  js      loc_180063266
0x1800631c3  cmp     dword ptr [rdi+0A0h], 0
0x1800631ca  jz      loc_180063266
0x1800631d0  mov     rcx, [rsi]
0x1800631d3  lea     r8, [rbp+arg_0]
0x1800631d7  xor     r14d, r14d
0x1800631da  lea     rdx, _GUID_9b783db4_b705_4639_838e_b30451702c2b
0x1800631e1  mov     [rbp+arg_0], r14
0x1800631e5  mov     [rbp+arg_10], r14
0x1800631e9  mov     rax, [rcx]
0x1800631ec  mov     rax, [rax]
0x1800631ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631f4  mov     ebx, eax
0x1800631f6  test    eax, eax
0x1800631f8  jnz     short loc_180063249
0x1800631fa  mov     rcx, [rdi+30h]; this
0x1800631fe  lea     rdx, [rbp+arg_10]; unsigned __int8 **
0x180063202  call    ?GetRootItemIdInternal@CSyncChangeWrapper@@QEAAJPEAPEAE@Z; CSyncChangeWrapper::GetRootItemIdInternal(uchar * *)
0x180063207  mov     r14, [rbp+arg_10]
0x18006320b  mov     ebx, eax
0x18006320d  test    eax, eax
0x18006320f  jnz     short loc_180063249
0x180063211  mov     rcx, [rbp+arg_0]
0x180063215  mov     rdx, r14
0x180063218  mov     rax, [rcx]
0x18006321b  mov     rax, [rax+28h]
0x18006321f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063224  mov     ebx, eax
0x180063226  test    eax, eax
0x180063228  jnz     short loc_180063241
0x18006322a  mov     rcx, [rbp+arg_0]
0x18006322e  mov     rdx, r14
0x180063231  mov     rax, [rcx]
0x180063234  mov     rax, [rax+38h]
0x180063238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006323d  mov     ebx, eax
0x18006323f  jmp     short loc_180063249
0x180063241  xor     eax, eax
0x180063243  cmp     ebx, 1
0x180063246  cmovz   ebx, eax
0x180063249  mov     rcx, [rbp+arg_0]
0x18006324d  test    rcx, rcx
0x180063250  jz      short loc_18006325E
0x180063252  mov     rax, [rcx]
0x180063255  mov     rax, [rax+10h]
0x180063259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006325e  mov     rcx, r14; unsigned __int8 *
0x180063261  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x180063266  xor     esi, esi
0x180063268  jmp     loc_180063325
0x18006326d  cmp     esi, [rdi+0A4h]
0x180063273  jnb     loc_18006332F
0x180063279  mov     rax, [rdi+0A8h]
0x180063280  mov     [rbp+arg_0], 0
0x180063288  lea     rdx, [rax+rsi*8]
0x18006328c  mov     rax, [rdi+0B0h]
0x180063293  cmp     qword ptr [rdx], 0
0x180063297  mov     rcx, [rax+rsi*8]
0x18006329b  mov     rax, [rcx]
0x18006329e  mov     rax, [rax+50h]
0x1800632a2  jz      short loc_180063307
0x1800632a4  lea     rdx, [rbp+arg_0]
0x1800632a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800632ad  mov     ebx, eax
0x1800632af  test    eax, eax
0x1800632b1  jnz     short loc_18006330E
0x1800632b3  mov     rax, [rdi+0A8h]
0x1800632ba  mov     rdx, [rax+rsi*8]
0x1800632be  test    rdx, rdx
0x1800632c1  jz      short loc_1800632D9
0x1800632c3  mov     rcx, [rbp+arg_0]
0x1800632c7  mov     rax, [rcx]
0x1800632ca  mov     rax, [rax+68h]
0x1800632ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800632d3  mov     ebx, eax
0x1800632d5  test    eax, eax
0x1800632d7  jnz     short loc_18006330E
0x1800632d9  mov     rax, [rdi+0A8h]
0x1800632e0  mov     rcx, [rax+rsi*8]
0x1800632e4  mov     rax, [rcx]
0x1800632e7  mov     rax, [rax+10h]
0x1800632eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800632f0  mov     rcx, [rdi+0A8h]
0x1800632f7  mov     rax, [rbp+arg_0]
0x1800632fb  mov     [rcx+rsi*8], rax
0x1800632ff  xor     ecx, ecx
0x180063301  mov     [rbp+arg_0], rcx
0x180063305  jmp     short loc_180063312
0x180063307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006330c  mov     ebx, eax
0x18006330e  mov     rcx, [rbp+arg_0]
0x180063312  test    rcx, rcx
0x180063315  jz      short loc_180063323
0x180063317  mov     rax, [rcx]
0x18006331a  mov     rax, [rax+10h]
0x18006331e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063323  inc     esi
0x180063325  test    ebx, ebx
0x180063327  jns     loc_18006326D
0x18006332d  jmp     short loc_180063336
0x18006332f  mov     dword ptr [rdi+48h], 0
0x180063336  mov     rcx, [rbp+arg_8]
0x18006333a  test    rcx, rcx
0x18006333d  jz      short loc_18006334B
0x18006333f  mov     rax, [rcx]
0x180063342  mov     rax, [rax+10h]
0x180063346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006334b  mov     rcx, cs:WPP_GLOBAL_Control
0x180063352  cmp     rcx, r12
0x180063355  jz      short loc_180063383
0x180063357  test    byte ptr [rcx+1Ch], 8
0x18006335b  jz      short loc_180063383
0x18006335d  cmp     byte ptr [rcx+19h], 5
0x180063361  jb      short loc_180063383
0x180063363  mov     rcx, [rcx+10h]
0x180063367  lea     r9, aCsyncchangecon_3; "CSyncChangeContext::UpdateLearnedKnowle"...
0x18006336e  mov     edx, 14h
0x180063373  mov     [rsp+30h+var_10], ebx
0x180063377  lea     r8, WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids
0x18006337e  call    WPP_SF_sD
0x180063383  mov     eax, ebx
0x180063385  mov     rbx, [rsp+30h+arg_18]
0x18006338a  add     rsp, 30h
0x18006338e  pop     r14
0x180063390  pop     r12
0x180063392  pop     rdi
0x180063393  pop     rsi
0x180063394  pop     rbp
0x180063395  retn
```
