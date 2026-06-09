# Microsoft::WRL::Details::MakeAndInitialize<CreateSystemObjectServer,ICreateObject,>(ICreateObject * *)

- ea: `0x140006680`
- end: `0x14000677f`
- name: `??$MakeAndInitialize@VCreateSystemObjectServer@@UICreateObject@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUICreateObject@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140007ad0`

## callees

- `0x1400021a8`
- `0x140006680`
- `0x1400071f4`
- `0x140007360`
- `0x1400084f0`
- `0x140009374`
- `0x14000a010`

## string_xrefs

- `0x1400066e7`: `SOFTWARE\Microsoft\Windows\CurrentVersion\CloudExperienceHost\Broker\ElevatedClsids`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CreateSystemObjectServer,ICreateObject,>(_QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  unsigned int v4; // edi
  __int64 v5; // rcx
  _QWORD *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v7 = v2;
  if ( v2 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>(v2);
    *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICreateObject>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v3[2] = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Broker\\ElevatedClsids";
    *v3 = &CreateSystemObjectServer::`vftable';
    v7 = 0;
    *a1 = 0;
    if ( (unsigned int)InlineIsEqualGUID(
                         &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                         &GUID_00000000_0000_0000_c000_000000000046) )
    {
      *a1 = v3;
      (*(void (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
      v4 = 0;
    }
    else if ( (unsigned int)InlineIsEqualGUID(v5, v5) )
    {
      *a1 = v3;
      v4 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
    }
    else
    {
      v4 = -2147467262;
    }
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(v3);
  }
  else
  {
    v4 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>(&v7);
  return v4;
}

```

## disassembly

```asm
0x140006680  mov     [rsp+arg_8], rbx
0x140006685  push    rdi
0x140006686  sub     rsp, 20h
0x14000668a  mov     rdi, rcx
0x14000668d  mov     qword ptr [rcx], 0
0x140006694  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000669b  mov     ecx, 18h; unsigned __int64
0x1400066a0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400066a5  mov     rbx, rax
0x1400066a8  mov     [rsp+28h+arg_0], rax
0x1400066ad  test    rax, rax
0x1400066b0  jnz     short loc_1400066BC
0x1400066b2  mov     edi, 8007000Eh
0x1400066b7  jmp     loc_140006768
0x1400066bc  mov     rcx, rbx
0x1400066bf  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>(void)
0x1400066c4  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICreateObject@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICreateObject>::`vftable'
0x1400066cb  mov     [rbx], rcx
0x1400066ce  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400066d5  test    rcx, rcx
0x1400066d8  jz      short loc_1400066E7
0x1400066da  mov     rax, [rcx]
0x1400066dd  mov     rax, [rax+8]
0x1400066e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066e6  nop
0x1400066e7  lea     rax, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400066ee  mov     [rbx+10h], rax
0x1400066f2  lea     rax, ??_7CreateSystemObjectServer@@6B@; const CreateSystemObjectServer::`vftable'
0x1400066f9  mov     [rbx], rax
0x1400066fc  mov     [rsp+28h+arg_0], 0
0x140006705  mov     qword ptr [rdi], 0
0x14000670c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140006713  lea     rcx, _GUID_75121952_e0d0_43e5_9380_1d80483acf72
0x14000671a  call    InlineIsEqualGUID
0x14000671f  test    eax, eax
0x140006721  jnz     short loc_14000674C
0x140006723  mov     rdx, rcx
0x140006726  call    InlineIsEqualGUID
0x14000672b  test    eax, eax
0x14000672d  jz      short loc_140006745
0x14000672f  mov     [rdi], rbx
0x140006732  xor     edi, edi
0x140006734  mov     rax, [rbx]
0x140006737  mov     rcx, rbx
0x14000673a  mov     rax, [rax+8]
0x14000673e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006743  jmp     short loc_140006760
0x140006745  mov     edi, 80004002h
0x14000674a  jmp     short loc_140006760
0x14000674c  mov     [rdi], rbx
0x14000674f  mov     rax, [rbx]
0x140006752  mov     rcx, rbx
0x140006755  mov     rax, [rax+8]
0x140006759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000675e  xor     edi, edi
0x140006760  mov     rcx, rbx
0x140006763  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)
0x140006768  lea     rcx, [rsp+28h+arg_0]
0x14000676d  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>(void)
0x140006772  mov     eax, edi
0x140006774  mov     rbx, [rsp+28h+arg_8]
0x140006779  add     rsp, 20h
0x14000677d  pop     rdi
0x14000677e  retn
```
