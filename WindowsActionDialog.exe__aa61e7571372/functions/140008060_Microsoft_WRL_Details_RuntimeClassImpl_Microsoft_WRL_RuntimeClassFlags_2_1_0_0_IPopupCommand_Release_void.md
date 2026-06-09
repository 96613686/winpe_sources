# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommand>::Release(void)

- ea: `0x140008060`
- end: `0x1400080c1`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIPopupCommand@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140008060`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommand>::Release(
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
0x140008060  push    rbx
0x140008062  sub     rsp, 20h
0x140008066  mov     r9d, 7FFFFFFFh
0x14000806c  jmp     short loc_14000807C
0x14000806e  lea     edx, [r8-1]
0x140008072  mov     eax, r8d
0x140008075  lock cmpxchg [rcx+0Ch], edx
0x14000807a  jz      short loc_140008085
0x14000807c  mov     r8d, [rcx+0Ch]
0x140008080  cmp     r8d, r9d
0x140008083  jnz     short loc_14000806E
0x140008085  lea     ebx, [r8-1]
0x140008089  test    ebx, ebx
0x14000808b  jnz     short loc_1400080B9
0x14000808d  test    rcx, rcx
0x140008090  jz      short loc_1400080A1
0x140008092  mov     rax, [rcx]
0x140008095  lea     edx, [rbx+1]
0x140008098  mov     rax, [rax+30h]
0x14000809c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080a1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400080a8  test    rcx, rcx
0x1400080ab  jz      short loc_1400080B9
0x1400080ad  mov     rdx, [rcx]
0x1400080b0  mov     rax, [rdx+10h]
0x1400080b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080b9  mov     eax, ebx
0x1400080bb  add     rsp, 20h
0x1400080bf  pop     rbx
0x1400080c0  retn
```
