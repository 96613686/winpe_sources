# CStowedExceptionPlugin::BuildUnloadedModuleList(utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,void *)

- ea: `0x14004f2dc`
- end: `0x14004f5d6`
- name: `?BuildUnloadedModuleList@CStowedExceptionPlugin@@CAJPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@PEAX@Z`
- size: `762`
- prototype: `signed int __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x14004fc20`

## callees

- `0x140002470`
- `0x140002494`
- `0x140002d24`
- `0x1400030a8`
- `0x14004f2dc`
- `0x140050520`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x14004f542`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x14004f542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f377`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f36d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f3cd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f40d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f463`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f36d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f3cd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f40d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f463`
- `ntdll!RtlGetUnloadEventTraceEx` at `0x14004f34a`
- `ntdll!RtlGetUnloadEventTraceEx` at `0x14004f34a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
signed int __fastcall CStowedExceptionPlugin::BuildUnloadedModuleList(__int64 a1, void *a2)
{
  signed int result; // eax
  __int64 v5; // rcx
  unsigned int v6; // esi
  __int64 v7; // rdx
  _WORD *v8; // rax
  unsigned __int64 v9; // rdi
  _OWORD *v10; // rax
  _OWORD *v11; // rbx
  unsigned __int64 v12; // r14
  char v13; // al
  void *v14; // rcx
  unsigned int v15; // [rsp+30h] [rbp-99h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-91h] BYREF
  int Buffer; // [rsp+40h] [rbp-89h] BYREF
  __int64 v18; // [rsp+48h] [rbp-81h] BYREF
  void *Block; // [rsp+50h] [rbp-79h] BYREF
  LPCVOID lpBaseAddress; // [rsp+58h] [rbp-71h] BYREF
  LPCVOID v21; // [rsp+60h] [rbp-69h] BYREF
  LPCVOID v22; // [rsp+68h] [rbp-61h] BYREF
  __int64 v23; // [rsp+70h] [rbp-59h] BYREF
  int v24; // [rsp+78h] [rbp-51h]
  int v25; // [rsp+84h] [rbp-45h]
  _WORD v26[42]; // [rsp+8Ch] [rbp-3Dh] BYREF

  NumberOfBytesRead = 0;
  lpBaseAddress = 0;
  v21 = 0;
  v22 = 0;
  Buffer = 0;
  v15 = 0;
  v18 = 0;
  memset_0(&v23, 0, 0x68u);
  RtlGetUnloadEventTraceEx(&lpBaseAddress, &v21, &v22);
  if ( !ReadProcessMemory(a2, lpBaseAddress, &Buffer, 4u, &NumberOfBytesRead) )
  {
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147467259;
    return result;
  }
  if ( NumberOfBytesRead != 4 )
    return -2147024597;
  if ( Buffer != 104 )
    return -2147023266;
  if ( !ReadProcessMemory(a2, v21, &v15, 4u, &NumberOfBytesRead) )
    goto LABEL_2;
  if ( NumberOfBytesRead != 4 )
    return -2147024597;
  if ( v15 >= 0x1000 )
    v15 = 4096;
  if ( !ReadProcessMemory(a2, v22, &v18, 8u, &NumberOfBytesRead) )
    goto LABEL_2;
  if ( NumberOfBytesRead != 8 )
    return -2147024597;
  v5 = v18;
  if ( !v18 )
    return 0;
  v6 = 0;
  if ( !v15 )
    return 0;
  while ( 1 )
  {
    if ( !ReadProcessMemory(a2, (LPCVOID)(v5 + 104LL * v6), &v23, 0x68u, &NumberOfBytesRead) || NumberOfBytesRead != 104 )
      goto LABEL_35;
    v7 = 32;
    v8 = v26;
    do
    {
      if ( !*v8 )
        break;
      ++v8;
      --v7;
    }
    while ( v7 );
    v9 = (32 - v7) & -(__int64)(v7 != 0);
    if ( !v7 )
    {
      v9 = 31;
      v26[31] = 0;
    }
    v10 = operator new((unsigned int)(2 * v9 + 2) + 40LL, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( v10 )
      break;
    v14 = 0;
LABEL_33:
    if ( v14 )
      operator delete(v14);
LABEL_35:
    if ( ++v6 >= v15 )
      return 0;
    v5 = v18;
  }
  Block = v10;
  v12 = 0;
  *v10 = 0;
  v10[1] = 0;
  *((_QWORD *)v10 + 4) = 0;
  *(_QWORD *)v10 = v23;
  *((_DWORD *)v10 + 2) = v24;
  *((_DWORD *)v10 + 3) = v25;
  *((_WORD *)v10 + 8) = v26[33];
  *((_WORD *)v10 + 9) = v26[32];
  *((_WORD *)v10 + 10) = v26[35];
  *((_WORD *)v10 + 11) = v26[34];
  *((_QWORD *)v10 + 3) = (char *)v10 + 40;
  for ( *((_DWORD *)v10 + 8) = 1; v12 < v9; ++v12 )
    *(_WORD *)(*((_QWORD *)v11 + 3) + 2 * v12) = _o_towlower((unsigned __int16)v26[v12]);
  *(_WORD *)(*((_QWORD *)v11 + 3) + 2 * v9) = 0;
  v13 = utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>>::push_back(
          a1,
          &Block);
  v14 = Block;
  if ( v13 )
    goto LABEL_33;
  if ( Block )
    operator delete(Block);
  return -2147024882;
}

```

