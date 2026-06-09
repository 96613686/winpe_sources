# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IObjectWithSelection>::Release(void)

- ea: `0x14000c350`
- end: `0x14000c3b1`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400071ac`
- `0x140007264`
- `0x14000c3c0`

## callees

- `0x14000c350`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IObjectWithSelection>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 5);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 5, v2 - 1, v2) );
  v3 = v2 - 1;
  if ( (_DWORD)v2 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 80LL))(
        a1,
        1,
        v2,
        0x7FFFFFFF);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                  + 16LL))(
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
0x14000c350  push    rbx
0x14000c352  sub     rsp, 20h
0x14000c356  mov     r9d, 7FFFFFFFh
0x14000c35c  jmp     short loc_14000C36C
0x14000c35e  lea     edx, [r8-1]
0x14000c362  mov     eax, r8d
0x14000c365  lock cmpxchg [rcx+14h], edx
0x14000c36a  jz      short loc_14000C375
0x14000c36c  mov     r8d, [rcx+14h]
0x14000c370  cmp     r8d, r9d
0x14000c373  jnz     short loc_14000C35E
0x14000c375  lea     ebx, [r8-1]
0x14000c379  test    ebx, ebx
0x14000c37b  jnz     short loc_14000C3A9
0x14000c37d  test    rcx, rcx
0x14000c380  jz      short loc_14000C391
0x14000c382  mov     rax, [rcx]
0x14000c385  lea     edx, [rbx+1]
0x14000c388  mov     rax, [rax+50h]
0x14000c38c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c391  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000c398  test    rcx, rcx
0x14000c39b  jz      short loc_14000C3A9
0x14000c39d  mov     rdx, [rcx]
0x14000c3a0  mov     rax, [rdx+10h]
0x14000c3a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c3a9  mov     eax, ebx
0x14000c3ab  add     rsp, 20h
0x14000c3af  pop     rbx
0x14000c3b0  retn
```
