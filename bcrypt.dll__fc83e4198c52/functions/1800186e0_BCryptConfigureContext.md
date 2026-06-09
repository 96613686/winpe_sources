# BCryptConfigureContext

- ea: `0x1800186e0`
- end: `0x18001884e`
- name: `BCryptConfigureContext`
- size: `366`
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
- `0x1800186e0`
- `0x18001b7e0`

## pseudocode

```c
NTSTATUS __stdcall BCryptConfigureContext(ULONG dwTable, LPCWSTR pszContext, PCRYPT_CONTEXT_CONFIG pConfig)
{
  unsigned __int8 *v4; // rbx
  NTSTATUS v7; // eax
  unsigned int v8; // edi
  NTSTATUS v9; // eax
  NTSTATUS v10; // edi
  size_t Size; // [rsp+48h] [rbp-170h]
  size_t Sizea; // [rsp+48h] [rbp-170h]
  unsigned int v14[4]; // [rsp+70h] [rbp-148h] BYREF
  unsigned __int8 v15[256]; // [rsp+80h] [rbp-138h] BYREF

  v14[0] = 0;
  v4 = v15;
  if ( dwTable - 1 > 1 || !pConfig )
  {
    v7 = 87;
    goto LABEL_10;
  }
  LODWORD(Size) = 0;
  v7 = IoPack_Configuration_ParamBlock(dwTable, pszContext, 0, 0, 0, 0, 0, pConfig, 0, Size, 0, 0, v14, 0);
  if ( v7 )
  {
LABEL_10:
    v9 = WinErrorToNtStatus(v7);
    goto LABEL_11;
  }
  v8 = v14[0];
  if ( v14[0] > 0x100 )
  {
    v4 = (unsigned __int8 *)SafeAllocaAllocateFromHeap(v14[0]);
    if ( !v4 )
    {
      v7 = 8;
      goto LABEL_10;
    }
  }
  LODWORD(Sizea) = 0;
  v7 = IoPack_Configuration_ParamBlock(dwTable, pszContext, 0, 0, 0, 0, 0, pConfig, 0, Sizea, 0, 0, 0, v4);
  if ( v7 )
    goto LABEL_10;
  v9 = IoCallKernelDriver(65539, v4, v8, 0, 0);
LABEL_11:
  v10 = v9;
  if ( v4 && v4 != v15 )
    BCryptFree(v4);
  return v10;
}

```

## disassembly

