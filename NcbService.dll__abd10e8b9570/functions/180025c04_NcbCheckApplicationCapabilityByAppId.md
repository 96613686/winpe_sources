# NcbCheckApplicationCapabilityByAppId

- ea: `0x180025c04`
- end: `0x180025ce1`
- name: `NcbCheckApplicationCapabilityByAppId`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000e1d0`

## callees

- `0x180025c04`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180025cba`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180025cba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025c6a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025c6a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180025c37`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180025c37`

## pseudocode

```c
__int64 __fastcall NcbCheckApplicationCapabilityByAppId(__int64 a1, __int64 a2, bool *a3)
{
  __int64 result; // rax
  HRESULT v7; // ebx
  LPVOID v8; // rcx
  int v9; // [rsp+60h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+20h] BYREF

  v9 = 0;
  if ( !a3 )
    return 87;
  *a3 = 0;
  v7 = CoInitializeEx(0, 0);
  if ( v7 >= 0 )
  {
    ppv = 0;
    v7 = CoCreateInstance(&CLSID_BackgroundTaskCapability, 0, 1u, &GUID_d54e68c2_54cd_48b3_ad9a_3f4a4503ba80, &ppv);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64, int *))(*(_QWORD *)ppv + 40LL))(
             ppv,
             a1,
             a2,
             2,
             &v9);
      v8 = ppv;
      *a3 = v9 != 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
    }
    CoUninitialize();
  }
  result = (unsigned __int16)v7;
  if ( (v7 & 0x1FFF0000) != 0x70000 )
    return (unsigned int)v7;
  return result;
}

```

## disassembly

```asm
0x180025c04  mov     [rsp+arg_0], rbx
0x180025c09  push    rbp
0x180025c0a  push    rsi
0x180025c0b  push    rdi
0x180025c0c  sub     rsp, 30h
0x180025c10  mov     [rsp+48h+arg_10], 0
0x180025c18  mov     rdi, r8
0x180025c1b  mov     rsi, rdx
0x180025c1e  mov     rbp, rcx
0x180025c21  test    r8, r8
0x180025c24  jnz     short loc_180025C2F
0x180025c26  lea     eax, [r8+57h]
0x180025c2a  jmp     loc_180025CD4
0x180025c2f  xor     edx, edx; dwCoInit
0x180025c31  mov     byte ptr [r8], 0
0x180025c35  xor     ecx, ecx; pvReserved
0x180025c37  call    cs:__imp_CoInitializeEx
0x180025c3d  mov     ebx, eax
0x180025c3f  test    eax, eax
0x180025c41  js      short loc_180025CC0
0x180025c43  xor     edx, edx; pUnkOuter
0x180025c45  mov     [rsp+48h+arg_18], 0
0x180025c4e  lea     rax, [rsp+48h+arg_18]
0x180025c53  lea     r9, _GUID_d54e68c2_54cd_48b3_ad9a_3f4a4503ba80; riid
0x180025c5a  mov     [rsp+48h+ppv], rax; ppv
0x180025c5f  lea     rcx, CLSID_BackgroundTaskCapability; rclsid
0x180025c66  lea     r8d, [rdx+1]; dwClsContext
0x180025c6a  call    cs:__imp_CoCreateInstance
0x180025c70  mov     ebx, eax
0x180025c72  test    eax, eax
0x180025c74  js      short loc_180025CBA
0x180025c76  mov     rcx, [rsp+48h+arg_18]
0x180025c7b  lea     rdx, [rsp+48h+arg_10]
0x180025c80  mov     [rsp+48h+ppv], rdx
0x180025c85  mov     r9d, 2
0x180025c8b  mov     r8, rsi
0x180025c8e  mov     rdx, rbp
0x180025c91  mov     rax, [rcx]
0x180025c94  mov     rax, [rax+28h]
0x180025c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c9d  cmp     [rsp+48h+arg_10], 0
0x180025ca2  mov     ebx, eax
0x180025ca4  mov     rcx, [rsp+48h+arg_18]
0x180025ca9  setnz   al
0x180025cac  mov     [rdi], al
0x180025cae  mov     rax, [rcx]
0x180025cb1  mov     rax, [rax+10h]
0x180025cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cba  call    cs:__imp_CoUninitialize
0x180025cc0  mov     ecx, ebx
0x180025cc2  movzx   eax, bx
0x180025cc5  and     ecx, 1FFF0000h
0x180025ccb  cmp     ecx, 70000h
0x180025cd1  cmovnz  eax, ebx
0x180025cd4  mov     rbx, [rsp+48h+arg_0]
0x180025cd9  add     rsp, 30h
0x180025cdd  pop     rdi
0x180025cde  pop     rsi
0x180025cdf  pop     rbp
0x180025ce0  retn
```
