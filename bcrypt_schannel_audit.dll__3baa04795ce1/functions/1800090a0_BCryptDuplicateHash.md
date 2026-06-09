# BCryptDuplicateHash

- ea: `0x1800090a0`
- end: `0x18000941e`
- name: `BCryptDuplicateHash`
- size: `894`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash, BCRYPT_HASH_HANDLE *phNewHash, PUCHAR pbHashObject, ULONG cbHashObject, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180004200`
- `0x180005060`
- `0x1800066f0`
- `0x180007a7c`
- `0x1800090a0`
- `0x180009430`
- `0x18000ed20`
- `0x18001c010`

## string_xrefs

- `0x1800091f5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180009321`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180009365`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180009406`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDuplicateHash(
        BCRYPT_HASH_HANDLE hHash,
        BCRYPT_HASH_HANDLE *phNewHash,
        PUCHAR pbHashObject,
        ULONG cbHashObject,
        ULONG dwFlags)
{
  ULONG v5; // ebp
  PUCHAR v6; // rdi
  _QWORD *v9; // rcx
  ULONG v10; // r13d
  __int64 v11; // rsi
  __int64 v12; // rdx
  _QWORD *v13; // r14
  __int64 v14; // rax
  UCHAR *v15; // rdx
  unsigned int v16; // r9d
  unsigned __int64 v17; // r8
  unsigned int v18; // ebp
  unsigned int v19; // eax
  NTSTATUS v20; // edi
  NTSTATUS result; // eax
  NTSTATUS Property; // eax
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // rcx
  unsigned __int64 v26; // rbp
  __int64 v27; // rcx
  unsigned int v28; // eax
  __int64 v29; // rcx
  ULONG pcbResult; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v31; // [rsp+44h] [rbp-44h]
  int v32; // [rsp+48h] [rbp-40h]
  __int64 v33; // [rsp+50h] [rbp-38h]
  ULONG pbOutput; // [rsp+90h] [rbp+8h] BYREF

  v5 = cbHashObject;
  v6 = pbHashObject;
  v9 = WPP_GLOBAL_Control;
  v10 = dwFlags;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qqqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      pbHashObject,
      hHash,
      phNewHash,
      pbHashObject,
      cbHashObject,
      dwFlags);
    v9 = WPP_GLOBAL_Control;
  }
  if ( hHash && *(_DWORD *)hHash >= 0x28u && *((_DWORD *)hHash + 1) == 1431655763 )
  {
    v11 = *((_QWORD *)hHash + 1);
    if ( !v6 && !v5 )
    {
      pbOutput = 0;
      pcbResult = 0;
      Property = BCryptGetProperty((BCRYPT_HANDLE)v11, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
      v20 = Property;
      if ( Property < 0 )
      {
        v25 = (unsigned int)Property;
      }
      else
      {
        v23 = SafeAllocaAllocateFromHeap(pbOutput);
        v33 = v23;
        v12 = v23;
        if ( v23 )
        {
          v5 = pbOutput;
          v6 = (PUCHAR)v23;
          v9 = WPP_GLOBAL_Control;
LABEL_7:
          if ( phNewHash )
          {
            if ( v5 < 0x46 )
            {
              v20 = -1073741789;
              if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
                WPP_SF_sDsd(
                  v9[2],
                  (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  (_DWORD)pbHashObject,
                  (unsigned int)"Status",
                  35,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  109);
              goto LABEL_29;
            }
            v13 = (_QWORD *)((unsigned __int64)(v6 + 15) & 0xFFFFFFFFFFFFFFF0uLL);
            v14 = (((_DWORD)v6 + 15) & 0xFFFFFFF0) - (unsigned int)v6;
            v13[4] = v12;
            *(_DWORD *)v13 = 40;
            *((_DWORD *)v13 + 1) = 1431655763;
            v15 = &v6[v14 + 40];
            v13[1] = v11;
            v16 = v5 - v14 - 40;
            if ( (*(_BYTE *)(v11 + 8) & 8) == 0 )
            {
              v17 = (unsigned __int64)(v15 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
              v18 = v16 + (_DWORD)v15 - v17;
LABEL_11:
              v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, unsigned __int64, _QWORD, ULONG))(v11 + 112))(
                      *((_QWORD *)hHash + 2),
                      v13 + 2,
                      v17,
                      v18,
                      v10);
              v20 = v19;
              if ( !v19 )
              {
                *phNewHash = v13;
                v20 = 0;
                goto LABEL_13;
              }
              v29 = v19;
              goto LABEL_42;
            }
            v24 = *(unsigned int *)(v11 + 12);
            if ( v16 < (int)v24 + 15 )
            {
              v20 = -1073741789;
              goto LABEL_29;
            }
            v32 = v16 - v24;
            v26 = (unsigned __int64)&v15[v24 + 15] & 0xFFFFFFFFFFFFFFF0uLL;
            v27 = *((_QWORD *)hHash + 3);
            v31 = (_DWORD)v15 + v24 + ((v16 - (unsigned int)v24) >> 1) - v26;
            v28 = (*(__int64 (__fastcall **)(__int64, _QWORD *, unsigned __int64, _QWORD, ULONG))(v11 + 112))(
                    v27,
                    v13 + 3,
                    v26,
                    v31,
                    v10);
            v20 = v28;
            if ( !v28 )
            {
              v17 = (v26 + v31 + 15LL) & 0xFFFFFFFFFFFFFFF0uLL;
              v18 = v32 + v26 - v17;
              goto LABEL_11;
            }
            v29 = v28;
LABEL_42:
            DebugTraceError(v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
LABEL_29:
            if ( v33 )
              MSCryptFree(v33);
            goto LABEL_13;
          }
LABEL_41:
          v20 = -1073741811;
          v29 = 3221225485LL;
          goto LABEL_42;
        }
        v20 = -1073741801;
        v25 = 3221225495LL;
      }
      DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
LABEL_13:
      result = v20;
      if ( v11 )
      {
        if ( v20 >= 0 )
          _InterlockedIncrement((volatile signed __int32 *)(v11 + 16));
      }
      return result;
    }
    v12 = 0;
    v33 = 0;
    if ( !v6 )
      goto LABEL_41;
    goto LABEL_7;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
    WPP_SF_sDsd(
      v9[2],
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      (_DWORD)pbHashObject,
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      71);
  return -1073741816;
}

```

