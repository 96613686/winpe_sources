# Microsoft::WRL::SimpleClassFactory<UserOOBECreateUserObjectHandlerServer,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140008d40`
- end: `0x140008e63`
- name: `?CreateInstance@?$SimpleClassFactory@VUserOOBECreateUserObjectHandlerServer@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `291`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400025d8`
- `0x140008d40`
- `0x14000aa50`
- `0x14000c2e0`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140008d6d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140008d6d`

## string_xrefs

- `0x140008dc9`: `SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE\Broker\UserBrokeredClsids`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<UserOOBECreateUserObjectHandlerServer,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD *); // rbx
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  int v10; // esi
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD *); // rbx
  unsigned int v12; // edi
  __int64 (__fastcall ***v13)(_QWORD, __int64, _QWORD *); // [rsp+48h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    RoOriginateError(2147746064LL, 0);
    return 2147746064LL;
  }
  v7 = 0;
  v13 = 0;
  v8 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
  {
    v10 = -2147024882;
LABEL_9:
    if ( v7 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v7)[2])(v7);
    return (unsigned int)v10;
  }
  *((_DWORD *)v8 + 3) = 1;
  *v8 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICreateObject>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  v9[2] = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Broker\\UserBrokeredClsids";
  *v9 = &UserOOBECreateUserObjectHandlerServer::`vftable';
  v10 = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::QueryInterface(
          v9,
          &GUID_00000000_0000_0000_c000_000000000046,
          &v13);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(v9);
  if ( v10 < 0 )
  {
    v7 = v13;
    goto LABEL_9;
  }
  v11 = v13;
  v12 = (**v13)(v13, a3, a4);
  if ( v11 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v11)[2])(v11);
  return v12;
}

```

## disassembly

```asm
0x140008d40  mov     [rsp+arg_0], rbx
0x140008d45  mov     [rsp+arg_10], rbp
0x140008d4a  push    rsi
0x140008d4b  push    rdi
0x140008d4c  push    r14
0x140008d4e  sub     rsp, 20h
0x140008d52  mov     r14, r9
0x140008d55  mov     rbp, r8
0x140008d58  mov     qword ptr [r9], 0
0x140008d5f  test    rdx, rdx
0x140008d62  jz      short loc_140008D7A
0x140008d64  xor     edx, edx
0x140008d66  mov     ebx, 80040110h
0x140008d6b  mov     ecx, ebx
0x140008d6d  call    cs:__imp_RoOriginateError
0x140008d73  mov     eax, ebx
0x140008d75  jmp     loc_140008E50
0x140008d7a  xor     ebx, ebx
0x140008d7c  mov     [rsp+38h+arg_8], rbx
0x140008d81  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140008d88  lea     ecx, [rbx+18h]; unsigned __int64
0x140008d8b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140008d90  mov     rdi, rax
0x140008d93  test    rax, rax
0x140008d96  jnz     short loc_140008D9F
0x140008d98  mov     esi, 8007000Eh
0x140008d9d  jmp     short loc_140008E05
0x140008d9f  mov     dword ptr [rax+0Ch], 1
0x140008da6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICreateObject@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICreateObject>::`vftable'
0x140008dad  mov     [rdi], rax
0x140008db0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140008db7  test    rcx, rcx
0x140008dba  jz      short loc_140008DC9
0x140008dbc  mov     rax, [rcx]
0x140008dbf  mov     rax, [rax+8]
0x140008dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008dc8  nop
0x140008dc9  lea     rax, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140008dd0  mov     [rdi+10h], rax
0x140008dd4  lea     rax, ??_7UserOOBECreateUserObjectHandlerServer@@6B@; const UserOOBECreateUserObjectHandlerServer::`vftable'
0x140008ddb  mov     [rdi], rax
0x140008dde  lea     r8, [rsp+38h+arg_8]
0x140008de3  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140008dea  mov     rcx, rdi
0x140008ded  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::QueryInterface(_GUID const &,void * *)
0x140008df2  mov     esi, eax
0x140008df4  mov     rcx, rdi
0x140008df7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)
0x140008dfc  test    esi, esi
0x140008dfe  jns     short loc_140008E1E
0x140008e00  mov     rbx, [rsp+38h+arg_8]
0x140008e05  test    rbx, rbx
0x140008e08  jz      short loc_140008E1A
0x140008e0a  mov     rdx, [rbx]
0x140008e0d  mov     rcx, rbx
0x140008e10  mov     rax, [rdx+10h]
0x140008e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e19  nop
0x140008e1a  mov     eax, esi
0x140008e1c  jmp     short loc_140008E50
0x140008e1e  mov     rbx, [rsp+38h+arg_8]
0x140008e23  mov     rax, [rbx]
0x140008e26  mov     r8, r14
0x140008e29  mov     rdx, rbp
0x140008e2c  mov     rcx, rbx
0x140008e2f  mov     rax, [rax]
0x140008e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e37  mov     edi, eax
0x140008e39  test    rbx, rbx
0x140008e3c  jz      short loc_140008E4E
0x140008e3e  mov     rdx, [rbx]
0x140008e41  mov     rcx, rbx
0x140008e44  mov     rax, [rdx+10h]
0x140008e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e4d  nop
0x140008e4e  mov     eax, edi
0x140008e50  mov     rbx, [rsp+38h+arg_0]
0x140008e55  mov     rbp, [rsp+38h+arg_10]
0x140008e5a  add     rsp, 20h
0x140008e5e  pop     r14
0x140008e60  pop     rdi
0x140008e61  pop     rsi
0x140008e62  retn
```
