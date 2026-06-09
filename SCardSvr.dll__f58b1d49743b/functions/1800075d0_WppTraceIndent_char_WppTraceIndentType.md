# WppTraceIndent(char * *,_WppTraceIndentType)

- ea: `0x1800075d0`
- end: `0x180007903`
- name: `?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z`
- size: `819`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `74`
- callee_count: `2`
- tags: ``

## callers

- `0x1800016e0`
- `0x180002584`
- `0x1800034c0`
- `0x180003580`
- `0x18000371c`
- `0x18000457c`
- `0x180005a10`
- `0x180005eac`
- `0x1800062f0`
- `0x1800065d0`
- `0x180006ad0`
- `0x180006c70`
- `0x180007060`
- `0x180007170`
- `0x180007230`
- `0x1800072f0`
- `0x1800073d0`
- `0x1800074b0`
- `0x180007910`
- `0x18000a310`
- `0x18000d9c0`
- `0x180010b3c`
- `0x180010ca0`
- `0x180010e90`
- `0x180011410`
- `0x180013740`
- `0x1800144e0`
- `0x180015120`
- `0x1800154e8`
- `0x180015604`
- `0x180017bd4`
- `0x180017e6c`
- `0x180017f44`
- `0x1800181dc`
- `0x1800183d0`
- `0x180019d68`
- `0x18001a01c`
- `0x18001a53c`
- `0x1800249e0`
- `0x18002a150`
- `0x18002b044`
- `0x18002b214`
- `0x18002b764`
- `0x18002b7d4`
- `0x18002b844`
- `0x18002b8b4`
- `0x18002b924`
- `0x18002b980`
- `0x18002b9dc`
- `0x18002ba38`

## callees

- `0x1800075d0`
- `0x18000e4b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075e5`

## pseudocode

```c
__int64 __fastcall WppTraceIndent(__int64 a1, int a2)
{
  DWORD CurrentThreadId; // eax
  unsigned __int64 v4; // rdx
  char *v5; // rcx
  int v6; // ebx
  DWORD v7; // r9d
  int v8; // edi
  __int64 result; // rax
  char *v10; // rdx
  __int64 v11; // rdx
  const char *v12; // r8
  __int64 v13; // rax
  char *v14; // r9
  __int64 v15; // rcx
  int v16; // r8d
  unsigned int i; // eax
  bool v18; // zf
  char *v19; // rdx
  __int64 v20; // rdx
  const char *v21; // r8
  __int64 v22; // rax
  __int64 v23; // rcx
  char *v24; // rdx
  __int64 v25; // rcx
  const char *v26; // r8
  char *v27; // rdx
  __int64 v28; // rax
  int j; // esi

  CurrentThreadId = GetCurrentThreadId();
  v6 = `WppTraceIndent'::`2'::idxCurrentThread;
  v7 = CurrentThreadId;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v6 = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    dword_18004BD54 = 0;
  }
  else
  {
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
      || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != CurrentThreadId )
    {
      v16 = -1;
      for ( i = 0; ; ++i )
      {
        v18 = i == 32;
        if ( i >= 0x20 )
          break;
        v5 = (char *)(int)i;
        v4 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)i);
        if ( (_DWORD)v4 == v7 )
        {
          v6 = i;
          `WppTraceIndent'::`2'::idxCurrentThread = i;
          v18 = i == 32;
          break;
        }
        if ( v16 == -1 && !(_DWORD)v4 )
          v16 = i;
      }
      if ( v18 )
      {
        if ( v16 == -1 )
        {
          v6 = -2;
          `WppTraceIndent'::`2'::idxCurrentThread = -2;
          goto LABEL_31;
        }
        v6 = v16;
        `WppTraceIndent'::`2'::idxCurrentThread = v16;
        *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v16) = v7;
        *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v16 + 1) = 0;
      }
    }
    if ( v6 < 0 )
    {
LABEL_31:
      v8 = 0;
      goto LABEL_8;
    }
  }
  if ( !a2 )
    ++*((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v6 + 1);
  v8 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v6 + 1);
