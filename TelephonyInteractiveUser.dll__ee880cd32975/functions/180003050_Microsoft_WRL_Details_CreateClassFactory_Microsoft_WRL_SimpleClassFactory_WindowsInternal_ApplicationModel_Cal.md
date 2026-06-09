# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180003050`
- end: `0x180003128`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001de4`
- `0x180003050`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics,0>>(
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
    *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics,0>::`vftable';
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
0x180003050  mov     [rsp+arg_8], rbx
0x180003055  push    rbp
0x180003056  push    rsi
0x180003057  push    rdi
0x180003058  sub     rsp, 20h
0x18000305c  mov     rsi, rcx
0x18000305f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003066  mov     ecx, 18h; unsigned __int64
0x18000306b  mov     rbp, r9
0x18000306e  mov     rdi, r8
0x180003071  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003076  mov     rbx, rax
0x180003079  test    rax, rax
0x18000307c  jz      loc_180003116
0x180003082  mov     dword ptr [rax+0Ch], 1
0x180003089  mov     rcx, rbx
0x18000308c  mov     dword ptr [rax+14h], 4
0x180003093  lea     rax, ??_7?$SimpleClassFactory@VServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics,0>::`vftable'
0x18000309a  mov     [rbx], rax
0x18000309d  mov     rax, cs:off_18001A4B8
0x1800030a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a9  mov     rax, [rbx]
0x1800030ac  mov     rcx, rbx
0x1800030af  mov     rax, [rax+10h]
0x1800030b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b8  mov     eax, [rsi]
0x1800030ba  mov     r8, rbp
0x1800030bd  mov     [rbx+14h], eax
0x1800030c0  mov     rdx, rdi
0x1800030c3  mov     rax, [rbx]
0x1800030c6  mov     rcx, rbx
0x1800030c9  mov     rax, [rax]
0x1800030cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d1  test    byte ptr [rsi], 1
0x1800030d4  mov     edi, eax
0x1800030d6  jz      short loc_180003103
0x1800030d8  test    eax, eax
0x1800030da  js      short loc_1800030FF
0x1800030dc  test    byte ptr [rsi], 4
0x1800030df  jz      short loc_1800030F6
0x1800030e1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800030e8  mov     rdx, [rcx]
0x1800030eb  mov     rax, [rdx+8]
0x1800030ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f4  jmp     short loc_1800030F8
0x1800030f6  xor     ebx, ebx
0x1800030f8  test    rbx, rbx
0x1800030fb  jz      short loc_180003112
0x1800030fd  jmp     short loc_180003103
0x1800030ff  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180003103  mov     rax, [rbx]
0x180003106  mov     rcx, rbx
0x180003109  mov     rax, [rax+10h]
0x18000310d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003112  mov     eax, edi
0x180003114  jmp     short loc_18000311B
0x180003116  mov     eax, 8007000Eh
0x18000311b  mov     rbx, [rsp+38h+arg_8]
0x180003120  add     rsp, 20h
0x180003124  pop     rdi
0x180003125  pop     rsi
0x180003126  pop     rbp
0x180003127  retn
```
