# PolicyManagerScopeData::~PolicyManagerScopeData(void)

- ea: `0x1800ce630`
- end: `0x1800ce7a9`
- name: `??1PolicyManagerScopeData@@QEAA@XZ`
- size: `377`
- prototype: `void __fastcall(PolicyManagerScopeData *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800cf734`
- `0x1801362cb`

## callees

- `0x18000be80`
- `0x1800ce594`
- `0x1800ce630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ce6db`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ce6ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ce6db`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ce6ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce645`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce654`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce663`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce672`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce681`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce690`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce69f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce6ae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce645`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce654`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce663`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce672`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce681`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce690`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce69f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ce6ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce704`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce70e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce739`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce743`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce77e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce704`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce70e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce739`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce743`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce77e`

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
    operator delete(v10);
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
0x1800ce630  mov     [rsp+arg_0], rbx
0x1800ce635  push    rdi
0x1800ce636  sub     rsp, 20h
0x1800ce63a  mov     rdi, rcx
0x1800ce63d  mov     rcx, [rcx]; bstrString
0x1800ce640  test    rcx, rcx
0x1800ce643  jz      short loc_1800CE64B
0x1800ce645  call    cs:__imp_SysFreeString
0x1800ce64b  mov     rcx, [rdi+10h]; bstrString
0x1800ce64f  test    rcx, rcx
0x1800ce652  jz      short loc_1800CE65A
0x1800ce654  call    cs:__imp_SysFreeString
0x1800ce65a  mov     rcx, [rdi+18h]; bstrString
0x1800ce65e  test    rcx, rcx
0x1800ce661  jz      short loc_1800CE669
0x1800ce663  call    cs:__imp_SysFreeString
0x1800ce669  mov     rcx, [rdi+20h]; bstrString
0x1800ce66d  test    rcx, rcx
0x1800ce670  jz      short loc_1800CE678
0x1800ce672  call    cs:__imp_SysFreeString
0x1800ce678  mov     rcx, [rdi+8]; bstrString
0x1800ce67c  test    rcx, rcx
0x1800ce67f  jz      short loc_1800CE687
0x1800ce681  call    cs:__imp_SysFreeString
0x1800ce687  mov     rcx, [rdi+28h]; bstrString
0x1800ce68b  test    rcx, rcx
0x1800ce68e  jz      short loc_1800CE696
0x1800ce690  call    cs:__imp_SysFreeString
0x1800ce696  mov     rcx, [rdi+30h]; bstrString
0x1800ce69a  test    rcx, rcx
0x1800ce69d  jz      short loc_1800CE6A5
0x1800ce69f  call    cs:__imp_SysFreeString
0x1800ce6a5  mov     rcx, [rdi+38h]; bstrString
0x1800ce6a9  test    rcx, rcx
0x1800ce6ac  jz      short loc_1800CE6B4
0x1800ce6ae  call    cs:__imp_SysFreeString
0x1800ce6b4  mov     rbx, [rdi+60h]
0x1800ce6b8  test    rbx, rbx
0x1800ce6bb  jz      short loc_1800CE6D2
0x1800ce6bd  mov     rcx, rbx; this
0x1800ce6c0  call    ??1PolicyManagerPolicyMetaData@@QEAA@XZ; PolicyManagerPolicyMetaData::~PolicyManagerPolicyMetaData(void)
0x1800ce6c5  mov     edx, 78h ; 'x'
0x1800ce6ca  mov     rcx, rbx; Block
0x1800ce6cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ce6d2  mov     rcx, [rdi+68h]; hLibModule
0x1800ce6d6  test    rcx, rcx
0x1800ce6d9  jz      short loc_1800CE6E1
0x1800ce6db  call    cs:__imp_FreeLibrary
0x1800ce6e1  mov     rcx, [rdi+90h]; hLibModule
0x1800ce6e8  test    rcx, rcx
0x1800ce6eb  jz      short loc_1800CE6F3
0x1800ce6ed  call    cs:__imp_FreeLibrary
0x1800ce6f3  mov     rcx, [rdi+70h]
0x1800ce6f7  test    rcx, rcx
0x1800ce6fa  jz      short loc_1800CE720
0x1800ce6fc  mov     rbx, [rcx+10h]
0x1800ce700  mov     rcx, [rcx+8]; pv
0x1800ce704  call    cs:__imp_CoTaskMemFree
0x1800ce70a  mov     rcx, [rdi+70h]; pv
0x1800ce70e  call    cs:__imp_CoTaskMemFree
0x1800ce714  mov     [rdi+70h], rbx
0x1800ce718  mov     rcx, rbx
0x1800ce71b  test    rbx, rbx
0x1800ce71e  jnz     short loc_1800CE6FC
0x1800ce720  mov     rcx, [rdi+78h]
0x1800ce724  mov     qword ptr [rdi+70h], 0
0x1800ce72c  test    rcx, rcx
0x1800ce72f  jz      short loc_1800CE755
0x1800ce731  mov     rbx, [rcx+10h]
0x1800ce735  mov     rcx, [rcx+8]; pv
0x1800ce739  call    cs:__imp_CoTaskMemFree
0x1800ce73f  mov     rcx, [rdi+78h]; pv
0x1800ce743  call    cs:__imp_CoTaskMemFree
0x1800ce749  mov     [rdi+78h], rbx
0x1800ce74d  mov     rcx, rbx
0x1800ce750  test    rbx, rbx
0x1800ce753  jnz     short loc_1800CE731
0x1800ce755  mov     rcx, [rdi+80h]
0x1800ce75c  mov     qword ptr [rdi+78h], 0
0x1800ce764  test    rcx, rcx
0x1800ce767  jz      short loc_1800CE793
0x1800ce769  mov     rbx, [rcx+10h]
0x1800ce76d  mov     rcx, [rcx+8]; pv
0x1800ce771  call    cs:__imp_CoTaskMemFree
0x1800ce777  mov     rcx, [rdi+80h]; pv
0x1800ce77e  call    cs:__imp_CoTaskMemFree
0x1800ce784  mov     [rdi+80h], rbx
0x1800ce78b  mov     rcx, rbx
0x1800ce78e  test    rbx, rbx
0x1800ce791  jnz     short loc_1800CE769
0x1800ce793  mov     rbx, [rsp+28h+arg_0]
0x1800ce798  mov     qword ptr [rdi+80h], 0
0x1800ce7a3  add     rsp, 20h
0x1800ce7a7  pop     rdi
0x1800ce7a8  retn
```
