# _lambda_d08e70a79089e89c441a40e2cff7cb32_::operator()

- ea: `0x18003c2d4`
- end: `0x18003c670`
- name: `_lambda_d08e70a79089e89c441a40e2cff7cb32_::operator()`
- size: `924`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003c678`

## callees

- `0x18000c190`
- `0x180011d40`
- `0x18003c2d4`
- `0x1800543c0`
- `0x180065150`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c3b9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c3e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c415`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c499`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c4e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c52d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c577`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c3b9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c3e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c415`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c499`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c4e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c52d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c577`
- `KERNEL32!GetLastError` at `0x18003c34c`
- `KERNEL32!GetLastError` at `0x18003c37a`
- `KERNEL32!GetLastError` at `0x18003c34c`
- `KERNEL32!GetLastError` at `0x18003c37a`
- `SHELL32!CommandLineToArgvW` at `0x18003c32a`
- `SHELL32!CommandLineToArgvW` at `0x18003c32a`

## string_xrefs

- `0x18003c356`: `CommandLineToArgvW failed %d, %ws, numArgs=%d`
- `0x18003c305`: `Commandline: %ws`
- `0x18003c640`: `CommandLine is null/empty.`
- `0x18003c314`: `ParseCommandLineAndSetDefaults::<lambda_d08e70a79089e89c441a40e2cff7cb32>::operator ()`
- `0x18003c366`: `ParseCommandLineAndSetDefaults::<lambda_d08e70a79089e89c441a40e2cff7cb32>::operator ()`
- `0x18003c5cc`: `ParseCommandLineAndSetDefaults::<lambda_d08e70a79089e89c441a40e2cff7cb32>::operator ()`
- `0x18003c64d`: `ParseCommandLineAndSetDefaults::<lambda_d08e70a79089e89c441a40e2cff7cb32>::operator ()`

## pseudocode

```c
signed int __fastcall lambda_d08e70a79089e89c441a40e2cff7cb32_::operator()(LPCWSTR **a1)
{
  _WORD *v2; // rcx
  LPCWSTR v3; // rbx
  signed int result; // eax
  int v5; // esi
  _QWORD **v6; // r14
  __int64 v7; // rbx
  _QWORD **v8; // rax
  _WORD *v9; // r9
  __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  char *v12; // rbp
  __int64 v13; // rbx
  _QWORD **v14; // rbx
  _QWORD *v15; // rax
  __int64 v16; // [rsp+20h] [rbp-58h]
  int v17; // [rsp+30h] [rbp-48h]

  v2 = **a1;
  if ( !v2 || !*v2 )
  {
    AslLogCallPrintf(
      1,
      "ParseCommandLineAndSetDefaults::<lambda_d08e70a79089e89c441a40e2cff7cb32>::operator ()",
      82,
      "CommandLine is null/empty.");
    return -2147024809;
  }
  AslLogCallPrintf(
    3,
    "ParseCommandLineAndSetDefaults::<lambda_d08e70a79089e89c441a40e2cff7cb32>::operator ()",
    86,
    "Commandline: %ws",
    v2);
  *a1[1] = (LPCWSTR)CommandLineToArgvW(**a1, (int *)a1[2]);
  if ( !*a1[1] )
  {
    v3 = **a1;
    v17 = *(_DWORD *)a1[2];
    LODWORD(v16) = GetLastError();
    AslLogCallPrintf(
      1,
      "ParseCommandLineAndSetDefaults::<lambda_d08e70a79089e89c441a40e2cff7cb32>::operator ()",
      95,
      "CommandLineToArgvW failed %d, %ws, numArgs=%d",
      v16,
      v3,
      v17);
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v5 = 0;
  if ( *(int *)a1[2] > 0 )
  {
    v6 = a1 + 3;
    while ( 1 )
    {
      v7 = v5;
      if ( (unsigned int)_o__wcsicmp(L"-Collect", *(_QWORD *)&(*a1[1])[4 * v5]) )
        break;
      *(_DWORD *)a1[3] = 1;
      v8 = a1 + 3;
LABEL_41:
      v14 = v6;
      ++v5;
      v6 = v8;
      if ( v5 >= *(_DWORD *)a1[2] )
        goto LABEL_45;
    }
    if ( (unsigned int)_o__wcsicmp(L"-Apply", *(_QWORD *)&(*a1[1])[4 * v5]) )
    {
      ++v5;
      if ( (unsigned int)_o__wcsicmp(L"-Key", *(_QWORD *)&(*a1[1])[4 * v7]) || v5 >= *(_DWORD *)a1[2] )
      {
        if ( (unsigned int)_o__wcsicmp(L"-Value", *(_QWORD *)&(*a1[1])[4 * v7]) || v5 >= *(_DWORD *)a1[2] )
        {
          if ( (unsigned int)_o__wcsicmp(L"-NewKey", *(_QWORD *)&(*a1[1])[4 * v7]) || v5 >= *(_DWORD *)a1[2] )
          {
            if ( (unsigned int)_o__wcsicmp(L"-NewValue", *(_QWORD *)&(*a1[1])[4 * v7]) || v5 >= *(_DWORD *)a1[2] )
            {
              if ( (unsigned int)_o__wcsicmp(L"-ConcatChar", *(_QWORD *)&(*a1[1])[4 * v7]) || v5 >= *(_DWORD *)a1[2] )
              {
                AslLogCallPrintf(
                  1,
                  "ParseCommandLineAndSetDefaults::<lambda_d08e70a79089e89c441a40e2cff7cb32>::operator ()",
                  139,
                  "Unexpected parameter '%ls'.",
                  *(const wchar_t **)&(*a1[1])[4 * v7]);
                return -2147024809;
              }
              *((_WORD *)*v6 + 68) = **(_WORD **)&(*a1[1])[4 * v7 + 4];
              goto LABEL_40;
            }
            v9 = *(_WORD **)&(*a1[1])[4 * v7 + 4];
            v10 = (__int64)(*v6 + 13);
            v11 = -1;
            do
              ++v11;
            while ( v9[v11] );
          }
          else
          {
            v9 = *(_WORD **)&(*a1[1])[4 * v7 + 4];
            v10 = (__int64)(*v6 + 9);
            v11 = -1;
            do
              ++v11;
            while ( v9[v11] );
          }
        }
        else
        {
          v9 = *(_WORD **)&(*a1[1])[4 * v7 + 4];
          v10 = (__int64)(*v6 + 5);
          v11 = -1;
          do
            ++v11;
          while ( v9[v11] );
        }
      }
      else
      {
        v9 = *(_WORD **)&(*a1[1])[4 * v7 + 4];
        v10 = (__int64)(*v6 + 1);
        v11 = -1;
        do
          ++v11;
        while ( v9[v11] );
      }
      if ( v11 > *(_QWORD *)(v10 + 24) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v10);
      }
      else
      {
        if ( *(_QWORD *)(v10 + 24) <= 7u )
          v12 = (char *)v10;
        else
          v12 = *(char **)v10;
        v13 = 2 * v11;
        *(_QWORD *)(v10 + 16) = v11;
        memmove_0(v12, v9, 2 * v11);
        *(_WORD *)&v12[v13] = 0;
      }
    }
    else
    {
      *((_DWORD *)*v6 + 1) = 1;
    }
LABEL_40:
    v8 = v6;
    goto LABEL_41;
  }
  v14 = a1 + 3;
LABEL_45:
  v15 = *v14;
  if ( !(*v14)[3] || !v15[7] || !v15[15] )
  {
    AslLogCallPrintf(
      1,
      "ParseCommandLineAndSetDefaults::<lambda_d08e70a79089e89c441a40e2cff7cb32>::operator ()",
      151,
      "Missing parameters. -Key, -Value and -NewValue are required.");
    return -2147024809;
  }
  if ( !v15[11] )
    std::wstring::operator=(v15 + 9, *v14 + 1);
  if ( !*((_WORD *)*v14 + 68) )
    *((_WORD *)*v14 + 68) = 59;
  return 0;
}