LABEL_8:
  result = (__int64)WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix[0] = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    for ( j = 1; j <= v8; ++j )
    {
      result = StringCbCatA(v5, v4, "..");
      if ( (_DWORD)result )
        break;
    }
  }
  switch ( a2 )
  {
    case 1:
      v19 = `WppTraceIndent'::`2'::szIndentPrefix;
      result = 256;
      do
      {
        if ( !*v19 )
          break;
        ++v19;
        --result;
      }
      while ( result );
      v20 = 256 - result;
      if ( !result )
        goto LABEL_41;
      v21 = "<";
      v22 = 2147483646;
      v14 = &`WppTraceIndent'::`2'::szIndentPrefix[v20];
      v15 = 256 - v20;
      if ( 256 != v20 )
      {
        do
        {
          if ( !v22 )
            break;
          if ( !*v21 )
            break;
          *v14++ = *v21++;
          --v22;
          --v15;
        }
        while ( v15 );
      }
      break;
    case 0:
      v24 = `WppTraceIndent'::`2'::szIndentPrefix;
      result = 256;
      do
      {
        if ( !*v24 )
          break;
        ++v24;
        --result;
      }
      while ( result );
      if ( !result )
        goto LABEL_41;
      v25 = result;
      v26 = ">";
      v27 = &`WppTraceIndent'::`2'::szIndentPrefix[256 - result];
      v28 = 2147483646;
      do
      {
        if ( !v28 )
          break;
        if ( !*v26 )
          break;
        *v27++ = *v26++;
        --v28;
        --v25;
      }
      while ( v25 );
      result = (__int64)(v27 - 1);
      if ( v25 )
        result = (__int64)v27;
      goto LABEL_40;
    case 2:
      v10 = `WppTraceIndent'::`2'::szIndentPrefix;
      result = 256;
      do
      {
        if ( !*v10 )
          break;
        ++v10;
        --result;
      }
      while ( result );
      v11 = 256 - result;
      if ( !result )
        goto LABEL_41;
      v12 = " ";
      v13 = 2147483646;
      v14 = &`WppTraceIndent'::`2'::szIndentPrefix[v11];
      v15 = 256 - v11;
      if ( 256 != v11 )
      {
        do
        {
          if ( !v13 )
            break;
          if ( !*v12 )
            break;
          *v14++ = *v12++;
          --v13;
          --v15;
        }
        while ( v15 );
      }
      break;
    default:
      goto LABEL_41;
  }
  result = (__int64)(v14 - 1);
  if ( v15 )
    result = (__int64)v14;
LABEL_40:
  *(_BYTE *)result = 0;
LABEL_41:
  if ( v6 >= 0 && a2 == 1 )
  {
    result = v6;
    WPP_pszIndent = `WppTraceIndent'::`2'::szIndentPrefix;
    v23 = 8LL * v6;
    v18 = (*(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v23 + 4))-- == 1;
    if ( v18 )
      *(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v23) = 0;
  }
  else
  {
    WPP_pszIndent = `WppTraceIndent'::`2'::szIndentPrefix;
  }
  return result;
}

