# CreateAttributesFromIntentEnterpriseId

- ea: `0x1400046e8`
- end: `0x1400047e4`
- name: `CreateAttributesFromIntentEnterpriseId`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005994`

## callees

- `0x1400046e8`
- `0x1400048b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400047b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400047cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400047b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400047cb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004756`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004756`

## pseudocode

```c
__int64 __fastcall CreateAttributesFromIntentEnterpriseId(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  void *v5; // rdi
  unsigned int v6; // ebx
  struct _UNICODE_STRING *v7; // rax
  struct _UNICODE_STRING *v8; // rsi
  __int64 v9; // rax

  *a2 = 0;
  if ( a1 )
  {
    v4 = EnterpriseContextLibMemAlloc(16);
    v5 = (void *)v4;
    if ( !v4 )
      return (unsigned int)-1073741801;
    *(_WORD *)(v4 + 2) = *(_WORD *)(a1 + 2);
    *(_WORD *)v4 = *(_WORD *)a1;
    *(_QWORD *)(v4 + 8) = *(_QWORD *)(a1 + 8);
  }
  else
  {
    v5 = 0;
  }
  v7 = (struct _UNICODE_STRING *)EnterpriseContextLibMemAlloc(40);
  v8 = v7;
  if ( v7 )
  {
    RtlInitUnicodeString(v7, L"PEDP://IntentEnterpriseId");
    *(_DWORD *)&v8[1].Length = 3;
    *(_DWORD *)(&v8[1].MaximumLength + 1) = 66;
    *(_QWORD *)&v8[2].Length = v5;
    LODWORD(v8[1].Buffer) = v5 != 0;
    v9 = EnterpriseContextLibMemAlloc(16);
    if ( v9 )
    {
      v6 = 0;
      *(_QWORD *)(v9 + 8) = v8;
      *a2 = v9;
      *(_WORD *)v9 = 1;
      *(_WORD *)(v9 + 2) = 0;
      *(_DWORD *)(v9 + 4) = 1;
      return v6;
    }
    ExFreePoolWithTag(v8, 0);
  }
  v6 = -1073741801;
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  return v6;
}

```

## disassembly

```asm
0x1400046e8  push    rbx
0x1400046ea  push    rsi
0x1400046eb  push    rdi
0x1400046ec  push    r14
0x1400046ee  sub     rsp, 28h
0x1400046f2  mov     qword ptr [rdx], 0
0x1400046f9  mov     r14, rdx
0x1400046fc  mov     rbx, rcx
0x1400046ff  test    rcx, rcx
0x140004702  jz      short loc_140004738
0x140004704  mov     ecx, 10h
0x140004709  call    EnterpriseContextLibMemAlloc
0x14000470e  mov     rdi, rax
0x140004711  test    rax, rax
0x140004714  jnz     short loc_140004720
0x140004716  mov     ebx, 0C0000017h
0x14000471b  jmp     loc_1400047D7
0x140004720  movzx   eax, word ptr [rbx+2]
0x140004724  mov     [rdi+2], ax
0x140004728  movzx   eax, word ptr [rbx]
0x14000472b  mov     [rdi], ax
0x14000472e  mov     rax, [rbx+8]
0x140004732  mov     [rdi+8], rax
0x140004736  jmp     short loc_14000473A
0x140004738  xor     edi, edi
0x14000473a  mov     ecx, 28h ; '('
0x14000473f  call    EnterpriseContextLibMemAlloc
0x140004744  mov     rsi, rax
0x140004747  test    rax, rax
0x14000474a  jz      short loc_1400047BC
0x14000474c  lea     rdx, aPedpIntentente; "PEDP://IntentEnterpriseId"
0x140004753  mov     rcx, rax; DestinationString
0x140004756  call    cs:__imp_RtlInitUnicodeString
0x14000475d  nop     dword ptr [rax+rax+00h]
0x140004762  xor     eax, eax
0x140004764  mov     dword ptr [rsi+10h], 3
0x14000476b  test    rdi, rdi
0x14000476e  mov     dword ptr [rsi+14h], 42h ; 'B'
0x140004775  mov     ecx, 10h
0x14000477a  mov     [rsi+20h], rdi
0x14000477e  setnz   al
0x140004781  mov     [rsi+18h], eax
0x140004784  call    EnterpriseContextLibMemAlloc
0x140004789  mov     rcx, rax
0x14000478c  test    rax, rax
0x14000478f  jz      short loc_1400047AB
0x140004791  xor     ebx, ebx
0x140004793  mov     [rcx+8], rsi
0x140004797  mov     [r14], rcx
0x14000479a  lea     edx, [rbx+1]
0x14000479d  mov     [rax], dx
0x1400047a0  xor     eax, eax
0x1400047a2  mov     [rcx+2], ax
0x1400047a6  mov     [rcx+4], edx
0x1400047a9  jmp     short loc_1400047D7
0x1400047ab  xor     edx, edx; Tag
0x1400047ad  mov     rcx, rsi; P
0x1400047b0  call    cs:__imp_ExFreePoolWithTag
0x1400047b7  nop     dword ptr [rax+rax+00h]
0x1400047bc  mov     ebx, 0C0000017h
0x1400047c1  test    rdi, rdi
0x1400047c4  jz      short loc_1400047D7
0x1400047c6  xor     edx, edx; Tag
0x1400047c8  mov     rcx, rdi; P
0x1400047cb  call    cs:__imp_ExFreePoolWithTag
0x1400047d2  nop     dword ptr [rax+rax+00h]
0x1400047d7  mov     eax, ebx
0x1400047d9  add     rsp, 28h
0x1400047dd  pop     r14
0x1400047df  pop     rdi
0x1400047e0  pop     rsi
0x1400047e1  pop     rbx
0x1400047e2  retn
```
