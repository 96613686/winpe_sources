# s_RPC_SCardGetStatusChange

- ea: `0x180009420`
- end: `0x1800098a2`
- name: `s_RPC_SCardGetStatusChange`
- size: `1154`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180009420`
- `0x18000a310`
- `0x18000e4b0`
- `0x180028b78`
- `0x18002ac04`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000943d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009573`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000943d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009573`
- `RPCRT4!RpcRaiseException` at `0x180009673`
- `RPCRT4!RpcRaiseException` at `0x180009673`

## pseudocode

```c
__int64 __fastcall s_RPC_SCardGetStatusChange(
        PVOID Context,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  DWORD CurrentThreadId; // eax
  int v10; // r11d
  unsigned __int64 *v11; // rdx
  int v12; // ebx
  DWORD v13; // r10d
  int v14; // edi
  char *v15; // rcx
  __int64 v16; // rax
  char *v17; // rdx
  __int64 v18; // r13
  __int64 v19; // rdx
  const char *v20; // r10
  char *v21; // r9
  __int64 v22; // rax
  __int64 v23; // r8
  char *v24; // rax
  RPC_STATUS v25; // ebp
  DWORD v26; // eax
  unsigned __int64 v27; // rdx
  char *v28; // r9
  int v29; // edi
  int v30; // ebx
  char *v31; // rcx
  __int64 v32; // rax
  char *v33; // rdx
  const char *v34; // rdx
  __int64 v35; // rsi
  char *v36; // rax
  __int64 v37; // rdx
  int v38; // r8d
  unsigned int i; // eax
  bool v40; // zf
  int v41; // edx
  unsigned int j; // ecx
  bool v43; // zf
  int v45; // esi
  int k; // r14d

  CurrentThreadId = GetCurrentThreadId();
  v10 = `WppTraceIndent'::`2'::idxCurrentThread;
  v11 = &`WppTraceIndent'::`2'::ThreadTable;
  v12 = -1;
  v13 = CurrentThreadId;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v10 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
    dword_18004BD54 = 0;
  }
  else
  {
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
      || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != CurrentThreadId )
    {
      v38 = -1;
      for ( i = 0; ; ++i )
      {
        v40 = i == 32;
        if ( i >= 0x20 )
          break;
        v41 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)i);
        if ( v41 == v13 )
        {
          v10 = i;
          `WppTraceIndent'::`2'::idxCurrentThread = i;
          v11 = &`WppTraceIndent'::`2'::ThreadTable;
          v40 = i == 32;
          break;
        }
        if ( v38 == -1 && !v41 )
          v38 = i;
        v11 = &`WppTraceIndent'::`2'::ThreadTable;
      }
      if ( v40 )
      {
        if ( v38 == -1 )
        {
          `WppTraceIndent'::`2'::idxCurrentThread = -2;
          goto LABEL_52;
        }
        v10 = v38;
        `WppTraceIndent'::`2'::idxCurrentThread = v38;
        *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v38) = v13;
        *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v38 + 1) = 0;
      }
    }
    if ( v10 < 0 )
    {
LABEL_52:
      v14 = 0;
      goto LABEL_6;
    }
  }
  v14 = ++*((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v10 + 1);
LABEL_6:
  v15 = (char *)WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix[0] = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v45 = 1;
    if ( v14 >= 1 )
    {
      do
      {
        if ( (unsigned int)StringCbCatA(v15, (unsigned __int64)v11, "..") )
          break;
        ++v45;
      }
      while ( v45 <= v14 );
      v15 = (char *)WPP_GLOBAL_Control;
    }
  }
  v16 = 256;
  v17 = `WppTraceIndent'::`2'::szIndentPrefix;
  do
  {
    if ( !*v17 )
      break;
    ++v17;
    --v16;
  }
  while ( v16 );
  v18 = 2147483646;
  v19 = 256 - v16;
  if ( v16 )
  {
    v20 = ">";
    v21 = &`WppTraceIndent'::`2'::szIndentPrefix[v19];
    v22 = 2147483646;
    v23 = 256 - v19;
    if ( v19 != 256 )
    {
      do
      {
        if ( !v22 )
          break;
        if ( !*v20 )
          break;
        *v21++ = *v20++;
        --v22;
        --v23;
      }
      while ( v23 );
    }
    v24 = v21 - 1;
    if ( v23 )
      v24 = v21;
    *v24 = 0;
  }
  WPP_pszIndent = `WppTraceIndent'::`2'::szIndentPrefix;
  if ( v15 != (char *)&WPP_GLOBAL_Control && (v15[28] & 0x20) != 0 && (unsigned __int8)v15[25] >= 4u )
    WPP_SF_s(
      *((_QWORD *)v15 + 2),
      26,
      WPP_6cb68c4060583735bafc290ec605627b_Traceguids,
      `WppTraceIndent'::`2'::szIndentPrefix);
  v25 = I_s_RPC_SCardGetStatusChange(Context, a5, a6, a7, a8);
  v26 = GetCurrentThreadId();
  v29 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v26;
    v29 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    dword_18004BD54 = 0;
  }
  else
  {
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
      || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != v26 )
    {
      for ( j = 0; ; ++j )
      {
        v43 = j == 32;
        if ( j >= 0x20 )
          break;
        v27 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)j);
        if ( (_DWORD)v27 == v26 )
        {
          v29 = j;
          `WppTraceIndent'::`2'::idxCurrentThread = j;
          v43 = j == 32;
          break;
        }
        if ( v12 == -1 && !(_DWORD)v27 )
          v12 = j;
      }
      if ( v43 )
      {
        if ( v12 == -1 )
        {
          v29 = -2;
          `WppTraceIndent'::`2'::idxCurrentThread = -2;
          goto LABEL_64;
        }
        v29 = v12;
        `WppTraceIndent'::`2'::idxCurrentThread = v12;
        *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v12) = v26;
        *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v12 + 1) = 0;
      }
    }
    if ( v29 < 0 )
    {
LABEL_64:
      v30 = 0;
      goto LABEL_23;
    }
  }
  v30 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v29 + 1);
