# WfpMidlObjectDecode

- ea: `0x18000ebf0`
- end: `0x18000ecdc`
- name: `WfpMidlObjectDecode`
- size: `236`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d6e0`
- `0x18000e250`
- `0x18000e870`
- `0x18000ea30`
- `0x1800305e0`
- `0x18003609c`

## callees

- `0x18000ebf0`
- `0x180012d8c`
- `0x1800135ac`
- `0x1800197d0`
- `0x18008e010`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x18000ec6d`
- `RPCRT4!MesHandleFree` at `0x18000ec6d`
- `RPCRT4!I_RpcExceptionFilter` at `0x18008adfe`
- `RPCRT4!I_RpcExceptionFilter` at `0x18008adfe`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18000ec23`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18000ec23`

## string_xrefs

- `0x18000ec8f`: `MesDecodeBufferHandleCreate`

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
0x18000ebf0  mov     [rsp+arg_18], r9
0x18000ebf5  push    rbx
0x18000ebf6  push    rsi
0x18000ebf7  push    rdi
0x18000ebf8  push    r14
0x18000ebfa  sub     rsp, 38h
0x18000ebfe  mov     rdi, r9
0x18000ec01  mov     eax, r8d
0x18000ec04  mov     r10, rdx
0x18000ec07  mov     r14, rcx
0x18000ec0a  xor     ebx, ebx
0x18000ec0c  mov     [rsp+58h+var_30], rbx
0x18000ec11  mov     [rsp+58h+pHandle], rbx
0x18000ec16  mov     [r9], rbx
0x18000ec19  lea     r8, [rsp+58h+pHandle]; pHandle
0x18000ec1e  mov     edx, eax; BufferSize
0x18000ec20  mov     rcx, r10; Buffer
0x18000ec23  call    cs:__imp_MesDecodeBufferHandleCreate
0x18000ec2a  nop     dword ptr [rax+rax+00h]
0x18000ec2f  mov     esi, eax
0x18000ec31  test    eax, eax
0x18000ec33  jnz     short loc_18000EC8C
0x18000ec35  lea     rdx, [rsp+58h+var_30]
0x18000ec3a  mov     rcx, [rsp+58h+pHandle]
0x18000ec3f  mov     rax, r14
0x18000ec42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec47  jmp     short loc_18000EC52
0x18000ec49  mov     esi, eax
0x18000ec4b  xor     ebx, ebx
0x18000ec4d  mov     rdi, [rsp+58h+arg_18]
0x18000ec52  test    esi, esi
0x18000ec54  jnz     short loc_18000ECA0
0x18000ec56  mov     rax, [rsp+58h+var_30]
0x18000ec5b  test    rax, rax
0x18000ec5e  jz      short loc_18000ECB4
0x18000ec60  mov     [rdi], rax
0x18000ec63  mov     rcx, [rsp+58h+pHandle]; Handle
0x18000ec68  test    rcx, rcx
0x18000ec6b  jz      short loc_18000EC79
0x18000ec6d  call    cs:__imp_MesHandleFree
0x18000ec74  nop     dword ptr [rax+rax+00h]
0x18000ec79  test    rbx, rbx
0x18000ec7c  jnz     short loc_18000ECCB
0x18000ec7e  mov     rax, rbx
0x18000ec81  add     rsp, 38h
0x18000ec85  pop     r14
0x18000ec87  pop     rdi
0x18000ec88  pop     rsi
0x18000ec89  pop     rbx
0x18000ec8a  retn
0x18000ec8c  mov     r8d, eax
0x18000ec8f  lea     rdx, aMesdecodebuffe; "MesDecodeBufferHandleCreate"
0x18000ec96  call    WfpReportSysErrorAsWinError
0x18000ec9b  mov     rbx, rax
0x18000ec9e  jmp     short loc_18000EC63
0x18000eca0  mov     r8d, esi
0x18000eca3  lea     rdx, aWfpMidlDecodeF; "WFP_MIDL_DECODE_FN"
0x18000ecaa  call    WfpReportSysErrorAsWinError
0x18000ecaf  mov     rbx, rax
0x18000ecb2  jmp     short loc_18000EC63
0x18000ecb4  mov     r8d, 0C0000017h
0x18000ecba  lea     rdx, aWfpmidlobjectd; "WfpMidlObjectDecode"
0x18000ecc1  call    WfpReportSysErrorAsNtStatus
0x18000ecc6  mov     rbx, rax
0x18000ecc9  jmp     short loc_18000EC63
0x18000eccb  lea     rdx, aWfpmidlobjectd; "WfpMidlObjectDecode"
0x18000ecd2  mov     rcx, rbx
0x18000ecd5  call    WfpReportError
0x18000ecda  jmp     short loc_18000EC7E
0x18008adf0  push    rbp
0x18008adf2  sub     rsp, 20h
0x18008adf6  mov     rbp, rdx
0x18008adf9  mov     rcx, [rcx]
0x18008adfc  mov     ecx, [rcx]; ExceptionCode
0x18008adfe  call    cs:__imp_I_RpcExceptionFilter
0x18008ae05  nop     dword ptr [rax+rax+00h]
0x18008ae0a  nop
0x18008ae0b  add     rsp, 20h
0x18008ae0f  pop     rbp
0x18008ae10  retn
```
