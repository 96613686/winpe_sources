# CGuestXvmAudioObject::CreatePlugin(void)

- ea: `0x18009b4c8`
- end: `0x18009b645`
- name: `?CreatePlugin@CGuestXvmAudioObject@@AEAAJXZ`
- size: `381`
- prototype: `__int64 __fastcall(CGuestXvmAudioObject *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180083378`
- `0x1800b0470`

## callees

- `0x180007f00`
- `0x180010a90`
- `0x180087e80`
- `0x18009b4c8`
- `0x18009d564`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b52a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b52a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009b5b9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009b5b9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18009b567`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18009b567`

## string_xrefs

- `0x18009b53f`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18009b57e`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18009b5d0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18009b515`: `GuestAudioClientPluginCLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall CGuestXvmAudioObject::CreatePlugin(CGuestXvmAudioObject *this)
{
  unsigned int ValueW; // eax
  HRESULT v4; // eax
  HRESULT v5; // ebx
  HRESULT v6; // eax
  LPVOID v7; // rcx
  __int64 v8; // rbx
  unsigned int pdwType; // [rsp+20h] [rbp-458h]
  int pdwTypea; // [rsp+20h] [rbp-458h]
  DWORD pcbData; // [rsp+40h] [rbp-438h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-430h] BYREF
  GUID pclsid; // [rsp+50h] [rbp-428h] BYREF
  OLECHAR sz[512]; // [rsp+60h] [rbp-418h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+0h]

  pcbData = 1024;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
             L"GuestAudioClientPluginCLSID",
             2u,
             0,
             sz,
             &pcbData);
  if ( ValueW )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x11E,
             (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
             (const char *)ValueW,
             pdwType);
  pclsid = 0;
  v4 = CLSIDFromString(sz, &pclsid);
  v5 = v4;
  if ( v4 >= 0 )
  {
    ppv = 0;
    v6 = CoCreateInstance(&pclsid, 0, 1u, &GUID_f36b549a_9e77_402e_aa83_97b8d0da8d23, &ppv);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v7 = ppv;
      v8 = *((_QWORD *)this + 5);
      *((_QWORD *)this + 5) = ppv;
      if ( v7 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 8LL))(v7);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      v5 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x123,
        (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
        (const char *)(unsigned int)v6,
        pdwTypea);
    }
    wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&ppv);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x120,
      (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
      (const char *)(unsigned int)v4,
      pdwType);
  }
  return v5;
}

```

## disassembly

```asm
0x18009b4c8  mov     [rsp+arg_8], rbx
0x18009b4cd  push    rdi
0x18009b4ce  sub     rsp, 470h
0x18009b4d5  mov     rax, cs:__security_cookie
0x18009b4dc  xor     rax, rsp
0x18009b4df  mov     [rsp+478h+var_18], rax
0x18009b4e7  mov     rdi, rcx
0x18009b4ea  mov     [rsp+478h+var_438], 400h
0x18009b4f2  lea     rax, [rsp+478h+var_438]
0x18009b4f7  mov     [rsp+478h+pcbData], rax; pcbData
0x18009b4fc  lea     rax, [rsp+478h+sz]
0x18009b501  mov     [rsp+478h+pvData], rax; pvData
0x18009b506  mov     [rsp+478h+pdwType], 0; int
0x18009b50f  mov     r9d, 2; dwFlags
0x18009b515  lea     r8, aGuestaudioclie; "GuestAudioClientPluginCLSID"
0x18009b51c  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009b523  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18009b52a  call    cs:__imp_RegGetValueW
0x18009b530  test    eax, eax
0x18009b532  jz      short loc_18009B555
0x18009b534  mov     rcx, [rsp+478h]; this
0x18009b53c  mov     r9d, eax; char *
0x18009b53f  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18009b546  mov     edx, 11Eh; void *
0x18009b54b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009b550  jmp     loc_18009B624
0x18009b555  xorps   xmm0, xmm0
0x18009b558  movups  xmmword ptr [rsp+478h+pclsid.Data1], xmm0
0x18009b55d  lea     rdx, [rsp+478h+pclsid]; pclsid
0x18009b562  lea     rcx, [rsp+478h+sz]; lpsz
0x18009b567  call    cs:__imp_CLSIDFromString
0x18009b56d  mov     ebx, eax
0x18009b56f  test    eax, eax
0x18009b571  jns     short loc_18009B594
0x18009b573  mov     rcx, [rsp+478h]; this
0x18009b57b  mov     r9d, eax; char *
0x18009b57e  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18009b585  mov     edx, 120h; void *
0x18009b58a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b58f  jmp     loc_18009B622
0x18009b594  mov     [rsp+478h+ppv], 0
0x18009b59d  lea     rax, [rsp+478h+ppv]
0x18009b5a2  mov     [rsp+478h+pdwType], rax; int
0x18009b5a7  lea     r9, _GUID_f36b549a_9e77_402e_aa83_97b8d0da8d23; riid
0x18009b5ae  xor     edx, edx; pUnkOuter
0x18009b5b0  lea     r8d, [rdx+1]; dwClsContext
0x18009b5b4  lea     rcx, [rsp+478h+pclsid]; rclsid
0x18009b5b9  call    cs:__imp_CoCreateInstance
0x18009b5bf  mov     ebx, eax
0x18009b5c1  test    eax, eax
0x18009b5c3  jns     short loc_18009B5E3
0x18009b5c5  mov     rcx, [rsp+478h]; this
0x18009b5cd  mov     r9d, eax; char *
0x18009b5d0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18009b5d7  mov     edx, 123h; void *
0x18009b5dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b5e1  jmp     short loc_18009B618
0x18009b5e3  mov     rcx, [rsp+478h+ppv]
0x18009b5e8  mov     rbx, [rdi+28h]
0x18009b5ec  mov     [rdi+28h], rcx
0x18009b5f0  test    rcx, rcx
0x18009b5f3  jz      short loc_18009B601
0x18009b5f5  mov     rax, [rcx]
0x18009b5f8  mov     rax, [rax+8]
0x18009b5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b601  test    rbx, rbx
0x18009b604  jz      short loc_18009B616
0x18009b606  mov     rax, [rbx]
0x18009b609  mov     rcx, rbx
0x18009b60c  mov     rax, [rax+10h]
0x18009b610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b615  nop
0x18009b616  xor     ebx, ebx
0x18009b618  lea     rcx, [rsp+478h+ppv]; void *
0x18009b61d  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18009b622  mov     eax, ebx
0x18009b624  mov     rcx, [rsp+478h+var_18]
0x18009b62c  xor     rcx, rsp; StackCookie
0x18009b62f  call    __security_check_cookie
0x18009b634  mov     rbx, [rsp+478h+arg_8]
0x18009b63c  add     rsp, 470h
0x18009b643  pop     rdi
0x18009b644  retn
```
