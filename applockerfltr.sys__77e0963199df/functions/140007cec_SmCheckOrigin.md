# SmCheckOrigin

- ea: `0x140007cec`
- end: `0x140007dfa`
- name: `SmCheckOrigin`
- size: `270`
- prototype: `__int64 __fastcall(struct _KPROCESS *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007030`
- `0x140007410`

## callees

- `0x140007cec`

## import_xrefs

- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x140007d6b`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x140007d6b`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140007dde`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140007dde`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007d92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007dc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007d92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007dc8`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140007d09`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140007d09`
- `ntoskrnl!ExAllocatePool2` at `0x140007d32`
- `ntoskrnl!ExAllocatePool2` at `0x140007d32`

## pseudocode

```c
__int64 __fastcall SmCheckOrigin(struct _KPROCESS *a1, _BYTE *a2, _QWORD *a3)
{
  PACCESS_TOKEN v5; // rax
  unsigned int v6; // esi
  void *v7; // rbp
  _DWORD *Pool2; // rdi
  int v9; // ebx
  int v10; // eax
  unsigned int v12; // [rsp+78h] [rbp+10h] BYREF

  *a2 = 0;
  *a3 = 0;
  v5 = PsReferencePrimaryToken(a1);
  v6 = 589;
  v12 = 0;
  v7 = v5;
  while ( 1 )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(258, v6, 1098149235);
    if ( !Pool2 )
      break;
    v9 = SeQuerySecurityAttributesToken(v7, L"24", 1, Pool2, v6, &v12);
    if ( v9 != -1073741789 )
    {
      if ( v9 < 0 )
      {
LABEL_9:
        v10 = 0;
        if ( v9 != -1073741275 )
          v10 = v9;
        v9 = v10;
      }
      else if ( Pool2[1] )
      {
        *a2 = 1;
        *a3 = Pool2;
        goto LABEL_14;
      }
      ExFreePoolWithTag(Pool2, 0x41746D73u);
      goto LABEL_14;
    }
    if ( v6 >= v12 )
      goto LABEL_9;
    v6 = v12;
    ExFreePoolWithTag(Pool2, 0x41746D73u);
  }
  v9 = -1073741801;
LABEL_14:
  PsDereferencePrimaryToken(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140007cec  push    rbx
0x140007cee  push    rbp
0x140007cef  push    rsi
0x140007cf0  push    rdi
0x140007cf1  push    r14
0x140007cf3  push    r15
0x140007cf5  sub     rsp, 38h
0x140007cf9  mov     r14, r8
0x140007cfc  mov     byte ptr [rdx], 0
0x140007cff  mov     r15, rdx
0x140007d02  mov     qword ptr [r8], 0
0x140007d09  call    cs:__imp_PsReferencePrimaryToken
0x140007d10  nop     dword ptr [rax+rax+00h]
0x140007d15  mov     esi, 24Dh
0x140007d1a  mov     [rsp+68h+arg_8], 0
0x140007d22  mov     rbp, rax
0x140007d25  mov     edx, esi
0x140007d27  mov     ecx, 102h
0x140007d2c  mov     r8d, 41746D73h
0x140007d32  call    cs:__imp_ExAllocatePool2
0x140007d39  nop     dword ptr [rax+rax+00h]
0x140007d3e  mov     rdi, rax
0x140007d41  test    rax, rax
0x140007d44  jz      loc_140007DD6
0x140007d4a  lea     rax, [rsp+68h+arg_8]
0x140007d4f  mov     r9, rdi
0x140007d52  mov     [rsp+68h+var_40], rax
0x140007d57  lea     rdx, a24; "24"
0x140007d5e  mov     r8d, 1
0x140007d64  mov     [rsp+68h+var_48], esi
0x140007d68  mov     rcx, rbp
0x140007d6b  call    cs:__imp_SeQuerySecurityAttributesToken
0x140007d72  nop     dword ptr [rax+rax+00h]
0x140007d77  mov     ebx, eax
0x140007d79  cmp     eax, 0C0000023h
0x140007d7e  jnz     short loc_140007DA0
0x140007d80  cmp     esi, [rsp+68h+arg_8]
0x140007d84  jnb     short loc_140007DB3
0x140007d86  mov     esi, [rsp+68h+arg_8]
0x140007d8a  mov     edx, 41746D73h; Tag
0x140007d8f  mov     rcx, rdi; P
0x140007d92  call    cs:__imp_ExFreePoolWithTag
0x140007d99  nop     dword ptr [rax+rax+00h]
0x140007d9e  jmp     short loc_140007D25
0x140007da0  test    ebx, ebx
0x140007da2  js      short loc_140007DB3
0x140007da4  cmp     dword ptr [rdi+4], 0
0x140007da8  jbe     short loc_140007DC0
0x140007daa  mov     byte ptr [r15], 1
0x140007dae  mov     [r14], rdi
0x140007db1  jmp     short loc_140007DDB
0x140007db3  xor     eax, eax
0x140007db5  cmp     ebx, 0C0000225h
0x140007dbb  cmovnz  eax, ebx
0x140007dbe  mov     ebx, eax
0x140007dc0  mov     edx, 41746D73h; Tag
0x140007dc5  mov     rcx, rdi; P
0x140007dc8  call    cs:__imp_ExFreePoolWithTag
0x140007dcf  nop     dword ptr [rax+rax+00h]
0x140007dd4  jmp     short loc_140007DDB
0x140007dd6  mov     ebx, 0C0000017h
0x140007ddb  mov     rcx, rbp; PrimaryToken
0x140007dde  call    cs:__imp_PsDereferencePrimaryToken
0x140007de5  nop     dword ptr [rax+rax+00h]
0x140007dea  mov     eax, ebx
0x140007dec  add     rsp, 38h
0x140007df0  pop     r15
0x140007df2  pop     r14
0x140007df4  pop     rdi
0x140007df5  pop     rsi
0x140007df6  pop     rbp
0x140007df7  pop     rbx
0x140007df8  retn
```
