# ConnectedStorage::RegisteredUsers::ExecuteWithRegisteredUser(ConnectedStorage::WebService const *,ConnectedStorage::ContextDesc const &,std::function<void (ConnectedStorage::WebService::Status)> const &)

- ea: `0x180068974`
- end: `0x180068c99`
- name: `?ExecuteWithRegisteredUser@RegisteredUsers@ConnectedStorage@@QEBAXPEBVWebService@2@AEBVContextDesc@2@AEBV?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@Z`
- size: `805`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callers

- `0x180040740`

## callees

- `0x180003c70`
- `0x1800078e8`
- `0x18000c218`
- `0x18000cb9c`
- `0x18000d2b8`
- `0x180011b94`
- `0x180012f7c`
- `0x1800136a8`
- `0x1800190f0`
- `0x180019128`
- `0x18001a700`
- `0x18001ad00`
- `0x1800281e8`
- `0x18003cdd4`
- `0x18003f418`
- `0x180055898`
- `0x1800635c8`
- `0x18006364c`
- `0x180068474`
- `0x1800687c4`
- `0x180068864`
- `0x1800688b8`
- `0x180068974`
- `0x180068dc8`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068a30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068a30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068a3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068a3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
HRESULT __fastcall ConnectedStorage::RegisteredUsers::ExecuteWithRegisteredUser(
        __int64 a1,
        __int64 a2,
        HSTRING *a3,
        __int64 a4)
{
  __int64 v8; // r8
  char *v10; // r8
  __int64 v11; // rcx
  __int64 v12; // r8
  HSTRING v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // r8
  HSTRING *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // r13
  _QWORD **v20; // r15
  _QWORD *v21; // r14
  _QWORD *v22; // rbx
  std::_Ref_count_base *v23; // rcx
  volatile signed __int32 *v24; // rcx
  std::_Ref_count_base *v25; // rdi
  void (__fastcall *v26)(__int64, HSTRING *, _QWORD *); // rbx
  HSTRING string; // [rsp+20h] [rbp-118h] BYREF
  HSTRING newString[2]; // [rsp+28h] [rbp-110h] BYREF
  HSTRING v29; // [rsp+38h] [rbp-100h] BYREF
  __int128 v30; // [rsp+40h] [rbp-F8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-E8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+58h] [rbp-E0h] BYREF
  _QWORD v33[9]; // [rsp+68h] [rbp-D0h] BYREF
  _BYTE v34[64]; // [rsp+B0h] [rbp-88h] BYREF

  if ( ConnectedStorage::ContextDesc::IsNoSync((ConnectedStorage::ContextDesc *)a3) )
    return std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
             a4,
             2,
             v8);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, a3 + 2);
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)(a1 + 24),
    v10);
  v11 = *(_QWORD *)(a1 + 16);
  if ( !v11 || (*(unsigned __int8 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v11 + 24LL))(v11, &string) )
  {
    std::_Tree<std::_Tmap_traits<ConnectedStorage::SimpleHStringWrapper,std::list<std::function<void (enum ConnectedStorage::WebService::Status)>>,std::less<ConnectedStorage::SimpleHStringWrapper>,std::allocator<std::pair<ConnectedStorage::SimpleHStringWrapper const,std::list<std::function<void (enum ConnectedStorage::WebService::Status)>>>>,0>>::_Find_lower_bound<ConnectedStorage::SimpleHStringWrapper>(
      a1 + 88,
      newString,
      (__int64)&string);
    v13 = v29;
    if ( std::_Tree<std::_Tmap_traits<ConnectedStorage::SimpleHStringWrapper,enum ConnectedStorage::WebService::Status,std::less<ConnectedStorage::SimpleHStringWrapper>,std::allocator<std::pair<ConnectedStorage::SimpleHStringWrapper const,enum ConnectedStorage::WebService::Status>>,0>>::_Lower_bound_duplicate<ConnectedStorage::SimpleHStringWrapper>(
           v14,
           (__int64)v29,
           (__int64)&string)
      && v13 != *(HSTRING *)(a1 + 88) )
    {
      if ( *((_DWORD *)v13 + 10) != 1 )
      {
        try
        {
          std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
            a4,
            *((unsigned int *)v13 + 10),
            v15);
        }
        catch ( ConnectedStorage::ComError v34 )
        {
          ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v34);
          goto LABEL_6;
        }
        catch ( std::bad_alloc )
        {
          goto LABEL_6;
        }
        catch ( ... )
        {
          goto LABEL_6;
        }
        goto LABEL_6;
      }
      v16 = (HSTRING *)std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ConnectedStorage::Handle>>>::_Extract(
                         a1 + 88,
                         v13);
      std::_Tree_node<std::pair<ConnectedStorage::SimpleHStringWrapper const,enum ConnectedStorage::WebService::Status>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<ConnectedStorage::SimpleHStringWrapper const,enum ConnectedStorage::WebService::Status>,void *>>>(
        v17,
        v16);
    }
    v18 = std::_Tree<std::_Tmap_traits<ConnectedStorage::SimpleHStringWrapper,std::list<std::function<void (enum ConnectedStorage::WebService::Status)>>,std::less<ConnectedStorage::SimpleHStringWrapper>,std::allocator<std::pair<ConnectedStorage::SimpleHStringWrapper const,std::list<std::function<void (enum ConnectedStorage::WebService::Status)>>>>,0>>::_Find_lower_bound<ConnectedStorage::SimpleHStringWrapper>(
            a1 + 72,
            newString,
            (__int64)&string)[2];
    if ( v18 == *(_QWORD *)(a1 + 72)
      || !ConnectedStorage::SimpleHStringWrapper::operator==((HSTRING *)(v18 + 32), &string) )
    {
      v30 = 0;
      std::list<std::function<void (enum ConnectedStorage::WebService::Status)>>::_Alloc_sentinel_and_proxy(&v30);
      ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(newString, &string);
      std::list<std::function<void (enum ConnectedStorage::WebService::Status)>>::list<std::function<void (enum ConnectedStorage::WebService::Status)>>(
        &newString[1],
        &v30);
      v19 = *std::map<ConnectedStorage::SimpleHStringWrapper,std::list<std::function<void (enum ConnectedStorage::WebService::Status)>>>::insert<std::pair<ConnectedStorage::SimpleHStringWrapper,std::list<std::function<void (enum ConnectedStorage::WebService::Status)>>>,0>(
               a1 + 72,
               &v31,
               v18,
               newString);
      std::pair<ConnectedStorage::SimpleHStringWrapper const,std::list<std::function<void (enum ConnectedStorage::WebService::Status)>>>::~pair<ConnectedStorage::SimpleHStringWrapper const,std::list<std::function<void (enum ConnectedStorage::WebService::Status)>>>(newString);
      v20 = (_QWORD **)v30;
      **(_QWORD **)(v30 + 8) = 0;
      v21 = *v20;
      if ( *v20 )
      {
        do
        {
          v22 = (_QWORD *)*v21;
          std::function<long (void)>::~function<long (void)>(v21 + 2);
          std::_Deallocate<16>(v21, 0x50u);
          v21 = v22;
        }
        while ( v22 );
      }
      std::_Deallocate<16>(v20, 0x50u);
      std::list<std::function<void (enum ConnectedStorage::WebService::Status)>>::_Emplace<std::function<void (enum ConnectedStorage::WebService::Status)> const &>(
        v19 + 40,
        *(_QWORD *)(v19 + 40),
        a4);
      v23 = *(std::_Ref_count_base **)(a1 + 8);
      if ( !v23 || !std::_Ref_count_base::_Incref_nz(v23) )
        std::_Throw_bad_weak_ptr();
      v24 = *(volatile signed __int32 **)(a1 + 8);
      v30 = 0;
      if ( v24 )
      {
        *(_QWORD *)&v30 = *(_QWORD *)a1;
        v25 = (std::_Ref_count_base *)v24;
        *((_QWORD *)&v30 + 1) = v24;
        _InterlockedIncrement(v24 + 3);
      }
      else
      {
        v25 = (std::_Ref_count_base *)*((_QWORD *)&v30 + 1);
      }
      if ( v24 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v24);
      v26 = *(void (__fastcall **)(__int64, HSTRING *, _QWORD *))(*(_QWORD *)a2 + 24LL);
      std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(newString, &v30);
      ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v29, &string);
      v33[0] = off_1800925B8;
      v33[1] = newString[0];
      v33[2] = newString[1];
      *(_OWORD *)newString = 0;
      v33[3] = v29;
      v29 = 0;
      v33[7] = v33;
      v26(a2, &string, v33);
      lambda_4fce31053f559310a6d5731d3fc0d9e0_::__lambda_4fce31053f559310a6d5731d3fc0d9e0_(newString);
      if ( v25 )
        std::_Ref_count_base::_Decwref(v25);
    }
    else
    {
      std::list<std::function<void (enum ConnectedStorage::WebService::Status)>>::_Emplace<std::function<void (enum ConnectedStorage::WebService::Status)> const &>(
        v18 + 40,
        *(_QWORD *)(v18 + 40),
        a4);
    }
  }
  else
  {
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
      a4,
      2,
      v12);
  }
