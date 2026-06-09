# BCryptGenerateSymmetricKey

- ea: `0x180005bc0`
- end: `0x180005f47`
- name: `BCryptGenerateSymmetricKey`
- size: `903`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_KEY_HANDLE *phKey, PUCHAR pbKeyObject, ULONG cbKeyObject, PUCHAR pbSecret, ULONG cbSecret, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005060`
- `0x180005bc0`
- `0x1800066f0`
- `0x180006bd0`
- `0x180007a7c`
- `0x180009430`
- `0x1800159dc`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180005c77`
- `ntdll!RtlAllocateHeap` at `0x180005c77`

## string_xrefs

- `0x180005dcf`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180005e02`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180005e79`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180005eec`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180005f2d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptGenerateSymmetricKey(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_KEY_HANDLE *phKey,
        PUCHAR pbKeyObject,
        ULONG cbKeyObject,
        PUCHAR pbSecret,
        ULONG cbSecret,
        ULONG dwFlags)
{
  ULONG v7; // r15d
  PUCHAR v8; // rdi
  int v11; // edx
  __int64 v12; // rbx
  int v13; // r8d
  NTSTATUS Property; // eax
  int v15; // edi
  PVOID Heap; // rax
  void *v17; // r14
  _DWORD *v18; // rsi
  int v19; // eax
  int v21; // edx
  int v22; // r8d
  __int64 v23; // rcx
  __int64 v24; // r9
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-38h] BYREF
  ULONG pcbResult[3]; // [rsp+54h] [rbp-34h] BYREF

  v7 = cbKeyObject;
  v8 = pbKeyObject;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qqqdqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      pbKeyObject,
      hAlgorithm,
      phKey,
      pbKeyObject,
      cbKeyObject,
      pbSecret,
      cbSecret,
      dwFlags);
  v12 = ValidateBaseAlgHandle(hAlgorithm);
  if ( v12 )
  {
    if ( !v8 && !v7 )
    {
      *(_DWORD *)pbOutput = 0;
      pcbResult[0] = 0;
      Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutput, 4u, pcbResult, 0);
      v15 = Property;
      if ( Property < 0 )
      {
        v23 = (unsigned int)Property;
        v24 = 995;
      }
      else
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)pbOutput);
        v17 = Heap;
        if ( Heap )
        {
          v7 = *(_DWORD *)pbOutput;
          v8 = (PUCHAR)Heap;
LABEL_9:
          if ( phKey && pbSecret )
          {
            if ( v7 < 0x3E )
            {
              v15 = -1073741789;
            }
            else
            {
              v18 = (_DWORD *)((unsigned __int64)(v8 + 15) & 0xFFFFFFFFFFFFFFF0uLL);
              *v18 = 32;
              v18[1] = 1431655762;
              *((_QWORD *)v18 + 1) = v12;
              *((_QWORD *)v18 + 3) = v17;
              if ( *(_DWORD *)(v12 + 36) == 1 || *(_DWORD *)(v12 + 36) == 7 )
              {
                v19 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, unsigned __int64, _QWORD, PUCHAR, ULONG, ULONG))(v12 + 88))(
                        *(_QWORD *)(v12 + 24),
                        v18 + 4,
                        ((unsigned __int64)v18 + 47) & 0xFFFFFFFFFFFFFFF0uLL,
                        v7 + (_DWORD)v8 - (((_DWORD)v18 + 47) & 0xFFFFFFF0),
                        pbSecret,
                        cbSecret,
                        dwFlags);
                v15 = v19;
                if ( v19 >= 0 )
                {
                  *phKey = v18;
                  v15 = 0;
LABEL_15:
                  _InterlockedIncrement((volatile signed __int32 *)(v12 + 16));
                  return v15;
                }
                DebugTraceError(
                  (unsigned int)v19,
                  "Status",
                  "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  3419);
              }
              else
              {
                v15 = -1073741637;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_sDsd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v11,
                    v13,
                    (unsigned int)"Status",
                    187,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                    76);
                }
              }
            }
            goto LABEL_22;
          }
LABEL_19:
          v15 = -1073741811;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v11,
              v13,
              (unsigned int)"Status",
              13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
              39);
LABEL_22:
          if ( v17 )
            MSCryptFree(v17);
LABEL_27:
          if ( v15 < 0 )
            return v15;
          goto LABEL_15;
        }
        v15 = -1073741801;
        v23 = 3221225495LL;
        v24 = 1003;
      }
      DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v24);
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v15;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v21,
          v22,
          (unsigned int)"Status",
          v15,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          22);
      goto LABEL_27;
    }
    v17 = 0;
    if ( !v8 )
      goto LABEL_19;
    goto LABEL_9;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v13,
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      8);
  return -1073741816;
}

```