## disassembly

```asm
0x14004f2dc  mov     [rsp-8+arg_10], rbx
0x14004f2e1  push    rbp
0x14004f2e2  push    rsi
0x14004f2e3  push    rdi
0x14004f2e4  push    r12
0x14004f2e6  push    r13
0x14004f2e8  push    r14
0x14004f2ea  push    r15
0x14004f2ec  lea     rbp, [rsp-27h]
0x14004f2f1  sub     rsp, 0F0h
0x14004f2f8  mov     rax, cs:__security_cookie
0x14004f2ff  xor     rax, rsp
0x14004f302  mov     [rbp+57h+var_40], rax
0x14004f306  xor     r13d, r13d
0x14004f309  mov     r15, rdx
0x14004f30c  mov     r12, rcx
0x14004f30f  mov     [rsp+120h+NumberOfBytesRead], r13
0x14004f314  xor     edx, edx; Val
0x14004f316  mov     [rbp+57h+lpBaseAddress], r13
0x14004f31a  lea     rcx, [rbp+57h+var_B0]; void *
0x14004f31e  mov     [rbp+57h+var_C0], r13
0x14004f322  lea     r8d, [r13+68h]; Size
0x14004f326  mov     [rbp+57h+var_B8], r13
0x14004f32a  mov     [rsp+120h+Buffer], r13d
0x14004f32f  mov     [rsp+120h+var_F0], r13d
0x14004f334  mov     [rsp+120h+var_D8], r13
0x14004f339  call    memset_0
0x14004f33e  lea     r8, [rbp+57h+var_B8]
0x14004f342  lea     rdx, [rbp+57h+var_C0]
0x14004f346  lea     rcx, [rbp+57h+lpBaseAddress]
0x14004f34a  call    cs:__imp_RtlGetUnloadEventTraceEx
0x14004f350  mov     rdx, [rbp+57h+lpBaseAddress]; lpBaseAddress
0x14004f354  lea     rax, [rsp+120h+NumberOfBytesRead]
0x14004f359  lea     ebx, [r13+4]
0x14004f35d  mov     [rsp+120h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14004f362  mov     r9d, ebx; nSize
0x14004f365  lea     r8, [rsp+120h+Buffer]; lpBuffer
0x14004f36a  mov     rcx, r15; hProcess
0x14004f36d  call    cs:__imp_ReadProcessMemory
0x14004f373  test    eax, eax
0x14004f375  jnz     short loc_14004F398
0x14004f377  call    cs:__imp_GetLastError
0x14004f37d  test    eax, eax
0x14004f37f  jle     short loc_14004F389
0x14004f381  movzx   eax, ax
0x14004f384  or      eax, 80070000h
0x14004f389  test    eax, eax
0x14004f38b  mov     ecx, 80004005h
0x14004f390  cmovns  eax, ecx
0x14004f393  jmp     loc_14004F5AF
0x14004f398  cmp     [rsp+120h+NumberOfBytesRead], rbx
0x14004f39d  jnz     loc_14004F5AA
0x14004f3a3  cmp     [rsp+120h+Buffer], 68h ; 'h'
0x14004f3a8  jz      short loc_14004F3B4
0x14004f3aa  mov     eax, 8007065Eh
0x14004f3af  jmp     loc_14004F5AF
0x14004f3b4  mov     rdx, [rbp+57h+var_C0]; lpBaseAddress
0x14004f3b8  lea     rax, [rsp+120h+NumberOfBytesRead]
0x14004f3bd  mov     r9, rbx; nSize
0x14004f3c0  mov     [rsp+120h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14004f3c5  lea     r8, [rsp+120h+var_F0]; lpBuffer
0x14004f3ca  mov     rcx, r15; hProcess
0x14004f3cd  call    cs:__imp_ReadProcessMemory
0x14004f3d3  test    eax, eax
0x14004f3d5  jz      short loc_14004F377
0x14004f3d7  cmp     [rsp+120h+NumberOfBytesRead], rbx
0x14004f3dc  jnz     loc_14004F5AA
0x14004f3e2  mov     eax, 1000h
0x14004f3e7  cmp     [rsp+120h+var_F0], eax
0x14004f3eb  jb      short loc_14004F3F1
0x14004f3ed  mov     [rsp+120h+var_F0], eax
0x14004f3f1  mov     rdx, [rbp+57h+var_B8]; lpBaseAddress
0x14004f3f5  lea     rax, [rsp+120h+NumberOfBytesRead]
0x14004f3fa  mov     r9d, 8; nSize
0x14004f400  mov     [rsp+120h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14004f405  lea     r8, [rsp+120h+var_D8]; lpBuffer
0x14004f40a  mov     rcx, r15; hProcess
0x14004f40d  call    cs:__imp_ReadProcessMemory
0x14004f413  test    eax, eax
0x14004f415  jz      loc_14004F377
0x14004f41b  cmp     [rsp+120h+NumberOfBytesRead], 8
0x14004f421  jnz     loc_14004F5AA
0x14004f427  mov     rcx, [rsp+120h+var_D8]
0x14004f42c  test    rcx, rcx
0x14004f42f  jz      loc_14004F5A6
0x14004f435  mov     esi, r13d
0x14004f438  cmp     [rsp+120h+var_F0], r13d
0x14004f43d  jbe     loc_14004F5A6
0x14004f443  mov     eax, esi
0x14004f445  lea     r8, [rbp+57h+var_B0]; lpBuffer
0x14004f449  imul    rdx, rax, 68h ; 'h'
0x14004f44d  lea     rax, [rsp+120h+NumberOfBytesRead]
0x14004f452  mov     r9d, 68h ; 'h'; nSize
0x14004f458  add     rdx, rcx; lpBaseAddress
0x14004f45b  mov     [rsp+120h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14004f460  mov     rcx, r15; hProcess
0x14004f463  call    cs:__imp_ReadProcessMemory
0x14004f469  test    eax, eax
0x14004f46b  jz      loc_14004F594
0x14004f471  cmp     [rsp+120h+NumberOfBytesRead], 68h ; 'h'
0x14004f477  jnz     loc_14004F594
0x14004f47d  mov     edx, 20h ; ' '
0x14004f482  lea     rax, [rbp+57h+var_94]
0x14004f486  cmp     [rax], r13w
0x14004f48a  jz      short loc_14004F496
0x14004f48c  add     rax, 2
0x14004f490  sub     rdx, 1
0x14004f494  jnz     short loc_14004F486
0x14004f496  mov     ecx, 20h ; ' '
0x14004f49b  mov     rax, rdx
0x14004f49e  sub     rcx, rdx
0x14004f4a1  neg     rax
0x14004f4a4  sbb     rdi, rdi
0x14004f4a7  and     rdi, rcx
0x14004f4aa  test    rdx, rdx
0x14004f4ad  jnz     short loc_14004F4B7
0x14004f4af  lea     edi, [rdx+1Fh]
0x14004f4b2  mov     [rbp+57h+var_56], r13w
0x14004f4b7  lea     ecx, ds:2[rdi*2]
0x14004f4be  add     rcx, 28h ; '('; unsigned __int64
0x14004f4c2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14004f4c9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14004f4ce  mov     rbx, rax
0x14004f4d1  test    rax, rax
0x14004f4d4  jz      loc_14004F587
0x14004f4da  xor     eax, eax
0x14004f4dc  mov     [rbp+57h+Block], rbx
0x14004f4e0  xorps   xmm0, xmm0
0x14004f4e3  mov     r14, r13
0x14004f4e6  movups  xmmword ptr [rbx], xmm0
0x14004f4e9  movups  xmmword ptr [rbx+10h], xmm0
0x14004f4ed  mov     [rbx+20h], rax
0x14004f4f1  mov     rcx, [rbp+57h+var_B0]
0x14004f4f5  mov     [rbx], rcx
0x14004f4f8  mov     ecx, [rbp+57h+var_A8]
0x14004f4fb  mov     [rbx+8], ecx
0x14004f4fe  mov     eax, [rbp+57h+var_9C]
0x14004f501  mov     [rbx+0Ch], eax
0x14004f504  mov     eax, [rbp+57h+var_54]
0x14004f507  shr     eax, 10h
0x14004f50a  mov     [rbx+10h], ax
0x14004f50e  movzx   eax, word ptr [rbp+57h+var_54]
0x14004f512  mov     [rbx+12h], ax
0x14004f516  mov     eax, [rbp+57h+var_50]
0x14004f519  shr     eax, 10h
0x14004f51c  mov     [rbx+14h], ax
0x14004f520  movzx   eax, word ptr [rbp+57h+var_50]
0x14004f524  mov     [rbx+16h], ax
0x14004f528  lea     rax, [rbx+28h]
0x14004f52c  mov     [rbx+18h], rax
0x14004f530  mov     dword ptr [rbx+20h], 1
0x14004f537  test    rdi, rdi
0x14004f53a  jz      short loc_14004F559
0x14004f53c  movzx   ecx, [rbp+r14*2+57h+var_94]
0x14004f542  call    cs:__imp__o_towlower
0x14004f548  mov     rcx, [rbx+18h]
0x14004f54c  mov     [rcx+r14*2], ax
0x14004f551  inc     r14
0x14004f554  cmp     r14, rdi
0x14004f557  jb      short loc_14004F53C
0x14004f559  mov     rcx, [rbx+18h]
0x14004f55d  lea     rdx, [rbp+57h+Block]
0x14004f561  mov     [rcx+rdi*2], r13w
0x14004f566  mov     rcx, r12
0x14004f569  call    ?push_back@?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@2@@Z; utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>>::push_back(utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>> &&)
0x14004f56e  mov     rcx, [rbp+57h+Block]; Block
0x14004f572  test    al, al
0x14004f574  jnz     short loc_14004F58A
0x14004f576  test    rcx, rcx
0x14004f579  jz      short loc_14004F580
0x14004f57b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004f580  mov     eax, 8007000Eh
0x14004f585  jmp     short loc_14004F5AF
0x14004f587  mov     rcx, r13; Block
0x14004f58a  test    rcx, rcx
0x14004f58d  jz      short loc_14004F594
0x14004f58f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004f594  inc     esi
0x14004f596  cmp     esi, [rsp+120h+var_F0]
0x14004f59a  jnb     short loc_14004F5A6
0x14004f59c  mov     rcx, [rsp+120h+var_D8]
0x14004f5a1  jmp     loc_14004F443
0x14004f5a6  xor     eax, eax
0x14004f5a8  jmp     short loc_14004F5AF
0x14004f5aa  mov     eax, 8007012Bh
0x14004f5af  mov     rcx, [rbp+57h+var_40]
0x14004f5b3  xor     rcx, rsp; StackCookie
0x14004f5b6  call    __security_check_cookie
0x14004f5bb  mov     rbx, [rsp+120h+arg_10]
0x14004f5c3  add     rsp, 0F0h
0x14004f5ca  pop     r15
0x14004f5cc  pop     r14
0x14004f5ce  pop     r13
0x14004f5d0  pop     r12
0x14004f5d2  pop     rdi
0x14004f5d3  pop     rsi
0x14004f5d4  pop     rbp
0x14004f5d5  retn
```
