# CRequest::LoadCookies(char *)

- ea: `0x18004c610`
- end: `0x18004ca5d`
- name: `?LoadCookies@CRequest@@AEAAJPEAD@Z`
- size: `1101`
- prototype: `__int64 __fastcall(CRequest *__hidden this, char *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ca64`

## callees

- `0x180006ed4`
- `0x180007228`
- `0x180023d92`
- `0x18004a780`
- `0x18004a828`
- `0x18004a8f0`
- `0x18004ad4c`
- `0x18004b620`
- `0x18004be94`
- `0x18004c610`
- `0x180064010`

## import_xrefs

- `msvcrt!strchr` at `0x18004c73f`
- `msvcrt!strchr` at `0x18004c798`
- `msvcrt!strchr` at `0x18004c965`
- `msvcrt!strchr` at `0x18004ca0a`
- `msvcrt!strchr` at `0x18004c73f`
- `msvcrt!strchr` at `0x18004c798`
- `msvcrt!strchr` at `0x18004c965`
- `msvcrt!strchr` at `0x18004ca0a`
- `KERNEL32!HeapReAlloc` at `0x18004c68f`
- `KERNEL32!HeapReAlloc` at `0x18004c68f`
- `KERNEL32!HeapFree` at `0x18004c6b3`
- `KERNEL32!HeapFree` at `0x18004c6b3`
- `KERNEL32!HeapAlloc` at `0x18004c67d`
- `KERNEL32!HeapAlloc` at `0x18004c67d`
- `KERNEL32!GetACP` at `0x18004c714`
- `KERNEL32!GetACP` at `0x18004c76c`
- `KERNEL32!GetACP` at `0x18004c8aa`
- `KERNEL32!GetACP` at `0x18004c8fb`
- `KERNEL32!GetACP` at `0x18004c939`
- `KERNEL32!GetACP` at `0x18004c981`
- `KERNEL32!GetACP` at `0x18004c9d9`
- `KERNEL32!GetACP` at `0x18004c714`
- `KERNEL32!GetACP` at `0x18004c76c`
- `KERNEL32!GetACP` at `0x18004c8aa`
- `KERNEL32!GetACP` at `0x18004c8fb`
- `KERNEL32!GetACP` at `0x18004c939`
- `KERNEL32!GetACP` at `0x18004c981`
- `KERNEL32!GetACP` at `0x18004c9d9`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004c808`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004c808`

## pseudocode

