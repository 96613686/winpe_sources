# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::Release(void)

- ea: `0x18000a7f0`
- end: `0x18000a880`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIAppPrioritizationUserSessionInternal@@UIAppPrioritizationUserSession@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `144`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009110`
- `0x18000a890`
- `0x18000a8a0`
- `0x18000a8b0`
- `0x18000a8c0`
- `0x18000a8d0`
- `0x18000c890`

## callees

- `0x18000a7f0`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::Release(
        volatile signed __int64 *a1)
{
  signed __int64 v2; // rcx
  unsigned __int32 v3; // ebx
  bool v4; // zf
  signed __int64 v5; // rax
  signed __int32 v6; // r8d

  v2 = *((_QWORD *)a1 + 9);
  while ( v2 >= 0 )
  {
    if ( (_DWORD)v2 == 0x7FFFFFFF )
      return 2147483646;
    v3 = v2 - 1;
    v5 = _InterlockedCompareExchange64(a1 + 9, v2 - 1, v2);
    v4 = v2 == v5;
    v2 = v5;
    if ( v4 )
      goto LABEL_10;
  }
  do
    v6 = *(_DWORD *)(2 * v2 + 0x10);
  while ( v6 != 0x7FFFFFFF && v6 != _InterlockedCompareExchange((volatile signed __int32 *)(2 * v2 + 16), v6 - 1, v6) );
  v3 = v6 - 1;
LABEL_10:
  if ( !v3 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*a1 + 48))(a1, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v3;
}

```

## disassembly

```asm
0x18000a7f0  push    rbx
0x18000a7f2  sub     rsp, 20h
0x18000a7f6  mov     r9, rcx
0x18000a7f9  mov     r10d, 7FFFFFFFh
0x18000a7ff  mov     rcx, [rcx+48h]
0x18000a803  test    rcx, rcx
0x18000a806  js      short loc_18000A837
0x18000a808  cmp     ecx, r10d
0x18000a80b  jz      short loc_18000A821
0x18000a80d  lea     rbx, [rcx-1]
0x18000a811  mov     rax, rcx
0x18000a814  lock cmpxchg [r9+48h], rbx
0x18000a81a  mov     rcx, rax
0x18000a81d  jnz     short loc_18000A803
0x18000a81f  jmp     short loc_18000A845
0x18000a821  mov     ebx, 7FFFFFFEh
0x18000a826  jmp     short loc_18000A878
0x18000a828  lea     edx, [r8-1]
0x18000a82c  mov     eax, r8d
0x18000a82f  lock cmpxchg [rcx+rcx+10h], edx
0x18000a835  jz      short loc_18000A841
0x18000a837  mov     r8d, [rcx+rcx+10h]
0x18000a83c  cmp     r8d, r10d
0x18000a83f  jnz     short loc_18000A828
0x18000a841  lea     ebx, [r8-1]
0x18000a845  test    ebx, ebx
0x18000a847  jnz     short loc_18000A878
0x18000a849  test    r9, r9
0x18000a84c  jz      short loc_18000A860
0x18000a84e  mov     rax, [r9]
0x18000a851  lea     edx, [rbx+1]
0x18000a854  mov     rcx, r9
0x18000a857  mov     rax, [rax+30h]
0x18000a85b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a860  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a867  test    rcx, rcx
0x18000a86a  jz      short loc_18000A878
0x18000a86c  mov     rdx, [rcx]
0x18000a86f  mov     rax, [rdx+10h]
0x18000a873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a878  mov     eax, ebx
0x18000a87a  add     rsp, 20h
0x18000a87e  pop     rbx
0x18000a87f  retn
```