LABEL_23:
  v31 = (char *)WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix[0] = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v30 >= 1 )
  {
    for ( k = 1; k <= v30; ++k )
    {
      if ( (unsigned int)StringCbCatA(v31, v27, "..") )
        break;
    }
    v31 = (char *)WPP_GLOBAL_Control;
  }
  v32 = 256;
  v33 = `WppTraceIndent'::`2'::szIndentPrefix;
  do
  {
    if ( !*v33 )
      break;
    ++v33;
    --v32;
  }
  while ( v32 );
  if ( v32 )
  {
    v34 = "<";
    v28 = &`WppTraceIndent'::`2'::szIndentPrefix[256 - v32];
    v35 = v32;
    do
    {
      if ( !v18 )
        break;
      if ( !*v34 )
        break;
      *v28++ = *v34++;
      --v18;
      --v35;
    }
    while ( v35 );
    v36 = v28 - 1;
    if ( v35 )
      v36 = v28;
    *v36 = 0;
  }
  if ( v29 >= 0 )
  {
    v37 = 8LL * v29;
    v40 = (*(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v37 + 4))-- == 1;
    if ( v40 )
      *(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v37) = 0;
  }
  WPP_pszIndent = `WppTraceIndent'::`2'::szIndentPrefix;
  if ( v31 != (char *)&WPP_GLOBAL_Control && (v31[28] & 0x20) != 0 && (unsigned __int8)v31[25] >= 4u )
    WPP_SF_sd(*((_QWORD *)v31 + 2), 27, (unsigned int)WPP_6cb68c4060583735bafc290ec605627b_Traceguids, (_DWORD)v28, v25);
  if ( v25 )
    RpcRaiseException(v25);
  return 0;
}

