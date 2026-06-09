# DmRemoveToastNotification(ushort const *,ushort const *)

- ea: `0x1800716b0`
- end: `0x1800717de`
- name: `?DmRemoveToastNotification@@YAJPEBG0@Z`
- size: `302`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180064a44`
- `0x1800716b0`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800716dd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800716dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007172c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007172c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800717aa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800717aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DmRemoveToastNotification(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HRESULT v4; // esi
  HRESULT v5; // ebx
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, __int64 *); // rbx
  __int64 v9; // [rsp+80h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+48h] BYREF

  ppv = 0;
  v9 = 0;
  v4 = CoInitializeEx(0, 0);
  if ( (int)(v4 + 0x80000000) < 0 || v4 == -2147417850 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v5 = CoCreateInstance(
           &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
           0,
           0x17u,
           &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
           &ppv);
    if ( v5 >= 0 )
    {
      v6 = ppv;
      v7 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
      v5 = v7(v6, &v9);
      if ( v5 >= 0 )
        v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, _QWORD, const unsigned __int16 *, _QWORD))(*(_QWORD *)v9 + 80LL))(
               v9,
               L"System",
               a1,
               0,
               a2,
               0);
    }
  }
  else
  {
    v5 = v4;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  if ( v4 >= 0 )
    CoUninitialize();
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800716b0  mov     [rsp-28h+arg_0], rbx
0x1800716b5  push    rbp
0x1800716b6  push    rsi
0x1800716b7  push    rdi
0x1800716b8  push    r14
0x1800716ba  push    r15
0x1800716bc  mov     rbp, rsp
0x1800716bf  sub     rsp, 40h
0x1800716c3  mov     r14, rdx
0x1800716c6  mov     r15, rcx
0x1800716c9  mov     [rbp+arg_18], 0
0x1800716d1  mov     [rbp+arg_10], 0
0x1800716d9  xor     edx, edx; dwCoInit
0x1800716db  xor     ecx, ecx; pvReserved
0x1800716dd  call    cs:__imp_CoInitializeEx
0x1800716e4  nop     dword ptr [rax+rax+00h]
0x1800716e9  mov     esi, eax
0x1800716eb  mov     eax, 80000000h
0x1800716f0  lea     ecx, [rsi+rax]
0x1800716f3  test    eax, ecx
0x1800716f5  jnz     short loc_180071706
0x1800716f7  cmp     esi, 80010106h
0x1800716fd  jz      short loc_180071706
0x1800716ff  mov     ebx, esi
0x180071701  jmp     loc_180071794
0x180071706  lea     rcx, [rbp+arg_18]
0x18007170a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007170f  lea     rax, [rbp+arg_18]
0x180071713  mov     [rsp+40h+ppv], rax; ppv
0x180071718  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x18007171f  xor     edx, edx; pUnkOuter
0x180071721  lea     r8d, [rdx+17h]; dwClsContext
0x180071725  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x18007172c  call    cs:__imp_CoCreateInstance
0x180071733  nop     dword ptr [rax+rax+00h]
0x180071738  mov     ebx, eax
0x18007173a  test    eax, eax
0x18007173c  js      short loc_180071794
0x18007173e  mov     rdi, [rbp+arg_18]
0x180071742  mov     rax, [rdi]
0x180071745  mov     rbx, [rax+18h]
0x180071749  lea     rcx, [rbp+arg_10]
0x18007174d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071752  lea     rdx, [rbp+arg_10]
0x180071756  mov     rcx, rdi
0x180071759  mov     rax, rbx
0x18007175c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071761  mov     ebx, eax
0x180071763  test    eax, eax
0x180071765  js      short loc_180071794
0x180071767  mov     rcx, [rbp+arg_10]
0x18007176b  mov     rax, [rcx]
0x18007176e  mov     [rsp+40h+var_18], 0
0x180071777  mov     [rsp+40h+ppv], r14
0x18007177c  xor     r9d, r9d
0x18007177f  mov     r8, r15
0x180071782  lea     rdx, aSystem; "System"
0x180071789  mov     rax, [rax+50h]
0x18007178d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071792  mov     ebx, eax
0x180071794  lea     rcx, [rbp+arg_10]
0x180071798  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007179d  lea     rcx, [rbp+arg_18]
0x1800717a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800717a6  test    esi, esi
0x1800717a8  js      short loc_1800717B7
0x1800717aa  call    cs:__imp_CoUninitialize
0x1800717b1  nop     dword ptr [rax+rax+00h]
0x1800717b6  nop
0x1800717b7  lea     rcx, [rbp+arg_10]
0x1800717bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800717c0  nop
0x1800717c1  lea     rcx, [rbp+arg_18]
0x1800717c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800717ca  mov     eax, ebx
0x1800717cc  mov     rbx, [rsp+40h+arg_0]
0x1800717d1  add     rsp, 40h
0x1800717d5  pop     r15
0x1800717d7  pop     r14
0x1800717d9  pop     rdi
0x1800717da  pop     rsi
0x1800717db  pop     rbp
0x1800717dc  retn
```
