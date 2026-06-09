# GetNetworkConnectionStatus(bool &)

- ea: `0x140016800`
- end: `0x1400168ae`
- name: `?GetNetworkConnectionStatus@@YAJAEA_N@Z`
- size: `174`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a39c`
- `0x14000cd78`

## callees

- `0x14000740c`
- `0x140016800`
- `0x14001c010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140016842`
- `ole32!CoCreateInstance` at `0x140016842`

## pseudocode

```c
__int64 __fastcall GetNetworkConnectionStatus(bool *a1)
{
  HRESULT v2; // ebx
  __int16 v4; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  v4 = -1;
  *a1 = 0;
  v2 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &IID_INetworkListManager, &ppv);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 96LL))(ppv, &v4);
    if ( v2 >= 0 && v4 == -1 )
      *a1 = 1;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v2 < 0 )
    LogError(L"GetNetworkConnectionStatus failed with error = 0x%1!x!.", (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140016800  mov     rax, rsp
0x140016803  mov     [rax+18h], rbx
0x140016807  mov     [rax+20h], rsi
0x14001680b  push    rdi
0x14001680c  sub     rsp, 30h
0x140016810  or      esi, 0FFFFFFFFh
0x140016813  mov     qword ptr [rax+10h], 0
0x14001681b  mov     [rax+8], si
0x14001681f  lea     rax, [rax+10h]
0x140016823  mov     rdi, rcx
0x140016826  mov     byte ptr [rcx], 0
0x140016829  lea     r9, IID_INetworkListManager; riid
0x140016830  mov     [rsp+38h+ppv], rax; ppv
0x140016835  lea     r8d, [rsi+2]; dwClsContext
0x140016839  xor     edx, edx; pUnkOuter
0x14001683b  lea     rcx, CLSID_NetworkListManager; rclsid
0x140016842  call    cs:__imp_CoCreateInstance
0x140016848  mov     ebx, eax
0x14001684a  test    eax, eax
0x14001684c  js      short loc_140016874
0x14001684e  mov     rcx, [rsp+38h+arg_8]
0x140016853  lea     rdx, [rsp+38h+arg_0]
0x140016858  mov     rax, [rcx]
0x14001685b  mov     rax, [rax+60h]
0x14001685f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016864  mov     ebx, eax
0x140016866  test    eax, eax
0x140016868  js      short loc_140016874
0x14001686a  cmp     si, [rsp+38h+arg_0]
0x14001686f  jnz     short loc_140016874
0x140016871  mov     byte ptr [rdi], 1
0x140016874  mov     rcx, [rsp+38h+arg_8]
0x140016879  test    rcx, rcx
0x14001687c  jz      short loc_14001688A
0x14001687e  mov     rax, [rcx]
0x140016881  mov     rax, [rax+10h]
0x140016885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001688a  test    ebx, ebx
0x14001688c  jns     short loc_14001689C
0x14001688e  mov     edx, ebx
0x140016890  lea     rcx, aGetnetworkconn; "GetNetworkConnectionStatus failed with "...
0x140016897  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001689c  mov     rsi, [rsp+38h+arg_18]
0x1400168a1  mov     eax, ebx
0x1400168a3  mov     rbx, [rsp+38h+arg_10]
0x1400168a8  add     rsp, 30h
0x1400168ac  pop     rdi
0x1400168ad  retn
```
