# WfpMidlObjectEncode

- ea: `0x18000ecf0`
- end: `0x18000edfc`
- name: `WfpMidlObjectEncode`
- size: `268`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x180003a20`
- `0x1800052c0`
- `0x18000d080`
- `0x18000d6e0`
- `0x18000e250`
- `0x18000e870`
- `0x18000ea30`
- `0x18001fee8`
- `0x180020690`
- `0x18003609c`
- `0x1800756e8`

## callees

- `0x18000e7e0`
- `0x18000ecf0`
- `0x180012d8c`
- `0x1800197d0`
- `0x18008e010`

## import_xrefs

- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18000ed34`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18000ed34`
- `RPCRT4!MesHandleFree` at `0x18000ed8c`
- `RPCRT4!MesHandleFree` at `0x18000ed8c`
- `RPCRT4!I_RpcExceptionFilter` at `0x18008ae2e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18008ae2e`

## string_xrefs

- `0x18000edb0`: `MesEncodeDynBufferHandleCreate`

## pseudocode

```c
__int64 __fastcall WfpMidlObjectEncode(void (__fastcall *a1)(handle_t, _QWORD *), __int64 a2, _QWORD *a3, char *a4)
{
  __int64 v7; // rbx
  unsigned int v8; // eax
  __int64 v9; // rcx
  unsigned int v11; // [rsp+20h] [rbp-58h] BYREF
  char *v12; // [rsp+28h] [rbp-50h] BYREF
  handle_t Handle; // [rsp+30h] [rbp-48h] BYREF
  char *v14; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v15[7]; // [rsp+40h] [rbp-38h] BYREF

  v15[0] = a2;
  v15[1] = a3;
  v14 = a4;
  v7 = 0;
  v12 = 0;
  v11 = 0;
  Handle = 0;
  *a3 = 0;
  *(_DWORD *)a4 = 0;
  v8 = MesEncodeDynBufferHandleCreate(&v12, &v11, &Handle);
  if ( v8 )
  {
    v7 = WfpReportSysErrorAsWinError(v9, "MesEncodeDynBufferHandleCreate", v8);
  }
  else
  {
    a1(Handle, v15);
    *a3 = v12;
    *(_DWORD *)a4 = v11;
  }
  if ( v7 )
  {
    v14 = v12;
    WfpMemFree(&v14);
  }
  if ( Handle )
    MesHandleFree(Handle);
  if ( v7 )
    WfpReportError(v7, "WfpMidlObjectEncode");
  return v7;
}

```

## disassembly

```asm
0x18000ecf0  mov     rax, rsp
0x18000ecf3  push    rbx
0x18000ecf4  push    rsi
0x18000ecf5  push    rdi
0x18000ecf6  push    r14
0x18000ecf8  push    r15
0x18000ecfa  sub     rsp, 50h
0x18000ecfe  mov     rsi, r9
0x18000ed01  mov     rdi, r8
0x18000ed04  mov     r15, rcx
0x18000ed07  mov     [rax-38h], rdx
0x18000ed0b  mov     [rsp+78h+var_30], r8
0x18000ed10  mov     [rsp+78h+var_40], r9
0x18000ed15  xor     ebx, ebx
0x18000ed17  mov     [rax-50h], rbx
0x18000ed1b  mov     [rax-58h], ebx
0x18000ed1e  mov     [rax-48h], rbx
0x18000ed22  mov     [r8], rbx
0x18000ed25  mov     [r9], ebx
0x18000ed28  lea     r8, [rax-48h]; pHandle
0x18000ed2c  lea     rdx, [rax-58h]; pEncodedSize
0x18000ed30  lea     rcx, [rax-50h]; pBuffer
0x18000ed34  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18000ed3b  nop     dword ptr [rax+rax+00h]
0x18000ed40  mov     r14d, eax
0x18000ed43  test    eax, eax
0x18000ed45  jnz     short loc_18000EDAD
0x18000ed47  lea     rdx, [rsp+78h+var_38]
0x18000ed4c  mov     rcx, [rsp+78h+Handle]
0x18000ed51  mov     rax, r15
0x18000ed54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed59  jmp     short loc_18000ED6A
0x18000ed5b  mov     r14d, eax
0x18000ed5e  xor     ebx, ebx
0x18000ed60  mov     rdi, [rsp+78h+var_30]
0x18000ed65  mov     rsi, [rsp+78h+var_40]
0x18000ed6a  test    r14d, r14d
0x18000ed6d  jnz     short loc_18000EDC1
0x18000ed6f  mov     rax, [rsp+78h+var_50]
0x18000ed74  mov     [rdi], rax
0x18000ed77  mov     eax, [rsp+78h+var_58]
0x18000ed7b  mov     [rsi], eax
0x18000ed7d  test    rbx, rbx
0x18000ed80  jnz     short loc_18000EDD5
0x18000ed82  mov     rcx, [rsp+78h+Handle]; Handle
0x18000ed87  test    rcx, rcx
0x18000ed8a  jz      short loc_18000ED98
0x18000ed8c  call    cs:__imp_MesHandleFree
0x18000ed93  nop     dword ptr [rax+rax+00h]
0x18000ed98  test    rbx, rbx
0x18000ed9b  jnz     short loc_18000EDEB
0x18000ed9d  mov     rax, rbx
0x18000eda0  add     rsp, 50h
0x18000eda4  pop     r15
0x18000eda6  pop     r14
0x18000eda8  pop     rdi
0x18000eda9  pop     rsi
0x18000edaa  pop     rbx
0x18000edab  retn
0x18000edad  mov     r8d, eax
0x18000edb0  lea     rdx, aMesencodedynbu; "MesEncodeDynBufferHandleCreate"
0x18000edb7  call    WfpReportSysErrorAsWinError
0x18000edbc  mov     rbx, rax
0x18000edbf  jmp     short loc_18000ED7D
0x18000edc1  mov     r8d, r14d
0x18000edc4  lea     rdx, aWfpMidlEncodeF; "WFP_MIDL_ENCODE_FN"
0x18000edcb  call    WfpReportSysErrorAsWinError
0x18000edd0  mov     rbx, rax
0x18000edd3  jmp     short loc_18000ED7D
0x18000edd5  mov     rax, [rsp+78h+var_50]
0x18000edda  mov     [rsp+78h+var_40], rax
0x18000eddf  lea     rcx, [rsp+78h+var_40]
0x18000ede4  call    WfpMemFree
0x18000ede9  jmp     short loc_18000ED82
0x18000edeb  lea     rdx, aWfpmidlobjecte; "WfpMidlObjectEncode"
0x18000edf2  mov     rcx, rbx
0x18000edf5  call    WfpReportError
0x18000edfa  jmp     short loc_18000ED9D
0x18008ae20  push    rbp
0x18008ae22  sub     rsp, 20h
0x18008ae26  mov     rbp, rdx
0x18008ae29  mov     rcx, [rcx]
0x18008ae2c  mov     ecx, [rcx]; ExceptionCode
0x18008ae2e  call    cs:__imp_I_RpcExceptionFilter
0x18008ae35  nop     dword ptr [rax+rax+00h]
0x18008ae3a  nop
0x18008ae3b  add     rsp, 20h
0x18008ae3f  pop     rbp
0x18008ae40  retn
```
