# BCryptRemoveContextFunctionProvider

- ea: `0x180019770`
- end: `0x180019919`
- name: `BCryptRemoveContextFunctionProvider`
- size: `425`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 *Src)`
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
- `0x180019770`
- `0x18001b7e0`

## pseudocode

```c
__int64 __fastcall BCryptRemoveContextFunctionProvider(
        unsigned int a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int16 *Src)
{
  unsigned __int8 *v5; // rbx
  int v10; // r8d
  const unsigned __int16 *v11; // r9
  NTSTATUS v12; // eax
  unsigned int v13; // edi
  int v14; // eax
  unsigned int v15; // edi
  size_t Size; // [rsp+48h] [rbp-210h]
  size_t Sizea; // [rsp+48h] [rbp-210h]
  unsigned int v19[4]; // [rsp+70h] [rbp-1E8h] BYREF
  unsigned __int8 v20[384]; // [rsp+80h] [rbp-1D8h] BYREF

  v5 = v20;
  v19[0] = 0;
  if ( a1 - 1 > 1 || !(unsigned int)ValidateInterfaceId(a3, 0) || !v11 || !*v11 || !Src || !*Src )
  {
    v12 = 87;
    goto LABEL_14;
  }
  LODWORD(Size) = 0;
  v12 = IoPack_Configuration_ParamBlock(a1, a2, v10, v11, Src, 0, 0, 0, 0, Size, 0, 0, v19, 0);
  if ( v12 )
  {
LABEL_14:
    v14 = WinErrorToNtStatus(v12);
    goto LABEL_15;
  }
  v13 = v19[0];
  if ( v19[0] > 0x180 )
  {
    v5 = (unsigned __int8 *)SafeAllocaAllocateFromHeap(v19[0]);
    if ( !v5 )
    {
      v12 = 8;
      goto LABEL_14;
    }
  }
  LODWORD(Sizea) = 0;
  v12 = IoPack_Configuration_ParamBlock(a1, a2, a3, a4, Src, 0, 0, 0, 0, Sizea, 0, 0, 0, v5);
  if ( v12 )
    goto LABEL_14;
  v14 = IoCallKernelDriver(0x10301u, v5, v13, 0, 0);
LABEL_15:
  v15 = v14;
  if ( v5 && v5 != v20 )
    BCryptFree(v5);
  return v15;
}

