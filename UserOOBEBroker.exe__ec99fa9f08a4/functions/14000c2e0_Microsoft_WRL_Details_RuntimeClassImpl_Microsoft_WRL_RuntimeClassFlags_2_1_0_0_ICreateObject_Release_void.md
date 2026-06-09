# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)

- ea: `0x14000c2e0`
- end: `0x14000c341`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008d40`

## callees

- `0x14000c2e0`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(
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
0x14000c2e0  push    rbx
0x14000c2e2  sub     rsp, 20h
0x14000c2e6  mov     r9d, 7FFFFFFFh
0x14000c2ec  jmp     short loc_14000C2FC
0x14000c2ee  lea     edx, [r8-1]
0x14000c2f2  mov     eax, r8d
0x14000c2f5  lock cmpxchg [rcx+0Ch], edx
0x14000c2fa  jz      short loc_14000C305
0x14000c2fc  mov     r8d, [rcx+0Ch]
0x14000c300  cmp     r8d, r9d
0x14000c303  jnz     short loc_14000C2EE
0x14000c305  lea     ebx, [r8-1]
0x14000c309  test    ebx, ebx
0x14000c30b  jnz     short loc_14000C339
0x14000c30d  test    rcx, rcx
0x14000c310  jz      short loc_14000C321
0x14000c312  mov     rax, [rcx]
0x14000c315  lea     edx, [rbx+1]
0x14000c318  mov     rax, [rax+20h]
0x14000c31c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c321  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000c328  test    rcx, rcx
0x14000c32b  jz      short loc_14000C339
0x14000c32d  mov     rdx, [rcx]
0x14000c330  mov     rax, [rdx+10h]
0x14000c334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c339  mov     eax, ebx
0x14000c33b  add     rsp, 20h
0x14000c33f  pop     rbx
0x14000c340  retn
```
