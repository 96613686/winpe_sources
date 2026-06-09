# Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::UnregisterObjects(ushort const *)

- ea: `0x14000369c`
- end: `0x14000381f`
- name: `?UnregisterObjects@?$Module@$01VCSingleUseOutOfProcModule@@@WRL@Microsoft@@QEAAJPEBG@Z`
- size: `387`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003eb4`

## callees

- `0x140001184`
- `0x14000164c`
- `0x140003534`
- `0x14000369c`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::UnregisterObjects(
        Microsoft::WRL::Details *this)
{
  int v2; // edi
  __int64 v3; // rbx
  unsigned __int64 v4; // rax
  struct Microsoft::WRL::Details::ModuleBase *v5; // rbx
  unsigned int v6; // ebp
  unsigned __int64 v7; // r15
  struct Microsoft::WRL::Details::ModuleBase *v8; // rdx
  unsigned int v9; // ecx
  size_t v10; // rax
  _DWORD *v11; // rax
  _DWORD *v12; // r14
  __int64 v13; // r8
  struct Microsoft::WRL::Details::ModuleBase *v14; // rdx
  __int64 v15; // rax
  int v16; // ecx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rbp
  unsigned __int64 v20; // rcx

  v2 = 0;
  v3 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 32LL))(this);
  v4 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 40LL))(this);
  v5 = (struct Microsoft::WRL::Details::ModuleBase *)(v3 + 8);
  v6 = 0;
  v7 = v4;
  v8 = v5;
  if ( (unsigned __int64)v5 >= v4 )
    goto LABEL_30;
  do
  {
    v9 = v6 + 1;
    if ( !*(_QWORD *)v8 )
      v9 = v6;
    v8 = (struct Microsoft::WRL::Details::ModuleBase *)((char *)v8 + 8);
    v6 = v9;
  }
  while ( (unsigned __int64)v8 < v4 );
  if ( !v9 )
    goto LABEL_30;
  v10 = 4LL * v9;
  if ( !is_mul_ok(v9, 4u) )
    v10 = -1;
  v11 = operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( v11 )
  {
    v13 = 0;
    v14 = v5;
    do
    {
      if ( *(_QWORD *)v14 )
      {
        v11[v13] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v14 + 24LL) + 8LL);
        v13 = (unsigned int)(v13 + 1);
      }
      v14 = (struct Microsoft::WRL::Details::ModuleBase *)((char *)v14 + 8);
    }
    while ( (unsigned __int64)v14 < v7 );
    v2 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *, _QWORD, _DWORD *, _QWORD))(*(_QWORD *)this + 88LL))(
           this,
           0,
           v11,
           v6);
    v15 = 0;
    do
    {
      if ( *(_QWORD *)v5 )
      {
        v16 = v12[v15];
        v15 = (unsigned int)(v15 + 1);
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v5 + 24LL) + 8LL) = v16;
      }
      v5 = (struct Microsoft::WRL::Details::ModuleBase *)((char *)v5 + 8);
    }
    while ( (unsigned __int64)v5 < v7 );
  }
  else
  {
    v2 = -2147024882;
  }
  operator delete(v12);
  if ( v2 >= 0 )
  {
LABEL_30:
    v17 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *, struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)this + 48LL))(
            this,
            v8);
    v18 = v7 + 8;
    v19 = v17;
    v20 = v7 + 8;
    if ( v7 + 8 < v17 )
    {
      while ( !*(_QWORD *)v20 )
      {
        v20 += 8LL;
        if ( v20 >= v17 )
          goto LABEL_27;
      }
      v2 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *, _QWORD, _QWORD))(*(_QWORD *)this + 72LL))(
             this,
             0,
             *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v20 + 24LL) + 8LL));
      if ( v2 >= 0 )
      {
        do
        {
          if ( *(_QWORD *)v18 )
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v18 + 24LL) + 8LL) = 0;
          v18 += 8LL;
        }
        while ( v18 < v19 );
      }
    }
  }
LABEL_27:
  Microsoft::WRL::Details::TerminateMap(this, v8, 0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000369c  push    rbx
0x14000369e  push    rbp
0x14000369f  push    rsi
0x1400036a0  push    rdi
0x1400036a1  push    r14
0x1400036a3  push    r15
0x1400036a5  sub     rsp, 38h
0x1400036a9  mov     rax, [rcx]
0x1400036ac  mov     rsi, rcx
0x1400036af  xor     edi, edi
0x1400036b1  mov     rax, [rax+20h]
0x1400036b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036ba  mov     rbx, rax
0x1400036bd  mov     rcx, rsi
0x1400036c0  mov     rax, [rsi]
0x1400036c3  mov     rax, [rax+28h]
0x1400036c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036cc  add     rbx, 8
0x1400036d0  xor     ebp, ebp
0x1400036d2  mov     r15, rax
0x1400036d5  mov     rdx, rbx
0x1400036d8  cmp     rbx, rax
0x1400036db  jnb     loc_140003798
0x1400036e1  cmp     [rdx], rdi
0x1400036e4  lea     ecx, [rbp+1]
0x1400036e7  cmovz   ecx, ebp
0x1400036ea  add     rdx, 8
0x1400036ee  mov     ebp, ecx
0x1400036f0  cmp     rdx, r15
0x1400036f3  jb      short loc_1400036E1
0x1400036f5  test    ecx, ecx
0x1400036f7  jz      loc_140003798
0x1400036fd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140003704  mov     eax, 4
0x140003709  mul     rbp
0x14000370c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140003713  cmovb   rax, rcx
0x140003717  mov     rcx, rax; unsigned __int64
0x14000371a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000371f  mov     r14, rax
0x140003722  test    rax, rax
0x140003725  jnz     short loc_14000372E
0x140003727  mov     edi, 8007000Eh
0x14000372c  jmp     short loc_14000378C
0x14000372e  xor     r8d, r8d
0x140003731  mov     rdx, rbx
0x140003734  mov     rax, [rdx]
0x140003737  test    rax, rax
0x14000373a  jz      short loc_14000374A
0x14000373c  mov     rax, [rax+18h]
0x140003740  mov     eax, [rax+8]
0x140003743  mov     [r14+r8*4], eax
0x140003747  inc     r8d
0x14000374a  add     rdx, 8
0x14000374e  cmp     rdx, r15
0x140003751  jb      short loc_140003734
0x140003753  mov     rax, [rsi]
0x140003756  mov     r9d, ebp
0x140003759  mov     r8, r14
0x14000375c  xor     edx, edx
0x14000375e  mov     rcx, rsi
0x140003761  mov     rax, [rax+58h]
0x140003765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000376a  mov     edi, eax
0x14000376c  xor     eax, eax
0x14000376e  mov     rdx, [rbx]
0x140003771  test    rdx, rdx
0x140003774  jz      short loc_140003783
0x140003776  mov     ecx, [r14+rax*4]
0x14000377a  inc     eax
0x14000377c  mov     rdx, [rdx+18h]
0x140003780  mov     [rdx+8], ecx
0x140003783  add     rbx, 8
0x140003787  cmp     rbx, r15
0x14000378a  jb      short loc_14000376E
0x14000378c  mov     rcx, r14; Block
0x14000378f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003794  test    edi, edi
0x140003796  js      short loc_140003805
0x140003798  mov     rax, [rsi]
0x14000379b  mov     rcx, rsi
0x14000379e  mov     rax, [rax+30h]
0x1400037a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037a7  lea     rbx, [r15+8]
0x1400037ab  mov     rbp, rax
0x1400037ae  mov     rcx, rbx
0x1400037b1  cmp     rbx, rax
0x1400037b4  jnb     short loc_140003805
0x1400037b6  mov     r8, [rcx]
0x1400037b9  test    r8, r8
0x1400037bc  jnz     short loc_1400037C9
0x1400037be  add     rcx, 8
0x1400037c2  cmp     rcx, rbp
0x1400037c5  jb      short loc_1400037B6
0x1400037c7  jmp     short loc_140003805
0x1400037c9  mov     rax, [rsi]
0x1400037cc  xor     edx, edx
0x1400037ce  mov     r8, [r8+18h]
0x1400037d2  mov     rcx, rsi
0x1400037d5  mov     rax, [rax+48h]
0x1400037d9  mov     r8, [r8+8]
0x1400037dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037e2  mov     edi, eax
0x1400037e4  test    eax, eax
0x1400037e6  js      short loc_140003805
0x1400037e8  mov     rax, [rbx]
0x1400037eb  test    rax, rax
0x1400037ee  jz      short loc_1400037FC
0x1400037f0  mov     rax, [rax+18h]
0x1400037f4  mov     qword ptr [rax+8], 0
0x1400037fc  add     rbx, 8
0x140003800  cmp     rbx, rbp
0x140003803  jb      short loc_1400037E8
0x140003805  xor     r8d, r8d; unsigned __int16 *
0x140003808  mov     rcx, rsi; this
0x14000380b  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x140003810  mov     eax, edi
0x140003812  add     rsp, 38h
0x140003816  pop     r15
0x140003818  pop     r14
0x14000381a  pop     rdi
0x14000381b  pop     rsi
0x14000381c  pop     rbp
0x14000381d  pop     rbx
0x14000381e  retn
```
