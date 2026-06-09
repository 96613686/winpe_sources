# EncodeEvents(_BrokeredQueryContext *,ulong *,ulong *,uchar * *)

- ea: `0x180001bfc`
- end: `0x180002082`
- name: `?EncodeEvents@@YAJPEAU_BrokeredQueryContext@@PEAK1PEAPEAE@Z`
- size: `1158`
- prototype: `__int64 __fastcall(struct _BrokeredQueryContext *, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002160`

## callees

- `0x180001bfc`
- `0x1800039a0`
- `0x180003a64`

## import_xrefs

- `msvcrt!_aligned_malloc` at `0x180001ef3`
- `msvcrt!_aligned_malloc` at `0x180001ef3`
- `msvcrt!_aligned_free` at `0x18000201f`
- `msvcrt!_aligned_free` at `0x180002032`
- `msvcrt!_aligned_free` at `0x18000201f`
- `msvcrt!_aligned_free` at `0x180002032`
- `RPCRT4!MesIncrementalHandleReset` at `0x180001c91`
- `RPCRT4!MesIncrementalHandleReset` at `0x180001f27`
- `RPCRT4!MesIncrementalHandleReset` at `0x180001c91`
- `RPCRT4!MesIncrementalHandleReset` at `0x180001f27`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x180001c57`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x180001c57`
- `RPCRT4!MesHandleFree` at `0x180002042`
- `RPCRT4!MesHandleFree` at `0x180002042`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x180001e9f`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x180001e9f`
- `RPCRT4!NdrMesTypeEncode3` at `0x180001f62`
- `RPCRT4!NdrMesTypeEncode3` at `0x180001f62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001cf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001da3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001cf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001da3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ce3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001d7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ce3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001d7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e13`

## pseudocode

