# BCryptGenerateKeyPair

- ea: `0x18000a230`
- end: `0x18000a3e1`
- name: `BCryptGenerateKeyPair`
- size: `433`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_KEY_HANDLE *phKey, ULONG dwLength, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180004200`
- `0x180005060`
- `0x180006bd0`
- `0x180007a7c`
- `0x180009430`
- `0x18000a230`
- `0x1800124c4`
- `0x18001c010`

## string_xrefs

- `0x18000a30e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000a384`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000a3c1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptGenerateKeyPair(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_KEY_HANDLE *phKey,
        ULONG dwLength,
        ULONG dwFlags)
{
  int v8; // edx
  __int64 v9; // rbx
  __int64 v10; // rax
  void *v11; // rsi
  int v12; // eax
  NTSTATUS v13; // edi
  __int64 v15; // rcx
  __int64 v16; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qqdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, dwLength, hAlgorithm, phKey, dwLength, dwFlags);
  v9 = ValidateBaseAlgHandle(hAlgorithm);
  if ( v9 )
  {
    if ( phKey )
    {
      v10 = SafeAllocaAllocateFromHeap(32);
      v11 = (void *)v10;
      if ( v10 )
      {
        *(_DWORD *)v10 = 32;
        *(_DWORD *)(v10 + 4) = 1431655762;
        *(_QWORD *)(v10 + 8) = v9;
        if ( *(_DWORD *)(v9 + 36) != 3 )
        {
          if ( *(_DWORD *)(v9 + 36) == 4 )
          {
            v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(v9 + 112))(
                    *(_QWORD *)(v9 + 24),
                    v10 + 16,
                    dwLength,
                    dwFlags);
LABEL_10:
            v13 = v12;
            if ( v12 >= 0 )
            {
              *phKey = v11;
              _InterlockedIncrement((volatile signed __int32 *)(v9 + 16));
              return 0;
            }
            v16 = (unsigned int)v12;
LABEL_24:
            DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
            MSCryptFree(v11);
            return v13;
          }
          if ( *(_DWORD *)(v9 + 36) != 5 && *(_DWORD *)(v9 + 36) != 8 )
          {
            v13 = -1073741637;
            v16 = 3221225659LL;
            goto LABEL_24;
          }
        }
        v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(v9 + 88))(
                *(_QWORD *)(v9 + 24),
                v10 + 16,
                dwLength,
                dwFlags);
        goto LABEL_10;
      }
      v13 = -1073741801;
      v15 = 3221225495LL;
    }
    else
    {
      v13 = -1073741811;
      v15 = 3221225485LL;
    }
    DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    return v13;
  }
  v13 = -1073741816;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      141);
  return v13;
}

```

## disassembly

