# BCryptRemoveContextFunction

- ea: `0x1800195e0`
- end: `0x180019769`
- name: `BCryptRemoveContextFunction`
- size: `393`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180001d9c`
- `0x180002040`
- `0x18000283c`
- `0x180003860`
- `0x1800041d0`
- `0x180004200`
- `0x1800195e0`
- `0x18001b7e0`

## pseudocode

```c
NTSTATUS __stdcall BCryptRemoveContextFunction(
        ULONG dwTable,
        LPCWSTR pszContext,
        ULONG dwInterface,
        LPCWSTR pszFunction)
{
  unsigned __int8 *v5; // rbx
  int v9; // r8d
  const unsigned __int16 *v10; // r9
  NTSTATUS v11; // eax
  unsigned int v12; // edi
  NTSTATUS v13; // eax
  NTSTATUS v14; // edi
  size_t Size; // [rsp+48h] [rbp-1C0h]
  size_t Sizea; // [rsp+48h] [rbp-1C0h]
  unsigned int v18[4]; // [rsp+70h] [rbp-198h] BYREF
  unsigned __int8 v19[320]; // [rsp+80h] [rbp-188h] BYREF

  v18[0] = 0;
  v5 = v19;
  if ( dwTable - 1 > 1 || !(unsigned int)ValidateInterfaceId(dwInterface, 0) || !v10 || !*v10 )
  {
    v11 = 87;
    goto LABEL_12;
  }
  LODWORD(Size) = 0;
  v11 = IoPack_Configuration_ParamBlock(dwTable, pszContext, v9, v10, 0, 0, 0, 0, 0, Size, 0, 0, v18, 0);
  if ( v11 )
  {
LABEL_12:
    v13 = WinErrorToNtStatus(v11);
    goto LABEL_13;
  }
  v12 = v18[0];
  if ( v18[0] > 0x140 )
  {
    v5 = (unsigned __int8 *)SafeAllocaAllocateFromHeap(v18[0]);
    if ( !v5 )
    {
      v11 = 8;
      goto LABEL_12;
    }
  }
  LODWORD(Sizea) = 0;
  v11 = IoPack_Configuration_ParamBlock(
          dwTable,
          pszContext,
          dwInterface,
          pszFunction,
          0,
          0,
          0,
          0,
          0,
          Sizea,
          0,
          0,
          0,
          v5);
  if ( v11 )
    goto LABEL_12;
  v13 = IoCallKernelDriver(66049, v5, v12, 0, 0);
LABEL_13:
  v14 = v13;
  if ( v5 && v5 != v19 )
    BCryptFree(v5);
  return v14;
}

