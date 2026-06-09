# s_RPC_SCardListReaders

- ea: `0x18000e7f0`
- end: `0x18000ebed`
- name: `s_RPC_SCardListReaders`
- size: `1021`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180009da0`
- `0x18000e4b0`
- `0x18000e7f0`
- `0x180028b78`
- `0x18002ac04`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e80d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e8cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e80d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e8cb`
- `RPCRT4!RpcRaiseException` at `0x18000ebe6`
- `RPCRT4!RpcRaiseException` at `0x18000ebe6`

## pseudocode

```c
__int64 __fastcall s_RPC_SCardListReaders(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5)
{
  DWORD CurrentThreadId; // eax
  char *v10; // rcx
  int v11; // r11d
  unsigned __int64 *v12; // rdx
  int v13; // ebx
  DWORD v14; // r10d
  int v15; // edi
  int v16; // r13d
  RPC_STATUS v17; // esi
  DWORD v18; // eax
  unsigned __int64 v19; // rdx
  int v20; // edi
  int v21; // ebx
  char *v22; // rcx
  __int64 v23; // rax
  char *v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  char *v27; // r11
  __int64 v28; // rdx
  char *v29; // rax
  __int64 v30; // rdx
  int v32; // r8d
  unsigned int i; // eax
  bool v34; // zf
  int v35; // edx
  unsigned int k; // ecx
  bool v37; // zf
  int j; // esi

  CurrentThreadId = GetCurrentThreadId();
  v11 = `WppTraceIndent'::`2'::idxCurrentThread;
  v12 = &`WppTraceIndent'::`2'::ThreadTable;
  v13 = -1;
  v14 = CurrentThreadId;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v11 = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    dword_18004BD54 = 0;
    goto LABEL_5;
  }
  v10 = 0;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != CurrentThreadId )
  {
    v32 = -1;
    for ( i = 0; ; ++i )
    {
      v34 = i == 32;
      if ( i >= 0x20 )
        break;
      v35 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)i);
      if ( v35 == v14 )
      {
        v11 = i;
        `WppTraceIndent'::`2'::idxCurrentThread = i;
        v12 = &`WppTraceIndent'::`2'::ThreadTable;
        v34 = i == 32;
        break;
      }
      if ( v32 == -1 && !v35 )
        v32 = i;
      v12 = &`WppTraceIndent'::`2'::ThreadTable;
    }
    if ( v34 )
    {
      v10 = 0;
      if ( v32 == -1 )
      {
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_58;
      }
      v11 = v32;
      `WppTraceIndent'::`2'::idxCurrentThread = v32;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v32) = v14;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v32 + 1) = 0;
    }
    else
    {
      v10 = 0;
    }
  }
  if ( v11 < 0 )
  {
LABEL_58:
    v15 = 0;
    goto LABEL_6;
  }
LABEL_5:
  v15 = ++*((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v11 + 1);
LABEL_6:
  v16 = 1;
  `WppTraceIndent'::`2'::szIndentPrefix[0] = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    for ( j = 1; j <= v15; ++j )
    {
      if ( (unsigned int)StringCbCatA(v10, (unsigned __int64)v12, "..") )
        break;
    }
  }
  StringCbCatA(v10, (unsigned __int64)v12, ">");
  WPP_pszIndent = `WppTraceIndent'::`2'::szIndentPrefix;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      WPP_6cb68c4060583735bafc290ec605627b_Traceguids,
      `WppTraceIndent'::`2'::szIndentPrefix);
  }
  v17 = I_s_RPC_SCardListReaders(a1, a2, a3, a4, a5);
  v18 = GetCurrentThreadId();
  v20 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v20 = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v18;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    dword_18004BD54 = 0;
  }
  else
  {
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
      || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != v18 )
    {
      for ( k = 0; ; ++k )
      {
        v37 = k == 32;
        if ( k >= 0x20 )
          break;
        v19 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)k);
        if ( (_DWORD)v19 == v18 )
        {
          v20 = k;
          `WppTraceIndent'::`2'::idxCurrentThread = k;
          v37 = k == 32;
          break;
        }
        if ( v13 == -1 && !(_DWORD)v19 )
          v13 = k;
      }
      if ( v37 )
      {
        if ( v13 == -1 )
        {
          v20 = -2;
          `WppTraceIndent'::`2'::idxCurrentThread = -2;
          goto LABEL_53;
        }
        v20 = v13;
        `WppTraceIndent'::`2'::idxCurrentThread = v13;
        *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v13) = v18;
        *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v13 + 1) = 0;
      }
    }
    if ( v20 < 0 )
    {
LABEL_53:
      v21 = 0;
      goto LABEL_13;
    }
  }
  v21 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v20 + 1);
