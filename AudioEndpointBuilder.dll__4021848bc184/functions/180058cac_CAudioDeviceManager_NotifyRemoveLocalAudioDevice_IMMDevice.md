# CAudioDeviceManager::NotifyRemoveLocalAudioDevice(IMMDevice *)

- ea: `0x180058cac`
- end: `0x180058d5c`
- name: `?NotifyRemoveLocalAudioDevice@CAudioDeviceManager@@QEAAJPEAUIMMDevice@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(CAudioDeviceManager *__hidden this, struct IMMDevice *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e43c`
- `0x180050048`

## callees

- `0x18000fb60`
- `0x180010da8`
- `0x180031920`
- `0x180058cac`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058d16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058d44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058d16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058d44`

## string_xrefs

- `0x180058cf7`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioDeviceManager::NotifyRemoveLocalAudioDevice(CAudioDeviceManager *this, struct IMMDevice *a2)
{
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  int v5; // ebx
  __int64 v6; // rdx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  pv = 0;
  GetId = a2->lpVtbl->GetId;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v5 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(a2, &pv);
  if ( v5 < 0 )
  {
    v6 = 3679;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)(unsigned int)v5,
      v8);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v5;
  }
  v5 = CAudioDeviceManager::OnDeviceRemoved(this, (const unsigned __int16 *)pv);
  if ( v5 < 0 )
  {
    v6 = 3681;
    goto LABEL_3;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return 0;
}

```

## disassembly

```asm
0x180058cac  mov     r11, rsp
0x180058caf  mov     [r11+8], rbx
0x180058cb3  mov     [r11+18h], rsi
0x180058cb7  push    rdi; int
0x180058cb8  sub     rsp, 20h
0x180058cbc  mov     rdi, rdx
0x180058cbf  mov     rsi, rcx
0x180058cc2  mov     qword ptr [r11+10h], 0
0x180058cca  mov     rax, [rdx]
0x180058ccd  mov     rbx, [rax+28h]
0x180058cd1  xor     edx, edx
0x180058cd3  lea     rcx, [r11+10h]
0x180058cd7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180058cdc  lea     rdx, [rsp+28h+pv]
0x180058ce1  mov     rcx, rdi
0x180058ce4  mov     rax, rbx
0x180058ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058cec  mov     ebx, eax
0x180058cee  test    eax, eax
0x180058cf0  jns     short loc_180058D20
0x180058cf2  mov     edx, 0E5Fh; void *
0x180058cf7  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180058cfe  mov     r9d, ebx; char *
0x180058d01  mov     rcx, [rsp+28h]; this
0x180058d06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058d0b  nop
0x180058d0c  mov     rcx, [rsp+28h+pv]; pv
0x180058d11  test    rcx, rcx
0x180058d14  jz      short loc_180058D1C
0x180058d16  call    cs:__imp_CoTaskMemFree
0x180058d1c  mov     eax, ebx
0x180058d1e  jmp     short loc_180058D4C
0x180058d20  mov     rdx, [rsp+28h+pv]; unsigned __int16 *
0x180058d25  mov     rcx, rsi; this
0x180058d28  call    ?OnDeviceRemoved@CAudioDeviceManager@@UEAAJPEBG@Z; CAudioDeviceManager::OnDeviceRemoved(ushort const *)
0x180058d2d  mov     ebx, eax
0x180058d2f  test    eax, eax
0x180058d31  jns     short loc_180058D3A
0x180058d33  mov     edx, 0E61h
0x180058d38  jmp     short loc_180058CF7
0x180058d3a  mov     rcx, [rsp+28h+pv]; pv
0x180058d3f  test    rcx, rcx
0x180058d42  jz      short loc_180058D4A
0x180058d44  call    cs:__imp_CoTaskMemFree
0x180058d4a  xor     eax, eax
0x180058d4c  mov     rbx, [rsp+28h+arg_0]
0x180058d51  mov     rsi, [rsp+28h+arg_10]
0x180058d56  add     rsp, 20h
0x180058d5a  pop     rdi
0x180058d5b  retn
```
