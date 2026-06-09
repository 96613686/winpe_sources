# FSVMServerStreamSession::InternalQueueVMEvent(void)

- ea: `0x1800d46b0`
- end: `0x1800d4783`
- name: `?InternalQueueVMEvent@FSVMServerStreamSession@@MEAAJXZ`
- size: `211`
- prototype: `__int64 __fastcall(FSVMServerStreamSession *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008cf0`
- `0x180009608`
- `0x1800d46b0`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreateAsyncResult` at `0x1800d46ff`
- `MFPlat!MFCreateAsyncResult` at `0x1800d46ff`
- `MFPlat!MFPutWaitingWorkItem` at `0x1800d472f`
- `MFPlat!MFPutWaitingWorkItem` at `0x1800d472f`

## pseudocode

```c
__int64 __fastcall FSVMServerStreamSession::InternalQueueVMEvent(FSVMServerStreamSession *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rcx
  void *v4; // rsi
  HRESULT v5; // eax
  __int64 v6; // rdx
  IMFAsyncResult *ppAsyncResult; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  v3 = *((_QWORD *)this + 17);
  if ( v3 )
  {
    v4 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 64LL))(v3);
    if ( v4 )
    {
      ppAsyncResult = 0;
      v5 = MFCreateAsyncResult(0, (IMFAsyncCallback *)this + 5, 0, &ppAsyncResult);
      v2 = v5;
      if ( v5 >= 0 )
      {
        v5 = MFPutWaitingWorkItem(v4, 1, ppAsyncResult, (MFWORKITEM_KEY *)this + 21);
        v2 = v5;
        if ( v5 >= 0 || !g_wppLevels )
          goto LABEL_10;
        v6 = 67;
      }
      else
      {
        if ( !g_wppLevels )
        {
LABEL_10:
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppAsyncResult);
          return v2;
        }
        v6 = 66;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_acda0c9d11ca3542551ba2894de7f2f4_Traceguids, this, v5);
      goto LABEL_10;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800d46b0  mov     [rsp+arg_8], rbx
0x1800d46b5  mov     [rsp+arg_10], rsi
0x1800d46ba  push    rdi
0x1800d46bb  sub     rsp, 30h
0x1800d46bf  mov     rdi, rcx
0x1800d46c2  xor     ebx, ebx
0x1800d46c4  mov     rcx, [rcx+88h]
0x1800d46cb  test    rcx, rcx
0x1800d46ce  jz      loc_1800D4771
0x1800d46d4  mov     rax, [rcx]
0x1800d46d7  mov     rax, [rax+40h]
0x1800d46db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d46e0  mov     rsi, rax
0x1800d46e3  test    rax, rax
0x1800d46e6  jz      loc_1800D4771
0x1800d46ec  lea     rdx, [rdi+28h]; pCallback
0x1800d46f0  mov     [rsp+38h+ppAsyncResult], rbx
0x1800d46f5  lea     r9, [rsp+38h+ppAsyncResult]; ppAsyncResult
0x1800d46fa  xor     r8d, r8d; punkState
0x1800d46fd  xor     ecx, ecx; punkObject
0x1800d46ff  call    cs:__imp_MFCreateAsyncResult
0x1800d4705  mov     ebx, eax
0x1800d4707  test    eax, eax
0x1800d4709  jns     short loc_1800D471B
0x1800d470b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d4712  jb      short loc_1800D4767
0x1800d4714  mov     edx, 42h ; 'B'
0x1800d4719  jmp     short loc_1800D4749
0x1800d471b  mov     r8, [rsp+38h+ppAsyncResult]; pResult
0x1800d4720  lea     r9, [rdi+0A8h]; pKey
0x1800d4727  mov     edx, 1; Priority
0x1800d472c  mov     rcx, rsi; hEvent
0x1800d472f  call    cs:__imp_MFPutWaitingWorkItem
0x1800d4735  mov     ebx, eax
0x1800d4737  test    eax, eax
0x1800d4739  jns     short loc_1800D4767
0x1800d473b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d4742  jb      short loc_1800D4767
0x1800d4744  mov     edx, 43h ; 'C'
0x1800d4749  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d4750  lea     r8, WPP_acda0c9d11ca3542551ba2894de7f2f4_Traceguids
0x1800d4757  mov     r9, rdi
0x1800d475a  mov     [rsp+38h+var_18], eax
0x1800d475e  mov     rcx, [rcx+10h]
0x1800d4762  call    WPP_SF_qD
0x1800d4767  lea     rcx, [rsp+38h+ppAsyncResult]; void *
0x1800d476c  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800d4771  mov     rsi, [rsp+38h+arg_10]
0x1800d4776  mov     eax, ebx
0x1800d4778  mov     rbx, [rsp+38h+arg_8]
0x1800d477d  add     rsp, 30h
0x1800d4781  pop     rdi
0x1800d4782  retn
```
