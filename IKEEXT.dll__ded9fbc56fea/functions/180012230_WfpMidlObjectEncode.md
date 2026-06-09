# WfpMidlObjectEncode

- ea: `0x180012230`
- end: `0x18001242a`
- name: `WfpMidlObjectEncode`
- size: `506`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180006910`
- `0x180012150`
- `0x180112cd0`

## callees

- `0x1800037c4`
- `0x1800061ec`
- `0x180010db0`
- `0x180011680`
- `0x180012230`
- `0x18004890c`
- `0x180050850`
- `0x1800528e4`
- `0x180119010`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18011802e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18011802e`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001228e`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001228e`
- `RPCRT4!MesHandleFree` at `0x1800122e6`
- `RPCRT4!MesHandleFree` at `0x1800122e6`

## string_xrefs

- `0x180012330`: `MesEncodeDynBufferHandleCreate`
- `0x1800123b1`: `MesEncodeDynBufferHandleCreate`

## pseudocode

```c
__int64 __fastcall WfpMidlObjectEncode(
        void (__fastcall *a1)(handle_t, __int64 *),
        __int64 a2,
        char **a3,
        unsigned int *a4)
{
  __int64 v7; // rbx
  int v8; // edi
  int v9; // r8d
  int TlsPeerAddr; // eax
  int v12; // edx
  int v13; // r8d
  unsigned int pEncodedSize; // [rsp+30h] [rbp-98h] BYREF
  char **v15; // [rsp+38h] [rbp-90h] BYREF
  char *pBuffer; // [rsp+40h] [rbp-88h] BYREF
  handle_t pHandle; // [rsp+48h] [rbp-80h] BYREF
  char *v18; // [rsp+50h] [rbp-78h] BYREF
  __int64 v19; // [rsp+58h] [rbp-70h] BYREF
  char v20[16]; // [rsp+60h] [rbp-68h] BYREF
  const char *v21; // [rsp+70h] [rbp-58h]
  __int64 v22; // [rsp+78h] [rbp-50h]
  char ***v23; // [rsp+80h] [rbp-48h]
  __int64 v24; // [rsp+88h] [rbp-40h]

  v19 = a2;
  v15 = a3;
  v18 = (char *)a4;
  v7 = 0;
  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  *a3 = 0;
  *a4 = 0;
  v8 = MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      TlsPeerAddr = IkeGetTlsPeerAddr(&WPP_GLOBAL_Control);
      WPP_SF_SsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        v13,
        TlsPeerAddr,
        (__int64)"MesEncodeDynBufferHandleCreate",
        v8);
    }
    if ( gWfpLogUserModeErrors && (byte_180178161 & 1) != 0 )
    {
      LODWORD(v15) = v8;
      v21 = "MesEncodeDynBufferHandleCreate";
      v22 = 31;
      v23 = &v15;
      v24 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v9,
        3,
        (__int64)v20);
    }
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v7 = v8;
  }
  else
  {
    a1(pHandle, &v19);
    *a3 = pBuffer;
    *a4 = pEncodedSize;
  }
  if ( v7 )
  {
    v18 = pBuffer;
    WfpMemFree(&v18);
  }
  if ( pHandle )
    MesHandleFree(pHandle);
  if ( v7 )
    WfpReportError(v7, "WfpMidlObjectEncode");
  return v7;
}

```

## disassembly

