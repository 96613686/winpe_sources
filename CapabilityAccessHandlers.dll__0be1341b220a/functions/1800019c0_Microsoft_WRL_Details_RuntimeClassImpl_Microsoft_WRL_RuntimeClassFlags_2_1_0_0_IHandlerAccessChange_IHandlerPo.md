# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>::Release(void)

- ea: `0x1800019c0`
- end: `0x180001a2b`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessChange@@UIHandlerPolicy@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `107`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008fc0`

## callees

- `0x1800019c0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>::Release(
        volatile signed __int32 *a1)
{
  signed __int32 i; // edx
  unsigned __int32 v2; // ebx

  for ( i = *((_DWORD *)a1 + 5); i != 0x7FFFFFFF; i = *((_DWORD *)a1 + 5) )
  {
    if ( i == _InterlockedCompareExchange(a1 + 5, i - 1, i) )
      break;
  }
  v2 = i - 1;
  if ( i == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 32LL))(a1, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x1800019c0  push    rbx
0x1800019c2  sub     rsp, 20h
0x1800019c6  mov     edx, [rcx+14h]
0x1800019c9  cmp     edx, 7FFFFFFFh
0x1800019cf  jz      short loc_1800019DF
0x1800019d1  lea     r8d, [rdx-1]
0x1800019d5  mov     eax, edx
0x1800019d7  lock cmpxchg [rcx+14h], r8d
0x1800019dd  jnz     short loc_180001A1E
0x1800019df  lea     ebx, [rdx-1]
0x1800019e2  test    ebx, ebx
0x1800019e4  jz      short loc_1800019EE
0x1800019e6  mov     eax, ebx
0x1800019e8  add     rsp, 20h
0x1800019ec  pop     rbx
0x1800019ed  retn
0x1800019ee  test    rcx, rcx
0x1800019f1  jz      short loc_180001A04
0x1800019f3  mov     rax, [rcx]
0x1800019f6  mov     edx, 1
0x1800019fb  mov     rax, [rax+20h]
0x1800019ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a04  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180001a0b  test    rcx, rcx
0x180001a0e  jz      short loc_1800019E6
0x180001a10  mov     rdx, [rcx]
0x180001a13  mov     rax, [rdx+10h]
0x180001a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a1c  jmp     short loc_1800019E6
0x180001a1e  mov     edx, [rcx+14h]
0x180001a21  cmp     edx, 7FFFFFFFh
0x180001a27  jnz     short loc_1800019D1
0x180001a29  jmp     short loc_1800019DF
```
