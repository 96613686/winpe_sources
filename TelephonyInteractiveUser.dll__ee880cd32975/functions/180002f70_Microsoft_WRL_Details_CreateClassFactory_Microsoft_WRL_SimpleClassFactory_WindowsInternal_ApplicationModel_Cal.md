# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180002f70`
- end: `0x180003048`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001de4`
- `0x180002f70`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics,0>>(
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
    *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics,0>::`vftable';
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
0x180002f70  mov     [rsp+arg_8], rbx
0x180002f75  push    rbp
0x180002f76  push    rsi
0x180002f77  push    rdi
0x180002f78  sub     rsp, 20h
0x180002f7c  mov     rsi, rcx
0x180002f7f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002f86  mov     ecx, 18h; unsigned __int64
0x180002f8b  mov     rbp, r9
0x180002f8e  mov     rdi, r8
0x180002f91  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002f96  mov     rbx, rax
0x180002f99  test    rax, rax
0x180002f9c  jz      loc_180003036
0x180002fa2  mov     dword ptr [rax+0Ch], 1
0x180002fa9  mov     rcx, rbx
0x180002fac  mov     dword ptr [rax+14h], 4
0x180002fb3  lea     rax, ??_7?$SimpleClassFactory@VIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics,0>::`vftable'
0x180002fba  mov     [rbx], rax
0x180002fbd  mov     rax, cs:off_18001A3A0
0x180002fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fc9  mov     rax, [rbx]
0x180002fcc  mov     rcx, rbx
0x180002fcf  mov     rax, [rax+10h]
0x180002fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd8  mov     eax, [rsi]
0x180002fda  mov     r8, rbp
0x180002fdd  mov     [rbx+14h], eax
0x180002fe0  mov     rdx, rdi
0x180002fe3  mov     rax, [rbx]
0x180002fe6  mov     rcx, rbx
0x180002fe9  mov     rax, [rax]
0x180002fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ff1  test    byte ptr [rsi], 1
0x180002ff4  mov     edi, eax
0x180002ff6  jz      short loc_180003023
0x180002ff8  test    eax, eax
0x180002ffa  js      short loc_18000301F
0x180002ffc  test    byte ptr [rsi], 4
0x180002fff  jz      short loc_180003016
0x180003001  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180003008  mov     rdx, [rcx]
0x18000300b  mov     rax, [rdx+8]
0x18000300f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003014  jmp     short loc_180003018
0x180003016  xor     ebx, ebx
0x180003018  test    rbx, rbx
0x18000301b  jz      short loc_180003032
0x18000301d  jmp     short loc_180003023
0x18000301f  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180003023  mov     rax, [rbx]
0x180003026  mov     rcx, rbx
0x180003029  mov     rax, [rax+10h]
0x18000302d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003032  mov     eax, edi
0x180003034  jmp     short loc_18000303B
0x180003036  mov     eax, 8007000Eh
0x18000303b  mov     rbx, [rsp+38h+arg_8]
0x180003040  add     rsp, 20h
0x180003044  pop     rdi
0x180003045  pop     rsi
0x180003046  pop     rbp
0x180003047  retn
```
