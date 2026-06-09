# RemoveVmsDevice(wchar_t const *)

- ea: `0x18007e068`
- end: `0x18007e162`
- name: `?RemoveVmsDevice@@YAJPEB_W@Z`
- size: `250`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18007dda0`

## callees

- `0x18004b460`
- `0x18007dd78`
- `0x18007e068`
- `0x1800810d0`

## import_xrefs

- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18007e09a`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18007e09a`
- `DEVOBJ!DevObjDeleteDevice` at `0x18007e127`
- `DEVOBJ!DevObjDeleteDevice` at `0x18007e127`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18007e0ea`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18007e0ea`

## string_xrefs

- `0x18007e0ff`: `onecore\net\netsetup\plugins\vmsnetsetupplugin.cpp`

## pseudocode

```c
__int64 __fastcall RemoveVmsDevice(const wchar_t *a1)
{
  __int64 DeviceInfoList; // rbx
  const char *v3; // r9
  __int64 v4; // rdx
  unsigned int LastError; // ebx
  __int64 v7; // [rsp+30h] [rbp-58h] BYREF
  int v8; // [rsp+38h] [rbp-50h] BYREF
  _OWORD v9[3]; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v7 = DeviceInfoList;
  if ( ((DeviceInfoList + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    memset(v9, 0, sizeof(v9));
    LODWORD(v9[0]) = 48;
    if ( (unsigned int)DevObjOpenDeviceInfo(DeviceInfoList, a1, 0, 0, v9) )
    {
      v8 = 0;
      if ( (unsigned int)DevObjDeleteDevice(DeviceInfoList, v9, 0, &v8) )
      {
        LastError = 0;
        goto LABEL_9;
      }
      v4 = 50;
    }
    else
    {
      v4 = 47;
    }
  }
  else
  {
    v4 = 36;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v4,
                (unsigned int)"onecore\\net\\netsetup\\plugins\\vmsnetsetupplugin.cpp",
                v3);
LABEL_9:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&v7);
  return LastError;
}

```

## disassembly

```asm
0x18007e068  mov     [rsp+arg_8], rbx
0x18007e06d  push    rdi
0x18007e06e  sub     rsp, 80h
0x18007e075  mov     rax, cs:__security_cookie
0x18007e07c  xor     rax, rsp
0x18007e07f  mov     [rsp+88h+var_18], rax
0x18007e084  mov     rdi, rcx
0x18007e087  mov     [rsp+88h+var_68], 0
0x18007e090  xor     ecx, ecx
0x18007e092  xor     r9d, r9d
0x18007e095  xor     r8d, r8d
0x18007e098  xor     edx, edx
0x18007e09a  call    cs:__imp_DevObjCreateDeviceInfoList
0x18007e0a0  mov     rbx, rax
0x18007e0a3  mov     [rsp+88h+var_58], rax
0x18007e0a8  inc     rax
0x18007e0ab  test    rax, 0FFFFFFFFFFFFFFFEh
0x18007e0b1  jnz     short loc_18007E0BA
0x18007e0b3  mov     edx, 24h ; '$'
0x18007e0b8  jmp     short loc_18007E0F7
0x18007e0ba  xorps   xmm0, xmm0
0x18007e0bd  lea     rax, [rsp+88h+var_48]
0x18007e0c2  movups  [rsp+88h+var_48], xmm0
0x18007e0c7  xor     r9d, r9d
0x18007e0ca  mov     dword ptr [rsp+88h+var_48], 30h ; '0'
0x18007e0d2  xor     r8d, r8d
0x18007e0d5  mov     [rsp+88h+var_68], rax
0x18007e0da  mov     rdx, rdi
0x18007e0dd  mov     rcx, rbx
0x18007e0e0  movups  [rsp+88h+var_38], xmm0
0x18007e0e5  movups  [rsp+88h+var_28], xmm0
0x18007e0ea  call    cs:__imp_DevObjOpenDeviceInfo
0x18007e0f0  test    eax, eax
0x18007e0f2  jnz     short loc_18007E10F
0x18007e0f4  lea     edx, [rax+2Fh]; void *
0x18007e0f7  mov     rcx, [rsp+88h]; this
0x18007e0ff  lea     r8, aOnecoreNetNets; "onecore\\net\\netsetup\\plugins\\vmsnet"...
0x18007e106  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007e10b  mov     ebx, eax
0x18007e10d  jmp     short loc_18007E138
0x18007e10f  lea     r9, [rsp+88h+var_50]
0x18007e114  mov     [rsp+88h+var_50], 0
0x18007e11c  xor     r8d, r8d
0x18007e11f  lea     rdx, [rsp+88h+var_48]
0x18007e124  mov     rcx, rbx
0x18007e127  call    cs:__imp_DevObjDeleteDevice
0x18007e12d  test    eax, eax
0x18007e12f  jnz     short loc_18007E136
0x18007e131  lea     edx, [rax+32h]
0x18007e134  jmp     short loc_18007E0F7
0x18007e136  xor     ebx, ebx
0x18007e138  lea     rcx, [rsp+88h+var_58]
0x18007e13d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x18007e142  mov     eax, ebx
0x18007e144  mov     rcx, [rsp+88h+var_18]
0x18007e149  xor     rcx, rsp; StackCookie
0x18007e14c  call    __security_check_cookie
0x18007e151  mov     rbx, [rsp+88h+arg_8]
0x18007e159  add     rsp, 80h
0x18007e160  pop     rdi
0x18007e161  retn
```
