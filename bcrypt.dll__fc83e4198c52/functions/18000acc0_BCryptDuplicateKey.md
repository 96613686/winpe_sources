# BCryptDuplicateKey

- ea: `0x18000acc0`
- end: `0x18000af1b`
- name: `BCryptDuplicateKey`
- size: `603`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, BCRYPT_KEY_HANDLE *phNewKey, PUCHAR pbKeyObject, ULONG cbKeyObject, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180005060`
- `0x180005f50`
- `0x180007a7c`
- `0x180009430`
- `0x180009740`
- `0x18000acc0`
- `0x18000ed20`
- `0x18001c010`

## string_xrefs

- `0x18000ae13`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000ae7a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000aea2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000aedb`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDuplicateKey(
        BCRYPT_KEY_HANDLE hKey,
        BCRYPT_KEY_HANDLE *phNewKey,
        PUCHAR pbKeyObject,
        ULONG cbKeyObject,
        ULONG dwFlags)
{
  void *v5; // rdi
  ULONG v6; // ebp
  PUCHAR v7; // rbx
  __int64 v10; // rax
  int v11; // edx
  __int64 v12; // r10
  __int64 v13; // r13
  __int64 v14; // rsi
  int v15; // eax
  NTSTATUS v16; // ebx
  _DWORD *v17; // r14
  int v18; // eax
  __int64 v20; // r9
  __int64 v21; // rcx
  ULONG v22; // [rsp+40h] [rbp-58h] BYREF
  void *v23; // [rsp+48h] [rbp-50h] BYREF

  v5 = 0;
  v6 = cbKeyObject;
  v23 = 0;
  v7 = pbKeyObject;
  v22 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qqqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      pbKeyObject,
      hKey,
      phNewKey,
      pbKeyObject,
      cbKeyObject,
      dwFlags);
  v10 = ValidateBaseKeyHandle(hKey);
  v13 = v10;
  if ( v10 )
  {
    if ( !phNewKey )
    {
      v16 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 5460);
      return v16;
    }
    v14 = *(_QWORD *)(v10 + 8);
    if ( v7 )
      goto LABEL_11;
    if ( !v6 )
    {
      v15 = AllocateObjectBuffer(*(_QWORD *)(v10 + 8), &v23, &v22);
      v16 = v15;
      if ( v15 < 0 )
      {
        DebugTraceError((unsigned int)v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 5475);
        v5 = v23;
        goto LABEL_15;
      }
      v5 = v23;
      v6 = v22;
      v7 = (PUCHAR)v23;
    }
    if ( v7 )
    {
LABEL_11:
      if ( v6 < 0x3E )
      {
        v16 = -1073741789;
        goto LABEL_15;
      }
      v17 = (_DWORD *)((unsigned __int64)(v7 + 15) & 0xFFFFFFFFFFFFFFF0uLL);
      *v17 = 32;
      v17[1] = 1431655762;
      *((_QWORD *)v17 + 1) = v14;
      *((_QWORD *)v17 + 3) = v5;
      if ( *(_DWORD *)(v14 + 36) != 1 && *(_DWORD *)(v14 + 36) != 7 )
      {
        v16 = -1073741637;
        v20 = 5528;
        v21 = 3221225659LL;
        goto LABEL_29;
      }
      v18 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, unsigned __int64, _QWORD, ULONG))(v14 + 128))(
              *(_QWORD *)(v13 + 16),
              v17 + 4,
              ((unsigned __int64)v17 + 47) & 0xFFFFFFFFFFFFFFF0uLL,
              (_DWORD)v7 - (((_DWORD)v17 + 47) & 0xFFFFFFF0) + v6,
              dwFlags);
      v16 = v18;
      if ( v18 >= 0 )
      {
        v5 = 0;
        *phNewKey = v17;
LABEL_15:
        if ( v5 )
          MSCryptFree(v5);
        if ( v14 && v16 >= 0 )
          _InterlockedIncrement((volatile signed __int32 *)(v14 + 16));
        return v16;
      }
      v20 = 5539;
      v21 = (unsigned int)v18;
    }
    else
    {
      v16 = -1073741811;
      v20 = 5492;
      v21 = 3221225485LL;
    }
