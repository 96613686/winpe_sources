# IsMSFTInternalSelfHosting(void)

- ea: `0x180026814`
- end: `0x1800268c9`
- name: `?IsMSFTInternalSelfHosting@@YAHXZ`
- size: `181`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001e5d0`

## callees

- `0x180015198`
- `0x180026814`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180026835`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180026835`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026867`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026867`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 IsMSFTInternalSelfHosting(void)
{
  BOOL v0; // ebx
  __int16 v2; // [rsp+50h] [rbp+20h] BYREF
  int v3; // [rsp+58h] [rbp+28h] BYREF
  int v4; // [rsp+60h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+38h] BYREF

  v0 = 0;
  v2 = 0;
  ppv = 0;
  v3 = 0;
  v4 = 0;
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    if ( CoCreateInstance(&CLSID_FlightSettingsAPIBroker, 0, 1u, &GUID_e833feb2_c58a_45e4_8d93_08874744febb, &ppv) >= 0
      && (*(int (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, &v2) >= 0
      && v2 == -1
      && (*(int (__fastcall **)(LPVOID, int *, int *))(*(_QWORD *)ppv + 96LL))(ppv, &v3, &v4) >= 0 )
    {
      v0 = (unsigned int)(v3 - 1) <= 1;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return v0;
}

```

## disassembly

```asm
0x180026814  push    rbp
0x180026816  push    rbx
0x180026817  push    rsi
0x180026818  mov     rbp, rsp
0x18002681b  sub     rsp, 30h
0x18002681f  xor     ebx, ebx
0x180026821  xor     eax, eax
0x180026823  mov     [rbp+arg_0], ax
0x180026827  mov     [rbp+arg_18], rax
0x18002682b  mov     [rbp+arg_8], eax
0x18002682e  mov     [rbp+arg_10], eax
0x180026831  xor     edx, edx; dwCoInit
0x180026833  xor     ecx, ecx; pvReserved
0x180026835  call    cs:__imp_CoInitializeEx
0x18002683b  test    eax, eax
0x18002683d  js      short loc_1800268B6
0x18002683f  lea     rcx, [rbp+arg_18]
0x180026843  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026848  lea     rax, [rbp+arg_18]
0x18002684c  mov     [rsp+30h+ppv], rax; ppv
0x180026851  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x180026858  lea     esi, [rbx+1]
0x18002685b  mov     r8d, esi; dwClsContext
0x18002685e  xor     edx, edx; pUnkOuter
0x180026860  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x180026867  call    cs:__imp_CoCreateInstance
0x18002686d  test    eax, eax
0x18002686f  js      short loc_1800268B6
0x180026871  mov     rcx, [rbp+arg_18]
0x180026875  mov     rax, [rcx]
0x180026878  lea     rdx, [rbp+arg_0]
0x18002687c  mov     rax, [rax+18h]
0x180026880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026885  test    eax, eax
0x180026887  js      short loc_1800268B6
0x180026889  cmp     [rbp+arg_0], 0FFFFh
0x18002688e  jnz     short loc_1800268B6
0x180026890  mov     rcx, [rbp+arg_18]
0x180026894  mov     rax, [rcx]
0x180026897  lea     r8, [rbp+arg_10]
0x18002689b  lea     rdx, [rbp+arg_8]
0x18002689f  mov     rax, [rax+60h]
0x1800268a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268a8  test    eax, eax
0x1800268aa  js      short loc_1800268B6
0x1800268ac  mov     ecx, [rbp+arg_8]
0x1800268af  dec     ecx
0x1800268b1  cmp     ecx, esi
0x1800268b3  cmovbe  ebx, esi
0x1800268b6  lea     rcx, [rbp+arg_18]
0x1800268ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800268bf  mov     eax, ebx
0x1800268c1  add     rsp, 30h
0x1800268c5  pop     rsi
0x1800268c6  pop     rbx
0x1800268c7  pop     rbp
0x1800268c8  retn
```
