# CAppContainer::ChooseBestFit(tagPACKAGEDISPINFO *,uint *,ulong,ulong *)

- ea: `0x18001c6b0`
- end: `0x18001c846`
- name: `?ChooseBestFit@CAppContainer@@QEAAJPEAUtagPACKAGEDISPINFO@@PEAIKPEAK@Z`
- size: `406`
- prototype: `__int64 __fastcall(CAppContainer *this, const FILETIME *, unsigned int *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d240`

## callees

- `0x1800016d0`
- `0x18001b1a0`
- `0x18001c6b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c77b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c77b`

## pseudocode

```c
__int64 __fastcall CAppContainer::ChooseBestFit(
        CAppContainer *this,
        const FILETIME *a2,
        unsigned int *a3,
        unsigned int a4,
        unsigned int *a5)
{
  unsigned int *v5; // r15
  const FILETIME *v7; // r14
  __int64 i; // rcx
  unsigned int v10; // r12d
  unsigned int v11; // edi
  __int64 v12; // rsi
  unsigned int v13; // ebp
  unsigned int v14; // r14d
  __int64 v15; // r15
  LONG v16; // eax
  int v17; // ecx
  __int64 v18; // rdi
  unsigned int v19; // ebp
  __int64 v20; // rsi
  bool v21; // zf
  unsigned int v22; // [rsp+20h] [rbp-98h]
  unsigned int *v23; // [rsp+28h] [rbp-90h]
  _OWORD v25[2]; // [rsp+40h] [rbp-78h] BYREF
  __int64 v26; // [rsp+60h] [rbp-58h]

  v5 = a5;
  v23 = a3;
  v7 = a2;
  *a5 = 0;
  v26 = 0;
  memset(v25, 0, sizeof(v25));
  if ( a4 > 0xA )
    return 2147942487LL;
  for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
    *((_DWORD *)v25 + i) = i;
  v10 = a4 - 1;
  v11 = 0;
  if ( a4 != 1 )
  {
    do
    {
      v12 = v11 + 1;
      v22 = v12;
      v13 = v11;
      v14 = a3[v11];
      if ( (unsigned int)v12 < a4 )
      {
        do
        {
          v15 = *((unsigned int *)v25 + v12);
          if ( a3[v15] > v14
            || a3[v15] == v14
            && (v16 = CompareFileTime(&a2[26 * v15 + 10], &a2[26 * *((unsigned int *)v25 + v13) + 10]),
                a3 = v23,
                v16 == 1) )
          {
            v14 = a3[v15];
            v13 = v12;
          }
          v12 = (unsigned int)(v12 + 1);
        }
        while ( (unsigned int)v12 < a4 );
        v10 = a4 - 1;
        if ( v13 != v11 )
        {
          v17 = *((_DWORD *)v25 + v13);
          *((_DWORD *)v25 + v13) = *((_DWORD *)v25 + v11);
          *((_DWORD *)v25 + v11) = v17;
        }
      }
      v11 = v22;
    }
    while ( v22 < v10 );
    v7 = a2;
    v5 = a5;
  }
  v18 = LODWORD(v25[0]);
  v19 = 0;
  if ( a4 )
  {
    v20 = 26LL * LODWORD(v25[0]);
    do
    {
      if ( gDebug )
        _DebugMsg(2, 0xC88u, *(_QWORD *)&v7[v20]);
      ++v19;
    }
    while ( v19 < a4 );
  }
  v21 = gDebug == 0;
  *v5 = v18;
  if ( !v21 )
    _DebugMsg(2, 0xC8Au, *(_QWORD *)&v7[26 * v18]);
  return 0;
}

```

## disassembly

