# WfpMidlObjectEncode

- ea: `0x18000e4e0`
- end: `0x18000e5df`
- name: `WfpMidlObjectEncode`
- size: `255`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x180003a00`
- `0x180005830`
- `0x18000c960`
- `0x18000cfb0`
- `0x18000dab0`
- `0x18000e080`
- `0x18000e240`
- `0x180024a44`
- `0x180024f80`
- `0x1800379b0`
- `0x180072e38`

## callees

- `0x18000e000`
- `0x18000e4e0`
- `0x18001236c`
- `0x180018b74`
- `0x18008b010`

## import_xrefs

- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18000e524`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18000e524`
- `RPCRT4!MesHandleFree` at `0x18000e576`
- `RPCRT4!MesHandleFree` at `0x18000e576`
- `RPCRT4!I_RpcExceptionFilter` at `0x180087e8e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180087e8e`

## string_xrefs

- `0x18000e593`: `MesEncodeDynBufferHandleCreate`

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
0x18000e4e0  mov     rax, rsp
0x18000e4e3  push    rbx
0x18000e4e4  push    rsi
0x18000e4e5  push    rdi
0x18000e4e6  push    r14
0x18000e4e8  push    r15
0x18000e4ea  sub     rsp, 50h
0x18000e4ee  mov     rsi, r9
0x18000e4f1  mov     rdi, r8
0x18000e4f4  mov     r15, rcx
0x18000e4f7  mov     [rax-38h], rdx
0x18000e4fb  mov     [rsp+78h+var_30], r8
0x18000e500  mov     [rsp+78h+var_40], r9
0x18000e505  xor     ebx, ebx
0x18000e507  mov     [rax-50h], rbx
0x18000e50b  mov     [rax-58h], ebx
0x18000e50e  mov     [rax-48h], rbx
0x18000e512  mov     [r8], rbx
0x18000e515  mov     [r9], ebx
0x18000e518  lea     r8, [rax-48h]; pHandle
0x18000e51c  lea     rdx, [rax-58h]; pEncodedSize
0x18000e520  lea     rcx, [rax-50h]; pBuffer
0x18000e524  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18000e52a  mov     r14d, eax
0x18000e52d  test    eax, eax
0x18000e52f  jnz     short loc_18000E590
0x18000e531  lea     rdx, [rsp+78h+var_38]
0x18000e536  mov     rcx, [rsp+78h+Handle]
0x18000e53b  mov     rax, r15
0x18000e53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e543  jmp     short loc_18000E554
0x18000e545  mov     r14d, eax
0x18000e548  xor     ebx, ebx
0x18000e54a  mov     rdi, [rsp+78h+var_30]
0x18000e54f  mov     rsi, [rsp+78h+var_40]
0x18000e554  test    r14d, r14d
0x18000e557  jnz     short loc_18000E5A4
0x18000e559  mov     rax, [rsp+78h+var_50]
0x18000e55e  mov     [rdi], rax
0x18000e561  mov     eax, [rsp+78h+var_58]
0x18000e565  mov     [rsi], eax
0x18000e567  test    rbx, rbx
0x18000e56a  jnz     short loc_18000E5B8
0x18000e56c  mov     rcx, [rsp+78h+Handle]; Handle
0x18000e571  test    rcx, rcx
0x18000e574  jz      short loc_18000E57C
0x18000e576  call    cs:__imp_MesHandleFree
0x18000e57c  test    rbx, rbx
0x18000e57f  jnz     short loc_18000E5CE
0x18000e581  mov     rax, rbx
0x18000e584  add     rsp, 50h
0x18000e588  pop     r15
0x18000e58a  pop     r14
0x18000e58c  pop     rdi
0x18000e58d  pop     rsi
0x18000e58e  pop     rbx
0x18000e58f  retn
0x18000e590  mov     r8d, eax
0x18000e593  lea     rdx, aMesencodedynbu; "MesEncodeDynBufferHandleCreate"
0x18000e59a  call    WfpReportSysErrorAsWinError
0x18000e59f  mov     rbx, rax
0x18000e5a2  jmp     short loc_18000E567
0x18000e5a4  mov     r8d, r14d
0x18000e5a7  lea     rdx, aWfpMidlEncodeF; "WFP_MIDL_ENCODE_FN"
0x18000e5ae  call    WfpReportSysErrorAsWinError
0x18000e5b3  mov     rbx, rax
0x18000e5b6  jmp     short loc_18000E567
0x18000e5b8  mov     rax, [rsp+78h+var_50]
0x18000e5bd  mov     [rsp+78h+var_40], rax
0x18000e5c2  lea     rcx, [rsp+78h+var_40]
0x18000e5c7  call    WfpMemFree
0x18000e5cc  jmp     short loc_18000E56C
0x18000e5ce  lea     rdx, aWfpmidlobjecte; "WfpMidlObjectEncode"
0x18000e5d5  mov     rcx, rbx
0x18000e5d8  call    WfpReportError
0x18000e5dd  jmp     short loc_18000E581
0x180087e80  push    rbp
0x180087e82  sub     rsp, 20h
0x180087e86  mov     rbp, rdx
0x180087e89  mov     rcx, [rcx]
0x180087e8c  mov     ecx, [rcx]; ExceptionCode
0x180087e8e  call    cs:__imp_I_RpcExceptionFilter
0x180087e94  nop
0x180087e95  add     rsp, 20h
0x180087e99  pop     rbp
0x180087e9a  retn
```
