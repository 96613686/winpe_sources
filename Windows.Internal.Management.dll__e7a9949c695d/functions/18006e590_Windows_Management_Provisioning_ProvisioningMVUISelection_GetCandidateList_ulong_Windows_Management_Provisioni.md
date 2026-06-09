# Windows::Management::Provisioning::ProvisioningMVUISelection::GetCandidateList(ulong *,Windows::Management::Provisioning::ProvisioningMVUIItem * *)

- ea: `0x18006e590`
- end: `0x18006e709`
- name: `?GetCandidateList@ProvisioningMVUISelection@Provisioning@Management@Windows@@UEAAJPEAKPEAPEAUProvisioningMVUIItem@234@@Z`
- size: `377`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::ProvisioningMVUISelection *__hidden this, unsigned int *, struct Windows::Management::Provisioning::ProvisioningMVUIItem **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a2a4`
- `0x1800170c8`
- `0x18006e250`
- `0x18006e3bc`
- `0x18006e418`
- `0x18006e42c`
- `0x18006e590`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006e67d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006e67d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e6b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e6b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Management::Provisioning::ProvisioningMVUISelection::GetCandidateList(
        Windows::Management::Provisioning::ProvisioningMVUISelection *this,
        unsigned int *a2,
        LPVOID *a3)
{
  __int64 v5; // rsi
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 (__fastcall *v8)(__int64, unsigned int *, __int64); // rbx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // r8
  unsigned int i; // ebx
  _DWORD *v13; // rax
  __int64 v14; // r9
  __int64 v15; // r8
  const WCHAR *v16; // rcx
  __int64 v17; // r9
  __int64 v18; // rdx
  HRESULT String; // eax
  HRESULT v20; // esi
  void *v21; // rcx
  _QWORD v23[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+30h]
  LPVOID pv; // [rsp+78h] [rbp+40h] BYREF

  if ( !a2 || !a3 )
  {
    v6 = -2147024809;
    v7 = 32;
    goto LABEL_19;
  }
  v5 = *((_QWORD *)this + 4);
  if ( !v5 )
  {
    v6 = -2147418113;
    v7 = 33;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\provisioningmvuistatus.cpp",
      (const char *)v6,
      v23[0]);
    return v6;
  }
  std::_Compressed_pair<std::allocator<std::_List_node<CommandResult,void *>>,std::_List_val<std::_List_simple_types<CommandResult>>,1>::_Compressed_pair<std::allocator<std::_List_node<CommandResult,void *>>,std::_List_val<std::_List_simple_types<CommandResult>>,1>(v23);
  v8 = *(__int64 (__fastcall **)(__int64, unsigned int *, __int64))(*(_QWORD *)v5 + 24LL);
  v9 = wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::operator&(v23);
  v10 = v8(v5, a2, v9);
  v6 = v10;
  if ( v10 >= 0 )
  {
    v23[1] = *a2;
    wil::make_unique_cotaskmem<Windows::Management::Provisioning::ProvisioningMVUIItem [0]>(&pv);
    for ( i = 0; ; ++i )
    {
      if ( i >= *a2 )
      {
        *a3 = pv;
        pv = 0;
        wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::~unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>(v23);
        return 0;
      }
      v13 = (_DWORD *)wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::operator[](
                        v23,
                        i,
                        v11,
                        16LL * i);
      *(_DWORD *)((char *)pv + v14) = *v13;
      v16 = *(const WCHAR **)(wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::operator[](
                                v23,
                                i,
                                v15,
                                v14)
                            + 8);
      v18 = -1;
      do
        ++v18;
      while ( v16[v18] );
      String = WindowsCreateString(v16, v18, (HSTRING *)((char *)pv + v17 + 8));
      v20 = String;
      if ( String < 0 )
        break;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\provisioningmvuistatus.cpp",
      (const char *)(unsigned int)String,
      v23[0]);
    v21 = pv;
    pv = 0;
    if ( v21 )
      CoTaskMemFree(v21);
    v6 = v20;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\provisioningmvuistatus.cpp",
      (const char *)(unsigned int)v10,
      v23[0]);
  }
  wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::~unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>(v23);
  return v6;
}

```

