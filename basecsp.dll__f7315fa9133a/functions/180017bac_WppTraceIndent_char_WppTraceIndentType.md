# WppTraceIndent(char * *,_WppTraceIndentType)

- ea: `0x180017bac`
- end: `0x180017d15`
- name: `?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `99`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c6ac`
- `0x18000c868`
- `0x18000ce8c`
- `0x18000d024`
- `0x18000d130`
- `0x18000d2b0`
- `0x18000d5c0`
- `0x18000d904`
- `0x1800102a8`
- `0x180010760`
- `0x180010f10`
- `0x1800111d0`
- `0x180011470`
- `0x180011590`
- `0x180011ac0`
- `0x180011da0`
- `0x180012660`
- `0x180012800`
- `0x180012db0`
- `0x180012fa0`
- `0x180013420`
- `0x180013ab0`
- `0x180013ee0`
- `0x18001cd44`
- `0x18001ced4`
- `0x18001d064`
- `0x18001d1fc`
- `0x18001d568`
- `0x18001d88c`
- `0x18001da50`
- `0x18001db2c`
- `0x18001dbec`
- `0x18001dd04`
- `0x18001de28`
- `0x18001ded8`
- `0x18001e398`
- `0x18001e480`
- `0x18001e560`
- `0x18001e66c`
- `0x18001e86c`
- `0x18001eaa8`
- `0x18001ebf4`
- `0x18001ef0c`
- `0x18001efd8`
- `0x180020394`
- `0x180020824`
- `0x1800210a0`
- `0x1800212b0`
- `0x18002140c`
- `0x180021554`

## callees

- `0x180016d98`
- `0x180017bac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017bb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017bb8`

## pseudocode

```c
char *__fastcall WppTraceIndent(__int64 a1, unsigned int a2)
{
  DWORD CurrentThreadId; // eax
  unsigned __int64 i; // rdx
  __int64 v5; // rcx
  unsigned int v6; // r8d
  bool v7; // zf
  int v8; // ebx
  int v9; // edi
  unsigned __int64 v10; // rdx
  const char *v11; // r8
  char *result; // rax

  CurrentThreadId = GetCurrentThreadId();
  v5 = (int)`WppTraceIndent'::`2'::idxCurrentThread;
  if ( (_DWORD)`WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v5 = 0;
    `WppTraceIndent'::`2'::ThreadTable[0] = CurrentThreadId;
    LODWORD(`WppTraceIndent'::`2'::idxCurrentThread) = 0;
    dword_18003C554 = 0;
  }
  else
  {
    if ( (_DWORD)`WppTraceIndent'::`2'::idxCurrentThread == -2
      || `WppTraceIndent'::`2'::ThreadTable[2 * (int)`WppTraceIndent'::`2'::idxCurrentThread] != CurrentThreadId )
    {
      v6 = -1;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v7 = (_DWORD)i == 32;
        if ( (unsigned int)i >= 0x20 )
          break;
        if ( `WppTraceIndent'::`2'::ThreadTable[2 * (int)i] == CurrentThreadId )
        {
          v5 = (unsigned int)i;
          LODWORD(`WppTraceIndent'::`2'::idxCurrentThread) = i;
          v7 = (_DWORD)i == 32;
          break;
        }
        if ( v6 == -1 && !`WppTraceIndent'::`2'::ThreadTable[2 * (int)i] )
          v6 = i;
      }
      if ( v7 )
      {
        if ( v6 == -1 )
        {
          v5 = 4294967294LL;
        }
        else
        {
          v5 = v6;
          `WppTraceIndent'::`2'::ThreadTable[2 * v6] = CurrentThreadId;
          `WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1] = 0;
        }
        LODWORD(`WppTraceIndent'::`2'::idxCurrentThread) = v5;
      }
    }
    if ( (int)v5 < 0 )
    {
      v8 = 0;
      goto LABEL_24;
    }
  }
  if ( !a2 )
    ++`WppTraceIndent'::`2'::ThreadTable[2 * (int)v5 + 1];
  v8 = `WppTraceIndent'::`2'::ThreadTable[2 * (int)v5 + 1];
LABEL_24:
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v9 = 1;
    if ( v8 >= 1 )
    {
      do
      {
        if ( StringCbCatA((char *)v5, i, "..") )
          break;
        ++v9;
      }
      while ( v9 <= v8 );
      v5 = (unsigned int)`WppTraceIndent'::`2'::idxCurrentThread;
    }
  }
  v10 = a2;
  if ( !a2 )
  {
    v11 = ">";
    goto LABEL_36;
  }
  v10 = a2 - 1;
  if ( a2 == 1 )
  {
    v11 = "<";
    goto LABEL_36;
  }
  if ( a2 == 2 )
  {
    v11 = " ";
LABEL_36:
    StringCbCatA((char *)v5, v10, v11);
    LODWORD(v5) = (_DWORD)`WppTraceIndent'::`2'::idxCurrentThread;
  }
  if ( (int)v5 >= 0 && a2 == 1 )
  {
    v7 = `WppTraceIndent'::`2'::ThreadTable[2 * (int)v5 + 1]-- == 1;
    if ( v7 )
      `WppTraceIndent'::`2'::ThreadTable[2 * (int)v5] = 0;
  }
  result = &`WppTraceIndent'::`2'::szIndentPrefix;
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  return result;
}

