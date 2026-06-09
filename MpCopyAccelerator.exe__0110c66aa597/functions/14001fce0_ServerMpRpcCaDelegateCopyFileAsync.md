# ServerMpRpcCaDelegateCopyFileAsync

- ea: `0x14001fce0`
- end: `0x14001fe38`
- name: `ServerMpRpcCaDelegateCopyFileAsync`
- size: `344`
- prototype: `unsigned int __fastcall(PRPC_ASYNC_STATE pAsync, RPC_BINDING_HANDLE BindingHandle, unsigned int, const WCHAR *, WCHAR *pwszNewFileName, DWORD, HRESULT *, DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140005c20`
- `0x14001da70`
- `0x14001eee0`
- `0x14001f6a0`
- `0x14001fce0`
- `0x140020800`
- `0x14002380c`
- `0x1400241f8`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x14001fdd8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14001fdd8`

## string_xrefs

- `0x14001fd6f`: `Copy Result - Async copy was triggered but the feature is disabled. Api (%ls), SourceFile (%ls), DestinationFile (%ls)\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall ServerMpRpcCaDelegateCopyFileAsync(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        unsigned int a3,
        const WCHAR *a4,
        WCHAR *pwszNewFileName,
        DWORD a6,
        HRESULT *a7,
        DWORD *a8,
        _DWORD *a9)
{
  const wchar_t *v10; // rdi
  __int64 v14; // rdx
  int v15; // eax
  unsigned int result; // eax
  __int128 v17; // [rsp+40h] [rbp-58h] BYREF
  unsigned int Reply; // [rsp+50h] [rbp-48h] BYREF

  v10 = pwszNewFileName;
  *a9 = 0;
  if ( *(_BYTE *)CopyAcceleratorFeatures::GetInstance() )
  {
    v15 = ServerMpRpcCaDelegateCopyFileImpl(BindingHandle, v14, a3, a4, pwszNewFileName, a6, a7, a8);
  }
  else
  {
    if ( dword_14003DB98 )
    {
      v17 = 0;
      MpCopyFileApiToStr(&v17, a3);
      if ( dword_14003DB98 )
      {
        if ( !pwszNewFileName )
          v10 = L"-";
        if ( !a4 )
          a4 = L"-";
        MpCmdLogWithTimePrintf(
          L"Copy Result - Async copy was triggered but the feature is disabled. Api (%ls), SourceFile (%ls), DestinationFile (%ls)\n",
          (_QWORD)v17,
          a4,
          v10);
        if ( qword_14003DBC8 )
          CLogHandle::Flush(qword_14003DBC8);
      }
    }
    v15 = -2147024891;
  }
  Reply = v15;
  result = RpcAsyncCompleteCall(pAsync, &Reply);
  if ( result )
  {
    result |= 0x80010000;
    Reply = result;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      return WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids, result);
  }
  return result;
}

