# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IInspectable>::Release(void)

- ea: `0x180002710`
- end: `0x180002793`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIInspectable@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `131`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006070`
- `0x180006080`
- `0x180006090`

## callees

- `0x180002710`
- `0x180004350`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IInspectable>::Release(
        __int64 a1,
        volatile int *a2)
{
  signed __int64 v2; // rax
  __int64 v3; // r9
  unsigned int v4; // ebx
  signed __int64 v5; // rtt

  v2 = *(_QWORD *)(a1 + 64);
  v3 = a1;
  while ( v2 >= 0 )
  {
    if ( (_DWORD)v2 == 0x7FFFFFFF )
      return 2147483646;
    v4 = v2 - 1;
    v5 = v2;
    v2 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 64), v2 - 1, v2);
    if ( v5 == v2 )
      goto LABEL_5;
  }
  v4 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(2 * v2 + 16), a2);
LABEL_5:
  if ( !v4 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 48LL))(v3, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v4;
}

```

## disassembly

```asm
0x180002710  sub     rsp, 28h
0x180002714  mov     rax, [rcx+40h]
0x180002718  mov     r9, rcx
0x18000271b  mov     [rsp+28h+var_8], rbx
0x180002720  test    rax, rax
0x180002723  js      short loc_180002774
0x180002725  cmp     eax, 7FFFFFFFh
0x18000272a  jz      short loc_180002765
0x18000272c  lea     rbx, [rax-1]
0x180002730  lock cmpxchg [rcx+40h], rbx
0x180002736  jnz     short loc_180002720
0x180002738  test    ebx, ebx
0x18000273a  jnz     short loc_180002761
0x18000273c  test    r9, r9
0x18000273f  jz      short loc_180002755
0x180002741  mov     rcx, [r9]
0x180002744  mov     edx, 1
0x180002749  mov     rax, [rcx+30h]
0x18000274d  mov     rcx, r9
0x180002750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002755  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000275c  test    rcx, rcx
0x18000275f  jnz     short loc_180002785
0x180002761  mov     eax, ebx
0x180002763  jmp     short loc_18000276A
0x180002765  mov     eax, 7FFFFFFEh
0x18000276a  mov     rbx, [rsp+28h+var_8]
0x18000276f  add     rsp, 28h
0x180002773  retn
0x180002774  lea     rcx, ds:10h[rax*2]; this
0x18000277c  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180002781  mov     ebx, eax
0x180002783  jmp     short loc_180002738
0x180002785  mov     rax, [rcx]
0x180002788  mov     rax, [rax+10h]
0x18000278c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002791  jmp     short loc_180002761
```
