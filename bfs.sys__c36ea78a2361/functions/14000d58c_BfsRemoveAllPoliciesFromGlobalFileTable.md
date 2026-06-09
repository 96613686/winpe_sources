# BfsRemoveAllPoliciesFromGlobalFileTable

- ea: `0x14000d58c`
- end: `0x14000d6e8`
- name: `BfsRemoveAllPoliciesFromGlobalFileTable`
- size: `348`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000a64c`

## callees

- `0x140001008`
- `0x140006330`
- `0x14000d58c`
- `0x14000d734`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d69b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d69b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6ac`

## pseudocode

```c
__int64 __fastcall BfsRemoveAllPoliciesFromGlobalFileTable(__int64 a1, __int64 a2)
{
  int v4; // eax
  int v5; // r8d
  int v6; // r9d
  int v7; // edi
  int v8; // ecx
  PVOID *i; // rbx
  int v10; // eax
  struct _UNICODE_STRING *v11; // rbx
  __int64 v12; // rax
  int v14; // [rsp+20h] [rbp-29h]
  int v15; // [rsp+30h] [rbp-19h] BYREF
  PVOID P[2]; // [rsp+38h] [rbp-11h] BYREF
  int v17; // [rsp+48h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+50h] [rbp+7h] BYREF
  int *v19; // [rsp+70h] [rbp+27h]
  __int64 v20; // [rsp+78h] [rbp+2Fh]

  v15 = 0;
  v17 = 0;
  P[1] = P;
  P[0] = P;
  v4 = BfsEnumeratePolicy(a2, (__int64)P, &v15, &v17);
  v7 = v4;
  if ( v4 >= 0 )
  {
    for ( i = (PVOID *)P[0]; i != P; i = (PVOID *)*i )
    {
      v10 = BfsRemovePolicyFromGlobalFileTable(a1, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32), (__int64)(i + 4));
      v7 = 0;
      if ( v10 != -1073741275 )
        v7 = v10;
      if ( v7 < 0 )
      {
        if ( (unsigned int)dword_140019000 <= 3 )
          break;
        v15 = v7;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v8 = dword_140019000;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v15 = v4;
LABEL_13:
      v20 = 4;
      v19 = &v15;
      tlgWriteTransfer_EtwWriteTransfer(v8, (int)&byte_140016D91, v5, v6, v14, &v18);
    }
  }
  while ( 1 )
  {
    v11 = (struct _UNICODE_STRING *)P[0];
    if ( P[0] == P )
      break;
    if ( *((PVOID **)P[0] + 1) != P || (v12 = *(_QWORD *)P[0], *(PVOID *)(*(_QWORD *)P[0] + 8LL) != P[0]) )
      __fastfail(3u);
    P[0] = *(PVOID *)P[0];
    *(_QWORD *)(v12 + 8) = P;
    RtlFreeUnicodeString(v11 + 2);
    ExFreePoolWithTag(v11, 0);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000d58c  mov     [rsp-8+arg_10], rbx
0x14000d591  mov     [rsp-8+arg_18], rsi
0x14000d596  push    rbp
0x14000d597  push    rdi
0x14000d598  push    r14
0x14000d59a  lea     rbp, [rsp-47h]
0x14000d59f  sub     rsp, 90h
0x14000d5a6  mov     rax, cs:__security_cookie
0x14000d5ad  xor     rax, rsp
0x14000d5b0  mov     [rbp+57h+var_20], rax
0x14000d5b4  mov     rsi, rdx
0x14000d5b7  mov     [rbp+57h+var_70], 0
0x14000d5be  lea     rax, [rbp+57h+P]
0x14000d5c2  mov     [rbp+57h+var_58], 0
0x14000d5c9  mov     [rbp+57h+var_60], rax
0x14000d5cd  lea     r9, [rbp+57h+var_58]
0x14000d5d1  lea     rax, [rbp+57h+P]
0x14000d5d5  mov     r14, rcx
0x14000d5d8  lea     r8, [rbp+57h+var_70]
0x14000d5dc  mov     [rbp+57h+P], rax
0x14000d5e0  lea     rdx, [rbp+57h+P]
0x14000d5e4  mov     rcx, rsi
0x14000d5e7  call    BfsEnumeratePolicy
0x14000d5ec  mov     edi, eax
0x14000d5ee  test    eax, eax
0x14000d5f0  jns     short loc_14000D602
0x14000d5f2  mov     ecx, cs:dword_140019000
0x14000d5f8  cmp     ecx, 3
0x14000d5fb  jbe     short loc_14000D66B
0x14000d5fd  mov     [rbp+57h+var_70], eax
0x14000d600  jmp     short loc_14000D646
0x14000d602  mov     rbx, [rbp+57h+P]
0x14000d606  jmp     short loc_14000D62D
0x14000d608  mov     r8, [rsi+20h]
0x14000d60c  lea     r9, [rbx+20h]
0x14000d610  mov     rdx, [rsi+18h]
0x14000d614  mov     rcx, r14
0x14000d617  call    BfsRemovePolicyFromGlobalFileTable
0x14000d61c  xor     edi, edi
0x14000d61e  cmp     eax, 0C0000225h
0x14000d623  cmovnz  edi, eax
0x14000d626  test    edi, edi
0x14000d628  js      short loc_14000D638
0x14000d62a  mov     rbx, [rbx]
0x14000d62d  lea     rax, [rbp+57h+P]
0x14000d631  cmp     rbx, rax
0x14000d634  jnz     short loc_14000D608
0x14000d636  jmp     short loc_14000D66B
0x14000d638  mov     eax, cs:dword_140019000
0x14000d63e  cmp     eax, 3
0x14000d641  jbe     short loc_14000D66B
0x14000d643  mov     [rbp+57h+var_70], edi
0x14000d646  lea     rax, [rbp+57h+var_70]
0x14000d64a  mov     [rbp+57h+var_28], 4
0x14000d652  mov     [rbp+57h+var_30], rax
0x14000d656  lea     rdx, byte_140016D91; int
0x14000d65d  lea     rax, [rbp+57h+var_50]
0x14000d661  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x14000d666  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000d66b  mov     rbx, [rbp+57h+P]
0x14000d66f  lea     rax, [rbp+57h+P]
0x14000d673  cmp     rbx, rax
0x14000d676  jz      short loc_14000D6C1
0x14000d678  lea     rax, [rbp+57h+P]
0x14000d67c  cmp     [rbx+8], rax
0x14000d680  jnz     short loc_14000D6BA
0x14000d682  mov     rax, [rbx]
0x14000d685  cmp     [rax+8], rbx
0x14000d689  jnz     short loc_14000D6BA
0x14000d68b  lea     rcx, [rbp+57h+P]
0x14000d68f  mov     [rbp+57h+P], rax
0x14000d693  mov     [rax+8], rcx
0x14000d697  lea     rcx, [rbx+20h]; UnicodeString
0x14000d69b  call    cs:__imp_RtlFreeUnicodeString
0x14000d6a2  nop     dword ptr [rax+rax+00h]
0x14000d6a7  xor     edx, edx; Tag
0x14000d6a9  mov     rcx, rbx; P
0x14000d6ac  call    cs:__imp_ExFreePoolWithTag
0x14000d6b3  nop     dword ptr [rax+rax+00h]
0x14000d6b8  jmp     short loc_14000D66B
0x14000d6ba  mov     ecx, 3
0x14000d6bf  int     29h; Win8: RtlFailFast(ecx)
0x14000d6c1  mov     eax, edi
0x14000d6c3  mov     rcx, [rbp+57h+var_20]
0x14000d6c7  xor     rcx, rsp; StackCookie
0x14000d6ca  call    __security_check_cookie
0x14000d6cf  lea     r11, [rsp+0A0h+var_10]
0x14000d6d7  mov     rbx, [r11+30h]
0x14000d6db  mov     rsi, [r11+38h]
0x14000d6df  mov     rsp, r11
0x14000d6e2  pop     r14
0x14000d6e4  pop     rdi
0x14000d6e5  pop     rbp
0x14000d6e6  retn
```
