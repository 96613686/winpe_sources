# UserService::COMInitialize(bool)

- ea: `0x18000d34c`
- end: `0x18000d405`
- name: `?COMInitialize@UserService@@AEAAJ_N@Z`
- size: `185`
- prototype: `__int64 __fastcall(UserService *__hidden this, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d124`
- `0x18000d288`

## callees

- `0x180003678`
- `0x18000d34c`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000d365`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000d365`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d3c4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d3c4`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18000d383`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18000d383`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserService::COMInitialize(UserService *this, char a2)
{
  HRESULT v4; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  v4 = CoInitializeEx(0, 0);
  *((_DWORD *)this + 24) = v4;
  if ( v4 < 0 )
  {
LABEL_5:
    if ( v4 < 0 )
      return (unsigned int)v4;
    goto LABEL_6;
  }
  if ( a2 && !*((_QWORD *)this + 14) )
  {
    v4 = CoIncrementMTAUsage();
    goto LABEL_5;
  }
LABEL_6:
  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v4 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
  if ( v4 >= 0 )
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d34c  mov     [rsp+arg_8], rbx
0x18000d351  mov     [rsp+arg_10], rsi
0x18000d356  push    rdi
0x18000d357  sub     rsp, 30h
0x18000d35b  mov     sil, dl
0x18000d35e  mov     rdi, rcx
0x18000d361  xor     edx, edx; dwCoInit
0x18000d363  xor     ecx, ecx; pvReserved
0x18000d365  call    cs:__imp_CoInitializeEx
0x18000d36b  mov     ebx, eax
0x18000d36d  mov     [rdi+60h], eax
0x18000d370  test    eax, eax
0x18000d372  js      short loc_18000D38B
0x18000d374  test    sil, sil
0x18000d377  jz      short loc_18000D38F
0x18000d379  lea     rcx, [rdi+70h]
0x18000d37d  cmp     qword ptr [rcx], 0
0x18000d381  jnz     short loc_18000D38F
0x18000d383  call    cs:__imp_CoIncrementMTAUsage
0x18000d389  mov     ebx, eax
0x18000d38b  test    ebx, ebx
0x18000d38d  js      short loc_18000D3F3
0x18000d38f  mov     [rsp+38h+arg_0], 0
0x18000d398  lea     rcx, [rsp+38h+arg_0]
0x18000d39d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d3a2  lea     rax, [rsp+38h+arg_0]
0x18000d3a7  mov     [rsp+38h+ppv], rax; ppv
0x18000d3ac  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18000d3b3  mov     edi, 1
0x18000d3b8  mov     r8d, edi; dwClsContext
0x18000d3bb  xor     edx, edx; pUnkOuter
0x18000d3bd  lea     rcx, CLSID_GlobalOptions; rclsid
0x18000d3c4  call    cs:__imp_CoCreateInstance
0x18000d3ca  mov     ebx, eax
0x18000d3cc  test    eax, eax
0x18000d3ce  js      short loc_18000D3E9
0x18000d3d0  mov     rcx, [rsp+38h+arg_0]
0x18000d3d5  mov     rax, [rcx]
0x18000d3d8  mov     r8d, edi
0x18000d3db  lea     edx, [rdi+4]
0x18000d3de  mov     rax, [rax+18h]
0x18000d3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3e7  mov     ebx, eax
0x18000d3e9  lea     rcx, [rsp+38h+arg_0]
0x18000d3ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d3f3  mov     eax, ebx
0x18000d3f5  mov     rbx, [rsp+38h+arg_8]
0x18000d3fa  mov     rsi, [rsp+38h+arg_10]
0x18000d3ff  add     rsp, 30h
0x18000d403  pop     rdi
0x18000d404  retn
```
