# `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyRedemptionResult *> *>(Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyRedemptionResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vector deleting destructor'(uint)

- ea: `0x18000f020`
- end: `0x18000f097`
- name: `??_ECompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAAPEAXI@Z`
- size: `119`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001e90`
- `0x1800086fc`
- `0x18000f020`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f038`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f038`

## pseudocode

```c
_QWORD *__fastcall `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyRedemptionResult *> *>'::`2'::CompletionDelegate::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  void *v4; // rcx
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = (void *)a1[7];
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v5, v6);
  *((_DWORD *)a1 + 11) = -1073741823;
  v7 = a1[4];
  if ( v7 )
  {
    a1[4] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000f020  mov     [rsp+arg_0], rbx
0x18000f025  push    rdi
0x18000f026  sub     rsp, 20h
0x18000f02a  mov     rbx, rcx
0x18000f02d  mov     edi, edx
0x18000f02f  mov     rcx, [rcx+38h]; hObject
0x18000f033  test    rcx, rcx
0x18000f036  jz      short loc_18000F042
0x18000f038  call    cs:__imp_CloseHandle
0x18000f03e  test    eax, eax
0x18000f040  jz      short loc_18000F087
0x18000f042  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18000f049  mov     rcx, [rbx+20h]
0x18000f04d  test    rcx, rcx
0x18000f050  jz      short loc_18000F066
0x18000f052  mov     qword ptr [rbx+20h], 0
0x18000f05a  mov     rax, [rcx]
0x18000f05d  mov     rax, [rax+10h]
0x18000f061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f066  test    dil, 1
0x18000f06a  jz      short loc_18000F079
0x18000f06c  mov     edx, 40h ; '@'; unsigned __int64
0x18000f071  mov     rcx, rbx; void *
0x18000f074  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f079  mov     rax, rbx
0x18000f07c  mov     rbx, [rsp+28h+arg_0]
0x18000f081  add     rsp, 20h
0x18000f085  pop     rdi
0x18000f086  retn
0x18000f087  mov     rcx, [rsp+28h]; this
0x18000f08c  mov     edx, 0A0Bh; void *
0x18000f091  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
