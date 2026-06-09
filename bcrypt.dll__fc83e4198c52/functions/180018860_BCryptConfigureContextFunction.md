# BCryptConfigureContextFunction

- ea: `0x180018860`
- end: `0x1800189f5`
- name: `BCryptConfigureContextFunction`
- size: `405`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction, PCRYPT_CONTEXT_FUNCTION_CONFIG pConfig)`
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
- `0x180018860`
- `0x18001b7e0`

## pseudocode

```c
NTSTATUS __stdcall BCryptConfigureContextFunction(
        ULONG dwTable,
        LPCWSTR pszContext,
        ULONG dwInterface,
        LPCWSTR pszFunction,
        PCRYPT_CONTEXT_FUNCTION_CONFIG pConfig)
{
  unsigned __int8 *v5; // rbx
  int v10; // r8d
  const unsigned __int16 *v11; // r9
  NTSTATUS v12; // eax
  unsigned int v13; // edi
  int v14; // eax
  NTSTATUS v15; // edi
  size_t Size; // [rsp+48h] [rbp-1D0h]
  size_t Sizea; // [rsp+48h] [rbp-1D0h]
  unsigned int v19[4]; // [rsp+70h] [rbp-1A8h] BYREF
  unsigned __int8 v20[320]; // [rsp+80h] [rbp-198h] BYREF

  v5 = v20;
  v19[0] = 0;
  if ( dwTable - 1 > 1 || !(unsigned int)ValidateInterfaceId(dwInterface, 0) || !v11 || !*v11 )
  {
    v12 = 87;
    goto LABEL_12;
  }
  LODWORD(Size) = 0;
  v12 = IoPack_Configuration_ParamBlock(dwTable, pszContext, v10, v11, 0, 0, 0, 0, pConfig, Size, 0, 0, v19, 0);
  if ( v12 )
  {
LABEL_12:
    v14 = WinErrorToNtStatus(v12);
    goto LABEL_13;
  }
  v13 = v19[0];
  if ( v19[0] > 0x140 )
  {
    v5 = (unsigned __int8 *)SafeAllocaAllocateFromHeap(v19[0]);
    if ( !v5 )
    {
      v12 = 8;
      goto LABEL_12;
    }
  }
  LODWORD(Sizea) = 0;
  v12 = IoPack_Configuration_ParamBlock(
          dwTable,
          pszContext,
          dwInterface,
          pszFunction,
          0,
          0,
          0,
          0,
          pConfig,
          Sizea,
          0,
          0,
          0,
          v5);
  if ( v12 )
    goto LABEL_12;
  v14 = IoCallKernelDriver(0x10203u, v5, v13, 0, 0);
LABEL_13:
  v15 = v14;
  if ( v5 && v5 != v20 )
    BCryptFree(v5);
  return v15;
}

