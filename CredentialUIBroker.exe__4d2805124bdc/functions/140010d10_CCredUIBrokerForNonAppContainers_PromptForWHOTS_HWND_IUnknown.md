# CCredUIBrokerForNonAppContainers::PromptForWHOTS(HWND__ *,IUnknown *)

- ea: `0x140010d10`
- end: `0x140010d96`
- name: `?PromptForWHOTS@CCredUIBrokerForNonAppContainers@@UEAAJPEAUHWND__@@PEAUIUnknown@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(CCredUIBrokerForNonAppContainers *__hidden this, HWND, struct IUnknown *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000e920`
- `0x140010d10`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140010d55`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140010d55`

## pseudocode

```c
__int64 __fastcall CCredUIBrokerForNonAppContainers::PromptForWHOTS(
        CCredUIBrokerForNonAppContainers *this,
        HWND a2,
        struct IUnknown *a3)
{
  HRESULT v5; // ebx
  LPVOID ppv; // [rsp+58h] [rbp+20h] BYREF

  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v5 = CoCreateInstance(
         &GUID_96b42929_01f1_468c_b521_6294ab438f4a,
         0,
         1u,
         &GUID_8e84d694_46f1_48d5_846e_e2663dd726a1,
         &ppv);
  if ( v5 >= 0 )
    v5 = (*(__int64 (__fastcall **)(LPVOID, HWND, struct IUnknown *))(*(_QWORD *)ppv + 56LL))(ppv, a2, a3);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140010d10  mov     rax, rsp
0x140010d13  mov     [rax+8], rbx
0x140010d17  mov     [rax+10h], rsi
0x140010d1b  push    rdi
0x140010d1c  sub     rsp, 30h
0x140010d20  lea     rcx, [rax+20h]
0x140010d24  mov     qword ptr [rax+20h], 0
0x140010d2c  mov     rdi, r8
0x140010d2f  mov     rsi, rdx
0x140010d32  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140010d37  xor     edx, edx; pUnkOuter
0x140010d39  lea     rax, [rsp+38h+arg_18]
0x140010d3e  lea     r9, _GUID_8e84d694_46f1_48d5_846e_e2663dd726a1; riid
0x140010d45  mov     [rsp+38h+ppv], rax; ppv
0x140010d4a  lea     rcx, _GUID_96b42929_01f1_468c_b521_6294ab438f4a; rclsid
0x140010d51  lea     r8d, [rdx+1]; dwClsContext
0x140010d55  call    cs:__imp_CoCreateInstance
0x140010d5b  mov     ebx, eax
0x140010d5d  test    eax, eax
0x140010d5f  js      short loc_140010D7A
0x140010d61  mov     rcx, [rsp+38h+arg_18]
0x140010d66  mov     r8, rdi
0x140010d69  mov     rdx, rsi
0x140010d6c  mov     rax, [rcx]
0x140010d6f  mov     rax, [rax+38h]
0x140010d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d78  mov     ebx, eax
0x140010d7a  lea     rcx, [rsp+38h+arg_18]
0x140010d7f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140010d84  mov     rsi, [rsp+38h+arg_8]
0x140010d89  mov     eax, ebx
0x140010d8b  mov     rbx, [rsp+38h+arg_0]
0x140010d90  add     rsp, 30h
0x140010d94  pop     rdi
0x140010d95  retn
```
