# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x180007150`
- end: `0x1800071e0`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectionBroker@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `144`
- prototype: `__int64 __fastcall(volatile signed __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800071f0`
- `0x180007200`
- `0x180007280`

## callees

- `0x180007150`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::Release(
        volatile signed __int64 *a1)
{
  signed __int64 v1; // rdx
  unsigned __int32 v2; // ebx
  bool v3; // zf
  signed __int64 v4; // rax
  signed __int32 v5; // r8d

  v1 = *((_QWORD *)a1 + 7);
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return 2147483646;
    v2 = v1 - 1;
    v4 = _InterlockedCompareExchange64(a1 + 7, v1 - 1, v1);
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
      (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*a1 + 112))(a1, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x180007150  push    rbx
0x180007152  sub     rsp, 20h
0x180007156  mov     rdx, [rcx+38h]
0x18000715a  mov     r9, rcx
0x18000715d  mov     r10d, 7FFFFFFFh
0x180007163  test    rdx, rdx
0x180007166  js      short loc_180007197
0x180007168  cmp     edx, r10d
0x18000716b  jz      short loc_180007181
0x18000716d  lea     rbx, [rdx-1]
0x180007171  mov     rax, rdx
0x180007174  lock cmpxchg [rcx+38h], rbx
0x18000717a  mov     rdx, rax
0x18000717d  jnz     short loc_180007163
0x18000717f  jmp     short loc_1800071A5
0x180007181  mov     ebx, 7FFFFFFEh
0x180007186  jmp     short loc_1800071D8
0x180007188  lea     ecx, [r8-1]
0x18000718c  mov     eax, r8d
0x18000718f  lock cmpxchg [rdx+rdx+10h], ecx
0x180007195  jz      short loc_1800071A1
0x180007197  mov     r8d, [rdx+rdx+10h]
0x18000719c  cmp     r8d, r10d
0x18000719f  jnz     short loc_180007188
0x1800071a1  lea     ebx, [r8-1]
0x1800071a5  test    ebx, ebx
0x1800071a7  jnz     short loc_1800071D8
0x1800071a9  test    r9, r9
0x1800071ac  jz      short loc_1800071C0
0x1800071ae  mov     rax, [r9]
0x1800071b1  lea     edx, [rbx+1]
0x1800071b4  mov     rcx, r9
0x1800071b7  mov     rax, [rax+70h]
0x1800071bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071c0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800071c7  test    rcx, rcx
0x1800071ca  jz      short loc_1800071D8
0x1800071cc  mov     rdx, [rcx]
0x1800071cf  mov     rax, [rdx+10h]
0x1800071d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071d8  mov     eax, ebx
0x1800071da  add     rsp, 20h
0x1800071de  pop     rbx
0x1800071df  retn
```
