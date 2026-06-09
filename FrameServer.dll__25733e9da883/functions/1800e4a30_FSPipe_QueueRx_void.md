# FSPipe::QueueRx(void)

- ea: `0x1800e4a30`
- end: `0x1800e4b10`
- name: `?QueueRx@FSPipe@@MEAAJXZ`
- size: `224`
- prototype: `__int64 __fastcall(FSPipe *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008cf0`
- `0x180009608`
- `0x18001c84c`
- `0x1800e4a30`

## import_xrefs

- `MFPlat!MFCreateAsyncResult` at `0x1800e4a54`
- `MFPlat!MFCreateAsyncResult` at `0x1800e4a54`
- `MFPlat!MFPutWaitingWorkItem` at `0x1800e4a82`
- `MFPlat!MFPutWaitingWorkItem` at `0x1800e4a82`

## pseudocode

```c
__int64 __fastcall FSPipe::QueueRx(FSPipe *this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  IMFAsyncResult *ppAsyncResult; // [rsp+50h] [rbp+8h] BYREF

  ppAsyncResult = 0;
  v2 = MFCreateAsyncResult(0, (IMFAsyncCallback *)this + 1, 0, &ppAsyncResult);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_8;
    v4 = 21;
    goto LABEL_7;
  }
  v2 = MFPutWaitingWorkItem(*((HANDLE *)this + 14), 1, ppAsyncResult, (MFWORKITEM_KEY *)this + 15);
  v3 = v2;
  if ( v2 >= 0 )
    goto LABEL_10;
  if ( g_wppLevels )
  {
    v4 = 22;
LABEL_7:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, WPP_bf6ffc4ce26e3facbb7b5cf5ad7a4bf2_Traceguids, this, v2);
  }
LABEL_8:
  if ( byte_18010EC4D )
    WPP_SF_qDqd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      23,
      WPP_bf6ffc4ce26e3facbb7b5cf5ad7a4bf2_Traceguids,
      this,
      v3,
      *((_QWORD *)this + 10),
      *((_DWORD *)this + 24));
LABEL_10:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppAsyncResult);
  return v3;
}

```

## disassembly

```asm
0x1800e4a30  mov     [rsp+arg_8], rbx
0x1800e4a35  push    rdi
0x1800e4a36  sub     rsp, 40h
0x1800e4a3a  mov     rdi, rcx
0x1800e4a3d  mov     [rsp+48h+ppAsyncResult], 0
0x1800e4a46  lea     rdx, [rcx+8]; pCallback
0x1800e4a4a  xor     r8d, r8d; punkState
0x1800e4a4d  xor     ecx, ecx; punkObject
0x1800e4a4f  lea     r9, [rsp+48h+ppAsyncResult]; ppAsyncResult
0x1800e4a54  call    cs:__imp_MFCreateAsyncResult
0x1800e4a5a  mov     ebx, eax
0x1800e4a5c  test    eax, eax
0x1800e4a5e  jns     short loc_1800E4A70
0x1800e4a60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e4a67  jb      short loc_1800E4ABA
0x1800e4a69  mov     edx, 15h
0x1800e4a6e  jmp     short loc_1800E4A9C
0x1800e4a70  mov     r8, [rsp+48h+ppAsyncResult]; pResult
0x1800e4a75  lea     r9, [rdi+78h]; pKey
0x1800e4a79  mov     rcx, [rdi+70h]; hEvent
0x1800e4a7d  mov     edx, 1; Priority
0x1800e4a82  call    cs:__imp_MFPutWaitingWorkItem
0x1800e4a88  mov     ebx, eax
0x1800e4a8a  test    eax, eax
0x1800e4a8c  jns     short loc_1800E4AF9
0x1800e4a8e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e4a95  jb      short loc_1800E4ABA
0x1800e4a97  mov     edx, 16h
0x1800e4a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4aa3  lea     r8, WPP_bf6ffc4ce26e3facbb7b5cf5ad7a4bf2_Traceguids
0x1800e4aaa  mov     r9, rdi
0x1800e4aad  mov     [rsp+48h+var_28], eax
0x1800e4ab1  mov     rcx, [rcx+10h]
0x1800e4ab5  call    WPP_SF_qD
0x1800e4aba  cmp     cs:byte_18010EC4D, 1
0x1800e4ac1  jb      short loc_1800E4AF9
0x1800e4ac3  mov     eax, [rdi+60h]
0x1800e4ac6  lea     r8, WPP_bf6ffc4ce26e3facbb7b5cf5ad7a4bf2_Traceguids
0x1800e4acd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4ad4  mov     edx, 17h
0x1800e4ad9  mov     [rsp+48h+var_18], eax
0x1800e4add  mov     r9, rdi
0x1800e4ae0  mov     rax, [rdi+50h]
0x1800e4ae4  mov     [rsp+48h+var_20], rax
0x1800e4ae9  mov     rcx, [rcx+0D8h]
0x1800e4af0  mov     [rsp+48h+var_28], ebx
0x1800e4af4  call    WPP_SF_qDqd
0x1800e4af9  lea     rcx, [rsp+48h+ppAsyncResult]; void *
0x1800e4afe  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e4b03  mov     eax, ebx
0x1800e4b05  mov     rbx, [rsp+48h+arg_8]
0x1800e4b0a  add     rsp, 40h
0x1800e4b0e  pop     rdi
0x1800e4b0f  retn
```
