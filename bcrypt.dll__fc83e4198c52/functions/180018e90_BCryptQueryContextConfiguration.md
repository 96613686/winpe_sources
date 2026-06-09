# BCryptQueryContextConfiguration

- ea: `0x180018e90`
- end: `0x180019066`
- name: `BCryptQueryContextConfiguration`
- size: `470`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG *pcbBuffer, PCRYPT_CONTEXT_CONFIG *ppBuffer)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800023f0`
- `0x18000283c`
- `0x180003860`
- `0x1800041d0`
- `0x180004200`
- `0x180018e90`
- `0x18001b7e0`

## pseudocode

```c
NTSTATUS __stdcall BCryptQueryContextConfiguration(
        ULONG dwTable,
        LPCWSTR pszContext,
        ULONG *pcbBuffer,
        PCRYPT_CONTEXT_CONFIG *ppBuffer)
{
  unsigned __int8 *v6; // rsi
  NTSTATUS v9; // edi
  unsigned int v10; // ebx
  NTSTATUS v11; // ebx
  PCRYPT_CONTEXT_CONFIG v12; // rax
  size_t Size; // [rsp+48h] [rbp-190h]
  size_t Sizea; // [rsp+48h] [rbp-190h]
  unsigned int v16; // [rsp+70h] [rbp-168h] BYREF
  int v17[3]; // [rsp+74h] [rbp-164h] BYREF
  unsigned __int8 v18[256]; // [rsp+80h] [rbp-158h] BYREF

  v16 = 0;
  v17[0] = 0;
  v6 = v18;
  if ( dwTable - 1 <= 1 && pcbBuffer )
  {
    LODWORD(Size) = 0;
    v9 = IoPack_Configuration_ParamBlock(dwTable, pszContext, 0, 0, 0, 0, 0, 0, 0, Size, 0, 0, &v16, 0);
    if ( v9 )
    {
LABEL_17:
      v11 = WinErrorToNtStatus(v9);
      goto LABEL_18;
    }
    v10 = v16;
    if ( v16 > 0x100 )
    {
      v6 = (unsigned __int8 *)SafeAllocaAllocateFromHeap(v16);
      if ( !v6 )
      {
        v9 = 8;
        goto LABEL_17;
      }
    }
    LODWORD(Sizea) = 0;
    v9 = IoPack_Configuration_ParamBlock(dwTable, pszContext, 0, 0, 0, 0, 0, 0, 0, Sizea, 0, 0, 0, v6);
    if ( v9 )
      goto LABEL_17;
    v11 = IoCallKernelDriverQueryLoop(0x10004u, v6, v10, (unsigned __int8 **)ppBuffer, pcbBuffer, v17);
    if ( v11 >= 0 )
    {
      v12 = *ppBuffer;
      if ( !*ppBuffer || &v12[1] >= v12 && &v12[1] <= (PCRYPT_CONTEXT_CONFIG)((char *)v12 + *pcbBuffer) )
        goto LABEL_18;
      v9 = 1359;
    }
  }
  else
  {
    v11 = 0;
    v9 = 87;
  }
  if ( v17[0] )
  {
    BCryptFree(*ppBuffer);
    *ppBuffer = 0;
  }
  if ( v11 >= 0 )
    goto LABEL_17;
LABEL_18:
  if ( v6 && v6 != v18 )
    BCryptFree(v6);
  if ( !ppBuffer && v11 == -1073741789 )
    return 0;
  return v11;
}

