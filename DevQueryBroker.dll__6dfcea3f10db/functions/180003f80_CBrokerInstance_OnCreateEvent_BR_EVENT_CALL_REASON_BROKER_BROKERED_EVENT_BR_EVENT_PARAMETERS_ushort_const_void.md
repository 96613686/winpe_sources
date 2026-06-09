# CBrokerInstance::OnCreateEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,_BR_EVENT_PARAMETERS *,ushort const *,void *,void *,void *,void * *,ulong *,_BR_NEW_EVENT_INFORMATION *)

- ea: `0x180003f80`
- end: `0x1800043d9`
- name: `?OnCreateEvent@CBrokerInstance@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAU_BR_EVENT_PARAMETERS@@PEBGPEAX55PEAPEAXPEAKPEAU_BR_NEW_EVENT_INFORMATION@@@Z`
- size: `1113`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned __int16 *, __int64, __int64, __int64, __int64, struct _BrokeredQueryContext **, _DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18000314c`
- `0x18000383c`
- `0x180003f80`
- `0x1800044e0`
- `0x1800046e4`
- `0x18000a19e`
- `0x18000a1aa`
- `0x18000a1d0`

## import_xrefs

- `msvcrt!malloc` at `0x180004143`
- `msvcrt!malloc` at `0x18000416e`
- `msvcrt!malloc` at `0x180004143`
- `msvcrt!malloc` at `0x18000416e`
- `RPCRT4!UuidCompare` at `0x1800040ea`
- `RPCRT4!UuidCompare` at `0x1800040ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800041ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800041ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000418e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000418e`

## string_xrefs

- `0x18000407a`: `Update`
- `0x180004096`: `Remove`

## pseudocode

```c
__int64 __fastcall CBrokerInstance::OnCreateEvent(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        struct _BrokeredQueryContext **a9,
        _DWORD *a10,
        _DWORD *a11)
{
  UUID *v11; // rcx
  unsigned int v12; // ebx
  unsigned int v13; // edi
  int v14; // r12d
  unsigned int v15; // r14d
  unsigned __int16 *v16; // r13
  unsigned int v17; // eax
  unsigned int i; // r15d
  __int64 v19; // rsi
  __int64 v20; // rbx
  const wchar_t *v21; // rdi
  int v22; // ebx
  char *v24; // rax
  char *v25; // rsi
  struct _BrokeredQueryContext *v26; // rax
  struct _BrokeredQueryContext *v27; // rdi
  _QWORD *v28; // rcx
  unsigned int v29; // ecx
  unsigned int v30; // r14d
  __int64 v31; // r15
  __int64 v32; // rdi
  unsigned int v33; // ecx
  char *v34; // rdx
  unsigned int v35; // r13d
  struct _DEVPROP_FILTER_EXPRESSION *v36; // r12
  unsigned int v37; // r15d
  unsigned __int16 **v38; // rdi
  unsigned int v39; // ebx
  __int64 v40; // rax
  struct _DEVPROPCOMPKEY *v41; // r14
  char *v42; // rcx
  unsigned int v43; // esi
  unsigned int v44; // eax
  _DWORD *v45; // rax
  unsigned int v46; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v47; // [rsp+84h] [rbp-7Ch] BYREF
  int v48; // [rsp+88h] [rbp-78h] BYREF
  RPC_STATUS Status; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v50; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v51; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v52; // [rsp+98h] [rbp-68h] BYREF
  int v53; // [rsp+9Ch] [rbp-64h]
  unsigned int v54; // [rsp+A0h] [rbp-60h]
  UUID *v55; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v56; // [rsp+B0h] [rbp-50h] BYREF
  struct _DEV_QUERY_PARAMETER *v57; // [rsp+B8h] [rbp-48h] BYREF
  struct _BrokeredQueryContext *v58; // [rsp+C0h] [rbp-40h]
  struct _DEVPROP_FILTER_EXPRESSION *v59; // [rsp+C8h] [rbp-38h] BYREF
  struct _DEVPROPCOMPKEY *v60; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 **v61; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v62; // [rsp+E0h] [rbp-20h]
  __int64 v63; // [rsp+E8h] [rbp-18h]
  char *v64; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v65; // [rsp+F8h] [rbp-8h]
  struct _BrokeredQueryContext **v66; // [rsp+100h] [rbp+0h]
  _DWORD *v67; // [rsp+108h] [rbp+8h]
  _DWORD *v68; // [rsp+110h] [rbp+10h]
  UUID v69; // [rsp+120h] [rbp+20h] BYREF
  UUID Uuid1; // [rsp+130h] [rbp+30h] BYREF

  v11 = 0;
  v67 = a11;
  v12 = 0;
  v13 = 0;
  v66 = a9;
  v14 = 0;
  v15 = 0;
  v68 = a10;
  v65 = a4;
  v16 = a4;
  v62 = a3;
  v63 = a2;
  v46 = 0;
  v47 = 0;
  v55 = 0;
  Status = 0;
  Uuid1 = 0;
  if ( a4 )
  {
    v17 = *a4;
    for ( i = 0; i < v17; ++i )
    {
      v19 = *((_QWORD *)v16 + 1);
      v20 = 32LL * i;
      v21 = *(const wchar_t **)(v20 + v19);
      if ( !v21 )
        return (unsigned int)-2147024809;
      if ( !wcscmp_0(*(const wchar_t **)(v20 + v19), L"Context") )
      {
        if ( *(_DWORD *)(v20 + v19 + 8) != 4 || *(_WORD *)(v20 + v19 + 16) != 16 )
          return (unsigned int)-2147024809;
        v55 = *(UUID **)(v20 + v19 + 24);
      }
      else if ( !wcscmp_0(v21, L"Add") )
      {
        v14 = 1;
      }
      else if ( !wcscmp_0(v21, L"Update") )
      {
        v46 = 1;
      }
      else if ( !wcscmp_0(v21, L"Remove") )
      {
        v47 = 1;
      }
      else if ( !wcscmp_0(v21, L"DevQueryParamBlob") )
      {
        ++v15;
      }
      v17 = *v16;
    }
    v12 = v46;
    v13 = v47;
    v11 = v55;
  }
  if ( !UuidCompare(&Uuid1, v11, &Status) || Status || !v15 || !v14 && !v12 && !v13 )
    return (unsigned int)-2147024809;
  v24 = (char *)malloc(8LL * v15);
  v64 = v24;
  v25 = v24;
  if ( !v24 )
    return (unsigned int)-2147024882;
  memset_0(v24, 0, 8LL * v15);
  v26 = (struct _BrokeredQueryContext *)malloc(0x20u);
  v58 = v26;
  if ( (v27 = v26) == 0 )
    return (unsigned int)-2147024882;
  *(_DWORD *)v26 = v15;
  *((_QWORD *)v26 + 1) = v25;
  EnterCriticalSection(&g_csActiveQueriesList);
  v28 = (_QWORD *)qword_180011870;
  if ( *(struct _LIST_ENTRY **)qword_180011870 != &g_activeQueriesList )
    __fastfail(3u);
  *((_QWORD *)v27 + 3) = qword_180011870;
  *((_QWORD *)v27 + 2) = &g_activeQueriesList;
  *v28 = (char *)v27 + 16;
  qword_180011870 = (__int64)v27 + 16;
  LeaveCriticalSection(&g_csActiveQueriesList);
  v29 = 0;
  v22 = 0;
  v30 = 0;
  v54 = 0;
  v53 = 0;
  if ( !*v16 )
  {
LABEL_39:
    *v66 = v27;
    v45 = v67;
    *v67 = 0;
    v45[2] = 0;
    *v68 = 1;
    if ( v22 < 0 )
      goto LABEL_42;
    return (unsigned int)v22;
  }
  while ( 1 )
  {
    v31 = *((_QWORD *)v16 + 1);
    v32 = 32LL * v29;
    if ( !wcscmp_0(*(const wchar_t **)(v32 + v31), L"DevQueryParamBlob") )
      break;
LABEL_37:
    v44 = *v16;
    v29 = v54 + 1;
    v54 = v29;
    if ( v29 >= v44 )
    {
      v27 = v58;
      goto LABEL_39;
    }
  }
  v33 = *(unsigned __int16 *)(v32 + v31 + 16);
  v34 = *(char **)(v32 + v31 + 24);
  v48 = 0;
  v52 = 0;
  v51 = 0;
  v61 = 0;
  v50 = 0;
  v60 = 0;
  v46 = 0;
  v59 = 0;
  v47 = 0;
  v57 = 0;
  v56 = 0;
  v22 = DecodeDevQueryParamsBlob(
          v33,
          v34,
          (enum _DEV_OBJECT_TYPE *)&v48,
          &v52,
          &v51,
          &v61,
          &v50,
          &v60,
          &v46,
          &v59,
          &v47,
          &v57,
          &v56);
  if ( v22 >= 0 )
  {
    v35 = v47;
    v36 = v59;
    v37 = v46;
    v38 = v61;
    v39 = v51;
    v40 = v30;
    v41 = v60;
    v69 = *v55;
    v42 = &v25[8 * v40];
    v43 = v50;
    v48 = CQuery::Create(v63, v62, (unsigned int)v48, v52, v51, v61, v50, v60, v46, v59, v47, v57, v56, &v69, v42);
    FreeDecodedDevQueryParams(v39, v38, v43, v41, v37, v36, v35, v57, v56);
    v22 = v48;
    if ( v48 >= 0 )
    {
      v25 = v64;
      v30 = v53 + 1;
      v16 = v65;
      ++v53;
      goto LABEL_37;
    }
  }
  v27 = v58;
LABEL_42:
  if ( v27 )
    CActiveQueries::RemoveBrokeredQueryContext(v27);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180003f80  push    rbp
0x180003f82  push    rbx
0x180003f83  push    rsi
0x180003f84  push    rdi
0x180003f85  push    r12
0x180003f87  push    r13
0x180003f89  push    r14
0x180003f8b  push    r15
0x180003f8d  lea     rbp, [rsp-58h]
0x180003f92  sub     rsp, 158h
0x180003f99  mov     rax, cs:__security_cookie
0x180003fa0  xor     rax, rsp
0x180003fa3  mov     [rbp+90h+var_50], rax
0x180003fa7  mov     rax, [rbp+90h+arg_50]
0x180003fae  xor     ecx, ecx
0x180003fb0  mov     [rbp+90h+var_88], rax
0x180003fb4  xor     ebx, ebx
0x180003fb6  mov     rax, [rbp+90h+arg_40]
0x180003fbd  xor     edi, edi
0x180003fbf  mov     [rbp+90h+var_90], rax
0x180003fc3  xor     r12d, r12d
0x180003fc6  mov     rax, [rbp+90h+arg_48]
0x180003fcd  xor     r14d, r14d
0x180003fd0  mov     [rbp+90h+var_80], rax
0x180003fd4  xorps   xmm0, xmm0
0x180003fd7  mov     [rbp+90h+var_98], r9
0x180003fdb  mov     r13, r9
0x180003fde  mov     [rbp+90h+var_B0], r8
0x180003fe2  mov     [rbp+90h+var_A8], rdx
0x180003fe6  mov     [rbp+90h+var_110], ebx
0x180003fe9  mov     [rbp+90h+var_10C], edi
0x180003fec  mov     [rbp+90h+var_E8], rcx
0x180003ff0  mov     [rbp+90h+Status], ecx
0x180003ff3  movups  xmmword ptr [rbp+90h+Uuid1.Data1], xmm0
0x180003ff7  test    r9, r9
0x180003ffa  jz      loc_1800040DF
0x180004000  movzx   eax, word ptr [r9]
0x180004004  xor     r15d, r15d
0x180004007  cmp     r15d, eax
0x18000400a  jnb     loc_1800040D5
0x180004010  mov     rsi, [r13+8]
0x180004014  mov     ebx, r15d
0x180004017  shl     rbx, 5
0x18000401b  mov     rdi, [rbx+rsi]
0x18000401f  test    rdi, rdi
0x180004022  jz      loc_18000410F
0x180004028  lea     rdx, aContext; "Context"
0x18000402f  mov     rcx, rdi; String1
0x180004032  call    wcscmp_0
0x180004037  test    eax, eax
0x180004039  jnz     short loc_180004061
0x18000403b  cmp     dword ptr [rbx+rsi+8], 4
0x180004040  jnz     loc_18000410F
0x180004046  mov     eax, 10h
0x18000404b  cmp     ax, [rbx+rsi+10h]
0x180004050  jnz     loc_18000410F
0x180004056  mov     rax, [rbx+rsi+18h]
0x18000405b  mov     [rbp+90h+var_E8], rax
0x18000405f  jmp     short loc_1800040C8
0x180004061  lea     rdx, aAdd; "Add"
0x180004068  mov     rcx, rdi; String1
0x18000406b  call    wcscmp_0
0x180004070  test    eax, eax
0x180004072  jnz     short loc_18000407A
0x180004074  lea     r12d, [rax+1]
0x180004078  jmp     short loc_1800040C8
0x18000407a  lea     rdx, aUpdate; "Update"
0x180004081  mov     rcx, rdi; String1
0x180004084  call    wcscmp_0
0x180004089  test    eax, eax
0x18000408b  jnz     short loc_180004096
0x18000408d  mov     [rbp+90h+var_110], 1
0x180004094  jmp     short loc_1800040C8
0x180004096  lea     rdx, aRemove; "Remove"
0x18000409d  mov     rcx, rdi; String1
0x1800040a0  call    wcscmp_0
0x1800040a5  test    eax, eax
0x1800040a7  jnz     short loc_1800040B2
0x1800040a9  mov     [rbp+90h+var_10C], 1
0x1800040b0  jmp     short loc_1800040C8
0x1800040b2  lea     rdx, aDevqueryparamb; "DevQueryParamBlob"
0x1800040b9  mov     rcx, rdi; String1
0x1800040bc  call    wcscmp_0
0x1800040c1  test    eax, eax
0x1800040c3  jnz     short loc_1800040C8
0x1800040c5  inc     r14d
0x1800040c8  movzx   eax, word ptr [r13+0]
0x1800040cd  inc     r15d
0x1800040d0  jmp     loc_180004007
0x1800040d5  mov     ebx, [rbp+90h+var_110]
0x1800040d8  mov     edi, [rbp+90h+var_10C]
0x1800040db  mov     rcx, [rbp+90h+var_E8]
0x1800040df  mov     rdx, rcx; Uuid2
0x1800040e2  lea     r8, [rbp+90h+Status]; Status
0x1800040e6  lea     rcx, [rbp+90h+Uuid1]; Uuid1
0x1800040ea  call    cs:__imp_UuidCompare
0x1800040f0  test    eax, eax
0x1800040f2  jz      short loc_18000410F
0x1800040f4  cmp     [rbp+90h+Status], 0
0x1800040f8  jnz     short loc_18000410F
0x1800040fa  test    r14d, r14d
0x1800040fd  jz      short loc_18000410F
0x1800040ff  test    r12d, r12d
0x180004102  jnz     short loc_180004136
0x180004104  xor     r12d, r12d
0x180004107  test    ebx, ebx
0x180004109  jnz     short loc_180004139
0x18000410b  test    edi, edi
0x18000410d  jnz     short loc_180004139
0x18000410f  mov     ebx, 80070057h
0x180004114  mov     eax, ebx
0x180004116  mov     rcx, [rbp+90h+var_50]
0x18000411a  xor     rcx, rsp; StackCookie
0x18000411d  call    __security_check_cookie
0x180004122  add     rsp, 158h
0x180004129  pop     r15
0x18000412b  pop     r14
0x18000412d  pop     r13
0x18000412f  pop     r12
0x180004131  pop     rdi
0x180004132  pop     rsi
0x180004133  pop     rbx
0x180004134  pop     rbp
0x180004135  retn
0x180004136  xor     r12d, r12d
0x180004139  mov     ebx, r14d
0x18000413c  shl     rbx, 3
0x180004140  mov     rcx, rbx; Size
0x180004143  call    cs:__imp_malloc
0x180004149  mov     [rbp+90h+var_A0], rax
0x18000414d  mov     rsi, rax
0x180004150  test    rax, rax
0x180004153  jnz     short loc_18000415C
0x180004155  mov     ebx, 8007000Eh
0x18000415a  jmp     short loc_180004114
0x18000415c  mov     r8, rbx; Size
0x18000415f  xor     edx, edx; Val
0x180004161  mov     rcx, rsi; void *
0x180004164  call    memset_0
0x180004169  mov     ecx, 20h ; ' '; Size
0x18000416e  call    cs:__imp_malloc
0x180004174  mov     [rbp+90h+var_D0], rax
0x180004178  mov     rdi, rax
0x18000417b  test    rax, rax
0x18000417e  jz      short loc_180004155
0x180004180  lea     rcx, ?g_csActiveQueriesList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004187  mov     [rax], r14d
0x18000418a  mov     [rax+8], rsi
0x18000418e  call    cs:__imp_EnterCriticalSection
0x180004194  mov     rcx, cs:qword_180011870
0x18000419b  lea     rdx, ?g_activeQueriesList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_activeQueriesList
0x1800041a2  cmp     [rcx], rdx
0x1800041a5  jz      short loc_1800041AE
0x1800041a7  mov     ecx, 3
0x1800041ac  int     29h; Win8: RtlFailFast(ecx)
0x1800041ae  lea     rax, [rdi+10h]
0x1800041b2  mov     [rax+8], rcx
0x1800041b6  mov     [rax], rdx
0x1800041b9  mov     [rcx], rax
0x1800041bc  lea     rcx, ?g_csActiveQueriesList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800041c3  mov     cs:qword_180011870, rax
0x1800041ca  call    cs:__imp_LeaveCriticalSection
0x1800041d0  mov     ecx, r12d
0x1800041d3  mov     ebx, r12d
0x1800041d6  mov     r14d, r12d
0x1800041d9  mov     [rbp+90h+var_F0], ecx
0x1800041dc  mov     [rbp+90h+var_F4], r12d
0x1800041e0  cmp     r12w, [r13+0]
0x1800041e5  jnb     loc_180004399
0x1800041eb  mov     r15, [r13+8]
0x1800041ef  lea     rdx, aDevqueryparamb; "DevQueryParamBlob"
0x1800041f6  mov     edi, ecx
0x1800041f8  shl     rdi, 5
0x1800041fc  mov     rcx, [rdi+r15]; String1
0x180004200  call    wcscmp_0
0x180004205  test    eax, eax
0x180004207  jnz     loc_180004380
0x18000420d  movzx   ecx, word ptr [rdi+r15+10h]; BufferSize
0x180004213  lea     rax, [rbp+90h+var_E0]
0x180004217  mov     rdx, [rdi+r15+18h]; Buffer
0x18000421c  lea     r9, [rbp+90h+var_F8]; unsigned int *
0x180004220  mov     [rsp+190h+var_130], rax; unsigned __int16 **
0x180004225  lea     r8, [rbp+90h+var_108]; enum _DEV_OBJECT_TYPE *
0x180004229  lea     rax, [rbp+90h+var_D8]
0x18000422d  mov     [rbp+90h+var_108], r12d
0x180004231  mov     [rsp+190h+var_138], rax; struct _DEV_QUERY_PARAMETER **
0x180004236  lea     rax, [rbp+90h+var_10C]
0x18000423a  mov     [rsp+190h+var_140], rax; unsigned int *
0x18000423f  lea     rax, [rbp+90h+var_C8]
0x180004243  mov     [rsp+190h+var_148], rax; struct _DEVPROP_FILTER_EXPRESSION **
0x180004248  lea     rax, [rbp+90h+var_110]
0x18000424c  mov     [rsp+190h+var_150], rax; unsigned int *
0x180004251  lea     rax, [rbp+90h+var_C0]
0x180004255  mov     [rsp+190h+var_158], rax; struct _DEVPROPCOMPKEY **
0x18000425a  lea     rax, [rbp+90h+var_100]
0x18000425e  mov     [rsp+190h+var_160], rax; unsigned int *
0x180004263  lea     rax, [rbp+90h+var_B8]
0x180004267  mov     [rsp+190h+var_168], rax; unsigned __int16 ***
0x18000426c  lea     rax, [rbp+90h+var_FC]
0x180004270  mov     [rsp+190h+var_170], rax; unsigned int *
0x180004275  mov     [rbp+90h+var_F8], r12d
0x180004279  mov     [rbp+90h+var_FC], r12d
0x18000427d  mov     [rbp+90h+var_B8], r12
0x180004281  mov     [rbp+90h+var_100], r12d
0x180004285  mov     [rbp+90h+var_C0], r12
0x180004289  mov     [rbp+90h+var_110], r12d
0x18000428d  mov     [rbp+90h+var_C8], r12
0x180004291  mov     [rbp+90h+var_10C], r12d
0x180004295  mov     [rbp+90h+var_D8], r12
0x180004299  mov     [rbp+90h+var_E0], r12
0x18000429d  call    ?DecodeDevQueryParamsBlob@@YAJKPEBXPEAW4_DEV_OBJECT_TYPE@@PEAK2PEAPEAPEAG2PEAPEAU_DEVPROPCOMPKEY@@2PEAPEAU_DEVPROP_FILTER_EXPRESSION@@2PEAPEAU_DEV_QUERY_PARAMETER@@PEAPEAG@Z; DecodeDevQueryParamsBlob(ulong,void const *,_DEV_OBJECT_TYPE *,ulong *,ulong *,ushort * * *,ulong *,_DEVPROPCOMPKEY * *,ulong *,_DEVPROP_FILTER_EXPRESSION * *,ulong *,_DEV_QUERY_PARAMETER * *,ushort * *)
0x1800042a2  mov     ebx, eax
0x1800042a4  test    eax, eax
0x1800042a6  js      loc_1800043BF
0x1800042ac  mov     rax, [rbp+90h+var_E8]
0x1800042b0  mov     r13d, [rbp+90h+var_10C]
0x1800042b4  mov     r12, [rbp+90h+var_C8]
0x1800042b8  mov     r15d, [rbp+90h+var_110]
0x1800042bc  movups  xmm0, xmmword ptr [rax]
0x1800042bf  mov     rdi, [rbp+90h+var_B8]
0x1800042c3  mov     ebx, [rbp+90h+var_FC]
0x1800042c6  mov     r9d, [rbp+90h+var_F8]
0x1800042ca  mov     r8d, [rbp+90h+var_108]
0x1800042ce  mov     rdx, [rbp+90h+var_B0]
0x1800042d2  mov     eax, r14d
0x1800042d5  mov     r14, [rbp+90h+var_C0]
0x1800042d9  movdqu  [rbp+90h+var_70], xmm0
0x1800042de  lea     rcx, [rsi+rax*8]
0x1800042e2  mov     esi, [rbp+90h+var_100]
0x1800042e5  mov     [rsp+190h+var_120], rcx
0x1800042ea  lea     rax, [rbp+90h+var_70]
0x1800042ee  mov     rcx, [rbp+90h+var_A8]
0x1800042f2  mov     [rsp+190h+var_128], rax
0x1800042f7  mov     rax, [rbp+90h+var_E0]
0x1800042fb  mov     [rsp+190h+var_130], rax
0x180004300  mov     rax, [rbp+90h+var_D8]
0x180004304  mov     [rsp+190h+var_138], rax
0x180004309  mov     dword ptr [rsp+190h+var_140], r13d
0x18000430e  mov     [rsp+190h+var_148], r12
0x180004313  mov     dword ptr [rsp+190h+var_150], r15d
0x180004318  mov     [rsp+190h+var_158], r14
0x18000431d  mov     dword ptr [rsp+190h+var_160], esi
0x180004321  mov     [rsp+190h+var_168], rdi
0x180004326  mov     dword ptr [rsp+190h+var_170], ebx
0x18000432a  call    ?Create@CQuery@@SAJPEAU_BROKER@@PEAU_BROKERED_EVENT@@W4_DEV_OBJECT_TYPE@@KKPEAPEBGKPEBU_DEVPROPCOMPKEY@@KPEBU_DEVPROP_FILTER_EXPRESSION@@KPEBU_DEV_QUERY_PARAMETER@@PEBGU_GUID@@PEAPEAV1@@Z; CQuery::Create(_BROKER *,_BROKERED_EVENT *,_DEV_OBJECT_TYPE,ulong,ulong,ushort const * *,ulong,_DEVPROPCOMPKEY const *,ulong,_DEVPROP_FILTER_EXPRESSION const *,ulong,_DEV_QUERY_PARAMETER const *,ushort const *,_GUID,CQuery * *)
0x18000432f  mov     [rbp+90h+var_108], eax
0x180004332  mov     r9, r14; struct _DEVPROPCOMPKEY *
0x180004335  mov     rax, [rbp+90h+var_E0]
0x180004339  mov     r8d, esi; unsigned int
0x18000433c  mov     [rsp+190h+var_150], rax; unsigned __int16 *
0x180004341  mov     rdx, rdi; unsigned __int16 **
0x180004344  mov     rax, [rbp+90h+var_D8]
0x180004348  mov     ecx, ebx; unsigned int
0x18000434a  mov     [rsp+190h+var_158], rax; struct _DEV_QUERY_PARAMETER *
0x18000434f  mov     dword ptr [rsp+190h+var_160], r13d; unsigned int
0x180004354  mov     [rsp+190h+var_168], r12; struct _DEVPROP_FILTER_EXPRESSION *
0x180004359  mov     dword ptr [rsp+190h+var_170], r15d; unsigned int
0x18000435e  call    ?FreeDecodedDevQueryParams@@YAXKPEAPEAGKPEAU_DEVPROPCOMPKEY@@KPEAU_DEVPROP_FILTER_EXPRESSION@@KPEAU_DEV_QUERY_PARAMETER@@PEAG@Z; FreeDecodedDevQueryParams(ulong,ushort * *,ulong,_DEVPROPCOMPKEY *,ulong,_DEVPROP_FILTER_EXPRESSION *,ulong,_DEV_QUERY_PARAMETER *,ushort *)
0x180004363  mov     ebx, [rbp+90h+var_108]
0x180004366  xor     r12d, r12d
0x180004369  test    ebx, ebx
0x18000436b  js      short loc_1800043BF
0x18000436d  mov     r14d, [rbp+90h+var_F4]
0x180004371  mov     rsi, [rbp+90h+var_A0]
0x180004375  inc     r14d
0x180004378  mov     r13, [rbp+90h+var_98]
0x18000437c  mov     [rbp+90h+var_F4], r14d
0x180004380  mov     ecx, [rbp+90h+var_F0]
0x180004383  movzx   eax, word ptr [r13+0]
0x180004388  inc     ecx
0x18000438a  mov     [rbp+90h+var_F0], ecx
0x18000438d  cmp     ecx, eax
0x18000438f  jb      loc_1800041EB
0x180004395  mov     rdi, [rbp+90h+var_D0]
0x180004399  mov     rax, [rbp+90h+var_90]
0x18000439d  mov     [rax], rdi
0x1800043a0  mov     rax, [rbp+90h+var_88]
0x1800043a4  mov     [rax], r12d
0x1800043a7  mov     [rax+8], r12d
0x1800043ab  mov     rax, [rbp+90h+var_80]
0x1800043af  mov     dword ptr [rax], 1
0x1800043b5  test    ebx, ebx
0x1800043b7  jns     loc_180004114
0x1800043bd  jmp     short loc_1800043C3
0x1800043bf  mov     rdi, [rbp+90h+var_D0]
0x1800043c3  test    rdi, rdi
0x1800043c6  jz      loc_180004114
0x1800043cc  mov     rcx, rdi; struct _BrokeredQueryContext *
0x1800043cf  call    ?RemoveBrokeredQueryContext@CActiveQueries@@SAXPEAU_BrokeredQueryContext@@@Z; CActiveQueries::RemoveBrokeredQueryContext(_BrokeredQueryContext *)
0x1800043d4  jmp     loc_180004114
```
