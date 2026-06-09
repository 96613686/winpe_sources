# UiaWindowNotifier::RegisterWindow(HWND__ *)

- ea: `0x180074b20`
- end: `0x180074bf9`
- name: `?RegisterWindow@UiaWindowNotifier@@UEAAJPEAUHWND__@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(UiaWindowNotifier *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800054f8`
- `0x180006edc`
- `0x180074b20`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180074b68`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180074b68`

## string_xrefs

- `0x180074bc3`: `onecore\windows\accessibletech\uiamanager\dll\uiawindownotifier.cpp`

## pseudocode

```c
__int64 __fastcall UiaWindowNotifier::RegisterWindow(UiaWindowNotifier *this, HWND a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  LPVOID v7; // rsi
  __int64 (__fastcall *v8)(LPVOID, _QWORD, unsigned __int64, char *); // rdi
  int ppv; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID v12; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  v4 = CoCreateInstance(&CLSID_UiaManager, 0, 4u, &GUID_83140d1c_7e82_4cfb_96e4_f997cede7e10, &v12);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v7 = v12;
    v8 = *(__int64 (__fastcall **)(LPVOID, _QWORD, unsigned __int64, char *))(*(_QWORD *)v12 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 32);
    v4 = v8(
           v7,
           (unsigned int)a2,
           ((unsigned __int64)this + 8) & -(__int64)(this != (UiaWindowNotifier *)48),
           (char *)this + 32);
    v5 = v4;
    if ( v4 >= 0 )
    {
      *((_QWORD *)this + 6) = a2;
      v5 = 0;
      goto LABEL_7;
    }
    v6 = 42;
  }
  else
  {
    v6 = 36;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiawindownotifier.cpp",
    (const char *)(unsigned int)v4,
    ppv);
LABEL_7:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  return v5;
}

```

## disassembly

```asm
0x180074b20  mov     rax, rsp
0x180074b23  mov     [rax+8], rbx
0x180074b27  mov     [rax+10h], rbp
0x180074b2b  push    rsi
0x180074b2c  push    rdi
0x180074b2d  push    r14
0x180074b2f  sub     rsp, 30h
0x180074b33  mov     rbp, rcx
0x180074b36  mov     qword ptr [rax+18h], 0
0x180074b3e  lea     rcx, [rax+18h]
0x180074b42  mov     r14, rdx
0x180074b45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180074b4a  xor     edx, edx; pUnkOuter
0x180074b4c  lea     rax, [rsp+48h+arg_10]
0x180074b51  lea     r9, _GUID_83140d1c_7e82_4cfb_96e4_f997cede7e10; riid
0x180074b58  mov     qword ptr [rsp+48h+ppv], rax; int
0x180074b5d  lea     rcx, CLSID_UiaManager; rclsid
0x180074b64  lea     r8d, [rdx+4]; dwClsContext
0x180074b68  call    cs:__imp_CoCreateInstance
0x180074b6e  mov     ebx, eax
0x180074b70  test    eax, eax
0x180074b72  jns     short loc_180074B7B
0x180074b74  mov     edx, 24h ; '$'
0x180074b79  jmp     short loc_180074BBE
0x180074b7b  mov     rsi, [rsp+48h+arg_10]
0x180074b80  lea     rcx, [rbp+20h]
0x180074b84  mov     rax, [rsi]
0x180074b87  mov     rdi, [rax+18h]
0x180074b8b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180074b90  lea     r10, [rbp+8]
0x180074b94  mov     rcx, rsi
0x180074b97  lea     rdx, [rbp-30h]
0x180074b9b  mov     rax, rdi
0x180074b9e  neg     rdx
0x180074ba1  lea     r9, [rbp+20h]
0x180074ba5  mov     edx, r14d
0x180074ba8  sbb     r8, r8
0x180074bab  and     r8, r10
0x180074bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074bb3  mov     ebx, eax
0x180074bb5  test    eax, eax
0x180074bb7  jns     short loc_180074BD4
0x180074bb9  mov     edx, 2Ah ; '*'; void *
0x180074bbe  mov     rcx, [rsp+48h]; this
0x180074bc3  lea     r8, aOnecoreWindows_25; "onecore\\windows\\accessibletech\\uiama"...
0x180074bca  mov     r9d, eax; char *
0x180074bcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074bd2  jmp     short loc_180074BDA
0x180074bd4  mov     [rbp+30h], r14
0x180074bd8  xor     ebx, ebx
0x180074bda  lea     rcx, [rsp+48h+arg_10]
0x180074bdf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180074be4  mov     rbp, [rsp+48h+arg_8]
0x180074be9  mov     eax, ebx
0x180074beb  mov     rbx, [rsp+48h+arg_0]
0x180074bf0  add     rsp, 30h
0x180074bf4  pop     r14
0x180074bf6  pop     rdi
0x180074bf7  pop     rsi
0x180074bf8  retn
```
