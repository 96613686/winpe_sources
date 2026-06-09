# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::Release(void)

- ea: `0x1800174b0`
- end: `0x180017511`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800174b0`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 3);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 3, v2 - 1, v2) );
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
0x1800174b0  push    rbx
0x1800174b2  sub     rsp, 20h
0x1800174b6  mov     r9d, 7FFFFFFFh
0x1800174bc  jmp     short loc_1800174CC
0x1800174be  lea     edx, [r8-1]
0x1800174c2  mov     eax, r8d
0x1800174c5  lock cmpxchg [rcx+0Ch], edx
0x1800174ca  jz      short loc_1800174D5
0x1800174cc  mov     r8d, [rcx+0Ch]
0x1800174d0  cmp     r8d, r9d
0x1800174d3  jnz     short loc_1800174BE
0x1800174d5  lea     ebx, [r8-1]
0x1800174d9  test    ebx, ebx
0x1800174db  jnz     short loc_180017509
0x1800174dd  test    rcx, rcx
0x1800174e0  jz      short loc_1800174F1
0x1800174e2  mov     rax, [rcx]
0x1800174e5  lea     edx, [rbx+1]
0x1800174e8  mov     rax, [rax+20h]
0x1800174ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174f1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800174f8  test    rcx, rcx
0x1800174fb  jz      short loc_180017509
0x1800174fd  mov     rdx, [rcx]
0x180017500  mov     rax, [rdx+10h]
0x180017504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017509  mov     eax, ebx
0x18001750b  add     rsp, 20h
0x18001750f  pop     rbx
0x180017510  retn
```
