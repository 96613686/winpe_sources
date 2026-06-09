# CStowedExceptionPlugin::BuildUnloadedModuleList(utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,void *)

- ea: `0x1400529b0`
- end: `0x140052cd5`
- name: `?BuildUnloadedModuleList@CStowedExceptionPlugin@@CAJPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@PEAX@Z`
- size: `805`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x1400533b0`

## callees

- `0x140002490`
- `0x1400024b4`
- `0x140002d74`
- `0x1400030f8`
- `0x1400529b0`
- `0x140053ce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x140052c3a`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x140052c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052a57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052a57`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140052a47`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140052ab3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140052af9`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140052b55`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140052a47`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140052ab3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140052af9`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140052b55`
- `ntdll!RtlGetUnloadEventTraceEx` at `0x140052a1e`
- `ntdll!RtlGetUnloadEventTraceEx` at `0x140052a1e`

## pseudocode

```c
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
0x1400529b0  mov     [rsp-8+arg_10], rbx
0x1400529b5  push    rbp
0x1400529b6  push    rsi
0x1400529b7  push    rdi
0x1400529b8  push    r12
0x1400529ba  push    r13
0x1400529bc  push    r14
0x1400529be  push    r15
0x1400529c0  lea     rbp, [rsp-27h]
0x1400529c5  sub     rsp, 0F0h
0x1400529cc  mov     rax, cs:__security_cookie
0x1400529d3  xor     rax, rsp
0x1400529d6  mov     [rbp+57h+var_40], rax
0x1400529da  xor     r13d, r13d
0x1400529dd  mov     r15, rdx
0x1400529e0  mov     r12, rcx
0x1400529e3  mov     [rsp+120h+NumberOfBytesRead], r13
0x1400529e8  xor     edx, edx; Val
0x1400529ea  mov     [rbp+57h+lpBaseAddress], r13
0x1400529ee  lea     rcx, [rbp+57h+var_B0]; void *
0x1400529f2  mov     [rbp+57h+var_C0], r13
0x1400529f6  lea     r8d, [r13+68h]; Size
0x1400529fa  mov     [rbp+57h+var_B8], r13
0x1400529fe  mov     [rsp+120h+Buffer], r13d
0x140052a03  mov     [rsp+120h+var_F0], r13d
0x140052a08  mov     [rsp+120h+var_D8], r13
0x140052a0d  call    memset_0
0x140052a12  lea     r8, [rbp+57h+var_B8]
0x140052a16  lea     rdx, [rbp+57h+var_C0]
0x140052a1a  lea     rcx, [rbp+57h+lpBaseAddress]
0x140052a1e  call    cs:__imp_RtlGetUnloadEventTraceEx
0x140052a25  nop     dword ptr [rax+rax+00h]
0x140052a2a  mov     rdx, [rbp+57h+lpBaseAddress]; lpBaseAddress
0x140052a2e  lea     rax, [rsp+120h+NumberOfBytesRead]
0x140052a33  lea     ebx, [r13+4]
0x140052a37  mov     [rsp+120h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x140052a3c  mov     r9d, ebx; nSize
0x140052a3f  lea     r8, [rsp+120h+Buffer]; lpBuffer
0x140052a44  mov     rcx, r15; hProcess
0x140052a47  call    cs:__imp_ReadProcessMemory
0x140052a4e  nop     dword ptr [rax+rax+00h]
0x140052a53  test    eax, eax
0x140052a55  jnz     short loc_140052A7E
0x140052a57  call    cs:__imp_GetLastError
0x140052a5e  nop     dword ptr [rax+rax+00h]
0x140052a63  test    eax, eax
0x140052a65  jle     short loc_140052A6F
0x140052a67  movzx   eax, ax
0x140052a6a  or      eax, 80070000h
0x140052a6f  test    eax, eax
0x140052a71  mov     ecx, 80004005h
0x140052a76  cmovns  eax, ecx
0x140052a79  jmp     loc_140052CAD
0x140052a7e  cmp     [rsp+120h+NumberOfBytesRead], rbx
0x140052a83  jnz     loc_140052CA8
0x140052a89  cmp     [rsp+120h+Buffer], 68h ; 'h'
0x140052a8e  jz      short loc_140052A9A
0x140052a90  mov     eax, 8007065Eh
0x140052a95  jmp     loc_140052CAD
0x140052a9a  mov     rdx, [rbp+57h+var_C0]; lpBaseAddress
0x140052a9e  lea     rax, [rsp+120h+NumberOfBytesRead]
0x140052aa3  mov     r9, rbx; nSize
0x140052aa6  mov     [rsp+120h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x140052aab  lea     r8, [rsp+120h+var_F0]; lpBuffer
0x140052ab0  mov     rcx, r15; hProcess
0x140052ab3  call    cs:__imp_ReadProcessMemory
0x140052aba  nop     dword ptr [rax+rax+00h]
0x140052abf  test    eax, eax
0x140052ac1  jz      short loc_140052A57
0x140052ac3  cmp     [rsp+120h+NumberOfBytesRead], rbx
0x140052ac8  jnz     loc_140052CA8
0x140052ace  mov     eax, 1000h
0x140052ad3  cmp     [rsp+120h+var_F0], eax
0x140052ad7  jb      short loc_140052ADD
0x140052ad9  mov     [rsp+120h+var_F0], eax
0x140052add  mov     rdx, [rbp+57h+var_B8]; lpBaseAddress
0x140052ae1  lea     rax, [rsp+120h+NumberOfBytesRead]
0x140052ae6  mov     r9d, 8; nSize
0x140052aec  mov     [rsp+120h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x140052af1  lea     r8, [rsp+120h+var_D8]; lpBuffer
0x140052af6  mov     rcx, r15; hProcess
0x140052af9  call    cs:__imp_ReadProcessMemory
0x140052b00  nop     dword ptr [rax+rax+00h]
0x140052b05  test    eax, eax
0x140052b07  jz      loc_140052A57
0x140052b0d  cmp     [rsp+120h+NumberOfBytesRead], 8
0x140052b13  jnz     loc_140052CA8
0x140052b19  mov     rcx, [rsp+120h+var_D8]
0x140052b1e  test    rcx, rcx
0x140052b21  jz      loc_140052CA4
0x140052b27  mov     esi, r13d
0x140052b2a  cmp     [rsp+120h+var_F0], r13d
0x140052b2f  jbe     loc_140052CA4
0x140052b35  mov     eax, esi
0x140052b37  lea     r8, [rbp+57h+var_B0]; lpBuffer
0x140052b3b  imul    rdx, rax, 68h ; 'h'
0x140052b3f  lea     rax, [rsp+120h+NumberOfBytesRead]
0x140052b44  mov     r9d, 68h ; 'h'; nSize
0x140052b4a  add     rdx, rcx; lpBaseAddress
0x140052b4d  mov     [rsp+120h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x140052b52  mov     rcx, r15; hProcess
0x140052b55  call    cs:__imp_ReadProcessMemory
0x140052b5c  nop     dword ptr [rax+rax+00h]
0x140052b61  test    eax, eax
0x140052b63  jz      loc_140052C92
0x140052b69  cmp     [rsp+120h+NumberOfBytesRead], 68h ; 'h'
0x140052b6f  jnz     loc_140052C92
0x140052b75  mov     edx, 20h ; ' '
0x140052b7a  lea     rax, [rbp+57h+var_94]
0x140052b7e  cmp     [rax], r13w
0x140052b82  jz      short loc_140052B8E
0x140052b84  add     rax, 2
0x140052b88  sub     rdx, 1
0x140052b8c  jnz     short loc_140052B7E
0x140052b8e  mov     ecx, 20h ; ' '
0x140052b93  mov     rax, rdx
0x140052b96  sub     rcx, rdx
0x140052b99  neg     rax
0x140052b9c  sbb     rdi, rdi
0x140052b9f  and     rdi, rcx
0x140052ba2  test    rdx, rdx
0x140052ba5  jnz     short loc_140052BAF
0x140052ba7  lea     edi, [rdx+1Fh]
0x140052baa  mov     [rbp+57h+var_56], r13w
0x140052baf  lea     ecx, ds:2[rdi*2]
0x140052bb6  add     rcx, 28h ; '('; unsigned __int64
0x140052bba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140052bc1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140052bc6  mov     rbx, rax
0x140052bc9  test    rax, rax
0x140052bcc  jz      loc_140052C85
0x140052bd2  xor     eax, eax
0x140052bd4  mov     [rbp+57h+Block], rbx
0x140052bd8  xorps   xmm0, xmm0
0x140052bdb  mov     r14, r13
0x140052bde  movups  xmmword ptr [rbx], xmm0
0x140052be1  movups  xmmword ptr [rbx+10h], xmm0
0x140052be5  mov     [rbx+20h], rax
0x140052be9  mov     rcx, [rbp+57h+var_B0]
0x140052bed  mov     [rbx], rcx
0x140052bf0  mov     ecx, [rbp+57h+var_A8]
0x140052bf3  mov     [rbx+8], ecx
0x140052bf6  mov     eax, [rbp+57h+var_9C]
0x140052bf9  mov     [rbx+0Ch], eax
0x140052bfc  mov     eax, [rbp+57h+var_54]
0x140052bff  shr     eax, 10h
0x140052c02  mov     [rbx+10h], ax
0x140052c06  movzx   eax, word ptr [rbp+57h+var_54]
0x140052c0a  mov     [rbx+12h], ax
0x140052c0e  mov     eax, [rbp+57h+var_50]
0x140052c11  shr     eax, 10h
0x140052c14  mov     [rbx+14h], ax
0x140052c18  movzx   eax, word ptr [rbp+57h+var_50]
0x140052c1c  mov     [rbx+16h], ax
0x140052c20  lea     rax, [rbx+28h]
0x140052c24  mov     [rbx+18h], rax
0x140052c28  mov     dword ptr [rbx+20h], 1
0x140052c2f  test    rdi, rdi
0x140052c32  jz      short loc_140052C57
0x140052c34  movzx   ecx, [rbp+r14*2+57h+var_94]
0x140052c3a  call    cs:__imp__o_towlower
0x140052c41  nop     dword ptr [rax+rax+00h]
0x140052c46  mov     rcx, [rbx+18h]
0x140052c4a  mov     [rcx+r14*2], ax
0x140052c4f  inc     r14
0x140052c52  cmp     r14, rdi
0x140052c55  jb      short loc_140052C34
0x140052c57  mov     rcx, [rbx+18h]
0x140052c5b  lea     rdx, [rbp+57h+Block]
0x140052c5f  mov     [rcx+rdi*2], r13w
0x140052c64  mov     rcx, r12
0x140052c67  call    ?push_back@?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@2@@Z; utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>>::push_back(utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>> &&)
0x140052c6c  mov     rcx, [rbp+57h+Block]; Block
0x140052c70  test    al, al
0x140052c72  jnz     short loc_140052C88
0x140052c74  test    rcx, rcx
0x140052c77  jz      short loc_140052C7E
0x140052c79  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140052c7e  mov     eax, 8007000Eh
0x140052c83  jmp     short loc_140052CAD
0x140052c85  mov     rcx, r13; Block
0x140052c88  test    rcx, rcx
0x140052c8b  jz      short loc_140052C92
0x140052c8d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140052c92  inc     esi
0x140052c94  cmp     esi, [rsp+120h+var_F0]
0x140052c98  jnb     short loc_140052CA4
0x140052c9a  mov     rcx, [rsp+120h+var_D8]
0x140052c9f  jmp     loc_140052B35
0x140052ca4  xor     eax, eax
0x140052ca6  jmp     short loc_140052CAD
0x140052ca8  mov     eax, 8007012Bh
0x140052cad  mov     rcx, [rbp+57h+var_40]
0x140052cb1  xor     rcx, rsp; StackCookie
0x140052cb4  call    __security_check_cookie
0x140052cb9  mov     rbx, [rsp+120h+arg_10]
0x140052cc1  add     rsp, 0F0h
0x140052cc8  pop     r15
0x140052cca  pop     r14
0x140052ccc  pop     r13
0x140052cce  pop     r12
0x140052cd0  pop     rdi
0x140052cd1  pop     rsi
0x140052cd2  pop     rbp
0x140052cd3  retn
```
