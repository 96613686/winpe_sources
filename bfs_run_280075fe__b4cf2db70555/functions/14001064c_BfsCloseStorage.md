# BfsCloseStorage

- ea: `0x14001064c`
- end: `0x14001075a`
- name: `BfsCloseStorage`
- size: `270`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140006040`
- `0x14000cd20`

## callees

- `0x14001064c`
- `0x14001126c`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400106f1`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400106f1`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14001071d`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14001071d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001067a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400106ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400106bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400106d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010742`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001067a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400106ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400106bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400106d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010742`
- `FLTMGR!FltClose` at `0x140010663`
- `FLTMGR!FltClose` at `0x140010663`

## pseudocode

```c
void __fastcall BfsCloseStorage(_QWORD *P)
{
  void *v2; // rcx
  void *v3; // rcx
  void **v4; // rbx
  void *v5; // rdi
  void **v6; // rax
  struct _RTL_AVL_TABLE *v7; // rbx
  char *p_DeleteCount; // rdi

  v2 = (void *)P[1];
  if ( v2 )
    FltClose(v2);
  v3 = (void *)P[2];
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  v4 = (void **)P[8];
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == v4 )
      break;
    if ( *((void ***)v5 + 1) != v4 || (v6 = *(void ***)v5, *(void **)(*(_QWORD *)v5 + 8LL) != v5) )
      __fastfail(3u);
    *v4 = v6;
    v6[1] = v4;
    ExFreePoolWithTag(*((PVOID *)v5 + 2), 0);
    ExFreePoolWithTag(v5, 0);
  }
  ExFreePoolWithTag(v4, 0);
  v7 = (struct _RTL_AVL_TABLE *)(P + 10);
  while ( 1 )
  {
    p_DeleteCount = (char *)RtlEnumerateGenericTableAvl(v7, 1u);
    if ( !p_DeleteCount )
      break;
LABEL_15:
    if ( RtlIsGenericTableEmptyAvl((PRTL_AVL_TABLE)(p_DeleteCount + 40)) )
      BfsDereferenceTableEntry((volatile signed __int32 *)p_DeleteCount);
    else
      v7 = (struct _RTL_AVL_TABLE *)(p_DeleteCount + 40);
  }
  if ( v7 != (struct _RTL_AVL_TABLE *)(P + 10) )
  {
    p_DeleteCount = (char *)&v7[-1].DeleteCount;
    v7 = (struct _RTL_AVL_TABLE *)&v7[1].BalancedRoot.Parent[1];
    goto LABEL_15;
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14001064c  push    rbx
0x14001064e  push    rbp
0x14001064f  push    rsi
0x140010650  push    rdi
0x140010651  push    r14
0x140010653  sub     rsp, 20h
0x140010657  mov     rsi, rcx
0x14001065a  mov     rcx, [rcx+8]; FileHandle
0x14001065e  test    rcx, rcx
0x140010661  jz      short loc_14001066F
0x140010663  call    cs:__imp_FltClose
0x14001066a  nop     dword ptr [rax+rax+00h]
0x14001066f  mov     rcx, [rsi+10h]; P
0x140010673  test    rcx, rcx
0x140010676  jz      short loc_140010686
0x140010678  xor     edx, edx; Tag
0x14001067a  call    cs:__imp_ExFreePoolWithTag
0x140010681  nop     dword ptr [rax+rax+00h]
0x140010686  mov     rbx, [rsi+40h]
0x14001068a  mov     rdi, [rbx]
0x14001068d  cmp     rdi, rbx
0x140010690  jz      short loc_1400106D4
0x140010692  cmp     [rdi+8], rbx
0x140010696  jnz     short loc_1400106CD
0x140010698  mov     rax, [rdi]
0x14001069b  cmp     [rax+8], rdi
0x14001069f  jnz     short loc_1400106CD
0x1400106a1  mov     [rbx], rax
0x1400106a4  xor     edx, edx; Tag
0x1400106a6  mov     [rax+8], rbx
0x1400106aa  mov     rcx, [rdi+10h]; P
0x1400106ae  call    cs:__imp_ExFreePoolWithTag
0x1400106b5  nop     dword ptr [rax+rax+00h]
0x1400106ba  xor     edx, edx; Tag
0x1400106bc  mov     rcx, rdi; P
0x1400106bf  call    cs:__imp_ExFreePoolWithTag
0x1400106c6  nop     dword ptr [rax+rax+00h]
0x1400106cb  jmp     short loc_14001068A
0x1400106cd  mov     ecx, 3
0x1400106d2  int     29h; Win8: RtlFailFast(ecx)
0x1400106d4  xor     edx, edx; Tag
0x1400106d6  mov     rcx, rbx; P
0x1400106d9  call    cs:__imp_ExFreePoolWithTag
0x1400106e0  nop     dword ptr [rax+rax+00h]
0x1400106e5  lea     rbp, [rsi+50h]
0x1400106e9  mov     rbx, rbp
0x1400106ec  mov     dl, 1; Restart
0x1400106ee  mov     rcx, rbx; Table
0x1400106f1  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400106f8  nop     dword ptr [rax+rax+00h]
0x1400106fd  mov     rdi, rax
0x140010700  test    rax, rax
0x140010703  jnz     short loc_140010719
0x140010705  cmp     rbx, rbp
0x140010708  jz      short loc_14001073D
0x14001070a  lea     rdi, [rbx-28h]
0x14001070e  mov     rbx, [rdi+90h]
0x140010715  add     rbx, 20h ; ' '
0x140010719  lea     rcx, [rdi+28h]; Table
0x14001071d  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x140010724  nop     dword ptr [rax+rax+00h]
0x140010729  test    al, al
0x14001072b  jz      short loc_140010737
0x14001072d  mov     rcx, rdi; Buffer
0x140010730  call    BfsDereferenceTableEntry
0x140010735  jmp     short loc_1400106EC
0x140010737  lea     rbx, [rdi+28h]
0x14001073b  jmp     short loc_1400106EC
0x14001073d  xor     edx, edx; Tag
0x14001073f  mov     rcx, rsi; P
0x140010742  call    cs:__imp_ExFreePoolWithTag
0x140010749  nop     dword ptr [rax+rax+00h]
0x14001074e  add     rsp, 20h
0x140010752  pop     r14
0x140010754  pop     rdi
0x140010755  pop     rsi
0x140010756  pop     rbp
0x140010757  pop     rbx
0x140010758  retn
```
