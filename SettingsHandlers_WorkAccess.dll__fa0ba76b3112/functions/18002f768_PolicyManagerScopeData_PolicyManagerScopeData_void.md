# PolicyManagerScopeData::~PolicyManagerScopeData(void)

- ea: `0x18002f768`
- end: `0x18002f942`
- name: `??1PolicyManagerScopeData@@QEAA@XZ`
- size: `474`
- prototype: `void __fastcall(PolicyManagerScopeData *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180030924`
- `0x1800506e8`

## callees

- `0x180002f0c`
- `0x18002f69c`
- `0x18002f768`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f843`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f85b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f843`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f85b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f77d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f792`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f7a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f7bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f7d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f7e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f7fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f810`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f77d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f792`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f7a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f7bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f7d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f7e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f7fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f810`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f878`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f8b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f8c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f8fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f910`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f878`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f8b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f8c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f8fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f910`

## pseudocode

```c
void __fastcall PolicyManagerScopeData::~PolicyManagerScopeData(PolicyManagerScopeData *this)
{
  OLECHAR *v2; // rcx
  OLECHAR *v3; // rcx
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx
  OLECHAR *v6; // rcx
  OLECHAR *v7; // rcx
  OLECHAR *v8; // rcx
  OLECHAR *v9; // rcx
  void *v10; // rbx
  HMODULE v11; // rcx
  HMODULE v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rbx

  v2 = *(OLECHAR **)this;
  if ( v2 )
    SysFreeString(v2);
  v3 = (OLECHAR *)*((_QWORD *)this + 2);
  if ( v3 )
    SysFreeString(v3);
  v4 = (OLECHAR *)*((_QWORD *)this + 3);
  if ( v4 )
    SysFreeString(v4);
  v5 = (OLECHAR *)*((_QWORD *)this + 4);
  if ( v5 )
    SysFreeString(v5);
  v6 = (OLECHAR *)*((_QWORD *)this + 1);
  if ( v6 )
    SysFreeString(v6);
  v7 = (OLECHAR *)*((_QWORD *)this + 5);
  if ( v7 )
    SysFreeString(v7);
  v8 = (OLECHAR *)*((_QWORD *)this + 6);
  if ( v8 )
    SysFreeString(v8);
  v9 = (OLECHAR *)*((_QWORD *)this + 7);
  if ( v9 )
    SysFreeString(v9);
  v10 = (void *)*((_QWORD *)this + 12);
  if ( v10 )
  {
    PolicyManagerPolicyMetaData::~PolicyManagerPolicyMetaData(*((PolicyManagerPolicyMetaData **)this + 12));
    operator delete(v10, (const struct std::nothrow_t *)0x78);
  }
  v11 = (HMODULE)*((_QWORD *)this + 13);
  if ( v11 )
    FreeLibrary(v11);
  v12 = (HMODULE)*((_QWORD *)this + 18);
  if ( v12 )
    FreeLibrary(v12);
  v13 = *((_QWORD *)this + 14);
  if ( v13 )
  {
    do
    {
      v14 = *(_QWORD *)(v13 + 16);
      CoTaskMemFree(*(LPVOID *)(v13 + 8));
      CoTaskMemFree(*((LPVOID *)this + 14));
      *((_QWORD *)this + 14) = v14;
      v13 = v14;
    }
    while ( v14 );
  }
  v15 = *((_QWORD *)this + 15);
  *((_QWORD *)this + 14) = 0;
  if ( v15 )
  {
    do
    {
      v16 = *(_QWORD *)(v15 + 16);
      CoTaskMemFree(*(LPVOID *)(v15 + 8));
      CoTaskMemFree(*((LPVOID *)this + 15));
      *((_QWORD *)this + 15) = v16;
      v15 = v16;
    }
    while ( v16 );
  }
  v17 = *((_QWORD *)this + 16);
  *((_QWORD *)this + 15) = 0;
  if ( v17 )
  {
    do
    {
      v18 = *(_QWORD *)(v17 + 16);
      CoTaskMemFree(*(LPVOID *)(v17 + 8));
      CoTaskMemFree(*((LPVOID *)this + 16));
      *((_QWORD *)this + 16) = v18;
      v17 = v18;
    }
    while ( v18 );
  }
  *((_QWORD *)this + 16) = 0;
}

```

## disassembly

