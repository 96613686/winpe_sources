# WfpMidlObjectEncode

- ea: `0x18000a2bc`
- end: `0x18000a3c4`
- name: `WfpMidlObjectEncode`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f1b8`

## callees

- `0x180008440`
- `0x18000a2bc`
- `0x18000c354`
- `0x18000c9b4`
- `0x180020400`

## import_xrefs

- `msrpc!I_RpcExceptionFilter` at `0x180020dcb`
- `msrpc!I_RpcExceptionFilter` at `0x180020dcb`
- `msrpc!MesEncodeDynBufferHandleCreate` at `0x18000a312`
- `msrpc!MesEncodeDynBufferHandleCreate` at `0x18000a312`
- `msrpc!MesHandleFree` at `0x18000a391`
- `msrpc!MesHandleFree` at `0x18000a391`

## string_xrefs

- `0x18000a327`: `MesEncodeDynBufferHandleCreate`

## pseudocode

```c
__int64 WfpMidlObjectEncode(void (__fastcall *a1)(_QWORD, __int64 *), ...)
{
  _DWORD *v1; // rsi
  _QWORD *v2; // r14
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rdi
  int v8; // [rsp+20h] [rbp-38h] BYREF
  void *v9; // [rsp+28h] [rbp-30h] BYREF
  _QWORD v10[5]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF
  va_list va; // [rsp+68h] [rbp+10h]
  _QWORD *v13; // [rsp+70h] [rbp+18h]
  _DWORD *v14; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v11 = va_arg(va1, _QWORD);
  v13 = va_arg(va1, _QWORD *);
  v14 = va_arg(va1, _DWORD *);
  v1 = v14;
  v2 = v13;
  v9 = 0;
  v8 = 0;
  v10[0] = 0;
  *v13 = 0;
  *v1 = 0;
  v4 = MesEncodeDynBufferHandleCreate(&v9, &v8, v10);
  if ( v4 )
  {
    v6 = WfpReportSysErrorAsWinError(v5, "MesEncodeDynBufferHandleCreate", v4);
  }
  else
  {
    a1(v10[0], (__int64 *)va);
    v6 = 0;
    *v2 = v9;
    *v1 = v8;
  }
  if ( v6 )
    FwppDeepFree_GUID(v9);
  if ( v10[0] )
    MesHandleFree();
  if ( v6 )
    WfpReportError(v6, (int)"WfpMidlObjectEncode");
  return v6;
}

```

## disassembly

```asm
0x18000a2bc  mov     rax, rsp
0x18000a2bf  mov     [rax+8], rsi
0x18000a2c3  mov     [rax+20h], r9
0x18000a2c7  mov     [rax+18h], r8
0x18000a2cb  mov     [rax+10h], rdx
0x18000a2cf  push    rdi
0x18000a2d0  push    r14
0x18000a2d2  push    r15
0x18000a2d4  sub     rsp, 40h
0x18000a2d8  mov     rsi, r9
0x18000a2db  mov     r14, r8
0x18000a2de  mov     r15, rcx
0x18000a2e1  mov     qword ptr [rax-30h], 0
0x18000a2e9  mov     dword ptr [rax-38h], 0
0x18000a2f0  mov     qword ptr [rax-28h], 0
0x18000a2f8  mov     qword ptr [r8], 0
0x18000a2ff  mov     dword ptr [r9], 0
0x18000a306  lea     r8, [rax-28h]
0x18000a30a  lea     rdx, [rax-38h]
0x18000a30e  lea     rcx, [rax-30h]
0x18000a312  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18000a319  nop     dword ptr [rax+rax+00h]
0x18000a31e  mov     edi, eax
0x18000a320  test    eax, eax
0x18000a322  jz      short loc_18000A338
0x18000a324  mov     r8d, eax
0x18000a327  lea     rdx, aMesencodedynbu; "MesEncodeDynBufferHandleCreate"
0x18000a32e  call    WfpReportSysErrorAsWinError
0x18000a333  mov     rdi, rax
0x18000a336  jmp     short loc_18000A378
0x18000a338  lea     rdx, [rsp+58h+arg_8]
0x18000a33d  mov     rcx, [rsp+58h+var_28]
0x18000a342  mov     rax, r15
0x18000a345  call    _guard_dispatch_icall
0x18000a34a  jmp     short loc_18000A358
0x18000a34c  mov     edi, eax
0x18000a34e  mov     rsi, [rsp+58h+arg_18]
0x18000a353  mov     r14, [rsp+58h+arg_10]
0x18000a358  test    edi, edi
0x18000a35a  jz      short loc_18000A368
0x18000a35c  mov     r8d, edi
0x18000a35f  lea     rdx, aWfpMidlEncodeF; "WFP_MIDL_ENCODE_FN"
0x18000a366  jmp     short loc_18000A32E
0x18000a368  xor     edi, edi
0x18000a36a  mov     rax, [rsp+58h+var_30]
0x18000a36f  mov     [r14], rax
0x18000a372  mov     eax, [rsp+58h+var_38]
0x18000a376  mov     [rsi], eax
0x18000a378  test    rdi, rdi
0x18000a37b  jz      short loc_18000A387
0x18000a37d  mov     rcx, [rsp+58h+var_30]
0x18000a382  call    FwppDeepFree_GUID
0x18000a387  mov     rcx, [rsp+58h+var_28]
0x18000a38c  test    rcx, rcx
0x18000a38f  jz      short loc_18000A39D
0x18000a391  call    cs:__imp_MesHandleFree
0x18000a398  nop     dword ptr [rax+rax+00h]
0x18000a39d  test    rdi, rdi
0x18000a3a0  jz      short loc_18000A3B1
0x18000a3a2  lea     rdx, aWfpmidlobjecte; "WfpMidlObjectEncode"
0x18000a3a9  mov     rcx, rdi
0x18000a3ac  call    WfpReportError
0x18000a3b1  mov     rax, rdi
0x18000a3b4  mov     rsi, [rsp+58h+arg_0]
0x18000a3b9  add     rsp, 40h
0x18000a3bd  pop     r15
0x18000a3bf  pop     r14
0x18000a3c1  pop     rdi
0x18000a3c2  retn
0x180020dbd  push    rbp
0x180020dbf  sub     rsp, 20h
0x180020dc3  mov     rbp, rdx
0x180020dc6  mov     rcx, [rcx]
0x180020dc9  mov     ecx, [rcx]; ExceptionCode
0x180020dcb  call    cs:__imp_I_RpcExceptionFilter
0x180020dd2  nop     dword ptr [rax+rax+00h]
0x180020dd7  nop
0x180020dd8  add     rsp, 20h
0x180020ddc  pop     rbp
0x180020ddd  retn
```