```

## disassembly

```asm
0x14001fce0  push    rbx
0x14001fce2  push    rbp
0x14001fce3  push    rsi
0x14001fce4  push    rdi
0x14001fce5  push    r12
0x14001fce7  push    r14
0x14001fce9  push    r15
0x14001fceb  sub     rsp, 60h
0x14001fcef  mov     rax, cs:__security_cookie
0x14001fcf6  xor     rax, rsp
0x14001fcf9  mov     [rsp+98h+var_40], rax
0x14001fcfe  mov     rax, [rsp+98h+arg_40]
0x14001fd06  mov     rbx, r9
0x14001fd09  mov     rdi, [rsp+98h+arg_20]
0x14001fd11  mov     esi, r8d
0x14001fd14  mov     r15, [rsp+98h+arg_30]
0x14001fd1c  mov     r14, rdx
0x14001fd1f  mov     r12, [rsp+98h+arg_38]
0x14001fd27  mov     rbp, rcx
0x14001fd2a  mov     dword ptr [rax], 0
0x14001fd30  call    ?GetInstance@CopyAcceleratorFeatures@@SAAEAV1@XZ; CopyAcceleratorFeatures::GetInstance(void)
0x14001fd35  cmp     byte ptr [rax], 0
0x14001fd38  jnz     short loc_14001FDA4
0x14001fd3a  cmp     cs:dword_14003DB98, 0
0x14001fd41  jz      short loc_14001FD9D
0x14001fd43  xorps   xmm0, xmm0
0x14001fd46  lea     rcx, [rsp+98h+var_58]
0x14001fd4b  mov     edx, esi
0x14001fd4d  movups  [rsp+98h+var_58], xmm0
0x14001fd52  call    MpCopyFileApiToStr
0x14001fd57  cmp     cs:dword_14003DB98, 0
0x14001fd5e  jz      short loc_14001FD9D
0x14001fd60  mov     rdx, qword ptr [rsp+98h+var_58]
0x14001fd65  lea     rax, asc_140034698; "-"
0x14001fd6c  test    rdi, rdi
0x14001fd6f  lea     rcx, aCopyResultAsyn; "Copy Result - Async copy was triggered "...
0x14001fd76  cmovz   rdi, rax
0x14001fd7a  test    rbx, rbx
0x14001fd7d  mov     r9, rdi
0x14001fd80  cmovz   rbx, rax
0x14001fd84  mov     r8, rbx
0x14001fd87  call    ?MpCmdLogWithTimePrintf@@YAXPEB_WZZ; MpCmdLogWithTimePrintf(wchar_t const *,...)
0x14001fd8c  mov     rcx, cs:qword_14003DBC8; this
0x14001fd93  test    rcx, rcx
0x14001fd96  jz      short loc_14001FD9D
0x14001fd98  call    ?Flush@CLogHandle@@QEAAJXZ; CLogHandle::Flush(void)
0x14001fd9d  mov     eax, 80070005h
0x14001fda2  jmp     short loc_14001FDCC
0x14001fda4  mov     eax, [rsp+98h+arg_28]
0x14001fdab  mov     r9, rbx
0x14001fdae  mov     [rsp+98h+var_60], r12; __int64
0x14001fdb3  mov     r8d, esi
0x14001fdb6  mov     [rsp+98h+var_68], r15; __int64
0x14001fdbb  mov     rcx, r14; BindingHandle
0x14001fdbe  mov     [rsp+98h+var_70], eax; DWORD
0x14001fdc2  mov     [rsp+98h+pwszNewFileName], rdi; pwszNewFileName
0x14001fdc7  call    ServerMpRpcCaDelegateCopyFileImpl
0x14001fdcc  lea     rdx, [rsp+98h+Reply]; Reply
0x14001fdd1  mov     [rsp+98h+Reply], eax
0x14001fdd5  mov     rcx, rbp; pAsync
0x14001fdd8  call    cs:__imp_RpcAsyncCompleteCall
0x14001fdde  test    eax, eax
0x14001fde0  jz      short loc_14001FE1C
0x14001fde2  or      eax, 80010000h
0x14001fde7  mov     [rsp+98h+Reply], eax
0x14001fdeb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fdf2  lea     rdx, WPP_GLOBAL_Control
0x14001fdf9  cmp     rcx, rdx
0x14001fdfc  jz      short loc_14001FE1C
0x14001fdfe  test    byte ptr [rcx+1Ch], 1
0x14001fe02  jz      short loc_14001FE1C
0x14001fe04  mov     rcx, [rcx+10h]
0x14001fe08  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001fe0f  mov     edx, 29h ; ')'
0x14001fe14  mov     r9d, eax
0x14001fe17  call    WPP_SF_d
0x14001fe1c  mov     rcx, [rsp+98h+var_40]
0x14001fe21  xor     rcx, rsp; StackCookie
0x14001fe24  call    __security_check_cookie
0x14001fe29  add     rsp, 60h
0x14001fe2d  pop     r15
0x14001fe2f  pop     r14
0x14001fe31  pop     r12
0x14001fe33  pop     rdi
0x14001fe34  pop     rsi
0x14001fe35  pop     rbp
0x14001fe36  pop     rbx
0x14001fe37  retn
```
