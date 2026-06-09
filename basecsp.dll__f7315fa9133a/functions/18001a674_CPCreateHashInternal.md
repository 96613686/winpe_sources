# CPCreateHashInternal

- ea: `0x18001a674`
- end: `0x18001a7da`
- name: `CPCreateHashInternal`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001a650`

## callees

- `0x18000de80`
- `0x180019430`
- `0x180019650`
- `0x18001a674`
- `0x18001c218`
- `0x18001c2d4`
- `0x18001c96c`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a799`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a7c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a7c1`
- `CRYPTSP!CryptCreateHash` at `0x18001a78f`
- `CRYPTSP!CryptCreateHash` at `0x18001a78f`

## pseudocode

```c
__int64 __fastcall CPCreateHashInternal(HCRYPTPROV *a1, ALG_ID a2, __int64 a3, DWORD a4, HCRYPTHASH **a5)
{
  HCRYPTHASH **v5; // r14
  unsigned int v6; // edi
  HCRYPTHASH *v12; // rax
  __int64 v13; // rcx
  HCRYPTHASH *v14; // rbx
  __int64 v15; // rsi
  int v16; // eax
  HCRYPTKEY v17; // r8
  unsigned int v18; // [rsp+80h] [rbp+8h] BYREF

  v5 = a5;
  v6 = 0;
  v18 = 0;
  if ( !a5 )
    return 87;
  *a5 = 0;
  LODWORD(a5) = 0;
  v12 = (HCRYPTHASH *)MIDL_user_allocate(0x20u);
  v14 = v12;
  if ( !v12 )
  {
    WppTraceIndent(v13, 2);
    LODWORD(v15) = 8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b43b3ea2fd9e3cf0f45da766fe22fd5f_Traceguids, WPP_pszIndent);
    }
    goto LABEL_17;
  }
  *((_DWORD *)v12 + 5) = a2;
  LODWORD(v15) = 0;
  *((_DWORD *)v12 + 4) = a4;
  *v12 = (HCRYPTHASH)a1;
  if ( !qword_18003B078
    || (v15 = (unsigned int)qword_18003B078(v12, a3, &a5), v16 = CheckLocalCallInfo(&a5, v15, &v18), v6 = v18, v16) )
  {
    if ( a3 )
      v17 = *(_QWORD *)(a3 + 8);
    else
      v17 = 0;
    if ( CryptCreateHash(*a1, a2, v17, a4, v14 + 1) )
    {
      *v5 = v14;
      v6 = 1;
      goto LABEL_17;
    }
    LODWORD(v15) = GetLastError();
  }
  DeleteHashContext(v14);
  CspFreeH(v14);
LABEL_17:
  if ( !v6 )
    SetLastError(v15);
  return v6;
}