```

## disassembly

```asm
0x180018860  push    rbx
0x180018862  push    rbp
0x180018863  push    rsi
0x180018864  push    rdi
0x180018865  push    r12
0x180018867  push    r13
0x180018869  push    r14
0x18001886b  push    r15
0x18001886d  sub     rsp, 1D8h
0x180018874  mov     rax, cs:__security_cookie
0x18001887b  xor     rax, rsp
0x18001887e  mov     [rsp+218h+var_58], rax
0x180018886  mov     r12, [rsp+218h+pConfig]
0x18001888e  lea     eax, [rcx-1]
0x180018891  xor     r13d, r13d
0x180018894  lea     rbx, [rsp+218h+var_198]
0x18001889c  mov     [rsp+218h+var_1A8], r13d
0x1800188a1  mov     rsi, r9
0x1800188a4  mov     ebp, r8d
0x1800188a7  mov     r15, rdx
0x1800188aa  mov     r14d, ecx
0x1800188ad  cmp     eax, 1
0x1800188b0  ja      loc_1800189A6
0x1800188b6  xor     edx, edx; unsigned int
0x1800188b8  mov     ecx, r8d; unsigned int
0x1800188bb  call    ?ValidateInterfaceId@@YAHKK@Z; ValidateInterfaceId(ulong,ulong)
0x1800188c0  test    eax, eax
0x1800188c2  jz      loc_1800189A6
0x1800188c8  test    r9, r9
0x1800188cb  jz      loc_1800189A6
0x1800188d1  cmp     [r9], r13w
0x1800188d5  jz      loc_1800189A6
0x1800188db  mov     [rsp+218h+var_1B0], r13; unsigned __int8 *
0x1800188e0  lea     rax, [rsp+218h+var_1A8]
0x1800188e5  mov     [rsp+218h+var_1B8], rax; unsigned int *
0x1800188ea  mov     rdx, r15; unsigned __int16 *
0x1800188ed  mov     [rsp+218h+var_1C0], r13; void *
0x1800188f2  mov     ecx, r14d; unsigned int
0x1800188f5  mov     [rsp+218h+var_1C8], r13; unsigned __int8 *
0x1800188fa  mov     dword ptr [rsp+218h+Size], r13d; Size
0x1800188ff  mov     [rsp+218h+var_1D8], r12; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x180018904  mov     [rsp+218h+var_1E0], r13; struct _CRYPT_CONTEXT_CONFIG *
0x180018909  mov     [rsp+218h+var_1E8], r13d; unsigned int
0x18001890e  mov     [rsp+218h+var_1F0], r13; unsigned __int16 *
0x180018913  mov     [rsp+218h+var_1F8], r13; Src
0x180018918  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x18001891d  test    eax, eax
0x18001891f  jnz     loc_1800189AB
0x180018925  mov     edi, [rsp+218h+var_1A8]
0x180018929  cmp     edi, 140h
0x18001892f  jbe     short loc_180018945
0x180018931  mov     ecx, edi
0x180018933  call    SafeAllocaAllocateFromHeap
0x180018938  mov     rbx, rax
0x18001893b  test    rax, rax
0x18001893e  jnz     short loc_180018945
0x180018940  lea     eax, [rbx+8]
0x180018943  jmp     short loc_1800189AB
0x180018945  mov     [rsp+218h+var_1B0], rbx; unsigned __int8 *
0x18001894a  mov     r9, rsi; unsigned __int16 *
0x18001894d  mov     [rsp+218h+var_1B8], r13; unsigned int *
0x180018952  mov     r8d, ebp; unsigned int
0x180018955  mov     [rsp+218h+var_1C0], r13; void *
0x18001895a  mov     rdx, r15; unsigned __int16 *
0x18001895d  mov     [rsp+218h+var_1C8], r13; unsigned __int8 *
0x180018962  mov     ecx, r14d; unsigned int
0x180018965  mov     dword ptr [rsp+218h+Size], r13d; Size
0x18001896a  mov     [rsp+218h+var_1D8], r12; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x18001896f  mov     [rsp+218h+var_1E0], r13; struct _CRYPT_CONTEXT_CONFIG *
0x180018974  mov     [rsp+218h+var_1E8], r13d; unsigned int
0x180018979  mov     [rsp+218h+var_1F0], r13; unsigned __int16 *
0x18001897e  mov     [rsp+218h+var_1F8], r13; Src
0x180018983  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x180018988  test    eax, eax
0x18001898a  jnz     short loc_1800189AB
0x18001898c  xor     r9d, r9d; unsigned __int8 *
0x18001898f  mov     [rsp+218h+var_1F8], r13; unsigned int *
0x180018994  mov     r8d, edi; unsigned int
0x180018997  mov     rdx, rbx; unsigned __int8 *
0x18001899a  mov     ecx, 10203h; unsigned int
0x18001899f  call    ?IoCallKernelDriver@@YAJKPEAEK0PEAK@Z; IoCallKernelDriver(ulong,uchar *,ulong,uchar *,ulong *)
0x1800189a4  jmp     short loc_1800189B2
0x1800189a6  mov     eax, 57h ; 'W'
0x1800189ab  mov     ecx, eax; Status
0x1800189ad  call    ?WinErrorToNtStatus@@YAJK@Z; WinErrorToNtStatus(ulong)
0x1800189b2  mov     edi, eax
0x1800189b4  test    rbx, rbx
0x1800189b7  jz      short loc_1800189CE
0x1800189b9  lea     rax, [rsp+218h+var_198]
0x1800189c1  cmp     rbx, rax
0x1800189c4  jz      short loc_1800189CE
0x1800189c6  mov     rcx, rbx
0x1800189c9  call    BCryptFree
0x1800189ce  mov     eax, edi
0x1800189d0  mov     rcx, [rsp+218h+var_58]
0x1800189d8  xor     rcx, rsp; StackCookie
0x1800189db  call    __security_check_cookie
0x1800189e0  add     rsp, 1D8h
0x1800189e7  pop     r15
0x1800189e9  pop     r14
0x1800189eb  pop     r13
0x1800189ed  pop     r12
0x1800189ef  pop     rdi
0x1800189f0  pop     rsi
0x1800189f1  pop     rbp
0x1800189f2  pop     rbx
0x1800189f3  retn
```
