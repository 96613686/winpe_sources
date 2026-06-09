# Windows::Internal::Management::Provision::ConfigurationData::GetBinary(Windows::Storage::Streams::IBuffer * *)

- ea: `0x18003f480`
- end: `0x18003f58b`
- name: `?GetBinary@ConfigurationData@Provision@Management@Internal@Windows@@UEAAJPEAPEAUIBuffer@Streams@Storage@5@@Z`
- size: `267`
- prototype: `int(Windows::Internal::Management::Provision::ConfigurationData *__hidden this, struct Windows::Storage::Streams::IBuffer **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180007ad5`
- `0x18000a2a4`
- `0x18000d79c`
- `0x18000eaf4`
- `0x18003ef70`
- `0x18003f480`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f528`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f4e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f4e3`

## string_xrefs

- `0x18003f4a7`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationdata.cpp`
- `0x18003f4fc`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationdata.cpp`
- `0x18003f547`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationdata.cpp`

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
0x18003f480  mov     [rsp+arg_0], rbx
0x18003f485  push    rsi
0x18003f486  push    rdi
0x18003f487  push    r14
0x18003f489  sub     rsp, 30h
0x18003f48d  mov     rsi, rdx
0x18003f490  mov     rdi, rcx
0x18003f493  xor     ebx, ebx
0x18003f495  test    rdx, rdx
0x18003f498  jnz     short loc_18003F4BB
0x18003f49a  mov     rcx, [rsp+48h]; this
0x18003f49f  mov     ebx, 80004003h
0x18003f4a4  mov     r9d, ebx; char *
0x18003f4a7  lea     r8, aOnecoreuapAdmi_35; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003f4ae  lea     edx, [rsi+2Ch]; void *
0x18003f4b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f4b6  jmp     loc_18003F57B
0x18003f4bb  lea     rdx, [rcx+68h]
0x18003f4bf  lea     rcx, [rsp+48h+arg_10]
0x18003f4c4  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18003f4c9  nop
0x18003f4ca  cmp     dword ptr [rdi+40h], 1
0x18003f4ce  jz      short loc_18003F4DC
0x18003f4d0  mov     ebx, 80004005h
0x18003f4d5  mov     edx, 30h ; '0'
0x18003f4da  jmp     short loc_18003F4F9
0x18003f4dc  mov     [rsi], rbx
0x18003f4df  mov     rcx, [rdi+60h]; cb
0x18003f4e3  call    cs:__imp_CoTaskMemAlloc
0x18003f4e9  mov     r14, rax
0x18003f4ec  test    rax, rax
0x18003f4ef  jnz     short loc_18003F50F
0x18003f4f1  mov     ebx, 8007000Eh
0x18003f4f6  lea     edx, [rax+36h]; void *
0x18003f4f9  mov     r9d, ebx; char *
0x18003f4fc  lea     r8, aOnecoreuapAdmi_35; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003f503  mov     rcx, [rsp+48h]; this
0x18003f508  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f50d  jmp     short loc_18003F571
0x18003f50f  mov     r8, [rdi+60h]; Size
0x18003f513  mov     rdx, [rdi+50h]; Src
0x18003f517  mov     rcx, r14; void *
0x18003f51a  call    memcpy_0
0x18003f51f  nop
0x18003f520  mov     ecx, [rdi+60h]
0x18003f523  mov     qword ptr [rsp+48h+var_28], rsi; int
0x18003f528  mov     r9, cs:__imp_CoTaskMemFree
0x18003f52f  mov     r8, r14
0x18003f532  mov     edx, ecx
0x18003f534  call    ??$MakeCBuffer@P6AXPEAX@Z@Streams@Storage@Windows@@YAJIIPEAEP6AXPEAX@ZPEAPEAUIBuffer@012@@Z; Windows::Storage::Streams::MakeCBuffer<void (*)(void *)>(uint,uint,uchar *,void (*)(void *),Windows::Storage::Streams::IBuffer * *)
0x18003f539  mov     edi, eax
0x18003f53b  test    eax, eax
0x18003f53d  jns     short loc_18003F567
0x18003f53f  mov     rcx, [rsp+48h]; this
0x18003f544  mov     r9d, eax; char *
0x18003f547  lea     r8, aOnecoreuapAdmi_35; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003f54e  mov     edx, 45h ; 'E'; void *
0x18003f553  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f558  nop
0x18003f559  lea     rcx, [rsp+48h+arg_10]
0x18003f55e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003f563  mov     eax, edi
0x18003f565  jmp     short loc_18003F57D
0x18003f567  jmp     short loc_18003F571
0x18003f569  mov     ebx, [rsp+48h+arg_8]
0x18003f56d  jmp     short loc_18003F571
0x18003f56f  xor     ebx, ebx
0x18003f571  lea     rcx, [rsp+48h+arg_10]
0x18003f576  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003f57b  mov     eax, ebx
0x18003f57d  mov     rbx, [rsp+48h+arg_0]
0x18003f582  add     rsp, 30h
0x18003f586  pop     r14
0x18003f588  pop     rdi
0x18003f589  pop     rsi
0x18003f58a  retn
```
