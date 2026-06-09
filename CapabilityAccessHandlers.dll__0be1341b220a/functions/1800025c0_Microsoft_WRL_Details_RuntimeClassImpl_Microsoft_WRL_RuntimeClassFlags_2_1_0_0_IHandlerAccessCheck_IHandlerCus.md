# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::Release(void)

- ea: `0x1800025c0`
- end: `0x18000261f`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessCheck@@UIHandlerCustomConsent@@UIHandlerAccessChange@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `95`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800022c0`
- `0x180002410`
- `0x18000279c`
- `0x180008fe0`
- `0x180008ff0`

## callees

- `0x1800025c0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 7);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 7, v2 - 1, v2) );
  v3 = v2 - 1;
  if ( (_DWORD)v2 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 48LL))(
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
0x1800025c0  push    rbx
0x1800025c2  sub     rsp, 20h
0x1800025c6  mov     r9d, 7FFFFFFFh
0x1800025cc  mov     r8d, [rcx+1Ch]
0x1800025d0  cmp     r8d, r9d
0x1800025d3  jz      short loc_1800025E3
0x1800025d5  lea     edx, [r8-1]
0x1800025d9  mov     eax, r8d
0x1800025dc  lock cmpxchg [rcx+1Ch], edx
0x1800025e1  jnz     short loc_1800025CC
0x1800025e3  lea     ebx, [r8-1]
0x1800025e7  test    ebx, ebx
0x1800025e9  jnz     short loc_180002617
0x1800025eb  test    rcx, rcx
0x1800025ee  jz      short loc_1800025FF
0x1800025f0  mov     rax, [rcx]
0x1800025f3  lea     edx, [rbx+1]
0x1800025f6  mov     rax, [rax+30h]
0x1800025fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ff  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002606  test    rcx, rcx
0x180002609  jz      short loc_180002617
0x18000260b  mov     rdx, [rcx]
0x18000260e  mov     rax, [rdx+10h]
0x180002612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002617  mov     eax, ebx
0x180002619  add     rsp, 20h
0x18000261d  pop     rbx
0x18000261e  retn
```
