# CreateCache

- ea: `0x140068a14`
- end: `0x140068b2b`
- name: `CreateCache`
- size: `279`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14004f054`
- `0x140050834`
- `0x1400677c0`

## callees

- `0x140006c40`
- `0x140009520`
- `0x14000afa0`
- `0x14004fd90`
- `0x140068a14`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140068a67`
- `ntoskrnl!KeInitializeSpinLock` at `0x140068a67`

## string_xrefs

- `0x140068b05`: `CreateCache`

## pseudocode

```c
__int64 __fastcall CreateCache(__int64 a1, int a2, __int64 a3)
{
  __int64 v6; // rax
  _DWORD *v7; // rdi
  __int64 CombinedHashTable; // rbx
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 result; // rax
  _QWORD v12[5]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+68h] [rbp+20h] BYREF

  v12[0] = 0;
  v13 = 0;
  v6 = WfpPoolAllocNonPaged(176, 1215325783, &v13);
  v7 = (_DWORD *)v13;
  CombinedHashTable = v6;
  if ( v6 )
    goto LABEL_12;
  KeInitializeSpinLock((PKSPIN_LOCK)(v13 + 8));
  v9 = 0;
  do
  {
    ++v9;
    v10 = &v7[4 * v9];
    v10[1] = v10;
    *v10 = v10;
  }
  while ( v9 != 10 );
  *v7 = 0;
  CombinedHashTable = CreateCombinedHashTable((__int64)&gWfpGlobal[8].L.ListEntry.Blink, v12);
  if ( CombinedHashTable )
  {
LABEL_12:
    if ( !v7 || (WfpPoolFree(&v13), CombinedHashTable) )
      WfpReportError(CombinedHashTable, "CreateCache");
    return CombinedHashTable;
  }
  else
  {
    *(_QWORD *)(a3 + 8) = v12[0];
    *(_QWORD *)(a3 + 16) = a1;
    *(_QWORD *)(a3 + 24) = v7;
    *(_DWORD *)a3 = 1;
    *(_DWORD *)(a3 + 32) = a2;
    ++LODWORD(gWfpGlobal[13].L.ListEntry.Blink);
    result = 0;
    *(_DWORD *)(a3 + 36) = gWfpGlobal[13].L.ListEntry.Blink;
  }
  return result;
}

```

## disassembly

```asm
0x140068a14  mov     rax, rsp
0x140068a17  mov     [rax+8], rbx
0x140068a1b  mov     [rax+10h], rbp
0x140068a1f  push    rsi
0x140068a20  push    rdi
0x140068a21  push    r14
0x140068a23  sub     rsp, 30h
0x140068a27  mov     rsi, r8
0x140068a2a  mov     qword ptr [rax-28h], 0
0x140068a32  mov     ebp, edx
0x140068a34  mov     qword ptr [rax+20h], 0
0x140068a3c  mov     r14, rcx
0x140068a3f  lea     r8, [rax+20h]
0x140068a43  mov     edx, 48706657h
0x140068a48  mov     ecx, 0B0h
0x140068a4d  call    WfpPoolAllocNonPaged
0x140068a52  mov     rdi, [rsp+48h+arg_18]
0x140068a57  mov     rbx, rax
0x140068a5a  test    rax, rax
0x140068a5d  jnz     loc_140068AF1
0x140068a63  lea     rcx, [rdi+8]; SpinLock
0x140068a67  call    cs:__imp_KeInitializeSpinLock
0x140068a6e  nop     dword ptr [rax+rax+00h]
0x140068a73  xor     edx, edx
0x140068a75  lea     rcx, [rdx+1]
0x140068a79  inc     rdx
0x140068a7c  shl     rcx, 4
0x140068a80  add     rcx, rdi
0x140068a83  mov     [rcx+8], rcx
0x140068a87  mov     [rcx], rcx
0x140068a8a  cmp     rdx, 0Ah
0x140068a8e  jnz     short loc_140068A75
0x140068a90  mov     dword ptr [rdi], 0
0x140068a96  lea     rdx, [rsp+48h+var_28]
0x140068a9b  mov     rcx, cs:gWfpGlobal
0x140068aa2  add     rcx, 448h
0x140068aa9  call    CreateCombinedHashTable
0x140068aae  mov     rbx, rax
0x140068ab1  test    rax, rax
0x140068ab4  jnz     short loc_140068AF1
0x140068ab6  mov     rax, [rsp+48h+var_28]
0x140068abb  mov     [rsi+8], rax
0x140068abf  mov     [rsi+10h], r14
0x140068ac3  mov     [rsi+18h], rdi
0x140068ac7  mov     dword ptr [rsi], 1
0x140068acd  mov     [rsi+20h], ebp
0x140068ad0  mov     rax, cs:gWfpGlobal
0x140068ad7  inc     dword ptr [rax+6C8h]
0x140068add  mov     rax, cs:gWfpGlobal
0x140068ae4  mov     ecx, [rax+6C8h]
0x140068aea  xor     eax, eax
0x140068aec  mov     [rsi+24h], ecx
0x140068aef  jmp     short loc_140068B17
0x140068af1  test    rdi, rdi
0x140068af4  jz      short loc_140068B05
0x140068af6  lea     rcx, [rsp+48h+arg_18]
0x140068afb  call    WfpPoolFree
0x140068b00  test    rbx, rbx
0x140068b03  jz      short loc_140068B14
0x140068b05  lea     rdx, aCreatecache; "CreateCache"
0x140068b0c  mov     rcx, rbx
0x140068b0f  call    WfpReportError
0x140068b14  mov     rax, rbx
0x140068b17  mov     rbx, [rsp+48h+arg_0]
0x140068b1c  mov     rbp, [rsp+48h+arg_8]
0x140068b21  add     rsp, 30h
0x140068b25  pop     r14
0x140068b27  pop     rdi
0x140068b28  pop     rsi
0x140068b29  retn
```
