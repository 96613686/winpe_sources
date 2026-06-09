# IsHardwareVoiceActivationSupported(IMMDeviceCollection *,uint)

- ea: `0x14000c37c`
- end: `0x14000c467`
- name: `?IsHardwareVoiceActivationSupported@@YAJPEAUIMMDeviceCollection@@I@Z`
- size: `235`
- prototype: `__int64 __fastcall(struct IMMDeviceCollection *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000c470`

## callees

- `0x14000c32c`
- `0x14000c37c`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c42f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c42f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c441`
- `MMDevAPI!__imp_mmdDevGetInterfaceIdFromMMDevice` at `0x14000c3f2`
- `MMDevAPI!__imp_mmdDevGetInterfaceIdFromMMDevice` at `0x14000c3f2`
- `MMDevAPI!__imp_mmdDevGetRelatedInterfaceId` at `0x14000c418`
- `MMDevAPI!__imp_mmdDevGetRelatedInterfaceId` at `0x14000c418`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IsHardwareVoiceActivationSupported(struct IMMDeviceCollection *a1, unsigned int a2)
{
  HRESULT (__stdcall *Item)(IMMDeviceCollection *, UINT, IMMDevice **); // rbx
  int v6; // ebx
  int InterfaceIdFromMMDevice; // eax
  __int128 v8; // [rsp+20h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+50h] [rbp+20h] BYREF
  LPVOID v10; // [rsp+60h] [rbp+30h] BYREF
  __int64 v11; // [rsp+68h] [rbp+38h] BYREF

  if ( !a1 )
    return 2147500035LL;
  v11 = 0;
  v10 = 0;
  pv = 0;
  Item = a1->lpVtbl->Item;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
  v6 = ((__int64 (__fastcall *)(struct IMMDeviceCollection *, _QWORD, __int64 *))Item)(a1, a2, &v11);
  if ( v6 >= 0 )
  {
    if ( v11 )
    {
      InterfaceIdFromMMDevice = mmdDevGetInterfaceIdFromMMDevice(v11, &pv);
      if ( InterfaceIdFromMMDevice < 0
        || (v8 = DEVINTERFACE_AUDIO_KEYWORDDETECTOR,
            InterfaceIdFromMMDevice = mmdDevGetRelatedInterfaceId(pv, &v8, &v10),
            InterfaceIdFromMMDevice < 0) )
      {
        v6 = InterfaceIdFromMMDevice;
        goto LABEL_11;
      }
      if ( v10 )
      {
        v6 = 0;
        goto LABEL_11;
      }
    }
    v6 = -2147023728;
  }
LABEL_11:
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v10);
  v10 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000c37c  mov     [rsp-18h+arg_8], rbx
0x14000c381  push    rbp
0x14000c382  push    rsi
0x14000c383  push    rdi
0x14000c384  mov     rbp, rsp
0x14000c387  sub     rsp, 30h
0x14000c38b  mov     esi, edx
0x14000c38d  mov     rdi, rcx
0x14000c390  test    rcx, rcx
0x14000c393  jnz     short loc_14000C39F
0x14000c395  mov     eax, 80004003h
0x14000c39a  jmp     loc_14000C45A
0x14000c39f  mov     [rbp+arg_18], 0
0x14000c3a7  mov     [rbp+arg_10], 0
0x14000c3af  mov     [rbp+pv], 0
0x14000c3b7  mov     rax, [rcx]
0x14000c3ba  mov     rbx, [rax+20h]
0x14000c3be  lea     rcx, [rbp+arg_18]
0x14000c3c2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000c3c7  lea     r8, [rbp+arg_18]
0x14000c3cb  mov     edx, esi
0x14000c3cd  mov     rcx, rdi
0x14000c3d0  mov     rax, rbx
0x14000c3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c3d8  mov     ebx, eax
0x14000c3da  test    eax, eax
0x14000c3dc  js      short loc_14000C42B
0x14000c3de  mov     rcx, [rbp+arg_18]
0x14000c3e2  test    rcx, rcx
0x14000c3e5  jnz     short loc_14000C3EE
0x14000c3e7  mov     ebx, 80070490h
0x14000c3ec  jmp     short loc_14000C42B
0x14000c3ee  lea     rdx, [rbp+pv]
0x14000c3f2  call    cs:__imp_mmdDevGetInterfaceIdFromMMDevice
0x14000c3f8  test    eax, eax
0x14000c3fa  jns     short loc_14000C400
0x14000c3fc  mov     ebx, eax
0x14000c3fe  jmp     short loc_14000C42B
0x14000c400  movups  xmm0, cs:DEVINTERFACE_AUDIO_KEYWORDDETECTOR
0x14000c407  movdqu  [rbp+var_10], xmm0
0x14000c40c  lea     r8, [rbp+arg_10]
0x14000c410  lea     rdx, [rbp+var_10]
0x14000c414  mov     rcx, [rbp+pv]
0x14000c418  call    cs:__imp_mmdDevGetRelatedInterfaceId
0x14000c41e  test    eax, eax
0x14000c420  js      short loc_14000C3FC
0x14000c422  cmp     [rbp+arg_10], 0
0x14000c427  jz      short loc_14000C3E7
0x14000c429  xor     ebx, ebx
0x14000c42b  mov     rcx, [rbp+pv]; pv
0x14000c42f  call    cs:__imp_CoTaskMemFree
0x14000c435  mov     [rbp+pv], 0
0x14000c43d  mov     rcx, [rbp+arg_10]; pv
0x14000c441  call    cs:__imp_CoTaskMemFree
0x14000c447  mov     [rbp+arg_10], 0
0x14000c44f  lea     rcx, [rbp+arg_18]
0x14000c453  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000c458  mov     eax, ebx
0x14000c45a  mov     rbx, [rsp+30h+arg_8]
0x14000c45f  add     rsp, 30h
0x14000c463  pop     rdi
0x14000c464  pop     rsi
0x14000c465  pop     rbp
0x14000c466  retn
```
