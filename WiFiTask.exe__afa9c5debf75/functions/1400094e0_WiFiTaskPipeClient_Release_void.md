# WiFiTaskPipeClient::Release(void)

- ea: `0x1400094e0`
- end: `0x140009589`
- name: `?Release@WiFiTaskPipeClient@@UEAAKXZ`
- size: `169`
- prototype: `__int64 __fastcall(WiFiTaskPipeClient *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task`

## callees

- `0x1400016c4`
- `0x1400094e0`
- `0x14000b5d4`
- `0x140012010`

## pseudocode

```c
__int64 __fastcall WiFiTaskPipeClient::Release(WiFiTaskPipeClient *this)
{
  char IsEnabled; // al
  unsigned __int32 v3; // edi

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_56366472>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_56366472>::GetImpl'::`2'::impl);
  v3 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( IsEnabled )
  {
    if ( !v3 )
    {
      if ( this )
      {
        *(_QWORD *)this = &WiFiTaskPipeClient::`vftable';
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2));
        *((_QWORD *)this + 2) = 0;
        operator delete(this);
      }
    }
    return v3;
  }
  else if ( v3 )
  {
    return *((unsigned int *)this + 2);
  }
  else
  {
    if ( this )
    {
      *(_QWORD *)this = &WiFiTaskPipeClient::`vftable';
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2));
      *((_QWORD *)this + 2) = 0;
      operator delete(this);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1400094e0  mov     [rsp+arg_0], rbx
0x1400094e5  push    rdi
0x1400094e6  sub     rsp, 20h
0x1400094ea  mov     rbx, rcx
0x1400094ed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NetworkUX_BugFix_56366472@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_56366472@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_56366472> `wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_56366472>::GetImpl(void)'::`2'::impl
0x1400094f4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_56366472@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_56366472>::__private_IsEnabled(void)
0x1400094f9  or      edi, 0FFFFFFFFh
0x1400094fc  lock xadd [rbx+8], edi
0x140009501  dec     edi
0x140009503  test    al, al
0x140009505  jz      short loc_140009541
0x140009507  test    edi, edi
0x140009509  jnz     short loc_14000953D
0x14000950b  test    rbx, rbx
0x14000950e  jz      short loc_14000953D
0x140009510  lea     rax, ??_7WiFiTaskPipeClient@@6B@; const WiFiTaskPipeClient::`vftable'
0x140009517  mov     [rbx], rax
0x14000951a  mov     rcx, [rbx+10h]
0x14000951e  mov     rdx, [rcx]
0x140009521  mov     rax, [rdx+18h]
0x140009525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000952a  mov     qword ptr [rbx+10h], 0
0x140009532  lea     edx, [rdi+18h]
0x140009535  mov     rcx, rbx; Block
0x140009538  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000953d  mov     eax, edi
0x14000953f  jmp     short loc_14000957E
0x140009541  test    edi, edi
0x140009543  jnz     short loc_14000957B
0x140009545  test    rbx, rbx
0x140009548  jz      short loc_140009577
0x14000954a  lea     rax, ??_7WiFiTaskPipeClient@@6B@; const WiFiTaskPipeClient::`vftable'
0x140009551  mov     [rbx], rax
0x140009554  mov     rcx, [rbx+10h]
0x140009558  mov     rax, [rcx]
0x14000955b  mov     rax, [rax+18h]
0x14000955f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009564  mov     qword ptr [rbx+10h], 0
0x14000956c  lea     edx, [rdi+18h]
0x14000956f  mov     rcx, rbx; Block
0x140009572  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140009577  xor     eax, eax
0x140009579  jmp     short loc_14000957E
0x14000957b  mov     eax, [rbx+8]
0x14000957e  mov     rbx, [rsp+28h+arg_0]
0x140009583  add     rsp, 20h
0x140009587  pop     rdi
0x140009588  retn
```
