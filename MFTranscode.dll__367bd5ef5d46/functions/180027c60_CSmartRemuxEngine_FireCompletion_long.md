# CSmartRemuxEngine::_FireCompletion(long)

- ea: `0x180027c60`
- end: `0x180027cd9`
- name: `?_FireCompletion@CSmartRemuxEngine@@IEAAXJ@Z`
- size: `121`
- prototype: `void __fastcall(CSmartRemuxEngine *__hidden this, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001d100`
- `0x18001eed8`
- `0x18001f5b8`
- `0x1800287fc`

## callees

- `0x18000a3f4`
- `0x18001ce18`
- `0x180027c60`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFPutWorkItemEx` at `0x180027cb4`
- `MFPlat!MFPutWorkItemEx` at `0x180027cb4`
- `MFPlat!MFCreateAsyncResult` at `0x180027c89`
- `MFPlat!MFCreateAsyncResult` at `0x180027c89`

## pseudocode

```c
void __fastcall CSmartRemuxEngine::_FireCompletion(IUnknown *this, unsigned int a2)
{
  IUnknown *v2; // rbx
  IMFAsyncCallback *lpVtbl; // rdx
  IMFAsyncResult *ppAsyncResult; // [rsp+30h] [rbp+8h] BYREF

  v2 = this + 2;
  lpVtbl = (IMFAsyncCallback *)this[2].lpVtbl;
  if ( lpVtbl )
  {
    ppAsyncResult = 0;
    if ( MFCreateAsyncResult(this, lpVtbl, 0, &ppAsyncResult) >= 0
      && ((int (__fastcall *)(IMFAsyncResult *, _QWORD))ppAsyncResult->lpVtbl->SetStatus)(ppAsyncResult, a2) >= 0 )
    {
      MFPutWorkItemEx(5u, ppAsyncResult);
    }
    ComSmartPtr<IMFStreamDescriptor>::operator=(v2, 0);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppAsyncResult);
  }
}

```

## disassembly

```asm
0x180027c60  mov     [rsp+arg_8], rbx
0x180027c65  push    rdi
0x180027c66  sub     rsp, 20h
0x180027c6a  lea     rbx, [rcx+10h]
0x180027c6e  mov     edi, edx
0x180027c70  mov     rdx, [rbx]; pCallback
0x180027c73  test    rdx, rdx
0x180027c76  jz      short loc_180027CCE
0x180027c78  lea     r9, [rsp+28h+ppAsyncResult]; ppAsyncResult
0x180027c7d  mov     [rsp+28h+ppAsyncResult], 0
0x180027c86  xor     r8d, r8d; punkState
0x180027c89  call    cs:__imp_MFCreateAsyncResult
0x180027c8f  test    eax, eax
0x180027c91  js      short loc_180027CBA
0x180027c93  mov     rcx, [rsp+28h+ppAsyncResult]
0x180027c98  mov     edx, edi
0x180027c9a  mov     rax, [rcx]
0x180027c9d  mov     rax, [rax+28h]
0x180027ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ca6  test    eax, eax
0x180027ca8  js      short loc_180027CBA
0x180027caa  mov     rdx, [rsp+28h+ppAsyncResult]; pResult
0x180027caf  mov     ecx, 5; dwQueue
0x180027cb4  call    cs:__imp_MFPutWorkItemEx
0x180027cba  xor     edx, edx
0x180027cbc  mov     rcx, rbx
0x180027cbf  call    ??4?$ComSmartPtr@UIMFStreamDescriptor@@@@QEAAPEAUIMFStreamDescriptor@@PEAU1@@Z; ComSmartPtr<IMFStreamDescriptor>::operator=(IMFStreamDescriptor *)
0x180027cc4  lea     rcx, [rsp+28h+ppAsyncResult]
0x180027cc9  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180027cce  mov     rbx, [rsp+28h+arg_8]
0x180027cd3  add     rsp, 20h
0x180027cd7  pop     rdi
0x180027cd8  retn
```
