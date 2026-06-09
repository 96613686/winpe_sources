# std::default_delete<std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>>>>>::operator()(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>>>> *)

- ea: `0x180011860`
- end: `0x180011888`
- name: `??R?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@@std@@@std@@QEBAXPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@@1@@Z`
- size: `40`
- prototype: `void __fastcall(__int64, _QWORD **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000e850`
- `0x1800113f0`

## callees

- `0x180002ea4`
- `0x180010fb0`
- `0x180011860`

## pseudocode

```c
void __fastcall std::default_delete<std::map<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>>>::operator()(
        __int64 a1,
        _QWORD **a2)
{
  if ( a2 )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x180011860  test    rdx, rdx
0x180011863  jz      short locret_180011887
0x180011865  push    rbx
0x180011866  sub     rsp, 20h
0x18001186a  mov     rcx, rdx
0x18001186d  mov     rbx, rdx
0x180011870  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>(void)
0x180011875  mov     edx, 10h; unsigned __int64
0x18001187a  mov     rcx, rbx; void *
0x18001187d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011882  add     rsp, 20h
0x180011886  pop     rbx
0x180011887  retn
```