```

## disassembly

```asm
0x1800195e0  push    rbx
0x1800195e2  push    rbp
0x1800195e3  push    rsi
0x1800195e4  push    rdi
0x1800195e5  push    r12
0x1800195e7  push    r14
0x1800195e9  push    r15
0x1800195eb  sub     rsp, 1D0h
0x1800195f2  mov     rax, cs:__security_cookie
0x1800195f9  xor     rax, rsp
0x1800195fc  mov     [rsp+208h+var_48], rax
0x180019604  xor     r12d, r12d
0x180019607  lea     eax, [rcx-1]
0x18001960a  mov     [rsp+208h+var_198], r12d
0x18001960f  mov     rsi, r9
0x180019612  lea     rbx, [rsp+208h+var_188]
0x18001961a  mov     ebp, r8d
0x18001961d  mov     r15, rdx
0x180019620  mov     r14d, ecx
0x180019623  cmp     eax, 1
0x180019626  ja      loc_18001971C
0x18001962c  xor     edx, edx; unsigned int
0x18001962e  mov     ecx, r8d; unsigned int
0x180019631  call    ?ValidateInterfaceId@@YAHKK@Z; ValidateInterfaceId(ulong,ulong)
0x180019636  test    eax, eax
0x180019638  jz      loc_18001971C
0x18001963e  test    r9, r9
0x180019641  jz      loc_18001971C
0x180019647  cmp     [r9], r12w
0x18001964b  jz      loc_18001971C
0x180019651  mov     [rsp+208h+var_1A0], r12; unsigned __int8 *
0x180019656  lea     rax, [rsp+208h+var_198]
0x18001965b  mov     [rsp+208h+var_1A8], rax; unsigned int *
0x180019660  mov     rdx, r15; unsigned __int16 *
0x180019663  mov     [rsp+208h+var_1B0], r12; void *
0x180019668  mov     ecx, r14d; unsigned int
0x18001966b  mov     [rsp+208h+var_1B8], r12; unsigned __int8 *
0x180019670  mov     dword ptr [rsp+208h+Size], r12d; Size
0x180019675  mov     [rsp+208h+var_1C8], r12; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x18001967a  mov     [rsp+208h+var_1D0], r12; struct _CRYPT_CONTEXT_CONFIG *
0x18001967f  mov     [rsp+208h+var_1D8], r12d; unsigned int
0x180019684  mov     [rsp+208h+var_1E0], r12; unsigned __int16 *
0x180019689  mov     [rsp+208h+var_1E8], r12; Src
0x18001968e  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x180019693  test    eax, eax
0x180019695  jnz     loc_180019721
0x18001969b  mov     edi, [rsp+208h+var_198]
0x18001969f  cmp     edi, 140h
0x1800196a5  jbe     short loc_1800196BB
0x1800196a7  mov     ecx, edi
0x1800196a9  call    SafeAllocaAllocateFromHeap
0x1800196ae  mov     rbx, rax
0x1800196b1  test    rax, rax
0x1800196b4  jnz     short loc_1800196BB
0x1800196b6  lea     eax, [rbx+8]
0x1800196b9  jmp     short loc_180019721
0x1800196bb  mov     [rsp+208h+var_1A0], rbx; unsigned __int8 *
0x1800196c0  mov     r9, rsi; unsigned __int16 *
0x1800196c3  mov     [rsp+208h+var_1A8], r12; unsigned int *
0x1800196c8  mov     r8d, ebp; unsigned int
0x1800196cb  mov     [rsp+208h+var_1B0], r12; void *
0x1800196d0  mov     rdx, r15; unsigned __int16 *
0x1800196d3  mov     [rsp+208h+var_1B8], r12; unsigned __int8 *
0x1800196d8  mov     ecx, r14d; unsigned int
0x1800196db  mov     dword ptr [rsp+208h+Size], r12d; Size
0x1800196e0  mov     [rsp+208h+var_1C8], r12; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x1800196e5  mov     [rsp+208h+var_1D0], r12; struct _CRYPT_CONTEXT_CONFIG *
0x1800196ea  mov     [rsp+208h+var_1D8], r12d; unsigned int
0x1800196ef  mov     [rsp+208h+var_1E0], r12; unsigned __int16 *
0x1800196f4  mov     [rsp+208h+var_1E8], r12; Src
0x1800196f9  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x1800196fe  test    eax, eax
0x180019700  jnz     short loc_180019721
0x180019702  xor     r9d, r9d; unsigned __int8 *
0x180019705  mov     [rsp+208h+var_1E8], r12; unsigned int *
0x18001970a  mov     r8d, edi; unsigned int
0x18001970d  mov     rdx, rbx; unsigned __int8 *
0x180019710  mov     ecx, 10201h; unsigned int
0x180019715  call    ?IoCallKernelDriver@@YAJKPEAEK0PEAK@Z; IoCallKernelDriver(ulong,uchar *,ulong,uchar *,ulong *)
0x18001971a  jmp     short loc_180019728
0x18001971c  mov     eax, 57h ; 'W'
0x180019721  mov     ecx, eax; Status
0x180019723  call    ?WinErrorToNtStatus@@YAJK@Z; WinErrorToNtStatus(ulong)
0x180019728  mov     edi, eax
0x18001972a  test    rbx, rbx
0x18001972d  jz      short loc_180019744
0x18001972f  lea     rax, [rsp+208h+var_188]
0x180019737  cmp     rbx, rax
0x18001973a  jz      short loc_180019744
0x18001973c  mov     rcx, rbx
0x18001973f  call    BCryptFree
0x180019744  mov     eax, edi
0x180019746  mov     rcx, [rsp+208h+var_48]
0x18001974e  xor     rcx, rsp; StackCookie
0x180019751  call    __security_check_cookie
0x180019756  add     rsp, 1D0h
0x18001975d  pop     r15
0x18001975f  pop     r14
0x180019761  pop     r12
0x180019763  pop     rdi
0x180019764  pop     rsi
0x180019765  pop     rbp
0x180019766  pop     rbx
0x180019767  retn
```