```

## disassembly

```asm
0x180019770  push    rbx
0x180019772  push    rbp
0x180019773  push    rsi
0x180019774  push    rdi
0x180019775  push    r12
0x180019777  push    r13
0x180019779  push    r14
0x18001977b  push    r15
0x18001977d  sub     rsp, 218h
0x180019784  mov     rax, cs:__security_cookie
0x18001978b  xor     rax, rsp
0x18001978e  mov     [rsp+258h+var_58], rax
0x180019796  mov     rbp, [rsp+258h+Src]
0x18001979e  lea     eax, [rcx-1]
0x1800197a1  xor     r13d, r13d
0x1800197a4  lea     rbx, [rsp+258h+var_1D8]
0x1800197ac  mov     [rsp+258h+var_1E8], r13d
0x1800197b1  mov     rsi, r9
0x1800197b4  mov     r14d, r8d
0x1800197b7  mov     r12, rdx
0x1800197ba  mov     r15d, ecx
0x1800197bd  cmp     eax, 1
0x1800197c0  ja      loc_1800198CA
0x1800197c6  xor     edx, edx; unsigned int
0x1800197c8  mov     ecx, r8d; unsigned int
0x1800197cb  call    ?ValidateInterfaceId@@YAHKK@Z; ValidateInterfaceId(ulong,ulong)
0x1800197d0  test    eax, eax
0x1800197d2  jz      loc_1800198CA
0x1800197d8  test    r9, r9
0x1800197db  jz      loc_1800198CA
0x1800197e1  cmp     [r9], r13w
0x1800197e5  jz      loc_1800198CA
0x1800197eb  test    rbp, rbp
0x1800197ee  jz      loc_1800198CA
0x1800197f4  cmp     [rbp+0], r13w
0x1800197f9  jz      loc_1800198CA
0x1800197ff  mov     [rsp+258h+var_1F0], r13; unsigned __int8 *
0x180019804  lea     rax, [rsp+258h+var_1E8]
0x180019809  mov     [rsp+258h+var_1F8], rax; unsigned int *
0x18001980e  mov     rdx, r12; unsigned __int16 *
0x180019811  mov     [rsp+258h+var_200], r13; void *
0x180019816  mov     ecx, r15d; unsigned int
0x180019819  mov     [rsp+258h+var_208], r13; unsigned __int8 *
0x18001981e  mov     dword ptr [rsp+258h+Size], r13d; Size
0x180019823  mov     [rsp+258h+var_218], r13; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x180019828  mov     [rsp+258h+var_220], r13; struct _CRYPT_CONTEXT_CONFIG *
0x18001982d  mov     [rsp+258h+var_228], r13d; unsigned int
0x180019832  mov     [rsp+258h+var_230], r13; unsigned __int16 *
0x180019837  mov     [rsp+258h+var_238], rbp; Src
0x18001983c  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x180019841  test    eax, eax
0x180019843  jnz     loc_1800198CF
0x180019849  mov     edi, [rsp+258h+var_1E8]
0x18001984d  cmp     edi, 180h
0x180019853  jbe     short loc_180019869
0x180019855  mov     ecx, edi
0x180019857  call    SafeAllocaAllocateFromHeap
0x18001985c  mov     rbx, rax
0x18001985f  test    rax, rax
0x180019862  jnz     short loc_180019869
0x180019864  lea     eax, [rbx+8]
0x180019867  jmp     short loc_1800198CF
0x180019869  mov     [rsp+258h+var_1F0], rbx; unsigned __int8 *
0x18001986e  mov     r9, rsi; unsigned __int16 *
0x180019871  mov     [rsp+258h+var_1F8], r13; unsigned int *
0x180019876  mov     r8d, r14d; unsigned int
0x180019879  mov     [rsp+258h+var_200], r13; void *
0x18001987e  mov     rdx, r12; unsigned __int16 *
0x180019881  mov     [rsp+258h+var_208], r13; unsigned __int8 *
0x180019886  mov     ecx, r15d; unsigned int
0x180019889  mov     dword ptr [rsp+258h+Size], r13d; Size
0x18001988e  mov     [rsp+258h+var_218], r13; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x180019893  mov     [rsp+258h+var_220], r13; struct _CRYPT_CONTEXT_CONFIG *
0x180019898  mov     [rsp+258h+var_228], r13d; unsigned int
0x18001989d  mov     [rsp+258h+var_230], r13; unsigned __int16 *
0x1800198a2  mov     [rsp+258h+var_238], rbp; Src
0x1800198a7  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x1800198ac  test    eax, eax
0x1800198ae  jnz     short loc_1800198CF
0x1800198b0  xor     r9d, r9d; unsigned __int8 *
0x1800198b3  mov     [rsp+258h+var_238], r13; unsigned int *
0x1800198b8  mov     r8d, edi; unsigned int
0x1800198bb  mov     rdx, rbx; unsigned __int8 *
0x1800198be  mov     ecx, 10301h; unsigned int
0x1800198c3  call    ?IoCallKernelDriver@@YAJKPEAEK0PEAK@Z; IoCallKernelDriver(ulong,uchar *,ulong,uchar *,ulong *)
0x1800198c8  jmp     short loc_1800198D6
0x1800198ca  mov     eax, 57h ; 'W'
0x1800198cf  mov     ecx, eax; Status
0x1800198d1  call    ?WinErrorToNtStatus@@YAJK@Z; WinErrorToNtStatus(ulong)
0x1800198d6  mov     edi, eax
0x1800198d8  test    rbx, rbx
0x1800198db  jz      short loc_1800198F2
0x1800198dd  lea     rax, [rsp+258h+var_1D8]
0x1800198e5  cmp     rbx, rax
0x1800198e8  jz      short loc_1800198F2
0x1800198ea  mov     rcx, rbx
0x1800198ed  call    BCryptFree
0x1800198f2  mov     eax, edi
0x1800198f4  mov     rcx, [rsp+258h+var_58]
0x1800198fc  xor     rcx, rsp; StackCookie
0x1800198ff  call    __security_check_cookie
0x180019904  add     rsp, 218h
0x18001990b  pop     r15
0x18001990d  pop     r14
0x18001990f  pop     r13
0x180019911  pop     r12
0x180019913  pop     rdi
0x180019914  pop     rsi
0x180019915  pop     rbp
0x180019916  pop     rbx
0x180019917  retn
```