## disassembly

```asm
0x18006e590  push    rbp
0x18006e592  push    rbx
0x18006e593  push    rsi
0x18006e594  push    rdi
0x18006e595  push    r14
0x18006e597  push    r15
0x18006e599  mov     rbp, rsp
0x18006e59c  sub     rsp, 38h
0x18006e5a0  mov     r14, r8
0x18006e5a3  mov     rdi, rdx
0x18006e5a6  xor     r15d, r15d
0x18006e5a9  test    rdx, rdx
0x18006e5ac  jz      loc_18006E6DD
0x18006e5b2  test    r8, r8
0x18006e5b5  jz      loc_18006E6DD
0x18006e5bb  mov     rsi, [rcx+20h]
0x18006e5bf  test    rsi, rsi
0x18006e5c2  jnz     short loc_18006E5D1
0x18006e5c4  mov     ebx, 8000FFFFh
0x18006e5c9  lea     edx, [rsi+21h]
0x18006e5cc  jmp     loc_18006E6E7
0x18006e5d1  lea     rcx, [rbp+var_18]
0x18006e5d5  call    ??$?0V?$allocator@U?$_List_node@UCommandResult@@PEAX@std@@@std@@$$V@?$_Compressed_pair@V?$allocator@U?$_List_node@UCommandResult@@PEAX@std@@@std@@V?$_List_val@U?$_List_simple_types@UCommandResult@@@std@@@2@$00@std@@QEAA@U_One_then_variadic_args_t@1@$$QEAV?$allocator@U?$_List_node@UCommandResult@@PEAX@std@@@1@@Z; std::_Compressed_pair<std::allocator<std::_List_node<CommandResult,void *>>,std::_List_val<std::_List_simple_types<CommandResult>>,1>::_Compressed_pair<std::allocator<std::_List_node<CommandResult,void *>>,std::_List_val<std::_List_simple_types<CommandResult>>,1>(std::_One_then_variadic_args_t,std::allocator<std::_List_node<CommandResult,void *>> &&)
0x18006e5da  nop
0x18006e5db  mov     rax, [rsi]
0x18006e5de  mov     rbx, [rax+18h]
0x18006e5e2  lea     rcx, [rbp+var_18]
0x18006e5e6  call    ??I?$unique_any_array_ptr@U_MVUIITem@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAU_MVUIITem@@@Z$1?FreeMVUIItem@Provisioning@Management@Windows@@YAX0@Z@details@3@_K@wil@@QEAAPEAPEAU_MVUIITem@@XZ; wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::operator&(void)
0x18006e5eb  mov     r8, rax
0x18006e5ee  mov     rdx, rdi
0x18006e5f1  mov     rcx, rsi
0x18006e5f4  mov     rax, rbx
0x18006e5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5fc  mov     ebx, eax
0x18006e5fe  test    eax, eax
0x18006e600  jns     short loc_18006E61F
0x18006e602  mov     rcx, [rbp+30h]; this
0x18006e606  mov     r9d, eax; char *
0x18006e609  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006e610  mov     edx, 24h ; '$'; void *
0x18006e615  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e61a  jmp     loc_18006E6BA
0x18006e61f  mov     edx, [rdi]
0x18006e621  mov     [rbp+var_10], rdx
0x18006e625  lea     rcx, [rbp+pv]
0x18006e629  call    ??$make_unique_cotaskmem@$$BY0A@UProvisioningMVUIItem@Provisioning@Management@Windows@@@wil@@YA?AV?$unique_ptr@$$BY0A@UProvisioningMVUIItem@Provisioning@Management@Windows@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<Windows::Management::Provisioning::ProvisioningMVUIItem [0]>(unsigned __int64)
0x18006e62e  mov     ebx, r15d
0x18006e631  cmp     ebx, [rdi]
0x18006e633  jnb     loc_18006E6C5
0x18006e639  mov     r9d, ebx
0x18006e63c  shl     r9, 4
0x18006e640  mov     edx, ebx
0x18006e642  lea     rcx, [rbp+var_18]
0x18006e646  call    ??A?$unique_any_array_ptr@U_MVUIITem@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAU_MVUIITem@@@Z$1?FreeMVUIItem@Provisioning@Management@Windows@@YAX0@Z@details@3@_K@wil@@QEAAAEAU_MVUIITem@@_K@Z; wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::operator[](unsigned __int64)
0x18006e64b  mov     ecx, [rax]
0x18006e64d  mov     rax, [rbp+pv]
0x18006e651  mov     [r9+rax], ecx
0x18006e655  mov     edx, ebx
0x18006e657  lea     rcx, [rbp+var_18]
0x18006e65b  call    ??A?$unique_any_array_ptr@U_MVUIITem@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAU_MVUIITem@@@Z$1?FreeMVUIItem@Provisioning@Management@Windows@@YAX0@Z@details@3@_K@wil@@QEAAAEAU_MVUIITem@@_K@Z; wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::operator[](unsigned __int64)
0x18006e660  mov     rcx, [rax+8]; sourceString
0x18006e664  mov     rax, [rbp+pv]
0x18006e668  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006e66c  inc     rdx; length
0x18006e66f  cmp     [rcx+rdx*2], r15w
0x18006e674  jnz     short loc_18006E66C
0x18006e676  lea     r8, [rax+8]
0x18006e67a  add     r8, r9; string
0x18006e67d  call    cs:__imp_WindowsCreateString
0x18006e683  mov     esi, eax
0x18006e685  test    eax, eax
0x18006e687  js      short loc_18006E68D
0x18006e689  inc     ebx
0x18006e68b  jmp     short loc_18006E631
0x18006e68d  mov     rcx, [rbp+30h]; this
0x18006e691  mov     r9d, esi; char *
0x18006e694  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006e69b  mov     edx, 2Dh ; '-'; void *
0x18006e6a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e6a5  mov     rcx, [rbp+pv]; pv
0x18006e6a9  mov     [rbp+pv], r15
0x18006e6ad  test    rcx, rcx
0x18006e6b0  jz      short loc_18006E6B8
0x18006e6b2  call    cs:__imp_CoTaskMemFree
0x18006e6b8  mov     ebx, esi
0x18006e6ba  lea     rcx, [rbp+var_18]
0x18006e6be  call    ??1?$unique_any_array_ptr@U_MVUIITem@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAU_MVUIITem@@@Z$1?FreeMVUIItem@Provisioning@Management@Windows@@YAX0@Z@details@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::~unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>(void)
0x18006e6c3  jmp     short loc_18006E6FA
0x18006e6c5  mov     rax, [rbp+pv]
0x18006e6c9  mov     [r14], rax
0x18006e6cc  mov     [rbp+pv], r15
0x18006e6d0  lea     rcx, [rbp+var_18]
0x18006e6d4  call    ??1?$unique_any_array_ptr@U_MVUIITem@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAU_MVUIITem@@@Z$1?FreeMVUIItem@Provisioning@Management@Windows@@YAX0@Z@details@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::~unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>(void)
0x18006e6d9  xor     eax, eax
0x18006e6db  jmp     short loc_18006E6FC
0x18006e6dd  mov     ebx, 80070057h
0x18006e6e2  mov     edx, 20h ; ' '; void *
0x18006e6e7  mov     r9d, ebx; char *
0x18006e6ea  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006e6f1  mov     rcx, [rbp+30h]; this
0x18006e6f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e6fa  mov     eax, ebx
0x18006e6fc  add     rsp, 38h
0x18006e700  pop     r15
0x18006e702  pop     r14
0x18006e704  pop     rdi
0x18006e705  pop     rsi
0x18006e706  pop     rbx
0x18006e707  pop     rbp
0x18006e708  retn
```
