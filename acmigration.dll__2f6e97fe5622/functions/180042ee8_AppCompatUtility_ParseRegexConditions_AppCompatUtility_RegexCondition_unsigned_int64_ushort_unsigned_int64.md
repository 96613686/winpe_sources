# AppCompatUtility::ParseRegexConditions(AppCompatUtility::_RegexCondition * &,unsigned __int64 &,ushort * *,unsigned __int64)

- ea: `0x180042ee8`
- end: `0x1800430ef`
- name: `?ParseRegexConditions@AppCompatUtility@@YAJAEAPEAU_RegexCondition@1@AEA_KPEAPEAG_K@Z`
- size: `519`
- prototype: `__int64 __fastcall(AppCompatUtility *__hidden this, struct AppCompatUtility::_RegexCondition **, unsigned __int64 *, unsigned __int16 **, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ef90`
- `0x180014580`
- `0x18001e440`

## callees

- `0x1800425fc`
- `0x1800426a8`
- `0x180042ee8`
- `0x1800543c0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180042f72`
- `ntdll!RtlAllocateHeap` at `0x180042f72`
- `ntdll!RtlFreeHeap` at `0x1800430dd`
- `ntdll!RtlFreeHeap` at `0x1800430dd`
- `SHLWAPI!StrToIntExW` at `0x180042fc5`
- `SHLWAPI!StrToIntExW` at `0x180042fc5`

## string_xrefs

- `0x180042f27`: `AppCompatUtility::ParseRegexConditions`
- `0x180042f8d`: `AppCompatUtility::ParseRegexConditions`
- `0x180043081`: `AppCompatUtility::ParseRegexConditions`
- `0x1800430aa`: `AppCompatUtility::ParseRegexConditions`

## pseudocode