```c
__int64 __fastcall CRequest::LoadCookies(CRequest *this, char *a2)
{
  __int64 result; // rax
  __int64 v5; // rbp
  __int64 v6; // r8
  int v7; // ebp
  unsigned __int64 v8; // rax
  LPVOID v9; // rax
  __int64 v10; // rcx
  void *v11; // r8
  CHAR *v12; // rsi
  char *v13; // r14
  UINT ACP; // eax
  signed __int8 v15; // bl
  char *v16; // rax
  int v17; // ebx
  const char *v18; // r12
  UINT v19; // eax
  signed __int8 v20; // r15
  char *v21; // rax
  __int64 v22; // r8
  struct CLinkElem *Elem; // rax
  struct CLinkElem *v24; // rbx
  struct CLinkElem *v25; // rax
  int v26; // r8d
  UINT v27; // eax
  UINT v28; // eax
  CHAR *v29; // r14
  UINT v30; // eax
  signed __int8 v31; // r15
  __int64 v32; // rdx
  UINT v33; // ecx
  int v34; // r13d
  UINT v35; // eax
  signed __int8 v36; // al
  char *v37; // rax
  signed __int8 *v38; // [rsp+88h] [rbp+10h] BYREF

  v38 = a2;
  if ( (int)CRequest::CheckForTombstone(this) < 0 )
    return 2147500037LL;
  if ( !a2 )
    return 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = *((_QWORD *)this + 7);
  v7 = v5 + 1;
  v8 = *(_QWORD *)(v6 + 384);
  if ( v7 <= v8 )
  {
LABEL_15:
    v12 = *(CHAR **)(*((_QWORD *)this + 7) + 376LL);
    if ( *a2 )
    {
      do
      {
        v13 = v12;
        ACP = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 56LL) + 164LL);
        if ( !ACP )
          ACP = GetACP();
        v15 = DecodeFromURL(&v38, ";=", v12, v7, ACP);
        v16 = strchr(v12, 0);
        v12 = v16 + 1;
        v7 += (_DWORD)v13 - ((_DWORD)v16 + 1);
        if ( v15 == 61 )
        {
          v17 = (_DWORD)v16 + 1;
          v18 = v16 + 1;
          v19 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 56LL) + 164LL);
          if ( !v19 )
            v19 = GetACP();
          v20 = DecodeFromURL(&v38, ";=", v12, v7, v19);
          v21 = strchr(v12, 0);
          v12 = v21 + 1;
          v7 = v17 + v7 - ((_DWORD)v21 + 1);
          if ( !strncmp_0(v13, "ASPSESSIONID", 0xCu) )
            continue;
        }
        else
        {
          if ( !*v13 )
            continue;
          v20 = 59;
          v18 = Str1;
        }
        v22 = -1;
        do
          ++v22;
        while ( v13[v22] );
        Elem = CHashTable::FindElem((CHashTable *)(*((_QWORD *)this + 7) + 64LL), v13, v22);
        v24 = Elem;
        if ( Elem )
        {
          if ( *((_QWORD *)Elem + 8) )
          {
            if ( v20 == 61 )
            {
              v28 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 56LL) + 164LL);
              if ( !v28 )
                v28 = GetACP();
              DecodeFromURL(&v38, ";", v12, v7, v28);
            }
            continue;
          }
        }
        else
        {
          v25 = (struct CLinkElem *)ALLOC_CACHE_HANDLER::Alloc(CRequestHit::sm_pach);
          v24 = v25;
          if ( !v25 )
            return 2147942414LL;
          *((_DWORD *)v25 + 10) &= 0xFFFFFFFC;
          *((_QWORD *)v25 + 1) = 0;
          *((_DWORD *)v25 + 4) = 0;
          *((_WORD *)v25 + 10) = 0;
          *((_QWORD *)v25 + 3) = 0;
          *((_QWORD *)v25 + 4) = 0;
          *(_QWORD *)v25 = &CRequestHit::`vftable';
          *((_QWORD *)v25 + 7) = 0;
          *((_QWORD *)v25 + 6) = 0;
          *((_QWORD *)v25 + 8) = 0;
          *((_QWORD *)v25 + 9) = 0;
          if ( (int)CRequestHit::Init(v25, v13, 0) < 0 )
          {
            (**(void (__fastcall ***)(struct CLinkElem *, __int64))v24)(v24, 1);
            return 2147500037LL;
          }
          CHashTable::AddElem((CHashTable *)(*((_QWORD *)this + 7) + 64LL), v24, v26);
          if ( !(unsigned int)CRequestHitsArray::AddRequestHit(
                                (CRequestHitsArray *)(*((_QWORD *)this + 7) + 784LL),
                                v24) )
            return 2147942414LL;
        }
        if ( v20 == 61 )
        {
          while ( 1 )
          {
            v29 = v12;
            v30 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 56LL) + 164LL);
            if ( !v30 )
              v30 = GetACP();
            v31 = DecodeFromURL(&v38, ";&", v12, v7, v30);
            v12 = strchr(v12, 0) + 1;
            v32 = *(_QWORD *)(*((_QWORD *)this + 7) + 56LL);
            v33 = *(_DWORD *)(v32 + 164);
            if ( !v33 )
              v33 = GetACP();
            result = CRequestHit::AddKeyAndValue(v24, v32, v18, v29, *(_QWORD *)(*((_QWORD *)this + 7) + 48LL), v33);
            if ( (int)result < 0 )
              return result;
            v34 = (int)v12;
            v7 += (_DWORD)v29 - (_DWORD)v12;
            if ( v31 == 59 || !v31 )
              goto LABEL_53;
            v18 = v12;
            v35 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 56LL) + 164LL);
            if ( !v35 )
              v35 = GetACP();
            v36 = DecodeFromURL(&v38, "=;", v12, v7, v35);
            if ( v36 == 59 || !v36 )
              goto LABEL_53;
            v37 = strchr(v12, 0);
            v12 = v37 + 1;
            v7 = v34 + v7 - ((_DWORD)v37 + 1);
          }
        }
        v27 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 56LL) + 164LL);
        if ( !v27 )
          v27 = GetACP();
        result = CRequestHit::AddValue(v24, 4, v18, *(_QWORD *)(*((_QWORD *)this + 7) + 48LL), v27);
        if ( (int)result < 0 )
          return result;
