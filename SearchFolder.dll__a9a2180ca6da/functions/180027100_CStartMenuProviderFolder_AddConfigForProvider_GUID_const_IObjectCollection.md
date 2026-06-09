# CStartMenuProviderFolder::_AddConfigForProvider(_GUID const &,IObjectCollection *)

- ea: `0x180027100`
- end: `0x1800271ed`
- name: `?_AddConfigForProvider@CStartMenuProviderFolder@@AEAAJAEBU_GUID@@PEAUIObjectCollection@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(CStartMenuProviderFolder *__hidden this, const struct _GUID *, struct IObjectCollection *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026fc0`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x180027100`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002713e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002713e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180027165`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180027165`

## pseudocode

```c
__int64 __fastcall CStartMenuProviderFolder::_AddConfigForProvider(
        CStartMenuProviderFolder *this,
        const struct _GUID *a2,
        struct IObjectCollection *a3)
{
  HRESULT v5; // ebx
  LPVOID v7; // [rsp+50h] [rbp+8h] BYREF
  void *ppv; // [rsp+68h] [rbp+20h] BYREF

  v7 = 0;
  v5 = CoCreateInstance(
         &GUID_3722c3b1_82e8_4022_8b27_1f8a68b44ac7,
         0,
         1u,
         &GUID_628880f3_0dc6_4359_a29b_15ef9aecbd23,
         &v7);
  if ( v5 >= 0 )
  {
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
    v5 = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, &ppv);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, const wchar_t *, void *, _QWORD, _QWORD))(*(_QWORD *)v7 + 24LL))(
             v7,
             a2,
             L"Merge Any",
             ppv,
             0,
             0);
      if ( v5 >= 0 )
        v5 = ((__int64 (__fastcall *)(struct IObjectCollection *, LPVOID))a3->lpVtbl->AddObject)(a3, v7);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&ppv);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180027100  mov     r11, rsp
0x180027103  mov     [r11+10h], rbx
0x180027107  mov     [r11+18h], rsi
0x18002710b  mov     [r11+8], rcx
0x18002710f  push    rdi
0x180027110  sub     rsp, 40h
0x180027114  mov     rdi, r8
0x180027117  mov     rsi, rdx
0x18002711a  mov     qword ptr [r11+8], 0
0x180027122  lea     rax, [r11+8]
0x180027126  mov     [r11-28h], rax
0x18002712a  lea     r9, _GUID_628880f3_0dc6_4359_a29b_15ef9aecbd23; riid
0x180027131  xor     edx, edx; pUnkOuter
0x180027133  lea     r8d, [rdx+1]; dwClsContext
0x180027137  lea     rcx, _GUID_3722c3b1_82e8_4022_8b27_1f8a68b44ac7; rclsid
0x18002713e  call    cs:__imp_CoCreateInstance
0x180027144  mov     ebx, eax
0x180027146  test    eax, eax
0x180027148  js      loc_1800271DB
0x18002714e  lea     rcx, [rsp+48h+ppv]; void *
0x180027153  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180027158  nop
0x180027159  lea     rdx, [rsp+48h+ppv]; ppv
0x18002715e  lea     rcx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; riid
0x180027165  call    cs:__imp_PSCreateMemoryPropertyStore
0x18002716b  mov     ebx, eax
0x18002716d  test    eax, eax
0x18002716f  js      short loc_1800271BF
0x180027171  mov     rcx, [rsp+48h+arg_0]
0x180027176  mov     rax, [rcx]
0x180027179  mov     [rsp+48h+var_20], 0
0x180027182  mov     [rsp+48h+var_28], 0
0x18002718b  mov     r9, [rsp+48h+ppv]
0x180027190  lea     r8, aMergeAny; "Merge Any"
0x180027197  mov     rdx, rsi
0x18002719a  mov     rax, [rax+18h]
0x18002719e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271a3  mov     ebx, eax
0x1800271a5  test    eax, eax
0x1800271a7  js      short loc_1800271BF
0x1800271a9  mov     rax, [rdi]
0x1800271ac  mov     rdx, [rsp+48h+arg_0]
0x1800271b1  mov     rcx, rdi
0x1800271b4  mov     rax, [rax+28h]
0x1800271b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271bd  mov     ebx, eax
0x1800271bf  mov     rcx, [rsp+48h+arg_0]
0x1800271c4  mov     rax, [rcx]
0x1800271c7  mov     rax, [rax+10h]
0x1800271cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271d0  nop
0x1800271d1  lea     rcx, [rsp+48h+ppv]
0x1800271d6  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800271db  mov     eax, ebx
0x1800271dd  mov     rbx, [rsp+48h+arg_8]
0x1800271e2  mov     rsi, [rsp+48h+arg_10]
0x1800271e7  add     rsp, 40h
0x1800271eb  pop     rdi
0x1800271ec  retn
```
