# SdbGetMergeRedirectPath

- ea: `0x14004224c`
- end: `0x1400423c9`
- name: `SdbGetMergeRedirectPath`
- size: `381`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140042ad4`
- `0x1400591c4`

## callees

- `0x14003e364`
- `0x140041638`
- `0x140041f48`
- `0x14004224c`
- `0x140045d44`

## string_xrefs

- `0x1400422df`: `SdbpGetMergeRedirectPathInternal failed[%x]`
- `0x1400422d8`: `SdbGetMergeRedirectPath`
- `0x140042326`: `SdbGetMergeRedirectPath`

## pseudocode

```c
__int64 __fastcall SdbGetMergeRedirectPath(_QWORD *a1, BOOL *a2, int a3, const wchar_t *a4)
{
  __int64 v9; // rcx
  int MergeRedirectPathInternal; // ebx
  __int64 v11; // rcx
  void *v12; // rdx
  BOOL v13; // edi
  const wchar_t *FileNamePart; // rax
  int v15; // eax
  void *v16[2]; // [rsp+30h] [rbp-10h] BYREF
  int v17; // [rsp+70h] [rbp+30h] BYREF

  v17 = 0;
  v16[0] = 0;
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( a2 )
    *a2 = 0;
  MergeRedirectPathInternal = SdbpGetMergeRedirectPathInternal(v16, &v17, 1, a4);
  if ( (int)(MergeRedirectPathInternal + 0x80000000) >= 0 && MergeRedirectPathInternal != -1073741772 )
  {
    AslLogCallPrintf(
      1,
      "SdbGetMergeRedirectPath",
      2134,
      "SdbpGetMergeRedirectPathInternal failed[%x]",
      MergeRedirectPathInternal);
LABEL_8:
    v12 = v16[0];
    goto LABEL_26;
  }
  v13 = 0;
  if ( MergeRedirectPathInternal >= 0 )
    v13 = v17 != 0;
  if ( !a3 || !v13 )
  {
    if ( v16[0] )
      AslFree(v9, v16[0]);
    v15 = SdbpGetMergeRedirectPathInternal(v16, 0, 0, a4);
    MergeRedirectPathInternal = v15;
    if ( v15 < 0 )
    {
      if ( v15 != -1073741772 )
        AslLogCallPrintf(1, "SdbGetMergeRedirectPath", 2149, "SdbpGetMergeRedirectPathInternal failed[%x]", v15);
      goto LABEL_8;
    }
    v12 = v16[0];
LABEL_23:
    *a1 = v12;
    v12 = 0;
    if ( a2 )
      *a2 = v13;
    MergeRedirectPathInternal = 0;
    goto LABEL_26;
  }
  FileNamePart = AslPathGetFileNamePart(a4);
  AslLogCallPrintf(
    1,
    "SdbGetMergeRedirectPath",
    2158,
    "Handled Error: MergeSdb staged deletion feature was used, probably to prevent sdb mismatch error. SdbName: [%ls].",
    FileNamePart);
  v12 = v16[0];
  if ( v16[0] )
  {
    if ( MergeRedirectPathInternal < 0 )
    {
LABEL_26:
      if ( v12 )
        AslFree(v11, v12);
      return (unsigned int)MergeRedirectPathInternal;
    }
    goto LABEL_23;
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x14004224c  mov     [rsp-28h+arg_8], rbx
0x140042251  mov     [rsp-28h+arg_10], rsi
0x140042256  push    rbp
0x140042257  push    rdi
0x140042258  push    r12
0x14004225a  push    r14
0x14004225c  push    r15
0x14004225e  mov     rbp, rsp
0x140042261  sub     rsp, 40h
0x140042265  mov     [rbp+arg_0], 0
0x14004226c  mov     r15, r9
0x14004226f  mov     [rbp+var_10], 0
0x140042277  mov     r12d, r8d
0x14004227a  mov     rsi, rdx
0x14004227d  mov     r14, rcx
0x140042280  test    rcx, rcx
0x140042283  jnz     short loc_14004228F
0x140042285  mov     eax, 0C00000EFh
0x14004228a  jmp     loc_1400423AF
0x14004228f  mov     qword ptr [rcx], 0
0x140042296  test    rsi, rsi
0x140042299  jz      short loc_1400422A1
0x14004229b  mov     dword ptr [rdx], 0
0x1400422a1  mov     edi, 1
0x1400422a6  lea     rdx, [rbp+arg_0]
0x1400422aa  mov     r8d, edi
0x1400422ad  lea     rcx, [rbp+var_10]
0x1400422b1  call    SdbpGetMergeRedirectPathInternal
0x1400422b6  mov     ebx, eax
0x1400422b8  mov     eax, 80000000h
0x1400422bd  lea     edx, [rbx+rax]
0x1400422c0  test    eax, edx
0x1400422c2  jnz     short loc_1400422F4
0x1400422c4  cmp     ebx, 0C0000034h
0x1400422ca  jz      short loc_1400422F4
0x1400422cc  mov     dword ptr [rsp+40h+var_20], ebx
0x1400422d0  mov     r8d, 856h
0x1400422d6  mov     ecx, edi
0x1400422d8  lea     rdx, aSdbgetmergered_0; "SdbGetMergeRedirectPath"
0x1400422df  lea     r9, aSdbpgetmergere_0; "SdbpGetMergeRedirectPathInternal failed"...
0x1400422e6  call    AslLogCallPrintf
0x1400422eb  mov     rdx, [rbp+var_10]
0x1400422ef  jmp     loc_1400423A3
0x1400422f4  xor     edi, edi
0x1400422f6  test    ebx, ebx
0x1400422f8  js      short loc_140042303
0x1400422fa  cmp     [rbp+arg_0], edi
0x1400422fd  lea     eax, [rdi+1]
0x140042300  cmovnz  edi, eax
0x140042303  test    r12d, r12d
0x140042306  jz      short loc_14004234D
0x140042308  test    edi, edi
0x14004230a  jz      short loc_14004234D
0x14004230c  mov     rcx, r15
0x14004230f  call    AslPathGetFileNamePart
0x140042314  lea     r9, aHandledErrorMe_0; "Handled Error: MergeSdb staged deletion"...
0x14004231b  mov     [rsp+40h+var_20], rax
0x140042320  mov     r8d, 86Eh
0x140042326  lea     rdx, aSdbgetmergered_0; "SdbGetMergeRedirectPath"
0x14004232d  mov     ecx, 1
0x140042332  call    AslLogCallPrintf
0x140042337  mov     rdx, [rbp+var_10]
0x14004233b  test    rdx, rdx
0x14004233e  jnz     short loc_140042347
0x140042340  mov     ebx, 0C0000034h
0x140042345  jmp     short loc_1400423AD
0x140042347  test    ebx, ebx
0x140042349  jns     short loc_140042395
0x14004234b  jmp     short loc_1400423A3
0x14004234d  mov     rdx, [rbp+var_10]
0x140042351  test    rdx, rdx
0x140042354  jz      short loc_14004235B
0x140042356  call    AslFree
0x14004235b  mov     r9, r15
0x14004235e  lea     rcx, [rbp+var_10]
0x140042362  xor     r8d, r8d
0x140042365  xor     edx, edx
0x140042367  call    SdbpGetMergeRedirectPathInternal
0x14004236c  mov     ebx, eax
0x14004236e  test    eax, eax
0x140042370  jns     short loc_140042391
0x140042372  cmp     eax, 0C0000034h
0x140042377  jz      loc_1400422EB
0x14004237d  mov     dword ptr [rsp+40h+var_20], eax
0x140042381  mov     r8d, 865h
0x140042387  mov     ecx, 1
0x14004238c  jmp     loc_1400422D8
0x140042391  mov     rdx, [rbp+var_10]
0x140042395  mov     [r14], rdx
0x140042398  xor     edx, edx
0x14004239a  test    rsi, rsi
0x14004239d  jz      short loc_1400423A1
0x14004239f  mov     [rsi], edi
0x1400423a1  xor     ebx, ebx
0x1400423a3  test    rdx, rdx
0x1400423a6  jz      short loc_1400423AD
0x1400423a8  call    AslFree
0x1400423ad  mov     eax, ebx
0x1400423af  lea     r11, [rsp+40h+var_s0]
0x1400423b4  mov     rbx, [r11+38h]
0x1400423b8  mov     rsi, [r11+40h]
0x1400423bc  mov     rsp, r11
0x1400423bf  pop     r15
0x1400423c1  pop     r14
0x1400423c3  pop     r12
0x1400423c5  pop     rdi
0x1400423c6  pop     rbp
0x1400423c7  retn
```