## disassembly

```asm
0x1800090a0  mov     [rsp+arg_18], rbx
0x1800090a5  push    rbp
0x1800090a6  push    rdi
0x1800090a7  push    r13
0x1800090a9  push    r14
0x1800090ab  push    r15
0x1800090ad  sub     rsp, 60h
0x1800090b1  mov     ebp, r9d
0x1800090b4  mov     rdi, r8
0x1800090b7  mov     r15, rdx
0x1800090ba  mov     rbx, rcx
0x1800090bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090c4  lea     r14, WPP_GLOBAL_Control
0x1800090cb  mov     r13d, [rsp+88h+dwFlags]
0x1800090d3  cmp     rcx, r14
0x1800090d6  jnz     loc_180009224
0x1800090dc  test    rbx, rbx
0x1800090df  jz      loc_1800091E6
0x1800090e5  cmp     dword ptr [rbx], 28h ; '('
0x1800090e8  jb      loc_1800091E6
0x1800090ee  cmp     dword ptr [rbx+4], 55555553h
0x1800090f5  jnz     loc_1800091E6
0x1800090fb  mov     [rsp+88h+arg_8], rsi
0x180009103  mov     rsi, [rbx+8]
0x180009107  mov     [rsp+88h+arg_10], r12
0x18000910f  test    rdi, rdi
0x180009112  jz      loc_18000925E
0x180009118  xor     r12d, r12d
0x18000911b  mov     edx, r12d
0x18000911e  mov     [rsp+88h+var_38], rdx
0x180009123  test    rdi, rdi
0x180009126  jz      loc_1800093F6
0x18000912c  test    r15, r15
0x18000912f  jz      loc_1800093F6
0x180009135  cmp     ebp, 46h ; 'F'
0x180009138  jb      loc_18000930D
0x18000913e  lea     r14, [rdi+0Fh]
0x180009142  and     r14, 0FFFFFFFFFFFFFFF0h
0x180009146  mov     eax, r14d
0x180009149  sub     eax, edi
0x18000914b  sub     ebp, eax
0x18000914d  mov     [r14+20h], rdx
0x180009151  mov     dword ptr [r14], 28h ; '('
0x180009158  lea     rdx, [rax+28h]
0x18000915c  mov     dword ptr [r14+4], 55555553h
0x180009164  add     rdx, rdi
0x180009167  mov     [r14+8], rsi
0x18000916b  test    byte ptr [rsi+8], 8
0x18000916f  lea     r9d, [rbp-28h]
0x180009173  jnz     loc_1800092DF
0x180009179  lea     r8, [rdx+0Fh]
0x18000917d  and     r8, 0FFFFFFFFFFFFFFF0h
0x180009181  sub     edx, r8d
0x180009184  lea     ebp, [r9+rdx]
0x180009188  mov     rcx, [rbx+10h]
0x18000918c  lea     rdx, [r14+10h]
0x180009190  mov     rax, [rsi+70h]
0x180009194  mov     r9d, ebp
0x180009197  mov     dword ptr [rsp+88h+pcbResult], r13d
0x18000919c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091a1  mov     edi, eax
0x1800091a3  test    eax, eax
0x1800091a5  jnz     loc_1800093EC
0x1800091ab  mov     [r15], r14
0x1800091ae  mov     edi, r12d
0x1800091b1  mov     r12, [rsp+88h+arg_10]
0x1800091b9  mov     eax, edi
0x1800091bb  test    rsi, rsi
0x1800091be  jz      short loc_1800091C8
0x1800091c0  test    edi, edi
0x1800091c2  js      short loc_1800091C8
0x1800091c4  lock inc dword ptr [rsi+10h]
0x1800091c8  mov     rsi, [rsp+88h+arg_8]
0x1800091d0  mov     rbx, [rsp+88h+arg_18]
0x1800091d8  add     rsp, 60h
0x1800091dc  pop     r15
0x1800091de  pop     r14
0x1800091e0  pop     r13
0x1800091e2  pop     rdi
0x1800091e3  pop     rbp
0x1800091e4  retn
0x1800091e6  cmp     rcx, r14
0x1800091e9  jz      short loc_18000921D
0x1800091eb  test    byte ptr [rcx+1Ch], 1
0x1800091ef  jz      short loc_18000921D
0x1800091f1  mov     rcx, [rcx+10h]
0x1800091f5  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800091fc  mov     [rsp+88h+var_58], 1947h
0x180009204  lea     r9, aStatus; "Status"
0x18000920b  mov     qword ptr [rsp+88h+var_60], rdx
0x180009210  mov     dword ptr [rsp+88h+pcbResult], 0C0000008h
0x180009218  call    WPP_SF_sDsd
0x18000921d  mov     eax, 0C0000008h
0x180009222  jmp     short loc_1800091D0
0x180009224  test    byte ptr [rcx+1Ch], 4
0x180009228  jz      loc_1800090DC
0x18000922e  mov     rcx, [rcx+10h]
0x180009232  mov     edx, 25h ; '%'
0x180009237  mov     [rsp+88h+var_50], r13d
0x18000923c  mov     r9, rbx
0x18000923f  mov     [rsp+88h+var_58], ebp
0x180009243  mov     qword ptr [rsp+88h+var_60], rdi
0x180009248  mov     [rsp+88h+pcbResult], r15
0x18000924d  call    WPP_SF_qqqdD
0x180009252  mov     rcx, cs:WPP_GLOBAL_Control
0x180009259  jmp     loc_1800090DC
0x18000925e  test    ebp, ebp
0x180009260  jnz     loc_180009118
0x180009266  xor     r12d, r12d
0x180009269  lea     rax, [rsp+88h+var_48]
0x18000926e  mov     [rsp+88h+var_60], r12d; dwFlags
0x180009273  lea     r8, [rsp+88h+pbOutput]; pbOutput
0x18000927b  mov     r9d, 4; cbOutput
0x180009281  mov     [rsp+88h+pcbResult], rax; pcbResult
0x180009286  lea     rdx, aObjectlength; "ObjectLength"
0x18000928d  mov     [rsp+88h+pbOutput], r12d
0x180009295  mov     rcx, rsi; hObject
0x180009298  mov     [rsp+88h+var_48], r12d
0x18000929d  call    BCryptGetProperty
0x1800092a2  mov     edi, eax
0x1800092a4  test    eax, eax
0x1800092a6  js      loc_18000934B
0x1800092ac  mov     ecx, [rsp+88h+pbOutput]
0x1800092b3  call    SafeAllocaAllocateFromHeap
0x1800092b8  mov     [rsp+88h+var_38], rax
0x1800092bd  mov     rdx, rax
0x1800092c0  test    rax, rax
0x1800092c3  jz      loc_180009355
0x1800092c9  mov     ebp, [rsp+88h+pbOutput]
0x1800092d0  mov     rdi, rax
0x1800092d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092da  jmp     loc_18000912C
0x1800092df  mov     r8d, [rsi+0Ch]
0x1800092e3  lea     eax, [r8+0Fh]
0x1800092e7  cmp     r9d, eax
0x1800092ea  jnb     loc_180009383
0x1800092f0  mov     edi, 0C0000023h
0x1800092f5  mov     rcx, [rsp+88h+var_38]
0x1800092fa  test    rcx, rcx
0x1800092fd  jz      loc_1800091B1
0x180009303  call    MSCryptFree
0x180009308  jmp     loc_1800091B1
0x18000930d  mov     edi, 0C0000023h
0x180009312  cmp     rcx, r14
0x180009315  jz      short loc_1800092F5
0x180009317  test    byte ptr [rcx+1Ch], 1
0x18000931b  jz      short loc_1800092F5
0x18000931d  mov     rcx, [rcx+10h]
0x180009321  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009328  mov     [rsp+88h+var_58], 196Dh
0x180009330  lea     r9, aStatus; "Status"
0x180009337  mov     qword ptr [rsp+88h+var_60], rdx
0x18000933c  mov     dword ptr [rsp+88h+pcbResult], 0C0000023h
0x180009344  call    WPP_SF_sDsd
0x180009349  jmp     short loc_1800092F5
0x18000934b  mov     ecx, eax
0x18000934d  mov     r9d, 3E3h
0x180009353  jmp     short loc_180009365
0x180009355  mov     edi, 0C0000017h
0x18000935a  mov     ecx, 0C0000017h
0x18000935f  mov     r9d, 3EBh
0x180009365  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000936c  lea     rax, aStatus; "Status"
0x180009373  mov     r8, rdx
0x180009376  mov     rdx, rax
0x180009379  call    DebugTraceError
0x18000937e  jmp     loc_1800091B1
0x180009383  lea     rcx, [rdx+r8]
0x180009387  mov     dword ptr [rsp+88h+pcbResult], r13d
0x18000938c  sub     r9d, r8d
0x18000938f  lea     rbp, [rcx+0Fh]
0x180009393  mov     eax, r9d
0x180009396  mov     [rsp+88h+var_40], r9d
0x18000939b  shr     eax, 1
0x18000939d  lea     rdx, [r14+18h]
0x1800093a1  and     rbp, 0FFFFFFFFFFFFFFF0h
0x1800093a5  sub     eax, ebp
0x1800093a7  mov     r8, rbp
0x1800093aa  add     eax, ecx
0x1800093ac  mov     rcx, [rbx+18h]
0x1800093b0  mov     [rsp+88h+var_44], eax
0x1800093b4  mov     r9d, eax
0x1800093b7  mov     rax, [rsi+70h]
0x1800093bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093c0  mov     edi, eax
0x1800093c2  test    eax, eax
0x1800093c4  jz      short loc_1800093D0
0x1800093c6  mov     r9d, 19A2h
0x1800093cc  mov     ecx, eax
0x1800093ce  jmp     short loc_180009406
0x1800093d0  mov     r8d, [rsp+88h+var_44]
0x1800093d5  add     r8, 0Fh
0x1800093d9  add     r8, rbp
0x1800093dc  and     r8, 0FFFFFFFFFFFFFFF0h
0x1800093e0  sub     ebp, r8d
0x1800093e3  add     ebp, [rsp+88h+var_40]
0x1800093e7  jmp     loc_180009188
0x1800093ec  mov     r9d, 19B7h
0x1800093f2  mov     ecx, eax
0x1800093f4  jmp     short loc_180009406
0x1800093f6  mov     edi, 0C000000Dh
0x1800093fb  mov     r9d, 1966h
0x180009401  mov     ecx, 0C000000Dh
0x180009406  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000940d  lea     rdx, aStatus; "Status"
0x180009414  call    DebugTraceError
0x180009419  jmp     loc_1800092F5
```