```

## disassembly

```asm
0x180018e90  push    rbx
0x180018e92  push    rbp
0x180018e93  push    rsi
0x180018e94  push    rdi
0x180018e95  push    r12
0x180018e97  push    r13
0x180018e99  push    r14
0x180018e9b  push    r15
0x180018e9d  sub     rsp, 198h
0x180018ea4  mov     rax, cs:__security_cookie
0x180018eab  xor     rax, rsp
0x180018eae  mov     [rsp+1D8h+var_58], rax
0x180018eb6  xor     r13d, r13d
0x180018eb9  lea     eax, [rcx-1]
0x180018ebc  mov     [rsp+1D8h+var_168], r13d
0x180018ec1  mov     r14, r9
0x180018ec4  mov     [rsp+1D8h+var_164], r13d
0x180018ec9  mov     rbp, r8
0x180018ecc  lea     rsi, [rsp+1D8h+var_158]
0x180018ed4  mov     r12, rdx
0x180018ed7  mov     r15d, ecx
0x180018eda  cmp     eax, 1
0x180018edd  ja      loc_180018FEF
0x180018ee3  test    r8, r8
0x180018ee6  jz      loc_180018FEF
0x180018eec  mov     [rsp+1D8h+var_170], r13; unsigned __int8 *
0x180018ef1  lea     rax, [rsp+1D8h+var_168]
0x180018ef6  mov     [rsp+1D8h+var_178], rax; unsigned int *
0x180018efb  xor     r9d, r9d; unsigned __int16 *
0x180018efe  mov     [rsp+1D8h+var_180], r13; void *
0x180018f03  xor     r8d, r8d; unsigned int
0x180018f06  mov     [rsp+1D8h+var_188], r13; unsigned __int8 *
0x180018f0b  mov     dword ptr [rsp+1D8h+Size], r13d; Size
0x180018f10  mov     [rsp+1D8h+var_198], r13; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x180018f15  mov     [rsp+1D8h+var_1A0], r13; struct _CRYPT_CONTEXT_CONFIG *
0x180018f1a  mov     [rsp+1D8h+var_1A8], r13d; unsigned int
0x180018f1f  mov     [rsp+1D8h+var_1B0], r13; unsigned __int16 *
0x180018f24  mov     [rsp+1D8h+var_1B8], r13; Src
0x180018f29  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x180018f2e  mov     edi, eax
0x180018f30  test    eax, eax
0x180018f32  jnz     loc_18001900D
0x180018f38  mov     ebx, [rsp+1D8h+var_168]
0x180018f3c  cmp     ebx, 100h
0x180018f42  jbe     short loc_180018F5B
0x180018f44  mov     ecx, ebx
0x180018f46  call    SafeAllocaAllocateFromHeap
0x180018f4b  mov     rsi, rax
0x180018f4e  test    rax, rax
0x180018f51  jnz     short loc_180018F5B
0x180018f53  lea     edi, [rax+8]
0x180018f56  jmp     loc_18001900D
0x180018f5b  mov     [rsp+1D8h+var_170], rsi; unsigned __int8 *
0x180018f60  xor     r9d, r9d; unsigned __int16 *
0x180018f63  mov     [rsp+1D8h+var_178], r13; unsigned int *
0x180018f68  xor     r8d, r8d; unsigned int
0x180018f6b  mov     [rsp+1D8h+var_180], r13; void *
0x180018f70  mov     rdx, r12; unsigned __int16 *
0x180018f73  mov     [rsp+1D8h+var_188], r13; unsigned __int8 *
0x180018f78  mov     ecx, r15d; unsigned int
0x180018f7b  mov     dword ptr [rsp+1D8h+Size], r13d; Size
0x180018f80  mov     [rsp+1D8h+var_198], r13; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x180018f85  mov     [rsp+1D8h+var_1A0], r13; struct _CRYPT_CONTEXT_CONFIG *
0x180018f8a  mov     [rsp+1D8h+var_1A8], r13d; unsigned int
0x180018f8f  mov     [rsp+1D8h+var_1B0], r13; unsigned __int16 *
0x180018f94  mov     [rsp+1D8h+var_1B8], r13; Src
0x180018f99  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x180018f9e  mov     edi, eax
0x180018fa0  test    eax, eax
0x180018fa2  jnz     short loc_18001900D
0x180018fa4  lea     rax, [rsp+1D8h+var_164]
0x180018fa9  mov     r9, r14; unsigned __int8 **
0x180018fac  mov     [rsp+1D8h+var_1B0], rax; int *
0x180018fb1  mov     r8d, ebx; unsigned int
0x180018fb4  mov     rdx, rsi; unsigned __int8 *
0x180018fb7  mov     [rsp+1D8h+var_1B8], rbp; unsigned int *
0x180018fbc  mov     ecx, 10004h; unsigned int
0x180018fc1  call    ?IoCallKernelDriverQueryLoop@@YAJKPEAEKPEAPEAEPEAKPEAH@Z; IoCallKernelDriverQueryLoop(ulong,uchar *,ulong,uchar * *,ulong *,int *)
0x180018fc6  mov     ebx, eax
0x180018fc8  test    eax, eax
0x180018fca  js      short loc_180018FF7
0x180018fcc  mov     rax, [r14]
0x180018fcf  test    rax, rax
0x180018fd2  jz      short loc_180019016
0x180018fd4  lea     rdx, [rax+8]
0x180018fd8  cmp     rdx, rax
0x180018fdb  jb      short loc_180018FE8
0x180018fdd  mov     ecx, [rbp+0]
0x180018fe0  add     rcx, rax
0x180018fe3  cmp     rdx, rcx
0x180018fe6  jbe     short loc_180019016
0x180018fe8  mov     edi, 54Fh
0x180018fed  jmp     short loc_180018FF7
0x180018fef  mov     ebx, r13d
0x180018ff2  mov     edi, 57h ; 'W'
0x180018ff7  cmp     [rsp+1D8h+var_164], r13d
0x180018ffc  jz      short loc_180019009
0x180018ffe  mov     rcx, [r14]
0x180019001  call    BCryptFree
0x180019006  mov     [r14], r13
0x180019009  test    ebx, ebx
0x18001900b  js      short loc_180019016
0x18001900d  mov     ecx, edi; Status
0x18001900f  call    ?WinErrorToNtStatus@@YAJK@Z; WinErrorToNtStatus(ulong)
0x180019014  mov     ebx, eax
0x180019016  test    rsi, rsi
0x180019019  jz      short loc_180019030
0x18001901b  lea     rax, [rsp+1D8h+var_158]
0x180019023  cmp     rsi, rax
0x180019026  jz      short loc_180019030
0x180019028  mov     rcx, rsi
0x18001902b  call    BCryptFree
0x180019030  test    r14, r14
0x180019033  jnz     short loc_18001903F
0x180019035  cmp     ebx, 0C0000023h
0x18001903b  cmovz   ebx, r13d
0x18001903f  mov     eax, ebx
0x180019041  mov     rcx, [rsp+1D8h+var_58]
0x180019049  xor     rcx, rsp; StackCookie
0x18001904c  call    __security_check_cookie
0x180019051  add     rsp, 198h
0x180019058  pop     r15
0x18001905a  pop     r14
0x18001905c  pop     r13
0x18001905e  pop     r12
0x180019060  pop     rdi
0x180019061  pop     rsi
0x180019062  pop     rbp
0x180019063  pop     rbx
0x180019064  retn
```
