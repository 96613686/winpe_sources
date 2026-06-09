# SpGetCategoryFromId(ushort const *,ISpObjectTokenCategory * *,int)

- ea: `0x180029f44`
- end: `0x180029fd0`
- name: `?SpGetCategoryFromId@@YAJPEBGPEAPEAUISpObjectTokenCategory@@H@Z`
- size: `140`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct ISpObjectTokenCategory **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800299c8`

## callees

- `0x18002990c`
- `0x180029f44`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029f7b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029f7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SpGetCategoryFromId(const unsigned __int16 *a1, struct ISpObjectTokenCategory **a2)
{
  HRESULT Instance; // ebx
  struct ISpObjectTokenCategory *v4; // rax
  struct ISpObjectTokenCategory *v6; // [rsp+40h] [rbp+8h] BYREF

  v6 = 0;
  Instance = CoCreateInstance(
               &CLSID_SpObjectTokenCategory,
               0,
               0x17u,
               &GUID_2d3d3845_39af_4850_bbf9_40b49780011d,
               (LPVOID *)&v6);
  if ( Instance >= 0 )
  {
    Instance = ((__int64 (__fastcall *)(struct ISpObjectTokenCategory *, const wchar_t *, _QWORD))v6->lpVtbl->SetId)(
                 v6,
                 L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech\\Voices",
                 0);
    if ( Instance >= 0 )
    {
      v4 = v6;
      v6 = 0;
      *a2 = v4;
    }
  }
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v6);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180029f44  mov     r11, rsp
0x180029f47  mov     [r11+10h], rbx
0x180029f4b  mov     [r11+8], rcx
0x180029f4f  push    rdi
0x180029f50  sub     rsp, 30h
0x180029f54  mov     rdi, rdx
0x180029f57  mov     qword ptr [r11+8], 0
0x180029f5f  lea     rax, [r11+8]
0x180029f63  mov     [r11-18h], rax
0x180029f67  lea     r9, _GUID_2d3d3845_39af_4850_bbf9_40b49780011d; riid
0x180029f6e  xor     edx, edx; pUnkOuter
0x180029f70  lea     r8d, [rdx+17h]; dwClsContext
0x180029f74  lea     rcx, CLSID_SpObjectTokenCategory; rclsid
0x180029f7b  call    cs:__imp_CoCreateInstance
0x180029f81  mov     ebx, eax
0x180029f83  test    eax, eax
0x180029f85  js      short loc_180029FB9
0x180029f87  mov     rcx, [rsp+38h+arg_0]
0x180029f8c  mov     rax, [rcx]
0x180029f8f  xor     r8d, r8d
0x180029f92  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x180029f99  mov     rax, [rax+78h]
0x180029f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fa2  mov     ebx, eax
0x180029fa4  test    eax, eax
0x180029fa6  js      short loc_180029FB9
0x180029fa8  mov     rax, [rsp+38h+arg_0]
0x180029fad  mov     [rsp+38h+arg_0], 0
0x180029fb6  mov     [rdi], rax
0x180029fb9  lea     rcx, [rsp+38h+arg_0]
0x180029fbe  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180029fc3  mov     eax, ebx
0x180029fc5  mov     rbx, [rsp+38h+arg_8]
0x180029fca  add     rsp, 30h
0x180029fce  pop     rdi
0x180029fcf  retn
```
