# StreamSubStringMatchW

- ea: `0x18000f6f0`
- end: `0x18000f8d8`
- name: `StreamSubStringMatchW`
- size: `488`
- prototype: `__int64 __fastcall(__int64 *, const WCHAR *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002698`
- `0x18000f1f0`
- `0x18000f6f0`
- `0x180012fc0`
- `0x180013050`
- `0x180014010`

## import_xrefs

- `KERNEL32!RtlMoveMemory` at `0x18000f888`
- `KERNEL32!RtlMoveMemory` at `0x18000f888`
- `SHLWAPI!StrStrIW` at `0x18000f84d`
- `SHLWAPI!StrStrIW` at `0x18000f84d`
- `SHLWAPI!__imp_IStream_Reset` at `0x18000f77e`
- `SHLWAPI!__imp_IStream_Reset` at `0x18000f77e`

## pseudocode

```c
__int64 __fastcall StreamSubStringMatchW(__int64 *a1, const WCHAR *a2)
{
  unsigned int v4; // r14d
  __int64 v5; // rdi
  int v6; // esi
  WCHAR *v7; // rbx
  unsigned __int64 v8; // r15
  __int64 v9; // r8
  WCHAR *v10; // r9
  int v11; // r10d
  __int64 v12; // rsi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // r14
  __int64 v17; // rax
  int v19; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v20; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszFirst[4096]; // [rsp+40h] [rbp-C0h] BYREF

  v19 = 0;
  v4 = 0;
  v20 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v5 = -1;
      do
        ++v5;
      while ( a2[v5] );
      v6 = 4095;
      if ( (unsigned int)v5 < 0xFFF && (int)HrGetStreamSize(a1, &v19) >= 0 && IStream_Reset((IStream *)a1) >= 0 )
      {
        v7 = pszFirst;
        v8 = (unsigned __int64)v19 >> 1;
        while ( (_DWORD)v8
             && !(*(unsigned int (__fastcall **)(__int64 *, WCHAR *, _QWORD, unsigned int *))(*a1 + 24))(
                   a1,
                   v7,
                   (unsigned int)(2 * v6),
                   &v20)
             && v20 )
        {
          v10 = pszFirst;
          v11 = 0;
          v12 = v20 >> 1;
          v13 = 0;
          v14 = ((__int64)v7 + 2 * v12 - (__int64)pszFirst) >> 1;
          if ( (_DWORD)v14 )
          {
            do
            {
              v9 = pszFirst[v13];
              if ( (_WORD)v9 == 10 || (_WORD)v9 == 13 )
                ++v11;
              else
                *v10++ = v9;
              v13 = (unsigned int)(v13 + 1);
            }
            while ( (unsigned int)v13 < (unsigned int)v14 );
          }
          v15 = (unsigned int)(v14 - v11);
          v16 = (unsigned int)v15;
          v17 = v15;
          if ( (unsigned __int64)(2 * v15) >= 0x2000 )
            _report_rangecheckfailure(v15, v13, v9, v10);
          v7 = &pszFirst[v17];
          pszFirst[v17] = 0;
          if ( StrStrIW(pszFirst, a2) )
            return 1;
          LODWORD(v8) = v8 - v12;
          if ( !(_DWORD)v8 )
            break;
          if ( (unsigned int)v16 >= (unsigned int)v5 )
          {
            v6 = 4095 - v5;
            RtlMoveMemory(pszFirst, &pszFirst[v16 - (unsigned int)v5], (unsigned int)(2 * v5));
            v7 = &pszFirst[(unsigned int)v5];
          }
          else
          {
            v6 = 4095 - v16;
          }
        }
        return 0;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000f6f0  mov     [rsp-8+arg_10], rbx
0x18000f6f5  push    rbp
0x18000f6f6  push    rsi
0x18000f6f7  push    rdi
0x18000f6f8  push    r12
0x18000f6fa  push    r13
0x18000f6fc  push    r14
0x18000f6fe  push    r15
0x18000f700  lea     rbp, [rsp-1F50h]
0x18000f708  mov     eax, 2050h
0x18000f70d  call    _alloca_probe
0x18000f712  sub     rsp, rax
0x18000f715  mov     rax, cs:__security_cookie
0x18000f71c  xor     rax, rsp
0x18000f71f  mov     [rbp+1F80h+var_40], rax
0x18000f726  xor     ebx, ebx
0x18000f728  mov     r13, rdx
0x18000f72b  mov     [rsp+2080h+var_2050], ebx
0x18000f72f  mov     r12, rcx
0x18000f732  mov     [rsp+2080h+var_204C], ebx
0x18000f736  mov     r14d, ebx
0x18000f739  mov     [rsp+2080h+var_2048], ebx
0x18000f73d  test    rcx, rcx
0x18000f740  jz      loc_18000F8AB
0x18000f746  test    rdx, rdx
0x18000f749  jz      loc_18000F8AB
0x18000f74f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000f753  inc     rdi
0x18000f756  cmp     [rdx+rdi*2], bx
0x18000f75a  jnz     short loc_18000F753
0x18000f75c  mov     esi, 0FFFh
0x18000f761  cmp     edi, esi
0x18000f763  jnb     loc_18000F8AB
0x18000f769  lea     rdx, [rsp+2080h+var_204C]
0x18000f76e  call    HrGetStreamSize
0x18000f773  test    eax, eax
0x18000f775  js      loc_18000F8AB
0x18000f77b  mov     rcx, r12; pstm
0x18000f77e  call    cs:__imp_IStream_Reset
0x18000f784  test    eax, eax
0x18000f786  js      loc_18000F8AB
0x18000f78c  movsxd  r15, [rsp+2080h+var_204C]
0x18000f791  lea     rbx, [rsp+2080h+pszFirst]
0x18000f796  shr     r15, 1
0x18000f799  test    r15d, r15d
0x18000f79c  jz      loc_18000F8A6
0x18000f7a2  mov     rax, [r12]
0x18000f7a6  lea     r8d, [rsi+rsi]
0x18000f7aa  lea     r9, [rsp+2080h+var_2048]
0x18000f7af  mov     rdx, rbx
0x18000f7b2  mov     rcx, r12
0x18000f7b5  mov     rax, [rax+18h]
0x18000f7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7be  test    eax, eax
0x18000f7c0  jnz     loc_18000F8A6
0x18000f7c6  mov     eax, [rsp+2080h+var_2048]
0x18000f7ca  test    eax, eax
0x18000f7cc  jz      loc_18000F8A6
0x18000f7d2  shr     eax, 1
0x18000f7d4  lea     r9, [rsp+2080h+pszFirst]
0x18000f7d9  mov     ecx, eax
0x18000f7db  xor     r10d, r10d
0x18000f7de  add     rcx, rcx
0x18000f7e1  mov     esi, eax
0x18000f7e3  lea     rax, [rsp+2080h+pszFirst]
0x18000f7e8  xor     edx, edx
0x18000f7ea  sub     rcx, rax
0x18000f7ed  add     rcx, rbx
0x18000f7f0  sar     rcx, 1
0x18000f7f3  test    ecx, ecx
0x18000f7f5  jz      short loc_18000F826
0x18000f7f7  movzx   r8d, [rsp+rdx*2+2080h+pszFirst]
0x18000f7fd  mov     eax, 0Ah
0x18000f802  cmp     ax, r8w
0x18000f806  jz      short loc_18000F81D
0x18000f808  mov     eax, 0Dh
0x18000f80d  cmp     ax, r8w
0x18000f811  jz      short loc_18000F81D
0x18000f813  mov     [r9], r8w
0x18000f817  add     r9, 2
0x18000f81b  jmp     short loc_18000F820
0x18000f81d  inc     r10d
0x18000f820  inc     edx
0x18000f822  cmp     edx, ecx
0x18000f824  jb      short loc_18000F7F7
0x18000f826  sub     ecx, r10d
0x18000f829  mov     r14d, ecx
0x18000f82c  lea     rax, [rcx+rcx]
0x18000f830  cmp     rax, 2000h
0x18000f836  jnb     short loc_18000F8A0
0x18000f838  lea     rbx, [rsp+2080h+pszFirst]
0x18000f83d  mov     rdx, r13; pszSrch
0x18000f840  add     rbx, rax
0x18000f843  lea     rcx, [rsp+2080h+pszFirst]; pszFirst
0x18000f848  xor     eax, eax
0x18000f84a  mov     [rbx], ax
0x18000f84d  call    cs:__imp_StrStrIW
0x18000f853  test    rax, rax
0x18000f856  jnz     short loc_18000F898
0x18000f858  sub     r15d, esi
0x18000f85b  jz      short loc_18000F8A6
0x18000f85d  mov     esi, 0FFFh
0x18000f862  cmp     r14d, edi
0x18000f865  jnb     short loc_18000F86F
0x18000f867  sub     esi, r14d
0x18000f86a  jmp     loc_18000F799
0x18000f86f  mov     ebx, edi
0x18000f871  lea     rdx, [rsp+2080h+pszFirst]
0x18000f876  sub     r14, rbx
0x18000f879  lea     r8d, [rdi+rdi]
0x18000f87d  sub     esi, edi
0x18000f87f  lea     rcx, [rsp+2080h+pszFirst]
0x18000f884  lea     rdx, [rdx+r14*2]
0x18000f888  call    cs:__imp_RtlMoveMemory
0x18000f88e  lea     rbx, [rsp+rbx*2+2080h+pszFirst]
0x18000f893  jmp     loc_18000F799
0x18000f898  mov     r14d, 1
0x18000f89e  jmp     short loc_18000F8AB
0x18000f8a0  call    __report_rangecheckfailure
0x18000f8a6  mov     r14d, [rsp+2080h+var_2050]
0x18000f8ab  mov     eax, r14d
0x18000f8ae  mov     rcx, [rbp+1F80h+var_40]
0x18000f8b5  xor     rcx, rsp; StackCookie
0x18000f8b8  call    __security_check_cookie
0x18000f8bd  mov     rbx, [rsp+2080h+arg_10]
0x18000f8c5  add     rsp, 2050h
0x18000f8cc  pop     r15
0x18000f8ce  pop     r14
0x18000f8d0  pop     r13
0x18000f8d2  pop     r12
0x18000f8d4  pop     rdi
0x18000f8d5  pop     rsi
0x18000f8d6  pop     rbp
0x18000f8d7  retn
```