```asm
0x18002f768  mov     [rsp+arg_0], rbx
0x18002f76d  push    rdi
0x18002f76e  sub     rsp, 20h
0x18002f772  mov     rdi, rcx
0x18002f775  mov     rcx, [rcx]; bstrString
0x18002f778  test    rcx, rcx
0x18002f77b  jz      short loc_18002F789
0x18002f77d  call    cs:__imp_SysFreeString
0x18002f784  nop     dword ptr [rax+rax+00h]
0x18002f789  mov     rcx, [rdi+10h]; bstrString
0x18002f78d  test    rcx, rcx
0x18002f790  jz      short loc_18002F79E
0x18002f792  call    cs:__imp_SysFreeString
0x18002f799  nop     dword ptr [rax+rax+00h]
0x18002f79e  mov     rcx, [rdi+18h]; bstrString
0x18002f7a2  test    rcx, rcx
0x18002f7a5  jz      short loc_18002F7B3
0x18002f7a7  call    cs:__imp_SysFreeString
0x18002f7ae  nop     dword ptr [rax+rax+00h]
0x18002f7b3  mov     rcx, [rdi+20h]; bstrString
0x18002f7b7  test    rcx, rcx
0x18002f7ba  jz      short loc_18002F7C8
0x18002f7bc  call    cs:__imp_SysFreeString
0x18002f7c3  nop     dword ptr [rax+rax+00h]
0x18002f7c8  mov     rcx, [rdi+8]; bstrString
0x18002f7cc  test    rcx, rcx
0x18002f7cf  jz      short loc_18002F7DD
0x18002f7d1  call    cs:__imp_SysFreeString
0x18002f7d8  nop     dword ptr [rax+rax+00h]
0x18002f7dd  mov     rcx, [rdi+28h]; bstrString
0x18002f7e1  test    rcx, rcx
0x18002f7e4  jz      short loc_18002F7F2
0x18002f7e6  call    cs:__imp_SysFreeString
0x18002f7ed  nop     dword ptr [rax+rax+00h]
0x18002f7f2  mov     rcx, [rdi+30h]; bstrString
0x18002f7f6  test    rcx, rcx
0x18002f7f9  jz      short loc_18002F807
0x18002f7fb  call    cs:__imp_SysFreeString
0x18002f802  nop     dword ptr [rax+rax+00h]
0x18002f807  mov     rcx, [rdi+38h]; bstrString
0x18002f80b  test    rcx, rcx
0x18002f80e  jz      short loc_18002F81C
0x18002f810  call    cs:__imp_SysFreeString
0x18002f817  nop     dword ptr [rax+rax+00h]
0x18002f81c  mov     rbx, [rdi+60h]
0x18002f820  test    rbx, rbx
0x18002f823  jz      short loc_18002F83A
0x18002f825  mov     rcx, rbx; this
0x18002f828  call    ??1PolicyManagerPolicyMetaData@@QEAA@XZ; PolicyManagerPolicyMetaData::~PolicyManagerPolicyMetaData(void)
0x18002f82d  mov     edx, 78h ; 'x'; struct std::nothrow_t *
0x18002f832  mov     rcx, rbx; void *
0x18002f835  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f83a  mov     rcx, [rdi+68h]; hLibModule
0x18002f83e  test    rcx, rcx
0x18002f841  jz      short loc_18002F84F
0x18002f843  call    cs:__imp_FreeLibrary
0x18002f84a  nop     dword ptr [rax+rax+00h]
0x18002f84f  mov     rcx, [rdi+90h]; hLibModule
0x18002f856  test    rcx, rcx
0x18002f859  jz      short loc_18002F867
0x18002f85b  call    cs:__imp_FreeLibrary
0x18002f862  nop     dword ptr [rax+rax+00h]
0x18002f867  mov     rcx, [rdi+70h]
0x18002f86b  test    rcx, rcx
0x18002f86e  jz      short loc_18002F8A0
0x18002f870  mov     rbx, [rcx+10h]
0x18002f874  mov     rcx, [rcx+8]; pv
0x18002f878  call    cs:__imp_CoTaskMemFree
0x18002f87f  nop     dword ptr [rax+rax+00h]
0x18002f884  mov     rcx, [rdi+70h]; pv
0x18002f888  call    cs:__imp_CoTaskMemFree
0x18002f88f  nop     dword ptr [rax+rax+00h]
0x18002f894  mov     [rdi+70h], rbx
0x18002f898  mov     rcx, rbx
0x18002f89b  test    rbx, rbx
0x18002f89e  jnz     short loc_18002F870
0x18002f8a0  mov     rcx, [rdi+78h]
0x18002f8a4  mov     qword ptr [rdi+70h], 0
0x18002f8ac  test    rcx, rcx
0x18002f8af  jz      short loc_18002F8E1
0x18002f8b1  mov     rbx, [rcx+10h]
0x18002f8b5  mov     rcx, [rcx+8]; pv
0x18002f8b9  call    cs:__imp_CoTaskMemFree
0x18002f8c0  nop     dword ptr [rax+rax+00h]
0x18002f8c5  mov     rcx, [rdi+78h]; pv
0x18002f8c9  call    cs:__imp_CoTaskMemFree
0x18002f8d0  nop     dword ptr [rax+rax+00h]
0x18002f8d5  mov     [rdi+78h], rbx
0x18002f8d9  mov     rcx, rbx
0x18002f8dc  test    rbx, rbx
0x18002f8df  jnz     short loc_18002F8B1
0x18002f8e1  mov     rcx, [rdi+80h]
0x18002f8e8  mov     qword ptr [rdi+78h], 0
0x18002f8f0  test    rcx, rcx
0x18002f8f3  jz      short loc_18002F92B
0x18002f8f5  mov     rbx, [rcx+10h]
0x18002f8f9  mov     rcx, [rcx+8]; pv
0x18002f8fd  call    cs:__imp_CoTaskMemFree
0x18002f904  nop     dword ptr [rax+rax+00h]
0x18002f909  mov     rcx, [rdi+80h]; pv
0x18002f910  call    cs:__imp_CoTaskMemFree
0x18002f917  nop     dword ptr [rax+rax+00h]
0x18002f91c  mov     [rdi+80h], rbx
0x18002f923  mov     rcx, rbx
0x18002f926  test    rbx, rbx
0x18002f929  jnz     short loc_18002F8F5
0x18002f92b  mov     rbx, [rsp+28h+arg_0]
0x18002f930  mov     qword ptr [rdi+80h], 0
0x18002f93b  add     rsp, 20h
0x18002f93f  pop     rdi
0x18002f940  retn
```
