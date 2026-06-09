# WfpMidlObjectDecode

- ea: `0x18000c25c`
- end: `0x18000c34e`
- name: `WfpMidlObjectDecode`
- size: `242`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f1b8`
- `0x1800530f0`

## callees

- `0x180004904`
- `0x18000c25c`
- `0x18000c354`
- `0x18000c9b4`
- `0x180020400`

## import_xrefs

- `msrpc!I_RpcExceptionFilter` at `0x180020df3`
- `msrpc!I_RpcExceptionFilter` at `0x180020df3`
- `msrpc!MesHandleFree` at `0x18000c31a`
- `msrpc!MesHandleFree` at `0x18000c31a`
- `msrpc!MesDecodeBufferHandleCreate` at `0x18000c29c`
- `msrpc!MesDecodeBufferHandleCreate` at `0x18000c29c`

## string_xrefs

- `0x18000c2b1`: `MesDecodeBufferHandleCreate`

## pseudocode

```c
__int64 __fastcall WfpMidlObjectDecode(
        void (__fastcall *a1)(__int64, __int64 *),
        __int64 a2,
        unsigned int a3,
        _QWORD *a4)
{
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-18h] BYREF
  __int64 v13; // [rsp+28h] [rbp-10h] BYREF

  v13 = 0;
  v12 = 0;
  *a4 = 0;
  v6 = MesDecodeBufferHandleCreate(a2, a3, &v12);
  if ( v6 )
  {
    v8 = WfpReportSysErrorAsWinError(v7, "MesDecodeBufferHandleCreate", v6);
LABEL_3:
    v9 = v8;
    goto LABEL_7;
  }
  a1(v12, &v13);
  if ( !v13 )
  {
    v8 = WfpReportSysErrorAsNtStatus(v10, (int)"WfpMidlObjectDecode", -1073741801);
    goto LABEL_3;
  }
  v9 = 0;
  *a4 = v13;
LABEL_7:
  if ( v12 )
    MesHandleFree();
  if ( v9 )
    WfpReportError(v9, (int)"WfpMidlObjectDecode");
  return v9;
}

```

## disassembly

```asm
0x18000c25c  mov     r11, rsp
0x18000c25f  mov     [r11+8], rbx
0x18000c263  mov     [r11+10h], rsi
0x18000c267  mov     [r11+20h], r9
0x18000c26b  push    rdi
0x18000c26c  sub     rsp, 30h
0x18000c270  mov     rdi, r9
0x18000c273  mov     eax, r8d
0x18000c276  mov     r10, rdx
0x18000c279  mov     rsi, rcx
0x18000c27c  mov     qword ptr [r11-10h], 0
0x18000c284  mov     qword ptr [r11-18h], 0
0x18000c28c  mov     qword ptr [r9], 0
0x18000c293  lea     r8, [r11-18h]
0x18000c297  mov     edx, eax
0x18000c299  mov     rcx, r10
0x18000c29c  call    cs:__imp_MesDecodeBufferHandleCreate
0x18000c2a3  nop     dword ptr [rax+rax+00h]
0x18000c2a8  mov     ebx, eax
0x18000c2aa  test    eax, eax
0x18000c2ac  jz      short loc_18000C2C2
0x18000c2ae  mov     r8d, eax
0x18000c2b1  lea     rdx, aMesdecodebuffe; "MesDecodeBufferHandleCreate"
0x18000c2b8  call    WfpReportSysErrorAsWinError
0x18000c2bd  mov     rbx, rax
0x18000c2c0  jmp     short loc_18000C310
0x18000c2c2  lea     rdx, [rsp+38h+var_10]
0x18000c2c7  mov     rcx, [rsp+38h+var_18]
0x18000c2cc  mov     rax, rsi
0x18000c2cf  call    _guard_dispatch_icall
0x18000c2d4  jmp     short loc_18000C2DD
0x18000c2d6  mov     ebx, eax
0x18000c2d8  mov     rdi, [rsp+38h+arg_18]
0x18000c2dd  test    ebx, ebx
0x18000c2df  jz      short loc_18000C2ED
0x18000c2e1  mov     r8d, ebx
0x18000c2e4  lea     rdx, aWfpMidlDecodeF; "WFP_MIDL_DECODE_FN"
0x18000c2eb  jmp     short loc_18000C2B8
0x18000c2ed  mov     rax, [rsp+38h+var_10]
0x18000c2f2  test    rax, rax
0x18000c2f5  jnz     short loc_18000C30B
0x18000c2f7  mov     r8d, 0C0000017h
0x18000c2fd  lea     rdx, aWfpmidlobjectd; "WfpMidlObjectDecode"
0x18000c304  call    WfpReportSysErrorAsNtStatus
0x18000c309  jmp     short loc_18000C2BD
0x18000c30b  xor     ebx, ebx
0x18000c30d  mov     [rdi], rax
0x18000c310  mov     rcx, [rsp+38h+var_18]
0x18000c315  test    rcx, rcx
0x18000c318  jz      short loc_18000C326
0x18000c31a  call    cs:__imp_MesHandleFree
0x18000c321  nop     dword ptr [rax+rax+00h]
0x18000c326  test    rbx, rbx
0x18000c329  jz      short loc_18000C33A
0x18000c32b  lea     rdx, aWfpmidlobjectd; "WfpMidlObjectDecode"
0x18000c332  mov     rcx, rbx
0x18000c335  call    WfpReportError
0x18000c33a  mov     rax, rbx
0x18000c33d  mov     rbx, [rsp+38h+arg_0]
0x18000c342  mov     rsi, [rsp+38h+arg_8]
0x18000c347  add     rsp, 30h
0x18000c34b  pop     rdi
0x18000c34c  retn
0x180020de5  push    rbp
0x180020de7  sub     rsp, 20h
0x180020deb  mov     rbp, rdx
0x180020dee  mov     rcx, [rcx]
0x180020df1  mov     ecx, [rcx]; ExceptionCode
0x180020df3  call    cs:__imp_I_RpcExceptionFilter
0x180020dfa  nop     dword ptr [rax+rax+00h]
0x180020dff  nop
0x180020e00  add     rsp, 20h
0x180020e04  pop     rbp
0x180020e05  retn
```