LABEL_13:
  v22 = (char *)WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix[0] = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v21 >= 1 )
  {
    do
    {
      if ( (unsigned int)StringCbCatA(v22, v19, "..") )
        break;
      ++v16;
    }
    while ( v16 <= v21 );
    v22 = (char *)WPP_GLOBAL_Control;
  }
  v23 = 256;
  v24 = `WppTraceIndent'::`2'::szIndentPrefix;
  do
  {
    if ( !*v24 )
      break;
    ++v24;
    --v23;
  }
  while ( v23 );
  if ( v23 )
  {
    v25 = "<";
    v26 = 2147483646;
    v27 = &`WppTraceIndent'::`2'::szIndentPrefix[256 - v23];
    v28 = v23;
    do
    {
      if ( !v26 )
        break;
      if ( !*v25 )
        break;
      *v27++ = *v25++;
      --v26;
      --v28;
    }
    while ( v28 );
    v29 = v27 - 1;
    if ( v28 )
      v29 = v27;
    *v29 = 0;
  }
  if ( v20 >= 0 )
  {
    v30 = 8LL * v20;
    v34 = (*(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v30 + 4))-- == 1;
    if ( v34 )
      *(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v30) = 0;
  }
  WPP_pszIndent = `WppTraceIndent'::`2'::szIndentPrefix;
  if ( v22 != (char *)&WPP_GLOBAL_Control && (v22[28] & 0x20) != 0 && (unsigned __int8)v22[25] >= 4u )
    WPP_SF_sd(*((_QWORD *)v22 + 2), 33, (unsigned int)WPP_6cb68c4060583735bafc290ec605627b_Traceguids, 0, v17);
  if ( v17 )
    RpcRaiseException(v17);
  return 0;
}

