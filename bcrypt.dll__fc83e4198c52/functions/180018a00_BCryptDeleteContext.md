# BCryptDeleteContext

- ea: `0x180018a00`
- end: `0x180018b71`
- name: `BCryptDeleteContext`
- size: `369`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180002040`
- `0x18000283c`
- `0x180003860`
- `0x1800041d0`
- `0x180004200`
- `0x180018a00`
- `0x18001b7e0`

## pseudocode

```c
NTSTATUS __stdcall BCryptDeleteContext(ULONG dwTable, LPCWSTR pszContext)
{
  unsigned __int8 *v3; // rbx
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  NTSTATUS v7; // edi
  size_t Size; // [rsp+48h] [rbp-160h]
  size_t Sizea; // [rsp+48h] [rbp-160h]
  unsigned int v11[4]; // [rsp+70h] [rbp-138h] BYREF
  unsigned __int8 v12[256]; // [rsp+80h] [rbp-128h] BYREF

  v11[0] = 0;
  v3 = v12;
  if ( dwTable - 1 > 1 || !pszContext || !*pszContext )
  {
    v5 = 87;
    goto LABEL_11;
  }
  LODWORD(Size) = 0;
  v5 = IoPack_Configuration_ParamBlock(dwTable, pszContext, 0, 0, 0, 0, 0, 0, 0, Size, 0, 0, v11, 0);
  if ( v5 )
  {
LABEL_11:
    v6 = WinErrorToNtStatus(v5);
    goto LABEL_12;
  }
  if ( v11[0] > 0x100 )
  {
    v3 = (unsigned __int8 *)SafeAllocaAllocateFromHeap(v11[0]);
    if ( !v3 )
    {
      v5 = 8;
      goto LABEL_11;
    }
  }
  LODWORD(Sizea) = 0;
  v5 = IoPack_Configuration_ParamBlock(dwTable, pszContext, 0, 0, 0, 0, 0, 0, 0, Sizea, 0, 0, 0, v3);
  if ( v5 )
    goto LABEL_11;
  v6 = IoCallKernelDriver(65537, v3, v11[0], 0, 0);
LABEL_12:
  v7 = v6;
  if ( v3 && v3 != v12 )
    BCryptFree(v3);
  return v7;
}

