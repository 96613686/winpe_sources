# StructuredQuery1::CompoundCondition::Load(IStream *)

- ea: `0x18003d560`
- end: `0x18003d6be`
- name: `?Load@CompoundCondition@StructuredQuery1@@UEAAJPEAUIStream@@@Z`
- size: `350`
- prototype: `int(StructuredQuery1::CompoundCondition *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000bd20`
- `0x18003d560`
- `0x18003d6c4`
- `0x18003db30`
- `0x18008b010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d59f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d5c2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d59f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d5c2`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::CompoundCondition::Load(
        StructuredQuery1::CompoundCondition *this,
        struct IStream *a2)
{
  int v4; // ebx
  void *v5; // rsi
  unsigned int v6; // ebp
  unsigned int pv; // [rsp+58h] [rbp+10h] BYREF
  void *v9; // [rsp+60h] [rbp+18h] BYREF

  if ( a2 )
  {
    v4 = StructuredQuery1::BaseCondition::Load(this, a2);
    if ( v4 >= 0 )
    {
      v4 = IStream_Read(a2, (char *)this + 48, 4u);
      if ( v4 >= 0 )
      {
        pv = 0;
        v4 = IStream_Read(a2, &pv, 4u);
        if ( v4 >= 0 && pv != -1 )
        {
          v9 = 0;
          v4 = FixedCapacityObjectCollection::CreateInstance(pv, &GUID_5632b1a4_e38a_400a_928a_d4cd63230295, &v9);
          if ( v4 >= 0 )
          {
            v5 = v9;
            v6 = 0;
            while ( v6 < pv )
            {
              v9 = 0;
              v4 = SQ_IUnknown_LoadKnownImplFromStream(
                     a2,
                     (const struct _GUID *const *)&g_rgClassIdCondition,
                     3u,
                     &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                     &v9);
              if ( v4 >= 0 )
              {
                v4 = (*(__int64 (__fastcall **)(void *, void *))(*(_QWORD *)v5 + 40LL))(v5, v9);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
              }
              ++v6;
              if ( v4 < 0 )
                goto LABEL_12;
            }
            v4 = (**(__int64 (__fastcall ***)(void *, GUID *, char *))v5)(
                   v5,
                   &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                   (char *)this + 56);
LABEL_12:
            (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003d560  mov     [rsp+arg_0], rbx
0x18003d565  mov     [rsp+arg_18], rbp
0x18003d56a  push    rsi
0x18003d56b  push    rdi
0x18003d56c  push    r14
0x18003d56e  sub     rsp, 30h
0x18003d572  mov     rdi, rdx
0x18003d575  mov     r14, rcx
0x18003d578  test    rdx, rdx
0x18003d57b  jz      loc_18003D687
0x18003d581  call    ?Load@BaseCondition@StructuredQuery1@@UEAAJPEAUIStream@@@Z; StructuredQuery1::BaseCondition::Load(IStream *)
0x18003d586  mov     ebx, eax
0x18003d588  test    eax, eax
0x18003d58a  js      loc_18003D68C
0x18003d590  mov     esi, 4
0x18003d595  lea     rdx, [r14+30h]; pv
0x18003d599  mov     r8d, esi; cb
0x18003d59c  mov     rcx, rdi; pstm
0x18003d59f  call    cs:__imp_IStream_Read
0x18003d5a5  mov     ebx, eax
0x18003d5a7  test    eax, eax
0x18003d5a9  js      loc_18003D68C
0x18003d5af  mov     r8d, esi; cb
0x18003d5b2  mov     [rsp+48h+pv], 0
0x18003d5ba  lea     rdx, [rsp+48h+pv]; pv
0x18003d5bf  mov     rcx, rdi; pstm
0x18003d5c2  call    cs:__imp_IStream_Read
0x18003d5c8  mov     ebx, eax
0x18003d5ca  test    eax, eax
0x18003d5cc  js      loc_18003D68C
0x18003d5d2  mov     ecx, [rsp+48h+pv]; unsigned int
0x18003d5d6  cmp     ecx, 0FFFFFFFFh
0x18003d5d9  jnb     loc_18003D68C
0x18003d5df  lea     r8, [rsp+48h+arg_10]; void **
0x18003d5e4  mov     [rsp+48h+arg_10], 0
0x18003d5ed  lea     rdx, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295; struct _GUID *
0x18003d5f4  call    ?CreateInstance@FixedCapacityObjectCollection@@SAJIAEBU_GUID@@PEAPEAX@Z; FixedCapacityObjectCollection::CreateInstance(uint,_GUID const &,void * *)
0x18003d5f9  mov     ebx, eax
0x18003d5fb  test    eax, eax
0x18003d5fd  js      loc_18003D68C
0x18003d603  mov     rsi, [rsp+48h+arg_10]
0x18003d608  xor     ebp, ebp
0x18003d60a  cmp     ebp, [rsp+48h+pv]
0x18003d60e  jnb     loc_18003D6A1
0x18003d614  lea     rax, [rsp+48h+arg_10]
0x18003d619  mov     [rsp+48h+arg_10], 0
0x18003d622  lea     r9, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x18003d629  mov     [rsp+48h+var_28], rax
0x18003d62e  mov     r8d, 3
0x18003d634  lea     rdx, ?g_rgClassIdCondition@@3QBQEBU_GUID@@B; _GUID const * const near * const g_rgClassIdCondition
0x18003d63b  mov     rcx, rdi
0x18003d63e  call    SQ_IUnknown_LoadKnownImplFromStream
0x18003d643  mov     ebx, eax
0x18003d645  test    eax, eax
0x18003d647  js      short loc_18003D670
0x18003d649  mov     rax, [rsi]
0x18003d64c  mov     rcx, rsi
0x18003d64f  mov     rdx, [rsp+48h+arg_10]
0x18003d654  mov     rax, [rax+28h]
0x18003d658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d65d  mov     rcx, [rsp+48h+arg_10]
0x18003d662  mov     ebx, eax
0x18003d664  mov     rax, [rcx]
0x18003d667  mov     rax, [rax+10h]
0x18003d66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d670  inc     ebp
0x18003d672  test    ebx, ebx
0x18003d674  jns     short loc_18003D60A
0x18003d676  mov     rax, [rsi]
0x18003d679  mov     rcx, rsi
0x18003d67c  mov     rax, [rax+10h]
0x18003d680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d685  jmp     short loc_18003D68C
0x18003d687  mov     ebx, 80070057h
0x18003d68c  mov     rbp, [rsp+48h+arg_18]
0x18003d691  mov     eax, ebx
0x18003d693  mov     rbx, [rsp+48h+arg_0]
0x18003d698  add     rsp, 30h
0x18003d69c  pop     r14
0x18003d69e  pop     rdi
0x18003d69f  pop     rsi
0x18003d6a0  retn
0x18003d6a1  mov     rax, [rsi]
0x18003d6a4  lea     r8, [r14+38h]
0x18003d6a8  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x18003d6af  mov     rcx, rsi
0x18003d6b2  mov     rax, [rax]
0x18003d6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6ba  mov     ebx, eax
0x18003d6bc  jmp     short loc_18003D676
```
