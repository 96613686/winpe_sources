# Microsoft::WRL::SimpleClassFactory<CBatteryNotificationManager,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180007080`
- end: `0x1800071a4`
- name: `?CreateInstance@?$SimpleClassFactory@VCBatteryNotificationManager@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `292`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001c0c`
- `0x180007080`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800070a4`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800070a4`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CBatteryNotificationManager,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // edi
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v13)(_QWORD, __int64, _QWORD *); // [rsp+58h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
    return v6;
  }
  v13 = 0;
  v7 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    v7[3] = 1;
    *(_QWORD *)v7 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IBatteryNotificationManager>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v8 = &CBatteryNotificationManager::`vftable';
    v9 = ((__int64 (__fastcall *)(_DWORD *, GUID *, _QWORD))CBatteryNotificationManager::`vftable')(
           v8,
           &GUID_00000000_0000_0000_c000_000000000046,
           &v13);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v9 >= 0 )
    {
      v6 = (**v13)(v13, a3, a4);
      v12 = v13;
      if ( v13 )
      {
        v13 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v12)[2])(v12);
      }
      return v6;
    }
  }
  else
  {
    v9 = -2147024882;
  }
  v10 = v13;
  if ( v13 )
  {
    v13 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v10)[2])(v10);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007080  push    rbx
0x180007082  push    rbp
0x180007083  push    rsi
0x180007084  push    rdi
0x180007085  sub     rsp, 28h
0x180007089  mov     rsi, r9
0x18000708c  mov     rbp, r8
0x18000708f  mov     qword ptr [r9], 0
0x180007096  test    rdx, rdx
0x180007099  jz      short loc_1800070AF
0x18000709b  xor     edx, edx
0x18000709d  mov     ebx, 80040110h
0x1800070a2  mov     ecx, ebx
0x1800070a4  call    cs:__imp_RoOriginateError
0x1800070aa  jmp     loc_180007199
0x1800070af  mov     [rsp+48h+arg_8], 0
0x1800070b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800070bf  mov     ecx, 10h; unsigned __int64
0x1800070c4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800070c9  mov     rbx, rax
0x1800070cc  test    rax, rax
0x1800070cf  jnz     short loc_1800070D8
0x1800070d1  mov     edi, 8007000Eh
0x1800070d6  jmp     short loc_18000713D
0x1800070d8  mov     dword ptr [rax+0Ch], 1
0x1800070df  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIBatteryNotificationManager@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IBatteryNotificationManager>::`vftable'
0x1800070e6  mov     [rbx], rax
0x1800070e9  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800070f0  test    rcx, rcx
0x1800070f3  jz      short loc_180007102
0x1800070f5  mov     rax, [rcx]
0x1800070f8  mov     rax, [rax+8]
0x1800070fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007101  nop
0x180007102  lea     rax, ??_7CBatteryNotificationManager@@6B@; const CBatteryNotificationManager::`vftable'
0x180007109  mov     [rbx], rax
0x18000710c  lea     r8, [rsp+48h+arg_8]
0x180007111  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180007118  mov     rcx, rbx
0x18000711b  mov     rax, cs:??_7CBatteryNotificationManager@@6B@; const CBatteryNotificationManager::`vftable'
0x180007122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007127  mov     edi, eax
0x180007129  mov     rax, [rbx]
0x18000712c  mov     rcx, rbx
0x18000712f  mov     rax, [rax+10h]
0x180007133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007138  nop
0x180007139  test    edi, edi
0x18000713b  jns     short loc_180007161
0x18000713d  mov     rcx, [rsp+48h+arg_8]
0x180007142  test    rcx, rcx
0x180007145  jz      short loc_18000715D
0x180007147  mov     [rsp+48h+arg_8], 0
0x180007150  mov     rdx, [rcx]
0x180007153  mov     rax, [rdx+10h]
0x180007157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000715c  nop
0x18000715d  mov     eax, edi
0x18000715f  jmp     short loc_18000719B
0x180007161  mov     rcx, [rsp+48h+arg_8]
0x180007166  mov     rax, [rcx]
0x180007169  mov     r8, rsi
0x18000716c  mov     rdx, rbp
0x18000716f  mov     rax, [rax]
0x180007172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007177  mov     ebx, eax
0x180007179  mov     rcx, [rsp+48h+arg_8]
0x18000717e  test    rcx, rcx
0x180007181  jz      short loc_180007199
0x180007183  mov     [rsp+48h+arg_8], 0
0x18000718c  mov     rdx, [rcx]
0x18000718f  mov     rax, [rdx+10h]
0x180007193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007198  nop
0x180007199  mov     eax, ebx
0x18000719b  add     rsp, 28h
0x18000719f  pop     rdi
0x1800071a0  pop     rsi
0x1800071a1  pop     rbp
0x1800071a2  pop     rbx
0x1800071a3  retn
```
