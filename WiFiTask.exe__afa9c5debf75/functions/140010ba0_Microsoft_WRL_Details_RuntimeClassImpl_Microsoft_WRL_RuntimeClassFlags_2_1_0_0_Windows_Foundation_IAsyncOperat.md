# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x140010ba0`
- end: `0x140010c01`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010c10`

## callees

- `0x140010ba0`
- `0x140012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 11);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 11, v2 - 1, v2) );
  v3 = v2 - 1;
  if ( (_DWORD)v2 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 32LL))(
        a1,
        1,
        v2,
        0x7FFFFFFF);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        *(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_,
        v2,
        v1);
  }
  return v3;
}

```

## disassembly

```asm
0x140010ba0  push    rbx
0x140010ba2  sub     rsp, 20h
0x140010ba6  mov     r9d, 7FFFFFFFh
0x140010bac  jmp     short loc_140010BBC
0x140010bae  lea     edx, [r8-1]
0x140010bb2  mov     eax, r8d
0x140010bb5  lock cmpxchg [rcx+2Ch], edx
0x140010bba  jz      short loc_140010BC5
0x140010bbc  mov     r8d, [rcx+2Ch]
0x140010bc0  cmp     r8d, r9d
0x140010bc3  jnz     short loc_140010BAE
0x140010bc5  lea     ebx, [r8-1]
0x140010bc9  test    ebx, ebx
0x140010bcb  jnz     short loc_140010BF9
0x140010bcd  test    rcx, rcx
0x140010bd0  jz      short loc_140010BE1
0x140010bd2  mov     rax, [rcx]
0x140010bd5  lea     edx, [rbx+1]
0x140010bd8  mov     rax, [rax+20h]
0x140010bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010be1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140010be8  test    rcx, rcx
0x140010beb  jz      short loc_140010BF9
0x140010bed  mov     rdx, [rcx]
0x140010bf0  mov     rax, [rdx+10h]
0x140010bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010bf9  mov     eax, ebx
0x140010bfb  add     rsp, 20h
0x140010bff  pop     rbx
0x140010c00  retn
```
