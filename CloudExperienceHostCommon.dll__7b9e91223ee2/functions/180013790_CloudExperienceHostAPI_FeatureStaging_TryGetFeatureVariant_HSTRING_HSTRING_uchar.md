# CloudExperienceHostAPI::FeatureStaging::TryGetFeatureVariant(HSTRING__ *,HSTRING__ * *,uchar *)

- ea: `0x180013790`
- end: `0x1800139ec`
- name: `?TryGetFeatureVariant@FeatureStaging@CloudExperienceHostAPI@@UEAAJPEAUHSTRING__@@PEAPEAU3@PEAE@Z`
- size: `604`
- prototype: `int(CloudExperienceHostAPI::FeatureStaging *__hidden this, HSTRING, HSTRING *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x1800049e0`
- `0x1800052ac`
- `0x180012d70`
- `0x1800135ec`
- `0x180013790`
- `0x1800139f4`
- `0x180013a74`
- `0x180013ab8`
- `0x180013c68`
- `0x1800153f8`
- `0x18001a540`
- `0x18006071c`
- `0x180060994`
- `0x18007283c`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800138d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001396d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800138d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001396d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800137da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800137da`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180013871`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180013871`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostAPI::FeatureStaging::TryGetFeatureVariant(
        CloudExperienceHostAPI::FeatureStaging *this,
        HSTRING a2,
        HSTRING *a3,
        unsigned __int8 *a4)
{
  unsigned __int8 *v4; // r14
  HSTRING *v5; // r12
  CloudExperienceHostAPI::FeatureStaging *v6; // r13
  PCWSTR StringRawBuffer; // r15
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 *v10; // rax
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rcx
  unsigned __int16 v14; // bx
  __int64 v15; // rcx
  const char *v16; // r9
  HRESULT v17; // eax
  unsigned int v18; // ebx
  _QWORD *v19; // rax
  const WCHAR *v20; // rax
  HRESULT String; // eax
  int v23; // [rsp+20h] [rbp-B8h]
  _BYTE v31[16]; // [rsp+48h] [rbp-90h] BYREF
  __int128 v32; // [rsp+58h] [rbp-80h] BYREF
  UINT32 length[4]; // [rsp+68h] [rbp-70h]
  _BYTE v34[32]; // [rsp+78h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v4 = a4;
  v5 = a3;
  v6 = this;
  *a4 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v32 = 0;
  *(_OWORD *)length = 0;
  v8 = std::_WChar_traits<unsigned short>::length(StringRawBuffer);
  std::wstring::_Construct<1,unsigned short const *>(&v32, v9, v8);
  v10 = (__int64 *)std::_Hash<std::_Umap_traits<std::wstring,std::function<bool (void)>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::function<bool (void)>>>,0>>::find(
                     (char *)v6 + 136,
                     v31,
                     &v32);
  v11 = *((_QWORD *)v6 + 18);
  v12 = *v10;
  std::wstring::_Tidy_deallocate(&v32);
  if ( v12 != v11 )
  {
    try
    {
      std::wstring::wstring(&v32, StringRawBuffer);
      v13 = *(_QWORD *)(std::unordered_map<std::wstring,std::function<unsigned short (void)>>::operator[](
                          (char *)v6 + 136,
                          &v32)
                      + 56);
      if ( !v13 )
        std::_Xbad_function_call();
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      LOWORD(v23) = v14;
      std::wstring::_Tidy_deallocate(&v32);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\featurestaging.cpp",
        v16);
      v14 = v23;
      v6 = this;
      v5 = a3;
      v4 = a4;
    }
    CloudExperienceHostAPI::FeatureStaging::GetFeatureVariantUniqueIdentifier(v15, v34, StringRawBuffer, v14);
    if ( v14 )
    {
      if ( *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                        (char *)v6 + 264,
                        v31,
                        v34) != *((_QWORD *)v6 + 34) )
      {
        v19 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(
                          (_QWORD *)v6 + 33,
                          (__int64)v31,
                          (__int64)v34);
        std::wstring::wstring(&v32, *v19 + 48LL);
        v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v32);
        String = WindowsCreateString(v20, length[0], v5);
        v18 = String;
        if ( String < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD3,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\featurestaging.cpp",
            (const char *)(unsigned int)String,
            v23);
          std::wstring::_Tidy_deallocate(&v32);
          goto LABEL_13;
        }
        *v4 = 1;
        std::wstring::_Tidy_deallocate(&v32);
      }
    }
    else
    {
      v17 = WindowsCreateString(L"None", 4u, v5);
      v18 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\featurestaging.cpp",
          (const char *)(unsigned int)v17,
          v23);
LABEL_13:
        std::wstring::_Tidy_deallocate(v34);
        return v18;
      }
      *v4 = 1;
    }
    std::wstring::_Tidy_deallocate(v34);
  }
  return 0;
}

```

