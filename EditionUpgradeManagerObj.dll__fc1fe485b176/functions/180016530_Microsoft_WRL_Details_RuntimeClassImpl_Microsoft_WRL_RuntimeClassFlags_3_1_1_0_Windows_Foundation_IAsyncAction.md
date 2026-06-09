# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x180016530`
- end: `0x1800165c0`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IAsyncActionProgressHandler@N@Foundation@Windows@@UIInspectable@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `144`
- prototype: `__int64 __fastcall(volatile signed __int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800165d0`
- `0x1800165e0`
- `0x1800165f0`
- `0x180016600`

## callees

- `0x180016530`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::Release(
        volatile signed __int64 *a1)
{
  signed __int64 v1; // rdx
  unsigned __int32 v2; // ebx
  bool v3; // zf
  signed __int64 v4; // rax
  signed __int32 v5; // r8d

  v1 = *((_QWORD *)a1 + 9);
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return 2147483646;
    v2 = v1 - 1;
    v4 = _InterlockedCompareExchange64(a1 + 9, v1 - 1, v1);
    v3 = v1 == v4;
    v1 = v4;
    if ( v3 )
      goto LABEL_10;
  }
  do
    v5 = *(_DWORD *)(2 * v1 + 0x10);
  while ( v5 != 0x7FFFFFFF && v5 != _InterlockedCompareExchange((volatile signed __int32 *)(2 * v1 + 16), v5 - 1, v5) );
  v2 = v5 - 1;
LABEL_10:
  if ( !v2 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*a1 + 48))(a1, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x180016530  push    rbx
0x180016532  sub     rsp, 20h
0x180016536  mov     rdx, [rcx+48h]
0x18001653a  mov     r9, rcx
0x18001653d  mov     r10d, 7FFFFFFFh
0x180016543  test    rdx, rdx
0x180016546  js      short loc_180016577
0x180016548  cmp     edx, r10d
0x18001654b  jz      short loc_180016561
0x18001654d  lea     rbx, [rdx-1]
0x180016551  mov     rax, rdx
0x180016554  lock cmpxchg [rcx+48h], rbx
0x18001655a  mov     rdx, rax
0x18001655d  jnz     short loc_180016543
0x18001655f  jmp     short loc_180016585
0x180016561  mov     ebx, 7FFFFFFEh
0x180016566  jmp     short loc_1800165B8
0x180016568  lea     ecx, [r8-1]
0x18001656c  mov     eax, r8d
0x18001656f  lock cmpxchg [rdx+rdx+10h], ecx
0x180016575  jz      short loc_180016581
0x180016577  mov     r8d, [rdx+rdx+10h]
0x18001657c  cmp     r8d, r10d
0x18001657f  jnz     short loc_180016568
0x180016581  lea     ebx, [r8-1]
0x180016585  test    ebx, ebx
0x180016587  jnz     short loc_1800165B8
0x180016589  test    r9, r9
0x18001658c  jz      short loc_1800165A0
0x18001658e  mov     rax, [r9]
0x180016591  lea     edx, [rbx+1]
0x180016594  mov     rcx, r9
0x180016597  mov     rax, [rax+30h]
0x18001659b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165a0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800165a7  test    rcx, rcx
0x1800165aa  jz      short loc_1800165B8
0x1800165ac  mov     rdx, [rcx]
0x1800165af  mov     rax, [rdx+10h]
0x1800165b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165b8  mov     eax, ebx
0x1800165ba  add     rsp, 20h
0x1800165be  pop     rbx
0x1800165bf  retn
```