```asm
0x18001c6b0  push    rbx
0x18001c6b2  push    rbp
0x18001c6b3  push    rsi
0x18001c6b4  push    rdi
0x18001c6b5  push    r12
0x18001c6b7  push    r13
0x18001c6b9  push    r14
0x18001c6bb  push    r15
0x18001c6bd  sub     rsp, 78h
0x18001c6c1  mov     rax, cs:__security_cookie
0x18001c6c8  xor     rax, rsp
0x18001c6cb  mov     [rsp+0B8h+var_50], rax
0x18001c6d0  mov     r15, [rsp+0B8h+arg_20]
0x18001c6d8  xor     eax, eax
0x18001c6da  mov     [rsp+0B8h+var_90], r8
0x18001c6df  xorps   xmm0, xmm0
0x18001c6e2  mov     [rsp+0B8h+var_88], rdx
0x18001c6e7  mov     ebx, r9d
0x18001c6ea  mov     [rsp+0B8h+var_80], r15
0x18001c6ef  mov     r14, rdx
0x18001c6f2  mov     [r15], eax
0x18001c6f5  mov     [rsp+0B8h+var_58], rax
0x18001c6fa  movups  [rsp+0B8h+var_78], xmm0
0x18001c6ff  movups  [rsp+0B8h+var_68], xmm0
0x18001c704  cmp     r9d, 0Ah
0x18001c708  jbe     short loc_18001C714
0x18001c70a  mov     eax, 80070057h
0x18001c70f  jmp     loc_18001C828
0x18001c714  xor     ecx, ecx
0x18001c716  test    ebx, ebx
0x18001c718  jz      short loc_18001C724
0x18001c71a  mov     dword ptr [rsp+rcx*4+0B8h+var_78], ecx
0x18001c71e  inc     ecx
0x18001c720  cmp     ecx, ebx
0x18001c722  jb      short loc_18001C71A
0x18001c724  lea     r12d, [r9-1]
0x18001c728  xor     edi, edi
0x18001c72a  test    r12d, r12d
0x18001c72d  jz      loc_18001C7CA
0x18001c733  lea     esi, [rdi+1]
0x18001c736  mov     r13d, edi
0x18001c739  mov     [rsp+0B8h+var_98], esi
0x18001c73d  mov     ebp, edi
0x18001c73f  mov     r14d, [r8+r13*4]
0x18001c743  cmp     esi, ebx
0x18001c745  jnb     short loc_18001C7B3
0x18001c747  mov     r12, [rsp+0B8h+var_88]
0x18001c74c  mov     r15d, dword ptr [rsp+rsi*4+0B8h+var_78]
0x18001c751  cmp     [r8+r15*4], r14d
0x18001c755  ja      short loc_18001C78B
0x18001c757  jnz     short loc_18001C791
0x18001c759  mov     eax, ebp
0x18001c75b  mov     ecx, dword ptr [rsp+rax*4+0B8h+var_78]
0x18001c75f  imul    rdx, rcx, 0D0h
0x18001c766  imul    rcx, r15, 0D0h
0x18001c76d  add     rdx, 50h ; 'P'
0x18001c771  add     rdx, r12; lpFileTime2
0x18001c774  add     rcx, 50h ; 'P'
0x18001c778  add     rcx, r12; lpFileTime1
0x18001c77b  call    cs:__imp_CompareFileTime
0x18001c781  mov     r8, [rsp+0B8h+var_90]
0x18001c786  cmp     eax, 1
0x18001c789  jnz     short loc_18001C791
0x18001c78b  mov     r14d, [r8+r15*4]
0x18001c78f  mov     ebp, esi
0x18001c791  inc     esi
0x18001c793  cmp     esi, ebx
0x18001c795  jb      short loc_18001C74C
0x18001c797  lea     r12d, [rbx-1]
0x18001c79b  cmp     ebp, edi
0x18001c79d  jz      short loc_18001C7B3
0x18001c79f  mov     eax, dword ptr [rsp+r13*4+0B8h+var_78]
0x18001c7a4  mov     edx, ebp
0x18001c7a6  mov     ecx, dword ptr [rsp+rdx*4+0B8h+var_78]
0x18001c7aa  mov     dword ptr [rsp+rdx*4+0B8h+var_78], eax
0x18001c7ae  mov     dword ptr [rsp+r13*4+0B8h+var_78], ecx
0x18001c7b3  mov     edi, [rsp+0B8h+var_98]
0x18001c7b7  cmp     edi, r12d
0x18001c7ba  jb      loc_18001C733
0x18001c7c0  mov     r14, [rsp+0B8h+var_88]
0x18001c7c5  mov     r15, [rsp+0B8h+var_80]
0x18001c7ca  mov     edi, dword ptr [rsp+0B8h+var_78]
0x18001c7ce  xor     ebp, ebp
0x18001c7d0  lea     r12d, [rbp+2]
0x18001c7d4  test    ebx, ebx
0x18001c7d6  jz      short loc_18001C802
0x18001c7d8  imul    rsi, rdi, 0D0h
0x18001c7df  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x18001c7e6  jz      short loc_18001C7F9
0x18001c7e8  mov     r8, [rsi+r14]
0x18001c7ec  mov     edx, 0C88h; unsigned int
0x18001c7f1  mov     ecx, r12d; unsigned int
0x18001c7f4  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001c7f9  lea     eax, [rbp+1]
0x18001c7fc  mov     ebp, eax
0x18001c7fe  cmp     eax, ebx
0x18001c800  jb      short loc_18001C7DF
0x18001c802  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x18001c809  mov     [r15], edi
0x18001c80c  jz      short loc_18001C826
0x18001c80e  imul    r8, rdi, 0D0h
0x18001c815  mov     edx, 0C8Ah; unsigned int
0x18001c81a  mov     ecx, r12d; unsigned int
0x18001c81d  mov     r8, [r8+r14]
0x18001c821  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001c826  xor     eax, eax
0x18001c828  mov     rcx, [rsp+0B8h+var_50]
0x18001c82d  xor     rcx, rsp; StackCookie
0x18001c830  call    __security_check_cookie
0x18001c835  add     rsp, 78h
0x18001c839  pop     r15
0x18001c83b  pop     r14
0x18001c83d  pop     r13
0x18001c83f  pop     r12
0x18001c841  pop     rdi
0x18001c842  pop     rsi
0x18001c843  pop     rbp
0x18001c844  pop     rbx
0x18001c845  retn
```
