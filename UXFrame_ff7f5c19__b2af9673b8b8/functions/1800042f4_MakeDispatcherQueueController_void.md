# MakeDispatcherQueueController(void)

- ea: `0x1800042f4`
- end: `0x180004363`
- name: `?MakeDispatcherQueueController@@YA?AUDispatcherQueueController@System@Windows@winrt@@XZ`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004488c`

## callees

- `0x1800043a0`
- `0x1800046c8`

## import_xrefs

- `CoreMessaging!CreateDispatcherQueueController` at `0x180004342`
- `CoreMessaging!CreateDispatcherQueueController` at `0x180004342`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
winrt *__fastcall MakeDispatcherQueueController(winrt *a1, struct IUnknown *a2)
{
  void **v3; // rax
  unsigned int v4; // eax
  DispatcherQueueOptions options; // [rsp+30h] [rbp-38h] BYREF
  int v7; // [rsp+40h] [rbp-28h] BYREF
  __int128 v8; // [rsp+48h] [rbp-20h]
  char v9; // [rsp+78h] [rbp+10h] BYREF

  *(_QWORD *)a1 = 0;
  v7 = 0;
  v8 = 0;
  options.dwSize = 12;
  options.threadType = DQTYPE_THREAD_CURRENT;
  options.apartmentType = DQTAT_COM_ASTA;
  v3 = winrt::put_abi(a1, a2);
  v4 = CreateDispatcherQueueController(&options, v3);
  winrt::check_hresult(&v9, v4, &v7);
  return a1;
}

```

## disassembly

```asm
0x1800042f4  mov     [rsp+arg_0], rcx
0x1800042f9  push    rbx
0x1800042fa  sub     rsp, 60h
0x1800042fe  mov     rbx, rcx
0x180004301  xor     eax, eax
0x180004303  mov     [rsp+68h+var_48], eax
0x180004307  mov     [rcx], rax
0x18000430a  lea     ecx, [rax+1]
0x18000430d  mov     [rsp+68h+var_48], ecx
0x180004311  mov     [rsp+68h+var_28], eax
0x180004315  xorps   xmm0, xmm0
0x180004318  movdqu  [rsp+68h+var_20], xmm0
0x18000431e  mov     [rsp+68h+options.dwSize], 0Ch
0x180004326  mov     [rsp+68h+options.threadType], 2
0x18000432e  mov     [rsp+68h+options.apartmentType], ecx
0x180004332  mov     rcx, rbx; this
0x180004335  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18000433a  mov     rdx, rax; dispatcherQueueController
0x18000433d  lea     rcx, [rsp+68h+options]; options
0x180004342  call    cs:__imp_CreateDispatcherQueueController
0x180004348  lea     r8, [rsp+68h+var_28]
0x18000434d  mov     edx, eax
0x18000434f  lea     rcx, [rsp+68h+arg_8]
0x180004354  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180004359  mov     rax, rbx
0x18000435c  add     rsp, 60h
0x180004360  pop     rbx
0x180004361  retn
```