```asm
0x1800186e0  mov     [rsp+arg_18], rbx
0x1800186e5  push    rbp
0x1800186e6  push    rsi
0x1800186e7  push    rdi
0x1800186e8  push    r14
0x1800186ea  push    r15
0x1800186ec  sub     rsp, 190h
0x1800186f3  mov     rax, cs:__security_cookie
0x1800186fa  xor     rax, rsp
0x1800186fd  mov     [rsp+1B8h+var_38], rax
0x180018705  xor     r15d, r15d
0x180018708  lea     eax, [rcx-1]
0x18001870b  mov     [rsp+1B8h+var_148], r15d
0x180018710  mov     rsi, r8
0x180018713  lea     rbx, [rsp+1B8h+var_138]
0x18001871b  mov     r14, rdx
0x18001871e  mov     ebp, ecx
0x180018720  cmp     eax, 1
0x180018723  ja      loc_1800187FC
0x180018729  test    r8, r8
0x18001872c  jz      loc_1800187FC
0x180018732  mov     [rsp+1B8h+var_150], r15; unsigned __int8 *
0x180018737  lea     rax, [rsp+1B8h+var_148]
0x18001873c  mov     [rsp+1B8h+var_158], rax; unsigned int *
0x180018741  xor     r9d, r9d; unsigned __int16 *
0x180018744  mov     [rsp+1B8h+var_160], r15; void *
0x180018749  mov     [rsp+1B8h+var_168], r15; unsigned __int8 *
0x18001874e  mov     dword ptr [rsp+1B8h+Size], r15d; Size
0x180018753  mov     [rsp+1B8h+var_178], r15; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x180018758  mov     [rsp+1B8h+var_180], r8; struct _CRYPT_CONTEXT_CONFIG *
0x18001875d  xor     r8d, r8d; unsigned int
0x180018760  mov     [rsp+1B8h+var_188], r15d; unsigned int
0x180018765  mov     [rsp+1B8h+var_190], r15; unsigned __int16 *
0x18001876a  mov     [rsp+1B8h+var_198], r15; Src
0x18001876f  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x180018774  test    eax, eax
0x180018776  jnz     loc_180018801
0x18001877c  mov     edi, [rsp+1B8h+var_148]
0x180018780  cmp     edi, 100h
0x180018786  jbe     short loc_18001879C
0x180018788  mov     ecx, edi
0x18001878a  call    SafeAllocaAllocateFromHeap
0x18001878f  mov     rbx, rax
0x180018792  test    rax, rax
0x180018795  jnz     short loc_18001879C
0x180018797  lea     eax, [rbx+8]
0x18001879a  jmp     short loc_180018801
0x18001879c  mov     [rsp+1B8h+var_150], rbx; unsigned __int8 *
0x1800187a1  xor     r9d, r9d; unsigned __int16 *
0x1800187a4  mov     [rsp+1B8h+var_158], r15; unsigned int *
0x1800187a9  xor     r8d, r8d; unsigned int
0x1800187ac  mov     [rsp+1B8h+var_160], r15; void *
0x1800187b1  mov     rdx, r14; unsigned __int16 *
0x1800187b4  mov     [rsp+1B8h+var_168], r15; unsigned __int8 *
0x1800187b9  mov     ecx, ebp; unsigned int
0x1800187bb  mov     dword ptr [rsp+1B8h+Size], r15d; Size
0x1800187c0  mov     [rsp+1B8h+var_178], r15; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x1800187c5  mov     [rsp+1B8h+var_180], rsi; struct _CRYPT_CONTEXT_CONFIG *
0x1800187ca  mov     [rsp+1B8h+var_188], r15d; unsigned int
0x1800187cf  mov     [rsp+1B8h+var_190], r15; unsigned __int16 *
0x1800187d4  mov     [rsp+1B8h+var_198], r15; Src
0x1800187d9  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x1800187de  test    eax, eax
0x1800187e0  jnz     short loc_180018801
0x1800187e2  xor     r9d, r9d; unsigned __int8 *
0x1800187e5  mov     [rsp+1B8h+var_198], r15; unsigned int *
0x1800187ea  mov     r8d, edi; unsigned int
0x1800187ed  mov     rdx, rbx; unsigned __int8 *
0x1800187f0  mov     ecx, 10003h; unsigned int
0x1800187f5  call    ?IoCallKernelDriver@@YAJKPEAEK0PEAK@Z; IoCallKernelDriver(ulong,uchar *,ulong,uchar *,ulong *)
0x1800187fa  jmp     short loc_180018808
0x1800187fc  mov     eax, 57h ; 'W'
0x180018801  mov     ecx, eax; Status
0x180018803  call    ?WinErrorToNtStatus@@YAJK@Z; WinErrorToNtStatus(ulong)
0x180018808  mov     edi, eax
0x18001880a  test    rbx, rbx
0x18001880d  jz      short loc_180018824
0x18001880f  lea     rax, [rsp+1B8h+var_138]
0x180018817  cmp     rbx, rax
0x18001881a  jz      short loc_180018824
0x18001881c  mov     rcx, rbx
0x18001881f  call    BCryptFree
0x180018824  mov     eax, edi
0x180018826  mov     rcx, [rsp+1B8h+var_38]
0x18001882e  xor     rcx, rsp; StackCookie
0x180018831  call    __security_check_cookie
0x180018836  mov     rbx, [rsp+1B8h+arg_18]
0x18001883e  add     rsp, 190h
0x180018845  pop     r15
0x180018847  pop     r14
0x180018849  pop     rdi
0x18001884a  pop     rsi
0x18001884b  pop     rbp
0x18001884c  retn
```