```

## disassembly

```asm
0x18001a674  mov     rax, rsp
0x18001a677  push    rbx
0x18001a678  push    rbp
0x18001a679  push    rsi
0x18001a67a  push    rdi
0x18001a67b  push    r12
0x18001a67d  push    r13
0x18001a67f  push    r14
0x18001a681  push    r15
0x18001a683  sub     rsp, 38h
0x18001a687  mov     r14, [rsp+78h+arg_20]
0x18001a68f  xor     edi, edi
0x18001a691  mov     [rax+8], edi
0x18001a694  mov     r15d, r9d
0x18001a697  mov     rbp, r8
0x18001a69a  mov     r12d, edx
0x18001a69d  mov     r13, rcx
0x18001a6a0  test    r14, r14
0x18001a6a3  jnz     short loc_18001A6AD
0x18001a6a5  lea     eax, [rdi+57h]
0x18001a6a8  jmp     loc_18001A7C9
0x18001a6ad  mov     ecx, 20h ; ' '; size
0x18001a6b2  mov     [r14], rdi
0x18001a6b5  mov     dword ptr [rsp+78h+arg_20], edi
0x18001a6bc  call    MIDL_user_allocate
0x18001a6c1  mov     rbx, rax
0x18001a6c4  test    rax, rax
0x18001a6c7  jnz     short loc_18001A71E
0x18001a6c9  lea     edx, [rax+2]
0x18001a6cc  call    WppTraceIndent
0x18001a6d1  lea     esi, [rbx+8]
0x18001a6d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6db  lea     rax, WPP_GLOBAL_Control
0x18001a6e2  cmp     rcx, rax
0x18001a6e5  jz      loc_18001A7BB
0x18001a6eb  test    byte ptr [rcx+1Ch], 1
0x18001a6ef  jz      loc_18001A7BB
0x18001a6f5  cmp     byte ptr [rcx+19h], 2
0x18001a6f9  jb      loc_18001A7BB
0x18001a6ff  mov     r9, cs:WPP_pszIndent
0x18001a706  lea     edx, [rbx+10h]
0x18001a709  mov     rcx, [rcx+10h]
0x18001a70d  lea     r8, WPP_b43b3ea2fd9e3cf0f45da766fe22fd5f_Traceguids
0x18001a714  call    WPP_SF_s
0x18001a719  jmp     loc_18001A7BB
0x18001a71e  mov     [rax+14h], r12d
0x18001a722  xor     esi, esi
0x18001a724  mov     [rax+10h], r15d
0x18001a728  mov     [rax], r13
0x18001a72b  mov     rax, cs:qword_18003B078
0x18001a732  test    rax, rax
0x18001a735  jz      short loc_18001A76E
0x18001a737  lea     r8, [rsp+78h+arg_20]
0x18001a73f  mov     rdx, rbp
0x18001a742  mov     rcx, rbx
0x18001a745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a74a  lea     r8, [rsp+78h+arg_0]
0x18001a752  mov     edx, eax
0x18001a754  lea     rcx, [rsp+78h+arg_20]
0x18001a75c  mov     esi, eax
0x18001a75e  call    CheckLocalCallInfo
0x18001a763  mov     edi, [rsp+78h+arg_0]
0x18001a76a  test    eax, eax
0x18001a76c  jz      short loc_18001A7A1
0x18001a76e  test    rbp, rbp
0x18001a771  jz      short loc_18001A779
0x18001a773  mov     r8, [rbp+8]
0x18001a777  jmp     short loc_18001A77C
0x18001a779  xor     r8d, r8d; hKey
0x18001a77c  mov     rcx, [r13+0]; hProv
0x18001a780  lea     rax, [rbx+8]
0x18001a784  mov     r9d, r15d; dwFlags
0x18001a787  mov     [rsp+78h+phHash], rax; phHash
0x18001a78c  mov     edx, r12d; Algid
0x18001a78f  call    cs:__imp_CryptCreateHash
0x18001a795  test    eax, eax
0x18001a797  jnz     short loc_18001A7B3
0x18001a799  call    cs:__imp_GetLastError
0x18001a79f  mov     esi, eax
0x18001a7a1  mov     rcx, rbx
0x18001a7a4  call    DeleteHashContext
0x18001a7a9  mov     rcx, rbx
0x18001a7ac  call    CspFreeH
0x18001a7b1  jmp     short loc_18001A7BB
0x18001a7b3  mov     [r14], rbx
0x18001a7b6  mov     edi, 1
0x18001a7bb  test    edi, edi
0x18001a7bd  jnz     short loc_18001A7C7
0x18001a7bf  mov     ecx, esi; dwErrCode
0x18001a7c1  call    cs:__imp_SetLastError
0x18001a7c7  mov     eax, edi
0x18001a7c9  add     rsp, 38h
0x18001a7cd  pop     r15
0x18001a7cf  pop     r14
0x18001a7d1  pop     r13
0x18001a7d3  pop     r12
0x18001a7d5  pop     rdi
0x18001a7d6  pop     rsi
0x18001a7d7  pop     rbp
0x18001a7d8  pop     rbx
0x18001a7d9  retn
```