```

## disassembly

```asm
0x18003c2d4  push    rbx
0x18003c2d6  push    rbp
0x18003c2d7  push    rsi
0x18003c2d8  push    rdi
0x18003c2d9  push    r13
0x18003c2db  push    r14
0x18003c2dd  sub     rsp, 48h
0x18003c2e1  mov     rax, [rcx]
0x18003c2e4  mov     rdi, rcx
0x18003c2e7  xor     r13d, r13d
0x18003c2ea  mov     rcx, [rax]
0x18003c2ed  test    rcx, rcx
0x18003c2f0  jz      loc_18003C640
0x18003c2f6  cmp     r13w, [rcx]
0x18003c2fa  jz      loc_18003C640
0x18003c300  mov     [rsp+78h+var_58], rcx
0x18003c305  lea     r9, aCommandlineWs; "Commandline: %ws"
0x18003c30c  lea     ecx, [r13+3]
0x18003c310  lea     r8d, [r13+56h]
0x18003c314  lea     rdx, aParsecommandli_0; "ParseCommandLineAndSetDefaults::<lambda"...
0x18003c31b  call    AslLogCallPrintf
0x18003c320  mov     rcx, [rdi]
0x18003c323  mov     rdx, [rdi+10h]; pNumArgs
0x18003c327  mov     rcx, [rcx]; lpCmdLine
0x18003c32a  call    cs:__imp_CommandLineToArgvW
0x18003c330  mov     rcx, [rdi+8]
0x18003c334  mov     [rcx], rax
0x18003c337  mov     rax, [rdi+10h]
0x18003c33b  mov     ebp, [rax]
0x18003c33d  mov     rax, [rdi+8]
0x18003c341  cmp     [rax], r13
0x18003c344  jnz     short loc_18003C395
0x18003c346  mov     rax, [rdi]
0x18003c349  mov     rbx, [rax]
0x18003c34c  call    cs:__imp_GetLastError
0x18003c352  mov     [rsp+78h+var_48], ebp
0x18003c356  lea     r9, aCommandlinetoa_0; "CommandLineToArgvW failed %d, %ws, numA"...
0x18003c35d  mov     [rsp+78h+var_50], rbx
0x18003c362  lea     r8d, [r13+5Fh]
0x18003c366  lea     rdx, aParsecommandli_0; "ParseCommandLineAndSetDefaults::<lambda"...
0x18003c36d  mov     dword ptr [rsp+78h+var_58], eax
0x18003c371  lea     ecx, [r13+1]
0x18003c375  call    AslLogCallPrintf
0x18003c37a  call    cs:__imp_GetLastError
0x18003c380  test    eax, eax
0x18003c382  jle     loc_18003C663
0x18003c388  movzx   eax, ax
0x18003c38b  or      eax, 80070000h
0x18003c390  jmp     loc_18003C663
0x18003c395  mov     esi, r13d
0x18003c398  test    ebp, ebp
0x18003c39a  jle     loc_18003C5EB
0x18003c3a0  lea     r14, [rdi+18h]
0x18003c3a4  mov     rax, [rdi+8]
0x18003c3a8  lea     rcx, aCollect_0; "-Collect"
0x18003c3af  movsxd  rbx, esi
0x18003c3b2  mov     rdx, [rax]
0x18003c3b5  mov     rdx, [rdx+rbx*8]
0x18003c3b9  call    cs:__imp__o__wcsicmp
0x18003c3bf  test    eax, eax
0x18003c3c1  jnz     short loc_18003C3D6
0x18003c3c3  mov     rax, [rdi+18h]
0x18003c3c7  mov     dword ptr [rax], 1
0x18003c3cd  lea     rax, [rdi+18h]
0x18003c3d1  jmp     loc_18003C5A5
0x18003c3d6  mov     rax, [rdi+8]
0x18003c3da  lea     rcx, aApply_0; "-Apply"
0x18003c3e1  mov     rdx, [rax]
0x18003c3e4  mov     rdx, [rdx+rbx*8]
0x18003c3e8  call    cs:__imp__o__wcsicmp
0x18003c3ee  test    eax, eax
0x18003c3f0  jnz     short loc_18003C401
0x18003c3f2  mov     rax, [r14]
0x18003c3f5  mov     dword ptr [rax+4], 1
0x18003c3fc  jmp     loc_18003C5A2
0x18003c401  mov     rax, [rdi+8]
0x18003c405  lea     rcx, aKey; "-Key"
0x18003c40c  inc     esi
0x18003c40e  mov     rdx, [rax]
0x18003c411  mov     rdx, [rdx+rbx*8]
0x18003c415  call    cs:__imp__o__wcsicmp
0x18003c41b  test    eax, eax
0x18003c41d  jnz     short loc_18003C487
0x18003c41f  mov     rax, [rdi+10h]
0x18003c423  cmp     esi, [rax]
0x18003c425  jge     short loc_18003C487
0x18003c427  mov     rax, [rdi+8]
0x18003c42b  mov     rcx, [rax]
0x18003c42e  mov     r9, [rcx+rbx*8+8]
0x18003c433  mov     rcx, [r14]
0x18003c436  add     rcx, 8
0x18003c43a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003c43e  inc     rdx
0x18003c441  cmp     [r9+rdx*2], r13w
0x18003c446  jnz     short loc_18003C43E
0x18003c448  cmp     rdx, [rcx+18h]
0x18003c44c  ja      short loc_18003C47D
0x18003c44e  cmp     qword ptr [rcx+18h], 7
0x18003c453  jbe     short loc_18003C45A
0x18003c455  mov     rbp, [rcx]
0x18003c458  jmp     short loc_18003C45D
0x18003c45a  mov     rbp, rcx
0x18003c45d  lea     rbx, [rdx+rdx]
0x18003c461  mov     [rcx+10h], rdx
0x18003c465  mov     r8, rbx; Size
0x18003c468  mov     rdx, r9; Src
0x18003c46b  mov     rcx, rbp; void *
0x18003c46e  call    memmove_0
0x18003c473  mov     [rbx+rbp], r13w
0x18003c478  jmp     loc_18003C5A2
0x18003c47d  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18003c482  jmp     loc_18003C5A2
0x18003c487  mov     rax, [rdi+8]
0x18003c48b  lea     rcx, aValue; "-Value"
0x18003c492  mov     rdx, [rax]
0x18003c495  mov     rdx, [rdx+rbx*8]
0x18003c499  call    cs:__imp__o__wcsicmp
0x18003c49f  test    eax, eax
0x18003c4a1  jnz     short loc_18003C4D1
0x18003c4a3  mov     rax, [rdi+10h]
0x18003c4a7  cmp     esi, [rax]
0x18003c4a9  jge     short loc_18003C4D1
0x18003c4ab  mov     rax, [rdi+8]
0x18003c4af  mov     rcx, [rax]
0x18003c4b2  mov     r9, [rcx+rbx*8+8]
0x18003c4b7  mov     rcx, [r14]
0x18003c4ba  add     rcx, 28h ; '('
0x18003c4be  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003c4c2  inc     rdx
0x18003c4c5  cmp     [r9+rdx*2], r13w
0x18003c4ca  jnz     short loc_18003C4C2
0x18003c4cc  jmp     loc_18003C448
0x18003c4d1  mov     rax, [rdi+8]
0x18003c4d5  lea     rcx, aNewkey; "-NewKey"
0x18003c4dc  mov     rdx, [rax]
0x18003c4df  mov     rdx, [rdx+rbx*8]
0x18003c4e3  call    cs:__imp__o__wcsicmp
0x18003c4e9  test    eax, eax
0x18003c4eb  jnz     short loc_18003C51B
0x18003c4ed  mov     rax, [rdi+10h]
0x18003c4f1  cmp     esi, [rax]
0x18003c4f3  jge     short loc_18003C51B
0x18003c4f5  mov     rax, [rdi+8]
0x18003c4f9  mov     rcx, [rax]
0x18003c4fc  mov     r9, [rcx+rbx*8+8]
0x18003c501  mov     rcx, [r14]
0x18003c504  add     rcx, 48h ; 'H'
0x18003c508  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003c50c  inc     rdx
0x18003c50f  cmp     [r9+rdx*2], r13w
0x18003c514  jnz     short loc_18003C50C
0x18003c516  jmp     loc_18003C448
0x18003c51b  mov     rax, [rdi+8]
0x18003c51f  lea     rcx, aNewvalue; "-NewValue"
0x18003c526  mov     rdx, [rax]
0x18003c529  mov     rdx, [rdx+rbx*8]
0x18003c52d  call    cs:__imp__o__wcsicmp
0x18003c533  test    eax, eax
0x18003c535  jnz     short loc_18003C565
0x18003c537  mov     rax, [rdi+10h]
0x18003c53b  cmp     esi, [rax]
0x18003c53d  jge     short loc_18003C565
0x18003c53f  mov     rax, [rdi+8]
0x18003c543  mov     rcx, [rax]
0x18003c546  mov     r9, [rcx+rbx*8+8]
0x18003c54b  mov     rcx, [r14]
0x18003c54e  add     rcx, 68h ; 'h'
0x18003c552  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003c556  inc     rdx
0x18003c559  cmp     [r9+rdx*2], r13w
0x18003c55e  jnz     short loc_18003C556
0x18003c560  jmp     loc_18003C448
0x18003c565  mov     rax, [rdi+8]
0x18003c569  lea     rcx, aConcatchar; "-ConcatChar"
0x18003c570  mov     rdx, [rax]
0x18003c573  mov     rdx, [rdx+rbx*8]
0x18003c577  call    cs:__imp__o__wcsicmp
0x18003c57d  test    eax, eax
0x18003c57f  jnz     short loc_18003C5BB
0x18003c581  mov     rax, [rdi+10h]
0x18003c585  cmp     esi, [rax]
0x18003c587  jge     short loc_18003C5BB
0x18003c589  mov     rax, [rdi+8]
0x18003c58d  mov     rcx, [rax]
0x18003c590  mov     rax, [rcx+rbx*8+8]
0x18003c595  mov     rcx, [r14]
0x18003c598  movzx   eax, word ptr [rax]
0x18003c59b  mov     [rcx+88h], ax
0x18003c5a2  mov     rax, r14
0x18003c5a5  mov     rbx, r14
0x18003c5a8  inc     esi
0x18003c5aa  mov     r14, rax
0x18003c5ad  mov     rax, [rdi+10h]
0x18003c5b1  cmp     esi, [rax]
0x18003c5b3  jl      loc_18003C3A4
0x18003c5b9  jmp     short loc_18003C5EF
0x18003c5bb  mov     rax, [rdi+8]
0x18003c5bf  lea     r9, aUnexpectedPara; "Unexpected parameter '%ls'."
0x18003c5c6  mov     r8d, 8Bh
0x18003c5cc  lea     rdx, aParsecommandli_0; "ParseCommandLineAndSetDefaults::<lambda"...
0x18003c5d3  mov     rcx, [rax]
0x18003c5d6  mov     rax, [rcx+rbx*8]
0x18003c5da  mov     ecx, 1
0x18003c5df  mov     [rsp+78h+var_58], rax
0x18003c5e4  call    AslLogCallPrintf
0x18003c5e9  jmp     short loc_18003C65E
0x18003c5eb  lea     rbx, [rdi+18h]
0x18003c5ef  mov     rax, [rbx]
0x18003c5f2  lea     rdx, [rax+8]
0x18003c5f6  cmp     [rdx+10h], r13
0x18003c5fa  jz      short loc_18003C631
0x18003c5fc  cmp     [rax+38h], r13
0x18003c600  jz      short loc_18003C631
0x18003c602  cmp     [rax+78h], r13
0x18003c606  jz      short loc_18003C631
0x18003c608  lea     rcx, [rax+48h]
0x18003c60c  cmp     [rcx+10h], r13
0x18003c610  jnz     short loc_18003C617
0x18003c612  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003c617  mov     rcx, [rbx]
0x18003c61a  cmp     r13w, [rcx+88h]
0x18003c622  jnz     short loc_18003C62D
0x18003c624  mov     word ptr [rcx+88h], 3Bh ; ';'
0x18003c62d  xor     eax, eax
0x18003c62f  jmp     short loc_18003C663
0x18003c631  lea     r9, aMissingParamet_0; "Missing parameters. -Key, -Value and -N"...
0x18003c638  mov     r8d, 97h
0x18003c63e  jmp     short loc_18003C64D
0x18003c640  lea     r9, aCommandlineIsN_0; "CommandLine is null/empty."
0x18003c647  mov     r8d, 52h ; 'R'
0x18003c64d  lea     rdx, aParsecommandli_0; "ParseCommandLineAndSetDefaults::<lambda"...
0x18003c654  mov     ecx, 1
0x18003c659  call    AslLogCallPrintf
0x18003c65e  mov     eax, 80070057h
0x18003c663  add     rsp, 48h
0x18003c667  pop     r14
0x18003c669  pop     r13
0x18003c66b  pop     rdi
0x18003c66c  pop     rsi
0x18003c66d  pop     rbp
0x18003c66e  pop     rbx
0x18003c66f  retn
```
