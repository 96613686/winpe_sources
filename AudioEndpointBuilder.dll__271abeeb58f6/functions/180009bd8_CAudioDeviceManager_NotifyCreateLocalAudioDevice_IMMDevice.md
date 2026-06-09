# CAudioDeviceManager::NotifyCreateLocalAudioDevice(IMMDevice *)

- ea: `0x180009bd8`
- end: `0x180009c79`
- name: `?NotifyCreateLocalAudioDevice@CAudioDeviceManager@@QEAAJPEAUIMMDevice@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(CAudioDeviceManager *__hidden this, struct IMMDevice *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e144`

## callees

- `0x180009bd8`
- `0x180009e90`
- `0x180010da8`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c38`

## string_xrefs

- `0x180009c50`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioDeviceManager::NotifyCreateLocalAudioDevice(struct IMMDeviceVtbl *this, struct IMMDevice *a2)
{
  int v3; // ebx
  __int64 v5; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  pv = 0;
  v3 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))a2->lpVtbl->GetId)(a2, &pv);
  if ( v3 < 0 )
  {
    v5 = 2800;
  }
  else
  {
    v3 = CAudioDeviceManager::OnDeviceStateChanged(this, (const unsigned __int16 *)pv, 1);
    if ( v3 >= 0 )
    {
      if ( pv )
        CoTaskMemFree(pv);
      return 0;
    }
    v5 = 2802;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
    (const char *)(unsigned int)v3,
    v6);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180009bd8  mov     [rsp+arg_0], rbx
0x180009bdd  push    rdi; int
0x180009bde  sub     rsp, 20h
0x180009be2  mov     r8, rdx
0x180009be5  mov     rdi, rcx
0x180009be8  mov     [rsp+28h+pv], 0
0x180009bf1  mov     rax, [rdx]
0x180009bf4  lea     rdx, [rsp+28h+pv]
0x180009bf9  mov     rcx, r8
0x180009bfc  mov     rax, [rax+28h]
0x180009c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c05  mov     ebx, eax
0x180009c07  test    eax, eax
0x180009c09  js      short loc_180009C71
0x180009c0b  mov     r8d, 1; unsigned int
0x180009c11  mov     rdx, [rsp+28h+pv]; unsigned __int16 *
0x180009c16  mov     rcx, rdi; this
0x180009c19  call    ?OnDeviceStateChanged@CAudioDeviceManager@@UEAAJPEBGK@Z; CAudioDeviceManager::OnDeviceStateChanged(ushort const *,ulong)
0x180009c1e  mov     ebx, eax
0x180009c20  test    eax, eax
0x180009c22  js      short loc_180009C4B
0x180009c24  mov     rcx, [rsp+28h+pv]; pv
0x180009c29  test    rcx, rcx
0x180009c2c  jz      short loc_180009C34
0x180009c2e  call    cs:__imp_CoTaskMemFree
0x180009c34  xor     eax, eax
0x180009c36  jmp     short loc_180009C40
0x180009c38  call    cs:__imp_CoTaskMemFree
0x180009c3e  mov     eax, ebx
0x180009c40  mov     rbx, [rsp+28h+arg_0]
0x180009c45  add     rsp, 20h
0x180009c49  pop     rdi
0x180009c4a  retn
0x180009c4b  mov     edx, 0AF2h; void *
0x180009c50  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180009c57  mov     r9d, ebx; char *
0x180009c5a  mov     rcx, [rsp+28h]; this
0x180009c5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c64  nop
0x180009c65  mov     rcx, [rsp+28h+pv]; pv
0x180009c6a  test    rcx, rcx
0x180009c6d  jz      short loc_180009C3E
0x180009c6f  jmp     short loc_180009C38
0x180009c71  mov     edx, 0AF0h
0x180009c76  jmp     short loc_180009C50
```