```

## disassembly

```asm
0x180017bac  push    rbx
0x180017bae  push    rsi
0x180017baf  push    rdi
0x180017bb0  push    r14
0x180017bb2  sub     rsp, 28h
0x180017bb6  mov     esi, edx
0x180017bb8  call    cs:__imp_GetCurrentThreadId
0x180017bbe  movsxd  rcx, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180017bc5  lea     r14, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180017bcc  mov     r9d, eax
0x180017bcf  cmp     ecx, 0FFFFFFFFh
0x180017bd2  jnz     short loc_180017BEA
0x180017bd4  xor     ecx, ecx
0x180017bd6  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, eax; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180017bdc  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180017be2  mov     cs:dword_18003C554, ecx
0x180017be8  jmp     short loc_180017C53
0x180017bea  cmp     ecx, 0FFFFFFFEh
0x180017bed  jz      short loc_180017BF5
0x180017bef  cmp     [r14+rcx*8], r9d
0x180017bf3  jz      short loc_180017C4F
0x180017bf5  or      r8d, 0FFFFFFFFh
0x180017bf9  xor     edx, edx; unsigned __int64
0x180017bfb  cmp     edx, 20h ; ' '
0x180017bfe  jnb     short loc_180017C27
0x180017c00  movsxd  rax, edx
0x180017c03  cmp     [r14+rax*8], r9d
0x180017c07  jz      short loc_180017C1C
0x180017c09  cmp     r8d, 0FFFFFFFFh
0x180017c0d  jnz     short loc_180017C18
0x180017c0f  cmp     dword ptr [r14+rax*8], 0
0x180017c14  cmovz   r8d, edx
0x180017c18  inc     edx
0x180017c1a  jmp     short loc_180017BFB
0x180017c1c  mov     ecx, edx
0x180017c1e  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, edx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180017c24  cmp     edx, 20h ; ' '
0x180017c27  jnz     short loc_180017C4F
0x180017c29  cmp     r8d, 0FFFFFFFFh
0x180017c2d  jz      short loc_180017C44
0x180017c2f  movsxd  rax, r8d
0x180017c32  mov     ecx, r8d
0x180017c35  mov     [r14+rax*8], r9d
0x180017c39  mov     dword ptr [r14+rax*8+4], 0
0x180017c42  jmp     short loc_180017C49
0x180017c44  mov     ecx, 0FFFFFFFEh; char *
0x180017c49  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180017c4f  test    ecx, ecx
0x180017c51  js      short loc_180017C6D
0x180017c53  movsxd  rax, ecx
0x180017c56  test    esi, esi
0x180017c58  jnz     short loc_180017C66
0x180017c5a  inc     dword ptr [r14+rax*8+4]
0x180017c5f  mov     ebx, [r14+rax*8+4]
0x180017c64  jmp     short loc_180017C6F
0x180017c66  mov     ebx, [r14+rax*8+4]
0x180017c6b  jmp     short loc_180017C6F
0x180017c6d  xor     ebx, ebx
0x180017c6f  mov     rax, cs:WPP_GLOBAL_Control
0x180017c76  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180017c7d  test    byte ptr [rax+1Ch], 2
0x180017c81  jz      short loc_180017CAE
0x180017c83  cmp     byte ptr [rax+19h], 5
0x180017c87  jb      short loc_180017CAE
0x180017c89  mov     edi, 1
0x180017c8e  cmp     ebx, edi
0x180017c90  jl      short loc_180017CAE
0x180017c92  lea     r8, pszSrc; ".."
0x180017c99  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x180017c9e  test    eax, eax
0x180017ca0  jnz     short loc_180017CA8
0x180017ca2  inc     edi
0x180017ca4  cmp     edi, ebx
0x180017ca6  jle     short loc_180017C92
0x180017ca8  mov     ecx, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; char *
0x180017cae  mov     edx, esi; unsigned __int64
0x180017cb0  test    esi, esi
0x180017cb2  jz      short loc_180017CD0
0x180017cb4  sub     edx, 1
0x180017cb7  jz      short loc_180017CC7
0x180017cb9  cmp     edx, 1
0x180017cbc  jnz     short loc_180017CE2
0x180017cbe  lea     r8, asc_180034264; " "
0x180017cc5  jmp     short loc_180017CD7
0x180017cc7  lea     r8, asc_180034268; "<"
0x180017cce  jmp     short loc_180017CD7
0x180017cd0  lea     r8, asc_180034260; ">"
0x180017cd7  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x180017cdc  mov     ecx, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180017ce2  test    ecx, ecx
0x180017ce4  js      short loc_180017CFD
0x180017ce6  cmp     esi, 1
0x180017ce9  jnz     short loc_180017CFD
0x180017ceb  movsxd  rdx, ecx
0x180017cee  sub     [r14+rdx*8+4], esi
0x180017cf3  jnz     short loc_180017CFD
0x180017cf5  mov     dword ptr [r14+rdx*8], 0
0x180017cfd  lea     rax, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180017d04  mov     cs:?WPP_pszIndent@@3PEADEA, rax; char * WPP_pszIndent
0x180017d0b  add     rsp, 28h
0x180017d0f  pop     r14
0x180017d11  pop     rdi
0x180017d12  pop     rsi
0x180017d13  pop     rbx
0x180017d14  retn
```
