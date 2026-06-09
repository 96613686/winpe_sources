# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::IHotKeyClientOwner>::Release(void)

- ea: `0x14000cb90`
- end: `0x14000cc08`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIHotKeyClientOwner@Text@Internal@UI@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `120`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002fbc`
- `0x14000c514`
- `0x14000cc10`
- `0x14000fd60`

## callees

- `0x14000cb90`
- `0x14000cd60`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::IHotKeyClientOwner>::Release(
        __int64 a1,
        volatile int *a2)
{
  signed __int64 v2; // rax
  __int64 v3; // r10
  unsigned int v4; // ebx
  signed __int64 v5; // rtt

  v2 = *(_QWORD *)(a1 + 24);
  v3 = a1;
  while ( v2 >= 0 )
  {
    if ( (_DWORD)v2 == 0x7FFFFFFF )
      return 2147483646;
    v4 = v2 - 1;
    v5 = v2;
    v2 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 24), v2 - 1, v2);
    if ( v5 == v2 )
      goto LABEL_8;
  }
  v4 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(2 * v2 + 16), a2);
LABEL_8:
  if ( !v4 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 64LL))(v3, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v4;
}

```

## disassembly

```asm
0x14000cb90  push    rbx
0x14000cb92  sub     rsp, 20h
0x14000cb96  mov     rax, [rcx+18h]
0x14000cb9a  mov     r10, rcx
0x14000cb9d  test    rax, rax
0x14000cba0  js      short loc_14000CBBE
0x14000cba2  cmp     eax, 7FFFFFFFh
0x14000cba7  jz      short loc_14000CBB7
0x14000cba9  lea     rbx, [rax-1]
0x14000cbad  lock cmpxchg [rcx+18h], rbx
0x14000cbb3  jnz     short loc_14000CB9D
0x14000cbb5  jmp     short loc_14000CBCD
0x14000cbb7  mov     ebx, 7FFFFFFEh
0x14000cbbc  jmp     short loc_14000CC00
0x14000cbbe  lea     rcx, ds:10h[rax*2]; this
0x14000cbc6  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x14000cbcb  mov     ebx, eax
0x14000cbcd  test    ebx, ebx
0x14000cbcf  jnz     short loc_14000CC00
0x14000cbd1  test    r10, r10
0x14000cbd4  jz      short loc_14000CBE8
0x14000cbd6  mov     rcx, [r10]
0x14000cbd9  lea     edx, [rbx+1]
0x14000cbdc  mov     rax, [rcx+40h]
0x14000cbe0  mov     rcx, r10
0x14000cbe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cbe8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000cbef  test    rcx, rcx
0x14000cbf2  jz      short loc_14000CC00
0x14000cbf4  mov     rax, [rcx]
0x14000cbf7  mov     rax, [rax+10h]
0x14000cbfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc00  mov     eax, ebx
0x14000cc02  add     rsp, 20h
0x14000cc06  pop     rbx
0x14000cc07  retn
```
