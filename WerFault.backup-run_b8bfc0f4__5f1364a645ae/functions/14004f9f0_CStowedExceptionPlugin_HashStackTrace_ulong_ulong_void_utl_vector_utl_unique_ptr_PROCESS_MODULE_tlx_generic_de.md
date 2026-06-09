# CStowedExceptionPlugin::HashStackTrace(ulong *,ulong,void * *,utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *)

- ea: `0x14004f9f0`
- end: `0x14004fc15`
- name: `?HashStackTrace@CStowedExceptionPlugin@@CAJPEAKKPEAPEAXPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@2@Z`
- size: `549`
- prototype: `__int64 __usercall@<rax>(unsigned int *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004fc20`

## callees

- `0x140002470`
- `0x14004f720`
- `0x14004f9f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14004fb32`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14004fb32`
- `bcrypt!BCryptFinishHash` at `0x14004fbc1`
- `bcrypt!BCryptFinishHash` at `0x14004fbc1`
- `bcrypt!BCryptDestroyHash` at `0x14004fbd6`
- `bcrypt!BCryptDestroyHash` at `0x14004fbd6`
- `bcrypt!BCryptCreateHash` at `0x14004fa66`
- `bcrypt!BCryptCreateHash` at `0x14004fa66`
- `bcrypt!BCryptHashData` at `0x14004fb52`
- `bcrypt!BCryptHashData` at `0x14004fb84`
- `bcrypt!BCryptHashData` at `0x14004fb52`
- `bcrypt!BCryptHashData` at `0x14004fb84`

## pseudocode

```c
__int64 __fastcall CStowedExceptionPlugin::HashStackTrace(
        unsigned int *a1,
        unsigned int a2,
        __int64 a3,
        __int64 *a4,
        __int64 *a5)
{
  __int64 *v5; // rdi
  __int64 v6; // rsi
  unsigned int *v8; // rbx
  _QWORD *v9; // r15
  unsigned int v10; // r14d
  unsigned __int64 v11; // r8
  __int64 i; // rax
  unsigned int v13; // ebx
  __int64 k; // rax
  int v15; // eax
  __int64 v16; // rsi
  __int64 v17; // rdi
  __int64 j; // rax
  UCHAR pbInput[8]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v22; // [rsp+50h] [rbp-30h]
  unsigned int *v23; // [rsp+58h] [rbp-28h]
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v25; // [rsp+70h] [rbp-10h]

  v22 = a3;
  v5 = a4;
  v23 = a1;
  v6 = a3;
  *a1 = 0;
  v8 = a1;
  v25 = 0;
  *(_QWORD *)pbInput = 0;
  *(_OWORD *)phHash = 0;
  v9 = 0;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  v10 = 0;
  if ( a2 )
  {
    do
    {
      v11 = *(_QWORD *)(v6 + 8LL * v10);
      for ( i = *v5; i != v5[1]; i += 8 )
      {
        if ( **(_QWORD **)i <= v11 && v11 < **(_QWORD **)i + (unsigned __int64)*(unsigned int *)(*(_QWORD *)i + 8LL) )
        {
          v9 = *(_QWORD **)i;
          v13 = 0;
LABEL_18:
          v16 = v9[3];
          v17 = -1;
          do
            ++v17;
          while ( *(_WORD *)(v16 + 2 * v17) );
          for ( j = v17; j; --j )
          {
            if ( *(_WORD *)(v16 + 2 * j) == 46 )
            {
              v17 = j;
              goto LABEL_25;
            }
          }
          do
          {
LABEL_25:
            if ( !(unsigned int)_o__wcsnicmp(v16, off_1400602E0[v13], v17) )
            {
              v6 = v22;
              goto LABEL_32;
            }
            ++v13;
          }
          while ( v13 < 0xC );
          if ( BCryptHashData(phHash[0], (PUCHAR)v9[3], 2 * v17, 0) < 0 )
            __fastfail(7u);
          v6 = v22;
          *(_QWORD *)pbInput = *(_QWORD *)(v22 + 8LL * v10) - *v9;
          if ( BCryptHashData(phHash[0], pbInput, 8u, 0) < 0 )
            __fastfail(7u);
LABEL_32:
          v5 = a4;
          goto LABEL_33;
        }
      }
      for ( k = *a5; k != a5[1]; k += 8 )
      {
        if ( **(_QWORD **)k <= v11 && v11 < **(_QWORD **)k + (unsigned __int64)*(unsigned int *)(*(_QWORD *)k + 8LL) )
        {
          v13 = 0;
          v9 = *(_QWORD **)k;
          v15 = 0;
          goto LABEL_17;
        }
      }
      v15 = -2147023728;
      v13 = 0;
LABEL_17:
      if ( v15 >= 0 )
        goto LABEL_18;
LABEL_33:
      ++v10;
    }
    while ( v10 < a2 );
    v8 = v23;
  }
  if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
    __fastfail(7u);
  BCryptDestroyHash(phHash[0]);
  phHash[0] = 0;
  CStowedExceptionPlugin::CompactMD5Digest(v8, (unsigned __int8 *)&phHash[1]);
  return 0;
}