## disassembly

```asm
0x180013790  push    rbx
0x180013792  push    rsi
0x180013793  push    rdi
0x180013794  push    r12
0x180013796  push    r13
0x180013798  push    r14
0x18001379a  push    r15
0x18001379c  sub     rsp, 0A0h
0x1800137a3  mov     rax, cs:__security_cookie
0x1800137aa  xor     rax, rsp
0x1800137ad  mov     [rsp+0D8h+var_40], rax
0x1800137b5  mov     r14, r9
0x1800137b8  mov     r12, r8
0x1800137bb  mov     rax, rdx
0x1800137be  mov     r13, rcx
0x1800137c1  mov     [rsp+0D8h+var_A8], rcx
0x1800137c6  mov     [rsp+0D8h+var_A0], r8
0x1800137cb  mov     [rsp+0D8h+var_98], r9
0x1800137d0  xor     esi, esi
0x1800137d2  mov     [r9], sil
0x1800137d5  xor     edx, edx; length
0x1800137d7  mov     rcx, rax; string
0x1800137da  call    cs:__imp_WindowsGetStringRawBuffer
0x1800137e0  mov     r15, rax
0x1800137e3  mov     [rsp+0D8h+var_B0], rax
0x1800137e8  xorps   xmm0, xmm0
0x1800137eb  movups  [rsp+0D8h+var_80], xmm0
0x1800137f0  xorps   xmm1, xmm1
0x1800137f3  movdqu  xmmword ptr [rsp+0D8h+length], xmm1
0x1800137f9  mov     rcx, rax
0x1800137fc  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180013801  mov     r8, rax
0x180013804  mov     rdx, rcx
0x180013807  lea     rcx, [rsp+0D8h+var_80]
0x18001380c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013811  lea     rcx, [r13+88h]
0x180013818  lea     r8, [rsp+0D8h+var_80]
0x18001381d  lea     rdx, [rsp+0D8h+var_90]
0x180013822  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::function<bool (void)>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::function<bool (void)>>>,0>>::find(std::wstring const &)
0x180013827  mov     rdi, [r13+90h]
0x18001382e  mov     rbx, [rax]
0x180013831  lea     rcx, [rsp+0D8h+var_80]
0x180013836  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001383b  cmp     rbx, rdi
0x18001383e  jz      loc_1800139C7
0x180013844  mov     [rsp+0D8h+var_B8], si
0x180013849  mov     rdx, r15
0x18001384c  lea     rcx, [rsp+0D8h+var_80]
0x180013851  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180013856  nop
0x180013857  lea     rdx, [rsp+0D8h+var_80]
0x18001385c  lea     rcx, [r13+88h]
0x180013863  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6AGXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6AGXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6AGXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<ushort (void)>>::operator[](std::wstring &&)
0x180013868  mov     rcx, [rax+38h]
0x18001386c  test    rcx, rcx
0x18001386f  jnz     short loc_180013877
0x180013871  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180013877  mov     rax, [rcx]
0x18001387a  mov     rax, [rax+10h]
0x18001387e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013883  movzx   ebx, ax
0x180013886  mov     [rsp+0D8h+var_B8], ax
0x18001388b  lea     rcx, [rsp+0D8h+var_80]
0x180013890  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013895  nop
0x180013896  jmp     short loc_1800138B1
0x180013898  mov     r15, [rsp+0D8h+var_B0]
0x18001389d  movzx   ebx, [rsp+0D8h+var_B8]
0x1800138a2  mov     r13, [rsp+0D8h+var_A8]
0x1800138a7  mov     r12, [rsp+0D8h+var_A0]
0x1800138ac  mov     r14, [rsp+0D8h+var_98]
0x1800138b1  movzx   r9d, bx
0x1800138b5  mov     r8, r15
0x1800138b8  lea     rdx, [rsp+0D8h+var_60]
0x1800138bd  call    ?GetFeatureVariantUniqueIdentifier@FeatureStaging@CloudExperienceHostAPI@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGG@Z; CloudExperienceHostAPI::FeatureStaging::GetFeatureVariantUniqueIdentifier(ushort const *,ushort)
0x1800138c2  nop
0x1800138c3  test    bx, bx
0x1800138c6  jnz     short loc_18001390D
0x1800138c8  mov     r8, r12; string
0x1800138cb  mov     edx, 4; length
0x1800138d0  lea     rcx, sourceString; "None"
0x1800138d7  call    cs:__imp_WindowsCreateString
0x1800138dd  mov     ebx, eax
0x1800138df  test    eax, eax
0x1800138e1  jns     short loc_180013904
0x1800138e3  mov     rcx, [rsp+0D8h]; this
0x1800138eb  mov     r9d, eax; char *
0x1800138ee  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800138f5  mov     edx, 0CCh; void *
0x1800138fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800138ff  jmp     loc_1800139A0
0x180013904  mov     byte ptr [r14], 1
0x180013908  jmp     loc_1800139BD
0x18001390d  lea     rbx, [r13+108h]
0x180013914  lea     r8, [rsp+0D8h+var_60]
0x180013919  lea     rdx, [rsp+0D8h+var_90]
0x18001391e  mov     rcx, rbx
0x180013921  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180013926  mov     rcx, [r13+110h]
0x18001392d  cmp     [rax], rcx
0x180013930  jz      loc_1800139BD
0x180013936  lea     r8, [rsp+0D8h+var_60]
0x18001393b  lea     rdx, [rsp+0D8h+var_90]
0x180013940  mov     rcx, rbx
0x180013943  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180013948  mov     rdx, [rax]
0x18001394b  add     rdx, 30h ; '0'
0x18001394f  lea     rcx, [rsp+0D8h+var_80]
0x180013954  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180013959  lea     rcx, [rsp+0D8h+var_80]
0x18001395e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013963  mov     rcx, rax; sourceString
0x180013966  mov     r8, r12; string
0x180013969  mov     edx, [rsp+0D8h+length]; length
0x18001396d  call    cs:__imp_WindowsCreateString
0x180013973  mov     ebx, eax
0x180013975  test    eax, eax
0x180013977  jns     short loc_1800139AE
0x180013979  mov     rcx, [rsp+0D8h]; this
0x180013981  mov     r9d, eax; char *
0x180013984  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\cloudexperiencehost"...
0x18001398b  mov     edx, 0D3h; void *
0x180013990  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013995  lea     rcx, [rsp+0D8h+var_80]
0x18001399a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001399f  nop
0x1800139a0  lea     rcx, [rsp+0D8h+var_60]
0x1800139a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800139aa  mov     eax, ebx
0x1800139ac  jmp     short loc_1800139C9
0x1800139ae  mov     byte ptr [r14], 1
0x1800139b2  lea     rcx, [rsp+0D8h+var_80]
0x1800139b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800139bc  nop
0x1800139bd  lea     rcx, [rsp+0D8h+var_60]
0x1800139c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800139c7  xor     eax, eax
0x1800139c9  mov     rcx, [rsp+0D8h+var_40]
0x1800139d1  xor     rcx, rsp; StackCookie
0x1800139d4  call    __security_check_cookie
0x1800139d9  add     rsp, 0A0h
0x1800139e0  pop     r15
0x1800139e2  pop     r14
0x1800139e4  pop     r13
0x1800139e6  pop     r12
0x1800139e8  pop     rdi
0x1800139e9  pop     rsi
0x1800139ea  pop     rbx
0x1800139eb  retn
```
