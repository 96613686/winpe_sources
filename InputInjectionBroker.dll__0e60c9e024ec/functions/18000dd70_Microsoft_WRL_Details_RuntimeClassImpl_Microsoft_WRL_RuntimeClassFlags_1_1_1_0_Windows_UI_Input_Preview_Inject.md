# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInputInjector,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x18000dd70`
- end: `0x18000de00`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInputInjector@Injection@Preview@Input@UI@Windows@@UIInputInjector2@56789@UIInputInjector3@56789@U?$CloakedIid@UIInputInjectorPrivate@Internal@Injection@Preview@Input@UI@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `144`
- prototype: `__int64 __fastcall(volatile signed __int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000de10`
- `0x18000de20`
- `0x18000de30`
- `0x18000de40`
- `0x18000de50`
- `0x18000de60`

## callees

- `0x18000dd70`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInputInjector,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>::Release(
        volatile signed __int64 *a1)
{
  signed __int64 v1; // rdx
  unsigned __int32 v2; // ebx
  bool v3; // zf
  signed __int64 v4; // rax
  signed __int32 v5; // r8d

  v1 = *((_QWORD *)a1 + 10);
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return 2147483646;
    v2 = v1 - 1;
    v4 = _InterlockedCompareExchange64(a1 + 10, v1 - 1, v1);
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
      (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*a1 + 120))(a1, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x18000dd70  push    rbx
0x18000dd72  sub     rsp, 20h
0x18000dd76  mov     rdx, [rcx+50h]
0x18000dd7a  mov     r9, rcx
0x18000dd7d  mov     r10d, 7FFFFFFFh
0x18000dd83  test    rdx, rdx
0x18000dd86  js      short loc_18000DDB7
0x18000dd88  cmp     edx, r10d
0x18000dd8b  jz      short loc_18000DDA1
0x18000dd8d  lea     rbx, [rdx-1]
0x18000dd91  mov     rax, rdx
0x18000dd94  lock cmpxchg [rcx+50h], rbx
0x18000dd9a  mov     rdx, rax
0x18000dd9d  jnz     short loc_18000DD83
0x18000dd9f  jmp     short loc_18000DDC5
0x18000dda1  mov     ebx, 7FFFFFFEh
0x18000dda6  jmp     short loc_18000DDF8
0x18000dda8  lea     ecx, [r8-1]
0x18000ddac  mov     eax, r8d
0x18000ddaf  lock cmpxchg [rdx+rdx+10h], ecx
0x18000ddb5  jz      short loc_18000DDC1
0x18000ddb7  mov     r8d, [rdx+rdx+10h]
0x18000ddbc  cmp     r8d, r10d
0x18000ddbf  jnz     short loc_18000DDA8
0x18000ddc1  lea     ebx, [r8-1]
0x18000ddc5  test    ebx, ebx
0x18000ddc7  jnz     short loc_18000DDF8
0x18000ddc9  test    r9, r9
0x18000ddcc  jz      short loc_18000DDE0
0x18000ddce  mov     rax, [r9]
0x18000ddd1  lea     edx, [rbx+1]
0x18000ddd4  mov     rcx, r9
0x18000ddd7  mov     rax, [rax+78h]
0x18000dddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dde0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000dde7  test    rcx, rcx
0x18000ddea  jz      short loc_18000DDF8
0x18000ddec  mov     rdx, [rcx]
0x18000ddef  mov     rax, [rdx+10h]
0x18000ddf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddf8  mov     eax, ebx
0x18000ddfa  add     rsp, 20h
0x18000ddfe  pop     rbx
0x18000ddff  retn
```
