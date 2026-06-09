# AslStringDuplicate

- ea: `0x1800314e4`
- end: `0x180031717`
- name: `AslStringDuplicate`
- size: `563`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180030fb4`

## callees

- `0x180030f40`
- `0x1800314e4`
- `0x180031a3c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18003163a`
- `ntdll!RtlAllocateHeap` at `0x18003163a`
- `ntdll!RtlFreeHeap` at `0x1800316fa`
- `ntdll!RtlFreeHeap` at `0x1800316fa`

## string_xrefs

- `0x180031690`: `RtlStringCchCopyW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslStringDuplicate(_QWORD *a1, _WORD *a2)
{
  void *v4; // rsi
  int v5; // ebx
  __int64 v6; // rax
  _WORD *i; // rcx
  const char *v8; // r9
  __int64 v9; // r8
  __int64 v10; // r14
  unsigned __int64 v11; // rdx
  SIZE_T v12; // rax
  PVOID Heap; // rax
  int v14; // eax
  unsigned __int64 v16; // [rsp+90h] [rbp+18h]

  v4 = 0;
  *a1 = 0;
  v5 = 0;
  if ( a2 )
  {
    v6 = 0x7FFFFFFF;
    for ( i = a2; v6 && *i; ++i )
      --v6;
    if ( !v6 )
      v5 = -1073741811;
    if ( v5 < 0 )
      v16 = 0;
    else
      v16 = 0x7FFFFFFF - v6;
    if ( v5 < 0 )
    {
      v8 = "RtlStringCchLengthW failed [%x]";
      v9 = 590;
LABEL_13:
      AslLogCallPrintf(1, "AslStringDuplicate", v9, v8, v5);
      goto LABEL_29;
    }
    v10 = v16 + 1;
    if ( v16 + 1 < v16 )
    {
      v10 = -1;
      v5 = -1073741675;
      v11 = -1;
    }
    else
    {
      v5 = 0;
      v11 = v16 + 1;
    }
    if ( v5 < 0 )
    {
      v8 = "SIZE_T arithmetic failed [%x]";
      v9 = 602;
      goto LABEL_13;
    }
    v12 = 2 * v11;
    if ( is_mul_ok(v11, 2u) )
    {
      v5 = 0;
    }
    else
    {
      v12 = -1;
      v5 = -1073741675;
    }
    if ( v5 < 0 )
    {
      v8 = "SIZE_T arithmetic failed [%x]";
      v9 = 608;
      goto LABEL_13;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v12);
    v4 = Heap;
    if ( Heap )
    {
      v14 = RtlStringCchCopyW(Heap, v10, a2);
      v5 = v14;
      if ( v14 >= 0 )
      {
        *a1 = v4;
        v4 = 0;
        v5 = 0;
      }
      else
      {
        AslLogCallPrintf(1, "AslStringDuplicate", 632, "RtlStringCchCopyW failed [%x]", v14);
      }
    }
    else
    {
      v5 = -1073741801;
      AslLogCallPrintf(1, "AslStringDuplicate", 615, "Out of memory");
    }
  }
LABEL_29:
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800314e4  mov     rax, rsp
0x1800314e7  mov     [rax+8], rbx
0x1800314eb  push    rsi
0x1800314ec  push    rdi
0x1800314ed  push    r12
0x1800314ef  push    r14
0x1800314f1  push    r15
0x1800314f3  sub     rsp, 50h
0x1800314f7  mov     r15, rdx
0x1800314fa  mov     r12, rcx
0x1800314fd  xor     edi, edi
0x1800314ff  mov     [rax+18h], rdi
0x180031503  mov     esi, edi
0x180031505  mov     [rax-40h], rdi
0x180031509  mov     [rcx], rdi
0x18003150c  mov     ebx, edi
0x18003150e  test    rdx, rdx
0x180031511  jz      loc_1800316B0
0x180031517  lea     r8, [rax+18h]
0x18003151b  mov     edx, 7FFFFFFFh
0x180031520  mov     eax, edx
0x180031522  mov     [rsp+78h+var_30], rdx
0x180031527  mov     rcx, r15
0x18003152a  mov     [rsp+78h+var_38], rcx
0x18003152f  test    rax, rax
0x180031532  jz      short loc_18003154C
0x180031534  cmp     [rcx], di
0x180031537  jz      short loc_18003154C
0x180031539  add     rcx, 2
0x18003153d  mov     [rsp+78h+var_38], rcx
0x180031542  dec     rax
0x180031545  mov     [rsp+78h+var_30], rax
0x18003154a  jmp     short loc_18003152F
0x18003154c  mov     ecx, 0C000000Dh
0x180031551  test    rax, rax
0x180031554  cmovz   ebx, ecx
0x180031557  test    ebx, ebx
0x180031559  js      short loc_180031563
0x18003155b  sub     rdx, rax
0x18003155e  mov     [r8], rdx
0x180031561  jmp     short loc_180031566
0x180031563  mov     [r8], rdi
0x180031566  test    ebx, ebx
0x180031568  jns     short loc_18003156D
0x18003156a  mov     [r8], rdi
0x18003156d  mov     [rsp+78h+var_48], ebx
0x180031571  test    ebx, ebx
0x180031573  jns     short loc_18003159C
0x180031575  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x18003157c  mov     r8d, 24Eh
0x180031582  mov     [rsp+78h+var_58], ebx
0x180031586  lea     rdx, aAslstringdupli; "AslStringDuplicate"
0x18003158d  mov     ecx, 1
0x180031592  call    AslLogCallPrintf
0x180031597  jmp     loc_1800316B4
0x18003159c  mov     rax, [rsp+78h+arg_10]
0x1800315a4  lea     r14, [rax+1]
0x1800315a8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800315ac  cmp     r14, rax
0x1800315af  jb      short loc_1800315C0
0x1800315b1  mov     [rsp+78h+arg_10], r14
0x1800315b9  mov     ebx, edi
0x1800315bb  mov     rdx, r14
0x1800315be  jmp     short loc_1800315D3
0x1800315c0  mov     r14, rcx
0x1800315c3  mov     [rsp+78h+arg_10], rcx
0x1800315cb  mov     ebx, 0C0000095h
0x1800315d0  mov     rdx, rcx
0x1800315d3  mov     [rsp+78h+var_48], ebx
0x1800315d7  test    ebx, ebx
0x1800315d9  jns     short loc_1800315EA
0x1800315db  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x1800315e2  mov     r8d, 25Ah
0x1800315e8  jmp     short loc_180031582
0x1800315ea  mov     [rsp+78h+arg_18], rdi
0x1800315f2  mov     eax, 2
0x1800315f7  mul     rdx
0x1800315fa  test    rdx, rdx
0x1800315fd  jnz     short loc_180031603
0x1800315ff  mov     ebx, edi
0x180031601  jmp     short loc_18003160B
0x180031603  mov     rax, rcx
0x180031606  mov     ebx, 0C0000095h
0x18003160b  mov     [rsp+78h+var_48], ebx
0x18003160f  test    ebx, ebx
0x180031611  jns     short loc_180031625
0x180031613  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x18003161a  mov     r8d, 260h
0x180031620  jmp     loc_180031582
0x180031625  mov     rcx, gs:60h
0x18003162e  mov     r8, rax; Size
0x180031631  mov     edx, 8; Flags
0x180031636  mov     rcx, [rcx+30h]; HeapHandle
0x18003163a  call    cs:__imp_RtlAllocateHeap
0x180031640  mov     rsi, rax
0x180031643  mov     [rsp+78h+var_40], rax
0x180031648  test    rax, rax
0x18003164b  jnz     short loc_180031674
0x18003164d  mov     ebx, 0C0000017h
0x180031652  mov     [rsp+78h+var_48], ebx
0x180031656  lea     r9, aOutOfMemory; "Out of memory"
0x18003165d  mov     r8d, 267h
0x180031663  lea     rdx, aAslstringdupli; "AslStringDuplicate"
0x18003166a  lea     ecx, [rax+1]
0x18003166d  call    AslLogCallPrintf
0x180031672  jmp     short loc_1800316B4
0x180031674  mov     r8, r15
0x180031677  mov     rdx, r14
0x18003167a  mov     rcx, rsi
0x18003167d  call    RtlStringCchCopyW
0x180031682  mov     ebx, eax
0x180031684  mov     [rsp+78h+var_48], eax
0x180031688  test    eax, eax
0x18003168a  jns     short loc_1800316A2
0x18003168c  mov     [rsp+78h+var_58], eax
0x180031690  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x180031697  mov     r8d, 278h
0x18003169d  jmp     loc_180031586
0x1800316a2  mov     [r12], rsi
0x1800316a6  mov     rsi, rdi
0x1800316a9  mov     [rsp+78h+var_40], rdi
0x1800316ae  mov     ebx, edi
0x1800316b0  mov     [rsp+78h+var_48], ebx
0x1800316b4  jmp     short loc_1800316E3
0x1800316b6  mov     ebx, eax
0x1800316b8  mov     [rsp+78h+var_48], eax
0x1800316bc  mov     [rsp+78h+var_58], eax
0x1800316c0  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x1800316c7  mov     r8d, 289h
0x1800316cd  lea     rdx, aAslstringdupli; "AslStringDuplicate"
0x1800316d4  mov     ecx, 1
0x1800316d9  call    AslLogCallPrintf
0x1800316de  mov     rsi, [rsp+78h+var_40]
0x1800316e3  test    rsi, rsi
0x1800316e6  jz      short loc_180031700
0x1800316e8  mov     rcx, gs:60h
0x1800316f1  mov     r8, rsi; P
0x1800316f4  xor     edx, edx; Flags
0x1800316f6  mov     rcx, [rcx+30h]; HeapHandle
0x1800316fa  call    cs:__imp_RtlFreeHeap
0x180031700  mov     eax, ebx
0x180031702  mov     rbx, [rsp+78h+arg_0]
0x18003170a  add     rsp, 50h
0x18003170e  pop     r15
0x180031710  pop     r14
0x180031712  pop     r12
0x180031714  pop     rdi
0x180031715  pop     rsi
0x180031716  retn
0x180032de6  push    rbp
0x180032de8  sub     rsp, 30h
0x180032dec  mov     rbp, rdx
0x180032def  mov     rax, [rcx]
0x180032df2  xor     ecx, ecx
0x180032df4  cmp     dword ptr [rax], 0C00000FDh
0x180032dfa  setnz   cl
0x180032dfd  mov     [rbp+34h], ecx
0x180032e00  mov     eax, [rbp+34h]
0x180032e03  add     rsp, 30h
0x180032e07  pop     rbp
0x180032e08  retn
```
