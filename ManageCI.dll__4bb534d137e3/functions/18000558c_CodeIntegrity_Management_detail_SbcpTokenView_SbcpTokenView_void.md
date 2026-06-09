# CodeIntegrity::Management::detail::SbcpTokenView::~SbcpTokenView(void)

- ea: `0x18000558c`
- end: `0x1800055d1`
- name: `??1SbcpTokenView@detail@Management@CodeIntegrity@@IEAA@XZ`
- size: `69`
- prototype: `void __fastcall(CodeIntegrity::Management::detail::SbcpTokenView *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005494`
- `0x1800057a8`

## callees

- `0x180005370`
- `0x18000830c`
- `0x180008474`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::detail::SbcpTokenView::~SbcpTokenView(
        CodeIntegrity::Management::detail::SbcpTokenView *this)
{
  *(_QWORD *)this = &CodeIntegrity::Management::detail::SbcpTokenView::`vftable';
  std::vector<unsigned char>::_Tidy((char *)this + 112);
  std::vector<unsigned char>::_Tidy((char *)this + 88);
  std::wstring::_Tidy_deallocate((char *)this + 56);
  std::wstring::_Tidy_deallocate((char *)this + 24);
  wil::details::unique_storage<wil::details::resource_policy<_SECUREBOOT_POLICY *,void (*)(_SECUREBOOT_POLICY *),&void SbFreePolicy(_SECUREBOOT_POLICY *),wistd::integral_constant<unsigned __int64,0>,_SECUREBOOT_POLICY *,_SECUREBOOT_POLICY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECUREBOOT_POLICY *,void (*)(_SECUREBOOT_POLICY *),&void SbFreePolicy(_SECUREBOOT_POLICY *),wistd::integral_constant<unsigned __int64,0>,_SECUREBOOT_POLICY *,_SECUREBOOT_POLICY *,0,std::nullptr_t>>((char *)this + 16);
}

```

## disassembly

```asm
0x18000558c  push    rbx
0x18000558e  sub     rsp, 20h
0x180005592  lea     rax, ??_7SbcpTokenView@detail@Management@CodeIntegrity@@6B@; const CodeIntegrity::Management::detail::SbcpTokenView::`vftable'
0x180005599  mov     rbx, rcx
0x18000559c  mov     [rcx], rax
0x18000559f  add     rcx, 70h ; 'p'
0x1800055a3  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800055a8  lea     rcx, [rbx+58h]
0x1800055ac  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800055b1  lea     rcx, [rbx+38h]
0x1800055b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800055ba  lea     rcx, [rbx+18h]
0x1800055be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800055c3  lea     rcx, [rbx+10h]
0x1800055c7  add     rsp, 20h
0x1800055cb  pop     rbx
0x1800055cc  jmp     ??1?$unique_storage@U?$resource_policy@PEAU_SECUREBOOT_POLICY@@P6AXPEAU1@@Z$1?SbFreePolicy@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECUREBOOT_POLICY *,void (*)(_SECUREBOOT_POLICY *),&SbFreePolicy(_SECUREBOOT_POLICY *),wistd::integral_constant<unsigned __int64,0>,_SECUREBOOT_POLICY *,_SECUREBOOT_POLICY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECUREBOOT_POLICY *,void (*)(_SECUREBOOT_POLICY *),&SbFreePolicy(_SECUREBOOT_POLICY *),wistd::integral_constant<unsigned __int64,0>,_SECUREBOOT_POLICY *,_SECUREBOOT_POLICY *,0,std::nullptr_t>>(void)
```
