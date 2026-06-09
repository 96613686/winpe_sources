# BCryptCreateContext

- ea: `0x1800138c0`
- end: `0x180013a38`
- name: `BCryptCreateContext`
- size: `376`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, PCRYPT_CONTEXT_CONFIG pConfig)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180002040`
- `0x18000283c`
- `0x180003860`
- `0x1800041d0`
- `0x180004200`
- `0x1800138c0`
- `0x18001b7e0`

## pseudocode

```c
NTSTATUS __stdcall BCryptCreateContext(ULONG dwTable, LPCWSTR pszContext, PCRYPT_CONTEXT_CONFIG pConfig)
{
  unsigned __int8 *v4; // rbx
  NTSTATUS v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  NTSTATUS v10; // edi
  size_t Size; // [rsp+48h] [rbp-170h]
  size_t Sizea; // [rsp+48h] [rbp-170h]
  unsigned int v14[4]; // [rsp+70h] [rbp-148h] BYREF
  unsigned __int8 v15[256]; // [rsp+80h] [rbp-138h] BYREF

  v14[0] = 0;
  v4 = v15;
  if ( dwTable - 1 > 1 || !pszContext || !*pszContext )
  {
    v7 = 87;
    goto LABEL_11;
  }
  LODWORD(Size) = 0;
  v7 = IoPack_Configuration_ParamBlock(dwTable, pszContext, 0, 0, 0, 0, 0, pConfig, 0, Size, 0, 0, v14, 0);
  if ( v7 )
  {
LABEL_11:
    v9 = WinErrorToNtStatus(v7);
    goto LABEL_12;
  }
  v8 = v14[0];
  if ( v14[0] > 0x100 )
  {
    v4 = (unsigned __int8 *)SafeAllocaAllocateFromHeap(v14[0]);
    if ( !v4 )
    {
      v7 = 8;
      goto LABEL_11;
    }
  }
  LODWORD(Sizea) = 0;
  v7 = IoPack_Configuration_ParamBlock(dwTable, pszContext, 0, 0, 0, 0, 0, pConfig, 0, Sizea, 0, 0, 0, v4);
  if ( v7 )
    goto LABEL_11;
  v9 = IoCallKernelDriver(0x10000u, v4, v8, 0, 0);
LABEL_12:
  v10 = v9;
  if ( v4 && v4 != v15 )
    BCryptFree(v4);
  return v10;
}

