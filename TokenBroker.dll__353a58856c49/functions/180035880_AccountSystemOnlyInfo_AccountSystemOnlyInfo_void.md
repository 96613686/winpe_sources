# AccountSystemOnlyInfo::~AccountSystemOnlyInfo(void)

- ea: `0x180035880`
- end: `0x180035923`
- name: `??1AccountSystemOnlyInfo@@QEAA@XZ`
- size: `163`
- prototype: `void __fastcall(AccountSystemOnlyInfo *__hidden this)`
- caller_count: `19`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180060038`
- `0x180063184`
- `0x1800722ac`
- `0x1800724cc`
- `0x1800729e0`
- `0x1800743a0`
- `0x180074b84`
- `0x18010de6c`
- `0x18010e6c4`
- `0x18010e9f0`
- `0x18010ffac`
- `0x180110268`
- `0x180116366`
- `0x1801164ac`
- `0x180119f66`
- `0x180119fa4`
- `0x18011a022`
- `0x18011a058`
- `0x18011a0ee`

## callees

- `0x180035880`
- `0x1800359ac`
- `0x18008e6b4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800358a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800358b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800358c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800358d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035912`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800358a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800358b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800358c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800358d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035912`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035904`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035904`

## pseudocode

```c
void __fastcall AccountSystemOnlyInfo::~AccountSystemOnlyInfo(AccountSystemOnlyInfo *this)
{
  HSTRING v2; // rcx
  HSTRING v3; // rcx
  HSTRING v4; // rcx
  HSTRING v5; // rcx
  HSTRING v6; // rcx
  void *v7; // rcx

  v2 = (HSTRING)*((_QWORD *)this + 10);
  if ( v2 )
    WindowsDeleteString(v2);
  v3 = (HSTRING)*((_QWORD *)this + 9);
  if ( v3 )
    WindowsDeleteString(v3);
  v4 = (HSTRING)*((_QWORD *)this + 8);
  if ( v4 )
    WindowsDeleteString(v4);
  v5 = (HSTRING)*((_QWORD *)this + 7);
  if ( v5 )
    WindowsDeleteString(v5);
  v6 = (HSTRING)*((_QWORD *)this + 5);
  if ( v6 )
    WindowsDeleteString(v6);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<PerAppAccountData>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<PerAppAccountData>>,void *>>>(
    (char *)this + 24,
    (char *)this + 24,
    *(_QWORD *)(*((_QWORD *)this + 3) + 8LL));
  operator delete(*((void **)this + 3));
  v7 = (void *)*((_QWORD *)this + 1);
  if ( v7 )
    LocalFree(v7);
  if ( *(_QWORD *)this )
    WindowsDeleteString(*(HSTRING *)this);
}

```

## disassembly

```asm
0x180035880  mov     [rsp+arg_0], rbx
0x180035885  push    rdi
0x180035886  sub     rsp, 20h
0x18003588a  mov     rdi, rcx
0x18003588d  mov     rcx, [rcx+50h]; string
0x180035891  test    rcx, rcx
0x180035894  jz      short loc_18003589C
0x180035896  call    cs:__imp_WindowsDeleteString
0x18003589c  mov     rcx, [rdi+48h]; string
0x1800358a0  test    rcx, rcx
0x1800358a3  jz      short loc_1800358AB
0x1800358a5  call    cs:__imp_WindowsDeleteString
0x1800358ab  mov     rcx, [rdi+40h]; string
0x1800358af  test    rcx, rcx
0x1800358b2  jz      short loc_1800358BA
0x1800358b4  call    cs:__imp_WindowsDeleteString
0x1800358ba  mov     rcx, [rdi+38h]; string
0x1800358be  test    rcx, rcx
0x1800358c1  jz      short loc_1800358C9
0x1800358c3  call    cs:__imp_WindowsDeleteString
0x1800358c9  mov     rcx, [rdi+28h]; string
0x1800358cd  test    rcx, rcx
0x1800358d0  jz      short loc_1800358D8
0x1800358d2  call    cs:__imp_WindowsDeleteString
0x1800358d8  lea     rbx, [rdi+18h]
0x1800358dc  mov     r8, [rbx]
0x1800358df  mov     rdx, rbx
0x1800358e2  mov     rcx, rbx
0x1800358e5  mov     r8, [r8+8]
0x1800358e9  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPerAppAccountData@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPerAppAccountData@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPerAppAccountData@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPerAppAccountData@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<PerAppAccountData>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<PerAppAccountData>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<PerAppAccountData>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<PerAppAccountData>>,void *> *)
0x1800358ee  mov     rcx, [rbx]; Block
0x1800358f1  mov     edx, 50h ; 'P'
0x1800358f6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800358fb  mov     rcx, [rdi+8]; hMem
0x1800358ff  test    rcx, rcx
0x180035902  jz      short loc_18003590A
0x180035904  call    cs:__imp_LocalFree
0x18003590a  mov     rcx, [rdi]; string
0x18003590d  test    rcx, rcx
0x180035910  jz      short loc_180035918
0x180035912  call    cs:__imp_WindowsDeleteString
0x180035918  mov     rbx, [rsp+28h+arg_0]
0x18003591d  add     rsp, 20h
0x180035921  pop     rdi
0x180035922  retn
```