```c
__int64 __fastcall AppCompatUtility::ParseRegexConditions(
        PVOID *this,
        struct AppCompatUtility::_RegexCondition **a2,
        unsigned __int64 *a3,
        unsigned __int64 a4)
{
  unsigned int v7; // ebp
  unsigned __int64 v8; // r9
  PVOID Heap; // rax
  __int64 v10; // rsi
  unsigned __int64 v11; // rbx
  __int64 v12; // r14
  const unsigned __int16 *v13; // rdx
  char *v14; // r13
  const unsigned __int16 *v15; // rdx
  char *v16; // r13
  unsigned __int64 v17; // rax

  *this = 0;
  *a2 = 0;
  v7 = -2147024809;
  if ( a4 )
  {
    if ( (a4 & 3) != 0 )
    {
      AslLogCallPrintf(
        1,
        "AppCompatUtility::ParseRegexConditions",
        1602,
        "Incorrect number of parameters. RegexConditions values must be a multiple of 4 and be always at last.");
    }
    else
    {
      v8 = a4 >> 2;
      *a2 = (struct AppCompatUtility::_RegexCondition *)v8;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 32 * v8);
      *this = Heap;
      if ( Heap )
      {
        v10 = 0;
        v11 = 0;
        if ( !*a2 )
          return 0;
        while ( 1 )
        {
          v12 = 32 * v11;
          if ( !StrToIntExW((PCWSTR)a3[v10], 1, (int *)*this + 8 * v11) )
            break;
          if ( *((int *)*this + 8 * v11) < 0 )
          {
            AslLogCallPrintf(
              1,
              "AppCompatUtility::ParseRegexConditions",
              1624,
              "Incorrect Group for Condition %zu. Less than 0: %d",
              v11,
              *((_DWORD *)*this + 8 * v11));
            goto LABEL_20;
          }
          *(_QWORD *)((char *)*this + v12 + 8) = a3[v10 + 1];
          v14 = (char *)*this;
          if ( !AppCompatUtility::IsValidVariableType(*(wchar_t **)((char *)*this + v12 + 8), v13) )
          {
            AslLogCallPrintf(
              1,
              "AppCompatUtility::ParseRegexConditions",
              1631,
              "Incorrect Type for Condition %zu. Must be 'int', 'string', 'double' or 'version'.",
              v11);
            goto LABEL_20;
          }
          *(_QWORD *)&v14[v12 + 16] = a3[v10 + 2];
          v16 = (char *)*this;
          if ( !AppCompatUtility::IsValidComparisonOperation(*(wchar_t **)((char *)*this + v12 + 16), v15) )
          {
            AslLogCallPrintf(
              1,
              "AppCompatUtility::ParseRegexConditions",
              1638,
              "Incorrect Operator for Condition %zu. Must be 'eq', 'ne', 'gt', 'gte', 'lt' or 'lte'.",
              v11);
            goto LABEL_20;
          }
          v17 = a3[v10 + 3];
          ++v11;
          v10 += 4;
          *(_QWORD *)&v16[v12 + 24] = v17;
          if ( v11 >= (unsigned __int64)*a2 )
            return 0;
        }
        AslLogCallPrintf(
          1,
          "AppCompatUtility::ParseRegexConditions",
          1619,
          "Failed to convert Group from string to integer: '%ls'.",
          a3[v10]);
      }
      else
      {
        AslLogCallPrintf(
          1,
          "AppCompatUtility::ParseRegexConditions",
          1610,
          "Failed to allocate memory for RegexConditions.");
        v7 = -2147024882;
      }
    }
  }
  else
  {
    AslLogCallPrintf(
      1,
      "AppCompatUtility::ParseRegexConditions",
      1596,
      "Incorrect number of parameters. Missing value for RegexConditions.");
  }
LABEL_20:
  *a2 = 0;
  if ( *this )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *this);
    *this = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180042ee8  push    rbx
0x180042eea  push    rbp
0x180042eeb  push    rsi
0x180042eec  push    rdi
0x180042eed  push    r12
0x180042eef  push    r13
0x180042ef1  push    r14
0x180042ef3  push    r15
0x180042ef5  sub     rsp, 38h
0x180042ef9  mov     qword ptr [rcx], 0
0x180042f00  mov     r12, r8
0x180042f03  mov     qword ptr [rdx], 0
0x180042f0a  mov     r15, rdx
0x180042f0d  mov     rdi, rcx
0x180042f10  mov     ebp, 80070057h
0x180042f15  test    r9, r9
0x180042f18  jnz     short loc_180042F3D
0x180042f1a  lea     r9, aIncorrectNumbe_3; "Incorrect number of parameters. Missing"...
0x180042f21  mov     r8d, 63Ch
0x180042f27  lea     rdx, aAppcompatutili_0; "AppCompatUtility::ParseRegexConditions"
0x180042f2e  mov     ecx, 1
0x180042f33  call    AslLogCallPrintf
0x180042f38  jmp     loc_1800430BB
0x180042f3d  test    r9b, 3
0x180042f41  jz      short loc_180042F52
0x180042f43  lea     r9, aIncorrectNumbe; "Incorrect number of parameters. RegexCo"...
0x180042f4a  mov     r8d, 642h
0x180042f50  jmp     short loc_180042F27
0x180042f52  shr     r9, 2
0x180042f56  mov     [rdx], r9
0x180042f59  mov     edx, 8; Flags
0x180042f5e  mov     rcx, gs:60h
0x180042f67  shl     r9, 5
0x180042f6b  mov     r8, r9; Size
0x180042f6e  mov     rcx, [rcx+30h]; HeapHandle
0x180042f72  call    cs:__imp_RtlAllocateHeap
0x180042f78  mov     [rdi], rax
0x180042f7b  test    rax, rax
0x180042f7e  jnz     short loc_180042FA6
0x180042f80  lea     r9, aFailedToAlloca_8; "Failed to allocate memory for RegexCond"...
0x180042f87  mov     r8d, 64Ah
0x180042f8d  lea     rdx, aAppcompatutili_0; "AppCompatUtility::ParseRegexConditions"
0x180042f94  lea     ecx, [rax+1]
0x180042f97  call    AslLogCallPrintf
0x180042f9c  mov     ebp, 8007000Eh
0x180042fa1  jmp     loc_1800430BB
0x180042fa6  xor     esi, esi
0x180042fa8  xor     ebx, ebx
0x180042faa  cmp     [r15], rbx
0x180042fad  jbe     short loc_18004302E
0x180042faf  mov     r8, [rdi]
0x180042fb2  mov     r14, rbx
0x180042fb5  mov     rcx, [r12+rsi*8]; pszString
0x180042fb9  mov     edx, 1; dwFlags
0x180042fbe  shl     r14, 5
0x180042fc2  add     r8, r14; piRet
0x180042fc5  call    cs:__imp_StrToIntExW
0x180042fcb  test    eax, eax
0x180042fcd  jz      loc_180043094
0x180042fd3  mov     rcx, [rdi]
0x180042fd6  mov     eax, [rcx+r14]
0x180042fda  test    eax, eax
0x180042fdc  js      loc_18004306B
0x180042fe2  mov     rax, [r12+rsi*8+8]
0x180042fe7  mov     [rcx+r14+8], rax
0x180042fec  mov     r13, [rdi]
0x180042fef  mov     rcx, [r14+r13+8]; String1
0x180042ff4  call    ?IsValidVariableType@AppCompatUtility@@YA_NPEBG@Z; AppCompatUtility::IsValidVariableType(ushort const *)
0x180042ff9  test    al, al
0x180042ffb  jz      short loc_180043057
0x180042ffd  mov     rax, [r12+rsi*8+10h]
0x180043002  mov     [r14+r13+10h], rax
0x180043007  mov     r13, [rdi]
0x18004300a  mov     rcx, [r14+r13+10h]; String1
0x18004300f  call    ?IsValidComparisonOperation@AppCompatUtility@@YA_NPEBG@Z; AppCompatUtility::IsValidComparisonOperation(ushort const *)
0x180043014  test    al, al
0x180043016  jz      short loc_180043043
0x180043018  mov     rax, [r12+rsi*8+18h]
0x18004301d  inc     rbx
0x180043020  add     rsi, 4
0x180043024  mov     [r14+r13+18h], rax
0x180043029  cmp     rbx, [r15]
0x18004302c  jb      short loc_180042FAF
0x18004302e  xor     ebp, ebp
0x180043030  mov     eax, ebp
0x180043032  add     rsp, 38h
0x180043036  pop     r15
0x180043038  pop     r14
0x18004303a  pop     r13
0x18004303c  pop     r12
0x18004303e  pop     rdi
0x18004303f  pop     rsi
0x180043040  pop     rbp
0x180043041  pop     rbx
0x180043042  retn
0x180043043  mov     [rsp+78h+var_58], rbx
0x180043048  lea     r9, aIncorrectOpera; "Incorrect Operator for Condition %zu. M"...
0x18004304f  mov     r8d, 666h
0x180043055  jmp     short loc_1800430AA
0x180043057  mov     [rsp+78h+var_58], rbx
0x18004305c  lea     r9, aIncorrectTypeF; "Incorrect Type for Condition %zu. Must "...
0x180043063  mov     r8d, 65Fh
0x180043069  jmp     short loc_1800430AA
0x18004306b  mov     [rsp+78h+var_50], eax
0x18004306f  lea     r9, aIncorrectGroup; "Incorrect Group for Condition %zu. Less"...
0x180043076  mov     r8d, 658h
0x18004307c  mov     [rsp+78h+var_58], rbx
0x180043081  lea     rdx, aAppcompatutili_0; "AppCompatUtility::ParseRegexConditions"
0x180043088  mov     ecx, 1
0x18004308d  call    AslLogCallPrintf
0x180043092  jmp     short loc_1800430BB
0x180043094  mov     rax, [r12+rsi*8]
0x180043098  lea     r9, aFailedToConver_19; "Failed to convert Group from string to "...
0x18004309f  mov     [rsp+78h+var_58], rax
0x1800430a4  mov     r8d, 653h
0x1800430aa  lea     rdx, aAppcompatutili_0; "AppCompatUtility::ParseRegexConditions"
0x1800430b1  mov     ecx, 1
0x1800430b6  call    AslLogCallPrintf
0x1800430bb  mov     qword ptr [r15], 0
0x1800430c2  mov     r8, [rdi]; P
0x1800430c5  test    r8, r8
0x1800430c8  jz      loc_180043030
0x1800430ce  mov     rcx, gs:60h
0x1800430d7  xor     edx, edx; Flags
0x1800430d9  mov     rcx, [rcx+30h]; HeapHandle
0x1800430dd  call    cs:__imp_RtlFreeHeap
0x1800430e3  mov     qword ptr [rdi], 0
0x1800430ea  jmp     loc_180043030
```
