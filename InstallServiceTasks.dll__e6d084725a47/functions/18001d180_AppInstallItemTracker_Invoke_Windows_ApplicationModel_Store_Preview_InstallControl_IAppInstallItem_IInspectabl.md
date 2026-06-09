# AppInstallItemTracker::Invoke(Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *,IInspectable *)

- ea: `0x18001d180`
- end: `0x18001d3bb`
- name: `?Invoke@AppInstallItemTracker@@UEAAJPEAUIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Z`
- size: `571`
- prototype: `__int64 __fastcall(AppInstallItemTracker *__hidden this, struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *, struct IInspectable *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000760c`
- `0x18000912c`
- `0x18000fd08`
- `0x180012f10`
- `0x18001d180`
- `0x180046010`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x18001d196`
- `msvcp_win!_Xtime_get_ticks` at `0x18001d196`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d2ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d361`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d2ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d361`

## string_xrefs

- `0x18001d1e1`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001d236`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001d2ef`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001d3a3`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001d2e2`: `AppInstallItemTracker::Invoke`
- `0x18001d396`: `AppInstallItemTracker::Invoke`
- `0x18001d2ce`: `Tracking ProductId: %s. Marking Complete. State = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppInstallItemTracker::Invoke(
        AppInstallItemTracker *this,
        struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *a2,
        struct IInspectable *a3)
{
  __int64 v5; // rbx
  __int64 (*v6)(void); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 result; // rax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // ebx
  PCWSTR StringRawBuffer; // rax
  void *v15; // rdx
  PCWSTR v16; // rax
  int v17; // ebx
  PCWSTR v18; // rax
  void *v19; // rdx
  int v20; // [rsp+20h] [rbp-48h]
  int v21; // [rsp+48h] [rbp-20h]
  int v22; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v25; // [rsp+78h] [rbp+10h] BYREF
  __int64 v26; // [rsp+88h] [rbp+20h] BYREF

  v5 = *((_QWORD *)this + 9);
  *(_QWORD *)(v5 + 24) = _Xtime_get_ticks();
  v26 = 0;
  v6 = *(__int64 (**)(void))(*(_QWORD *)a2 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  try
  {
    v7 = v6();
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBE,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
        (const char *)(unsigned int)v7,
        v20);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      return v8;
    }
    v25 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 48LL))(v26, &v25);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC0,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
        (const char *)(unsigned int)v11,
        v20);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      return v12;
    }
    v13 = v25;
    if ( v25 > 7 )
    {
      if ( v25 == 8 || v25 == 9 || v25 == 10 || v25 == 11 || v25 == 12 )
        goto LABEL_10;
      if ( v25 != 13 )
        goto LABEL_11;
    }
    else
    {
      if ( v25 == 7 )
        goto LABEL_10;
      if ( (unsigned int)v25 >= 6 )
      {
        if ( v25 != 6 )
        {
LABEL_11:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
          return 0;
        }
LABEL_10:
        StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 11), 0);
        v21 = v13;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
          0xD3u,
          "AppInstallItemTracker::Invoke",
          -1,
          L"Tracking ProductId: %s. Marking Complete. State = %d",
          0,
          0,
          StringRawBuffer,
          v21);
        wil::details::SetEvent(*((wil::details **)this + 12), v15);
        goto LABEL_11;
      }
    }
    v16 = WindowsGetStringRawBuffer(*((HSTRING *)this + 11), 0);
    v22 = v13;
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
      0xCAu,
      "AppInstallItemTracker::Invoke",
      -1,
      L"Tracking ProductId: %s. In Progress. State = %d",
      0,
      0,
      v16,
      v22);
    goto LABEL_11;
  }
  catch ( ... )
  {
    v17 = wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0xDB,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
            v9);
    v25 = v17;
    v18 = WindowsGetStringRawBuffer(*((HSTRING *)this + 11), 0);
    LogMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
      0xDCu,
      "AppInstallItemTracker::Invoke",
      v17,
      L"Error Querying Status for ProductId: %s. Marking as Completed",
      0,
      0,
      v18);
    wil::details::SetEvent(*((wil::details **)this + 12), v19);
    return (unsigned int)v25;
  }
  return result;
}

