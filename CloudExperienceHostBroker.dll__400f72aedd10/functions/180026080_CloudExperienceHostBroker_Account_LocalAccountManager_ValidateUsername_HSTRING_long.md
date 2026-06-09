# CloudExperienceHostBroker::Account::LocalAccountManager::ValidateUsername(HSTRING__ *,long *)

- ea: `0x180026080`
- end: `0x180026129`
- name: `?ValidateUsername@LocalAccountManager@Account@CloudExperienceHostBroker@@UEAAJPEAUHSTRING__@@PEAJ@Z`
- size: `169`
- prototype: `int(CloudExperienceHostBroker::Account::LocalAccountManager *__hidden this, HSTRING, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006140`
- `0x180008344`
- `0x180026080`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800260da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800260da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800260b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800260b6`

## string_xrefs

- `0x1800260fc`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostBroker::Account::LocalAccountManager::ValidateUsername(
        CloudExperienceHostBroker::Account::LocalAccountManager *this,
        HSTRING a2,
        int *a3)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, PCWSTR, int *); // rbx
  PCWSTR StringRawBuffer; // rax
  int ppv; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID v14; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  v5 = CoCreateInstance(
         &GUID_54337179_c8b2_4ed4_95e4_95601c850d8c,
         0,
         1u,
         &GUID_30e038f9_64c9_4a5c_ba4c_f9f7df30849c,
         &v14);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = v14;
    v9 = *(__int64 (__fastcall **)(LPVOID, PCWSTR, int *))(*(_QWORD *)v14 + 56LL);
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    v5 = v9(v8, StringRawBuffer, a3);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v6 = 0;
      goto LABEL_7;
    }
    v7 = 404;
  }
  else
  {
    v7 = 403;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
    (const char *)(unsigned int)v5,
    ppv);
LABEL_7:
  wil::com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>::~com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>(&v14);
  return v6;
}

```

## disassembly

```asm
0x180026080  push    rbx
0x180026082  push    rbp
0x180026083  push    rsi
0x180026084  push    rdi
0x180026085  sub     rsp, 38h
0x180026089  mov     rsi, r8
0x18002608c  mov     rbp, rdx
0x18002608f  mov     [rsp+58h+arg_18], 0
0x180026098  lea     rax, [rsp+58h+arg_18]
0x18002609d  mov     qword ptr [rsp+58h+ppv], rax; int
0x1800260a2  lea     r9, _GUID_30e038f9_64c9_4a5c_ba4c_f9f7df30849c; riid
0x1800260a9  xor     edx, edx; pUnkOuter
0x1800260ab  lea     r8d, [rdx+1]; dwClsContext
0x1800260af  lea     rcx, _GUID_54337179_c8b2_4ed4_95e4_95601c850d8c; rclsid
0x1800260b6  call    cs:__imp_CoCreateInstance
0x1800260bc  mov     ebx, eax
0x1800260be  test    eax, eax
0x1800260c0  jns     short loc_1800260C9
0x1800260c2  mov     edx, 193h
0x1800260c7  jmp     short loc_1800260FC
0x1800260c9  mov     rdi, [rsp+58h+arg_18]
0x1800260ce  mov     rax, [rdi]
0x1800260d1  mov     rbx, [rax+38h]
0x1800260d5  xor     edx, edx; length
0x1800260d7  mov     rcx, rbp; string
0x1800260da  call    cs:__imp_WindowsGetStringRawBuffer
0x1800260e0  mov     r8, rsi
0x1800260e3  mov     rdx, rax
0x1800260e6  mov     rcx, rdi
0x1800260e9  mov     rax, rbx
0x1800260ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260f1  mov     ebx, eax
0x1800260f3  test    eax, eax
0x1800260f5  jns     short loc_180026112
0x1800260f7  mov     edx, 194h; void *
0x1800260fc  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180026103  mov     r9d, eax; char *
0x180026106  mov     rcx, [rsp+58h]; this
0x18002610b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026110  jmp     short loc_180026114
0x180026112  xor     ebx, ebx
0x180026114  lea     rcx, [rsp+58h+arg_18]
0x180026119  call    ??1?$com_ptr_t@UIOOBEOneDriveOptin@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>::~com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>(void)
0x18002611e  mov     eax, ebx
0x180026120  add     rsp, 38h
0x180026124  pop     rdi
0x180026125  pop     rsi
0x180026126  pop     rbp
0x180026127  pop     rbx
0x180026128  retn
```