```asm
0x180012230  push    rbx
0x180012232  push    rsi
0x180012233  push    rdi
0x180012234  push    r14
0x180012236  push    r15
0x180012238  sub     rsp, 0A0h
0x18001223f  mov     rax, cs:__security_cookie
0x180012246  xor     rax, rsp
0x180012249  mov     [rsp+0C8h+var_38], rax
0x180012251  mov     r14, r9
0x180012254  mov     rsi, r8
0x180012257  mov     r15, rcx
0x18001225a  mov     [rsp+0C8h+var_70], rdx
0x18001225f  mov     [rsp+0C8h+var_90], r8
0x180012264  mov     [rsp+0C8h+var_78], r9
0x180012269  xor     ebx, ebx
0x18001226b  mov     [rsp+0C8h+pBuffer], rbx
0x180012270  mov     [rsp+0C8h+pEncodedSize], ebx
0x180012274  mov     [rsp+0C8h+pHandle], rbx
0x180012279  mov     [r8], rbx
0x18001227c  mov     [r9], ebx
0x18001227f  lea     r8, [rsp+0C8h+pHandle]; pHandle
0x180012284  lea     rdx, [rsp+0C8h+pEncodedSize]; pEncodedSize
0x180012289  lea     rcx, [rsp+0C8h+pBuffer]; pBuffer
0x18001228e  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x180012294  mov     edi, eax
0x180012296  test    eax, eax
0x180012298  jnz     short loc_180012317
0x18001229a  lea     rdx, [rsp+0C8h+var_70]
0x18001229f  mov     rcx, [rsp+0C8h+pHandle]
0x1800122a4  mov     rax, r15
0x1800122a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122ac  jmp     short loc_1800122BC
0x1800122ae  mov     edi, eax
0x1800122b0  xor     ebx, ebx
0x1800122b2  mov     rsi, [rsp+0C8h+var_90]
0x1800122b7  mov     r14, [rsp+0C8h+var_78]
0x1800122bc  test    edi, edi
0x1800122be  jnz     loc_1800123E0
0x1800122c4  mov     rax, [rsp+0C8h+pBuffer]
0x1800122c9  mov     [rsi], rax
0x1800122cc  mov     eax, [rsp+0C8h+pEncodedSize]
0x1800122d0  mov     [r14], eax
0x1800122d3  test    rbx, rbx
0x1800122d6  jnz     loc_1800123FD
0x1800122dc  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x1800122e1  test    rcx, rcx
0x1800122e4  jz      short loc_1800122EC
0x1800122e6  call    cs:__imp_MesHandleFree
0x1800122ec  test    rbx, rbx
0x1800122ef  jnz     loc_180012416
0x1800122f5  mov     rax, rbx
0x1800122f8  mov     rcx, [rsp+0C8h+var_38]
0x180012300  xor     rcx, rsp; StackCookie
0x180012303  call    __security_check_cookie
0x180012308  add     rsp, 0A0h
0x18001230f  pop     r15
0x180012311  pop     r14
0x180012313  pop     rdi
0x180012314  pop     rsi
0x180012315  pop     rbx
0x180012316  retn
0x180012317  lea     rcx, WPP_GLOBAL_Control
0x18001231e  mov     rax, cs:WPP_GLOBAL_Control
0x180012325  cmp     rax, rcx
0x180012328  jz      short loc_180012330
0x18001232a  cmp     byte ptr [rax+19h], 2
0x18001232e  jnb     short loc_1800123A2
0x180012330  lea     rsi, aMesencodedynbu; "MesEncodeDynBufferHandleCreate"
0x180012337  cmp     cs:gWfpLogUserModeErrors, ebx
0x18001233d  jz      short loc_180012396
0x18001233f  test    cs:byte_180178161, 1
0x180012346  jz      short loc_180012396
0x180012348  mov     dword ptr [rsp+0C8h+var_90], edi
0x18001234c  mov     [rsp+0C8h+var_58], rsi
0x180012351  mov     [rsp+0C8h+var_50], 1Fh
0x18001235a  lea     rax, [rsp+0C8h+var_90]
0x18001235f  mov     [rsp+0C8h+var_48], rax
0x180012367  mov     [rsp+0C8h+var_40], 4
0x180012373  lea     rax, [rsp+0C8h+var_68]
0x180012378  mov     [rsp+0C8h+var_A8], rax
0x18001237d  mov     r9d, 3
0x180012383  lea     rdx, WFP_USERMODE_ERROR
0x18001238a  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180012391  call    McGenEventWrite_EtwEventWriteTransfer
0x180012396  test    edi, edi
0x180012398  jg      short loc_1800123D5
0x18001239a  movsxd  rbx, edi
0x18001239d  jmp     loc_1800122D3
0x1800123a2  test    byte ptr [rax+1Ch], 1
0x1800123a6  jz      short loc_180012330
0x1800123a8  call    IkeGetTlsPeerAddr
0x1800123ad  mov     [rsp+0C8h+var_A0], edi
0x1800123b1  lea     rsi, aMesencodedynbu; "MesEncodeDynBufferHandleCreate"
0x1800123b8  mov     [rsp+0C8h+var_A8], rsi
0x1800123bd  mov     r9, rax
0x1800123c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123c7  mov     rcx, [rcx+10h]
0x1800123cb  call    WPP_SF_SsD
0x1800123d0  jmp     loc_180012337
0x1800123d5  movzx   edi, di
0x1800123d8  or      edi, 80070000h
0x1800123de  jmp     short loc_18001239A
0x1800123e0  mov     r9d, 1
0x1800123e6  mov     r8d, edi
0x1800123e9  lea     rdx, aWfpMidlEncodeF; "WFP_MIDL_ENCODE_FN"
0x1800123f0  call    WfpReportSysErrorAsWinError
0x1800123f5  mov     rbx, rax
0x1800123f8  jmp     loc_1800122D3
0x1800123fd  mov     rax, [rsp+0C8h+pBuffer]
0x180012402  mov     [rsp+0C8h+var_78], rax
0x180012407  lea     rcx, [rsp+0C8h+var_78]
0x18001240c  call    WfpMemFree
0x180012411  jmp     loc_1800122DC
0x180012416  lea     rdx, aWfpmidlobjecte; "WfpMidlObjectEncode"
0x18001241d  mov     rcx, rbx
0x180012420  call    WfpReportError
0x180012425  jmp     loc_1800122F5
0x180118020  push    rbp
0x180118022  sub     rsp, 30h
0x180118026  mov     rbp, rdx
0x180118029  mov     rcx, [rcx]
0x18011802c  mov     ecx, [rcx]; ExceptionCode
0x18011802e  call    cs:__imp_I_RpcExceptionFilter
0x180118034  nop
0x180118035  add     rsp, 30h
0x180118039  pop     rbp
0x18011803a  retn
```
