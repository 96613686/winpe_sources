# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyProperties *>,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x1800164b0`
- end: `0x180016511`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVProductKeyProperties@Licensing@System@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016520`

## callees

- `0x1800164b0`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyProperties *>,Microsoft::WRL::FtmBase>::Release(
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
0x1800164b0  push    rbx
0x1800164b2  sub     rsp, 20h
0x1800164b6  mov     r9d, 7FFFFFFFh
0x1800164bc  jmp     short loc_1800164CC
0x1800164be  lea     edx, [r8-1]
0x1800164c2  mov     eax, r8d
0x1800164c5  lock cmpxchg [rcx+2Ch], edx
0x1800164ca  jz      short loc_1800164D5
0x1800164cc  mov     r8d, [rcx+2Ch]
0x1800164d0  cmp     r8d, r9d
0x1800164d3  jnz     short loc_1800164BE
0x1800164d5  lea     ebx, [r8-1]
0x1800164d9  test    ebx, ebx
0x1800164db  jnz     short loc_180016509
0x1800164dd  test    rcx, rcx
0x1800164e0  jz      short loc_1800164F1
0x1800164e2  mov     rax, [rcx]
0x1800164e5  lea     edx, [rbx+1]
0x1800164e8  mov     rax, [rax+20h]
0x1800164ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164f1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800164f8  test    rcx, rcx
0x1800164fb  jz      short loc_180016509
0x1800164fd  mov     rdx, [rcx]
0x180016500  mov     rax, [rdx+10h]
0x180016504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016509  mov     eax, ebx
0x18001650b  add     rsp, 20h
0x18001650f  pop     rbx
0x180016510  retn
```
