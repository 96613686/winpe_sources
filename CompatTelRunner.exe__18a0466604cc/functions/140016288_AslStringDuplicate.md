# AslStringDuplicate

- ea: `0x140016288`
- end: `0x1400164bb`
- name: `AslStringDuplicate`
- size: `563`
- prototype: `__int64 __fastcall(_QWORD *, _WORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400129e0`

## callees

- `0x1400135a4`
- `0x1400151b0`
- `0x140016288`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14001649e`
- `ntdll!RtlFreeHeap` at `0x14001649e`
- `ntdll!RtlAllocateHeap` at `0x1400163de`
- `ntdll!RtlAllocateHeap` at `0x1400163de`

## string_xrefs

- `0x140016434`: `RtlStringCchCopyW failed [%x]`

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
0x140016288  mov     rax, rsp
0x14001628b  mov     [rax+8], rbx
0x14001628f  push    rsi
0x140016290  push    rdi
0x140016291  push    r12
0x140016293  push    r14
0x140016295  push    r15
0x140016297  sub     rsp, 50h
0x14001629b  mov     r15, rdx
0x14001629e  mov     r12, rcx
0x1400162a1  xor     edi, edi
0x1400162a3  mov     [rax+18h], rdi
0x1400162a7  mov     esi, edi
0x1400162a9  mov     [rax-40h], rdi
0x1400162ad  mov     [rcx], rdi
0x1400162b0  mov     ebx, edi
0x1400162b2  test    rdx, rdx
0x1400162b5  jz      loc_140016454
0x1400162bb  lea     r8, [rax+18h]
0x1400162bf  mov     edx, 7FFFFFFFh
0x1400162c4  mov     eax, edx
0x1400162c6  mov     [rsp+78h+var_30], rdx
0x1400162cb  mov     rcx, r15
0x1400162ce  mov     [rsp+78h+var_38], rcx
0x1400162d3  test    rax, rax
0x1400162d6  jz      short loc_1400162F0
0x1400162d8  cmp     [rcx], di
0x1400162db  jz      short loc_1400162F0
0x1400162dd  add     rcx, 2
0x1400162e1  mov     [rsp+78h+var_38], rcx
0x1400162e6  dec     rax
0x1400162e9  mov     [rsp+78h+var_30], rax
0x1400162ee  jmp     short loc_1400162D3
0x1400162f0  mov     ecx, 0C000000Dh
0x1400162f5  test    rax, rax
0x1400162f8  cmovz   ebx, ecx
0x1400162fb  test    ebx, ebx
0x1400162fd  js      short loc_140016307
0x1400162ff  sub     rdx, rax
0x140016302  mov     [r8], rdx
0x140016305  jmp     short loc_14001630A
0x140016307  mov     [r8], rdi
0x14001630a  test    ebx, ebx
0x14001630c  jns     short loc_140016311
0x14001630e  mov     [r8], rdi
0x140016311  mov     [rsp+78h+var_48], ebx
0x140016315  test    ebx, ebx
0x140016317  jns     short loc_140016340
0x140016319  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x140016320  mov     r8d, 24Eh
0x140016326  mov     [rsp+78h+var_58], ebx
0x14001632a  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x140016331  mov     ecx, 1
0x140016336  call    AslLogCallPrintf
0x14001633b  jmp     loc_140016458
0x140016340  mov     rax, [rsp+78h+arg_10]
0x140016348  lea     r14, [rax+1]
0x14001634c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140016350  cmp     r14, rax
0x140016353  jb      short loc_140016364
0x140016355  mov     [rsp+78h+arg_10], r14
0x14001635d  mov     ebx, edi
0x14001635f  mov     rdx, r14
0x140016362  jmp     short loc_140016377
0x140016364  mov     r14, rcx
0x140016367  mov     [rsp+78h+arg_10], rcx
0x14001636f  mov     ebx, 0C0000095h
0x140016374  mov     rdx, rcx
0x140016377  mov     [rsp+78h+var_48], ebx
0x14001637b  test    ebx, ebx
0x14001637d  jns     short loc_14001638E
0x14001637f  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x140016386  mov     r8d, 25Ah
0x14001638c  jmp     short loc_140016326
0x14001638e  mov     [rsp+78h+arg_18], rdi
0x140016396  mov     eax, 2
0x14001639b  mul     rdx
0x14001639e  test    rdx, rdx
0x1400163a1  jnz     short loc_1400163A7
0x1400163a3  mov     ebx, edi
0x1400163a5  jmp     short loc_1400163AF
0x1400163a7  mov     rax, rcx
0x1400163aa  mov     ebx, 0C0000095h
0x1400163af  mov     [rsp+78h+var_48], ebx
0x1400163b3  test    ebx, ebx
0x1400163b5  jns     short loc_1400163C9
0x1400163b7  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x1400163be  mov     r8d, 260h
0x1400163c4  jmp     loc_140016326
0x1400163c9  mov     rcx, gs:60h
0x1400163d2  mov     r8, rax; Size
0x1400163d5  mov     edx, 8; Flags
0x1400163da  mov     rcx, [rcx+30h]; HeapHandle
0x1400163de  call    cs:__imp_RtlAllocateHeap
0x1400163e4  mov     rsi, rax
0x1400163e7  mov     [rsp+78h+var_40], rax
0x1400163ec  test    rax, rax
0x1400163ef  jnz     short loc_140016418
0x1400163f1  mov     ebx, 0C0000017h
0x1400163f6  mov     [rsp+78h+var_48], ebx
0x1400163fa  lea     r9, aOutOfMemory_0; "Out of memory"
0x140016401  mov     r8d, 267h
0x140016407  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x14001640e  lea     ecx, [rax+1]
0x140016411  call    AslLogCallPrintf
0x140016416  jmp     short loc_140016458
0x140016418  mov     r8, r15
0x14001641b  mov     rdx, r14
0x14001641e  mov     rcx, rsi
0x140016421  call    RtlStringCchCopyW
0x140016426  mov     ebx, eax
0x140016428  mov     [rsp+78h+var_48], eax
0x14001642c  test    eax, eax
0x14001642e  jns     short loc_140016446
0x140016430  mov     [rsp+78h+var_58], eax
0x140016434  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x14001643b  mov     r8d, 278h
0x140016441  jmp     loc_14001632A
0x140016446  mov     [r12], rsi
0x14001644a  mov     rsi, rdi
0x14001644d  mov     [rsp+78h+var_40], rdi
0x140016452  mov     ebx, edi
0x140016454  mov     [rsp+78h+var_48], ebx
0x140016458  jmp     short loc_140016487
0x14001645a  mov     ebx, eax
0x14001645c  mov     [rsp+78h+var_48], eax
0x140016460  mov     [rsp+78h+var_58], eax
0x140016464  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x14001646b  mov     r8d, 289h
0x140016471  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x140016478  mov     ecx, 1
0x14001647d  call    AslLogCallPrintf
0x140016482  mov     rsi, [rsp+78h+var_40]
0x140016487  test    rsi, rsi
0x14001648a  jz      short loc_1400164A4
0x14001648c  mov     rcx, gs:60h
0x140016495  mov     r8, rsi; P
0x140016498  xor     edx, edx; Flags
0x14001649a  mov     rcx, [rcx+30h]; HeapHandle
0x14001649e  call    cs:__imp_RtlFreeHeap
0x1400164a4  mov     eax, ebx
0x1400164a6  mov     rbx, [rsp+78h+arg_0]
0x1400164ae  add     rsp, 50h
0x1400164b2  pop     r15
0x1400164b4  pop     r14
0x1400164b6  pop     r12
0x1400164b8  pop     rdi
0x1400164b9  pop     rsi
0x1400164ba  retn
0x1400a7885  push    rbp
0x1400a7887  sub     rsp, 30h
0x1400a788b  mov     rbp, rdx
0x1400a788e  mov     rax, [rcx]
0x1400a7891  xor     ecx, ecx
0x1400a7893  cmp     dword ptr [rax], 0C00000FDh
0x1400a7899  setnz   cl
0x1400a789c  mov     [rbp+34h], ecx
0x1400a789f  mov     eax, [rbp+34h]
0x1400a78a2  add     rsp, 30h
0x1400a78a6  pop     rbp
0x1400a78a7  retn
```
