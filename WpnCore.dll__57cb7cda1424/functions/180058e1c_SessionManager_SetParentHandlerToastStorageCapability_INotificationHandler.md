# SessionManager::SetParentHandlerToastStorageCapability(INotificationHandler *)

- ea: `0x180058e1c`
- end: `0x18005902c`
- name: `?SetParentHandlerToastStorageCapability@SessionManager@@AEAAJPEAUINotificationHandler@@@Z`
- size: `528`
- prototype: `__int64 __fastcall(SessionManager *__hidden this, struct INotificationHandler *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180058590`

## callees

- `0x180004e38`
- `0x180011618`
- `0x18001bf30`
- `0x180045c9c`
- `0x180058e1c`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180058eda`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180058eda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058e73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058f89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059008`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058e73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058f89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059008`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059017`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SessionManager::SetParentHandlerToastStorageCapability(
        SessionManager *this,
        struct INotificationHandler *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  void *v7; // rcx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rcx
  LPVOID v13[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v15; // [rsp+58h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+30h] BYREF
  LPVOID v17; // [rsp+68h] [rbp+38h] BYREF

  pv = 0;
  v4 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, &pv);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\sessionmanager.cpp",
      (const char *)(unsigned int)v4,
      (int)v13[0]);
LABEL_3:
    if ( pv )
      CoTaskMemFree(pv);
    return v5;
  }
  v7 = pv;
  if ( pv )
  {
    if ( *(_WORD *)pv )
    {
      v17 = 0;
      v8 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 24LL))(a2, &v17);
      v5 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\sessionmanager.cpp",
          (const char *)(unsigned int)v8,
          (int)v13[0]);
LABEL_21:
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
        return v5;
      }
      if ( (unsigned int)_o__wcsicmp(v17, pv) )
      {
        v15 = 0;
        v13[0] = pv;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
        v9 = Microsoft::WRL::Details::MakeAndInitialize<NotificationSettings,NotificationSettings,unsigned short *>(
               &v15,
               v13);
        v5 = v9;
        if ( v9 < 0 )
        {
          v10 = 97;
LABEL_20:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v10,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\sessionmanager.cpp",
            (const char *)(unsigned int)v9,
            (int)v13[0]);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
          goto LABEL_21;
        }
        v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)(v15 + 32) + 40LL))(
                v15 + 32,
                L"c:storage:toast",
                1);
        v5 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x62,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\sessionmanager.cpp",
            (const char *)(unsigned int)v11,
            (int)v13[0]);
          v12 = v15;
          if ( v15 )
          {
            v15 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          }
          if ( v17 )
            CoTaskMemFree(v17);
          goto LABEL_3;
        }
        v9 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 7) + 216LL))(
               *((_QWORD *)this + 7),
               (v15 + 32) & -(__int64)(v15 != 0));
        v5 = v9;
        if ( v9 < 0 )
        {
          v10 = 99;
          goto LABEL_20;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      }
      if ( v17 )
        CoTaskMemFree(v17);
      v7 = pv;
    }
    if ( v7 )
      CoTaskMemFree(v7);
  }
  return 0;
}

