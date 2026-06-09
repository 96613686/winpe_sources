# CStowedExceptionPlugin::HashStackTrace(ulong *,ulong,void * *,utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *)

- ea: `0x140053158`
- end: `0x1400533a2`
- name: `?HashStackTrace@CStowedExceptionPlugin@@CAJPEAKKPEAPEAXPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@2@Z`
- size: `586`
- prototype: `__int64 __usercall@<rax>(unsigned int *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400533b0`

## callees

- `0x140002490`
- `0x140052e3c`
- `0x140053158`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400532a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400532a0`
- `bcrypt!BCryptFinishHash` at `0x140053341`
- `bcrypt!BCryptFinishHash` at `0x140053341`
- `bcrypt!BCryptDestroyHash` at `0x14005335c`
- `bcrypt!BCryptDestroyHash` at `0x14005335c`
- `bcrypt!BCryptCreateHash` at `0x1400531ce`
- `bcrypt!BCryptCreateHash` at `0x1400531ce`
- `bcrypt!BCryptHashData` at `0x1400532c6`
- `bcrypt!BCryptHashData` at `0x1400532fe`
- `bcrypt!BCryptHashData` at `0x1400532c6`
- `bcrypt!BCryptHashData` at `0x1400532fe`

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
            if ( !(unsigned int)_o__wcsnicmp(v16, off_1400642E0[v13], v17) )
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
0x140053158  mov     [rsp-38h+arg_8], rbx
0x14005315d  push    rbp
0x14005315e  push    rsi
0x14005315f  push    rdi
0x140053160  push    r12
0x140053162  push    r13
0x140053164  push    r14
0x140053166  push    r15
0x140053168  mov     rbp, rsp
0x14005316b  sub     rsp, 80h
0x140053172  mov     rax, cs:__security_cookie
0x140053179  xor     rax, rsp
0x14005317c  mov     [rbp+var_8], rax
0x140053180  xor     r12d, r12d
0x140053183  mov     [rbp+var_40], r9
0x140053187  xor     eax, eax
0x140053189  mov     [rbp+var_30], r8
0x14005318d  mov     rdi, r9
0x140053190  mov     [rbp+var_28], rcx
0x140053194  mov     rsi, r8
0x140053197  mov     [rcx], r12d
0x14005319a  mov     r13d, edx
0x14005319d  mov     [rsp+80h+dwFlags], r12d; dwFlags
0x1400531a2  mov     rbx, rcx
0x1400531a5  mov     [rsp+80h+cbSecret], r12d; cbSecret
0x1400531aa  xorps   xmm0, xmm0
0x1400531ad  mov     [rbp+var_10], rax
0x1400531b1  lea     ecx, [rax+21h]; hAlgorithm
0x1400531b4  mov     qword ptr [rbp+pbInput], r12
0x1400531b8  xor     r9d, r9d; cbHashObject
0x1400531bb  mov     [rsp+80h+pbSecret], r12; pbSecret
0x1400531c0  xor     r8d, r8d; pbHashObject
0x1400531c3  lea     rdx, [rbp+phHash]; phHash
0x1400531c7  movups  xmmword ptr [rbp+phHash], xmm0
0x1400531cb  mov     r15d, r12d
0x1400531ce  call    cs:__imp_BCryptCreateHash
0x1400531d5  nop     dword ptr [rax+rax+00h]
0x1400531da  test    eax, eax
0x1400531dc  jns     short loc_1400531E5
0x1400531de  lea     ecx, [r12+7]
0x1400531e3  int     29h; Win8: RtlFailFast(ecx)
0x1400531e5  mov     r14d, r12d
0x1400531e8  test    r13d, r13d
0x1400531eb  jz      loc_140053332
0x1400531f1  mov     r12, [rbp+arg_20]
0x1400531f5  mov     eax, r14d
0x1400531f8  mov     r8, [rsi+rax*8]
0x1400531fc  mov     rax, [rdi]
0x1400531ff  cmp     rax, [rdi+8]
0x140053203  jz      short loc_140053225
0x140053205  mov     rdx, [rax]
0x140053208  cmp     [rdx], r8
0x14005320b  ja      short loc_140053218
0x14005320d  mov     ecx, [rdx+8]
0x140053210  add     rcx, [rdx]
0x140053213  cmp     r8, rcx
0x140053216  jb      short loc_14005321E
0x140053218  add     rax, 8
0x14005321c  jmp     short loc_1400531FF
0x14005321e  mov     r15, rdx
0x140053221  xor     ebx, ebx
0x140053223  jmp     short loc_140053261
0x140053225  mov     rax, [r12]
0x140053229  cmp     rax, [r12+8]
0x14005322e  jz      short loc_140053252
0x140053230  mov     rdx, [rax]
0x140053233  cmp     [rdx], r8
0x140053236  ja      short loc_140053243
0x140053238  mov     ecx, [rdx+8]
0x14005323b  add     rcx, [rdx]
0x14005323e  cmp     r8, rcx
0x140053241  jb      short loc_140053249
0x140053243  add     rax, 8
0x140053247  jmp     short loc_140053229
0x140053249  xor     ebx, ebx
0x14005324b  mov     r15, rdx
0x14005324e  mov     eax, ebx
0x140053250  jmp     short loc_140053259
0x140053252  mov     eax, 80070490h
0x140053257  xor     ebx, ebx
0x140053259  test    eax, eax
0x14005325b  js      loc_14005331F
0x140053261  mov     rsi, [r15+18h]
0x140053265  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140053269  inc     rdi
0x14005326c  cmp     [rsi+rdi*2], bx
0x140053270  jnz     short loc_140053269
0x140053272  mov     rax, rdi
0x140053275  test    rdi, rdi
0x140053278  jz      short loc_14005328C
0x14005327a  cmp     word ptr [rsi+rax*2], 2Eh ; '.'
0x14005327f  jz      short loc_140053289
0x140053281  sub     rax, 1
0x140053285  jnz     short loc_14005327A
0x140053287  jmp     short loc_14005328C
0x140053289  mov     rdi, rax
0x14005328c  lea     rax, off_1400642E0; "ntdll"
0x140053293  movsxd  rdx, ebx
0x140053296  mov     r8, rdi
0x140053299  mov     rcx, rsi
0x14005329c  mov     rdx, [rax+rdx*8]
0x1400532a0  call    cs:__imp__o__wcsnicmp
0x1400532a7  nop     dword ptr [rax+rax+00h]
0x1400532ac  test    eax, eax
0x1400532ae  jz      short loc_140053317
0x1400532b0  inc     ebx
0x1400532b2  cmp     ebx, 0Ch
0x1400532b5  jb      short loc_14005328C
0x1400532b7  mov     rdx, [r15+18h]; pbInput
0x1400532bb  lea     r8d, [rdi+rdi]; cbInput
0x1400532bf  mov     rcx, [rbp+phHash]; hHash
0x1400532c3  xor     r9d, r9d; dwFlags
0x1400532c6  call    cs:__imp_BCryptHashData
0x1400532cd  nop     dword ptr [rax+rax+00h]
0x1400532d2  test    eax, eax
0x1400532d4  jns     short loc_1400532DD
0x1400532d6  mov     ecx, 7
0x1400532db  int     29h; Win8: RtlFailFast(ecx)
0x1400532dd  mov     rsi, [rbp+var_30]
0x1400532e1  lea     rdx, [rbp+pbInput]; pbInput
0x1400532e5  mov     rcx, [rbp+phHash]; hHash
0x1400532e9  xor     r9d, r9d; dwFlags
0x1400532ec  mov     eax, r14d
0x1400532ef  lea     r8d, [r9+8]; cbInput
0x1400532f3  mov     rax, [rsi+rax*8]
0x1400532f7  sub     rax, [r15]
0x1400532fa  mov     qword ptr [rbp+pbInput], rax
0x1400532fe  call    cs:__imp_BCryptHashData
0x140053305  nop     dword ptr [rax+rax+00h]
0x14005330a  test    eax, eax
0x14005330c  jns     short loc_14005331B
0x14005330e  mov     ecx, 7
0x140053313  int     29h; Win8: RtlFailFast(ecx)
0x140053315  jmp     short loc_14005331B
0x140053317  mov     rsi, [rbp+var_30]
0x14005331b  mov     rdi, [rbp+var_40]
0x14005331f  inc     r14d
0x140053322  cmp     r14d, r13d
0x140053325  jb      loc_1400531F5
0x14005332b  mov     rbx, [rbp+var_28]
0x14005332f  xor     r12d, r12d
0x140053332  mov     rcx, [rbp+phHash]; hHash
0x140053336  lea     rdx, [rbp+phHash+8]; pbOutput
0x14005333a  xor     r9d, r9d; dwFlags
0x14005333d  lea     r8d, [r9+10h]; cbOutput
0x140053341  call    cs:__imp_BCryptFinishHash
0x140053348  nop     dword ptr [rax+rax+00h]
0x14005334d  test    eax, eax
0x14005334f  jns     short loc_140053358
0x140053351  mov     ecx, 7
0x140053356  int     29h; Win8: RtlFailFast(ecx)
0x140053358  mov     rcx, [rbp+phHash]; hHash
0x14005335c  call    cs:__imp_BCryptDestroyHash
0x140053363  nop     dword ptr [rax+rax+00h]
0x140053368  lea     rdx, [rbp+phHash+8]; unsigned __int8 *
0x14005336c  mov     [rbp+phHash], r12
0x140053370  mov     rcx, rbx; unsigned int *
0x140053373  call    ?CompactMD5Digest@CStowedExceptionPlugin@@CAXPEAKPEAE@Z; CStowedExceptionPlugin::CompactMD5Digest(ulong *,uchar *)
0x140053378  xor     eax, eax
0x14005337a  mov     rcx, [rbp+var_8]
0x14005337e  xor     rcx, rsp; StackCookie
0x140053381  call    __security_check_cookie
0x140053386  mov     rbx, [rsp+80h+arg_8]
0x14005338e  add     rsp, 80h
0x140053395  pop     r15
0x140053397  pop     r14
0x140053399  pop     r13
0x14005339b  pop     r12
0x14005339d  pop     rdi
0x14005339e  pop     rsi
0x14005339f  pop     rbp
0x1400533a0  retn
```
