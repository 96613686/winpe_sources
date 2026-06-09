# WimFSFAllocateReadCompletionContext

- ea: `0x14000c24c`
- end: `0x14000c382`
- name: `WimFSFAllocateReadCompletionContext`
- size: `310`
- prototype: `__int64 __fastcall(__int64, struct _NPAGED_LOOKASIDE_LIST *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000c20c`

## callees

- `0x14000c24c`
- `0x14000d3fc`
- `0x14000fb60`
- `0x1400119c0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14000c29c`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000c29c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000c2c4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000c2c4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000c368`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000c368`

## pseudocode

```c
__int64 __fastcall WimFSFAllocateReadCompletionContext(__int64 a1, struct _NPAGED_LOOKASIDE_LIST *a2, _QWORD *a3)
{
  char v3; // bp
  unsigned int v7; // ebx
  _DWORD *v8; // rax
  _DWORD *v9; // rbx

  v3 = 0;
  *a3 = 0;
  if ( a1 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_b091599abfd73b8a76031cd442416986_Traceguids);
    if ( !ExAcquireRundownProtection(*(PEX_RUNDOWN_REF *)(a1 + 96)) )
      return (unsigned int)-1073740690;
    a2 = *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 104);
    v3 = 1;
  }
  v8 = ExAllocateFromNPagedLookasideList(a2 + 6);
  v9 = v8;
  if ( v8 )
  {
    memset(v8, 0, 0x120u);
    v9[3] |= 1u;
    *((_QWORD *)v9 + 6) = a2;
    *((_QWORD *)v9 + 17) = a1;
    v9[4] = 1;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_b091599abfd73b8a76031cd442416986_Traceguids, v9);
    *a3 = v9;
    return 0;
  }
  else
  {
    v7 = -1073741670;
    if ( v3 )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_b091599abfd73b8a76031cd442416986_Traceguids);
      ExReleaseRundownProtection(*(PEX_RUNDOWN_REF *)(a1 + 96));
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14000c24c  push    rbx
0x14000c24e  push    rbp
0x14000c24f  push    rsi
0x14000c250  push    rdi
0x14000c251  push    r14
0x14000c253  sub     rsp, 20h
0x14000c257  xor     bpl, bpl
0x14000c25a  mov     qword ptr [r8], 0
0x14000c261  mov     r14, r8
0x14000c264  mov     rsi, rdx
0x14000c267  mov     rdi, rcx
0x14000c26a  test    rcx, rcx
0x14000c26d  jz      short loc_14000C2BD
0x14000c26f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c276  mov     eax, [rcx+2Ch]
0x14000c279  test    al, 20h
0x14000c27b  jz      short loc_14000C298
0x14000c27d  cmp     byte ptr [rcx+29h], 5
0x14000c281  jb      short loc_14000C298
0x14000c283  mov     rcx, [rcx+18h]
0x14000c287  lea     r8, WPP_b091599abfd73b8a76031cd442416986_Traceguids
0x14000c28e  mov     edx, 0Bh
0x14000c293  call    WPP_SF_
0x14000c298  mov     rcx, [rdi+60h]; RunRef
0x14000c29c  call    cs:__imp_ExAcquireRundownProtection
0x14000c2a3  nop     dword ptr [rax+rax+00h]
0x14000c2a8  test    al, al
0x14000c2aa  jnz     short loc_14000C2B6
0x14000c2ac  mov     ebx, 0C000046Eh
0x14000c2b1  jmp     loc_14000C374
0x14000c2b6  mov     rsi, [rdi+68h]
0x14000c2ba  mov     bpl, 1
0x14000c2bd  lea     rcx, [rsi+300h]; Lookaside
0x14000c2c4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000c2cb  nop     dword ptr [rax+rax+00h]
0x14000c2d0  mov     rbx, rax
0x14000c2d3  test    rax, rax
0x14000c2d6  jz      short loc_14000C331
0x14000c2d8  xor     edx, edx; Val
0x14000c2da  mov     r8d, 120h; Size
0x14000c2e0  mov     rcx, rax; void *
0x14000c2e3  call    memset
0x14000c2e8  or      dword ptr [rbx+0Ch], 1
0x14000c2ec  mov     [rbx+30h], rsi
0x14000c2f0  mov     [rbx+88h], rdi
0x14000c2f7  mov     dword ptr [rbx+10h], 1
0x14000c2fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c305  mov     eax, [rcx+2Ch]
0x14000c308  test    al, 20h
0x14000c30a  jz      short loc_14000C32A
0x14000c30c  cmp     byte ptr [rcx+29h], 5
0x14000c310  jb      short loc_14000C32A
0x14000c312  mov     rcx, [rcx+18h]
0x14000c316  lea     r8, WPP_b091599abfd73b8a76031cd442416986_Traceguids
0x14000c31d  mov     edx, 0Ch
0x14000c322  mov     r9, rbx
0x14000c325  call    WPP_SF_q
0x14000c32a  mov     [r14], rbx
0x14000c32d  xor     ebx, ebx
0x14000c32f  jmp     short loc_14000C374
0x14000c331  mov     ebx, 0C000009Ah
0x14000c336  test    bpl, bpl
0x14000c339  jz      short loc_14000C374
0x14000c33b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c342  mov     eax, [rcx+2Ch]
0x14000c345  test    al, 20h
0x14000c347  jz      short loc_14000C364
0x14000c349  cmp     byte ptr [rcx+29h], 5
0x14000c34d  jb      short loc_14000C364
0x14000c34f  mov     rcx, [rcx+18h]
0x14000c353  lea     r8, WPP_b091599abfd73b8a76031cd442416986_Traceguids
0x14000c35a  mov     edx, 0Dh
0x14000c35f  call    WPP_SF_
0x14000c364  mov     rcx, [rdi+60h]; RunRef
0x14000c368  call    cs:__imp_ExReleaseRundownProtection
0x14000c36f  nop     dword ptr [rax+rax+00h]
0x14000c374  mov     eax, ebx
0x14000c376  add     rsp, 20h
0x14000c37a  pop     r14
0x14000c37c  pop     rdi
0x14000c37d  pop     rsi
0x14000c37e  pop     rbp
0x14000c37f  pop     rbx
0x14000c380  retn
```
