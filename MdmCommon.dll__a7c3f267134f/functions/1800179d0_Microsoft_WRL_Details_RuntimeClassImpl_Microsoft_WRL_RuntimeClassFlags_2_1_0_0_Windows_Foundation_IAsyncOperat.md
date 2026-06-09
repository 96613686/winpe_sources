# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::Release(void)

- ea: `0x1800179d0`
- end: `0x180017a32`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800179d0`
- `0x18001f010`

## pseudocode

```c
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
0x1800179d0  push    rbx
0x1800179d2  sub     rsp, 20h
0x1800179d6  mov     r9d, 7FFFFFFFh
0x1800179dc  jmp     short loc_1800179EC
0x1800179de  lea     edx, [r8-1]
0x1800179e2  mov     eax, r8d
0x1800179e5  lock cmpxchg [rcx+0Ch], edx
0x1800179ea  jz      short loc_1800179F5
0x1800179ec  mov     r8d, [rcx+0Ch]
0x1800179f0  cmp     r8d, r9d
0x1800179f3  jnz     short loc_1800179DE
0x1800179f5  lea     ebx, [r8-1]
0x1800179f9  test    ebx, ebx
0x1800179fb  jnz     short loc_180017A29
0x1800179fd  test    rcx, rcx
0x180017a00  jz      short loc_180017A11
0x180017a02  mov     rax, [rcx]
0x180017a05  lea     edx, [rbx+1]
0x180017a08  mov     rax, [rax+20h]
0x180017a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a11  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180017a18  test    rcx, rcx
0x180017a1b  jz      short loc_180017A29
0x180017a1d  mov     rdx, [rcx]
0x180017a20  mov     rax, [rdx+10h]
0x180017a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a29  mov     eax, ebx
0x180017a2b  add     rsp, 20h
0x180017a2f  pop     rbx
0x180017a30  retn
```