```

## disassembly

```asm
0x18001d180  mov     [rsp+arg_0], rcx
0x18001d185  push    rbx
0x18001d186  push    rsi
0x18001d187  push    rdi
0x18001d188  sub     rsp, 50h
0x18001d18c  mov     rsi, rdx
0x18001d18f  mov     rdi, rcx
0x18001d192  mov     rbx, [rcx+48h]
0x18001d196  call    cs:__imp__Xtime_get_ticks
0x18001d19c  mov     [rbx+18h], rax
0x18001d1a0  mov     [rsp+68h+arg_18], 0
0x18001d1ac  mov     rax, [rsi]
0x18001d1af  mov     rbx, [rax+50h]
0x18001d1b3  lea     rcx, [rsp+68h+arg_18]
0x18001d1bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d1c0  lea     rdx, [rsp+68h+arg_18]
0x18001d1c8  mov     rcx, rsi
0x18001d1cb  mov     rax, rbx
0x18001d1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1d3  mov     ebx, eax
0x18001d1d5  test    eax, eax
0x18001d1d7  jns     short loc_18001D207
0x18001d1d9  mov     rcx, [rsp+68h]; this
0x18001d1de  mov     r9d, eax; char *
0x18001d1e1  lea     r8, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001d1e8  mov     edx, 0BEh; void *
0x18001d1ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d1f2  nop
0x18001d1f3  lea     rcx, [rsp+68h+arg_18]
0x18001d1fb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d200  mov     eax, ebx
0x18001d202  jmp     loc_18001D31F
0x18001d207  mov     [rsp+68h+arg_8], 0
0x18001d20f  mov     rcx, [rsp+68h+arg_18]
0x18001d217  mov     rax, [rcx]
0x18001d21a  lea     rdx, [rsp+68h+arg_8]
0x18001d21f  mov     rax, [rax+30h]
0x18001d223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d228  mov     ebx, eax
0x18001d22a  test    eax, eax
0x18001d22c  jns     short loc_18001D25C
0x18001d22e  mov     rcx, [rsp+68h]; this
0x18001d233  mov     r9d, eax; char *
0x18001d236  lea     r8, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001d23d  mov     edx, 0C0h; void *
0x18001d242  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d247  nop
0x18001d248  lea     rcx, [rsp+68h+arg_18]
0x18001d250  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d255  mov     eax, ebx
0x18001d257  jmp     loc_18001D31F
0x18001d25c  mov     ebx, [rsp+68h+arg_8]
0x18001d260  cmp     ebx, 7
0x18001d263  jg      loc_18001D327
0x18001d269  jz      short loc_18001D2A7
0x18001d26b  mov     ecx, ebx
0x18001d26d  test    ebx, ebx
0x18001d26f  jz      loc_18001D35B
0x18001d275  sub     ecx, 1
0x18001d278  jz      loc_18001D35B
0x18001d27e  sub     ecx, 1
0x18001d281  jz      loc_18001D35B
0x18001d287  sub     ecx, 1
0x18001d28a  jz      loc_18001D35B
0x18001d290  sub     ecx, 1
0x18001d293  jz      loc_18001D35B
0x18001d299  sub     ecx, 1
0x18001d29c  jz      loc_18001D35B
0x18001d2a2  cmp     ecx, 1
0x18001d2a5  jnz     short loc_18001D30A
0x18001d2a7  xor     edx, edx; length
0x18001d2a9  mov     rcx, [rdi+58h]; string
0x18001d2ad  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d2b3  mov     [rsp+68h+var_20], ebx
0x18001d2b7  mov     [rsp+68h+var_28], rax
0x18001d2bc  mov     [rsp+68h+var_30], 0; unsigned __int16 *
0x18001d2c5  mov     [rsp+68h+var_38], 0; char *
0x18001d2ce  lea     rax, aTrackingProduc_1; "Tracking ProductId: %s. Marking Complet"...
0x18001d2d5  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18001d2da  mov     [rsp+68h+var_48], 0FFFFFFFFh; int
0x18001d2e2  lea     r9, aAppinstallitem_0; "AppInstallItemTracker::Invoke"
0x18001d2e9  mov     r8d, 0D3h; unsigned int
0x18001d2ef  lea     rdx, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001d2f6  mov     ecx, 3; unsigned int
0x18001d2fb  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18001d300  mov     rcx, [rdi+60h]; this
0x18001d304  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18001d309  nop
0x18001d30a  lea     rcx, [rsp+68h+arg_18]
0x18001d312  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d317  xor     eax, eax
0x18001d319  jmp     short loc_18001D31F
0x18001d31b  mov     eax, [rsp+68h+arg_8]
0x18001d31f  add     rsp, 50h
0x18001d323  pop     rdi
0x18001d324  pop     rsi
0x18001d325  pop     rbx
0x18001d326  retn
0x18001d327  mov     ecx, ebx
0x18001d329  sub     ecx, 8
0x18001d32c  jz      loc_18001D2A7
0x18001d332  sub     ecx, 1
0x18001d335  jz      loc_18001D2A7
0x18001d33b  sub     ecx, 1
0x18001d33e  jz      loc_18001D2A7
0x18001d344  sub     ecx, 1
0x18001d347  jz      loc_18001D2A7
0x18001d34d  sub     ecx, 1
0x18001d350  jz      loc_18001D2A7
0x18001d356  cmp     ecx, 1
0x18001d359  jnz     short loc_18001D30A
0x18001d35b  xor     edx, edx; length
0x18001d35d  mov     rcx, [rdi+58h]; string
0x18001d361  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d367  mov     [rsp+68h+var_20], ebx
0x18001d36b  mov     [rsp+68h+var_28], rax
0x18001d370  mov     [rsp+68h+var_30], 0; unsigned __int16 *
0x18001d379  mov     [rsp+68h+var_38], 0; char *
0x18001d382  lea     rax, aTrackingProduc_0; "Tracking ProductId: %s. In Progress. St"...
0x18001d389  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18001d38e  mov     [rsp+68h+var_48], 0FFFFFFFFh; int
0x18001d396  lea     r9, aAppinstallitem_0; "AppInstallItemTracker::Invoke"
0x18001d39d  mov     r8d, 0CAh; unsigned int
0x18001d3a3  lea     rdx, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001d3aa  mov     ecx, 3; unsigned int
0x18001d3af  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18001d3b4  jmp     loc_18001D30A
```
