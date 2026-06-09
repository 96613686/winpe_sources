# CTranscodeEngine::_FireCompletion(long)

- ea: `0x18001190c`
- end: `0x180011988`
- name: `?_FireCompletion@CTranscodeEngine@@IEAAXJ@Z`
- size: `124`
- prototype: `void __fastcall(CTranscodeEngine *__hidden this, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004b2c`
- `0x1800118b0`
- `0x18002f120`
- `0x18002f158`

## callees

- `0x18000a3f4`
- `0x18001190c`
- `0x18001ce18`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFPutWorkItemEx` at `0x180011963`
- `MFPlat!MFPutWorkItemEx` at `0x180011963`
- `MFPlat!MFCreateAsyncResult` at `0x180011938`
- `MFPlat!MFCreateAsyncResult` at `0x180011938`

## pseudocode

```c
void __fastcall CTranscodeEngine::_FireCompletion(IUnknown *this, unsigned int a2)
{
  IUnknown *v2; // rbx
  IMFAsyncCallback *lpVtbl; // rdx
  IMFAsyncResult *ppAsyncResult; // [rsp+30h] [rbp+8h] BYREF

  v2 = this + 20;
  lpVtbl = (IMFAsyncCallback *)this[20].lpVtbl;
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
0x18001190c  mov     [rsp+arg_8], rbx
0x180011911  push    rdi
0x180011912  sub     rsp, 20h
0x180011916  lea     rbx, [rcx+0A0h]
0x18001191d  mov     edi, edx
0x18001191f  mov     rdx, [rbx]; pCallback
0x180011922  test    rdx, rdx
0x180011925  jz      short loc_18001197D
0x180011927  lea     r9, [rsp+28h+ppAsyncResult]; ppAsyncResult
0x18001192c  mov     [rsp+28h+ppAsyncResult], 0
0x180011935  xor     r8d, r8d; punkState
0x180011938  call    cs:__imp_MFCreateAsyncResult
0x18001193e  test    eax, eax
0x180011940  js      short loc_180011969
0x180011942  mov     rcx, [rsp+28h+ppAsyncResult]
0x180011947  mov     edx, edi
0x180011949  mov     rax, [rcx]
0x18001194c  mov     rax, [rax+28h]
0x180011950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011955  test    eax, eax
0x180011957  js      short loc_180011969
0x180011959  mov     rdx, [rsp+28h+ppAsyncResult]; pResult
0x18001195e  mov     ecx, 5; dwQueue
0x180011963  call    cs:__imp_MFPutWorkItemEx
0x180011969  xor     edx, edx
0x18001196b  mov     rcx, rbx
0x18001196e  call    ??4?$ComSmartPtr@UIMFStreamDescriptor@@@@QEAAPEAUIMFStreamDescriptor@@PEAU1@@Z; ComSmartPtr<IMFStreamDescriptor>::operator=(IMFStreamDescriptor *)
0x180011973  lea     rcx, [rsp+28h+ppAsyncResult]
0x180011978  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001197d  mov     rbx, [rsp+28h+arg_8]
0x180011982  add     rsp, 20h
0x180011986  pop     rdi
0x180011987  retn
```
