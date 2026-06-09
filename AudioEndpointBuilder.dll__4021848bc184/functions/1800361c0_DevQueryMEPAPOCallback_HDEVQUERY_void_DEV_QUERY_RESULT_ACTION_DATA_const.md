# DevQueryMEPAPOCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)

- ea: `0x1800361c0`
- end: `0x1800364ce`
- name: `?DevQueryMEPAPOCallback@@YAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z`
- size: `782`
- prototype: `void __fastcall(struct HDEVQUERY__ *, void *, const struct _DEV_QUERY_RESULT_ACTION_DATA *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18001707c`
- `0x18001b5bc`
- `0x18003512c`
- `0x18003514c`
- `0x1800361c0`
- `0x1800364d4`
- `0x18003e920`
- `0x18005ae10`
- `0x18005aeb8`
- `0x18005afd0`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800362a2`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180036463`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180036463`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180036413`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180036413`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180036222`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180036222`

## string_xrefs

- `0x18003623e`: `avcore\audiocore\server\audioendpointbuilder\dll\globalapo.cpp`
- `0x180036478`: `avcore\audiocore\server\audioendpointbuilder\dll\globalapo.cpp`

## pseudocode

```c
void __fastcall DevQueryMEPAPOCallback(
        struct HDEVQUERY__ *a1,
        void *a2,
        const struct _DEV_QUERY_RESULT_ACTION_DATA *a3)
{
  __int64 Property; // rax
  __int64 v5; // rsi
  _WORD *v6; // rdi
  _QWORD *v7; // rdx
  unsigned __int16 *v8; // r15
  unsigned __int16 *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 *v13; // rbx
  __int64 v14; // rdi
  int v15; // eax
  const char *v16; // r9
  int v17; // [rsp+20h] [rbp-148h]
  int v18; // [rsp+20h] [rbp-148h]
  char v19; // [rsp+50h] [rbp-118h] BYREF
  _BYTE v20[8]; // [rsp+58h] [rbp-110h] BYREF
  _BYTE v21[24]; // [rsp+60h] [rbp-108h] BYREF
  _QWORD v22[3]; // [rsp+78h] [rbp-F0h] BYREF
  unsigned __int64 v23; // [rsp+90h] [rbp-D8h]
  DEVPROPKEY v24; // [rsp+98h] [rbp-D0h] BYREF
  int v25; // [rsp+ACh] [rbp-BCh]
  __int64 v26; // [rsp+B0h] [rbp-B8h]
  int v27; // [rsp+C0h] [rbp-A8h] BYREF
  DEVPROPKEY v28; // [rsp+C8h] [rbp-A0h]
  int v29; // [rsp+DCh] [rbp-8Ch]
  __int64 v30; // [rsp+E0h] [rbp-88h]
  int v31; // [rsp+E8h] [rbp-80h]
  int v32; // [rsp+ECh] [rbp-7Ch]
  __int64 v33; // [rsp+F0h] [rbp-78h]
  int v34; // [rsp+F8h] [rbp-70h]
  DEVPROPKEY v35; // [rsp+100h] [rbp-68h]
  int v36; // [rsp+114h] [rbp-54h]
  __int64 v37; // [rsp+118h] [rbp-50h]
  int v38; // [rsp+120h] [rbp-48h]
  int v39; // [rsp+124h] [rbp-44h]
  char *v40; // [rsp+128h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  if ( *(_DWORD *)a3 && *((_QWORD *)a3 + 2) && *(_DWORD *)a3 != 3 )
  {
    Property = DevFindProperty(&DEVPKEY_Device_InstanceId, 0, 0, *((unsigned int *)a3 + 6), *((_QWORD *)a3 + 4));
    v5 = Property;
    if ( Property )
    {
      try
      {
        std::wstring::wstring(v22, *(_QWORD *)(Property + 40));
        if ( v23 <= 7 )
        {
          v6 = v22;
          v7 = v22;
        }
        else
        {
          v6 = (_WORD *)v22[0];
          v7 = (_QWORD *)v22[0];
        }
        v8 = (unsigned __int16 *)v7 + v22[2];
        v9 = (unsigned __int16 *)v22;
        if ( v23 > 7 )
          v9 = (unsigned __int16 *)v22[0];
        while ( v9 != v8 )
          *v6++ = _o_towlower(*v9++);
        if ( !a2
          || (v10 = std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&void DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&void DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>>>>,0>>::_Find_lower_bound<std::wstring>(
                      a2,
                      v21,
                      v22),
              (unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&void DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&void DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>>>>,0>>::_Lower_bound_duplicate<std::wstring>(
                                 v11,
                                 *(_QWORD *)(v10 + 16),
                                 v22)) )
        {
          std::wstring::_Tidy_deallocate(v22);
        }
        else
        {
          v12 = -1;
          v19 = -1;
          v27 = 131074;
          v28 = DEVPKEY_Device_InstanceId;
          v29 = 0;
          v30 = 0;
          v31 = 18;
          do
            ++v12;
          while ( *(_WORD *)(*(_QWORD *)(v5 + 40) + 2 * v12) );
          v32 = 2 * v12 + 2;
          v33 = *(_QWORD *)(v5 + 40);
          v34 = 2;
          v35 = DEVPKEY_Device_IsPresent;
          v36 = 0;
          v37 = 0;
          v38 = 17;
          v39 = 1;
          v40 = &v19;
          v24 = DEVPKEY_Device_InstallDate;
          v25 = 0;
          v26 = 0;
          v13 = (__int64 *)(*(_QWORD *)std::map<std::wstring,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&void DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>>>::_Try_emplace<std::wstring const &,>(
                                         a2,
                                         v21,
                                         v22)
                          + 64LL);
          v14 = *v13;
          if ( *v13 )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)v20);
            DevCloseObjectQuery(v14);
            wil::last_error_context::~last_error_context((wil::last_error_context *)v20);
          }
          *v13 = 0;
          v15 = DevCreateObjectQuery(3, 1, 1, &v24, 2, &v27, DevQueryGlobalAPOCallback, 0, v13);
          if ( v15 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xCA,
              (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\globalapo.cpp",
              (const char *)(unsigned int)v15,
              v18);
          std::wstring::_Tidy_deallocate(v22);
        }
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0xCD,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\globalapo.cpp",
          v16);
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x98,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\globalapo.cpp",
        (const char *)0x8000FFFFLL,
        v17);
    }
  }
}