```asm
0x18000a230  push    rbx
0x18000a232  push    rbp
0x18000a233  push    rsi
0x18000a234  push    rdi
0x18000a235  push    r14
0x18000a237  sub     rsp, 40h
0x18000a23b  mov     edi, r9d
0x18000a23e  mov     ebp, r8d
0x18000a241  mov     r14, rdx
0x18000a244  mov     rbx, rcx
0x18000a247  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a24e  lea     rsi, WPP_GLOBAL_Control
0x18000a255  cmp     rcx, rsi
0x18000a258  jz      short loc_18000A264
0x18000a25a  test    byte ptr [rcx+1Ch], 4
0x18000a25e  jnz     loc_18000A338
0x18000a264  mov     rcx, rbx
0x18000a267  call    ValidateBaseAlgHandle
0x18000a26c  mov     rbx, rax
0x18000a26f  test    rax, rax
0x18000a272  jz      short loc_18000A2F3
0x18000a274  test    r14, r14
0x18000a277  jz      loc_18000A35B
0x18000a27d  mov     ecx, 20h ; ' '
0x18000a282  call    SafeAllocaAllocateFromHeap
0x18000a287  mov     rsi, rax
0x18000a28a  test    rax, rax
0x18000a28d  jz      loc_18000A36D
0x18000a293  mov     dword ptr [rax], 20h ; ' '
0x18000a299  mov     dword ptr [rax+4], 55555552h
0x18000a2a0  mov     [rax+8], rbx
0x18000a2a4  mov     ecx, [rbx+24h]
0x18000a2a7  sub     ecx, 3
0x18000a2aa  jz      short loc_18000A2ED
0x18000a2ac  sub     ecx, 1
0x18000a2af  jnz     loc_18000A395
0x18000a2b5  mov     rax, [rbx+70h]
0x18000a2b9  mov     rcx, [rbx+18h]
0x18000a2bd  lea     rdx, [rsi+10h]
0x18000a2c1  mov     r9d, edi
0x18000a2c4  mov     r8d, ebp
0x18000a2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2cc  mov     edi, eax
0x18000a2ce  test    eax, eax
0x18000a2d0  js      loc_18000A3B9
0x18000a2d6  mov     [r14], rsi
0x18000a2d9  lock inc dword ptr [rbx+10h]
0x18000a2dd  xor     edi, edi
0x18000a2df  mov     eax, edi
0x18000a2e1  add     rsp, 40h
0x18000a2e5  pop     r14
0x18000a2e7  pop     rdi
0x18000a2e8  pop     rsi
0x18000a2e9  pop     rbp
0x18000a2ea  pop     rbx
0x18000a2eb  retn
0x18000a2ed  mov     rax, [rbx+58h]
0x18000a2f1  jmp     short loc_18000A2B9
0x18000a2f3  mov     edi, 0C0000008h
0x18000a2f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2ff  cmp     rcx, rsi
0x18000a302  jz      short loc_18000A2DF
0x18000a304  test    byte ptr [rcx+1Ch], 1
0x18000a308  jz      short loc_18000A2DF
0x18000a30a  mov     rcx, [rcx+10h]
0x18000a30e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a315  mov     [rsp+68h+var_38], 0D8Dh
0x18000a31d  lea     r9, aStatus; "Status"
0x18000a324  mov     [rsp+68h+var_40], r8
0x18000a329  mov     dword ptr [rsp+68h+var_48], 0C0000008h
0x18000a331  call    WPP_SF_sDsd
0x18000a336  jmp     short loc_18000A2DF
0x18000a338  mov     rcx, [rcx+10h]
0x18000a33c  mov     edx, 15h
0x18000a341  mov     [rsp+68h+var_38], edi
0x18000a345  mov     r9, rbx
0x18000a348  mov     dword ptr [rsp+68h+var_40], ebp
0x18000a34c  mov     [rsp+68h+var_48], r14
0x18000a351  call    WPP_SF_qqdD
0x18000a356  jmp     loc_18000A264
0x18000a35b  mov     edi, 0C000000Dh
0x18000a360  mov     r9d, 0D94h
0x18000a366  mov     ecx, 0C000000Dh
0x18000a36b  jmp     short loc_18000A37D
0x18000a36d  mov     edi, 0C0000017h
0x18000a372  mov     r9d, 0D9Dh
0x18000a378  mov     ecx, 0C0000017h
0x18000a37d  lea     rdx, aStatus; "Status"
0x18000a384  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a38b  call    DebugTraceError
0x18000a390  jmp     loc_18000A2DF
0x18000a395  sub     ecx, 1
0x18000a398  jz      loc_18000A2ED
0x18000a39e  cmp     ecx, 3
0x18000a3a1  jz      loc_18000A2ED
0x18000a3a7  mov     edi, 0C00000BBh
0x18000a3ac  mov     ecx, 0C00000BBh
0x18000a3b1  mov     r9d, 0DBBh
0x18000a3b7  jmp     short loc_18000A3C1
0x18000a3b9  mov     ecx, eax
0x18000a3bb  mov     r9d, 0DC6h
0x18000a3c1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a3c8  lea     rdx, aStatus; "Status"
0x18000a3cf  call    DebugTraceError
0x18000a3d4  mov     rcx, rsi
0x18000a3d7  call    MSCryptFree
0x18000a3dc  jmp     loc_18000A2DF
```
