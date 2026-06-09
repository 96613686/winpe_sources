# BfspValidateBcdEntry

- ea: `0x180051084`
- end: `0x180051159`
- name: `BfspValidateBcdEntry`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004dc10`

## callees

- `0x18004f888`
- `0x180051084`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800510e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051141`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800510e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051141`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800510da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051133`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800510da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051133`
- `bcd!BcdCloseObject` at `0x180051128`
- `bcd!BcdCloseObject` at `0x180051128`
- `bcd!BcdOpenObject` at `0x1800510ad`
- `bcd!BcdOpenObject` at `0x1800510ad`

## pseudocode

```c
_BOOL8 __fastcall BfspValidateBcdEntry(__int64 a1, __int64 a2)
{
  void *v2; // rbx
  BOOL v3; // edi
  HANDLE ProcessHeap; // rax
  HANDLE v5; // rax
  __int64 v7; // [rsp+20h] [rbp-10h] BYREF
  int v8; // [rsp+50h] [rbp+20h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp+28h] BYREF

  v2 = 0;
  v8 = 0;
  lpMem = 0;
  v7 = 0;
  v3 = 0;
  if ( (int)BcdOpenObject(a1, a2, &v7) >= 0 )
  {
    if ( (int)BfspGetBcdElementData(v7, 285212673, &lpMem, &v8) < 0 )
      goto LABEL_6;
    v2 = lpMem;
    if ( !lpMem )
      goto LABEL_7;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    lpMem = 0;
    if ( (int)BfspGetBcdElementData(v7, 301989890, &lpMem, &v8) < 0 )
    {
LABEL_6:
      v2 = lpMem;
    }
    else
    {
      v2 = lpMem;
      v3 = lpMem != 0;
    }
  }
LABEL_7:
  if ( v7 )
    BcdCloseObject(v7);
  if ( v2 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v2);
  }
  return v3;
}

```

## disassembly

```asm
0x180051084  mov     [rsp-8+arg_0], rbx
0x180051089  mov     [rsp-8+arg_8], rdi
0x18005108e  push    rbp
0x18005108f  mov     rbp, rsp
0x180051092  sub     rsp, 30h
0x180051096  xor     ebx, ebx
0x180051098  mov     [rbp+arg_10], 0
0x18005109f  lea     r8, [rbp+var_10]
0x1800510a3  mov     [rbp+lpMem], rbx
0x1800510a7  mov     [rbp+var_10], rbx
0x1800510ab  xor     edi, edi
0x1800510ad  call    cs:__imp_BcdOpenObject
0x1800510b3  test    eax, eax
0x1800510b5  js      short loc_18005111F
0x1800510b7  mov     rcx, [rbp+var_10]
0x1800510bb  lea     r9, [rbp+arg_10]
0x1800510bf  lea     r8, [rbp+lpMem]
0x1800510c3  mov     edx, 11000001h
0x1800510c8  call    BfspGetBcdElementData
0x1800510cd  test    eax, eax
0x1800510cf  js      short loc_18005111B
0x1800510d1  mov     rbx, [rbp+lpMem]
0x1800510d5  test    rbx, rbx
0x1800510d8  jz      short loc_18005111F
0x1800510da  call    cs:__imp_GetProcessHeap
0x1800510e0  mov     r8, rbx; lpMem
0x1800510e3  xor     edx, edx; dwFlags
0x1800510e5  mov     rcx, rax; hHeap
0x1800510e8  call    cs:__imp_HeapFree
0x1800510ee  mov     rcx, [rbp+var_10]
0x1800510f2  lea     r9, [rbp+arg_10]
0x1800510f6  lea     r8, [rbp+lpMem]
0x1800510fa  mov     [rbp+lpMem], rdi
0x1800510fe  mov     edx, 12000002h
0x180051103  call    BfspGetBcdElementData
0x180051108  test    eax, eax
0x18005110a  js      short loc_18005111B
0x18005110c  mov     rbx, [rbp+lpMem]
0x180051110  lea     eax, [rdi+1]
0x180051113  test    rbx, rbx
0x180051116  cmovnz  edi, eax
0x180051119  jmp     short loc_18005111F
0x18005111b  mov     rbx, [rbp+lpMem]
0x18005111f  mov     rcx, [rbp+var_10]
0x180051123  test    rcx, rcx
0x180051126  jz      short loc_18005112E
0x180051128  call    cs:__imp_BcdCloseObject
0x18005112e  test    rbx, rbx
0x180051131  jz      short loc_180051147
0x180051133  call    cs:__imp_GetProcessHeap
0x180051139  mov     r8, rbx; lpMem
0x18005113c  xor     edx, edx; dwFlags
0x18005113e  mov     rcx, rax; hHeap
0x180051141  call    cs:__imp_HeapFree
0x180051147  mov     rbx, [rsp+30h+arg_0]
0x18005114c  mov     eax, edi
0x18005114e  mov     rdi, [rsp+30h+arg_8]
0x180051153  add     rsp, 30h
0x180051157  pop     rbp
0x180051158  retn
```