```

## disassembly

```asm
0x1800361c0  mov     [rsp+arg_0], rbx
0x1800361c5  push    rsi
0x1800361c6  push    rdi
0x1800361c7  push    r12
0x1800361c9  push    r14
0x1800361cb  push    r15
0x1800361cd  sub     rsp, 140h
0x1800361d4  mov     rax, cs:__security_cookie
0x1800361db  xor     rax, rsp
0x1800361de  mov     [rsp+168h+var_38], rax
0x1800361e6  mov     r14, rdx
0x1800361e9  xor     r12d, r12d
0x1800361ec  cmp     [r8], r12d
0x1800361ef  jz      loc_1800364A3
0x1800361f5  cmp     [r8+10h], r12
0x1800361f9  jz      loc_1800364A3
0x1800361ff  cmp     dword ptr [r8], 3
0x180036203  jz      loc_1800364A3
0x180036209  mov     rax, [r8+20h]
0x18003620d  mov     qword ptr [rsp+168h+var_148], rax; int
0x180036212  mov     r9d, [r8+18h]
0x180036216  xor     r8d, r8d
0x180036219  xor     edx, edx
0x18003621b  lea     rcx, DEVPKEY_Device_InstanceId
0x180036222  call    cs:__imp_DevFindProperty
0x180036228  mov     rsi, rax
0x18003622b  test    rax, rax
0x18003622e  jnz     short loc_180036254
0x180036230  mov     rcx, [rsp+168h]; this
0x180036238  mov     r9d, 8000FFFFh; char *
0x18003623e  lea     r8, aAvcoreAudiocor_8; "avcore\\audiocore\\server\\audioendpoin"...
0x180036245  mov     edx, 98h; void *
0x18003624a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003624f  jmp     loc_1800364A5
0x180036254  mov     rdx, [rax+28h]
0x180036258  lea     rcx, [rsp+168h+var_F0]
0x18003625d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180036262  nop
0x180036263  mov     rcx, [rsp+168h+var_F0]
0x180036268  cmp     [rsp+168h+var_D8], 7
0x180036271  jbe     short loc_18003627B
0x180036273  mov     rdi, rcx
0x180036276  mov     rdx, rcx
0x180036279  jmp     short loc_180036285
0x18003627b  lea     rdi, [rsp+168h+var_F0]
0x180036280  lea     rdx, [rsp+168h+var_F0]
0x180036285  mov     rax, [rsp+168h+var_E0]
0x18003628d  lea     r15, [rdx+rax*2]
0x180036291  lea     rbx, [rsp+168h+var_F0]
0x180036296  cmova   rbx, rcx
0x18003629a  cmp     rbx, r15
0x18003629d  jz      short loc_1800362BB
0x18003629f  movzx   ecx, word ptr [rbx]
0x1800362a2  mov     rax, cs:__imp__o_towlower
0x1800362a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362ae  mov     [rdi], ax
0x1800362b1  add     rbx, 2
0x1800362b5  add     rdi, 2
0x1800362b9  jmp     short loc_18003629A
0x1800362bb  test    r14, r14
0x1800362be  jz      loc_180036497
0x1800362c4  lea     r8, [rsp+168h+var_F0]
0x1800362c9  lea     rdx, [rsp+168h+var_108]
0x1800362ce  mov     rcx, r14
0x1800362d1  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800362d6  lea     r8, [rsp+168h+var_F0]
0x1800362db  mov     rdx, [rax+10h]
0x1800362df  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>>>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>>>,void *> * const,std::wstring const &)
0x1800362e4  test    al, al
0x1800362e6  jnz     loc_180036497
0x1800362ec  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800362f0  mov     [rsp+168h+var_118], cl
0x1800362f4  mov     [rsp+168h+var_A8], 20002h
0x1800362ff  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x180036306  movups  [rsp+168h+var_A0], xmm0
0x18003630e  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x180036314  mov     [rsp+168h+var_90], eax
0x18003631b  mov     [rsp+168h+var_8C], r12d
0x180036323  mov     [rsp+168h+var_88], r12
0x18003632b  mov     [rsp+168h+var_80], 12h
0x180036336  mov     rax, [rsi+28h]
0x18003633a  inc     rcx
0x18003633d  cmp     [rax+rcx*2], r12w
0x180036342  jnz     short loc_18003633A
0x180036344  lea     eax, ds:2[rcx*2]
0x18003634b  mov     [rsp+168h+var_7C], eax
0x180036352  mov     rax, [rsi+28h]
0x180036356  mov     [rsp+168h+var_78], rax
0x18003635e  mov     [rsp+168h+var_70], 2
0x180036369  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_IsPresent.fmtid.Data1
0x180036370  movaps  [rsp+168h+var_68], xmm0
0x180036378  mov     eax, cs:DEVPKEY_Device_IsPresent.pid
0x18003637e  mov     [rsp+168h+var_58], eax
0x180036385  mov     [rsp+168h+var_54], r12d
0x18003638d  mov     [rsp+168h+var_50], r12
0x180036395  mov     [rsp+168h+var_48], 11h
0x1800363a0  mov     esi, 1
0x1800363a5  mov     [rsp+168h+var_44], esi
0x1800363ac  lea     rax, [rsp+168h+var_118]
0x1800363b1  mov     [rsp+168h+var_40], rax
0x1800363b9  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstallDate.fmtid.Data1
0x1800363c0  movups  [rsp+168h+var_D0], xmm0
0x1800363c8  mov     eax, cs:DEVPKEY_Device_InstallDate.pid
0x1800363ce  mov     [rsp+168h+var_C0], eax
0x1800363d5  mov     [rsp+168h+var_BC], r12d
0x1800363dd  mov     [rsp+168h+var_B8], r12
0x1800363e5  lea     r8, [rsp+168h+var_F0]
0x1800363ea  lea     rdx, [rsp+168h+var_108]
0x1800363ef  mov     rcx, r14
0x1800363f2  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800363f7  mov     rbx, [rax]
0x1800363fa  add     rbx, 40h ; '@'
0x1800363fe  mov     rdi, [rbx]
0x180036401  test    rdi, rdi
0x180036404  jz      short loc_180036423
0x180036406  lea     rcx, [rsp+168h+var_110]; this
0x18003640b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180036410  mov     rcx, rdi
0x180036413  call    cs:__imp_DevCloseObjectQuery
0x180036419  lea     rcx, [rsp+168h+var_110]; this
0x18003641e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180036423  mov     [rbx], r12
0x180036426  mov     [rsp+168h+var_128], rbx
0x18003642b  mov     [rsp+168h+var_130], r12
0x180036430  lea     rax, ?DevQueryGlobalAPOCallback@@YAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; DevQueryGlobalAPOCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180036437  mov     [rsp+168h+var_138], rax
0x18003643c  lea     rax, [rsp+168h+var_A8]
0x180036444  mov     [rsp+168h+var_140], rax
0x180036449  mov     [rsp+168h+var_148], 2; int
0x180036451  lea     r9, [rsp+168h+var_D0]
0x180036459  mov     r8d, esi
0x18003645c  mov     edx, esi
0x18003645e  mov     ecx, 3
0x180036463  call    cs:__imp_DevCreateObjectQuery
0x180036469  mov     rcx, [rsp+168h]; this
0x180036471  test    eax, eax
0x180036473  jns     short loc_18003648A
0x180036475  mov     r9d, eax; char *
0x180036478  lea     r8, aAvcoreAudiocor_8; "avcore\\audiocore\\server\\audioendpoin"...
0x18003647f  mov     edx, 0CAh; void *
0x180036484  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180036489  nop
0x18003648a  lea     rcx, [rsp+168h+var_F0]
0x18003648f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036494  nop
0x180036495  jmp     short loc_1800364A5
0x180036497  lea     rcx, [rsp+168h+var_F0]
0x18003649c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800364a1  jmp     short loc_1800364A5
0x1800364a3  jmp     short $+2
0x1800364a5  mov     rcx, [rsp+168h+var_38]
0x1800364ad  xor     rcx, rsp; StackCookie
0x1800364b0  call    __security_check_cookie
0x1800364b5  mov     rbx, [rsp+168h+arg_0]
0x1800364bd  add     rsp, 140h
0x1800364c4  pop     r15
0x1800364c6  pop     r14
0x1800364c8  pop     r12
0x1800364ca  pop     rdi
0x1800364cb  pop     rsi
0x1800364cc  retn
```
