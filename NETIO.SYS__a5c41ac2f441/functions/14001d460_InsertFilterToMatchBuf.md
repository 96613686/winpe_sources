# InsertFilterToMatchBuf

- ea: `0x14001d460`
- end: `0x14001d5d4`
- name: `InsertFilterToMatchBuf`
- size: `372`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14001d2c8`
- `0x14001d6b0`
- `0x14001d86c`
- `0x14001e040`
- `0x14004ccb0`
- `0x14004cee0`

## callees

- `0x140009520`
- `0x140009e00`
- `0x14001d460`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001d583`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001d583`

## string_xrefs

- `0x14001d5a6`: `ExAllocateFromNPagedLookasideList`
- `0x14001d5c0`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
__int64 __fastcall InsertFilterToMatchBuf(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  __int64 v7; // rax
  __int64 v9; // rdx
  __int64 v10; // rbp
  _DWORD *v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rax

  if ( a1 && *(_WORD *)(a1 + 24) < 7u )
  {
    _InterlockedIncrement64((volatile signed __int64 *)(a2 + 16));
    v7 = *(unsigned __int16 *)(a1 + 24);
    *a3 = a1;
    *(_QWORD *)(a1 + 8 * v7 + 32) = a2;
    ++*(_WORD *)(a1 + 24);
    return 0;
  }
  if ( a4 )
  {
    v9 = *(unsigned __int16 *)(a4 + 16);
    if ( (unsigned int)v9 < 3 )
    {
      v10 = 0;
      v11 = (_DWORD *)(a4 + 96 * v9 + 24);
      *(_WORD *)(a4 + 16) = v9 + 1;
      v11[7] = 1;
      goto LABEL_7;
    }
  }
  v10 = 0;
  v11 = ExAllocateFromNPagedLookasideList(gWfpGlobal);
  if ( v11
    || (v13 = WfpReportSysErrorAsNtStatus(v12, "ExAllocateFromNPagedLookasideList", 3221225495LL, 1), (v10 = v13) == 0) )
  {
    v11[7] = 0;
LABEL_7:
    *((_QWORD *)v11 + 1) = v11;
    *(_QWORD *)v11 = v11;
    *((_QWORD *)v11 + 2) = 0;
    v11[6] = -65536;
    *((_QWORD *)v11 + 11) = 0;
    _InterlockedIncrement64((volatile signed __int64 *)(a2 + 16));
    ++*((_WORD *)v11 + 12);
    *((_QWORD *)v11 + 4) = a2;
    if ( a1 )
      *(_QWORD *)(a1 + 16) = v11;
    *a3 = v11;
    if ( !v10 )
      return v10;
    goto LABEL_10;
  }
  WfpReportError(v13, "WfpAllocFromNPagedLookasideList");
LABEL_10:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"InsertFilterToMatchBuf",
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x14001d460  push    rbx
0x14001d462  push    rsi
0x14001d463  push    r14
0x14001d465  sub     rsp, 30h
0x14001d469  mov     r14, r8
0x14001d46c  mov     rsi, rdx
0x14001d46f  mov     rbx, rcx
0x14001d472  test    rcx, rcx
0x14001d475  jz      short loc_14001D49F
0x14001d477  cmp     word ptr [rcx+18h], 7
0x14001d47c  jnb     short loc_14001D49F
0x14001d47e  lock inc qword ptr [rdx+10h]
0x14001d483  movzx   eax, word ptr [rcx+18h]
0x14001d487  mov     [r8], rcx
0x14001d48a  mov     [rcx+rax*8+20h], rdx
0x14001d48f  inc     word ptr [rcx+18h]
0x14001d493  xor     eax, eax
0x14001d495  add     rsp, 30h
0x14001d499  pop     r14
0x14001d49b  pop     rsi
0x14001d49c  pop     rbx
0x14001d49d  retn
0x14001d49f  mov     [rsp+48h+arg_0], rbp
0x14001d4a4  mov     [rsp+48h+arg_8], rdi
0x14001d4a9  mov     [rsp+48h+arg_10], r15
0x14001d4ae  test    r9, r9
0x14001d4b1  jz      loc_14001D576
0x14001d4b7  movzx   edx, word ptr [r9+10h]
0x14001d4bc  cmp     edx, 3
0x14001d4bf  jnb     loc_14001D576
0x14001d4c5  lea     rdi, [rdx+rdx*2]
0x14001d4c9  xor     r15d, r15d
0x14001d4cc  shl     rdi, 5
0x14001d4d0  mov     ebp, r15d
0x14001d4d3  add     rdi, 18h
0x14001d4d7  add     rdi, r9
0x14001d4da  inc     dx
0x14001d4dd  mov     [r9+10h], dx
0x14001d4e2  mov     dword ptr [rdi+1Ch], 1
0x14001d4e9  mov     [rdi+8], rdi
0x14001d4ed  mov     [rdi], rdi
0x14001d4f0  mov     [rdi+10h], r15
0x14001d4f4  mov     dword ptr [rdi+18h], 0FFFF0000h
0x14001d4fb  mov     [rdi+58h], r15
0x14001d4ff  lock inc qword ptr [rsi+10h]
0x14001d504  inc     word ptr [rdi+18h]
0x14001d508  mov     [rdi+20h], rsi
0x14001d50c  test    rbx, rbx
0x14001d50f  jz      short loc_14001D515
0x14001d511  mov     [rbx+10h], rdi
0x14001d515  mov     [r14], rdi
0x14001d518  test    rbp, rbp
0x14001d51b  jz      short loc_14001D55F
0x14001d51d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d524  lea     rax, WPP_GLOBAL_Control
0x14001d52b  cmp     rcx, rax
0x14001d52e  jz      short loc_14001D55F
0x14001d530  cmp     byte ptr [rcx+29h], 2
0x14001d534  jb      short loc_14001D55F
0x14001d536  test    dword ptr [rcx+2Ch], 1000h
0x14001d53d  jz      short loc_14001D55F
0x14001d53f  mov     rcx, [rcx+18h]
0x14001d543  lea     r9, aInsertfilterto; "InsertFilterToMatchBuf"
0x14001d54a  mov     edx, 0Fh
0x14001d54f  mov     [rsp+48h+var_28], ebp
0x14001d553  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14001d55a  call    WPP_SF_sd
0x14001d55f  mov     r15, [rsp+48h+arg_10]
0x14001d564  mov     rax, rbp
0x14001d567  mov     rbp, [rsp+48h+arg_0]
0x14001d56c  mov     rdi, [rsp+48h+arg_8]
0x14001d571  jmp     loc_14001D495
0x14001d576  mov     rcx, cs:gWfpGlobal; Lookaside
0x14001d57d  xor     r15d, r15d
0x14001d580  mov     ebp, r15d
0x14001d583  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001d58a  nop     dword ptr [rax+rax+00h]
0x14001d58f  mov     rdi, rax
0x14001d592  test    rax, rax
0x14001d595  jz      short loc_14001D5A0
0x14001d597  mov     [rdi+1Ch], r15d
0x14001d59b  jmp     loc_14001D4E9
0x14001d5a0  mov     r9d, 1
0x14001d5a6  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x14001d5ad  mov     r8d, 0C0000017h
0x14001d5b3  call    WfpReportSysErrorAsNtStatus
0x14001d5b8  mov     rbp, rax
0x14001d5bb  test    rax, rax
0x14001d5be  jz      short loc_14001D597
0x14001d5c0  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x14001d5c7  mov     rcx, rax
0x14001d5ca  call    WfpReportError
0x14001d5cf  jmp     loc_14001D51D
```