```

## disassembly

```asm
0x180058e1c  mov     [rsp-18h+arg_0], rbx
0x180058e21  push    rbp
0x180058e22  push    rsi
0x180058e23  push    rdi
0x180058e24  mov     rbp, rsp
0x180058e27  sub     rsp, 30h
0x180058e2b  mov     rdi, rdx
0x180058e2e  mov     rsi, rcx
0x180058e31  mov     [rbp+pv], 0
0x180058e39  mov     rax, [rdx]
0x180058e3c  lea     rdx, [rbp+pv]
0x180058e40  mov     rcx, rdi
0x180058e43  mov     rax, [rax+28h]
0x180058e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e4c  mov     ebx, eax
0x180058e4e  test    eax, eax
0x180058e50  jns     short loc_180058E80
0x180058e52  mov     rcx, [rbp+18h]; this
0x180058e56  mov     r9d, eax; char *
0x180058e59  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180058e60  mov     edx, 56h ; 'V'; void *
0x180058e65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058e6a  mov     rcx, [rbp+pv]; pv
0x180058e6e  test    rcx, rcx
0x180058e71  jz      short loc_180058E79
0x180058e73  call    cs:__imp_CoTaskMemFree
0x180058e79  mov     eax, ebx
0x180058e7b  jmp     loc_18005901F
0x180058e80  mov     rcx, [rbp+pv]
0x180058e84  test    rcx, rcx
0x180058e87  jz      loc_18005901D
0x180058e8d  xor     eax, eax
0x180058e8f  cmp     ax, [rcx]
0x180058e92  jz      loc_180059012
0x180058e98  mov     [rbp+arg_18], rax
0x180058e9c  mov     rax, [rdi]
0x180058e9f  lea     rdx, [rbp+arg_18]
0x180058ea3  mov     rcx, rdi
0x180058ea6  mov     rax, [rax+18h]
0x180058eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058eaf  mov     ebx, eax
0x180058eb1  test    eax, eax
0x180058eb3  jns     short loc_180058ED2
0x180058eb5  mov     rcx, [rbp+18h]; this
0x180058eb9  mov     r9d, eax; char *
0x180058ebc  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180058ec3  mov     edx, 5Bh ; '['; void *
0x180058ec8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058ecd  jmp     loc_180058FDF
0x180058ed2  mov     rdx, [rbp+pv]
0x180058ed6  mov     rcx, [rbp+arg_18]
0x180058eda  call    cs:__imp__o__wcsicmp
0x180058ee0  test    eax, eax
0x180058ee2  jz      loc_180058FFF
0x180058ee8  mov     [rbp+arg_8], 0
0x180058ef0  mov     rax, [rbp+pv]
0x180058ef4  mov     [rbp+var_10], rax
0x180058ef8  lea     rcx, [rbp+arg_8]
0x180058efc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180058f01  lea     rdx, [rbp+var_10]
0x180058f05  lea     rcx, [rbp+arg_8]
0x180058f09  call    ??$MakeAndInitialize@VNotificationSettings@@V1@PEAG@Details@WRL@Microsoft@@YAJPEAPEAVNotificationSettings@@$$QEAPEAG@Z; Microsoft::WRL::Details::MakeAndInitialize<NotificationSettings,NotificationSettings,ushort *>(NotificationSettings * *,ushort * &&)
0x180058f0e  mov     ebx, eax
0x180058f10  test    eax, eax
0x180058f12  jns     short loc_180058F1E
0x180058f14  mov     edx, 61h ; 'a'
0x180058f19  jmp     loc_180058FC3
0x180058f1e  mov     rcx, [rbp+arg_8]
0x180058f22  add     rcx, 20h ; ' '
0x180058f26  mov     rax, [rcx]
0x180058f29  mov     r8d, 1
0x180058f2f  mov     rdx, cs:off_18011DE98; "c:storage:toast"
0x180058f36  mov     rax, [rax+28h]
0x180058f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058f3f  mov     ebx, eax
0x180058f41  test    eax, eax
0x180058f43  jns     short loc_180058F94
0x180058f45  mov     rcx, [rbp+18h]; this
0x180058f49  mov     r9d, eax; char *
0x180058f4c  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180058f53  mov     edx, 62h ; 'b'; void *
0x180058f58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058f5d  nop
0x180058f5e  mov     rcx, [rbp+arg_8]
0x180058f62  test    rcx, rcx
0x180058f65  jz      short loc_180058F7C
0x180058f67  mov     [rbp+arg_8], 0
0x180058f6f  mov     rax, [rcx]
0x180058f72  mov     rax, [rax+10h]
0x180058f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058f7b  nop
0x180058f7c  mov     rcx, [rbp+arg_18]; pv
0x180058f80  test    rcx, rcx
0x180058f83  jz      loc_180058E6A
0x180058f89  call    cs:__imp_CoTaskMemFree
0x180058f8f  jmp     loc_180058E6A
0x180058f94  mov     rcx, [rsi+38h]
0x180058f98  mov     rdx, [rbp+arg_8]
0x180058f9c  mov     r8, [rcx]
0x180058f9f  lea     rax, [rdx+20h]
0x180058fa3  neg     rdx
0x180058fa6  sbb     rdx, rdx
0x180058fa9  and     rdx, rax
0x180058fac  mov     rax, [r8+0D8h]
0x180058fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058fb8  mov     ebx, eax
0x180058fba  test    eax, eax
0x180058fbc  jns     short loc_180058FF6
0x180058fbe  mov     edx, 63h ; 'c'; void *
0x180058fc3  mov     r9d, eax; char *
0x180058fc6  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180058fcd  mov     rcx, [rbp+18h]; this
0x180058fd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058fd6  lea     rcx, [rbp+arg_8]
0x180058fda  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180058fdf  lea     rcx, [rbp+arg_18]
0x180058fe3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180058fe8  lea     rcx, [rbp+pv]
0x180058fec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180058ff1  jmp     loc_180058E79
0x180058ff6  lea     rcx, [rbp+arg_8]
0x180058ffa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180058fff  mov     rcx, [rbp+arg_18]; pv
0x180059003  test    rcx, rcx
0x180059006  jz      short loc_18005900E
0x180059008  call    cs:__imp_CoTaskMemFree
0x18005900e  mov     rcx, [rbp+pv]; pv
0x180059012  test    rcx, rcx
0x180059015  jz      short loc_18005901D
0x180059017  call    cs:__imp_CoTaskMemFree
0x18005901d  xor     eax, eax
0x18005901f  mov     rbx, [rsp+30h+arg_0]
0x180059024  add     rsp, 30h
0x180059028  pop     rdi
0x180059029  pop     rsi
0x18005902a  pop     rbp
0x18005902b  retn
```
