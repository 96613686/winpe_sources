# SRCache_GetDefaultAccountSid

- ea: `0x18000de90`
- end: `0x18000df17`
- name: `SRCache_GetDefaultAccountSid`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003d78`
- `0x180004650`
- `0x18000940c`
- `0x18000db3c`
- `0x18000de90`

## string_xrefs

- `0x18000decd`: `onecore\base\appmodel\staterepository\core\lib\srcache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SRCache_GetDefaultAccountSid(_QWORD *a1)
{
  void *v2; // rdx
  StateRepository::Security *v3; // rcx
  void *v4; // rax
  int DefaultAccountSid; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v10; // [rsp+38h] [rbp+10h] BYREF

  wil::AcquireSRWLockExclusive(&v10, &unk_1800186A0);
  v4 = (void *)qword_1800186A8;
  if ( !qword_1800186A8 )
  {
    DefaultAccountSid = StateRepository::Security::CreateDefaultAccountSid(v3, v2);
    v6 = DefaultAccountSid;
    if ( DefaultAccountSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcache.cpp",
        (const char *)(unsigned int)DefaultAccountSid,
        v8);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
      return v6;
    }
    v4 = &unk_1800186B0;
    qword_1800186A8 = (__int64)&unk_1800186B0;
  }
  *a1 = v4;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  return 0;
}

```

## disassembly

```asm
0x18000de90  mov     [rsp+arg_0], rbx
0x18000de95  push    rdi; int
0x18000de96  sub     rsp, 20h
0x18000de9a  mov     rdi, rcx
0x18000de9d  lea     rdx, unk_1800186A0
0x18000dea4  lea     rcx, [rsp+28h+arg_8]
0x18000dea9  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18000deae  mov     rax, cs:qword_1800186A8
0x18000deb5  test    rax, rax
0x18000deb8  jnz     short loc_18000DEFC
0x18000deba  call    ?CreateDefaultAccountSid@Security@StateRepository@@YAJPEAXK@Z; StateRepository::Security::CreateDefaultAccountSid(void *,ulong)
0x18000debf  mov     ebx, eax
0x18000dec1  test    eax, eax
0x18000dec3  jns     short loc_18000DEEE
0x18000dec5  mov     rcx, [rsp+28h]; this
0x18000deca  mov     r9d, eax; char *
0x18000decd  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x18000ded4  mov     edx, 7Bh ; '{'; void *
0x18000ded9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dede  nop
0x18000dedf  lea     rcx, [rsp+28h+arg_8]
0x18000dee4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000dee9  nop
0x18000deea  mov     eax, ebx
0x18000deec  jmp     short loc_18000DF0C
0x18000deee  lea     rax, unk_1800186B0
0x18000def5  mov     cs:qword_1800186A8, rax
0x18000defc  mov     [rdi], rax
0x18000deff  lea     rcx, [rsp+28h+arg_8]
0x18000df04  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000df09  nop
0x18000df0a  xor     eax, eax
0x18000df0c  mov     rbx, [rsp+28h+arg_0]
0x18000df11  add     rsp, 20h
0x18000df15  pop     rdi
0x18000df16  retn
```