```

## disassembly

```asm
0x14004f9f0  mov     [rsp-38h+arg_8], rbx
0x14004f9f5  push    rbp
0x14004f9f6  push    rsi
0x14004f9f7  push    rdi
0x14004f9f8  push    r12
0x14004f9fa  push    r13
0x14004f9fc  push    r14
0x14004f9fe  push    r15
0x14004fa00  mov     rbp, rsp
0x14004fa03  sub     rsp, 80h
0x14004fa0a  mov     rax, cs:__security_cookie
0x14004fa11  xor     rax, rsp
0x14004fa14  mov     [rbp+var_8], rax
0x14004fa18  xor     r12d, r12d
0x14004fa1b  mov     [rbp+var_40], r9
0x14004fa1f  xor     eax, eax
0x14004fa21  mov     [rbp+var_30], r8
0x14004fa25  mov     rdi, r9
0x14004fa28  mov     [rbp+var_28], rcx
0x14004fa2c  mov     rsi, r8
0x14004fa2f  mov     [rcx], r12d
0x14004fa32  mov     r13d, edx
0x14004fa35  mov     [rsp+80h+dwFlags], r12d; dwFlags
0x14004fa3a  mov     rbx, rcx
0x14004fa3d  mov     [rsp+80h+cbSecret], r12d; cbSecret
0x14004fa42  xorps   xmm0, xmm0
0x14004fa45  mov     [rbp+var_10], rax
0x14004fa49  lea     ecx, [rax+21h]; hAlgorithm
0x14004fa4c  mov     qword ptr [rbp+pbInput], r12
0x14004fa50  xor     r9d, r9d; cbHashObject
0x14004fa53  mov     [rsp+80h+pbSecret], r12; pbSecret
0x14004fa58  xor     r8d, r8d; pbHashObject
0x14004fa5b  lea     rdx, [rbp+phHash]; phHash
0x14004fa5f  movups  xmmword ptr [rbp+phHash], xmm0
0x14004fa63  mov     r15d, r12d
0x14004fa66  call    cs:__imp_BCryptCreateHash
0x14004fa6c  test    eax, eax
0x14004fa6e  jns     short loc_14004FA77
0x14004fa70  lea     ecx, [r12+7]
0x14004fa75  int     29h; Win8: RtlFailFast(ecx)
0x14004fa77  mov     r14d, r12d
0x14004fa7a  test    r13d, r13d
0x14004fa7d  jz      loc_14004FBB2
0x14004fa83  mov     r12, [rbp+arg_20]
0x14004fa87  mov     eax, r14d
0x14004fa8a  mov     r8, [rsi+rax*8]
0x14004fa8e  mov     rax, [rdi]
0x14004fa91  cmp     rax, [rdi+8]
0x14004fa95  jz      short loc_14004FAB7
0x14004fa97  mov     rdx, [rax]
0x14004fa9a  cmp     [rdx], r8
0x14004fa9d  ja      short loc_14004FAAA
0x14004fa9f  mov     ecx, [rdx+8]
0x14004faa2  add     rcx, [rdx]
0x14004faa5  cmp     r8, rcx
0x14004faa8  jb      short loc_14004FAB0
0x14004faaa  add     rax, 8
0x14004faae  jmp     short loc_14004FA91
0x14004fab0  mov     r15, rdx
0x14004fab3  xor     ebx, ebx
0x14004fab5  jmp     short loc_14004FAF3
0x14004fab7  mov     rax, [r12]
0x14004fabb  cmp     rax, [r12+8]
0x14004fac0  jz      short loc_14004FAE4
0x14004fac2  mov     rdx, [rax]
0x14004fac5  cmp     [rdx], r8
0x14004fac8  ja      short loc_14004FAD5
0x14004faca  mov     ecx, [rdx+8]
0x14004facd  add     rcx, [rdx]
0x14004fad0  cmp     r8, rcx
0x14004fad3  jb      short loc_14004FADB
0x14004fad5  add     rax, 8
0x14004fad9  jmp     short loc_14004FABB
0x14004fadb  xor     ebx, ebx
0x14004fadd  mov     r15, rdx
0x14004fae0  mov     eax, ebx
0x14004fae2  jmp     short loc_14004FAEB
0x14004fae4  mov     eax, 80070490h
0x14004fae9  xor     ebx, ebx
0x14004faeb  test    eax, eax
0x14004faed  js      loc_14004FB9F
0x14004faf3  mov     rsi, [r15+18h]
0x14004faf7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14004fafb  inc     rdi
0x14004fafe  cmp     [rsi+rdi*2], bx
0x14004fb02  jnz     short loc_14004FAFB
0x14004fb04  mov     rax, rdi
0x14004fb07  test    rdi, rdi
0x14004fb0a  jz      short loc_14004FB1E
0x14004fb0c  cmp     word ptr [rsi+rax*2], 2Eh ; '.'
0x14004fb11  jz      short loc_14004FB1B
0x14004fb13  sub     rax, 1
0x14004fb17  jnz     short loc_14004FB0C
0x14004fb19  jmp     short loc_14004FB1E
0x14004fb1b  mov     rdi, rax
0x14004fb1e  lea     rax, off_1400602E0; "ntdll"
0x14004fb25  movsxd  rdx, ebx
0x14004fb28  mov     r8, rdi
0x14004fb2b  mov     rcx, rsi
0x14004fb2e  mov     rdx, [rax+rdx*8]
0x14004fb32  call    cs:__imp__o__wcsnicmp
0x14004fb38  test    eax, eax
0x14004fb3a  jz      short loc_14004FB97
0x14004fb3c  inc     ebx
0x14004fb3e  cmp     ebx, 0Ch
0x14004fb41  jb      short loc_14004FB1E
0x14004fb43  mov     rdx, [r15+18h]; pbInput
0x14004fb47  lea     r8d, [rdi+rdi]; cbInput
0x14004fb4b  mov     rcx, [rbp+phHash]; hHash
0x14004fb4f  xor     r9d, r9d; dwFlags
0x14004fb52  call    cs:__imp_BCryptHashData
0x14004fb58  test    eax, eax
0x14004fb5a  jns     short loc_14004FB63
0x14004fb5c  mov     ecx, 7
0x14004fb61  int     29h; Win8: RtlFailFast(ecx)
0x14004fb63  mov     rsi, [rbp+var_30]
0x14004fb67  lea     rdx, [rbp+pbInput]; pbInput
0x14004fb6b  mov     rcx, [rbp+phHash]; hHash
0x14004fb6f  xor     r9d, r9d; dwFlags
0x14004fb72  mov     eax, r14d
0x14004fb75  lea     r8d, [r9+8]; cbInput
0x14004fb79  mov     rax, [rsi+rax*8]
0x14004fb7d  sub     rax, [r15]
0x14004fb80  mov     qword ptr [rbp+pbInput], rax
0x14004fb84  call    cs:__imp_BCryptHashData
0x14004fb8a  test    eax, eax
0x14004fb8c  jns     short loc_14004FB9B
0x14004fb8e  mov     ecx, 7
0x14004fb93  int     29h; Win8: RtlFailFast(ecx)
0x14004fb95  jmp     short loc_14004FB9B
0x14004fb97  mov     rsi, [rbp+var_30]
0x14004fb9b  mov     rdi, [rbp+var_40]
0x14004fb9f  inc     r14d
0x14004fba2  cmp     r14d, r13d
0x14004fba5  jb      loc_14004FA87
0x14004fbab  mov     rbx, [rbp+var_28]
0x14004fbaf  xor     r12d, r12d
0x14004fbb2  mov     rcx, [rbp+phHash]; hHash
0x14004fbb6  lea     rdx, [rbp+phHash+8]; pbOutput
0x14004fbba  xor     r9d, r9d; dwFlags
0x14004fbbd  lea     r8d, [r9+10h]; cbOutput
0x14004fbc1  call    cs:__imp_BCryptFinishHash
0x14004fbc7  test    eax, eax
0x14004fbc9  jns     short loc_14004FBD2
0x14004fbcb  mov     ecx, 7
0x14004fbd0  int     29h; Win8: RtlFailFast(ecx)
0x14004fbd2  mov     rcx, [rbp+phHash]; hHash
0x14004fbd6  call    cs:__imp_BCryptDestroyHash
0x14004fbdc  lea     rdx, [rbp+phHash+8]; unsigned __int8 *
0x14004fbe0  mov     [rbp+phHash], r12
0x14004fbe4  mov     rcx, rbx; unsigned int *
0x14004fbe7  call    ?CompactMD5Digest@CStowedExceptionPlugin@@CAXPEAKPEAE@Z; CStowedExceptionPlugin::CompactMD5Digest(ulong *,uchar *)
0x14004fbec  xor     eax, eax
0x14004fbee  mov     rcx, [rbp+var_8]
0x14004fbf2  xor     rcx, rsp; StackCookie
0x14004fbf5  call    __security_check_cookie
0x14004fbfa  mov     rbx, [rsp+80h+arg_8]
0x14004fc02  add     rsp, 80h
0x14004fc09  pop     r15
0x14004fc0b  pop     r14
0x14004fc0d  pop     r13
0x14004fc0f  pop     r12
0x14004fc11  pop     rdi
0x14004fc12  pop     rsi
0x14004fc13  pop     rbp
0x14004fc14  retn
```
