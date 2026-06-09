# BfsRemoveAllPoliciesFromGlobalFileTable

- ea: `0x14000d3f8`
- end: `0x14000d554`
- name: `BfsRemoveAllPoliciesFromGlobalFileTable`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000a4bc`

## callees

- `0x140001008`
- `0x1400061a0`
- `0x14000d3f8`
- `0x14000d5a0`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d507`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d507`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d518`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d518`

## pseudocode

```c
__int64 __fastcall BfsRemoveAllPoliciesFromGlobalFileTable(__int64 a1, __int64 a2)
{
  int v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // edi
  __int64 v8; // rcx
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
  v4 = BfsEnumeratePolicy(a2, P, &v15, &v17);
  v7 = v4;
  if ( v4 >= 0 )
  {
    for ( i = (PVOID *)P[0]; i != P; i = (PVOID *)*i )
    {
      v10 = BfsRemovePolicyFromGlobalFileTable(
              a1,
              *(unsigned __int8 **)(a2 + 24),
              *(unsigned __int8 **)(a2 + 32),
              (__int64)(i + 4));
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
    v8 = (unsigned int)dword_140019000;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v15 = v4;
LABEL_13:
      v20 = 4;
      v19 = &v15;
      tlgWriteTransfer_EtwWriteTransfer(v8, (unsigned __int8 *)&byte_140016D91, v5, v6, v14, &v18);
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
0x14000d3f8  mov     [rsp-8+arg_10], rbx
0x14000d3fd  mov     [rsp-8+arg_18], rsi
0x14000d402  push    rbp
0x14000d403  push    rdi
0x14000d404  push    r14
0x14000d406  lea     rbp, [rsp-47h]
0x14000d40b  sub     rsp, 90h
0x14000d412  mov     rax, cs:__security_cookie
0x14000d419  xor     rax, rsp
0x14000d41c  mov     [rbp+57h+var_20], rax
0x14000d420  mov     rsi, rdx
0x14000d423  mov     [rbp+57h+var_70], 0
0x14000d42a  lea     rax, [rbp+57h+P]
0x14000d42e  mov     [rbp+57h+var_58], 0
0x14000d435  mov     [rbp+57h+var_60], rax
0x14000d439  lea     r9, [rbp+57h+var_58]
0x14000d43d  lea     rax, [rbp+57h+P]
0x14000d441  mov     r14, rcx
0x14000d444  lea     r8, [rbp+57h+var_70]
0x14000d448  mov     [rbp+57h+P], rax
0x14000d44c  lea     rdx, [rbp+57h+P]
0x14000d450  mov     rcx, rsi
0x14000d453  call    BfsEnumeratePolicy
0x14000d458  mov     edi, eax
0x14000d45a  test    eax, eax
0x14000d45c  jns     short loc_14000D46E
0x14000d45e  mov     ecx, cs:dword_140019000
0x14000d464  cmp     ecx, 3
0x14000d467  jbe     short loc_14000D4D7
0x14000d469  mov     [rbp+57h+var_70], eax
0x14000d46c  jmp     short loc_14000D4B2
0x14000d46e  mov     rbx, [rbp+57h+P]
0x14000d472  jmp     short loc_14000D499
0x14000d474  mov     r8, [rsi+20h]
0x14000d478  lea     r9, [rbx+20h]
0x14000d47c  mov     rdx, [rsi+18h]
0x14000d480  mov     rcx, r14
0x14000d483  call    BfsRemovePolicyFromGlobalFileTable
0x14000d488  xor     edi, edi
0x14000d48a  cmp     eax, 0C0000225h
0x14000d48f  cmovnz  edi, eax
0x14000d492  test    edi, edi
0x14000d494  js      short loc_14000D4A4
0x14000d496  mov     rbx, [rbx]
0x14000d499  lea     rax, [rbp+57h+P]
0x14000d49d  cmp     rbx, rax
0x14000d4a0  jnz     short loc_14000D474
0x14000d4a2  jmp     short loc_14000D4D7
0x14000d4a4  mov     eax, cs:dword_140019000
0x14000d4aa  cmp     eax, 3
0x14000d4ad  jbe     short loc_14000D4D7
0x14000d4af  mov     [rbp+57h+var_70], edi
0x14000d4b2  lea     rax, [rbp+57h+var_70]
0x14000d4b6  mov     [rbp+57h+var_28], 4
0x14000d4be  mov     [rbp+57h+var_30], rax
0x14000d4c2  lea     rdx, byte_140016D91; int
0x14000d4c9  lea     rax, [rbp+57h+var_50]
0x14000d4cd  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x14000d4d2  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000d4d7  mov     rbx, [rbp+57h+P]
0x14000d4db  lea     rax, [rbp+57h+P]
0x14000d4df  cmp     rbx, rax
0x14000d4e2  jz      short loc_14000D52D
0x14000d4e4  lea     rax, [rbp+57h+P]
0x14000d4e8  cmp     [rbx+8], rax
0x14000d4ec  jnz     short loc_14000D526
0x14000d4ee  mov     rax, [rbx]
0x14000d4f1  cmp     [rax+8], rbx
0x14000d4f5  jnz     short loc_14000D526
0x14000d4f7  lea     rcx, [rbp+57h+P]
0x14000d4fb  mov     [rbp+57h+P], rax
0x14000d4ff  mov     [rax+8], rcx
0x14000d503  lea     rcx, [rbx+20h]; UnicodeString
0x14000d507  call    cs:__imp_RtlFreeUnicodeString
0x14000d50e  nop     dword ptr [rax+rax+00h]
0x14000d513  xor     edx, edx; Tag
0x14000d515  mov     rcx, rbx; P
0x14000d518  call    cs:__imp_ExFreePoolWithTag
0x14000d51f  nop     dword ptr [rax+rax+00h]
0x14000d524  jmp     short loc_14000D4D7
0x14000d526  mov     ecx, 3
0x14000d52b  int     29h; Win8: RtlFailFast(ecx)
0x14000d52d  mov     eax, edi
0x14000d52f  mov     rcx, [rbp+57h+var_20]
0x14000d533  xor     rcx, rsp; StackCookie
0x14000d536  call    __security_check_cookie
0x14000d53b  lea     r11, [rsp+0A0h+var_10]
0x14000d543  mov     rbx, [r11+30h]
0x14000d547  mov     rsi, [r11+38h]
0x14000d54b  mov     rsp, r11
0x14000d54e  pop     r14
0x14000d550  pop     rdi
0x14000d551  pop     rbp
0x14000d552  retn
```