```

## disassembly

```asm
0x1800075d0  mov     [rsp+arg_18], rbx
0x1800075d5  push    rbp
0x1800075d6  push    r14
0x1800075d8  push    r15
0x1800075da  sub     rsp, 20h
0x1800075de  mov     [rsp+38h+arg_10], rdi
0x1800075e3  mov     ebp, edx
0x1800075e5  call    cs:__imp_GetCurrentThreadId
0x1800075eb  movsxd  rbx, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x1800075f2  lea     r15, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x1800075f9  xor     r14d, r14d
0x1800075fc  mov     r9d, eax
0x1800075ff  cmp     ebx, 0FFFFFFFFh
0x180007602  jz      loc_180007879
0x180007608  cmp     ebx, 0FFFFFFFEh
0x18000760b  jz      loc_1800076DC
0x180007611  cmp     [r15+rbx*8], eax
0x180007615  jnz     loc_1800076DC
0x18000761b  test    ebx, ebx
0x18000761d  js      loc_18000772C
0x180007623  movsxd  rax, ebx
0x180007626  test    ebp, ebp
0x180007628  jz      loc_180007850
0x18000762e  mov     edi, [r15+rax*8+4]
0x180007633  mov     rax, cs:WPP_GLOBAL_Control
0x18000763a  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180007641  test    byte ptr [rax+1Ch], 2
0x180007645  jnz     loc_180007895
0x18000764b  mov     rdi, [rsp+38h+arg_10]
0x180007650  lea     r10, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180007657  cmp     ebp, 1
0x18000765a  jz      loc_180007734
0x180007660  test    ebp, ebp
0x180007662  jz      loc_1800077E5
0x180007668  cmp     ebp, 2
0x18000766b  jnz     loc_180007786
0x180007671  mov     ecx, 100h
0x180007676  mov     rdx, r10
0x180007679  mov     eax, ecx
0x18000767b  cmp     byte ptr [rdx], 0
0x18000767e  jnz     loc_1800078CD
0x180007684  mov     rdx, rcx
0x180007687  sub     rdx, rax
0x18000768a  test    rax, rax
0x18000768d  cmovz   rdx, r14
0x180007691  jz      loc_180007786
0x180007697  lea     r8, asc_18003BC60; " "
0x18000769e  mov     eax, 7FFFFFFEh
0x1800076a3  lea     r9, [rdx+r10]
0x1800076a7  sub     rcx, rdx
0x1800076aa  jz      loc_180007778
0x1800076b0  test    rax, rax
0x1800076b3  jz      loc_180007778
0x1800076b9  movzx   edx, byte ptr [r8]
0x1800076bd  test    dl, dl
0x1800076bf  jz      loc_180007778
0x1800076c5  mov     [r9], dl
0x1800076c8  inc     r8
0x1800076cb  inc     r9
0x1800076ce  dec     rax
0x1800076d1  sub     rcx, 1
0x1800076d5  jnz     short loc_1800076B0
0x1800076d7  jmp     loc_180007778
0x1800076dc  mov     r8d, 0FFFFFFFFh
0x1800076e2  mov     eax, r14d
0x1800076e5  cmp     eax, 20h ; ' '
0x1800076e8  jnb     short loc_180007711
0x1800076ea  movsxd  rcx, eax
0x1800076ed  mov     edx, [r15+rcx*8]
0x1800076f1  cmp     edx, r9d
0x1800076f4  jz      short loc_180007706
0x1800076f6  cmp     r8d, 0FFFFFFFFh
0x1800076fa  jnz     short loc_180007702
0x1800076fc  test    edx, edx
0x1800076fe  cmovz   r8d, eax
0x180007702  inc     eax
0x180007704  jmp     short loc_1800076E5
0x180007706  mov     ebx, eax
0x180007708  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, eax; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000770e  cmp     eax, 20h ; ' '
0x180007711  jnz     loc_18000761B
0x180007717  cmp     r8d, 0FFFFFFFFh
0x18000771b  jnz     loc_18000785F
0x180007721  mov     ebx, 0FFFFFFFEh
0x180007726  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ebx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000772c  mov     edi, r14d
0x18000772f  jmp     loc_180007633
0x180007734  mov     ecx, 100h
0x180007739  mov     rdx, r10
0x18000773c  mov     eax, ecx
0x18000773e  cmp     byte ptr [rdx], 0
0x180007741  jnz     loc_1800078F1
0x180007747  mov     rdx, rcx
0x18000774a  sub     rdx, rax
0x18000774d  test    rax, rax
0x180007750  cmovz   rdx, r14
0x180007754  jz      short loc_180007786
0x180007756  lea     r8, asc_18003BC58; "<"
0x18000775d  mov     eax, 7FFFFFFEh
0x180007762  lea     r9, [rdx+r10]
0x180007766  sub     rcx, rdx
0x180007769  jz      short loc_180007778
0x18000776b  test    rax, rax
0x18000776e  jz      short loc_180007778
0x180007770  movzx   edx, byte ptr [r8]
0x180007774  test    dl, dl
0x180007776  jnz     short loc_1800077D1
0x180007778  test    rcx, rcx
0x18000777b  lea     rax, [r9-1]
0x18000777f  cmovnz  rax, r9
0x180007783  mov     byte ptr [rax], 0
0x180007786  test    ebx, ebx
0x180007788  js      short loc_1800077BB
0x18000778a  cmp     ebp, 1
0x18000778d  jnz     short loc_1800077BB
0x18000778f  movsxd  rax, ebx
0x180007792  mov     cs:?WPP_pszIndent@@3PEADEA, r10; char * WPP_pszIndent
0x180007799  lea     rcx, ds:0[rax*8]
0x1800077a1  sub     [rcx+r15+4], ebp
0x1800077a6  jnz     short loc_1800077C2
0x1800077a8  mov     [rcx+r15], r14d
0x1800077ac  mov     rbx, [rsp+38h+arg_18]
0x1800077b1  add     rsp, 20h
0x1800077b5  pop     r15
0x1800077b7  pop     r14
0x1800077b9  pop     rbp
0x1800077ba  retn
0x1800077bb  mov     cs:?WPP_pszIndent@@3PEADEA, r10; char * WPP_pszIndent
0x1800077c2  mov     rbx, [rsp+38h+arg_18]
0x1800077c7  add     rsp, 20h
0x1800077cb  pop     r15
0x1800077cd  pop     r14
0x1800077cf  pop     rbp
0x1800077d0  retn
0x1800077d1  mov     [r9], dl
0x1800077d4  inc     r8
0x1800077d7  inc     r9
0x1800077da  dec     rax
0x1800077dd  sub     rcx, 1
0x1800077e1  jnz     short loc_18000776B
0x1800077e3  jmp     short loc_180007778
0x1800077e5  mov     ecx, 100h
0x1800077ea  mov     rdx, r10
0x1800077ed  mov     eax, ecx
0x1800077ef  cmp     byte ptr [rdx], 0
0x1800077f2  jnz     loc_1800078DF
0x1800077f8  mov     rdx, rcx
0x1800077fb  sub     rdx, rax
0x1800077fe  test    rax, rax
0x180007801  cmovz   rdx, r14
0x180007805  jz      loc_180007786
0x18000780b  sub     rcx, rdx
0x18000780e  lea     r8, pszSrc; ">"
0x180007815  lea     rdx, [rdx+r10]
0x180007819  mov     eax, 7FFFFFFEh
0x18000781e  jz      short loc_180007840
0x180007820  test    rax, rax
0x180007823  jz      short loc_180007840
0x180007825  movzx   r9d, byte ptr [r8]
0x180007829  test    r9b, r9b
0x18000782c  jz      short loc_180007840
0x18000782e  mov     [rdx], r9b
0x180007831  inc     r8
0x180007834  inc     rdx
0x180007837  dec     rax
0x18000783a  sub     rcx, 1
0x18000783e  jnz     short loc_180007820
0x180007840  test    rcx, rcx
0x180007843  lea     rax, [rdx-1]
0x180007847  cmovnz  rax, rdx
0x18000784b  jmp     loc_180007783
0x180007850  inc     dword ptr [r15+rax*8+4]
0x180007855  mov     edi, [r15+rax*8+4]
0x18000785a  jmp     loc_180007633
0x18000785f  movsxd  rax, r8d
0x180007862  mov     ebx, r8d
0x180007865  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ebx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000786b  mov     [r15+rax*8], r9d
0x18000786f  mov     [r15+rax*8+4], r14d
0x180007874  jmp     loc_18000761B
0x180007879  mov     ebx, r14d
0x18000787c  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, r9d; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180007883  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ebx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180007889  mov     cs:dword_18004BD54, r14d
0x180007890  jmp     loc_180007623
0x180007895  cmp     byte ptr [rax+19h], 5
0x180007899  jb      loc_18000764B
0x18000789f  mov     [rsp+38h+arg_8], rsi
0x1800078a4  mov     esi, 1
0x1800078a9  cmp     edi, esi
0x1800078ab  jl      short loc_1800078C3
0x1800078ad  lea     r8, asc_1800400D4; ".."
0x1800078b4  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x1800078b9  test    eax, eax
0x1800078bb  jnz     short loc_1800078C3
0x1800078bd  inc     esi
0x1800078bf  cmp     esi, edi
0x1800078c1  jle     short loc_1800078AD
0x1800078c3  mov     rsi, [rsp+38h+arg_8]
0x1800078c8  jmp     loc_18000764B
0x1800078cd  inc     rdx
0x1800078d0  sub     rax, 1
0x1800078d4  jnz     loc_18000767B
0x1800078da  jmp     loc_180007684
0x1800078df  inc     rdx
0x1800078e2  sub     rax, 1
0x1800078e6  jnz     loc_1800077EF
0x1800078ec  jmp     loc_1800077F8
0x1800078f1  inc     rdx
0x1800078f4  sub     rax, 1
0x1800078f8  jnz     loc_18000773E
0x1800078fe  jmp     loc_180007747
```