```

## disassembly

```asm
0x180018a00  mov     [rsp+arg_10], rbx
0x180018a05  push    rbp
0x180018a06  push    rdi
0x180018a07  push    r14
0x180018a09  sub     rsp, 190h
0x180018a10  mov     rax, cs:__security_cookie
0x180018a17  xor     rax, rsp
0x180018a1a  mov     [rsp+1A8h+var_28], rax
0x180018a22  xor     r14d, r14d
0x180018a25  lea     eax, [rcx-1]
0x180018a28  mov     [rsp+1A8h+var_138], r14d
0x180018a2d  mov     rdi, rdx
0x180018a30  lea     rbx, [rsp+1A8h+var_128]
0x180018a38  mov     ebp, ecx
0x180018a3a  cmp     eax, 1
0x180018a3d  ja      loc_180018B22
0x180018a43  test    rdx, rdx
0x180018a46  jz      loc_180018B22
0x180018a4c  cmp     [rdx], r14w
0x180018a50  jz      loc_180018B22
0x180018a56  mov     [rsp+1A8h+var_140], r14; unsigned __int8 *
0x180018a5b  lea     rax, [rsp+1A8h+var_138]
0x180018a60  mov     [rsp+1A8h+var_148], rax; unsigned int *
0x180018a65  xor     r9d, r9d; unsigned __int16 *
0x180018a68  mov     [rsp+1A8h+var_150], r14; void *
0x180018a6d  xor     r8d, r8d; unsigned int
0x180018a70  mov     [rsp+1A8h+var_158], r14; unsigned __int8 *
0x180018a75  mov     dword ptr [rsp+1A8h+Size], r14d; Size
0x180018a7a  mov     [rsp+1A8h+var_168], r14; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x180018a7f  mov     [rsp+1A8h+var_170], r14; struct _CRYPT_CONTEXT_CONFIG *
0x180018a84  mov     [rsp+1A8h+var_178], r14d; unsigned int
0x180018a89  mov     [rsp+1A8h+var_180], r14; unsigned __int16 *
0x180018a8e  mov     [rsp+1A8h+var_188], r14; Src
0x180018a93  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x180018a98  test    eax, eax
0x180018a9a  jnz     loc_180018B27
0x180018aa0  cmp     [rsp+1A8h+var_138], 100h
0x180018aa8  jbe     short loc_180018AC0
0x180018aaa  mov     ecx, [rsp+1A8h+var_138]
0x180018aae  call    SafeAllocaAllocateFromHeap
0x180018ab3  mov     rbx, rax
0x180018ab6  test    rax, rax
0x180018ab9  jnz     short loc_180018AC0
0x180018abb  lea     eax, [rbx+8]
0x180018abe  jmp     short loc_180018B27
0x180018ac0  mov     [rsp+1A8h+var_140], rbx; unsigned __int8 *
0x180018ac5  xor     r9d, r9d; unsigned __int16 *
0x180018ac8  mov     [rsp+1A8h+var_148], r14; unsigned int *
0x180018acd  xor     r8d, r8d; unsigned int
0x180018ad0  mov     [rsp+1A8h+var_150], r14; void *
0x180018ad5  mov     rdx, rdi; unsigned __int16 *
0x180018ad8  mov     [rsp+1A8h+var_158], r14; unsigned __int8 *
0x180018add  mov     ecx, ebp; unsigned int
0x180018adf  mov     dword ptr [rsp+1A8h+Size], r14d; Size
0x180018ae4  mov     [rsp+1A8h+var_168], r14; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x180018ae9  mov     [rsp+1A8h+var_170], r14; struct _CRYPT_CONTEXT_CONFIG *
0x180018aee  mov     [rsp+1A8h+var_178], r14d; unsigned int
0x180018af3  mov     [rsp+1A8h+var_180], r14; unsigned __int16 *
0x180018af8  mov     [rsp+1A8h+var_188], r14; Src
0x180018afd  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x180018b02  test    eax, eax
0x180018b04  jnz     short loc_180018B27
0x180018b06  mov     r8d, [rsp+1A8h+var_138]; unsigned int
0x180018b0b  xor     r9d, r9d; unsigned __int8 *
0x180018b0e  mov     rdx, rbx; unsigned __int8 *
0x180018b11  mov     [rsp+1A8h+var_188], r14; unsigned int *
0x180018b16  mov     ecx, 10001h; unsigned int
0x180018b1b  call    ?IoCallKernelDriver@@YAJKPEAEK0PEAK@Z; IoCallKernelDriver(ulong,uchar *,ulong,uchar *,ulong *)
0x180018b20  jmp     short loc_180018B2E
0x180018b22  mov     eax, 57h ; 'W'
0x180018b27  mov     ecx, eax; Status
0x180018b29  call    ?WinErrorToNtStatus@@YAJK@Z; WinErrorToNtStatus(ulong)
0x180018b2e  mov     edi, eax
0x180018b30  test    rbx, rbx
0x180018b33  jz      short loc_180018B4A
0x180018b35  lea     rax, [rsp+1A8h+var_128]
0x180018b3d  cmp     rbx, rax
0x180018b40  jz      short loc_180018B4A
0x180018b42  mov     rcx, rbx
0x180018b45  call    BCryptFree
0x180018b4a  mov     eax, edi
0x180018b4c  mov     rcx, [rsp+1A8h+var_28]
0x180018b54  xor     rcx, rsp; StackCookie
0x180018b57  call    __security_check_cookie
0x180018b5c  mov     rbx, [rsp+1A8h+arg_10]
0x180018b64  add     rsp, 190h
0x180018b6b  pop     r14
0x180018b6d  pop     rdi
0x180018b6e  pop     rbp
0x180018b6f  retn
```
