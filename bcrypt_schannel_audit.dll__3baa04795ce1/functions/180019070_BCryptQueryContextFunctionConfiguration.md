# BCryptQueryContextFunctionConfiguration

- ea: `0x180019070`
- end: `0x180019293`
- name: `BCryptQueryContextFunctionConfiguration`
- size: `547`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction, ULONG *pcbBuffer, PCRYPT_CONTEXT_FUNCTION_CONFIG *ppBuffer)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180001d9c`
- `0x1800023f0`
- `0x18000283c`
- `0x180003860`
- `0x1800041d0`
- `0x180004200`
- `0x180019070`
- `0x18001b7e0`

## pseudocode

```c
NTSTATUS __stdcall BCryptQueryContextFunctionConfiguration(
        ULONG dwTable,
        LPCWSTR pszContext,
        ULONG dwInterface,
        LPCWSTR pszFunction,
        ULONG *pcbBuffer,
        PCRYPT_CONTEXT_FUNCTION_CONFIG *ppBuffer)
{
  unsigned __int8 *v6; // rsi
  unsigned __int16 *v8; // r8
  const unsigned __int16 *v11; // r9
  const unsigned __int16 *v12; // r10
  NTSTATUS v13; // edi
  unsigned int v14; // ebx
  int v15; // eax
  NTSTATUS v16; // ebx
  PCRYPT_CONTEXT_FUNCTION_CONFIG v17; // rax
  size_t Size; // [rsp+48h] [rbp-1D0h]
  size_t Sizea; // [rsp+48h] [rbp-1D0h]
  unsigned int v21; // [rsp+70h] [rbp-1A8h] BYREF
  int v22; // [rsp+74h] [rbp-1A4h] BYREF
  unsigned __int16 *v23; // [rsp+78h] [rbp-1A0h]
  unsigned __int8 v24[320]; // [rsp+80h] [rbp-198h] BYREF

  v6 = v24;
  v23 = (unsigned __int16 *)pszContext;
  LODWORD(v8) = 0;
  v21 = 0;
  v22 = 0;
  if ( dwTable - 1 <= 1 && (unsigned int)ValidateInterfaceId(dwInterface, 0) && v11 && *v11 != (_WORD)v8 && pcbBuffer )
  {
    LODWORD(Size) = (_DWORD)v8;
    v13 = IoPack_Configuration_ParamBlock(
            dwTable,
            v12,
            dwInterface,
            v11,
            v8,
            v8,
            (unsigned int)v8,
            (struct _CRYPT_CONTEXT_CONFIG *)v8,
            (struct _CRYPT_CONTEXT_FUNCTION_CONFIG *)v8,
            Size,
            (unsigned __int8 *)v8,
            v8,
            &v21,
            (unsigned __int8 *)v8);
    if ( v13 )
    {
LABEL_20:
      v16 = WinErrorToNtStatus(v13);
      LODWORD(v8) = 0;
      goto LABEL_21;
    }
    v14 = v21;
    if ( v21 > 0x140 )
    {
      v6 = (unsigned __int8 *)SafeAllocaAllocateFromHeap(v21);
      if ( !v6 )
      {
        v13 = 8;
        goto LABEL_20;
      }
    }
    LODWORD(Sizea) = 0;
    v13 = IoPack_Configuration_ParamBlock(dwTable, v23, dwInterface, pszFunction, 0, 0, 0, 0, 0, Sizea, 0, 0, 0, v6);
    if ( v13 )
      goto LABEL_20;
    v15 = IoCallKernelDriverQueryLoop(0x10204u, v6, v14, (unsigned __int8 **)ppBuffer, pcbBuffer, &v22);
    LODWORD(v8) = 0;
    v16 = v15;
    if ( v15 >= 0 )
    {
      v17 = *ppBuffer;
      if ( !*ppBuffer || &v17[1] >= v17 && &v17[1] <= (PCRYPT_CONTEXT_FUNCTION_CONFIG)((char *)v17 + *pcbBuffer) )
        goto LABEL_21;
      v13 = 1359;
    }
  }
  else
  {
    v16 = (int)v8;
    v13 = 87;
  }
  if ( v22 != (_DWORD)v8 )
  {
    BCryptFree(*ppBuffer);
    LODWORD(v8) = 0;
    *ppBuffer = 0;
  }
  if ( v16 >= 0 )
    goto LABEL_20;
LABEL_21:
  if ( v6 && v6 != v24 )
  {
    BCryptFree(v6);
    LODWORD(v8) = 0;
  }
  if ( !ppBuffer && v16 == -1073741789 )
    return (int)v8;
  return v16;
}

