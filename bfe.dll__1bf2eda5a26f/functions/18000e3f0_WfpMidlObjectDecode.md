# WfpMidlObjectDecode

- ea: `0x18000e3f0`
- end: `0x18000e4cf`
- name: `WfpMidlObjectDecode`
- size: `223`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x18000cfb0`
- `0x18000dab0`
- `0x18000e080`
- `0x18000e240`
- `0x18002eb1c`
- `0x1800379b0`

## callees

- `0x18000e3f0`
- `0x18001236c`
- `0x180012b54`
- `0x180018b74`
- `0x18008b010`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x18000e467`
- `RPCRT4!MesHandleFree` at `0x18000e467`
- `RPCRT4!I_RpcExceptionFilter` at `0x180087e5e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180087e5e`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18000e423`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18000e423`

## string_xrefs

- `0x18000e482`: `MesDecodeBufferHandleCreate`

## pseudocode

```c
__int64 __fastcall WfpMidlObjectDecode(
        void (__fastcall *a1)(handle_t, _QWORD *),
        char *a2,
        unsigned int a3,
        _QWORD *a4)
{
  __int64 v6; // rbx
  unsigned int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  handle_t pHandle; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v12[6]; // [rsp+28h] [rbp-30h] BYREF

  v6 = 0;
  v12[0] = 0;
  pHandle = 0;
  *a4 = 0;
  v7 = MesDecodeBufferHandleCreate(a2, a3, &pHandle);
  if ( v7 )
  {
    v6 = WfpReportSysErrorAsWinError(v8, "MesDecodeBufferHandleCreate", v7);
  }
  else
  {
    a1(pHandle, v12);
    if ( v12[0] )
      *a4 = v12[0];
    else
      v6 = WfpReportSysErrorAsNtStatus(v9, "WfpMidlObjectDecode", 3221225495LL);
  }
  if ( pHandle )
    MesHandleFree(pHandle);
  if ( v6 )
    WfpReportError(v6, "WfpMidlObjectDecode");
  return v6;
}

```

## disassembly

```asm
0x18000e3f0  mov     [rsp+arg_18], r9
0x18000e3f5  push    rbx
0x18000e3f6  push    rsi
0x18000e3f7  push    rdi
0x18000e3f8  push    r14
0x18000e3fa  sub     rsp, 38h
0x18000e3fe  mov     rdi, r9
0x18000e401  mov     eax, r8d
0x18000e404  mov     r10, rdx
0x18000e407  mov     r14, rcx
0x18000e40a  xor     ebx, ebx
0x18000e40c  mov     [rsp+58h+var_30], rbx
0x18000e411  mov     [rsp+58h+pHandle], rbx
0x18000e416  mov     [r9], rbx
0x18000e419  lea     r8, [rsp+58h+pHandle]; pHandle
0x18000e41e  mov     edx, eax; BufferSize
0x18000e420  mov     rcx, r10; Buffer
0x18000e423  call    cs:__imp_MesDecodeBufferHandleCreate
0x18000e429  mov     esi, eax
0x18000e42b  test    eax, eax
0x18000e42d  jnz     short loc_18000E47F
0x18000e42f  lea     rdx, [rsp+58h+var_30]
0x18000e434  mov     rcx, [rsp+58h+pHandle]
0x18000e439  mov     rax, r14
0x18000e43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e441  jmp     short loc_18000E44C
0x18000e443  mov     esi, eax
0x18000e445  xor     ebx, ebx
0x18000e447  mov     rdi, [rsp+58h+arg_18]
0x18000e44c  test    esi, esi
0x18000e44e  jnz     short loc_18000E493
0x18000e450  mov     rax, [rsp+58h+var_30]
0x18000e455  test    rax, rax
0x18000e458  jz      short loc_18000E4A7
0x18000e45a  mov     [rdi], rax
0x18000e45d  mov     rcx, [rsp+58h+pHandle]; Handle
0x18000e462  test    rcx, rcx
0x18000e465  jz      short loc_18000E46D
0x18000e467  call    cs:__imp_MesHandleFree
0x18000e46d  test    rbx, rbx
0x18000e470  jnz     short loc_18000E4BE
0x18000e472  mov     rax, rbx
0x18000e475  add     rsp, 38h
0x18000e479  pop     r14
0x18000e47b  pop     rdi
0x18000e47c  pop     rsi
0x18000e47d  pop     rbx
0x18000e47e  retn
0x18000e47f  mov     r8d, eax
0x18000e482  lea     rdx, aMesdecodebuffe; "MesDecodeBufferHandleCreate"
0x18000e489  call    WfpReportSysErrorAsWinError
0x18000e48e  mov     rbx, rax
0x18000e491  jmp     short loc_18000E45D
0x18000e493  mov     r8d, esi
0x18000e496  lea     rdx, aWfpMidlDecodeF; "WFP_MIDL_DECODE_FN"
0x18000e49d  call    WfpReportSysErrorAsWinError
0x18000e4a2  mov     rbx, rax
0x18000e4a5  jmp     short loc_18000E45D
0x18000e4a7  mov     r8d, 0C0000017h
0x18000e4ad  lea     rdx, aWfpmidlobjectd; "WfpMidlObjectDecode"
0x18000e4b4  call    WfpReportSysErrorAsNtStatus
0x18000e4b9  mov     rbx, rax
0x18000e4bc  jmp     short loc_18000E45D
0x18000e4be  lea     rdx, aWfpmidlobjectd; "WfpMidlObjectDecode"
0x18000e4c5  mov     rcx, rbx
0x18000e4c8  call    WfpReportError
0x18000e4cd  jmp     short loc_18000E472
0x180087e50  push    rbp
0x180087e52  sub     rsp, 20h
0x180087e56  mov     rbp, rdx
0x180087e59  mov     rcx, [rcx]
0x180087e5c  mov     ecx, [rcx]; ExceptionCode
0x180087e5e  call    cs:__imp_I_RpcExceptionFilter
0x180087e64  nop
0x180087e65  add     rsp, 20h
0x180087e69  pop     rbp
0x180087e6a  retn
```