LABEL_29:
    DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v20);
    goto LABEL_15;
  }
  v16 = -1073741816;
  if ( (_UNKNOWN **)v12 != &WPP_GLOBAL_Control && (*(_BYTE *)(v12 + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *(_QWORD *)(v12 + 16),
      v11,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      77);
  return v16;
}

```

## disassembly

```asm
0x18000acc0  push    rbx
0x18000acc2  push    rbp
0x18000acc3  push    rsi
0x18000acc4  push    rdi
0x18000acc5  push    r12
0x18000acc7  push    r13
0x18000acc9  push    r14
0x18000accb  push    r15
0x18000accd  sub     rsp, 58h
0x18000acd1  xor     edi, edi
0x18000acd3  mov     ebp, r9d
0x18000acd6  mov     [rsp+98h+var_50], rdi
0x18000acdb  mov     rbx, r8
0x18000acde  mov     [rsp+98h+var_58], edi
0x18000ace2  mov     r15, rdx
0x18000ace5  mov     rsi, rcx
0x18000ace8  mov     r10, cs:WPP_GLOBAL_Control
0x18000acef  lea     r14, WPP_GLOBAL_Control
0x18000acf6  mov     r12d, [rsp+98h+dwFlags]
0x18000acfe  cmp     r10, r14
0x18000ad01  jz      short loc_18000AD0E
0x18000ad03  test    byte ptr [r10+1Ch], 4
0x18000ad08  jnz     loc_18000AE44
0x18000ad0e  mov     rcx, rsi
0x18000ad11  call    ValidateBaseKeyHandle
0x18000ad16  mov     r13, rax
0x18000ad19  test    rax, rax
0x18000ad1c  jz      loc_18000ADFE
0x18000ad22  test    r15, r15
0x18000ad25  jz      loc_18000AE74
0x18000ad2b  mov     rsi, [rax+8]
0x18000ad2f  test    rbx, rbx
0x18000ad32  jnz     short loc_18000AD69
0x18000ad34  test    ebp, ebp
0x18000ad36  jnz     short loc_18000AD60
0x18000ad38  lea     r8, [rsp+98h+var_58]
0x18000ad3d  mov     rcx, rsi
0x18000ad40  lea     rdx, [rsp+98h+var_50]
0x18000ad45  call    AllocateObjectBuffer
0x18000ad4a  mov     ebx, eax
0x18000ad4c  test    eax, eax
0x18000ad4e  js      loc_18000AE9C
0x18000ad54  mov     rdi, [rsp+98h+var_50]
0x18000ad59  mov     ebp, [rsp+98h+var_58]
0x18000ad5d  mov     rbx, rdi
0x18000ad60  test    rbx, rbx
0x18000ad63  jz      loc_18000AEC1
0x18000ad69  cmp     ebp, 3Eh ; '>'
0x18000ad6c  jb      loc_18000AE3D
0x18000ad72  lea     r14, [rbx+0Fh]
0x18000ad76  and     r14, 0FFFFFFFFFFFFFFF0h
0x18000ad7a  mov     dword ptr [r14], 20h ; ' '
0x18000ad81  mov     dword ptr [r14+4], 55555552h
0x18000ad89  mov     [r14+8], rsi
0x18000ad8d  mov     [r14+18h], rdi
0x18000ad91  mov     ecx, [rsi+24h]
0x18000ad94  sub     ecx, 1
0x18000ad97  jnz     loc_18000AEF3
0x18000ad9d  mov     rcx, [r13+10h]
0x18000ada1  lea     r8, [r14+2Fh]
0x18000ada5  mov     rax, [rsi+80h]
0x18000adac  lea     rdx, [r14+10h]
0x18000adb0  and     r8, 0FFFFFFFFFFFFFFF0h
0x18000adb4  mov     dword ptr [rsp+98h+var_78], r12d
0x18000adb9  sub     ebx, r8d
0x18000adbc  lea     r9d, [rbx+rbp]
0x18000adc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adc5  mov     ebx, eax
0x18000adc7  test    eax, eax
0x18000adc9  js      loc_18000AED3
0x18000adcf  xor     edi, edi
0x18000add1  mov     [r15], r14
0x18000add4  test    rdi, rdi
0x18000add7  jnz     loc_18000AF0E
0x18000addd  test    rsi, rsi
0x18000ade0  jz      short loc_18000ADEA
0x18000ade2  test    ebx, ebx
0x18000ade4  js      short loc_18000ADEA
0x18000ade6  lock inc dword ptr [rsi+10h]
0x18000adea  mov     eax, ebx
0x18000adec  add     rsp, 58h
0x18000adf0  pop     r15
0x18000adf2  pop     r14
0x18000adf4  pop     r13
0x18000adf6  pop     r12
0x18000adf8  pop     rdi
0x18000adf9  pop     rsi
0x18000adfa  pop     rbp
0x18000adfb  pop     rbx
0x18000adfc  retn
0x18000adfe  mov     ebx, 0C0000008h
0x18000ae03  cmp     r10, r14
0x18000ae06  jz      short loc_18000ADEA
0x18000ae08  test    byte ptr [r10+1Ch], 1
0x18000ae0d  jz      short loc_18000ADEA
0x18000ae0f  mov     rcx, [r10+10h]
0x18000ae13  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ae1a  mov     [rsp+98h+var_68], 154Dh
0x18000ae22  lea     r9, aStatus; "Status"
0x18000ae29  mov     [rsp+98h+var_70], r8
0x18000ae2e  mov     dword ptr [rsp+98h+var_78], 0C0000008h
0x18000ae36  call    WPP_SF_sDsd
0x18000ae3b  jmp     short loc_18000ADEA
0x18000ae3d  mov     ebx, 0C0000023h
0x18000ae42  jmp     short loc_18000ADD4
0x18000ae44  mov     rcx, [r10+10h]
0x18000ae48  mov     edx, 1Eh
0x18000ae4d  mov     [rsp+98h+var_60], r12d
0x18000ae52  mov     r9, rsi
0x18000ae55  mov     [rsp+98h+var_68], ebp
0x18000ae59  mov     [rsp+98h+var_70], rbx
0x18000ae5e  mov     [rsp+98h+var_78], r15
0x18000ae63  call    WPP_SF_qqqdD
0x18000ae68  mov     r10, cs:WPP_GLOBAL_Control
0x18000ae6f  jmp     loc_18000AD0E
0x18000ae74  mov     r9d, 1554h
0x18000ae7a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ae81  lea     rdx, aStatus; "Status"
0x18000ae88  mov     ecx, 0C000000Dh
0x18000ae8d  mov     ebx, 0C000000Dh
0x18000ae92  call    DebugTraceError
0x18000ae97  jmp     loc_18000ADEA
0x18000ae9c  mov     r9d, 1563h
0x18000aea2  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000aea9  lea     rdx, aStatus; "Status"
0x18000aeb0  mov     ecx, eax
0x18000aeb2  call    DebugTraceError
0x18000aeb7  mov     rdi, [rsp+98h+var_50]
0x18000aebc  jmp     loc_18000ADD4
0x18000aec1  mov     ebx, 0C000000Dh
0x18000aec6  mov     r9d, 1574h
0x18000aecc  mov     ecx, 0C000000Dh
0x18000aed1  jmp     short loc_18000AEDB
0x18000aed3  mov     r9d, 15A3h
0x18000aed9  mov     ecx, eax
0x18000aedb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000aee2  lea     rdx, aStatus; "Status"
0x18000aee9  call    DebugTraceError
0x18000aeee  jmp     loc_18000ADD4
0x18000aef3  cmp     ecx, 6
0x18000aef6  jz      loc_18000AD9D
0x18000aefc  mov     ebx, 0C00000BBh
0x18000af01  mov     r9d, 1598h
0x18000af07  mov     ecx, 0C00000BBh
0x18000af0c  jmp     short loc_18000AEDB
0x18000af0e  mov     rcx, rdi
0x18000af11  call    MSCryptFree
0x18000af16  jmp     loc_18000ADDD
```