```

## disassembly

```asm
0x18000e7f0  push    rbx
0x18000e7f2  push    rbp
0x18000e7f3  push    rsi
0x18000e7f4  push    rdi
0x18000e7f5  push    r12
0x18000e7f7  push    r13
0x18000e7f9  push    r14
0x18000e7fb  push    r15
0x18000e7fd  sub     rsp, 48h
0x18000e801  mov     rbp, r9
0x18000e804  mov     r14d, r8d
0x18000e807  mov     r15, rdx
0x18000e80a  mov     r12, rcx
0x18000e80d  call    cs:__imp_GetCurrentThreadId
0x18000e813  movsxd  r11, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000e81a  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; unsigned __int64
0x18000e821  mov     ebx, 0FFFFFFFFh
0x18000e826  mov     r10d, eax
0x18000e829  cmp     r11d, ebx
0x18000e82c  jz      loc_18000EB04
0x18000e832  xor     ecx, ecx; char *
0x18000e834  cmp     r11d, 0FFFFFFFEh
0x18000e838  jz      loc_18000E9EE
0x18000e83e  cmp     [rdx+r11*8], eax
0x18000e842  jnz     loc_18000E9EE
0x18000e848  test    r11d, r11d
0x18000e84b  js      loc_18000EADD
0x18000e851  movsxd  rax, r11d
0x18000e854  inc     dword ptr [rdx+rax*8+4]
0x18000e858  mov     edi, [rdx+rax*8+4]
0x18000e85c  mov     rax, cs:WPP_GLOBAL_Control
0x18000e863  mov     r13d, 1
0x18000e869  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000e870  test    byte ptr [rax+1Ch], 2
0x18000e874  jnz     loc_18000EB21
0x18000e87a  lea     r8, pszSrc; ">"
0x18000e881  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x18000e886  lea     rax, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000e88d  mov     cs:?WPP_pszIndent@@3PEADEA, rax; char * WPP_pszIndent
0x18000e894  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e89b  lea     rdx, WPP_GLOBAL_Control
0x18000e8a2  cmp     rcx, rdx
0x18000e8a5  jnz     loc_18000EAA2
0x18000e8ab  mov     rax, [rsp+88h+arg_20]
0x18000e8b3  mov     r9, rbp
0x18000e8b6  mov     r8d, r14d
0x18000e8b9  mov     [rsp+88h+var_68], rax
0x18000e8be  mov     rdx, r15
0x18000e8c1  mov     rcx, r12
0x18000e8c4  call    I_s_RPC_SCardListReaders
0x18000e8c9  mov     esi, eax
0x18000e8cb  call    cs:__imp_GetCurrentThreadId
0x18000e8d1  movsxd  rdi, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000e8d8  lea     r14, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000e8df  mov     r8d, eax
0x18000e8e2  cmp     edi, ebx
0x18000e8e4  jz      loc_18000EB56
0x18000e8ea  cmp     edi, 0FFFFFFFEh
0x18000e8ed  jz      loc_18000EA19
0x18000e8f3  cmp     [r14+rdi*8], eax
0x18000e8f7  jnz     loc_18000EA19
0x18000e8fd  xor     r9d, r9d
0x18000e900  test    edi, edi
0x18000e902  js      loc_18000EA9A
0x18000e908  movsxd  rax, edi
0x18000e90b  xor     r9d, r9d
0x18000e90e  mov     ebx, [r14+rax*8+4]
0x18000e913  mov     rcx, cs:WPP_GLOBAL_Control; char *
0x18000e91a  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000e921  test    byte ptr [rcx+1Ch], 2
0x18000e925  jnz     loc_18000EB70
0x18000e92b  mov     edx, 100h
0x18000e930  lea     rbx, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000e937  mov     eax, edx
0x18000e939  mov     r8, rbx
0x18000e93c  cmp     byte ptr [r8], 0
0x18000e940  jnz     loc_18000EBAA
0x18000e946  mov     r10, rdx
0x18000e949  sub     r10, rax
0x18000e94c  test    rax, rax
0x18000e94f  cmovz   r10, r9
0x18000e953  jz      short loc_18000E99B
0x18000e955  lea     r9, asc_18003BC58; "<"
0x18000e95c  mov     r8d, 7FFFFFFEh
0x18000e962  lea     r11, [r10+rbx]
0x18000e966  sub     rdx, r10
0x18000e969  jz      short loc_18000E98A
0x18000e96b  test    r8, r8
0x18000e96e  jz      short loc_18000E98A
0x18000e970  movzx   eax, byte ptr [r9]
0x18000e974  test    al, al
0x18000e976  jz      short loc_18000E98A
0x18000e978  mov     [r11], al
0x18000e97b  inc     r9
0x18000e97e  inc     r11
0x18000e981  dec     r8
0x18000e984  sub     rdx, 1
0x18000e988  jnz     short loc_18000E96B
0x18000e98a  test    rdx, rdx
0x18000e98d  lea     rax, [r11-1]
0x18000e991  cmovnz  rax, r11
0x18000e995  xor     r9d, r9d
0x18000e998  mov     byte ptr [rax], 0
0x18000e99b  test    edi, edi
0x18000e99d  js      short loc_18000E9B6
0x18000e99f  movsxd  rax, edi
0x18000e9a2  lea     rdx, ds:0[rax*8]
0x18000e9aa  sub     dword ptr [rdx+r14+4], 1
0x18000e9b0  jnz     short loc_18000E9B6
0x18000e9b2  mov     [rdx+r14], r9d
0x18000e9b6  mov     cs:?WPP_pszIndent@@3PEADEA, rbx; char * WPP_pszIndent
0x18000e9bd  lea     rax, WPP_GLOBAL_Control
0x18000e9c4  cmp     rcx, rax
0x18000e9c7  jz      short loc_18000E9D3
0x18000e9c9  test    byte ptr [rcx+1Ch], 20h
0x18000e9cd  jnz     loc_18000EBBC
0x18000e9d3  test    esi, esi
0x18000e9d5  jnz     loc_18000EBE4
0x18000e9db  xor     eax, eax
0x18000e9dd  add     rsp, 48h
0x18000e9e1  pop     r15
0x18000e9e3  pop     r14
0x18000e9e5  pop     r13
0x18000e9e7  pop     r12
0x18000e9e9  pop     rdi
0x18000e9ea  pop     rsi
0x18000e9eb  pop     rbp
0x18000e9ec  pop     rbx
0x18000e9ed  retn
0x18000e9ee  mov     r8d, ebx
0x18000e9f1  mov     eax, ecx
0x18000e9f3  cmp     eax, 20h ; ' '
0x18000e9f6  jnb     short loc_18000EA52
0x18000e9f8  movsxd  rcx, eax
0x18000e9fb  mov     edx, [rdx+rcx*8]
0x18000e9fe  cmp     edx, r10d
0x18000ea01  jz      short loc_18000EA3F
0x18000ea03  cmp     r8d, ebx
0x18000ea06  jnz     short loc_18000EA0E
0x18000ea08  test    edx, edx
0x18000ea0a  cmovz   r8d, eax
0x18000ea0e  inc     eax
0x18000ea10  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000ea17  jmp     short loc_18000E9F3
0x18000ea19  xor     r9d, r9d
0x18000ea1c  mov     ecx, r9d
0x18000ea1f  nop
0x18000ea20  cmp     ecx, 20h ; ' '
0x18000ea23  jnb     short loc_18000EA84
0x18000ea25  movsxd  rax, ecx
0x18000ea28  mov     edx, [r14+rax*8]
0x18000ea2c  cmp     edx, r8d
0x18000ea2f  jz      short loc_18000EA79
0x18000ea31  cmp     ebx, 0FFFFFFFFh
0x18000ea34  jnz     short loc_18000EA3B
0x18000ea36  test    edx, edx
0x18000ea38  cmovz   ebx, ecx
0x18000ea3b  inc     ecx
0x18000ea3d  jmp     short loc_18000EA20
0x18000ea3f  mov     r11d, eax
0x18000ea42  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, eax; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000ea48  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000ea4f  cmp     eax, 20h ; ' '
0x18000ea52  jnz     loc_18000EAE4
0x18000ea58  xor     ecx, ecx
0x18000ea5a  cmp     r8d, ebx
0x18000ea5d  jz      short loc_18000EAD3
0x18000ea5f  movsxd  rax, r8d
0x18000ea62  mov     r11d, r8d
0x18000ea65  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r8d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000ea6c  mov     [rdx+rax*8], r10d
0x18000ea70  mov     [rdx+rax*8+4], ecx
0x18000ea74  jmp     loc_18000E848
0x18000ea79  mov     edi, ecx
0x18000ea7b  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000ea81  cmp     ecx, 20h ; ' '
0x18000ea84  jnz     loc_18000E900
0x18000ea8a  cmp     ebx, 0FFFFFFFFh
0x18000ea8d  jnz     short loc_18000EAEB
0x18000ea8f  mov     edi, 0FFFFFFFEh
0x18000ea94  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, edi; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000ea9a  mov     ebx, r9d
0x18000ea9d  jmp     loc_18000E913
0x18000eaa2  test    byte ptr [rcx+1Ch], 20h
0x18000eaa6  jz      loc_18000E8AB
0x18000eaac  cmp     byte ptr [rcx+19h], 4
0x18000eab0  jb      loc_18000E8AB
0x18000eab6  mov     rcx, [rcx+10h]
0x18000eaba  lea     r8, WPP_6cb68c4060583735bafc290ec605627b_Traceguids
0x18000eac1  mov     edx, 20h ; ' '
0x18000eac6  mov     r9, rax
0x18000eac9  call    WPP_SF_s
0x18000eace  jmp     loc_18000E8AB
0x18000ead3  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, 0FFFFFFFEh; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000eadd  mov     edi, ecx
0x18000eadf  jmp     loc_18000E85C
0x18000eae4  xor     ecx, ecx
0x18000eae6  jmp     loc_18000E848
0x18000eaeb  movsxd  rax, ebx
0x18000eaee  mov     edi, ebx
0x18000eaf0  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ebx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000eaf6  mov     [r14+rax*8], r8d
0x18000eafa  mov     [r14+rax*8+4], r9d
0x18000eaff  jmp     loc_18000E900
0x18000eb04  xor     r11d, r11d
0x18000eb07  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, r10d; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000eb0e  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r11d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000eb15  mov     cs:dword_18004BD54, r11d
0x18000eb1c  jmp     loc_18000E851
0x18000eb21  cmp     byte ptr [rax+19h], 5
0x18000eb25  jb      loc_18000E87A
0x18000eb2b  mov     esi, r13d
0x18000eb2e  cmp     edi, r13d
0x18000eb31  jl      loc_18000E87A
0x18000eb37  lea     r8, asc_1800400D4; ".."
0x18000eb3e  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x18000eb43  test    eax, eax
0x18000eb45  jnz     loc_18000E87A
0x18000eb4b  inc     esi
0x18000eb4d  cmp     esi, edi
0x18000eb4f  jle     short loc_18000EB37
0x18000eb51  jmp     loc_18000E87A
0x18000eb56  xor     edi, edi
0x18000eb58  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, r8d; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000eb5f  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, edi; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000eb65  mov     cs:dword_18004BD54, edi
0x18000eb6b  jmp     loc_18000E908
0x18000eb70  cmp     byte ptr [rcx+19h], 5
0x18000eb74  jb      loc_18000E92B
0x18000eb7a  cmp     ebx, r13d
0x18000eb7d  jl      loc_18000E92B
0x18000eb83  lea     r8, asc_1800400D4; ".."
0x18000eb8a  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x18000eb8f  test    eax, eax
0x18000eb91  jnz     short loc_18000EB9B
0x18000eb93  inc     r13d
0x18000eb96  cmp     r13d, ebx
0x18000eb99  jle     short loc_18000EB83
0x18000eb9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eba2  xor     r9d, r9d
0x18000eba5  jmp     loc_18000E92B
0x18000ebaa  inc     r8
0x18000ebad  sub     rax, 1
0x18000ebb1  jnz     loc_18000E93C
0x18000ebb7  jmp     loc_18000E946
0x18000ebbc  cmp     byte ptr [rcx+19h], 4
0x18000ebc0  jb      loc_18000E9D3
0x18000ebc6  mov     rcx, [rcx+10h]
0x18000ebca  lea     r8, WPP_6cb68c4060583735bafc290ec605627b_Traceguids
0x18000ebd1  mov     edx, 21h ; '!'
0x18000ebd6  mov     dword ptr [rsp+88h+var_68], esi
0x18000ebda  call    WPP_SF_sd
0x18000ebdf  jmp     loc_18000E9D3
0x18000ebe4  mov     ecx, esi; exception
0x18000ebe6  call    cs:__imp_RpcRaiseException
```
