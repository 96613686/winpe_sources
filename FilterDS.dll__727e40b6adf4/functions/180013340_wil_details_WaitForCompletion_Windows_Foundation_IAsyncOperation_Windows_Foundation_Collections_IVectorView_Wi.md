# `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`scalar deleting destructor'(uint)

- ea: `0x180013340`
- end: `0x1800133b4`
- name: `??_GCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAAPEAXI@Z`
- size: `116`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006bb4`
- `0x180013340`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180013395`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013395`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013358`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013358`

## pseudocode

```c
__int64 __fastcall `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *>'::`2'::CompletionDelegate::`scalar deleting destructor'(
        __int64 a1,
        char a2)
{
  void *v4; // rcx
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *(void **)(a1 + 56);
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v5, v6);
  *(_DWORD *)(a1 + 44) = -1073741823;
  v7 = *(_QWORD *)(a1 + 32);
  if ( v7 )
  {
    *(_QWORD *)(a1 + 32) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  if ( (a2 & 1) != 0 )
    operator delete((void *)a1);
  return a1;
}

```

## disassembly

```asm
0x180013340  mov     [rsp+arg_0], rbx
0x180013345  push    rdi
0x180013346  sub     rsp, 20h
0x18001334a  mov     edi, edx
0x18001334c  mov     rbx, rcx
0x18001334f  mov     rcx, [rcx+38h]; hObject
0x180013353  test    rcx, rcx
0x180013356  jz      short loc_180013367
0x180013358  call    cs:__imp_CloseHandle
0x18001335e  mov     rcx, [rsp+28h]; this
0x180013363  test    eax, eax
0x180013365  jz      short loc_1800133A9
0x180013367  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18001336e  mov     rcx, [rbx+20h]
0x180013372  test    rcx, rcx
0x180013375  jz      short loc_18001338C
0x180013377  mov     qword ptr [rbx+20h], 0
0x18001337f  mov     rax, [rcx]
0x180013382  mov     rax, [rax+10h]
0x180013386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001338b  nop
0x18001338c  test    dil, 1
0x180013390  jz      short loc_18001339B
0x180013392  mov     rcx, rbx
0x180013395  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001339b  mov     rax, rbx
0x18001339e  mov     rbx, [rsp+28h+arg_0]
0x1800133a3  add     rsp, 20h
0x1800133a7  pop     rdi
0x1800133a8  retn
0x1800133a9  mov     edx, 0A0Bh; void *
0x1800133ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
