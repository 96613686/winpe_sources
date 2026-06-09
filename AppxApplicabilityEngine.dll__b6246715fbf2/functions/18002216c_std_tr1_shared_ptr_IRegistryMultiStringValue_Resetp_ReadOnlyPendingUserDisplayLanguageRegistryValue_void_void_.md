# std::tr1::shared_ptr<IRegistryMultiStringValue>::_Resetp<ReadOnlyPendingUserDisplayLanguageRegistryValue,void (*)(void *)>(ReadOnlyPendingUserDisplayLanguageRegistryValue *,void (*)(void *))

- ea: `0x18002216c`
- end: `0x1800221d7`
- name: `??$_Resetp@VReadOnlyPendingUserDisplayLanguageRegistryValue@@P6AXPEAX@Z@?$shared_ptr@VIRegistryMultiStringValue@@@tr1@std@@AEAAXPEAVReadOnlyPendingUserDisplayLanguageRegistryValue@@P6AXPEAX@Z@Z`
- size: `107`
- prototype: `__int64 __fastcall(__int64, struct IUserLanguagesRegistrar *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ddc0`

## callees

- `0x180011a64`
- `0x180021098`
- `0x18002216c`

## pseudocode

```c
__int64 __fastcall std::tr1::shared_ptr<IRegistryMultiStringValue>::_Resetp<ReadOnlyPendingUserDisplayLanguageRegistryValue,void (*)(void *)>(
        __int64 a1,
        struct IUserLanguagesRegistrar *a2)
{
  _DWORD *v4; // rax
  __int64 result; // rax

  try
  {
    v4 = operator new(0x20u);
    if ( v4 )
    {
      v4[2] = 1;
      v4[3] = 1;
      *(_QWORD *)v4 = &std::tr1::_Ref_count_del<ReadOnlyPendingUserDisplayLanguageRegistryValue,void (*)(void *)>::`vftable';
      *((_QWORD *)v4 + 2) = a2;
      *((_QWORD *)v4 + 3) = UserLanguages::IUserLanguagesRegistrarNullDeleter;
    }
    result = std::tr1::_Ptr_base<IRegistryMultiStringValue>::_Reset0(a1, a2, v4);
  }
  catch ( ... )
  {
    UserLanguages::IUserLanguagesRegistrarNullDeleter(a2);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18002216c  mov     [rsp+arg_8], rdx
0x180022171  push    rdi
0x180022172  sub     rsp, 30h
0x180022176  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002217f  mov     [rsp+38h+arg_0], rbx
0x180022184  mov     rbx, rdx
0x180022187  mov     rdi, rcx
0x18002218a  mov     ecx, 20h ; ' '; Size
0x18002218f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022194  test    rax, rax
0x180022197  jz      short loc_1800221BD
0x180022199  mov     ecx, 1
0x18002219e  mov     [rax+8], ecx
0x1800221a1  mov     [rax+0Ch], ecx
0x1800221a4  lea     rcx, ??_7?$_Ref_count_del@VReadOnlyPendingUserDisplayLanguageRegistryValue@@P6AXPEAX@Z@tr1@std@@6B@; const std::tr1::_Ref_count_del<ReadOnlyPendingUserDisplayLanguageRegistryValue,void (*)(void *)>::`vftable'
0x1800221ab  mov     [rax], rcx
0x1800221ae  mov     [rax+10h], rbx
0x1800221b2  lea     rcx, ?IUserLanguagesRegistrarNullDeleter@UserLanguages@@SAXPEAVIUserLanguagesRegistrar@@@Z; UserLanguages::IUserLanguagesRegistrarNullDeleter(IUserLanguagesRegistrar *)
0x1800221b9  mov     [rax+18h], rcx
0x1800221bd  mov     r8, rax
0x1800221c0  mov     rdx, rbx
0x1800221c3  mov     rcx, rdi
0x1800221c6  call    ?_Reset0@?$_Ptr_base@VIRegistryMultiStringValue@@@tr1@std@@QEAAXPEAVIRegistryMultiStringValue@@PEAV_Ref_count_base@23@@Z; std::tr1::_Ptr_base<IRegistryMultiStringValue>::_Reset0(IRegistryMultiStringValue *,std::tr1::_Ref_count_base *)
0x1800221cb  nop
0x1800221cc  mov     rbx, [rsp+38h+arg_0]
0x1800221d1  add     rsp, 30h
0x1800221d5  pop     rdi
0x1800221d6  retn
```
