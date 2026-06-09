# Windows::Internal::Management::Provision::ConfigurationData::GetBinary(Windows::Storage::Streams::IBuffer * *)

- ea: `0x18003eea0`
- end: `0x18003efb2`
- name: `?GetBinary@ConfigurationData@Provision@Management@Internal@Windows@@UEAAJPEAPEAUIBuffer@Streams@Storage@5@@Z`
- size: `274`
- prototype: `int(Windows::Internal::Management::Provision::ConfigurationData *__hidden this, struct Windows::Storage::Streams::IBuffer **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180007c45`
- `0x18000a5c4`
- `0x18000dc98`
- `0x18000f088`
- `0x18003e964`
- `0x18003eea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ef03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ef03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ef4e`

## string_xrefs

- `0x18003eec7`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationdata.cpp`
- `0x18003ef22`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationdata.cpp`
- `0x18003ef6d`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Management::Provision::ConfigurationData::GetBinary(
        Windows::Internal::Management::Provision::ConfigurationData *this,
        struct Windows::Storage::Streams::IBuffer **a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  void *v6; // rax
  int v7; // r14d
  int v8; // eax
  wil *v9; // rcx
  unsigned int v10; // edi
  int v12; // eax
  int v13; // [rsp+20h] [rbp-28h]
  int v14; // [rsp+20h] [rbp-28h]
  int v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v17; // [rsp+58h] [rbp+10h]
  char v18; // [rsp+60h] [rbp+18h] BYREF

  v4 = 0;
  if ( a2 )
  {
    wil::EnterCriticalSection(&v18, (char *)this + 104);
    if ( *((_DWORD *)this + 16) == 1 )
    {
      *a2 = 0;
      v6 = CoTaskMemAlloc(*((_QWORD *)this + 12));
      v7 = (int)v6;
      if ( v6 )
      {
        memcpy_0(v6, *((const void **)this + 10), *((_QWORD *)this + 12));
        try
        {
          v8 = Windows::Storage::Streams::MakeCBuffer<void (*)(void *)>(
                 *((_DWORD *)this + 24),
                 *((_DWORD *)this + 24),
                 v7,
                 (_DWORD)CoTaskMemFree,
                 (__int64)a2);
        }
        catch ( ... )
        {
          v12 = wil::ResultFromCaughtException(v9);
          v17 = v12;
          if ( v12 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4A,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationdata.cpp",
              (const char *)(unsigned int)v12,
              v13);
            v4 = v17;
            goto LABEL_11;
          }
          v4 = 0;
          goto LABEL_11;
        }
        v10 = v8;
        if ( v8 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x45,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationdata.cpp",
            (const char *)(unsigned int)v8,
            v15);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v18);
          return v10;
        }
        goto LABEL_11;
      }
      v4 = -2147024882;
      v5 = 54;
    }
    else
    {
      v4 = -2147467259;
      v5 = 48;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationdata.cpp",
      (const char *)v4,
      v14);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v18);
    return v4;
  }
  v4 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2C,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationdata.cpp",
    (const char *)0x80004003LL,
    v14);
  return v4;
}

```

## disassembly

```asm
0x18003eea0  mov     [rsp+arg_0], rbx
0x18003eea5  push    rsi
0x18003eea6  push    rdi
0x18003eea7  push    r14
0x18003eea9  sub     rsp, 30h
0x18003eead  mov     rsi, rdx
0x18003eeb0  mov     rdi, rcx
0x18003eeb3  xor     ebx, ebx
0x18003eeb5  test    rdx, rdx
0x18003eeb8  jnz     short loc_18003EEDB
0x18003eeba  mov     rcx, [rsp+48h]; this
0x18003eebf  mov     ebx, 80004003h
0x18003eec4  mov     r9d, ebx; char *
0x18003eec7  lea     r8, aOnecoreuapAdmi_35; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003eece  lea     edx, [rsi+2Ch]; void *
0x18003eed1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eed6  jmp     loc_18003EFA1
0x18003eedb  lea     rdx, [rcx+68h]
0x18003eedf  lea     rcx, [rsp+48h+arg_10]
0x18003eee4  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18003eee9  nop
0x18003eeea  cmp     dword ptr [rdi+40h], 1
0x18003eeee  jz      short loc_18003EEFC
0x18003eef0  mov     ebx, 80004005h
0x18003eef5  mov     edx, 30h ; '0'
0x18003eefa  jmp     short loc_18003EF1F
0x18003eefc  mov     [rsi], rbx
0x18003eeff  mov     rcx, [rdi+60h]; cb
0x18003ef03  call    cs:__imp_CoTaskMemAlloc
0x18003ef0a  nop     dword ptr [rax+rax+00h]
0x18003ef0f  mov     r14, rax
0x18003ef12  test    rax, rax
0x18003ef15  jnz     short loc_18003EF35
0x18003ef17  mov     ebx, 8007000Eh
0x18003ef1c  lea     edx, [rax+36h]; void *
0x18003ef1f  mov     r9d, ebx; char *
0x18003ef22  lea     r8, aOnecoreuapAdmi_35; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003ef29  mov     rcx, [rsp+48h]; this
0x18003ef2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ef33  jmp     short loc_18003EF97
0x18003ef35  mov     r8, [rdi+60h]; Size
0x18003ef39  mov     rdx, [rdi+50h]; Src
0x18003ef3d  mov     rcx, r14; void *
0x18003ef40  call    memcpy_0
0x18003ef45  nop
0x18003ef46  mov     ecx, [rdi+60h]
0x18003ef49  mov     qword ptr [rsp+48h+var_28], rsi; int
0x18003ef4e  mov     r9, cs:__imp_CoTaskMemFree
0x18003ef55  mov     r8, r14
0x18003ef58  mov     edx, ecx
0x18003ef5a  call    ??$MakeCBuffer@P6AXPEAX@Z@Streams@Storage@Windows@@YAJIIPEAEP6AXPEAX@ZPEAPEAUIBuffer@012@@Z; Windows::Storage::Streams::MakeCBuffer<void (*)(void *)>(uint,uint,uchar *,void (*)(void *),Windows::Storage::Streams::IBuffer * *)
0x18003ef5f  mov     edi, eax
0x18003ef61  test    eax, eax
0x18003ef63  jns     short loc_18003EF8D
0x18003ef65  mov     rcx, [rsp+48h]; this
0x18003ef6a  mov     r9d, eax; char *
0x18003ef6d  lea     r8, aOnecoreuapAdmi_35; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003ef74  mov     edx, 45h ; 'E'; void *
0x18003ef79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ef7e  nop
0x18003ef7f  lea     rcx, [rsp+48h+arg_10]
0x18003ef84  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003ef89  mov     eax, edi
0x18003ef8b  jmp     short loc_18003EFA3
0x18003ef8d  jmp     short loc_18003EF97
0x18003ef8f  mov     ebx, [rsp+48h+arg_8]
0x18003ef93  jmp     short loc_18003EF97
0x18003ef95  xor     ebx, ebx
0x18003ef97  lea     rcx, [rsp+48h+arg_10]
0x18003ef9c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003efa1  mov     eax, ebx
0x18003efa3  mov     rbx, [rsp+48h+arg_0]
0x18003efa8  add     rsp, 30h
0x18003efac  pop     r14
0x18003efae  pop     rdi
0x18003efaf  pop     rsi
0x18003efb0  retn
```