```

## disassembly

```asm
0x1800138c0  mov     [rsp+arg_18], rbx
0x1800138c5  push    rbp
0x1800138c6  push    rsi
0x1800138c7  push    rdi
0x1800138c8  push    r14
0x1800138ca  push    r15
0x1800138cc  sub     rsp, 190h
0x1800138d3  mov     rax, cs:__security_cookie
0x1800138da  xor     rax, rsp
0x1800138dd  mov     [rsp+1B8h+var_38], rax
0x1800138e5  xor     r15d, r15d
0x1800138e8  lea     eax, [rcx-1]
0x1800138eb  mov     [rsp+1B8h+var_148], r15d
0x1800138f0  mov     r14, r8
0x1800138f3  lea     rbx, [rsp+1B8h+var_138]
0x1800138fb  mov     rsi, rdx
0x1800138fe  mov     ebp, ecx
0x180013900  cmp     eax, 1
0x180013903  ja      loc_1800139E6
0x180013909  test    rdx, rdx
0x18001390c  jz      loc_1800139E6
0x180013912  cmp     [rdx], r15w
0x180013916  jz      loc_1800139E6
0x18001391c  mov     [rsp+1B8h+var_150], r15; unsigned __int8 *
0x180013921  lea     rax, [rsp+1B8h+var_148]
0x180013926  mov     [rsp+1B8h+var_158], rax; unsigned int *
0x18001392b  xor     r9d, r9d; unsigned __int16 *
0x18001392e  mov     [rsp+1B8h+var_160], r15; void *
0x180013933  mov     [rsp+1B8h+var_168], r15; unsigned __int8 *
0x180013938  mov     dword ptr [rsp+1B8h+Size], r15d; Size
0x18001393d  mov     [rsp+1B8h+var_178], r15; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x180013942  mov     [rsp+1B8h+var_180], r8; struct _CRYPT_CONTEXT_CONFIG *
0x180013947  xor     r8d, r8d; unsigned int
0x18001394a  mov     [rsp+1B8h+var_188], r15d; unsigned int
0x18001394f  mov     [rsp+1B8h+var_190], r15; unsigned __int16 *
0x180013954  mov     [rsp+1B8h+var_198], r15; Src
0x180013959  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x18001395e  test    eax, eax
0x180013960  jnz     loc_1800139EB
0x180013966  mov     edi, [rsp+1B8h+var_148]
0x18001396a  cmp     edi, 100h
0x180013970  jbe     short loc_180013986
0x180013972  mov     ecx, edi
0x180013974  call    SafeAllocaAllocateFromHeap
0x180013979  mov     rbx, rax
0x18001397c  test    rax, rax
0x18001397f  jnz     short loc_180013986
0x180013981  lea     eax, [rbx+8]
0x180013984  jmp     short loc_1800139EB
0x180013986  mov     [rsp+1B8h+var_150], rbx; unsigned __int8 *
0x18001398b  xor     r9d, r9d; unsigned __int16 *
0x18001398e  mov     [rsp+1B8h+var_158], r15; unsigned int *
0x180013993  xor     r8d, r8d; unsigned int
0x180013996  mov     [rsp+1B8h+var_160], r15; void *
0x18001399b  mov     rdx, rsi; unsigned __int16 *
0x18001399e  mov     [rsp+1B8h+var_168], r15; unsigned __int8 *
0x1800139a3  mov     ecx, ebp; unsigned int
0x1800139a5  mov     dword ptr [rsp+1B8h+Size], r15d; Size
0x1800139aa  mov     [rsp+1B8h+var_178], r15; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x1800139af  mov     [rsp+1B8h+var_180], r14; struct _CRYPT_CONTEXT_CONFIG *
0x1800139b4  mov     [rsp+1B8h+var_188], r15d; unsigned int
0x1800139b9  mov     [rsp+1B8h+var_190], r15; unsigned __int16 *
0x1800139be  mov     [rsp+1B8h+var_198], r15; Src
0x1800139c3  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x1800139c8  test    eax, eax
0x1800139ca  jnz     short loc_1800139EB
0x1800139cc  xor     r9d, r9d; unsigned __int8 *
0x1800139cf  mov     [rsp+1B8h+var_198], r15; unsigned int *
0x1800139d4  mov     r8d, edi; unsigned int
0x1800139d7  mov     rdx, rbx; unsigned __int8 *
0x1800139da  mov     ecx, 10000h; unsigned int
0x1800139df  call    ?IoCallKernelDriver@@YAJKPEAEK0PEAK@Z; IoCallKernelDriver(ulong,uchar *,ulong,uchar *,ulong *)
0x1800139e4  jmp     short loc_1800139F2
0x1800139e6  mov     eax, 57h ; 'W'
0x1800139eb  mov     ecx, eax; Status
0x1800139ed  call    ?WinErrorToNtStatus@@YAJK@Z; WinErrorToNtStatus(ulong)
0x1800139f2  mov     edi, eax
0x1800139f4  test    rbx, rbx
0x1800139f7  jz      short loc_180013A0E
0x1800139f9  lea     rax, [rsp+1B8h+var_138]
0x180013a01  cmp     rbx, rax
0x180013a04  jz      short loc_180013A0E
0x180013a06  mov     rcx, rbx
0x180013a09  call    BCryptFree
0x180013a0e  mov     eax, edi
0x180013a10  mov     rcx, [rsp+1B8h+var_38]
0x180013a18  xor     rcx, rsp; StackCookie
0x180013a1b  call    __security_check_cookie
0x180013a20  mov     rbx, [rsp+1B8h+arg_18]
0x180013a28  add     rsp, 190h
0x180013a2f  pop     r15
0x180013a31  pop     r14
0x180013a33  pop     rdi
0x180013a34  pop     rsi
0x180013a35  pop     rbp
0x180013a36  retn
```