LABEL_6:
  LeaveCriticalSection(lpCriticalSection[0]);
  return WindowsDeleteString(string);
}

```

## disassembly

```asm
0x180068974  push    rbx
0x180068976  push    rsi
0x180068977  push    rdi
0x180068978  push    r12
0x18006897a  push    r13
0x18006897c  push    r14
0x18006897e  push    r15
0x180068980  sub     rsp, 100h
0x180068987  mov     rax, cs:__security_cookie
0x18006898e  xor     rax, rsp
0x180068991  mov     [rsp+138h+var_48], rax
0x180068999  mov     rsi, r9
0x18006899c  mov     rbx, r8
0x18006899f  mov     r12, rdx
0x1800689a2  mov     rdi, rcx
0x1800689a5  mov     rcx, r8; this
0x1800689a8  call    ?IsNoSync@ContextDesc@ConnectedStorage@@QEBA_NXZ; ConnectedStorage::ContextDesc::IsNoSync(void)
0x1800689ad  test    al, al
0x1800689af  jz      short loc_1800689E1
0x1800689b1  mov     edx, 2
0x1800689b6  mov     rcx, rsi
0x1800689b9  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x1800689be  mov     rcx, [rsp+138h+var_48]
0x1800689c6  xor     rcx, rsp; StackCookie
0x1800689c9  call    __security_check_cookie
0x1800689ce  add     rsp, 100h
0x1800689d5  pop     r15
0x1800689d7  pop     r14
0x1800689d9  pop     r13
0x1800689db  pop     r12
0x1800689dd  pop     rdi
0x1800689de  pop     rsi
0x1800689df  pop     rbx
0x1800689e0  retn
0x1800689e1  lea     rdx, [rbx+10h]; struct ConnectedStorage::SimpleHStringWrapper *
0x1800689e5  lea     rcx, [rsp+138h+string]; newString
0x1800689ea  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x1800689ef  nop
0x1800689f0  lea     rdx, [rdi+18h]; struct ConnectedStorage::Mutex *
0x1800689f4  lea     rcx, [rsp+138h+lpCriticalSection]; this
0x1800689f9  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x1800689fe  nop
0x1800689ff  mov     rcx, [rdi+10h]
0x180068a03  test    rcx, rcx
0x180068a06  jz      short loc_180068A47
0x180068a08  mov     rax, [rcx]
0x180068a0b  lea     rdx, [rsp+138h+string]
0x180068a10  mov     rax, [rax+18h]
0x180068a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068a19  test    al, al
0x180068a1b  jnz     short loc_180068A47
0x180068a1d  mov     edx, 2
0x180068a22  mov     rcx, rsi
0x180068a25  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180068a2a  nop
0x180068a2b  mov     rcx, [rsp+138h+lpCriticalSection]; lpCriticalSection
0x180068a30  call    cs:__imp_LeaveCriticalSection
0x180068a36  nop
0x180068a37  mov     rcx, [rsp+138h+string]; string
0x180068a3c  call    cs:__imp_WindowsDeleteString
0x180068a42  jmp     loc_1800689BE
0x180068a47  lea     r14, [rdi+58h]
0x180068a4b  lea     r8, [rsp+138h+string]
0x180068a50  lea     rdx, [rsp+138h+newString]
0x180068a55  mov     rcx, r14
0x180068a58  call    ??$_Find_lower_bound@VSimpleHStringWrapper@ConnectedStorage@@@?$_Tree@V?$_Tmap_traits@VSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@U?$less@VSimpleHStringWrapper@ConnectedStorage@@@4@V?$allocator@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@@std@@PEAX@std@@@1@AEBVSimpleHStringWrapper@ConnectedStorage@@@Z; std::_Tree<std::_Tmap_traits<ConnectedStorage::SimpleHStringWrapper,std::list<std::function<void (ConnectedStorage::WebService::Status)>>,std::less<ConnectedStorage::SimpleHStringWrapper>,std::allocator<std::pair<ConnectedStorage::SimpleHStringWrapper const,std::list<std::function<void (ConnectedStorage::WebService::Status)>>>>,0>>::_Find_lower_bound<ConnectedStorage::SimpleHStringWrapper>(ConnectedStorage::SimpleHStringWrapper const &)
0x180068a5d  lea     r8, [rsp+138h+string]
0x180068a62  mov     rbx, [rsp+138h+var_100]
0x180068a67  mov     rdx, rbx
0x180068a6a  call    ??$_Lower_bound_duplicate@VSimpleHStringWrapper@ConnectedStorage@@@?$_Tree@V?$_Tmap_traits@VSimpleHStringWrapper@ConnectedStorage@@W4Status@WebService@2@U?$less@VSimpleHStringWrapper@ConnectedStorage@@@std@@V?$allocator@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@W4Status@WebService@2@@std@@@6@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@W4Status@WebService@2@@std@@PEAX@1@AEBVSimpleHStringWrapper@ConnectedStorage@@@Z; std::_Tree<std::_Tmap_traits<ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::WebService::Status,std::less<ConnectedStorage::SimpleHStringWrapper>,std::allocator<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::WebService::Status>>,0>>::_Lower_bound_duplicate<ConnectedStorage::SimpleHStringWrapper>(std::_Tree_node<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::WebService::Status>,void *> * const,ConnectedStorage::SimpleHStringWrapper const &)
0x180068a6f  test    al, al
0x180068a71  jz      short loc_180068A91
0x180068a73  cmp     rbx, [r14]
0x180068a76  jz      short loc_180068A91
0x180068a78  cmp     dword ptr [rbx+28h], 1
0x180068a7c  jnz     short loc_180068AD6
0x180068a7e  mov     rdx, rbx
0x180068a81  mov     rcx, r14
0x180068a84  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ConnectedStorage::Handle>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ConnectedStorage::Handle>>>,std::_Iterator_base0>)
0x180068a89  mov     rdx, rax
0x180068a8c  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@W4Status@WebService@2@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@W4Status@WebService@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@W4Status@WebService@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::WebService::Status>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::WebService::Status>,void *>>>(std::allocator<std::_Tree_node<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::WebService::Status>,void *>> &,std::_Tree_node<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::WebService::Status>,void *> *)
0x180068a91  lea     r14, [rdi+48h]
0x180068a95  lea     r8, [rsp+138h+string]
0x180068a9a  lea     rdx, [rsp+138h+newString]
0x180068a9f  mov     rcx, r14
0x180068aa2  call    ??$_Find_lower_bound@VSimpleHStringWrapper@ConnectedStorage@@@?$_Tree@V?$_Tmap_traits@VSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@U?$less@VSimpleHStringWrapper@ConnectedStorage@@@4@V?$allocator@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@@std@@PEAX@std@@@1@AEBVSimpleHStringWrapper@ConnectedStorage@@@Z; std::_Tree<std::_Tmap_traits<ConnectedStorage::SimpleHStringWrapper,std::list<std::function<void (ConnectedStorage::WebService::Status)>>,std::less<ConnectedStorage::SimpleHStringWrapper>,std::allocator<std::pair<ConnectedStorage::SimpleHStringWrapper const,std::list<std::function<void (ConnectedStorage::WebService::Status)>>>>,0>>::_Find_lower_bound<ConnectedStorage::SimpleHStringWrapper>(ConnectedStorage::SimpleHStringWrapper const &)
0x180068aa7  mov     rbx, [rax+10h]
0x180068aab  cmp     rbx, [r14]
0x180068aae  jz      short loc_180068AEB
0x180068ab0  lea     rcx, [rbx+20h]
0x180068ab4  lea     rdx, [rsp+138h+string]
0x180068ab9  call    ??8SimpleHStringWrapper@ConnectedStorage@@QEBA_NAEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator==(ConnectedStorage::SimpleHStringWrapper const &)
0x180068abe  test    al, al
0x180068ac0  jz      short loc_180068AEB
0x180068ac2  lea     rcx, [rbx+28h]
0x180068ac6  mov     r8, rsi
0x180068ac9  mov     rdx, [rcx]
0x180068acc  call    ??$_Emplace@AEBV?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@QEAAPEAU?$_List_node@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@PEAX@1@QEAU21@AEBV?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@1@@Z; std::list<std::function<void (ConnectedStorage::WebService::Status)>>::_Emplace<std::function<void (ConnectedStorage::WebService::Status)> const &>(std::_List_node<std::function<void (ConnectedStorage::WebService::Status)>,void *> * const,std::function<void (ConnectedStorage::WebService::Status)> const &)
0x180068ad1  jmp     loc_180068A2B
0x180068ad6  mov     edx, [rbx+28h]
0x180068ad9  mov     rcx, rsi
0x180068adc  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180068ae1  nop
0x180068ae2  jmp     loc_180068A2B
0x180068ae7  jmp     short loc_180068AE2
0x180068ae9  jmp     short loc_180068AE2
0x180068aeb  xorps   xmm0, xmm0
0x180068aee  movdqu  [rsp+138h+var_F8], xmm0
0x180068af4  lea     rcx, [rsp+138h+var_F8]
0x180068af9  call    ?_Alloc_sentinel_and_proxy@?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@AEAAXXZ; std::list<std::function<void (ConnectedStorage::WebService::Status)>>::_Alloc_sentinel_and_proxy(void)
0x180068afe  nop
0x180068aff  lea     rdx, [rsp+138h+string]; struct ConnectedStorage::SimpleHStringWrapper *
0x180068b04  lea     rcx, [rsp+138h+newString]; newString
0x180068b09  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x180068b0e  nop
0x180068b0f  lea     rdx, [rsp+138h+var_F8]
0x180068b14  lea     rcx, [rsp+138h+newString+8]
0x180068b19  call    ??0?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::list<std::function<void (ConnectedStorage::WebService::Status)>>::list<std::function<void (ConnectedStorage::WebService::Status)>>(std::list<std::function<void (ConnectedStorage::WebService::Status)>> &&)
0x180068b1e  nop
0x180068b1f  lea     r9, [rsp+138h+newString]
0x180068b24  mov     r8, rbx
0x180068b27  lea     rdx, [rsp+138h+var_E8]
0x180068b2c  mov     rcx, r14
0x180068b2f  call    ??$insert@U?$pair@VSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@@std@@$0A@@?$map@VSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@U?$less@VSimpleHStringWrapper@ConnectedStorage@@@4@V?$allocator@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@@std@@@4@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@@std@@@std@@@std@@@1@$$QEAU?$pair@VSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@@1@@Z; std::map<ConnectedStorage::SimpleHStringWrapper,std::list<std::function<void (ConnectedStorage::WebService::Status)>>>::insert<std::pair<ConnectedStorage::SimpleHStringWrapper,std::list<std::function<void (ConnectedStorage::WebService::Status)>>>,0>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ConnectedStorage::SimpleHStringWrapper const,std::list<std::function<void (ConnectedStorage::WebService::Status)>>>>>>,std::pair<ConnectedStorage::SimpleHStringWrapper,std::list<std::function<void (ConnectedStorage::WebService::Status)>>> &&)
0x180068b34  mov     r13, [rax]
0x180068b37  lea     rcx, [rsp+138h+newString]
0x180068b3c  call    ??1?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@@std@@QEAA@XZ; std::pair<ConnectedStorage::SimpleHStringWrapper const,std::list<std::function<void (ConnectedStorage::WebService::Status)>>>::~pair<ConnectedStorage::SimpleHStringWrapper const,std::list<std::function<void (ConnectedStorage::WebService::Status)>>>(void)
0x180068b41  nop
0x180068b42  mov     r15, qword ptr [rsp+138h+var_F8]
0x180068b47  mov     rax, [r15+8]
0x180068b4b  mov     qword ptr [rax], 0
0x180068b52  mov     r14, [r15]
0x180068b55  test    r14, r14
0x180068b58  jz      short loc_180068B7B
0x180068b5a  mov     rbx, [r14]
0x180068b5d  lea     rcx, [r14+10h]
0x180068b61  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180068b66  mov     edx, 50h ; 'P'
0x180068b6b  mov     rcx, r14
0x180068b6e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180068b73  mov     r14, rbx
0x180068b76  test    rbx, rbx
0x180068b79  jnz     short loc_180068B5A
0x180068b7b  mov     edx, 50h ; 'P'
0x180068b80  mov     rcx, r15
0x180068b83  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180068b88  lea     rcx, [r13+28h]
0x180068b8c  mov     r8, rsi
0x180068b8f  mov     rdx, [rcx]
0x180068b92  call    ??$_Emplace@AEBV?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@QEAAPEAU?$_List_node@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@PEAX@1@QEAU21@AEBV?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@1@@Z; std::list<std::function<void (ConnectedStorage::WebService::Status)>>::_Emplace<std::function<void (ConnectedStorage::WebService::Status)> const &>(std::_List_node<std::function<void (ConnectedStorage::WebService::Status)>,void *> * const,std::function<void (ConnectedStorage::WebService::Status)> const &)
0x180068b97  mov     rcx, [rdi+8]; this
0x180068b9b  test    rcx, rcx
0x180068b9e  jz      loc_180068C93
0x180068ba4  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x180068ba9  test    al, al
0x180068bab  jz      loc_180068C93
0x180068bb1  mov     rcx, [rdi+8]; this
0x180068bb5  xorps   xmm0, xmm0
0x180068bb8  movdqu  [rsp+138h+var_F8], xmm0
0x180068bbe  test    rcx, rcx
0x180068bc1  jz      short loc_180068BD9
0x180068bc3  mov     rax, [rdi]
0x180068bc6  mov     qword ptr [rsp+138h+var_F8], rax
0x180068bcb  mov     rdi, rcx
0x180068bce  mov     qword ptr [rsp+138h+var_F8+8], rcx
0x180068bd3  lock inc dword ptr [rcx+0Ch]
0x180068bd7  jmp     short loc_180068BDE
0x180068bd9  mov     rdi, qword ptr [rsp+138h+var_F8+8]
0x180068bde  test    rcx, rcx
0x180068be1  jz      short loc_180068BE8
0x180068be3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180068be8  mov     rax, [r12]
0x180068bec  mov     rbx, [rax+18h]
0x180068bf0  lea     rdx, [rsp+138h+var_F8]
0x180068bf5  lea     rcx, [rsp+138h+newString]
0x180068bfa  call    ??$?0VContext@ConnectedStorage@@$0A@@?$weak_ptr@VContext@ConnectedStorage@@@std@@QEAA@AEBV?$shared_ptr@VContext@ConnectedStorage@@@1@@Z; std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(std::shared_ptr<ConnectedStorage::Context> const &)
0x180068bff  nop
0x180068c00  lea     rdx, [rsp+138h+string]; struct ConnectedStorage::SimpleHStringWrapper *
0x180068c05  lea     rcx, [rsp+138h+var_100]; newString
0x180068c0a  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x180068c0f  nop
0x180068c10  lea     rax, off_1800925B8
0x180068c17  mov     [rsp+138h+var_D0], rax
0x180068c1c  mov     rax, [rsp+138h+newString]
0x180068c21  mov     [rsp+138h+var_C8], rax
0x180068c26  mov     rdx, [rsp+138h+newString+8]
0x180068c2b  mov     [rsp+138h+var_C0], rdx
0x180068c30  xorps   xmm0, xmm0
0x180068c33  movdqu  xmmword ptr [rsp+138h+newString], xmm0
0x180068c39  mov     rdx, [rsp+138h+var_100]
0x180068c3e  mov     [rsp+138h+var_B8], rdx
0x180068c46  mov     [rsp+138h+var_100], 0
0x180068c4f  lea     rax, [rsp+138h+var_D0]
0x180068c54  mov     [rsp+138h+var_98], rax
0x180068c5c  lea     r8, [rsp+138h+var_D0]
0x180068c61  lea     rdx, [rsp+138h+string]
0x180068c66  mov     rcx, r12
0x180068c69  mov     rax, rbx
0x180068c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068c71  nop
0x180068c72  lea     rcx, [rsp+138h+newString]
0x180068c77  call    _lambda_4fce31053f559310a6d5731d3fc0d9e0_____lambda_4fce31053f559310a6d5731d3fc0d9e0_
0x180068c7c  nop
0x180068c7d  test    rdi, rdi
0x180068c80  jz      loc_180068A2B
0x180068c86  mov     rcx, rdi; this
0x180068c89  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180068c8e  jmp     loc_180068A2B
0x180068c93  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
```
