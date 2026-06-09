# Windows::Management::Provisioning::ProvisioningMVUISelection::GetCandidateList(ulong *,Windows::Management::Provisioning::ProvisioningMVUIItem * *)

- ea: `0x18006f9f0`
- end: `0x18006fb76`
- name: `?GetCandidateList@ProvisioningMVUISelection@Provisioning@Management@Windows@@UEAAJPEAKPEAPEAUProvisioningMVUIItem@234@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::ProvisioningMVUISelection *__hidden this, unsigned int *, struct Windows::Management::Provisioning::ProvisioningMVUIItem **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a5c4`
- `0x1800178b8`
- `0x18006f6a0`
- `0x18006f814`
- `0x18006f878`
- `0x18006f88c`
- `0x18006f9f0`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006fadd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006fadd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fb18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fb18`

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
  int v23; // [rsp+20h] [rbp-18h] BYREF
  __int64 v24; // [rsp+28h] [rbp-10h]
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
      v23);
    return v6;
  }
  std::_Compressed_pair<std::allocator<std::_List_node<CommandResult,void *>>,std::_List_val<std::_List_simple_types<CommandResult>>,1>::_Compressed_pair<std::allocator<std::_List_node<CommandResult,void *>>,std::_List_val<std::_List_simple_types<CommandResult>>,1>(&v23);
  v8 = *(__int64 (__fastcall **)(__int64, unsigned int *, __int64))(*(_QWORD *)v5 + 24LL);
  v9 = wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::operator&(&v23);
  v10 = v8(v5, a2, v9);
  v6 = v10;
  if ( v10 >= 0 )
  {
    v24 = *a2;
    wil::make_unique_cotaskmem<Windows::Management::Provisioning::ProvisioningMVUIItem [0]>(&pv);
    for ( i = 0; ; ++i )
    {
      if ( i >= *a2 )
      {
        *a3 = pv;
        pv = 0;
        wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::~unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>(&v23);
        return 0;
      }
      v13 = (_DWORD *)wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::operator[](
                        &v23,
                        i,
                        v11,
                        16LL * i);
      *(_DWORD *)((char *)pv + v14) = *v13;
      v16 = *(const WCHAR **)(wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::operator[](
                                &v23,
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
      v23);
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
      v23);
  }
  wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::~unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>(&v23);
  return v6;
}

```

## disassembly

