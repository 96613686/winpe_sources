# IISCERTMAP_AUTH_PROVIDER::SetupParsedSiteMetadata(IHttpContext *,INativeSectionException * *)

- ea: `0x180003260`
- end: `0x1800033d4`
- name: `?SetupParsedSiteMetadata@IISCERTMAP_AUTH_PROVIDER@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `372`
- prototype: `__int64 __fastcall(IISCERTMAP_AUTH_PROVIDER *this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180003160`

## callees

- `0x180001008`
- `0x180003260`
- `0x1800041f0`
- `0x180008010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x1800032e5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800032e5`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180003346`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180003346`

## pseudocode

```c
__int64 __fastcall IISCERTMAP_AUTH_PROVIDER::SetupParsedSiteMetadata(
        IISCERTMAP_AUTH_PROVIDER *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v5; // rax
  __int64 v6; // rdi
  _DWORD *v8; // rbx
  int v9; // esi
  int v10; // edi

  v5 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a2)(a2);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( (**(__int64 (__fastcall ***)(__int64, __int64))v6)(v6, qword_18000D800) )
    return 0;
  v8 = operator new(0xB0u);
  if ( !v8 )
    return 2147942408LL;
  v8[2] = 1;
  *(_QWORD *)v8 = &IISCERTMAP_SITE_META_STORED_CONTEXT::`vftable';
  v8[3] = 1;
  STRU::STRU((STRU *)(v8 + 4));
  v8[18] = -1;
  CLKRHashTable::CLKRHashTable(
    (CLKRHashTable *)(v8 + 20),
    "CERT_1TO1_MAP_RULE_HASH",
    (unsigned __int64 (*)(const void *))CTypedHashTable<CERT_1TO1_MAP_RULE_HASH,CERT_1TO1_MAP_RULE,unsigned char *,CLKRHashTable>::_ExtractKey,
    (unsigned int (*)(unsigned __int64))CTypedHashTable<CERT_1TO1_MAP_RULE_HASH,CERT_1TO1_MAP_RULE,unsigned char *,CLKRHashTable>::_CalcKeyHash,
    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<CERT_1TO1_MAP_RULE_HASH,CERT_1TO1_MAP_RULE,unsigned char *,CLKRHashTable>::_EqualKeys,
    (void (*)(const void *, int))CTypedHashTable<CERT_1TO1_MAP_RULE_HASH,CERT_1TO1_MAP_RULE,unsigned char *,CLKRHashTable>::_AddRefRecord,
    4.0,
    1u,
    0,
    0);
  v8[38] = 0;
  *((_QWORD *)v8 + 21) = v8 + 40;
  *((_QWORD *)v8 + 20) = v8 + 40;
  v9 = IISCERTMAP_SITE_META_STORED_CONTEXT::Initialize((IISCERTMAP_SITE_META_STORED_CONTEXT *)v8, a2, a3);
  if ( v9 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v6 + 8LL))(v6, v8, qword_18000D800);
    if ( v10 < 0 )
    {
      (**(void (__fastcall ***)(void *))v8)(v8);
      if ( v10 == -2147024811 )
        return 0;
    }
    return (unsigned int)v10;
  }
  else
  {
    (**(void (__fastcall ***)(void *))v8)(v8);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x180003260  push    rbx
0x180003262  push    rbp
0x180003263  push    rsi
0x180003264  push    rdi
0x180003265  sub     rsp, 58h
0x180003269  mov     rax, [rdx]
0x18000326c  mov     rcx, rdx
0x18000326f  mov     rbp, r8
0x180003272  mov     rsi, rdx
0x180003275  mov     rax, [rax]
0x180003278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000327d  mov     r9, rax
0x180003280  mov     rcx, [rax]
0x180003283  mov     rax, [rcx+10h]
0x180003287  mov     rcx, r9
0x18000328a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000328f  mov     rdx, cs:qword_18000D800
0x180003296  mov     rdi, rax
0x180003299  mov     rcx, [rax]
0x18000329c  mov     rax, [rcx]
0x18000329f  mov     rcx, rdi
0x1800032a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a7  test    rax, rax
0x1800032aa  jz      short loc_1800032B3
0x1800032ac  xor     eax, eax
0x1800032ae  jmp     loc_1800033CB
0x1800032b3  mov     ecx, 0B0h; Size
0x1800032b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800032bd  mov     rbx, rax
0x1800032c0  test    rax, rax
0x1800032c3  jz      loc_1800033C6
0x1800032c9  lea     rax, ??_7IISCERTMAP_SITE_META_STORED_CONTEXT@@6B@; const IISCERTMAP_SITE_META_STORED_CONTEXT::`vftable'
0x1800032d0  mov     dword ptr [rbx+8], 1
0x1800032d7  lea     rcx, [rbx+10h]
0x1800032db  mov     [rbx], rax
0x1800032de  mov     dword ptr [rbx+0Ch], 1
0x1800032e5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800032eb  movsd   xmm0, cs:__real@4010000000000000
0x1800032f3  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VCERT_1TO1_MAP_RULE_HASH@@VCERT_1TO1_MAP_RULE@@PEAEVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<CERT_1TO1_MAP_RULE_HASH,CERT_1TO1_MAP_RULE,uchar *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x1800032fa  mov     [rsp+78h+var_30], 0
0x1800032ff  lea     rcx, [rbx+50h]
0x180003303  mov     [rsp+78h+var_38], 0
0x18000330b  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VCERT_1TO1_MAP_RULE_HASH@@VCERT_1TO1_MAP_RULE@@PEAEVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<CERT_1TO1_MAP_RULE_HASH,CERT_1TO1_MAP_RULE,uchar *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180003312  mov     [rsp+78h+var_40], 1
0x18000331a  lea     r8, ?_ExtractKey@?$CTypedHashTable@VCERT_1TO1_MAP_RULE_HASH@@VCERT_1TO1_MAP_RULE@@PEAEVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<CERT_1TO1_MAP_RULE_HASH,CERT_1TO1_MAP_RULE,uchar *,CLKRHashTable>::_ExtractKey(void const *)
0x180003321  movsd   [rsp+78h+var_48], xmm0
0x180003327  lea     rdx, aCert1to1MapRul; "CERT_1TO1_MAP_RULE_HASH"
0x18000332e  mov     [rsp+78h+var_50], rax
0x180003333  lea     rax, ?_EqualKeys@?$CTypedHashTable@VCERT_1TO1_MAP_RULE_HASH@@VCERT_1TO1_MAP_RULE@@PEAEVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<CERT_1TO1_MAP_RULE_HASH,CERT_1TO1_MAP_RULE,uchar *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x18000333a  mov     [rsp+78h+var_58], rax
0x18000333f  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180003346  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18000334c  lea     rax, [rbx+0A0h]
0x180003353  mov     dword ptr [rbx+98h], 0
0x18000335d  mov     r8, rbp; struct INativeSectionException **
0x180003360  mov     [rax+8], rax
0x180003364  mov     rdx, rsi; struct IHttpContext *
0x180003367  mov     [rax], rax
0x18000336a  mov     rcx, rbx; this
0x18000336d  call    ?Initialize@IISCERTMAP_SITE_META_STORED_CONTEXT@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; IISCERTMAP_SITE_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)
0x180003372  mov     esi, eax
0x180003374  test    eax, eax
0x180003376  jns     short loc_18000338A
0x180003378  mov     rcx, [rbx]
0x18000337b  mov     rax, [rcx]
0x18000337e  mov     rcx, rbx
0x180003381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003386  mov     eax, esi
0x180003388  jmp     short loc_1800033CB
0x18000338a  mov     rax, [rdi]
0x18000338d  mov     rdx, rbx
0x180003390  mov     r8, cs:qword_18000D800
0x180003397  mov     rcx, rdi
0x18000339a  mov     rax, [rax+8]
0x18000339e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033a3  mov     edi, eax
0x1800033a5  test    eax, eax
0x1800033a7  jns     short loc_1800033C2
0x1800033a9  mov     rcx, [rbx]
0x1800033ac  mov     rax, [rcx]
0x1800033af  mov     rcx, rbx
0x1800033b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033b7  xor     ecx, ecx
0x1800033b9  cmp     edi, 80070055h
0x1800033bf  cmovz   edi, ecx
0x1800033c2  mov     eax, edi
0x1800033c4  jmp     short loc_1800033CB
0x1800033c6  mov     eax, 80070008h
0x1800033cb  add     rsp, 58h
0x1800033cf  pop     rdi
0x1800033d0  pop     rsi
0x1800033d1  pop     rbp
0x1800033d2  pop     rbx
0x1800033d3  retn
```
