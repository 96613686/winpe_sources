# AslStringDuplicate

- ea: `0x180015a4c`
- end: `0x180015c7f`
- name: `AslStringDuplicate`
- size: `563`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001551c`

## callees

- `0x180015220`
- `0x180015a4c`
- `0x1800160ec`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180015c62`
- `ntdll!RtlFreeHeap` at `0x180015c62`
- `ntdll!RtlAllocateHeap` at `0x180015ba2`
- `ntdll!RtlAllocateHeap` at `0x180015ba2`

## string_xrefs

- `0x180015bf8`: `RtlStringCchCopyW failed [%x]`

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
  unsigned __int64 v15; // [rsp+90h] [rbp+18h]

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
      v15 = 0;
    else
      v15 = 0x7FFFFFFF - v6;
    if ( v5 < 0 )
    {
      v8 = "RtlStringCchLengthW failed [%x]";
      v9 = 590;
LABEL_13:
      AslLogCallPrintf(1, "AslStringDuplicate", v9, v8);
      goto LABEL_29;
    }
    v10 = v15 + 1;
    if ( v15 + 1 < v15 )
    {
      v10 = -1;
      v5 = -1073741675;
      v11 = -1;
    }
    else
    {
      v5 = 0;
      v11 = v15 + 1;
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
      v5 = RtlStringCchCopyW(Heap, v10, a2);
      if ( v5 < 0 )
      {
        v8 = "RtlStringCchCopyW failed [%x]";
        v9 = 632;
        goto LABEL_13;
      }
      *a1 = v4;
      v4 = 0;
      v5 = 0;
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
0x180015a4c  mov     rax, rsp
0x180015a4f  mov     [rax+8], rbx
0x180015a53  push    rsi
0x180015a54  push    rdi
0x180015a55  push    r12
0x180015a57  push    r14
0x180015a59  push    r15
0x180015a5b  sub     rsp, 50h
0x180015a5f  mov     r15, rdx
0x180015a62  mov     r12, rcx
0x180015a65  xor     edi, edi
0x180015a67  mov     [rax+18h], rdi
0x180015a6b  mov     esi, edi
0x180015a6d  mov     [rax-40h], rdi
0x180015a71  mov     [rcx], rdi
0x180015a74  mov     ebx, edi
0x180015a76  test    rdx, rdx
0x180015a79  jz      loc_180015C18
0x180015a7f  lea     r8, [rax+18h]
0x180015a83  mov     edx, 7FFFFFFFh
0x180015a88  mov     eax, edx
0x180015a8a  mov     [rsp+78h+var_30], rdx
0x180015a8f  mov     rcx, r15
0x180015a92  mov     [rsp+78h+var_38], rcx
0x180015a97  test    rax, rax
0x180015a9a  jz      short loc_180015AB4
0x180015a9c  cmp     [rcx], di
0x180015a9f  jz      short loc_180015AB4
0x180015aa1  add     rcx, 2
0x180015aa5  mov     [rsp+78h+var_38], rcx
0x180015aaa  dec     rax
0x180015aad  mov     [rsp+78h+var_30], rax
0x180015ab2  jmp     short loc_180015A97
0x180015ab4  mov     ecx, 0C000000Dh
0x180015ab9  test    rax, rax
0x180015abc  cmovz   ebx, ecx
0x180015abf  test    ebx, ebx
0x180015ac1  js      short loc_180015ACB
0x180015ac3  sub     rdx, rax
0x180015ac6  mov     [r8], rdx
0x180015ac9  jmp     short loc_180015ACE
0x180015acb  mov     [r8], rdi
0x180015ace  test    ebx, ebx
0x180015ad0  jns     short loc_180015AD5
0x180015ad2  mov     [r8], rdi
0x180015ad5  mov     [rsp+78h+var_48], ebx
0x180015ad9  test    ebx, ebx
0x180015adb  jns     short loc_180015B04
0x180015add  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x180015ae4  mov     r8d, 24Eh
0x180015aea  mov     [rsp+78h+var_58], ebx
0x180015aee  lea     rdx, aAslstringdupli; "AslStringDuplicate"
0x180015af5  mov     ecx, 1
0x180015afa  call    AslLogCallPrintf
0x180015aff  jmp     loc_180015C1C
0x180015b04  mov     rax, [rsp+78h+arg_10]
0x180015b0c  lea     r14, [rax+1]
0x180015b10  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180015b14  cmp     r14, rax
0x180015b17  jb      short loc_180015B28
0x180015b19  mov     [rsp+78h+arg_10], r14
0x180015b21  mov     ebx, edi
0x180015b23  mov     rdx, r14
0x180015b26  jmp     short loc_180015B3B
0x180015b28  mov     r14, rcx
0x180015b2b  mov     [rsp+78h+arg_10], rcx
0x180015b33  mov     ebx, 0C0000095h
0x180015b38  mov     rdx, rcx
0x180015b3b  mov     [rsp+78h+var_48], ebx
0x180015b3f  test    ebx, ebx
0x180015b41  jns     short loc_180015B52
0x180015b43  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x180015b4a  mov     r8d, 25Ah
0x180015b50  jmp     short loc_180015AEA
0x180015b52  mov     [rsp+78h+arg_18], rdi
0x180015b5a  mov     eax, 2
0x180015b5f  mul     rdx
0x180015b62  test    rdx, rdx
0x180015b65  jnz     short loc_180015B6B
0x180015b67  mov     ebx, edi
0x180015b69  jmp     short loc_180015B73
0x180015b6b  mov     rax, rcx
0x180015b6e  mov     ebx, 0C0000095h
0x180015b73  mov     [rsp+78h+var_48], ebx
0x180015b77  test    ebx, ebx
0x180015b79  jns     short loc_180015B8D
0x180015b7b  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x180015b82  mov     r8d, 260h
0x180015b88  jmp     loc_180015AEA
0x180015b8d  mov     rcx, gs:60h
0x180015b96  mov     r8, rax; Size
0x180015b99  mov     edx, 8; Flags
0x180015b9e  mov     rcx, [rcx+30h]; HeapHandle
0x180015ba2  call    cs:__imp_RtlAllocateHeap
0x180015ba8  mov     rsi, rax
0x180015bab  mov     [rsp+78h+var_40], rax
0x180015bb0  test    rax, rax
0x180015bb3  jnz     short loc_180015BDC
0x180015bb5  mov     ebx, 0C0000017h
0x180015bba  mov     [rsp+78h+var_48], ebx
0x180015bbe  lea     r9, aOutOfMemory; "Out of memory"
0x180015bc5  mov     r8d, 267h
0x180015bcb  lea     rdx, aAslstringdupli; "AslStringDuplicate"
0x180015bd2  lea     ecx, [rax+1]
0x180015bd5  call    AslLogCallPrintf
0x180015bda  jmp     short loc_180015C1C
0x180015bdc  mov     r8, r15
0x180015bdf  mov     rdx, r14
0x180015be2  mov     rcx, rsi
0x180015be5  call    RtlStringCchCopyW
0x180015bea  mov     ebx, eax
0x180015bec  mov     [rsp+78h+var_48], eax
0x180015bf0  test    eax, eax
0x180015bf2  jns     short loc_180015C0A
0x180015bf4  mov     [rsp+78h+var_58], eax
0x180015bf8  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x180015bff  mov     r8d, 278h
0x180015c05  jmp     loc_180015AEE
0x180015c0a  mov     [r12], rsi
0x180015c0e  mov     rsi, rdi
0x180015c11  mov     [rsp+78h+var_40], rdi
0x180015c16  mov     ebx, edi
0x180015c18  mov     [rsp+78h+var_48], ebx
0x180015c1c  jmp     short loc_180015C4B
0x180015c1e  mov     ebx, eax
0x180015c20  mov     [rsp+78h+var_48], eax
0x180015c24  mov     [rsp+78h+var_58], eax
0x180015c28  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x180015c2f  mov     r8d, 289h
0x180015c35  lea     rdx, aAslstringdupli; "AslStringDuplicate"
0x180015c3c  mov     ecx, 1
0x180015c41  call    AslLogCallPrintf
0x180015c46  mov     rsi, [rsp+78h+var_40]
0x180015c4b  test    rsi, rsi
0x180015c4e  jz      short loc_180015C68
0x180015c50  mov     rcx, gs:60h
0x180015c59  mov     r8, rsi; P
0x180015c5c  xor     edx, edx; Flags
0x180015c5e  mov     rcx, [rcx+30h]; HeapHandle
0x180015c62  call    cs:__imp_RtlFreeHeap
0x180015c68  mov     eax, ebx
0x180015c6a  mov     rbx, [rsp+78h+arg_0]
0x180015c72  add     rsp, 50h
0x180015c76  pop     r15
0x180015c78  pop     r14
0x180015c7a  pop     r12
0x180015c7c  pop     rdi
0x180015c7d  pop     rsi
0x180015c7e  retn
0x180016772  push    rbp
0x180016774  sub     rsp, 30h
0x180016778  mov     rbp, rdx
0x18001677b  mov     rax, [rcx]
0x18001677e  xor     ecx, ecx
0x180016780  cmp     dword ptr [rax], 0C00000FDh
0x180016786  setnz   cl
0x180016789  mov     [rbp+34h], ecx
0x18001678c  mov     eax, [rbp+34h]
0x18001678f  add     rsp, 30h
0x180016793  pop     rbp
0x180016794  retn
```