```asm
0x18006f9f0  push    rbp
0x18006f9f2  push    rbx
0x18006f9f3  push    rsi
0x18006f9f4  push    rdi
0x18006f9f5  push    r14
0x18006f9f7  push    r15
0x18006f9f9  mov     rbp, rsp
0x18006f9fc  sub     rsp, 38h
0x18006fa00  mov     r14, r8
0x18006fa03  mov     rdi, rdx
0x18006fa06  xor     r15d, r15d
0x18006fa09  test    rdx, rdx
0x18006fa0c  jz      loc_18006FB49
0x18006fa12  test    r8, r8
0x18006fa15  jz      loc_18006FB49
0x18006fa1b  mov     rsi, [rcx+20h]
0x18006fa1f  test    rsi, rsi
0x18006fa22  jnz     short loc_18006FA31
0x18006fa24  mov     ebx, 8000FFFFh
0x18006fa29  lea     edx, [rsi+21h]
0x18006fa2c  jmp     loc_18006FB53
0x18006fa31  lea     rcx, [rbp+var_18]
0x18006fa35  call    ??$?0V?$allocator@U?$_List_node@UCommandResult@@PEAX@std@@@std@@$$V@?$_Compressed_pair@V?$allocator@U?$_List_node@UCommandResult@@PEAX@std@@@std@@V?$_List_val@U?$_List_simple_types@UCommandResult@@@std@@@2@$00@std@@QEAA@U_One_then_variadic_args_t@1@$$QEAV?$allocator@U?$_List_node@UCommandResult@@PEAX@std@@@1@@Z; std::_Compressed_pair<std::allocator<std::_List_node<CommandResult,void *>>,std::_List_val<std::_List_simple_types<CommandResult>>,1>::_Compressed_pair<std::allocator<std::_List_node<CommandResult,void *>>,std::_List_val<std::_List_simple_types<CommandResult>>,1>(std::_One_then_variadic_args_t,std::allocator<std::_List_node<CommandResult,void *>> &&)
0x18006fa3a  nop
0x18006fa3b  mov     rax, [rsi]
0x18006fa3e  mov     rbx, [rax+18h]
0x18006fa42  lea     rcx, [rbp+var_18]
0x18006fa46  call    ??I?$unique_any_array_ptr@U_MVUIITem@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAU_MVUIITem@@@Z$1?FreeMVUIItem@Provisioning@Management@Windows@@YAX0@Z@details@3@_K@wil@@QEAAPEAPEAU_MVUIITem@@XZ; wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::operator&(void)
0x18006fa4b  mov     r8, rax
0x18006fa4e  mov     rdx, rdi
0x18006fa51  mov     rcx, rsi
0x18006fa54  mov     rax, rbx
0x18006fa57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fa5c  mov     ebx, eax
0x18006fa5e  test    eax, eax
0x18006fa60  jns     short loc_18006FA7F
0x18006fa62  mov     rcx, [rbp+30h]; this
0x18006fa66  mov     r9d, eax; char *
0x18006fa69  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006fa70  mov     edx, 24h ; '$'; void *
0x18006fa75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fa7a  jmp     loc_18006FB26
0x18006fa7f  mov     edx, [rdi]
0x18006fa81  mov     [rbp+var_10], rdx
0x18006fa85  lea     rcx, [rbp+pv]
0x18006fa89  call    ??$make_unique_cotaskmem@$$BY0A@UProvisioningMVUIItem@Provisioning@Management@Windows@@@wil@@YA?AV?$unique_ptr@$$BY0A@UProvisioningMVUIItem@Provisioning@Management@Windows@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<Windows::Management::Provisioning::ProvisioningMVUIItem [0]>(unsigned __int64)
0x18006fa8e  mov     ebx, r15d
0x18006fa91  cmp     ebx, [rdi]
0x18006fa93  jnb     loc_18006FB31
0x18006fa99  mov     r9d, ebx
0x18006fa9c  shl     r9, 4
0x18006faa0  mov     edx, ebx
0x18006faa2  lea     rcx, [rbp+var_18]
0x18006faa6  call    ??A?$unique_any_array_ptr@U_MVUIITem@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAU_MVUIITem@@@Z$1?FreeMVUIItem@Provisioning@Management@Windows@@YAX0@Z@details@3@_K@wil@@QEAAAEAU_MVUIITem@@_K@Z; wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::operator[](unsigned __int64)
0x18006faab  mov     ecx, [rax]
0x18006faad  mov     rax, [rbp+pv]
0x18006fab1  mov     [r9+rax], ecx
0x18006fab5  mov     edx, ebx
0x18006fab7  lea     rcx, [rbp+var_18]
0x18006fabb  call    ??A?$unique_any_array_ptr@U_MVUIITem@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAU_MVUIITem@@@Z$1?FreeMVUIItem@Provisioning@Management@Windows@@YAX0@Z@details@3@_K@wil@@QEAAAEAU_MVUIITem@@_K@Z; wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::operator[](unsigned __int64)
0x18006fac0  mov     rcx, [rax+8]; sourceString
0x18006fac4  mov     rax, [rbp+pv]
0x18006fac8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006facc  inc     rdx; length
0x18006facf  cmp     [rcx+rdx*2], r15w
0x18006fad4  jnz     short loc_18006FACC
0x18006fad6  lea     r8, [rax+8]
0x18006fada  add     r8, r9; string
0x18006fadd  call    cs:__imp_WindowsCreateString
0x18006fae4  nop     dword ptr [rax+rax+00h]
0x18006fae9  mov     esi, eax
0x18006faeb  test    eax, eax
0x18006faed  js      short loc_18006FAF3
0x18006faef  inc     ebx
0x18006faf1  jmp     short loc_18006FA91
0x18006faf3  mov     rcx, [rbp+30h]; this
0x18006faf7  mov     r9d, esi; char *
0x18006fafa  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006fb01  mov     edx, 2Dh ; '-'; void *
0x18006fb06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fb0b  mov     rcx, [rbp+pv]; pv
0x18006fb0f  mov     [rbp+pv], r15
0x18006fb13  test    rcx, rcx
0x18006fb16  jz      short loc_18006FB24
0x18006fb18  call    cs:__imp_CoTaskMemFree
0x18006fb1f  nop     dword ptr [rax+rax+00h]
0x18006fb24  mov     ebx, esi
0x18006fb26  lea     rcx, [rbp+var_18]
0x18006fb2a  call    ??1?$unique_any_array_ptr@U_MVUIITem@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAU_MVUIITem@@@Z$1?FreeMVUIItem@Provisioning@Management@Windows@@YAX0@Z@details@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::~unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>(void)
0x18006fb2f  jmp     short loc_18006FB66
0x18006fb31  mov     rax, [rbp+pv]
0x18006fb35  mov     [r14], rax
0x18006fb38  mov     [rbp+pv], r15
0x18006fb3c  lea     rcx, [rbp+var_18]
0x18006fb40  call    ??1?$unique_any_array_ptr@U_MVUIITem@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAU_MVUIITem@@@Z$1?FreeMVUIItem@Provisioning@Management@Windows@@YAX0@Z@details@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::~unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>(void)
0x18006fb45  xor     eax, eax
0x18006fb47  jmp     short loc_18006FB68
0x18006fb49  mov     ebx, 80070057h
0x18006fb4e  mov     edx, 20h ; ' '; void *
0x18006fb53  mov     r9d, ebx; char *
0x18006fb56  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006fb5d  mov     rcx, [rbp+30h]; this
0x18006fb61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fb66  mov     eax, ebx
0x18006fb68  add     rsp, 38h
0x18006fb6c  pop     r15
0x18006fb6e  pop     r14
0x18006fb70  pop     rdi
0x18006fb71  pop     rsi
0x18006fb72  pop     rbx
0x18006fb73  pop     rbp
0x18006fb74  retn
```
