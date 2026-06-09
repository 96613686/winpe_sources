# CConfigSource::IsDuplicateUIMatch(IMVXMLComparison *,std::vector<std::shared_ptr<CConfigSet>,std::allocator<std::shared_ptr<CConfigSet>>> &,bool *)

- ea: `0x18000db4c`
- end: `0x18000dd28`
- name: `?IsDuplicateUIMatch@CConfigSource@@CAJPEAVIMVXMLComparison@@AEAV?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@PEA_N@Z`
- size: `476`
- prototype: `__int64 __fastcall(__int64, __int64 **, _BYTE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e184`

## callees

- `0x180009068`
- `0x18000a148`
- `0x18000db4c`
- `0x180012010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000dbd1`
- `msvcrt!_wcsicmp` at `0x18000dc57`
- `msvcrt!_wcsicmp` at `0x18000dbd1`
- `msvcrt!_wcsicmp` at `0x18000dc57`

## pseudocode

```c
__int64 __fastcall CConfigSource::IsDuplicateUIMatch(__int64 a1, __int64 **a2, _BYTE *a3)
{
  int v5; // r12d
  __int64 v6; // r14
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 *i; // rdi
  __int64 v10; // r14
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int16 *v14; // rax
  int v15; // r8d
  int v16; // edx
  unsigned int v17; // ebx
  __int64 v18; // rcx
  __int64 *v19; // r14
  __int64 *j; // rbx
  wchar_t *String1; // [rsp+20h] [rbp-10h] BYREF
  __int64 v23; // [rsp+28h] [rbp-8h] BYREF
  unsigned int v24; // [rsp+70h] [rbp+40h] BYREF
  _BYTE *v25; // [rsp+80h] [rbp+50h]
  unsigned __int16 *v26; // [rsp+88h] [rbp+58h] BYREF

  v25 = a3;
  v5 = 0;
  v24 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 24LL))(a1, &v24);
  v26 = 0;
  v7 = 0;
  if ( v6 )
  {
    while ( v7 < v24 )
    {
      v8 = *(_QWORD *)(v6 + 8LL * v7);
      if ( v8 )
      {
        String1 = 0;
        v5 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v8 + 40LL))(v8, &String1);
        if ( v5 >= 0 && !_wcsicmp(String1, L"uiname") )
        {
          _mm_lfence();
          v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(**(_QWORD **)(v6 + 8LL * v7) + 48LL))(
                 *(_QWORD *)(v6 + 8LL * v7),
                 &v26);
          break;
        }
      }
      ++v7;
    }
    if ( v26 )
    {
      for ( i = *a2; i != a2[1]; i += 2 )
      {
        v10 = *i;
        v23 = 0;
        v11 = 0;
        if ( *(_DWORD *)(v10 + 32) )
        {
          while ( 1 )
          {
            v12 = *(_QWORD *)(*(_QWORD *)(v10 + 24) + 8LL * v11);
            if ( v12 )
            {
              String1 = 0;
              if ( (*(int (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v12 + 40LL))(v12, &String1) >= 0
                && !_wcsicmp(String1, L"uiname") )
              {
                break;
              }
            }
            if ( ++v11 >= *(_DWORD *)(v10 + 32) )
              goto LABEL_18;
          }
          v13 = *(_QWORD *)(*(_QWORD *)(v10 + 24) + 8LL * v11);
          (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 48LL))(v13, &v23);
        }
LABEL_18:
        if ( v23 )
        {
          v14 = v26;
          do
          {
            v15 = *(unsigned __int16 *)((char *)v14 + v23 - (_QWORD)v26);
            v16 = *v14 - v15;
            if ( v16 )
              break;
            ++v14;
          }
          while ( v15 );
          if ( !v16 )
          {
            v17 = *(_DWORD *)(*i + 112);
            if ( v17 >= (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 72LL))(a1) )
            {
              *v25 = 0;
            }
            else
            {
              v19 = a2[1];
              for ( j = i + 2; j != v19; j += 2 )
              {
                std::shared_ptr<CConfigSet>::operator=(i, j);
                i += 2;
              }
              std::vector<std::shared_ptr<CConfigSet>>::_Destroy(v18, (__int64)(a2[1] - 2), (__int64)a2[1]);
              a2[1] -= 2;
            }
            return (unsigned int)v5;
          }
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000db4c  mov     [rsp-38h+arg_8], rbx
0x18000db51  mov     [rsp-38h+arg_10], r8
0x18000db56  push    rbp
0x18000db57  push    rsi
0x18000db58  push    rdi
0x18000db59  push    r12
0x18000db5b  push    r13
0x18000db5d  push    r14
0x18000db5f  push    r15
0x18000db61  mov     rbp, rsp
0x18000db64  sub     rsp, 30h
0x18000db68  mov     rsi, rdx
0x18000db6b  mov     r13, rcx
0x18000db6e  xor     r15d, r15d
0x18000db71  mov     r12d, r15d
0x18000db74  mov     [rbp+arg_0], r15d
0x18000db78  mov     rax, [rcx]
0x18000db7b  lea     rdx, [rbp+arg_0]
0x18000db7f  mov     rax, [rax+18h]
0x18000db83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db88  mov     r14, rax
0x18000db8b  mov     [rbp+arg_18], r15
0x18000db8f  mov     ebx, r15d
0x18000db92  test    rax, rax
0x18000db95  jz      loc_18000DD10
0x18000db9b  cmp     ebx, [rbp+arg_0]
0x18000db9e  jnb     short loc_18000DBF9
0x18000dba0  mov     edi, ebx
0x18000dba2  mov     rcx, [r14+rdi*8]
0x18000dba6  test    rcx, rcx
0x18000dba9  jz      short loc_18000DBDB
0x18000dbab  mov     [rbp+String1], r15
0x18000dbaf  mov     rax, [rcx]
0x18000dbb2  lea     rdx, [rbp+String1]
0x18000dbb6  mov     rax, [rax+28h]
0x18000dbba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbbf  mov     r12d, eax
0x18000dbc2  test    eax, eax
0x18000dbc4  js      short loc_18000DBDB
0x18000dbc6  lea     rdx, ?gc_wszUIName@@3QBGB; "uiname"
0x18000dbcd  mov     rcx, [rbp+String1]; String1
0x18000dbd1  call    cs:__imp__wcsicmp
0x18000dbd7  test    eax, eax
0x18000dbd9  jz      short loc_18000DBDF
0x18000dbdb  inc     ebx
0x18000dbdd  jmp     short loc_18000DB9B
0x18000dbdf  lfence
0x18000dbe2  mov     rcx, [r14+rdi*8]
0x18000dbe6  mov     rax, [rcx]
0x18000dbe9  lea     rdx, [rbp+arg_18]
0x18000dbed  mov     rax, [rax+30h]
0x18000dbf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbf6  mov     r12d, eax
0x18000dbf9  cmp     [rbp+arg_18], r15
0x18000dbfd  jz      loc_18000DD10
0x18000dc03  mov     rdi, [rsi]
0x18000dc06  cmp     rdi, [rsi+8]
0x18000dc0a  jz      loc_18000DD10
0x18000dc10  mov     r14, [rdi]
0x18000dc13  mov     [rbp+var_8], r15
0x18000dc17  mov     ebx, r15d
0x18000dc1a  cmp     [r14+20h], r15d
0x18000dc1e  jbe     short loc_18000DC86
0x18000dc20  mov     r15d, ebx
0x18000dc23  mov     rax, [r14+18h]
0x18000dc27  mov     rcx, [rax+r15*8]
0x18000dc2b  test    rcx, rcx
0x18000dc2e  jz      short loc_18000DC61
0x18000dc30  mov     [rbp+String1], 0
0x18000dc38  mov     rax, [rcx]
0x18000dc3b  lea     rdx, [rbp+String1]
0x18000dc3f  mov     rax, [rax+28h]
0x18000dc43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc48  test    eax, eax
0x18000dc4a  js      short loc_18000DC61
0x18000dc4c  lea     rdx, ?gc_wszUIName@@3QBGB; "uiname"
0x18000dc53  mov     rcx, [rbp+String1]; String1
0x18000dc57  call    cs:__imp__wcsicmp
0x18000dc5d  test    eax, eax
0x18000dc5f  jz      short loc_18000DC6B
0x18000dc61  inc     ebx
0x18000dc63  cmp     ebx, [r14+20h]
0x18000dc67  jb      short loc_18000DC20
0x18000dc69  jmp     short loc_18000DC83
0x18000dc6b  mov     rax, [r14+18h]
0x18000dc6f  mov     rcx, [rax+r15*8]
0x18000dc73  mov     rax, [rcx]
0x18000dc76  lea     rdx, [rbp+var_8]
0x18000dc7a  mov     rax, [rax+30h]
0x18000dc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc83  xor     r15d, r15d
0x18000dc86  mov     rcx, [rbp+var_8]
0x18000dc8a  test    rcx, rcx
0x18000dc8d  jz      short loc_18000DCB0
0x18000dc8f  mov     rax, [rbp+arg_18]
0x18000dc93  sub     rcx, rax
0x18000dc96  movzx   edx, word ptr [rax]
0x18000dc99  movzx   r8d, word ptr [rax+rcx]
0x18000dc9e  sub     edx, r8d
0x18000dca1  jnz     short loc_18000DCAC
0x18000dca3  add     rax, 2
0x18000dca7  test    r8d, r8d
0x18000dcaa  jnz     short loc_18000DC96
0x18000dcac  test    edx, edx
0x18000dcae  jz      short loc_18000DCB9
0x18000dcb0  add     rdi, 10h
0x18000dcb4  jmp     loc_18000DC06
0x18000dcb9  mov     rax, [rdi]
0x18000dcbc  mov     ebx, [rax+70h]
0x18000dcbf  mov     rax, [r13+0]
0x18000dcc3  mov     rcx, r13
0x18000dcc6  mov     rax, [rax+48h]
0x18000dcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dccf  cmp     ebx, eax
0x18000dcd1  jnb     short loc_18000DD09
0x18000dcd3  mov     r14, [rsi+8]
0x18000dcd7  lea     rbx, [rdi+10h]
0x18000dcdb  jmp     short loc_18000DCF0
0x18000dcdd  mov     rdx, rbx
0x18000dce0  mov     rcx, rdi
0x18000dce3  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000dce8  add     rdi, 10h
0x18000dcec  add     rbx, 10h
0x18000dcf0  cmp     rbx, r14
0x18000dcf3  jnz     short loc_18000DCDD
0x18000dcf5  mov     r8, [rsi+8]
0x18000dcf9  lea     rdx, [r8-10h]
0x18000dcfd  call    ?_Destroy@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@IEAAXPEAV?$shared_ptr@VCConfigSet@@@2@0@Z; std::vector<std::shared_ptr<CConfigSet>>::_Destroy(std::shared_ptr<CConfigSet> *,std::shared_ptr<CConfigSet> *)
0x18000dd02  add     qword ptr [rsi+8], 0FFFFFFFFFFFFFFF0h
0x18000dd07  jmp     short loc_18000DD10
0x18000dd09  mov     rax, [rbp+arg_10]
0x18000dd0d  mov     [rax], r15b
0x18000dd10  mov     eax, r12d
0x18000dd13  mov     rbx, [rsp+30h+arg_8]
0x18000dd18  add     rsp, 30h
0x18000dd1c  pop     r15
0x18000dd1e  pop     r14
0x18000dd20  pop     r13
0x18000dd22  pop     r12
0x18000dd24  pop     rdi
0x18000dd25  pop     rsi
0x18000dd26  pop     rbp
0x18000dd27  retn
```
