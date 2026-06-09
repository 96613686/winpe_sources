# CallerIdentity::GetCoreWindowHandleForCurrentThread(HWND__ * *)

- ea: `0x18001b168`
- end: `0x18001b268`
- name: `?GetCoreWindowHandleForCurrentThread@CallerIdentity@@YAJPEAPEAUHWND__@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, HWND *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180015490`

## callees

- `0x180014850`
- `0x18001b060`
- `0x18001b168`
- `0x18001b270`
- `0x18001c010`

## import_xrefs

- `combase!__imp_RoGetDesignMode` at `0x18001b18f`
- `combase!__imp_RoGetDesignMode` at `0x18001b18f`
- `combase!__imp_RoGetDesignModeV2` at `0x18001b1a6`
- `combase!__imp_RoGetDesignModeV2` at `0x18001b1a6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b1ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b1ec`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCoreWindowHandleForCurrentThread(CallerIdentity *this, HWND *a2)
{
  DWORD v3; // eax
  HRESULT CoreWindowForCurrentThread; // ebx
  CallerIdentity *v5; // rcx
  void **v6; // r8
  struct _GUID ppv; // [rsp+40h] [rbp+10h] BYREF

  *(_QWORD *)this = 0;
  ppv.Data1 = 0;
  RoGetDesignMode(&ppv, a2);
  if ( !ppv.Data1 || (*(_DWORD *)ppv.Data4 = 0, RoGetDesignModeV2(ppv.Data4), *(_DWORD *)ppv.Data4) )
  {
    *(_QWORD *)&ppv.Data1 = 0;
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&ppv);
    CoreWindowForCurrentThread = CallerIdentity::GetCoreWindowForCurrentThread(v5, &ppv, v6);
    if ( CoreWindowForCurrentThread >= 0 )
      CoreWindowForCurrentThread = (*(__int64 (__fastcall **)(_QWORD, CallerIdentity *))(**(_QWORD **)&ppv.Data1 + 24LL))(
                                     *(_QWORD *)&ppv.Data1,
                                     this);
  }
  else
  {
    *(_QWORD *)&ppv.Data1 = 0;
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&ppv);
    v3 = operator|(1);
    CoreWindowForCurrentThread = CoCreateInstance(
                                   &GUID_958a6fb5_dcb2_4faf_aafd_7fb054ad1a3b,
                                   0,
                                   v3,
                                   &GUID_a656e803_4059_4a4c_a5b8_0d0de2c809fb,
                                   (LPVOID *)&ppv);
    if ( CoreWindowForCurrentThread >= 0 )
      CoreWindowForCurrentThread = (*(__int64 (__fastcall **)(_QWORD, CallerIdentity *))(**(_QWORD **)&ppv.Data1 + 24LL))(
                                     *(_QWORD *)&ppv.Data1,
                                     this);
  }
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&ppv);
  return (unsigned int)CoreWindowForCurrentThread;
}

```

## disassembly

```asm
0x18001b168  mov     [rsp-8+arg_10], rbx
0x18001b16d  mov     [rsp-8+arg_18], rdi
0x18001b172  push    rbp
0x18001b173  mov     rbp, rsp
0x18001b176  sub     rsp, 30h
0x18001b17a  mov     rdi, rcx
0x18001b17d  mov     qword ptr [rcx], 0
0x18001b184  lea     rcx, [rbp+arg_0]
0x18001b188  mov     [rbp+arg_0.Data1], 0
0x18001b18f  call    cs:__imp_RoGetDesignMode
0x18001b195  cmp     [rbp+arg_0.Data1], 0
0x18001b199  jz      short loc_18001B218
0x18001b19b  lea     rcx, [rbp+arg_0.Data4]
0x18001b19f  mov     dword ptr [rbp+arg_0.Data4], 0
0x18001b1a6  call    cs:__imp_RoGetDesignModeV2
0x18001b1ac  cmp     dword ptr [rbp+arg_0.Data4], 0
0x18001b1b0  jnz     short loc_18001B218
0x18001b1b2  lea     rcx, [rbp+arg_0]
0x18001b1b6  mov     qword ptr [rbp+arg_0.Data1], 0
0x18001b1be  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18001b1c3  mov     edx, 2
0x18001b1c8  lea     ecx, [rdx-1]
0x18001b1cb  call    ??U@YA?AW4tagCLSCTX@@W40@0@Z; operator|(tagCLSCTX,tagCLSCTX)
0x18001b1d0  lea     rcx, [rbp+arg_0]
0x18001b1d4  mov     r8d, eax; dwClsContext
0x18001b1d7  mov     [rsp+30h+ppv], rcx; ppv
0x18001b1dc  lea     r9, _GUID_a656e803_4059_4a4c_a5b8_0d0de2c809fb; riid
0x18001b1e3  lea     rcx, _GUID_958a6fb5_dcb2_4faf_aafd_7fb054ad1a3b; rclsid
0x18001b1ea  xor     edx, edx; pUnkOuter
0x18001b1ec  call    cs:__imp_CoCreateInstance
0x18001b1f2  mov     ebx, eax
0x18001b1f4  test    eax, eax
0x18001b1f6  js      short loc_18001B20D
0x18001b1f8  mov     rcx, qword ptr [rbp+arg_0.Data1]
0x18001b1fc  mov     rdx, rdi
0x18001b1ff  mov     rax, [rcx]
0x18001b202  mov     rax, [rax+18h]
0x18001b206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b20b  mov     ebx, eax
0x18001b20d  lea     rcx, [rbp+arg_0]
0x18001b211  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18001b216  jmp     short loc_18001B256
0x18001b218  lea     rcx, [rbp+arg_0]
0x18001b21c  mov     qword ptr [rbp+arg_0.Data1], 0
0x18001b224  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18001b229  lea     rdx, [rbp+arg_0]; struct _GUID *
0x18001b22d  call    ?GetCoreWindowForCurrentThread@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z; CallerIdentity::GetCoreWindowForCurrentThread(_GUID const &,void * *)
0x18001b232  mov     ebx, eax
0x18001b234  test    eax, eax
0x18001b236  js      short loc_18001B24D
0x18001b238  mov     rcx, qword ptr [rbp+arg_0.Data1]
0x18001b23c  mov     rdx, rdi
0x18001b23f  mov     rax, [rcx]
0x18001b242  mov     rax, [rax+18h]
0x18001b246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b24b  mov     ebx, eax
0x18001b24d  lea     rcx, [rbp+arg_0]
0x18001b251  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18001b256  mov     rdi, [rsp+30h+arg_18]
0x18001b25b  mov     eax, ebx
0x18001b25d  mov     rbx, [rsp+30h+arg_10]
0x18001b262  add     rsp, 30h
0x18001b266  pop     rbp
0x18001b267  retn
```