## disassembly

```asm
0x180005bc0  mov     [rsp+arg_8], rbx
0x180005bc5  mov     [rsp+arg_10], rbp
0x180005bca  push    rsi
0x180005bcb  push    rdi
0x180005bcc  push    r12
0x180005bce  push    r13
0x180005bd0  push    r15
0x180005bd2  sub     rsp, 60h
0x180005bd6  mov     r15d, r9d
0x180005bd9  mov     rdi, r8
0x180005bdc  mov     r12, rdx
0x180005bdf  mov     rsi, rcx
0x180005be2  mov     rcx, cs:WPP_GLOBAL_Control
0x180005be9  lea     rbp, WPP_GLOBAL_Control
0x180005bf0  mov     r13, [rsp+88h+pbSecret]
0x180005bf8  cmp     rcx, rbp
0x180005bfb  jnz     loc_180005D5F
0x180005c01  mov     rcx, rsi
0x180005c04  call    ValidateBaseAlgHandle
0x180005c09  mov     rbx, rax
0x180005c0c  test    rax, rax
0x180005c0f  jz      loc_180005E63
0x180005c15  mov     [rsp+88h+arg_0], r14
0x180005c1d  test    rdi, rdi
0x180005c20  jnz     short loc_180005C99
0x180005c22  test    r15d, r15d
0x180005c25  jnz     short loc_180005C99
0x180005c27  xor     ebp, ebp
0x180005c29  lea     rax, [rsp+88h+var_34]
0x180005c2e  mov     [rsp+88h+var_60], ebp; dwFlags
0x180005c32  lea     r8, [rsp+88h+pbOutput]; pbOutput
0x180005c37  mov     r9d, 4; cbOutput
0x180005c3d  mov     [rsp+88h+pcbResult], rax; pcbResult
0x180005c42  lea     rdx, aObjectlength; "ObjectLength"
0x180005c49  mov     dword ptr [rsp+88h+pbOutput], ebp
0x180005c4d  mov     rcx, rsi; hObject
0x180005c50  mov     [rsp+88h+var_34], ebp
0x180005c54  call    BCryptGetProperty
0x180005c59  mov     edi, eax
0x180005c5b  test    eax, eax
0x180005c5d  js      loc_180005F05
0x180005c63  mov     rcx, gs:60h
0x180005c6c  xor     edx, edx; Flags
0x180005c6e  mov     r8d, dword ptr [rsp+88h+pbOutput]; Size
0x180005c73  mov     rcx, [rcx+30h]; HeapHandle
0x180005c77  call    cs:__imp_RtlAllocateHeap
0x180005c7e  nop     dword ptr [rax+rax+00h]
0x180005c83  mov     r14, rax
0x180005c86  test    rax, rax
0x180005c89  jz      loc_180005F12
0x180005c8f  mov     r15d, dword ptr [rsp+88h+pbOutput]
0x180005c94  mov     rdi, rax
0x180005c97  jmp     short loc_180005CA7
0x180005c99  xor     ebp, ebp
0x180005c9b  mov     r14d, ebp
0x180005c9e  test    rdi, rdi
0x180005ca1  jz      loc_180005DA9
0x180005ca7  test    r12, r12
0x180005caa  jz      loc_180005DA9
0x180005cb0  test    r13, r13
0x180005cb3  jz      loc_180005DA9
0x180005cb9  cmp     r15d, 3Eh ; '>'
0x180005cbd  jb      loc_180005EAB
0x180005cc3  lea     rsi, [rdi+0Fh]
0x180005cc7  and     rsi, 0FFFFFFFFFFFFFFF0h
0x180005ccb  mov     dword ptr [rsi], 20h ; ' '
0x180005cd1  mov     dword ptr [rsi+4], 55555552h
0x180005cd8  mov     [rsi+8], rbx
0x180005cdc  mov     [rsi+18h], r14
0x180005ce0  mov     ecx, [rbx+24h]
0x180005ce3  sub     ecx, 1
0x180005ce6  jnz     loc_180005EB5
0x180005cec  mov     eax, [rsp+88h+dwFlags]
0x180005cf3  lea     r8, [rsi+2Fh]
0x180005cf7  mov     rcx, [rbx+18h]
0x180005cfb  lea     rdx, [rsi+10h]
0x180005cff  mov     [rsp+88h+var_58], eax
0x180005d03  and     r8, 0FFFFFFFFFFFFFFF0h
0x180005d07  mov     eax, [rsp+88h+cbSecret]
0x180005d0e  sub     edi, r8d
0x180005d11  mov     [rsp+88h+var_60], eax
0x180005d15  mov     rax, [rbx+58h]
0x180005d19  mov     [rsp+88h+pcbResult], r13
0x180005d1e  lea     r9d, [r15+rdi]
0x180005d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d27  mov     edi, eax
0x180005d29  test    eax, eax
0x180005d2b  js      loc_180005F27
0x180005d31  mov     [r12], rsi
0x180005d35  mov     edi, ebp
0x180005d37  lock inc dword ptr [rbx+10h]
0x180005d3b  mov     r14, [rsp+88h+arg_0]
0x180005d43  mov     eax, edi
0x180005d45  lea     r11, [rsp+88h+var_28]
0x180005d4a  mov     rbx, [r11+38h]
0x180005d4e  mov     rbp, [r11+40h]
0x180005d52  mov     rsp, r11
0x180005d55  pop     r15
0x180005d57  pop     r13
0x180005d59  pop     r12
0x180005d5b  pop     rdi
0x180005d5c  pop     rsi
0x180005d5d  retn
0x180005d5f  test    byte ptr [rcx+1Ch], 4
0x180005d63  jz      loc_180005C01
0x180005d69  mov     eax, [rsp+88h+dwFlags]
0x180005d70  mov     edx, 14h
0x180005d75  mov     rcx, [rcx+10h]
0x180005d79  mov     r9, rsi
0x180005d7c  mov     [rsp+88h+var_40], eax
0x180005d80  mov     eax, [rsp+88h+cbSecret]
0x180005d87  mov     [rsp+88h+var_48], eax
0x180005d8b  mov     [rsp+88h+var_50], r13
0x180005d90  mov     [rsp+88h+var_58], r15d
0x180005d95  mov     qword ptr [rsp+88h+var_60], rdi
0x180005d9a  mov     [rsp+88h+pcbResult], r12
0x180005d9f  call    WPP_SF_qqqdqdD
0x180005da4  jmp     loc_180005C01
0x180005da9  mov     edi, 0C000000Dh
0x180005dae  mov     rcx, cs:WPP_GLOBAL_Control
0x180005db5  lea     rax, WPP_GLOBAL_Control
0x180005dbc  cmp     rcx, rax
0x180005dbf  jz      short loc_180005DF3
0x180005dc1  test    byte ptr [rcx+1Ch], 1
0x180005dc5  jz      short loc_180005DF3
0x180005dc7  mov     [rsp+88h+var_58], 0D27h
0x180005dcf  lea     rsi, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005dd6  mov     qword ptr [rsp+88h+var_60], rsi
0x180005ddb  mov     dword ptr [rsp+88h+pcbResult], 0C000000Dh
0x180005de3  mov     rcx, [rcx+10h]
0x180005de7  lea     r9, aStatus; "Status"
0x180005dee  call    WPP_SF_sDsd
0x180005df3  test    r14, r14
0x180005df6  jz      short loc_180005E56
0x180005df8  mov     rcx, r14
0x180005dfb  call    MSCryptFree
0x180005e00  jmp     short loc_180005E56
0x180005e02  lea     rsi, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005e09  mov     r8, rsi
0x180005e0c  lea     rdx, aStatus; "Status"
0x180005e13  call    DebugTraceError
0x180005e18  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e1f  lea     rax, WPP_GLOBAL_Control
0x180005e26  cmp     rcx, rax
0x180005e29  jz      loc_180005D3B
0x180005e2f  test    byte ptr [rcx+1Ch], 1
0x180005e33  jz      short loc_180005E56
0x180005e35  mov     rcx, [rcx+10h]
0x180005e39  lea     r9, aStatus; "Status"
0x180005e40  mov     [rsp+88h+var_58], 0D16h
0x180005e48  mov     qword ptr [rsp+88h+var_60], rsi
0x180005e4d  mov     dword ptr [rsp+88h+pcbResult], edi
0x180005e51  call    WPP_SF_sDsd
0x180005e56  test    edi, edi
0x180005e58  jns     loc_180005D37
0x180005e5e  jmp     loc_180005D3B
0x180005e63  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e6a  cmp     rcx, rbp
0x180005e6d  jz      short loc_180005EA1
0x180005e6f  test    byte ptr [rcx+1Ch], 1
0x180005e73  jz      short loc_180005EA1
0x180005e75  mov     rcx, [rcx+10h]
0x180005e79  lea     rsi, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005e80  mov     [rsp+88h+var_58], 0D08h
0x180005e88  lea     r9, aStatus; "Status"
0x180005e8f  mov     qword ptr [rsp+88h+var_60], rsi
0x180005e94  mov     dword ptr [rsp+88h+pcbResult], 0C0000008h
0x180005e9c  call    WPP_SF_sDsd
0x180005ea1  mov     eax, 0C0000008h
0x180005ea6  jmp     loc_180005D45
0x180005eab  mov     edi, 0C0000023h
0x180005eb0  jmp     loc_180005DF3
0x180005eb5  cmp     ecx, 6
0x180005eb8  jz      loc_180005CEC
0x180005ebe  mov     edi, 0C00000BBh
0x180005ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005eca  lea     rax, WPP_GLOBAL_Control
0x180005ed1  cmp     rcx, rax
0x180005ed4  jz      loc_180005DF3
0x180005eda  test    byte ptr [rcx+1Ch], 1
0x180005ede  jz      loc_180005DF3
0x180005ee4  mov     [rsp+88h+var_58], 0D4Ch
0x180005eec  lea     rsi, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005ef3  mov     qword ptr [rsp+88h+var_60], rsi
0x180005ef8  mov     dword ptr [rsp+88h+pcbResult], 0C00000BBh
0x180005f00  jmp     loc_180005DE3
0x180005f05  mov     ecx, eax
0x180005f07  mov     r9d, 3E3h
0x180005f0d  jmp     loc_180005E02
0x180005f12  mov     edi, 0C0000017h
0x180005f17  mov     ecx, 0C0000017h
0x180005f1c  mov     r9d, 3EBh
0x180005f22  jmp     loc_180005E02
0x180005f27  mov     r9d, 0D5Bh
0x180005f2d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005f34  lea     rdx, aStatus; "Status"
0x180005f3b  mov     ecx, eax
0x180005f3d  call    DebugTraceError
0x180005f42  jmp     loc_180005DF3
```