```

## disassembly

```asm
0x180019070  push    rbx
0x180019072  push    rbp
0x180019073  push    rsi
0x180019074  push    rdi
0x180019075  push    r12
0x180019077  push    r13
0x180019079  push    r14
0x18001907b  push    r15
0x18001907d  sub     rsp, 1D8h
0x180019084  mov     rax, cs:__security_cookie
0x18001908b  xor     rax, rsp
0x18001908e  mov     [rsp+218h+var_58], rax
0x180019096  mov     r15, [rsp+218h+pcbBuffer]
0x18001909e  lea     eax, [rcx-1]
0x1800190a1  mov     r14, [rsp+218h+ppBuffer]
0x1800190a9  lea     rsi, [rsp+218h+var_198]
0x1800190b1  mov     r12d, r8d
0x1800190b4  mov     [rsp+218h+var_1A0], rdx
0x1800190b9  xor     r8d, r8d
0x1800190bc  mov     rbp, r9
0x1800190bf  mov     [rsp+218h+var_1A8], r8d
0x1800190c4  mov     r10, rdx
0x1800190c7  mov     [rsp+218h+var_1A4], r8d
0x1800190cc  mov     r13d, ecx
0x1800190cf  cmp     eax, 1
0x1800190d2  ja      loc_180019213
0x1800190d8  xor     edx, edx; unsigned int
0x1800190da  mov     ecx, r12d; unsigned int
0x1800190dd  call    ?ValidateInterfaceId@@YAHKK@Z; ValidateInterfaceId(ulong,ulong)
0x1800190e2  test    eax, eax
0x1800190e4  jz      loc_180019213
0x1800190ea  test    r9, r9
0x1800190ed  jz      loc_180019213
0x1800190f3  cmp     [r9], r8w
0x1800190f7  jz      loc_180019213
0x1800190fd  test    r15, r15
0x180019100  jz      loc_180019213
0x180019106  mov     [rsp+218h+var_1B0], r8; unsigned __int8 *
0x18001910b  lea     rax, [rsp+218h+var_1A8]
0x180019110  mov     [rsp+218h+var_1B8], rax; unsigned int *
0x180019115  mov     rdx, r10; unsigned __int16 *
0x180019118  mov     [rsp+218h+var_1C0], r8; void *
0x18001911d  mov     ecx, r13d; unsigned int
0x180019120  mov     [rsp+218h+var_1C8], r8; unsigned __int8 *
0x180019125  mov     dword ptr [rsp+218h+Size], r8d; Size
0x18001912a  mov     [rsp+218h+var_1D8], r8; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x18001912f  mov     [rsp+218h+var_1E0], r8; struct _CRYPT_CONTEXT_CONFIG *
0x180019134  mov     [rsp+218h+var_1E8], r8d; unsigned int
0x180019139  mov     [rsp+218h+var_1F0], r8; unsigned __int16 *
0x18001913e  mov     [rsp+218h+var_1F8], r8; Src
0x180019143  mov     r8d, r12d; unsigned int
0x180019146  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x18001914b  mov     edi, eax
0x18001914d  xor     eax, eax
0x18001914f  test    edi, edi
0x180019151  jnz     loc_180019234
0x180019157  mov     ebx, [rsp+218h+var_1A8]
0x18001915b  cmp     ebx, 140h
0x180019161  jbe     short loc_18001917C
0x180019163  mov     ecx, ebx
0x180019165  call    SafeAllocaAllocateFromHeap
0x18001916a  mov     rsi, rax
0x18001916d  xor     eax, eax
0x18001916f  test    rsi, rsi
0x180019172  jnz     short loc_18001917C
0x180019174  lea     edi, [rax+8]
0x180019177  jmp     loc_180019234
0x18001917c  mov     rdx, [rsp+218h+var_1A0]; unsigned __int16 *
0x180019181  mov     r9, rbp; unsigned __int16 *
0x180019184  mov     [rsp+218h+var_1B0], rsi; unsigned __int8 *
0x180019189  mov     r8d, r12d; unsigned int
0x18001918c  mov     [rsp+218h+var_1B8], rax; unsigned int *
0x180019191  mov     ecx, r13d; unsigned int
0x180019194  mov     [rsp+218h+var_1C0], rax; void *
0x180019199  mov     [rsp+218h+var_1C8], rax; unsigned __int8 *
0x18001919e  mov     dword ptr [rsp+218h+Size], eax; Size
0x1800191a2  mov     [rsp+218h+var_1D8], rax; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x1800191a7  mov     [rsp+218h+var_1E0], rax; struct _CRYPT_CONTEXT_CONFIG *
0x1800191ac  mov     [rsp+218h+var_1E8], eax; unsigned int
0x1800191b0  mov     [rsp+218h+var_1F0], rax; unsigned __int16 *
0x1800191b5  mov     [rsp+218h+var_1F8], rax; Src
0x1800191ba  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x1800191bf  mov     edi, eax
0x1800191c1  test    eax, eax
0x1800191c3  jnz     short loc_180019234
0x1800191c5  lea     rax, [rsp+218h+var_1A4]
0x1800191ca  mov     r9, r14; unsigned __int8 **
0x1800191cd  mov     [rsp+218h+var_1F0], rax; int *
0x1800191d2  mov     r8d, ebx; unsigned int
0x1800191d5  mov     rdx, rsi; unsigned __int8 *
0x1800191d8  mov     [rsp+218h+var_1F8], r15; unsigned int *
0x1800191dd  mov     ecx, 10204h; unsigned int
0x1800191e2  call    ?IoCallKernelDriverQueryLoop@@YAJKPEAEKPEAPEAEPEAKPEAH@Z; IoCallKernelDriverQueryLoop(ulong,uchar *,ulong,uchar * *,ulong *,int *)
0x1800191e7  xor     r8d, r8d
0x1800191ea  mov     ebx, eax
0x1800191ec  test    eax, eax
0x1800191ee  js      short loc_18001921B
0x1800191f0  mov     rax, [r14]
0x1800191f3  test    rax, rax
0x1800191f6  jz      short loc_180019240
0x1800191f8  lea     rdx, [rax+8]
0x1800191fc  cmp     rdx, rax
0x1800191ff  jb      short loc_18001920C
0x180019201  mov     ecx, [r15]
0x180019204  add     rcx, rax
0x180019207  cmp     rdx, rcx
0x18001920a  jbe     short loc_180019240
0x18001920c  mov     edi, 54Fh
0x180019211  jmp     short loc_18001921B
0x180019213  mov     ebx, r8d
0x180019216  mov     edi, 57h ; 'W'
0x18001921b  cmp     [rsp+218h+var_1A4], r8d
0x180019220  jz      short loc_180019230
0x180019222  mov     rcx, [r14]
0x180019225  call    BCryptFree
0x18001922a  xor     r8d, r8d
0x18001922d  mov     [r14], r8
0x180019230  test    ebx, ebx
0x180019232  js      short loc_180019240
0x180019234  mov     ecx, edi; Status
0x180019236  call    ?WinErrorToNtStatus@@YAJK@Z; WinErrorToNtStatus(ulong)
0x18001923b  mov     ebx, eax
0x18001923d  xor     r8d, r8d
0x180019240  test    rsi, rsi
0x180019243  jz      short loc_18001925D
0x180019245  lea     rax, [rsp+218h+var_198]
0x18001924d  cmp     rsi, rax
0x180019250  jz      short loc_18001925D
0x180019252  mov     rcx, rsi
0x180019255  call    BCryptFree
0x18001925a  xor     r8d, r8d
0x18001925d  test    r14, r14
0x180019260  jnz     short loc_18001926C
0x180019262  cmp     ebx, 0C0000023h
0x180019268  cmovz   ebx, r8d
0x18001926c  mov     eax, ebx
0x18001926e  mov     rcx, [rsp+218h+var_58]
0x180019276  xor     rcx, rsp; StackCookie
0x180019279  call    __security_check_cookie
0x18001927e  add     rsp, 1D8h
0x180019285  pop     r15
0x180019287  pop     r14
0x180019289  pop     r13
0x18001928b  pop     r12
0x18001928d  pop     rdi
0x18001928e  pop     rsi
0x18001928f  pop     rbp
0x180019290  pop     rbx
0x180019291  retn
```
