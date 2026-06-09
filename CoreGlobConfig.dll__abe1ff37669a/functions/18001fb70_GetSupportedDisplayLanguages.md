# GetSupportedDisplayLanguages

- ea: `0x18001fb70`
- end: `0x18001fdfe`
- name: `GetSupportedDisplayLanguages`
- size: `654`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `reparse_path, registry_config, service_task, installer_update`

## callees

- `0x180002380`
- `0x180008294`
- `0x180009d24`
- `0x18000e928`
- `0x18000f35c`
- `0x18000f768`
- `0x1800113ac`
- `0x1800118c0`
- `0x18001210c`
- `0x180016620`
- `0x180016d8c`
- `0x18001997c`
- `0x180019f30`
- `0x18001d564`
- `0x18001ddf4`
- `0x18001de84`
- `0x18001fb70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001fc91`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001fc91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001fd29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001fd29`

## string_xrefs

- `0x18001fc51`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18001fd9d`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetSupportedDisplayLanguages(unsigned __int16 a1, int a2, int a3, _QWORD *a4, __int64 *a5)
{
  DWORD v9; // ecx
  int v10; // eax
  unsigned int v11; // edi
  unsigned int v12; // r8d
  const char *v13; // r9
  __int64 result; // rax
  __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rax
  void *v18; // rax
  void *v19[2]; // [rsp+20h] [rbp-1F8h] BYREF
  _QWORD v20[4]; // [rsp+30h] [rbp-1E8h] BYREF
  _BYTE v21[32]; // [rsp+50h] [rbp-1C8h] BYREF
  _BYTE v22[32]; // [rsp+70h] [rbp-1A8h] BYREF
  _QWORD v23[42]; // [rsp+90h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v23,
    (__int64)"GetSupportedDisplayLanguagesActivity");
  v23[0] = &CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity::`vftable';
  CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity::StartActivity((CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity *)v23);
  *a4 = 0;
  *a5 = 0;
  if ( a1 == 45
    || !a1
    || (unsigned __int16)(a1 - 48) <= 9u
    || (unsigned __int16)(a1 - 65) <= 0x19u
    || (unsigned __int16)(a1 - 97) <= 0x19u )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x173,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)0x80070057LL,
      (int)v19[0]);
    CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity::~GetSupportedDisplayLanguagesActivity((CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity *)v23);
    return 2147942487LL;
  }
  else
  {
    if ( a3 == 1 )
    {
      v9 = 40;
    }
    else
    {
      v9 = 24;
      if ( a3 == 2 )
        v9 = 72;
    }
    try
    {
      v10 = PopulateInstalledLanguages(v9);
      v11 = v10;
      if ( v10 >= 0 )
      {
        std::wstring::wstring(v21);
        v19[1] = &stru_180032FB8;
        AcquireSRWLockShared(&stru_180032FB8);
        v15 = qword_180032FA8 - qword_180032FA0;
        if ( a2 )
        {
          if ( a2 == 1 )
          {
            NormalizeAllLanguageTagsIntoNewContainer(v20);
            v17 = DelimitedStringFromItems<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(
                    v22,
                    v20[0],
                    v20[1],
                    a1);
            std::wstring::operator=(v21, v17);
            std::wstring::_Tidy_deallocate(v22);
            std::vector<std::wstring>::_Tidy(v20);
          }
        }
        else
        {
          v16 = DelimitedStringFromItems<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(
                  v20,
                  qword_180032FA0,
                  qword_180032FA8,
                  a1);
          std::wstring::operator=(v21, v16);
          std::wstring::_Tidy_deallocate(v20);
        }
        ReleaseSRWLockShared(&stru_180032FB8);
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
        wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v19);
        v18 = v19[0];
        v19[0] = 0;
        *a4 = v18;
        *a5 = v15 >> 5;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v19);
        std::wstring::_Tidy_deallocate(v21);
        wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::Stop(
          v23,
          0);
        CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity::~GetSupportedDisplayLanguagesActivity((CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity *)v23);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x186,
          (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
          (const char *)(unsigned int)v10,
          (int)v19[0]);
        CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity::~GetSupportedDisplayLanguagesActivity((CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity *)v23);
        result = v11;
      }
    }
    catch ( ... )
    {
      LODWORD(v19[0]) = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x1A1, v12, v13);
      CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity::~GetSupportedDisplayLanguagesActivity((CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity *)v23);
      return LODWORD(v19[0]);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001fb70  mov     [rsp+arg_8], rbx
0x18001fb75  mov     [rsp+arg_10], rsi
0x18001fb7a  push    rdi
0x18001fb7b  push    r12
0x18001fb7d  push    r13
0x18001fb7f  push    r14
0x18001fb81  push    r15
0x18001fb83  sub     rsp, 1F0h
0x18001fb8a  mov     rax, cs:__security_cookie
0x18001fb91  xor     rax, rsp
0x18001fb94  mov     [rsp+218h+var_38], rax
0x18001fb9c  mov     r14, r9
0x18001fb9f  mov     edi, r8d
0x18001fba2  mov     esi, edx
0x18001fba4  movzx   ebx, cx
0x18001fba7  mov     r15, [rsp+218h+arg_20]
0x18001fbaf  xor     r12d, r12d
0x18001fbb2  lea     rdx, aGetsupporteddi_0; "GetSupportedDisplayLanguagesActivity"
0x18001fbb9  lea     rcx, [rsp+218h+var_188]
0x18001fbc1  call    ??0?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001fbc6  lea     rax, ??_7GetSupportedDisplayLanguagesActivity@CoreGlobConfigTraceLogging@@6B@; const CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity::`vftable'
0x18001fbcd  mov     [rsp+218h+var_188], rax
0x18001fbd5  lea     rcx, [rsp+218h+var_188]; this
0x18001fbdd  call    ?StartActivity@GetSupportedDisplayLanguagesActivity@CoreGlobConfigTraceLogging@@QEAAXXZ; CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity::StartActivity(void)
0x18001fbe2  nop
0x18001fbe3  mov     [r14], r12
0x18001fbe6  mov     [r15], r12
0x18001fbe9  cmp     bx, 2Dh ; '-'
0x18001fbed  jz      loc_18001FD8D
0x18001fbf3  test    bx, bx
0x18001fbf6  jz      loc_18001FD8D
0x18001fbfc  lea     eax, [rbx-30h]
0x18001fbff  cmp     ax, 9
0x18001fc03  jbe     loc_18001FD8D
0x18001fc09  lea     eax, [rbx-41h]
0x18001fc0c  cmp     ax, 19h
0x18001fc10  jbe     loc_18001FD8D
0x18001fc16  lea     eax, [rbx-61h]
0x18001fc19  cmp     ax, 19h
0x18001fc1d  jbe     loc_18001FD8D
0x18001fc23  cmp     edi, 1
0x18001fc26  jnz     short loc_18001FC2D
0x18001fc28  lea     ecx, [rdi+27h]
0x18001fc2b  jmp     short loc_18001FC3B
0x18001fc2d  mov     ecx, 18h
0x18001fc32  lea     eax, [rcx+30h]
0x18001fc35  cmp     edi, 2
0x18001fc38  cmovz   ecx, eax; dwFlags
0x18001fc3b  call    ?PopulateInstalledLanguages@@YAJK@Z; PopulateInstalledLanguages(ulong)
0x18001fc40  mov     edi, eax
0x18001fc42  test    eax, eax
0x18001fc44  jns     short loc_18001FC77
0x18001fc46  mov     rcx, [rsp+218h]; this
0x18001fc4e  mov     r9d, eax; char *
0x18001fc51  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001fc58  mov     edx, 186h; void *
0x18001fc5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fc62  nop
0x18001fc63  lea     rcx, [rsp+218h+var_188]; this
0x18001fc6b  call    ??1GetSupportedDisplayLanguagesActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity::~GetSupportedDisplayLanguagesActivity(void)
0x18001fc70  mov     eax, edi
0x18001fc72  jmp     loc_18001FDD1
0x18001fc77  lea     rcx, [rsp+218h+var_1C8]
0x18001fc7c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001fc81  nop
0x18001fc82  lea     r13, stru_180032FB8
0x18001fc89  mov     [rsp+218h+var_1F0], r13
0x18001fc8e  mov     rcx, r13; SRWLock
0x18001fc91  call    cs:__imp_AcquireSRWLockShared
0x18001fc97  nop
0x18001fc98  mov     r8, cs:qword_180032FA8
0x18001fc9f  mov     rdi, r8
0x18001fca2  mov     rdx, cs:qword_180032FA0
0x18001fca9  sub     rdi, rdx
0x18001fcac  test    esi, esi
0x18001fcae  jnz     short loc_18001FCD7
0x18001fcb0  movzx   r9d, bx
0x18001fcb4  lea     rcx, [rsp+218h+var_1E8]
0x18001fcb9  call    ??$DelimitedStringFromItems@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@0G@Z; DelimitedStringFromItems<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,ushort)
0x18001fcbe  mov     rdx, rax
0x18001fcc1  lea     rcx, [rsp+218h+var_1C8]
0x18001fcc6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001fccb  lea     rcx, [rsp+218h+var_1E8]
0x18001fcd0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fcd5  jmp     short loc_18001FD22
0x18001fcd7  cmp     esi, 1
0x18001fcda  jnz     short loc_18001FD22
0x18001fcdc  lea     rcx, [rsp+218h+var_1E8]
0x18001fce1  call    ?NormalizeAllLanguageTagsIntoNewContainer@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV12@@Z; NormalizeAllLanguageTagsIntoNewContainer(std::vector<std::wstring> &)
0x18001fce6  nop
0x18001fce7  movzx   r9d, bx
0x18001fceb  mov     r8, [rsp+218h+var_1E0]
0x18001fcf0  mov     rdx, [rsp+218h+var_1E8]
0x18001fcf5  lea     rcx, [rsp+218h+var_1A8]
0x18001fcfa  call    ??$DelimitedStringFromItems@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@0G@Z; DelimitedStringFromItems<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,ushort)
0x18001fcff  mov     rdx, rax
0x18001fd02  lea     rcx, [rsp+218h+var_1C8]
0x18001fd07  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001fd0c  lea     rcx, [rsp+218h+var_1A8]
0x18001fd11  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fd16  nop
0x18001fd17  lea     rcx, [rsp+218h+var_1E8]
0x18001fd1c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001fd21  nop
0x18001fd22  sar     rdi, 5
0x18001fd26  mov     rcx, r13; SRWLock
0x18001fd29  call    cs:__imp_ReleaseSRWLockShared
0x18001fd2f  lea     rcx, [rsp+218h+var_1C8]
0x18001fd34  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001fd39  mov     rdx, rax
0x18001fd3c  lea     rcx, [rsp+218h+var_1F8]
0x18001fd41  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001fd46  mov     rax, [rsp+218h+var_1F8]
0x18001fd4b  mov     [rsp+218h+var_1F8], r12
0x18001fd50  mov     [r14], rax
0x18001fd53  mov     [r15], rdi
0x18001fd56  lea     rcx, [rsp+218h+var_1F8]
0x18001fd5b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001fd60  nop
0x18001fd61  lea     rcx, [rsp+218h+var_1C8]
0x18001fd66  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fd6b  nop
0x18001fd6c  xor     edx, edx
0x18001fd6e  lea     rcx, [rsp+218h+var_188]
0x18001fd76  call    ?Stop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001fd7b  nop
0x18001fd7c  lea     rcx, [rsp+218h+var_188]; this
0x18001fd84  call    ??1GetSupportedDisplayLanguagesActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity::~GetSupportedDisplayLanguagesActivity(void)
0x18001fd89  xor     eax, eax
0x18001fd8b  jmp     short loc_18001FDD1
0x18001fd8d  mov     rcx, [rsp+218h]; this
0x18001fd95  mov     ebx, 80070057h
0x18001fd9a  mov     r9d, ebx; char *
0x18001fd9d  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001fda4  mov     edx, 173h; void *
0x18001fda9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fdae  nop
0x18001fdaf  lea     rcx, [rsp+218h+var_188]; this
0x18001fdb7  call    ??1GetSupportedDisplayLanguagesActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity::~GetSupportedDisplayLanguagesActivity(void)
0x18001fdbc  mov     eax, ebx
0x18001fdbe  jmp     short loc_18001FDD1
0x18001fdc0  lea     rcx, [rsp+218h+var_188]; this
0x18001fdc8  call    ??1GetSupportedDisplayLanguagesActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity::~GetSupportedDisplayLanguagesActivity(void)
0x18001fdcd  mov     eax, dword ptr [rsp+218h+var_1F8]
0x18001fdd1  mov     rcx, [rsp+218h+var_38]
0x18001fdd9  xor     rcx, rsp; StackCookie
0x18001fddc  call    __security_check_cookie
0x18001fde1  lea     r11, [rsp+218h+var_28]
0x18001fde9  mov     rbx, [r11+38h]
0x18001fded  mov     rsi, [r11+40h]
0x18001fdf1  mov     rsp, r11
0x18001fdf4  pop     r15
0x18001fdf6  pop     r14
0x18001fdf8  pop     r13
0x18001fdfa  pop     r12
0x18001fdfc  pop     rdi
0x18001fdfd  retn
```