```

## disassembly

```asm
0x180009420  push    rbx
0x180009422  push    rbp
0x180009423  push    rsi
0x180009424  push    rdi
0x180009425  push    r12
0x180009427  push    r13
0x180009429  push    r14
0x18000942b  push    r15
0x18000942d  sub     rsp, 58h
0x180009431  mov     ebp, r9d
0x180009434  mov     r14, r8
0x180009437  mov     r15d, edx
0x18000943a  mov     r12, rcx
0x18000943d  call    cs:__imp_GetCurrentThreadId
0x180009443  movsxd  r11, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000944a  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; unsigned __int64
0x180009451  xor     r9d, r9d
0x180009454  mov     ebx, 0FFFFFFFFh
0x180009459  mov     r10d, eax
0x18000945c  cmp     r11d, ebx
0x18000945f  jz      loc_1800097A0
0x180009465  cmp     r11d, 0FFFFFFFEh
0x180009469  jz      loc_18000967A
0x18000946f  cmp     [rdx+r11*8], eax
0x180009473  jnz     loc_18000967A
0x180009479  test    r11d, r11d
0x18000947c  js      loc_1800096D2
0x180009482  movsxd  rax, r11d
0x180009485  inc     dword ptr [rdx+rax*8+4]
0x180009489  mov     edi, [rdx+rax*8+4]
0x18000948d  mov     rcx, cs:WPP_GLOBAL_Control; char *
0x180009494  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000949b  test    byte ptr [rcx+1Ch], 2
0x18000949f  jnz     loc_1800097BD
0x1800094a5  mov     esi, 100h
0x1800094aa  lea     r11, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x1800094b1  mov     eax, esi
0x1800094b3  mov     rdx, r11
0x1800094b6  cmp     byte ptr [rdx], 0
0x1800094b9  jnz     loc_1800097F9
0x1800094bf  mov     rdx, rsi
0x1800094c2  mov     r13d, 7FFFFFFEh
0x1800094c8  sub     rdx, rax
0x1800094cb  test    rax, rax
0x1800094ce  cmovz   rdx, r9
0x1800094d2  jz      short loc_180009517
0x1800094d4  mov     r8, rsi
0x1800094d7  lea     r10, pszSrc; ">"
0x1800094de  lea     r9, [rdx+r11]
0x1800094e2  mov     eax, r13d
0x1800094e5  sub     r8, rdx
0x1800094e8  jz      short loc_180009509
0x1800094ea  test    rax, rax
0x1800094ed  jz      short loc_180009509
0x1800094ef  movzx   edx, byte ptr [r10]
0x1800094f3  test    dl, dl
0x1800094f5  jz      short loc_180009509
0x1800094f7  mov     [r9], dl
0x1800094fa  inc     r10
0x1800094fd  inc     r9
0x180009500  dec     rax
0x180009503  sub     r8, 1
0x180009507  jnz     short loc_1800094EA
0x180009509  test    r8, r8
0x18000950c  lea     rax, [r9-1]
0x180009510  cmovnz  rax, r9
0x180009514  mov     byte ptr [rax], 0
0x180009517  mov     cs:?WPP_pszIndent@@3PEADEA, r11; char * WPP_pszIndent
0x18000951e  lea     rax, WPP_GLOBAL_Control
0x180009525  cmp     rcx, rax
0x180009528  jnz     loc_180009728
0x18000952e  mov     rax, [rsp+98h+arg_38]
0x180009536  mov     r9d, ebp
0x180009539  mov     [rsp+98h+var_60], rax; __int64
0x18000953e  mov     r8, r14
0x180009541  mov     rax, [rsp+98h+arg_30]
0x180009549  mov     edx, r15d
0x18000954c  mov     [rsp+98h+var_68], rax; __int64
0x180009551  mov     rcx, r12; Context
0x180009554  mov     eax, [rsp+98h+arg_28]
0x18000955b  mov     [rsp+98h+var_70], eax; int
0x18000955f  mov     rax, [rsp+98h+arg_20]
0x180009567  mov     [rsp+98h+var_78], rax; __int64
0x18000956c  call    I_s_RPC_SCardGetStatusChange
0x180009571  mov     ebp, eax
0x180009573  call    cs:__imp_GetCurrentThreadId
0x180009579  movsxd  rdi, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180009580  lea     r12, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180009587  mov     r8d, eax
0x18000958a  cmp     edi, ebx
0x18000958c  jz      loc_18000980B
0x180009592  cmp     edi, 0FFFFFFFEh
0x180009595  jz      loc_1800096DA
0x18000959b  cmp     [r12+rdi*8], eax
0x18000959f  jnz     loc_1800096DA
0x1800095a5  xor     r15d, r15d
0x1800095a8  test    edi, edi
0x1800095aa  js      loc_180009720
0x1800095b0  movsxd  rax, edi
0x1800095b3  mov     ebx, [r12+rax*8+4]
0x1800095b8  mov     rcx, cs:WPP_GLOBAL_Control; char *
0x1800095bf  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x1800095c6  test    byte ptr [rcx+1Ch], 2
0x1800095ca  jnz     loc_18000982B
0x1800095d0  lea     r10, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x1800095d7  mov     rax, rsi
0x1800095da  mov     rdx, r10
0x1800095dd  cmp     byte ptr [rdx], 0
0x1800095e0  jnz     loc_180009868
0x1800095e6  mov     r8, rsi
0x1800095e9  sub     r8, rax
0x1800095ec  test    rax, rax
0x1800095ef  cmovz   r8, r15
0x1800095f3  jz      short loc_180009631
0x1800095f5  lea     rdx, asc_18003BC58; "<"
0x1800095fc  lea     r9, [r8+r10]
0x180009600  sub     rsi, r8
0x180009603  jz      short loc_180009623
0x180009605  test    r13, r13
0x180009608  jz      short loc_180009623
0x18000960a  movzx   eax, byte ptr [rdx]
0x18000960d  test    al, al
0x18000960f  jz      short loc_180009623
0x180009611  mov     [r9], al
0x180009614  inc     rdx
0x180009617  inc     r9
0x18000961a  dec     r13
0x18000961d  sub     rsi, 1
0x180009621  jnz     short loc_180009605
0x180009623  test    rsi, rsi
0x180009626  lea     rax, [r9-1]
0x18000962a  cmovnz  rax, r9
0x18000962e  mov     byte ptr [rax], 0
0x180009631  test    edi, edi
0x180009633  js      short loc_18000964C
0x180009635  movsxd  rax, edi
0x180009638  lea     rdx, ds:0[rax*8]
0x180009640  sub     dword ptr [rdx+r12+4], 1
0x180009646  jnz     short loc_18000964C
0x180009648  mov     [rdx+r12], r15d
0x18000964c  mov     cs:?WPP_pszIndent@@3PEADEA, r10; char * WPP_pszIndent
0x180009653  lea     rax, WPP_GLOBAL_Control
0x18000965a  cmp     rcx, rax
0x18000965d  jz      short loc_180009669
0x18000965f  test    byte ptr [rcx+1Ch], 20h
0x180009663  jnz     loc_18000987A
0x180009669  test    ebp, ebp
0x18000966b  jz      loc_18000978D
0x180009671  mov     ecx, ebp; exception
0x180009673  call    cs:__imp_RpcRaiseException
0x180009679  int     3; Trap to Debugger
0x18000967a  mov     r8d, ebx
0x18000967d  mov     eax, r9d
0x180009680  cmp     eax, 20h ; ' '
0x180009683  jnb     short loc_1800096B9
0x180009685  movsxd  rcx, eax
0x180009688  mov     edx, [rdx+rcx*8]
0x18000968b  cmp     edx, r10d
0x18000968e  jz      short loc_1800096A6
0x180009690  cmp     r8d, ebx
0x180009693  jnz     short loc_18000969B
0x180009695  test    edx, edx
0x180009697  cmovz   r8d, eax
0x18000969b  inc     eax
0x18000969d  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x1800096a4  jmp     short loc_180009680
0x1800096a6  mov     r11d, eax
0x1800096a9  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, eax; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x1800096af  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x1800096b6  cmp     eax, 20h ; ' '
0x1800096b9  jnz     loc_180009479
0x1800096bf  cmp     r8d, ebx
0x1800096c2  jnz     loc_180009759
0x1800096c8  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, 0FFFFFFFEh; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x1800096d2  mov     edi, r9d
0x1800096d5  jmp     loc_18000948D
0x1800096da  xor     r15d, r15d
0x1800096dd  mov     ecx, r15d
0x1800096e0  cmp     ecx, 20h ; ' '
0x1800096e3  jnb     short loc_18000970A
0x1800096e5  movsxd  rax, ecx
0x1800096e8  mov     edx, [r12+rax*8]
0x1800096ec  cmp     edx, r8d
0x1800096ef  jz      short loc_1800096FF
0x1800096f1  cmp     ebx, 0FFFFFFFFh
0x1800096f4  jnz     short loc_1800096FB
0x1800096f6  test    edx, edx
0x1800096f8  cmovz   ebx, ecx
0x1800096fb  inc     ecx
0x1800096fd  jmp     short loc_1800096E0
0x1800096ff  mov     edi, ecx
0x180009701  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180009707  cmp     ecx, 20h ; ' '
0x18000970a  jnz     loc_1800095A8
0x180009710  cmp     ebx, 0FFFFFFFFh
0x180009713  jnz     short loc_180009774
0x180009715  mov     edi, 0FFFFFFFEh
0x18000971a  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, edi; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180009720  mov     ebx, r15d
0x180009723  jmp     loc_1800095B8
0x180009728  test    byte ptr [rcx+1Ch], 20h
0x18000972c  jz      loc_18000952E
0x180009732  cmp     byte ptr [rcx+19h], 4
0x180009736  jb      loc_18000952E
0x18000973c  mov     rcx, [rcx+10h]
0x180009740  lea     r8, WPP_6cb68c4060583735bafc290ec605627b_Traceguids
0x180009747  mov     edx, 1Ah
0x18000974c  mov     r9, r11
0x18000974f  call    WPP_SF_s
0x180009754  jmp     loc_18000952E
0x180009759  movsxd  rax, r8d
0x18000975c  mov     r11d, r8d
0x18000975f  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r8d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180009766  mov     [rdx+rax*8], r10d
0x18000976a  mov     [rdx+rax*8+4], r9d
0x18000976f  jmp     loc_180009479
0x180009774  movsxd  rax, ebx
0x180009777  mov     edi, ebx
0x180009779  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ebx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000977f  mov     [r12+rax*8], r8d
0x180009783  mov     [r12+rax*8+4], r15d
0x180009788  jmp     loc_1800095A8
0x18000978d  xor     eax, eax
0x18000978f  add     rsp, 58h
0x180009793  pop     r15
0x180009795  pop     r14
0x180009797  pop     r13
0x180009799  pop     r12
0x18000979b  pop     rdi
0x18000979c  pop     rsi
0x18000979d  pop     rbp
0x18000979e  pop     rbx
0x18000979f  retn
0x1800097a0  mov     r11d, r9d
0x1800097a3  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r9d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x1800097aa  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, r10d; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x1800097b1  mov     cs:dword_18004BD54, r9d
0x1800097b8  jmp     loc_180009482
0x1800097bd  cmp     byte ptr [rcx+19h], 5
0x1800097c1  jb      loc_1800094A5
0x1800097c7  mov     esi, 1
0x1800097cc  cmp     edi, esi
0x1800097ce  jl      loc_1800094A5
0x1800097d4  lea     r8, asc_1800400D4; ".."
0x1800097db  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x1800097e0  test    eax, eax
0x1800097e2  jnz     short loc_1800097EA
0x1800097e4  inc     esi
0x1800097e6  cmp     esi, edi
0x1800097e8  jle     short loc_1800097D4
0x1800097ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097f1  xor     r9d, r9d
0x1800097f4  jmp     loc_1800094A5
0x1800097f9  inc     rdx
0x1800097fc  sub     rax, 1
0x180009800  jnz     loc_1800094B6
0x180009806  jmp     loc_1800094BF
0x18000980b  xor     r15d, r15d
0x18000980e  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, r8d; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180009815  mov     edi, r15d
0x180009818  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r15d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000981f  mov     cs:dword_18004BD54, r15d
0x180009826  jmp     loc_1800095B0
0x18000982b  cmp     byte ptr [rcx+19h], 5
0x18000982f  jb      loc_1800095D0
0x180009835  cmp     ebx, 1
0x180009838  jl      loc_1800095D0
0x18000983e  mov     r14d, 1
0x180009844  lea     r8, asc_1800400D4; ".."
0x18000984b  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x180009850  test    eax, eax
0x180009852  jnz     short loc_18000985C
0x180009854  inc     r14d
0x180009857  cmp     r14d, ebx
0x18000985a  jle     short loc_180009844
0x18000985c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009863  jmp     loc_1800095D0
0x180009868  inc     rdx
0x18000986b  sub     rax, 1
0x18000986f  jnz     loc_1800095DD
0x180009875  jmp     loc_1800095E6
0x18000987a  cmp     byte ptr [rcx+19h], 4
0x18000987e  jb      loc_180009669
0x180009884  mov     rcx, [rcx+10h]
0x180009888  lea     r8, WPP_6cb68c4060583735bafc290ec605627b_Traceguids
0x18000988f  mov     edx, 1Bh
0x180009894  mov     dword ptr [rsp+98h+var_78], ebp
0x180009898  call    WPP_SF_sd
0x18000989d  jmp     loc_180009669
```
