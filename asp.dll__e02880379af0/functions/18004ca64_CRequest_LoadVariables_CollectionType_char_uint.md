# CRequest::LoadVariables(CollectionType,char *,uint)

- ea: `0x18004ca64`
- end: `0x18004cce6`
- name: `?LoadVariables@CRequest@@AEAAJW4CollectionType@@PEADI@Z`
- size: `642`
- prototype: `__int64 __fastcall(CRequest *, unsigned int, char *, unsigned int)`
- caller_count: `15`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004bf3c`
- `0x18004d600`
- `0x18004d6a0`
- `0x18004d740`
- `0x18004d850`
- `0x18004d9b0`
- `0x18004dec0`
- `0x18004e430`
- `0x18004e890`
- `0x18004ece0`
- `0x18004f610`
- `0x18004f950`
- `0x18004fca0`
- `0x180050000`
- `0x180053850`

## callees

- `0x180006ed4`
- `0x180007228`
- `0x18004a828`
- `0x18004a8f0`
- `0x18004ad4c`
- `0x18004b620`
- `0x18004be94`
- `0x18004c428`
- `0x18004c610`
- `0x18004ca64`
- `0x180064010`

## import_xrefs

- `msvcrt!strcpy_s` at `0x18004cb40`
- `msvcrt!strcpy_s` at `0x18004cb40`
- `KERNEL32!HeapFree` at `0x18004cb00`
- `KERNEL32!HeapFree` at `0x18004cb00`
- `KERNEL32!HeapAlloc` at `0x18004cb15`
- `KERNEL32!HeapAlloc` at `0x18004cb15`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004cbe6`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004cbe6`

## pseudocode

```c
__int64 __fastcall CRequest::LoadVariables(CRequest *a1, unsigned int a2, char *a3, unsigned int a4)
{
  char *v5; // rdi
  __int64 result; // rax
  __int64 v9; // rax
  unsigned int v10; // ebp
  void *v11; // r8
  LPVOID v12; // rax
  unsigned int v13; // r12d
  char *v14; // rbp
  __int64 v15; // r8
  struct CLinkElem *Elem; // rbx
  struct CLinkElem *v17; // rax
  int v18; // r8d
  CRequestHitsArray *v19; // rcx
  char *v20; // [rsp+90h] [rbp+18h] BYREF

  v20 = a3;
  v5 = a3;
  if ( (int)CRequest::CheckForTombstone(a1) < 0 )
    return 2147500037LL;
  if ( a2 == 4 )
    return CRequest::LoadCookies(a1, v5);
  if ( a2 == 5 )
    return CRequest::LoadClCerts(a1, v5, a4);
  if ( !v5 )
    return 0;
  v9 = -1;
  do
    ++v9;
  while ( v5[v9] );
  v10 = v9 + 1;
  if ( a2 != 2 )
  {
    while ( 1 )
    {
LABEL_27:
      if ( !*v5 )
        return 0;
      DecodeFromURL(&v20, "=", v5, v10, a4);
      v13 = v10 + (_DWORD)v5 - (_DWORD)v20;
      v14 = v20;
      DecodeFromURL(&v20, "&", v20, v13, a4);
      if ( *v5 )
        break;
LABEL_26:
      v5 = v20;
      v10 = v13 + (_DWORD)v14 - (_DWORD)v20;
    }
    v15 = -1;
    do
      ++v15;
    while ( v5[v15] );
    Elem = CHashTable::FindElem((CHashTable *)(*((_QWORD *)a1 + 7) + 64LL), v5, v15);
    if ( !Elem )
    {
      v17 = (struct CLinkElem *)ALLOC_CACHE_HANDLER::Alloc(CRequestHit::sm_pach);
      Elem = v17;
      if ( !v17 )
        return 2147942414LL;
      *((_DWORD *)v17 + 10) &= 0xFFFFFFFC;
      *((_QWORD *)v17 + 1) = 0;
      *((_DWORD *)v17 + 4) = 0;
      *((_WORD *)v17 + 10) = 0;
      *((_QWORD *)v17 + 3) = 0;
      *((_QWORD *)v17 + 4) = 0;
      *(_QWORD *)v17 = &CRequestHit::`vftable';
      *((_QWORD *)v17 + 7) = 0;
      *((_QWORD *)v17 + 6) = 0;
      *((_QWORD *)v17 + 8) = 0;
      *((_QWORD *)v17 + 9) = 0;
      if ( (int)CRequestHit::Init(v17, v5, 0) < 0 )
      {
        (**(void (__fastcall ***)(struct CLinkElem *, __int64))Elem)(Elem, 1);
        return 2147500037LL;
      }
      CHashTable::AddElem((CHashTable *)(*((_QWORD *)a1 + 7) + 64LL), Elem, v18);
      if ( a2 == 2 )
      {
        v19 = (CRequestHitsArray *)(*((_QWORD *)a1 + 7) + 456LL);
      }
      else
      {
        if ( a2 != 3 )
          goto LABEL_25;
        v19 = (CRequestHitsArray *)(*((_QWORD *)a1 + 7) + 672LL);
      }
      if ( !(unsigned int)CRequestHitsArray::AddRequestHit(v19, Elem) )
        return 2147500037LL;
    }
LABEL_25:
    result = CRequestHit::AddValue(Elem, a2, v14, *(_QWORD *)(*((_QWORD *)a1 + 7) + 48LL), a4);
    if ( (int)result < 0 )
      return result;
    goto LABEL_26;
  }
  v11 = *(void **)(*((_QWORD *)a1 + 7) + 408LL);
  if ( v11 )
    HeapFree(g_hDenaliHeap, 0, v11);
  v12 = HeapAlloc(g_hDenaliHeap, 0, (int)v10);
  *(_QWORD *)(*((_QWORD *)a1 + 7) + 408LL) = v12;
  if ( v12 )
  {
    strcpy_s(*(char **)(*((_QWORD *)a1 + 7) + 408LL), (int)v10, v5);
    v5 = *(char **)(*((_QWORD *)a1 + 7) + 408LL);
    v20 = v5;
    goto LABEL_27;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18004ca64  mov     [rsp+arg_10], r8
0x18004ca69  push    rbx
0x18004ca6a  push    rbp
0x18004ca6b  push    rsi
0x18004ca6c  push    rdi
0x18004ca6d  push    r12
0x18004ca6f  push    r13
0x18004ca71  push    r14
0x18004ca73  push    r15
0x18004ca75  sub     rsp, 38h
0x18004ca79  mov     r15d, r9d
0x18004ca7c  mov     rdi, r8
0x18004ca7f  mov     r14d, edx
0x18004ca82  mov     rsi, rcx
0x18004ca85  call    ?CheckForTombstone@CRequest@@QEAAJXZ; CRequest::CheckForTombstone(void)
0x18004ca8a  xor     r13d, r13d
0x18004ca8d  test    eax, eax
0x18004ca8f  js      loc_18004CCC9
0x18004ca95  cmp     r14d, 4
0x18004ca99  jnz     short loc_18004CAAB
0x18004ca9b  mov     rdx, rdi; char *
0x18004ca9e  mov     rcx, rsi; this
0x18004caa1  call    ?LoadCookies@CRequest@@AEAAJPEAD@Z; CRequest::LoadCookies(char *)
0x18004caa6  jmp     loc_18004CCCE
0x18004caab  cmp     r14d, 5
0x18004caaf  jnz     short loc_18004CAC4
0x18004cab1  mov     r8d, r15d; unsigned int
0x18004cab4  mov     rdx, rdi; char *
0x18004cab7  mov     rcx, rsi; this
0x18004caba  call    ?LoadClCerts@CRequest@@AEAAJPEADI@Z; CRequest::LoadClCerts(char *,uint)
0x18004cabf  jmp     loc_18004CCCE
0x18004cac4  test    rdi, rdi
0x18004cac7  jz      loc_18004CCB2
0x18004cacd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004cad1  inc     rax
0x18004cad4  cmp     [rdi+rax], r13b
0x18004cad8  jnz     short loc_18004CAD1
0x18004cada  lea     ebp, [rax+1]
0x18004cadd  cmp     r14d, 2
0x18004cae1  jnz     loc_18004CCA9
0x18004cae7  mov     rax, [rsi+38h]
0x18004caeb  mov     r8, [rax+198h]; lpMem
0x18004caf2  test    r8, r8
0x18004caf5  jz      short loc_18004CB06
0x18004caf7  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18004cafe  xor     edx, edx; dwFlags
0x18004cb00  call    cs:__imp_HeapFree
0x18004cb06  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18004cb0d  xor     edx, edx; dwFlags
0x18004cb0f  movsxd  rbx, ebp
0x18004cb12  mov     r8, rbx; dwBytes
0x18004cb15  call    cs:__imp_HeapAlloc
0x18004cb1b  mov     rcx, [rsi+38h]
0x18004cb1f  mov     [rcx+198h], rax
0x18004cb26  test    rax, rax
0x18004cb29  jz      loc_18004CCDF
0x18004cb2f  mov     rcx, [rsi+38h]
0x18004cb33  mov     r8, rdi; Source
0x18004cb36  mov     rdx, rbx; SizeInBytes
0x18004cb39  mov     rcx, [rcx+198h]; Destination
0x18004cb40  call    cs:__imp_strcpy_s
0x18004cb46  mov     rax, [rsi+38h]
0x18004cb4a  mov     rdi, [rax+198h]
0x18004cb51  mov     [rsp+78h+arg_10], rdi
0x18004cb59  jmp     loc_18004CCA9
0x18004cb5e  mov     r9d, ebp
0x18004cb61  mov     [rsp+78h+var_58], r15d
0x18004cb66  mov     r8, rdi
0x18004cb69  lea     rdx, asc_180068F78; "="
0x18004cb70  lea     rcx, [rsp+78h+arg_10]
0x18004cb78  call    DecodeFromURL
0x18004cb7d  mov     r8, [rsp+78h+arg_10]
0x18004cb85  lea     rdx, asc_18006A4B8; "&"
0x18004cb8c  mov     r12d, edi
0x18004cb8f  mov     [rsp+78h+var_58], r15d
0x18004cb94  sub     r12d, r8d
0x18004cb97  lea     rcx, [rsp+78h+arg_10]
0x18004cb9f  add     r12d, ebp
0x18004cba2  mov     rbp, r8
0x18004cba5  mov     r9d, r12d
0x18004cba8  call    DecodeFromURL
0x18004cbad  cmp     [rdi], r13b
0x18004cbb0  jz      loc_18004CC9C
0x18004cbb6  mov     rcx, [rsi+38h]
0x18004cbba  add     rcx, 40h ; '@'; this
0x18004cbbe  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004cbc2  inc     r8; int
0x18004cbc5  cmp     [rdi+r8], r13b
0x18004cbc9  jnz     short loc_18004CBC2
0x18004cbcb  mov     rdx, rdi; void *
0x18004cbce  call    ?FindElem@CHashTable@@QEAAPEAUCLinkElem@@PEBXH@Z; CHashTable::FindElem(void const *,int)
0x18004cbd3  mov     rbx, rax
0x18004cbd6  test    rax, rax
0x18004cbd9  jnz     loc_18004CC7D
0x18004cbdf  mov     rcx, cs:?sm_pach@CRequestHit@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CRequestHit::sm_pach
0x18004cbe6  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18004cbec  mov     rbx, rax
0x18004cbef  test    rax, rax
0x18004cbf2  jz      loc_18004CCDF
0x18004cbf8  and     dword ptr [rbx+28h], 0FFFFFFFCh
0x18004cbfc  xor     r8d, r8d; int
0x18004cbff  mov     [rax+8], r13
0x18004cc03  mov     rdx, rdi; Source
0x18004cc06  mov     [rax+10h], r13d
0x18004cc0a  mov     rcx, rbx; this
0x18004cc0d  mov     [rax+14h], r13w
0x18004cc12  mov     [rax+18h], r13
0x18004cc16  mov     [rax+20h], r13
0x18004cc1a  lea     rax, ??_7CRequestHit@@6B@; const CRequestHit::`vftable'
0x18004cc21  mov     [rbx], rax
0x18004cc24  mov     [rbx+38h], r13
0x18004cc28  mov     [rbx+30h], r13
0x18004cc2c  mov     [rbx+40h], r13
0x18004cc30  mov     [rbx+48h], r13
0x18004cc34  call    ?Init@CRequestHit@@QEAAJPEADH@Z; CRequestHit::Init(char *,int)
0x18004cc39  test    eax, eax
0x18004cc3b  js      short loc_18004CCB6
0x18004cc3d  mov     rcx, [rsi+38h]
0x18004cc41  mov     rdx, rbx; struct CLinkElem *
0x18004cc44  add     rcx, 40h ; '@'; this
0x18004cc48  call    ?AddElem@CHashTable@@QEAAPEAUCLinkElem@@PEAU2@H@Z; CHashTable::AddElem(CLinkElem *,int)
0x18004cc4d  cmp     r14d, 2
0x18004cc51  jnz     short loc_18004CC60
0x18004cc53  mov     rcx, [rsi+38h]
0x18004cc57  add     rcx, 1C8h
0x18004cc5e  jmp     short loc_18004CC71
0x18004cc60  cmp     r14d, 3
0x18004cc64  jnz     short loc_18004CC7D
0x18004cc66  mov     rcx, [rsi+38h]
0x18004cc6a  add     rcx, 2A0h; this
0x18004cc71  mov     rdx, rbx; struct CRequestHit *
0x18004cc74  call    ?AddRequestHit@CRequestHitsArray@@QEAAHPEAVCRequestHit@@@Z; CRequestHitsArray::AddRequestHit(CRequestHit *)
0x18004cc79  test    eax, eax
0x18004cc7b  jz      short loc_18004CCC9
0x18004cc7d  mov     r9, [rsi+38h]
0x18004cc81  mov     r8, rbp
0x18004cc84  mov     edx, r14d
0x18004cc87  mov     [rsp+78h+var_58], r15d
0x18004cc8c  mov     rcx, rbx
0x18004cc8f  mov     r9, [r9+30h]
0x18004cc93  call    ?AddValue@CRequestHit@@QEAAJW4CollectionType@@PEADPEAVCIsapiReqInfo@@I@Z; CRequestHit::AddValue(CollectionType,char *,CIsapiReqInfo *,uint)
0x18004cc98  test    eax, eax
0x18004cc9a  js      short loc_18004CCCE
0x18004cc9c  mov     rdi, [rsp+78h+arg_10]
0x18004cca4  sub     ebp, edi
0x18004cca6  add     ebp, r12d
0x18004cca9  cmp     [rdi], r13b
0x18004ccac  jnz     loc_18004CB5E
0x18004ccb2  xor     eax, eax
0x18004ccb4  jmp     short loc_18004CCCE
0x18004ccb6  mov     rax, [rbx]
0x18004ccb9  mov     edx, 1
0x18004ccbe  mov     rcx, rbx
0x18004ccc1  mov     rax, [rax]
0x18004ccc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ccc9  mov     eax, 80004005h
0x18004ccce  add     rsp, 38h
0x18004ccd2  pop     r15
0x18004ccd4  pop     r14
0x18004ccd6  pop     r13
0x18004ccd8  pop     r12
0x18004ccda  pop     rdi
0x18004ccdb  pop     rsi
0x18004ccdc  pop     rbp
0x18004ccdd  pop     rbx
0x18004ccde  retn
0x18004ccdf  mov     eax, 8007000Eh
0x18004cce4  jmp     short loc_18004CCCE
```
