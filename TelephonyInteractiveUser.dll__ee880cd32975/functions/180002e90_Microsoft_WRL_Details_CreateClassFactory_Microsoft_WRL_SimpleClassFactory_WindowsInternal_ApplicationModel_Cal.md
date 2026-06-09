# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::AppLauncherStatics,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180002e90`
- end: `0x180002f68`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VAppLauncherStatics@Calls@ApplicationModel@WindowsInternal@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001de4`
- `0x180002e90`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::AppLauncherStatics,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi

  v7 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    v7[3] = 1;
    v7[5] = 4;
    *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::AppLauncherStatics,0>::`vftable';
    ((void (__fastcall *)(_DWORD *))Microsoft::WRL::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef)(v7);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    v8[5] = *a1;
    v9 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, __int64))v8)(v8, a3, a4);
    v10 = v9;
    if ( (*(_BYTE *)a1 & 1) != 0 )
    {
      if ( v9 < 0 )
      {
        v8[5] &= 0xFFFFFFFA;
      }
      else
      {
        if ( (*(_BYTE *)a1 & 4) != 0 )
          (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                               + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
        else
          v8 = 0;
        if ( !v8 )
          return v10;
      }
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    return v10;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180002e90  mov     [rsp+arg_8], rbx
0x180002e95  push    rbp
0x180002e96  push    rsi
0x180002e97  push    rdi
0x180002e98  sub     rsp, 20h
0x180002e9c  mov     rsi, rcx
0x180002e9f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002ea6  mov     ecx, 18h; unsigned __int64
0x180002eab  mov     rbp, r9
0x180002eae  mov     rdi, r8
0x180002eb1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002eb6  mov     rbx, rax
0x180002eb9  test    rax, rax
0x180002ebc  jz      loc_180002F56
0x180002ec2  mov     dword ptr [rax+0Ch], 1
0x180002ec9  mov     rcx, rbx
0x180002ecc  mov     dword ptr [rax+14h], 4
0x180002ed3  lea     rax, ??_7?$SimpleClassFactory@VAppLauncherStatics@Calls@ApplicationModel@WindowsInternal@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::AppLauncherStatics,0>::`vftable'
0x180002eda  mov     [rbx], rax
0x180002edd  mov     rax, cs:off_18001A488
0x180002ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ee9  mov     rax, [rbx]
0x180002eec  mov     rcx, rbx
0x180002eef  mov     rax, [rax+10h]
0x180002ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef8  mov     eax, [rsi]
0x180002efa  mov     r8, rbp
0x180002efd  mov     [rbx+14h], eax
0x180002f00  mov     rdx, rdi
0x180002f03  mov     rax, [rbx]
0x180002f06  mov     rcx, rbx
0x180002f09  mov     rax, [rax]
0x180002f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f11  test    byte ptr [rsi], 1
0x180002f14  mov     edi, eax
0x180002f16  jz      short loc_180002F43
0x180002f18  test    eax, eax
0x180002f1a  js      short loc_180002F3F
0x180002f1c  test    byte ptr [rsi], 4
0x180002f1f  jz      short loc_180002F36
0x180002f21  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002f28  mov     rdx, [rcx]
0x180002f2b  mov     rax, [rdx+8]
0x180002f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f34  jmp     short loc_180002F38
0x180002f36  xor     ebx, ebx
0x180002f38  test    rbx, rbx
0x180002f3b  jz      short loc_180002F52
0x180002f3d  jmp     short loc_180002F43
0x180002f3f  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180002f43  mov     rax, [rbx]
0x180002f46  mov     rcx, rbx
0x180002f49  mov     rax, [rax+10h]
0x180002f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f52  mov     eax, edi
0x180002f54  jmp     short loc_180002F5B
0x180002f56  mov     eax, 8007000Eh
0x180002f5b  mov     rbx, [rsp+38h+arg_8]
0x180002f60  add     rsp, 20h
0x180002f64  pop     rdi
0x180002f65  pop     rsi
0x180002f66  pop     rbp
0x180002f67  retn
```