LABEL_53:
        ;
      }
      while ( *v38 );
    }
    return 0;
  }
  if ( v8 )
    v9 = HeapReAlloc(g_hDenaliHeap, 0, *(LPVOID *)(v6 + 376), v7);
  else
    v9 = HeapAlloc(g_hDenaliHeap, 0, v7);
  v10 = *((_QWORD *)this + 7);
  if ( v9 )
  {
    *(_QWORD *)(v10 + 376) = v9;
    *(_QWORD *)(*((_QWORD *)this + 7) + 384LL) = v7;
    goto LABEL_15;
  }
  v11 = *(void **)(v10 + 376);
  if ( v11 )
  {
    HeapFree(g_hDenaliHeap, 0, v11);
    *(_QWORD *)(*((_QWORD *)this + 7) + 376LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 7) + 384LL) = 0;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18004c610  mov     [rsp+arg_8], rdx
0x18004c615  push    rbx
0x18004c616  push    rbp
0x18004c617  push    rsi
0x18004c618  push    rdi
0x18004c619  push    r12
0x18004c61b  push    r13
0x18004c61d  push    r14
0x18004c61f  push    r15
0x18004c621  sub     rsp, 38h
0x18004c625  mov     rbx, rdx
0x18004c628  mov     rdi, rcx
0x18004c62b  call    ?CheckForTombstone@CRequest@@QEAAJXZ; CRequest::CheckForTombstone(void)
0x18004c630  xor     r13d, r13d
0x18004c633  test    eax, eax
0x18004c635  jns     short loc_18004C641
0x18004c637  mov     eax, 80004005h
0x18004c63c  jmp     loc_18004CA34
0x18004c641  test    rbx, rbx
0x18004c644  jz      loc_18004CA32
0x18004c64a  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18004c64e  inc     rbp
0x18004c651  cmp     [rbx+rbp], r13b
0x18004c655  jnz     short loc_18004C64E
0x18004c657  mov     r8, [rdi+38h]
0x18004c65b  inc     ebp
0x18004c65d  movsxd  rsi, ebp
0x18004c660  mov     rax, [r8+180h]
0x18004c667  cmp     rsi, rax
0x18004c66a  jbe     short loc_18004C6EB
0x18004c66c  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18004c673  xor     edx, edx; dwFlags
0x18004c675  test    rax, rax
0x18004c678  jnz     short loc_18004C685
0x18004c67a  mov     r8, rsi; dwBytes
0x18004c67d  call    cs:__imp_HeapAlloc
0x18004c683  jmp     short loc_18004C695
0x18004c685  mov     r8, [r8+178h]; lpMem
0x18004c68c  mov     r9, rsi; dwBytes
0x18004c68f  call    cs:__imp_HeapReAlloc
0x18004c695  mov     rcx, [rdi+38h]
0x18004c699  test    rax, rax
0x18004c69c  jnz     short loc_18004C6D9
0x18004c69e  mov     r8, [rcx+178h]; lpMem
0x18004c6a5  test    r8, r8
0x18004c6a8  jz      short loc_18004C6CF
0x18004c6aa  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18004c6b1  xor     edx, edx; dwFlags
0x18004c6b3  call    cs:__imp_HeapFree
0x18004c6b9  mov     rax, [rdi+38h]
0x18004c6bd  mov     [rax+178h], r13
0x18004c6c4  mov     rax, [rdi+38h]
0x18004c6c8  mov     [rax+180h], r13
0x18004c6cf  mov     eax, 8007000Eh
0x18004c6d4  jmp     loc_18004CA34
0x18004c6d9  mov     [rcx+178h], rax
0x18004c6e0  mov     rax, [rdi+38h]
0x18004c6e4  mov     [rax+180h], rsi
0x18004c6eb  mov     rax, [rdi+38h]
0x18004c6ef  mov     rsi, [rax+178h]
0x18004c6f6  cmp     [rbx], r13b
0x18004c6f9  jz      loc_18004CA32
0x18004c6ff  mov     rax, [rdi+38h]
0x18004c703  mov     r14, rsi
0x18004c706  mov     rcx, [rax+38h]
0x18004c70a  mov     eax, [rcx+0A4h]
0x18004c710  test    eax, eax
0x18004c712  jnz     short loc_18004C71A
0x18004c714  call    cs:__imp_GetACP
0x18004c71a  mov     r9d, ebp
0x18004c71d  mov     dword ptr [rsp+78h+var_58], eax
0x18004c721  mov     r8, rsi
0x18004c724  lea     rdx, asc_18006A4AC; ";="
0x18004c72b  lea     rcx, [rsp+78h+arg_8]
0x18004c733  call    DecodeFromURL
0x18004c738  xor     edx, edx; Val
0x18004c73a  mov     rcx, rsi; Str
0x18004c73d  mov     bl, al
0x18004c73f  call    cs:__imp_strchr
0x18004c745  mov     ecx, r14d
0x18004c748  lea     rsi, [rax+1]
0x18004c74c  sub     ecx, esi
0x18004c74e  add     ebp, ecx
0x18004c750  cmp     bl, 3Dh ; '='
0x18004c753  jnz     short loc_18004C7C5
0x18004c755  mov     rax, [rdi+38h]
0x18004c759  mov     ebx, esi
0x18004c75b  mov     r12, rsi
0x18004c75e  mov     rcx, [rax+38h]
0x18004c762  mov     eax, [rcx+0A4h]
0x18004c768  test    eax, eax
0x18004c76a  jnz     short loc_18004C772
0x18004c76c  call    cs:__imp_GetACP
0x18004c772  mov     r9d, ebp
0x18004c775  mov     dword ptr [rsp+78h+var_58], eax
0x18004c779  mov     r8, rsi
0x18004c77c  lea     rdx, asc_18006A4AC; ";="
0x18004c783  lea     rcx, [rsp+78h+arg_8]
0x18004c78b  call    DecodeFromURL
0x18004c790  xor     edx, edx; Val
0x18004c792  mov     rcx, rsi; Str
0x18004c795  mov     r15b, al
0x18004c798  call    cs:__imp_strchr
0x18004c79e  mov     r8d, 0Ch; MaxCount
0x18004c7a4  lea     rdx, aAspsessionid; "ASPSESSIONID"
0x18004c7ab  mov     rcx, r14; Str1
0x18004c7ae  lea     rsi, [rax+1]
0x18004c7b2  sub     ebp, esi
0x18004c7b4  add     ebp, ebx
0x18004c7b6  call    strncmp_0
0x18004c7bb  test    eax, eax
0x18004c7bd  jz      loc_18004CA21
0x18004c7c3  jmp     short loc_18004C7D8
0x18004c7c5  cmp     [r14], r13b
0x18004c7c8  jz      loc_18004CA21
0x18004c7ce  mov     r15b, 3Bh ; ';'
0x18004c7d1  lea     r12, Str1
0x18004c7d8  mov     rcx, [rdi+38h]
0x18004c7dc  add     rcx, 40h ; '@'; this
0x18004c7e0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004c7e4  inc     r8; int
0x18004c7e7  cmp     [r14+r8], r13b
0x18004c7eb  jnz     short loc_18004C7E4
0x18004c7ed  mov     rdx, r14; void *
0x18004c7f0  call    ?FindElem@CHashTable@@QEAAPEAUCLinkElem@@PEBXH@Z; CHashTable::FindElem(void const *,int)
0x18004c7f5  mov     rbx, rax
0x18004c7f8  test    rax, rax
0x18004c7fb  jnz     loc_18004C8D9
0x18004c801  mov     rcx, cs:?sm_pach@CRequestHit@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CRequestHit::sm_pach
0x18004c808  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18004c80e  mov     rbx, rax
0x18004c811  test    rax, rax
0x18004c814  jz      loc_18004C6CF
0x18004c81a  and     dword ptr [rbx+28h], 0FFFFFFFCh
0x18004c81e  xor     r8d, r8d; int
0x18004c821  mov     [rax+8], r13
0x18004c825  mov     rdx, r14; Source
0x18004c828  mov     [rax+10h], r13d
0x18004c82c  mov     rcx, rbx; this
0x18004c82f  mov     [rax+14h], r13w
0x18004c834  mov     [rax+18h], r13
0x18004c838  mov     [rax+20h], r13
0x18004c83c  lea     rax, ??_7CRequestHit@@6B@; const CRequestHit::`vftable'
0x18004c843  mov     [rbx], rax
0x18004c846  mov     [rbx+38h], r13
0x18004c84a  mov     [rbx+30h], r13
0x18004c84e  mov     [rbx+40h], r13
0x18004c852  mov     [rbx+48h], r13
0x18004c856  call    ?Init@CRequestHit@@QEAAJPEADH@Z; CRequestHit::Init(char *,int)
0x18004c85b  test    eax, eax
0x18004c85d  js      loc_18004CA45
0x18004c863  mov     rcx, [rdi+38h]
0x18004c867  mov     rdx, rbx; struct CLinkElem *
0x18004c86a  add     rcx, 40h ; '@'; this
0x18004c86e  call    ?AddElem@CHashTable@@QEAAPEAUCLinkElem@@PEAU2@H@Z; CHashTable::AddElem(CLinkElem *,int)
0x18004c873  mov     rcx, [rdi+38h]
0x18004c877  mov     rdx, rbx; struct CRequestHit *
0x18004c87a  add     rcx, 310h; this
0x18004c881  call    ?AddRequestHit@CRequestHitsArray@@QEAAHPEAVCRequestHit@@@Z; CRequestHitsArray::AddRequestHit(CRequestHit *)
0x18004c886  test    eax, eax
0x18004c888  jz      loc_18004C6CF
0x18004c88e  cmp     r15b, 3Dh ; '='
0x18004c892  jz      loc_18004C924
0x18004c898  mov     rax, [rdi+38h]
0x18004c89c  mov     rcx, [rax+38h]
0x18004c8a0  mov     eax, [rcx+0A4h]
0x18004c8a6  test    eax, eax
0x18004c8a8  jnz     short loc_18004C8B0
0x18004c8aa  call    cs:__imp_GetACP
0x18004c8b0  mov     r9, [rdi+38h]
0x18004c8b4  mov     r8, r12
0x18004c8b7  mov     edx, 4
0x18004c8bc  mov     dword ptr [rsp+78h+var_58], eax
0x18004c8c0  mov     rcx, rbx
0x18004c8c3  mov     r9, [r9+30h]
0x18004c8c7  call    ?AddValue@CRequestHit@@QEAAJW4CollectionType@@PEADPEAVCIsapiReqInfo@@I@Z; CRequestHit::AddValue(CollectionType,char *,CIsapiReqInfo *,uint)
0x18004c8cc  test    eax, eax
0x18004c8ce  js      loc_18004CA34
0x18004c8d4  jmp     loc_18004CA21
0x18004c8d9  cmp     [rax+40h], r13
0x18004c8dd  jz      short loc_18004C88E
0x18004c8df  cmp     r15b, 3Dh ; '='
0x18004c8e3  jnz     loc_18004CA21
0x18004c8e9  mov     rax, [rdi+38h]
0x18004c8ed  mov     rcx, [rax+38h]
0x18004c8f1  mov     eax, [rcx+0A4h]
0x18004c8f7  test    eax, eax
0x18004c8f9  jnz     short loc_18004C901
0x18004c8fb  call    cs:__imp_GetACP
0x18004c901  mov     r9d, ebp
0x18004c904  mov     dword ptr [rsp+78h+var_58], eax
0x18004c908  mov     r8, rsi
0x18004c90b  lea     rdx, asc_180069D44; ";"
0x18004c912  lea     rcx, [rsp+78h+arg_8]
0x18004c91a  call    DecodeFromURL
0x18004c91f  jmp     loc_18004CA21
0x18004c924  mov     rax, [rdi+38h]
0x18004c928  mov     r14, rsi
0x18004c92b  mov     rcx, [rax+38h]
0x18004c92f  mov     eax, [rcx+0A4h]
0x18004c935  test    eax, eax
0x18004c937  jnz     short loc_18004C93F
0x18004c939  call    cs:__imp_GetACP
0x18004c93f  mov     r9d, ebp
0x18004c942  mov     dword ptr [rsp+78h+var_58], eax
0x18004c946  mov     r8, rsi
0x18004c949  lea     rdx, asc_18006A4B0; ";&"
0x18004c950  lea     rcx, [rsp+78h+arg_8]
0x18004c958  call    DecodeFromURL
0x18004c95d  xor     edx, edx; Val
0x18004c95f  mov     rcx, rsi; Str
0x18004c962  mov     r15b, al
0x18004c965  call    cs:__imp_strchr
0x18004c96b  mov     rcx, [rdi+38h]
0x18004c96f  lea     rsi, [rax+1]
0x18004c973  mov     rdx, [rcx+38h]
0x18004c977  mov     ecx, [rdx+0A4h]
0x18004c97d  test    ecx, ecx
0x18004c97f  jnz     short loc_18004C989
0x18004c981  call    cs:__imp_GetACP
0x18004c987  mov     ecx, eax
0x18004c989  mov     rax, [rdi+38h]
0x18004c98d  mov     r9, r14
0x18004c990  mov     [rsp+78h+var_50], ecx
0x18004c994  mov     r8, r12
0x18004c997  mov     rcx, rbx
0x18004c99a  mov     rax, [rax+30h]
0x18004c99e  mov     [rsp+78h+var_58], rax
0x18004c9a3  call    ?AddKeyAndValue@CRequestHit@@QEAAJW4CollectionType@@PEAD1PEAVCIsapiReqInfo@@I@Z; CRequestHit::AddKeyAndValue(CollectionType,char *,char *,CIsapiReqInfo *,uint)
0x18004c9a8  test    eax, eax
0x18004c9aa  js      loc_18004CA34
0x18004c9b0  sub     r14d, esi
0x18004c9b3  mov     r13d, esi
0x18004c9b6  add     ebp, r14d
0x18004c9b9  cmp     r15b, 3Bh ; ';'
0x18004c9bd  jz      short loc_18004CA1E
0x18004c9bf  test    r15b, r15b
0x18004c9c2  jz      short loc_18004CA1E
0x18004c9c4  mov     rax, [rdi+38h]
0x18004c9c8  mov     r12, rsi
0x18004c9cb  mov     rcx, [rax+38h]
0x18004c9cf  mov     eax, [rcx+0A4h]
0x18004c9d5  test    eax, eax
0x18004c9d7  jnz     short loc_18004C9DF
0x18004c9d9  call    cs:__imp_GetACP
0x18004c9df  mov     r9d, ebp
0x18004c9e2  mov     dword ptr [rsp+78h+var_58], eax
0x18004c9e6  mov     r8, rsi
0x18004c9e9  lea     rdx, asc_18006A4B4; "=;"
0x18004c9f0  lea     rcx, [rsp+78h+arg_8]
0x18004c9f8  call    DecodeFromURL
0x18004c9fd  cmp     al, 3Bh ; ';'
0x18004c9ff  jz      short loc_18004CA1E
0x18004ca01  test    al, al
0x18004ca03  jz      short loc_18004CA1E
0x18004ca05  xor     edx, edx; Val
0x18004ca07  mov     rcx, rsi; Str
0x18004ca0a  call    cs:__imp_strchr
0x18004ca10  lea     rsi, [rax+1]
0x18004ca14  sub     ebp, esi
0x18004ca16  add     ebp, r13d
0x18004ca19  jmp     loc_18004C924
0x18004ca1e  xor     r13d, r13d
0x18004ca21  mov     rax, [rsp+78h+arg_8]
0x18004ca29  cmp     [rax], r13b
0x18004ca2c  jnz     loc_18004C6FF
0x18004ca32  xor     eax, eax
0x18004ca34  add     rsp, 38h
0x18004ca38  pop     r15
0x18004ca3a  pop     r14
0x18004ca3c  pop     r13
0x18004ca3e  pop     r12
0x18004ca40  pop     rdi
0x18004ca41  pop     rsi
0x18004ca42  pop     rbp
0x18004ca43  pop     rbx
0x18004ca44  retn
0x18004ca45  mov     rax, [rbx]
0x18004ca48  mov     edx, 1
0x18004ca4d  mov     rcx, rbx
0x18004ca50  mov     rax, [rax]
0x18004ca53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca58  jmp     loc_18004C637
```