```c
__int64 __fastcall EncodeEvents(
        struct _BrokeredQueryContext *a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  struct _QUERY_EVENT *v5; // r12
  RPC_STATUS v6; // eax
  signed int v7; // esi
  bool v8; // sf
  struct _BrokeredQueryContext *v9; // r8
  unsigned int v10; // r15d
  unsigned int v11; // r12d
  __int64 v12; // rbx
  struct _RTL_CRITICAL_SECTION *v13; // rdi
  char *v14; // rdx
  unsigned int v15; // ecx
  int v16; // eax
  unsigned int v17; // edi
  _QWORD *v18; // r12
  LPCRITICAL_SECTION v19; // rsi
  struct _RTL_CRITICAL_SECTION *v20; // rbx
  struct _RTL_CRITICAL_SECTION *DebugInfo; // r15
  __int64 v22; // rbx
  _QWORD *v23; // r15
  __int64 v24; // rdi
  _QWORD *v25; // rax
  _QWORD *v26; // rbx
  const struct _DEV_QUERY_RESULT_ACTION_DATA **v27; // rbx
  __int64 v28; // rdx
  unsigned int v29; // eax
  unsigned __int64 v30; // rcx
  unsigned int v31; // eax
  unsigned int v33; // [rsp+30h] [rbp-B8h]
  signed int v34; // [rsp+34h] [rbp-B4h]
  unsigned int v35; // [rsp+38h] [rbp-B0h]
  unsigned int v36; // [rsp+40h] [rbp-A8h]
  handle_t pHandle; // [rsp+48h] [rbp-A0h] BYREF
  const struct _DEV_QUERY_RESULT_ACTION_DATA **v38; // [rsp+50h] [rbp-98h]
  char *v39; // [rsp+58h] [rbp-90h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-88h]
  __int64 v41; // [rsp+68h] [rbp-80h]
  const struct _DEV_QUERY_RESULT_ACTION_DATA **v42; // [rsp+70h] [rbp-78h]
  __int128 UserState; // [rsp+78h] [rbp-70h] BYREF
  __int128 Block; // [rsp+88h] [rbp-60h]
  struct _BrokeredQueryContext *v45; // [rsp+98h] [rbp-50h]
  char *v46; // [rsp+A0h] [rbp-48h]

  UserState = 0;
  Block = 0;
  pHandle = 0;
  v5 = 0;
  *a3 = 0;
  *a4 = 0;
  v6 = MesEncodeIncrementalHandleCreate(&UserState, RpcSerializationAlloc, RpcSerializationWrite, &pHandle);
  v7 = v6;
  v8 = v6 < 0;
  if ( v6 || (v6 = MesIncrementalHandleReset(pHandle, &UserState, 0, 0, 0, MES_ENCODE), v7 = v6, v8 = v6 < 0, v6) )
  {
    if ( v8 )
      goto LABEL_43;
    goto LABEL_3;
  }
  v9 = a1;
  v45 = a1;
  v7 = 0;
  v34 = 0;
  v33 = 0;
  v35 = 0;
  v10 = 0;
  if ( *(_DWORD *)a1 )
  {
    v39 = (char *)a1 + 8;
    v11 = 0;
    do
    {
      v12 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 8LL * v10);
      v13 = (struct _RTL_CRITICAL_SECTION *)(v12 + 160);
      EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 160));
      LODWORD(v12) = *(_DWORD *)(v12 + 204);
      LeaveCriticalSection(v13);
      v11 += v12;
      ++v10;
    }
    while ( v10 < *(_DWORD *)a1 );
    v33 = v11;
    v5 = 0;
    v14 = v39;
    v9 = a1;
  }
  else
  {
    v14 = (char *)a1 + 8;
    v39 = (char *)a1 + 8;
  }
  v46 = v14;
  if ( v33 )
  {
    while ( 1 )
    {
      v15 = 0;
      v36 = 0;
      lpCriticalSection = (LPCRITICAL_SECTION)-1LL;
      v16 = 1;
      LODWORD(v38) = 1;
      v17 = 0;
      if ( *(_DWORD *)a1 )
        break;
      v23 = v14;
LABEL_24:
      v5 = 0;
      if ( v16 )
        goto LABEL_42;
      v41 = 8LL * v15;
      v24 = *(_QWORD *)(v41 + *v23);
      EnterCriticalSection((LPCRITICAL_SECTION)(v24 + 160));
      v25 = (_QWORD *)(v24 + 120);
      v26 = *(_QWORD **)(v24 + 120);
      if ( v26 == (_QWORD *)(v24 + 120) )
      {
        v27 = 0;
      }
      else
      {
        if ( (_QWORD *)v26[1] != v25 || (v28 = *v26, *(_QWORD **)(*v26 + 8LL) != v26) )
          __fastfail(3u);
        *v25 = v28;
        *(_QWORD *)(v28 + 8) = v25;
        v27 = (const struct _DEV_QUERY_RESULT_ACTION_DATA **)(v26 - 2);
        --*(_DWORD *)(v24 + 204);
      }
      v38 = v27;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v24 + 160));
      v5 = (struct _QUERY_EVENT *)v27;
      v42 = v27;
      if ( !DWORD2(UserState) )
      {
        v29 = NdrMesTypeAlignSize3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0, v27);
        v30 = v33 * (unsigned __int64)v29;
        v31 = v33 * v29;
        if ( v30 > 0xFFFFFFFF )
          v31 = -1;
        v7 = v30 > 0xFFFFFFFF ? 0x80070216 : 0;
        v34 = v7;
        if ( v30 > 0xFFFFFFFF )
          goto LABEL_43;
        HIDWORD(Block) = 0;
        *((_QWORD *)&UserState + 1) = v31;
        *(_QWORD *)&UserState = _aligned_malloc(v31, 0x10u);
        if ( !(_QWORD)UserState )
        {
          v7 = -2147024882;
          goto LABEL_43;
        }
        v6 = MesIncrementalHandleReset(pHandle, &UserState, 0, 0, 0, MES_ENCODE);
        if ( v6 )
        {
          if ( v6 < 0 )
          {
            v7 = v6;
            goto LABEL_43;
          }
LABEL_3:
          v7 = (unsigned __int16)v6 | 0x80010000;
          goto LABEL_43;
        }
      }
      NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0, v27);
      if ( v7 < 0 )
        goto LABEL_43;
      if ( HIDWORD(Block) )
      {
        CQuery::InsertEvent(*(CQuery **)(*v23 + v41), *v27, 1);
LABEL_42:
        *a2 = v35;
        *a3 = HIDWORD(UserState);
        *a4 = (unsigned __int8 *)UserState;
        goto LABEL_43;
      }
      ++v35;
      CQuery::FreeQueryEvent((struct _QUERY_EVENT *)v27);
      v14 = v39;
      v9 = v45;
    }
    v18 = (_QWORD *)((char *)v9 + 8);
    v19 = lpCriticalSection;
    while ( 1 )
    {
      v20 = *(struct _RTL_CRITICAL_SECTION **)(*v18 + 8LL * v17);
      lpCriticalSection = v20 + 4;
      EnterCriticalSection(v20 + 4);
      v41 = (__int64)&v20[3];
      DebugInfo = (struct _RTL_CRITICAL_SECTION *)v20[3].DebugInfo;
      v22 = DebugInfo == &v20[3] ? -1LL : DebugInfo[-1].SpinCount;
      LeaveCriticalSection(lpCriticalSection);
      if ( DebugInfo == (struct _RTL_CRITICAL_SECTION *)v41 )
        break;
      v16 = 0;
      LODWORD(v38) = 0;
      if ( v22 >= (__int64)v19 )
        goto LABEL_20;
      v19 = (LPCRITICAL_SECTION)v22;
      v15 = v17;
      v36 = v17;
LABEL_21:
      if ( ++v17 >= *(_DWORD *)a1 )
      {
        v7 = v34;
        v23 = v18;
        goto LABEL_24;
      }
    }
    v16 = (int)v38;
LABEL_20:
    v15 = v36;
    goto LABEL_21;
  }
LABEL_43:
  if ( v5 )
    CQuery::FreeQueryEvent(v5);
  if ( v7 < 0 && (_QWORD)UserState )
    _aligned_free((void *)UserState);
  if ( (_QWORD)Block )
    _aligned_free((void *)Block);
  if ( pHandle )
    MesHandleFree(pHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180001bfc  mov     rax, rsp
0x180001bff  mov     [rax+20h], r9
0x180001c03  mov     [rax+18h], r8
0x180001c07  mov     [rax+10h], rdx
0x180001c0b  mov     [rax+8], rcx
0x180001c0f  push    rbx
0x180001c10  push    rsi
0x180001c11  push    rdi
0x180001c12  push    r12
0x180001c14  push    r13
0x180001c16  push    r14
0x180001c18  push    r15
0x180001c1a  sub     rsp, 0B0h
0x180001c21  mov     r13, rcx
0x180001c24  xorps   xmm0, xmm0
0x180001c27  movups  xmmword ptr [rax-70h], xmm0
0x180001c2b  movups  xmmword ptr [rax-60h], xmm0
0x180001c2f  xor     r14d, r14d
0x180001c32  mov     [rsp+0E8h+pHandle], r14
0x180001c37  mov     r12d, r14d
0x180001c3a  mov     [r8], r14d
0x180001c3d  mov     [r9], r14
0x180001c40  lea     r9, [rsp+0E8h+pHandle]; pHandle
0x180001c45  lea     r8, ?RpcSerializationWrite@@YAXPEAXPEADI@Z; WriteFn
0x180001c4c  lea     rdx, ?RpcSerializationAlloc@@YAXPEAXPEAPEADPEAI@Z; AllocFn
0x180001c53  lea     rcx, [rax-70h]; UserState
0x180001c57  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x180001c5d  mov     esi, eax
0x180001c5f  test    eax, eax
0x180001c61  jz      short loc_180001C77
0x180001c63  js      loc_180002004
0x180001c69  movzx   esi, ax
0x180001c6c  or      esi, 80010000h
0x180001c72  jmp     loc_180002004
0x180001c77  mov     [rsp+0E8h+Operation], r14d; Operation
0x180001c7c  mov     [rsp+0E8h+ReadFn], r14; ReadFn
0x180001c81  xor     r9d, r9d; WriteFn
0x180001c84  xor     r8d, r8d; AllocFn
0x180001c87  lea     rdx, [rsp+0E8h+UserState]; UserState
0x180001c8c  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x180001c91  call    cs:__imp_MesIncrementalHandleReset
0x180001c97  mov     esi, eax
0x180001c99  test    eax, eax
0x180001c9b  jnz     short loc_180001C63
0x180001c9d  mov     r8, r13
0x180001ca0  mov     [rsp+0E8h+var_50], r13
0x180001ca8  mov     esi, r14d
0x180001cab  mov     [rsp+0E8h+var_B4], r14d
0x180001cb0  mov     [rsp+0E8h+var_B8], r14d
0x180001cb5  mov     [rsp+0E8h+var_B0], r14d
0x180001cba  mov     r15d, r14d
0x180001cbd  cmp     [r13+0], r14d
0x180001cc1  jbe     short loc_180001D19
0x180001cc3  lea     r14, [r13+8]
0x180001cc7  mov     [rsp+0E8h+var_90], r14
0x180001ccc  mov     r12d, r15d
0x180001ccf  mov     ecx, r15d
0x180001cd2  mov     rax, [r14]
0x180001cd5  mov     rbx, [rax+rcx*8]
0x180001cd9  lea     rdi, [rbx+0A0h]
0x180001ce0  mov     rcx, rdi; lpCriticalSection
0x180001ce3  call    cs:__imp_EnterCriticalSection
0x180001ce9  mov     ebx, [rbx+0CCh]
0x180001cef  mov     rcx, rdi; lpCriticalSection
0x180001cf2  call    cs:__imp_LeaveCriticalSection
0x180001cf8  add     r12d, ebx
0x180001cfb  inc     r15d
0x180001cfe  cmp     r15d, [r13+0]
0x180001d02  jb      short loc_180001CCF
0x180001d04  mov     [rsp+0E8h+var_B8], r12d
0x180001d09  xor     r14d, r14d
0x180001d0c  mov     r12d, r14d
0x180001d0f  mov     rdx, [rsp+0E8h+var_90]
0x180001d14  mov     r8, r13
0x180001d17  jmp     short loc_180001D22
0x180001d19  lea     rdx, [r13+8]
0x180001d1d  mov     [rsp+0E8h+var_90], rdx
0x180001d22  mov     [rsp+0E8h+var_48], rdx
0x180001d2a  cmp     [rsp+0E8h+var_B8], r14d
0x180001d2f  jz      loc_180002004
0x180001d35  mov     ecx, r14d
0x180001d38  mov     dword ptr [rsp+0E8h+var_A8], ecx
0x180001d3c  mov     [rsp+0E8h+lpCriticalSection], 0FFFFFFFFFFFFFFFFh
0x180001d45  mov     eax, 1
0x180001d4a  mov     dword ptr [rsp+0E8h+var_98], eax
0x180001d4e  mov     edi, r14d
0x180001d51  cmp     [r13+0], r14d
0x180001d55  jbe     loc_180001DE0
0x180001d5b  lea     r12, [r8+8]
0x180001d5f  mov     rsi, [rsp+0E8h+lpCriticalSection]
0x180001d64  mov     ecx, edi
0x180001d66  mov     rax, [r12]
0x180001d6a  mov     rbx, [rax+rcx*8]
0x180001d6e  lea     rax, [rbx+0A0h]
0x180001d75  mov     [rsp+0E8h+lpCriticalSection], rax
0x180001d7a  mov     rcx, rax; lpCriticalSection
0x180001d7d  call    cs:__imp_EnterCriticalSection
0x180001d83  lea     rax, [rbx+78h]
0x180001d87  mov     [rsp+0E8h+var_80], rax
0x180001d8c  mov     r15, [rax]
0x180001d8f  cmp     r15, rax
0x180001d92  jnz     short loc_180001D9A
0x180001d94  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180001d98  jmp     short loc_180001D9E
0x180001d9a  mov     rbx, [r15-8]
0x180001d9e  mov     rcx, [rsp+0E8h+lpCriticalSection]; lpCriticalSection
0x180001da3  call    cs:__imp_LeaveCriticalSection
0x180001da9  cmp     r15, [rsp+0E8h+var_80]
0x180001dae  jz      short loc_180001DC7
0x180001db0  mov     eax, r14d
0x180001db3  mov     dword ptr [rsp+0E8h+var_98], eax
0x180001db7  cmp     rbx, rsi
0x180001dba  jge     short loc_180001DCB
0x180001dbc  mov     rsi, rbx
0x180001dbf  mov     ecx, edi
0x180001dc1  mov     dword ptr [rsp+0E8h+var_A8], ecx
0x180001dc5  jmp     short loc_180001DCF
0x180001dc7  mov     eax, dword ptr [rsp+0E8h+var_98]
0x180001dcb  mov     ecx, dword ptr [rsp+0E8h+var_A8]
0x180001dcf  inc     edi
0x180001dd1  cmp     edi, [r13+0]
0x180001dd5  jb      short loc_180001D64
0x180001dd7  mov     esi, [rsp+0E8h+var_B4]
0x180001ddb  mov     r15, r12
0x180001dde  jmp     short loc_180001DE3
0x180001de0  mov     r15, rdx
0x180001de3  mov     [rsp+0E8h+var_A8], r15
0x180001de8  mov     r12, r14
0x180001deb  test    eax, eax
0x180001ded  jnz     loc_180001FD5
0x180001df3  mov     eax, ecx
0x180001df5  lea     rcx, ds:0[rax*8]
0x180001dfd  mov     [rsp+0E8h+var_80], rcx
0x180001e02  mov     rax, [r15]
0x180001e05  mov     rdi, [rcx+rax]
0x180001e09  lea     r12, [rdi+0A0h]
0x180001e10  mov     rcx, r12; lpCriticalSection
0x180001e13  call    cs:__imp_EnterCriticalSection
0x180001e19  lea     rax, [rdi+78h]
0x180001e1d  mov     rbx, [rax]
0x180001e20  cmp     rbx, rax
0x180001e23  jnz     short loc_180001E2A
0x180001e25  mov     rbx, r14
0x180001e28  jmp     short loc_180001E57
0x180001e2a  cmp     [rbx+8], rax
0x180001e2e  jnz     loc_18000207B
0x180001e34  mov     rdx, [rbx]
0x180001e37  cmp     [rdx+8], rbx
0x180001e3b  jnz     loc_18000207B
0x180001e41  mov     [rax], rdx
0x180001e44  mov     [rdx+8], rax
0x180001e48  add     rbx, 0FFFFFFFFFFFFFFF0h
0x180001e4c  mov     eax, 0FFFFFFFFh
0x180001e51  add     [rdi+0CCh], eax
0x180001e57  mov     [rsp+0E8h+var_98], rbx
0x180001e5c  mov     rcx, r12; lpCriticalSection
0x180001e5f  call    cs:__imp_LeaveCriticalSection
0x180001e65  mov     r12, rbx
0x180001e68  mov     [rsp+0E8h+var_78], rbx
0x180001e6d  cmp     [rsp+0E8h+var_68], r14d
0x180001e75  jnz     loc_180001F3E
0x180001e7b  mov     qword ptr [rsp+0E8h+Operation], rbx; pObject
0x180001e80  mov     dword ptr [rsp+0E8h+ReadFn], r14d; nTypeIndex
0x180001e85  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180001e8c  lea     r8, pProxyInfo; pProxyInfo
0x180001e93  lea     rdx, pPicklingInfo; pPicklingInfo
0x180001e9a  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x180001e9f  call    cs:__imp_NdrMesTypeAlignSize3
0x180001ea5  mov     ecx, eax
0x180001ea7  mov     eax, [rsp+0E8h+var_B8]
0x180001eab  imul    rcx, rax
0x180001eaf  mov     edi, 0FFFFFFFFh
0x180001eb4  cmp     rcx, rdi
0x180001eb7  mov     eax, ecx
0x180001eb9  jbe     short loc_180001EBD
0x180001ebb  mov     eax, edi
0x180001ebd  cmp     rdi, rcx
0x180001ec0  sbb     esi, esi
0x180001ec2  and     esi, 80070216h
0x180001ec8  mov     [rsp+0E8h+var_B4], esi
0x180001ecc  cmp     rcx, rdi
0x180001ecf  ja      loc_180002004
0x180001ed5  mov     [rsp+0E8h+var_54], r14d
0x180001edd  mov     [rsp+0E8h+var_64], r14d
0x180001ee5  mov     [rsp+0E8h+var_68], eax
0x180001eec  mov     ecx, eax; Size
0x180001eee  mov     edx, 10h; Alignment
0x180001ef3  call    cs:__imp__aligned_malloc
0x180001ef9  mov     [rsp+0E8h+UserState], rax
0x180001efe  test    rax, rax
0x180001f01  jnz     short loc_180001F0D
0x180001f03  mov     esi, 8007000Eh
0x180001f08  jmp     loc_180002004
0x180001f0d  mov     [rsp+0E8h+Operation], r14d; Operation
0x180001f12  mov     [rsp+0E8h+ReadFn], r14; ReadFn
0x180001f17  xor     r9d, r9d; WriteFn
0x180001f1a  xor     r8d, r8d; AllocFn
0x180001f1d  lea     rdx, [rsp+0E8h+UserState]; UserState
0x180001f22  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x180001f27  call    cs:__imp_MesIncrementalHandleReset
0x180001f2d  test    eax, eax
0x180001f2f  jz      short loc_180001F3E
0x180001f31  jns     loc_180001C69
0x180001f37  mov     esi, eax
0x180001f39  jmp     loc_180002004
0x180001f3e  mov     qword ptr [rsp+0E8h+Operation], rbx; pObject
0x180001f43  mov     dword ptr [rsp+0E8h+ReadFn], r14d; nTypeIndex
0x180001f48  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180001f4f  lea     r8, pProxyInfo; pProxyInfo
0x180001f56  lea     rdx, pPicklingInfo; pPicklingInfo
0x180001f5d  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x180001f62  call    cs:__imp_NdrMesTypeEncode3
0x180001f68  jmp     short loc_180001FA9
0x180001f6a  mov     esi, eax
0x180001f6c  mov     [rsp+0E8h+var_B4], eax
0x180001f70  cmp     eax, 1
0x180001f73  jl      short loc_180001F82
0x180001f75  movzx   esi, ax
0x180001f78  or      esi, 80010000h
0x180001f7e  mov     [rsp+0E8h+var_B4], esi
0x180001f82  xor     r14d, r14d
0x180001f85  mov     r13, [rsp+0E8h+arg_0]
0x180001f8d  mov     r12, [rsp+0E8h+var_78]
0x180001f92  mov     rbx, [rsp+0E8h+var_98]
0x180001f97  mov     rax, [rsp+0E8h+var_48]
0x180001f9f  mov     [rsp+0E8h+var_90], rax
0x180001fa4  mov     r15, [rsp+0E8h+var_A8]
0x180001fa9  test    esi, esi
0x180001fab  js      short loc_180002004
0x180001fad  cmp     [rsp+0E8h+var_54], r14d
0x180001fb5  jz      loc_18000205D
0x180001fbb  mov     rcx, [r15]
0x180001fbe  mov     r8d, 1; int
0x180001fc4  mov     rdx, [rbx]; struct _DEV_QUERY_RESULT_ACTION_DATA *
0x180001fc7  mov     rax, [rsp+0E8h+var_80]
0x180001fcc  mov     rcx, [rcx+rax]; this
0x180001fd0  call    ?InsertEvent@CQuery@@QEAAJPEBU_DEV_QUERY_RESULT_ACTION_DATA@@H@Z; CQuery::InsertEvent(_DEV_QUERY_RESULT_ACTION_DATA const *,int)
0x180001fd5  mov     eax, [rsp+0E8h+var_B0]
0x180001fd9  mov     rcx, [rsp+0E8h+arg_8]
0x180001fe1  mov     [rcx], eax
0x180001fe3  mov     eax, [rsp+0E8h+var_64]
0x180001fea  mov     rcx, [rsp+0E8h+arg_10]
0x180001ff2  mov     [rcx], eax
0x180001ff4  mov     rax, [rsp+0E8h+UserState]
0x180001ff9  mov     rcx, [rsp+0E8h+arg_18]
0x180002001  mov     [rcx], rax
0x180002004  test    r12, r12
0x180002007  jz      short loc_180002011
0x180002009  mov     rcx, r12; Block
0x18000200c  call    ?FreeQueryEvent@CQuery@@SAXPEAU_QUERY_EVENT@@@Z; CQuery::FreeQueryEvent(_QUERY_EVENT *)
0x180002011  test    esi, esi
0x180002013  jns     short loc_180002025
0x180002015  mov     rcx, [rsp+0E8h+UserState]; Block
0x18000201a  test    rcx, rcx
0x18000201d  jz      short loc_180002025
0x18000201f  call    cs:__imp__aligned_free
0x180002025  mov     rcx, [rsp+0E8h+Block]; Block
0x18000202d  test    rcx, rcx
0x180002030  jz      short loc_180002038
0x180002032  call    cs:__imp__aligned_free
0x180002038  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x18000203d  test    rcx, rcx
0x180002040  jz      short loc_180002048
0x180002042  call    cs:__imp_MesHandleFree
0x180002048  mov     eax, esi
0x18000204a  add     rsp, 0B0h
0x180002051  pop     r15
0x180002053  pop     r14
0x180002055  pop     r13
0x180002057  pop     r12
0x180002059  pop     rdi
0x18000205a  pop     rsi
0x18000205b  pop     rbx
0x18000205c  retn
0x18000205d  inc     [rsp+0E8h+var_B0]
0x180002061  mov     rcx, rbx; Block
0x180002064  call    ?FreeQueryEvent@CQuery@@SAXPEAU_QUERY_EVENT@@@Z; CQuery::FreeQueryEvent(_QUERY_EVENT *)
0x180002069  mov     rdx, [rsp+0E8h+var_90]
0x18000206e  mov     r8, [rsp+0E8h+var_50]
0x180002076  jmp     loc_180001D35
0x18000207b  mov     ecx, 3
0x180002080  int     29h; Win8: RtlFailFast(ecx)
0x18000a5b7  push    rbp
0x18000a5b9  sub     rsp, 30h
0x18000a5bd  mov     rbp, rdx
0x18000a5c0  mov     rcx, [rcx]
0x18000a5c3  mov     ecx, [rcx]; ExceptionCode
0x18000a5c5  call    cs:__imp_RpcExceptionFilter
0x18000a5cb  nop
0x18000a5cc  add     rsp, 30h
0x18000a5d0  pop     rbp
0x18000a5d1  retn
```
