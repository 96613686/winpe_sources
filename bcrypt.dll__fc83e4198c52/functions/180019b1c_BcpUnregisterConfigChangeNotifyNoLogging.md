# BcpUnregisterConfigChangeNotifyNoLogging

- ea: `0x180019b1c`
- end: `0x180019ca7`
- name: `BcpUnregisterConfigChangeNotifyNoLogging`
- size: `395`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001267c`
- `0x180019920`

## callees

- `0x180002040`
- `0x18000283c`
- `0x180003860`
- `0x1800041d0`
- `0x180004200`
- `0x18000b094`
- `0x180019b1c`
- `0x18001b7a9`
- `0x18001b7e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c62`

## pseudocode

```c
__int64 __fastcall BcpUnregisterConfigChangeNotifyNoLogging(void *a1)
{
  unsigned __int8 *v2; // rbx
  NTSTATUS v3; // eax
  NTSTATUS v4; // edi
  char TrustedEnvironment; // al
  unsigned int v6; // edi
  size_t Size; // [rsp+48h] [rbp-F0h]
  size_t Sizea; // [rsp+48h] [rbp-F0h]
  unsigned int v10[4]; // [rsp+70h] [rbp-C8h] BYREF
  unsigned __int8 v11[128]; // [rsp+80h] [rbp-B8h] BYREF

  memset_0(v11, 0, sizeof(v11));
  v2 = v11;
  v10[0] = 0;
  if ( a1 )
  {
    TrustedEnvironment = g_TrustedEnvironment;
    v4 = 0;
    if ( !g_TrustedEnvironment )
      TrustedEnvironment = GetTrustedEnvironment();
    if ( (TrustedEnvironment & 1) != 0 )
    {
      LODWORD(Size) = 0;
      v3 = IoPack_Configuration_ParamBlock(0, 0, 0, 0, 0, 0, 0, 0, 0, Size, 0, a1, v10, 0);
      if ( v3 )
        goto LABEL_3;
      v6 = v10[0];
      if ( v10[0] > 0x80 )
      {
        v2 = (unsigned __int8 *)SafeAllocaAllocateFromHeap(v10[0]);
        if ( !v2 )
        {
          v3 = 8;
          goto LABEL_3;
        }
      }
      LODWORD(Sizea) = 0;
      v3 = IoPack_Configuration_ParamBlock(0, 0, 0, 0, 0, 0, 0, 0, 0, Sizea, 0, a1, 0, v2);
      if ( v3 )
        goto LABEL_3;
      v4 = IoCallKernelDriver(66817, v2, v6, 0, 0);
      if ( v4 < 0 )
        goto LABEL_14;
    }
    CloseHandle(a1);
    goto LABEL_14;
  }
  v3 = 87;
LABEL_3:
  v4 = WinErrorToNtStatus(v3);
LABEL_14:
  if ( v2 && v2 != v11 )
    BCryptFree(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180019b1c  push    rbx
0x180019b1e  push    rbp
0x180019b1f  push    rsi
0x180019b20  push    rdi
0x180019b21  sub     rsp, 118h
0x180019b28  mov     rax, cs:__security_cookie
0x180019b2f  xor     rax, rsp
0x180019b32  mov     [rsp+138h+var_38], rax
0x180019b3a  mov     rsi, rcx
0x180019b3d  xor     edx, edx; Val
0x180019b3f  lea     rcx, [rsp+138h+var_B8]; void *
0x180019b47  mov     r8d, 80h; Size
0x180019b4d  call    memset_0
0x180019b52  xor     ebp, ebp
0x180019b54  lea     rbx, [rsp+138h+var_B8]
0x180019b5c  mov     [rsp+138h+var_C8], ebp
0x180019b60  test    rsi, rsi
0x180019b63  jnz     short loc_180019B76
0x180019b65  lea     eax, [rbp+57h]
0x180019b68  mov     ecx, eax; Status
0x180019b6a  call    ?WinErrorToNtStatus@@YAJK@Z; WinErrorToNtStatus(ulong)
0x180019b6f  mov     edi, eax
0x180019b71  jmp     loc_180019C6E
0x180019b76  mov     eax, cs:g_TrustedEnvironment
0x180019b7c  mov     edi, ebp
0x180019b7e  test    eax, eax
0x180019b80  jnz     short loc_180019B87
0x180019b82  call    GetTrustedEnvironment
0x180019b87  test    al, 1
0x180019b89  jz      loc_180019C5F
0x180019b8f  mov     [rsp+138h+var_D0], rbp; unsigned __int8 *
0x180019b94  lea     rax, [rsp+138h+var_C8]
0x180019b99  mov     [rsp+138h+var_D8], rax; unsigned int *
0x180019b9e  xor     r9d, r9d; unsigned __int16 *
0x180019ba1  mov     [rsp+138h+var_E0], rsi; void *
0x180019ba6  xor     r8d, r8d; unsigned int
0x180019ba9  mov     [rsp+138h+var_E8], rbp; unsigned __int8 *
0x180019bae  xor     edx, edx; unsigned __int16 *
0x180019bb0  mov     dword ptr [rsp+138h+Size], ebp; Size
0x180019bb4  xor     ecx, ecx; unsigned int
0x180019bb6  mov     [rsp+138h+var_F8], rbp; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x180019bbb  mov     [rsp+138h+var_100], rbp; struct _CRYPT_CONTEXT_CONFIG *
0x180019bc0  mov     [rsp+138h+var_108], ebp; unsigned int
0x180019bc4  mov     [rsp+138h+var_110], rbp; unsigned __int16 *
0x180019bc9  mov     [rsp+138h+var_118], rbp; Src
0x180019bce  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x180019bd3  test    eax, eax
0x180019bd5  jnz     short loc_180019B68
0x180019bd7  mov     edi, [rsp+138h+var_C8]
0x180019bdb  cmp     edi, 80h
0x180019be1  jbe     short loc_180019BFA
0x180019be3  mov     ecx, edi
0x180019be5  call    SafeAllocaAllocateFromHeap
0x180019bea  mov     rbx, rax
0x180019bed  test    rax, rax
0x180019bf0  jnz     short loc_180019BFA
0x180019bf2  lea     eax, [rbx+8]
0x180019bf5  jmp     loc_180019B68
0x180019bfa  mov     [rsp+138h+var_D0], rbx; unsigned __int8 *
0x180019bff  xor     r9d, r9d; unsigned __int16 *
0x180019c02  mov     [rsp+138h+var_D8], rbp; unsigned int *
0x180019c07  xor     r8d, r8d; unsigned int
0x180019c0a  mov     [rsp+138h+var_E0], rsi; void *
0x180019c0f  xor     edx, edx; unsigned __int16 *
0x180019c11  mov     [rsp+138h+var_E8], rbp; unsigned __int8 *
0x180019c16  xor     ecx, ecx; unsigned int
0x180019c18  mov     dword ptr [rsp+138h+Size], ebp; Size
0x180019c1c  mov     [rsp+138h+var_F8], rbp; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x180019c21  mov     [rsp+138h+var_100], rbp; struct _CRYPT_CONTEXT_CONFIG *
0x180019c26  mov     [rsp+138h+var_108], ebp; unsigned int
0x180019c2a  mov     [rsp+138h+var_110], rbp; unsigned __int16 *
0x180019c2f  mov     [rsp+138h+var_118], rbp; Src
0x180019c34  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x180019c39  test    eax, eax
0x180019c3b  jnz     loc_180019B68
0x180019c41  xor     r9d, r9d; unsigned __int8 *
0x180019c44  mov     [rsp+138h+var_118], rbp; unsigned int *
0x180019c49  mov     r8d, edi; unsigned int
0x180019c4c  mov     rdx, rbx; unsigned __int8 *
0x180019c4f  mov     ecx, 10501h; unsigned int
0x180019c54  call    ?IoCallKernelDriver@@YAJKPEAEK0PEAK@Z; IoCallKernelDriver(ulong,uchar *,ulong,uchar *,ulong *)
0x180019c59  mov     edi, eax
0x180019c5b  test    eax, eax
0x180019c5d  js      short loc_180019C6E
0x180019c5f  mov     rcx, rsi; hObject
0x180019c62  call    cs:__imp_CloseHandle
0x180019c69  nop     dword ptr [rax+rax+00h]
0x180019c6e  test    rbx, rbx
0x180019c71  jz      short loc_180019C88
0x180019c73  lea     rax, [rsp+138h+var_B8]
0x180019c7b  cmp     rbx, rax
0x180019c7e  jz      short loc_180019C88
0x180019c80  mov     rcx, rbx
0x180019c83  call    BCryptFree
0x180019c88  mov     eax, edi
0x180019c8a  mov     rcx, [rsp+138h+var_38]
0x180019c92  xor     rcx, rsp; StackCookie
0x180019c95  call    __security_check_cookie
0x180019c9a  add     rsp, 118h
0x180019ca1  pop     rdi
0x180019ca2  pop     rsi
0x180019ca3  pop     rbp
0x180019ca4  pop     rbx
0x180019ca5  retn
```
