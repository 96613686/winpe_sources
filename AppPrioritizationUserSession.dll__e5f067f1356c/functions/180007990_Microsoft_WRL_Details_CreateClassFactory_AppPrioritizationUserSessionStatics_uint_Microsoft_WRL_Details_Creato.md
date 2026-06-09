# Microsoft::WRL::Details::CreateClassFactory<AppPrioritizationUserSessionStatics>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180007990`
- end: `0x180007aaa`
- name: `??$CreateClassFactory@VAppPrioritizationUserSessionStatics@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `282`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002b38`
- `0x180007990`
- `0x18000868c`
- `0x18000a080`
- `0x18000a6d0`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<AppPrioritizationUserSessionStatics>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char *v7; // rax
  char *v8; // rbx
  __int64 v10; // r8
  __int64 v11; // rdx
  int Interface; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // edi

  v7 = (char *)operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v7 + 8));
  *((_DWORD *)v8 + 11) = 1;
  *((_DWORD *)v8 + 13) = 4;
  *(_QWORD *)v8 = &AppPrioritizationUserSessionStatics::`vftable'{for `IClassFactory'};
  *((_QWORD *)v8 + 1) = &AppPrioritizationUserSessionStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<6>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  v10 = 0x7FFFFFFF;
  while ( 1 )
  {
    v11 = *((unsigned int *)v8 + 11);
    if ( (_DWORD)v11 == 0x7FFFFFFF )
      break;
    if ( (_DWORD)v11 == _InterlockedCompareExchange((volatile signed __int32 *)v8 + 11, v11 + 1, v11) )
    {
      v10 = (unsigned int)(v11 + 1);
      break;
    }
  }
  if ( (v8[52] & 6) == 0 && (_DWORD)v10 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  Microsoft::WRL::ClassFactory<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
    v8,
    v11,
    v10);
  *((_DWORD *)v8 + 13) = *a1;
  Interface = Microsoft::WRL::ClassFactory<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(
                v8,
                a3,
                a4);
  v15 = Interface;
  if ( (*(_BYTE *)a1 & 1) != 0 )
  {
    if ( Interface < 0 )
    {
      *((_DWORD *)v8 + 13) &= 0xFFFFFFFA;
    }
    else
    {
      if ( (*(_BYTE *)a1 & 4) != 0 )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      else
        v8 = 0;
      if ( !v8 )
        return v15;
    }
  }
  Microsoft::WRL::ClassFactory<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
    v8,
    v13,
    v14);
  return v15;
}

```

## disassembly

```asm
0x180007990  mov     [rsp+arg_8], rbx
0x180007995  mov     [rsp+arg_10], rbp
0x18000799a  push    rsi
0x18000799b  push    rdi
0x18000799c  push    r14
0x18000799e  sub     rsp, 20h
0x1800079a2  mov     r14, r9
0x1800079a5  mov     rbp, r8
0x1800079a8  mov     rsi, rcx
0x1800079ab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800079b2  mov     ecx, 38h ; '8'; unsigned __int64
0x1800079b7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800079bc  mov     rbx, rax
0x1800079bf  test    rax, rax
0x1800079c2  jnz     short loc_1800079CE
0x1800079c4  mov     eax, 8007000Eh
0x1800079c9  jmp     loc_180007A97
0x1800079ce  lea     rcx, [rax+8]; this
0x1800079d2  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800079d7  mov     dword ptr [rbx+2Ch], 1
0x1800079de  mov     dword ptr [rbx+34h], 4
0x1800079e5  lea     rax, ??_7AppPrioritizationUserSessionStatics@@6BIClassFactory@@@; const AppPrioritizationUserSessionStatics::`vftable'{for `IClassFactory'}
0x1800079ec  mov     [rbx], rax
0x1800079ef  lea     rax, ??_7AppPrioritizationUserSessionStatics@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$05@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@VNil@523@V6523@V6523@@Details@WRL@Microsoft@@@; const AppPrioritizationUserSessionStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<6>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x1800079f6  mov     [rbx+8], rax
0x1800079fa  mov     r8d, 7FFFFFFFh
0x180007a00  jmp     short loc_180007A0E
0x180007a02  lea     ecx, [rdx+1]
0x180007a05  mov     eax, edx
0x180007a07  lock cmpxchg [rbx+2Ch], ecx
0x180007a0c  jz      short loc_180007A18
0x180007a0e  mov     edx, [rbx+2Ch]
0x180007a11  cmp     edx, r8d
0x180007a14  jnz     short loc_180007A02
0x180007a16  jmp     short loc_180007A1C
0x180007a18  lea     r8d, [rdx+1]
0x180007a1c  test    byte ptr [rbx+34h], 6
0x180007a20  jnz     short loc_180007A40
0x180007a22  cmp     r8d, 2
0x180007a26  jnz     short loc_180007A40
0x180007a28  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007a2f  test    rcx, rcx
0x180007a32  jz      short loc_180007A40
0x180007a34  mov     rax, [rcx]
0x180007a37  mov     rax, [rax+8]
0x180007a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a40  mov     rcx, rbx
0x180007a43  call    ?Release@?$ClassFactory@VFtmBase@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ClassFactory<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180007a48  mov     eax, [rsi]
0x180007a4a  mov     [rbx+34h], eax
0x180007a4d  mov     r8, r14
0x180007a50  mov     rdx, rbp
0x180007a53  mov     rcx, rbx
0x180007a56  call    ?QueryInterface@?$ClassFactory@VFtmBase@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ClassFactory<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)
0x180007a5b  mov     edi, eax
0x180007a5d  test    byte ptr [rsi], 1
0x180007a60  jz      short loc_180007A8D
0x180007a62  test    eax, eax
0x180007a64  js      short loc_180007A89
0x180007a66  test    byte ptr [rsi], 4
0x180007a69  jz      short loc_180007A80
0x180007a6b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007a72  mov     rdx, [rcx]
0x180007a75  mov     rax, [rdx+8]
0x180007a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a7e  jmp     short loc_180007A82
0x180007a80  xor     ebx, ebx
0x180007a82  test    rbx, rbx
0x180007a85  jz      short loc_180007A95
0x180007a87  jmp     short loc_180007A8D
0x180007a89  and     dword ptr [rbx+34h], 0FFFFFFFAh
0x180007a8d  mov     rcx, rbx
0x180007a90  call    ?Release@?$ClassFactory@VFtmBase@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ClassFactory<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180007a95  mov     eax, edi
0x180007a97  mov     rbx, [rsp+38h+arg_8]
0x180007a9c  mov     rbp, [rsp+38h+arg_10]
0x180007aa1  add     rsp, 20h
0x180007aa5  pop     r14
0x180007aa7  pop     rdi
0x180007aa8  pop     rsi
0x180007aa9  retn
```
