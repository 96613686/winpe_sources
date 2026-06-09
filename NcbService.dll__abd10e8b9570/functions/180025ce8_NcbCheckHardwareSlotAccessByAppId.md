# NcbCheckHardwareSlotAccessByAppId

- ea: `0x180025ce8`
- end: `0x180025e14`
- name: `NcbCheckHardwareSlotAccessByAppId`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000e1d0`

## callees

- `0x180025ce8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180025ded`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180025ded`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025d58`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025d58`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180025d18`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180025d18`

## pseudocode

```c
__int64 __fastcall NcbCheckHardwareSlotAccessByAppId(__int64 a1, __int64 a2, __int64 a3, bool *a4)
{
  __int64 result; // rax
  HRESULT v8; // ebx
  HRESULT v9; // eax
  __int64 v10; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-28h] BYREF
  __int64 v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  v12 = a3;
  if ( !a4 )
    return 87;
  *a4 = 0;
  v8 = CoInitializeEx(0, 0);
  if ( v8 >= 0 )
  {
    ppv = 0;
    v13 = 0;
    v8 = CoCreateInstance(
           &GUID_d648fea1_ea00_4ff4_b8bd_034bd2b25a23,
           0,
           1u,
           &GUID_9a12b667_ddbe_4fe9_9279_520c986e61d4,
           &ppv);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(LPVOID, __int64, SID *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             a1,
             &SID_BackgroundAccessManagerService,
             &GUID_428d4ddd_3462_43df_9395_1eff13ae7a4b,
             &v13);
      if ( v8 >= 0 )
      {
        LODWORD(v12) = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v13 + 40LL))(
               v13,
               a1,
               a2,
               &v12);
        v10 = v13;
        v8 = v9;
        *a4 = (v12 & 8) != 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
  }
  result = (unsigned __int16)v8;
  if ( (v8 & 0x1FFF0000) != 0x70000 )
    return (unsigned int)v8;
  return result;
}

```

## disassembly

```asm
0x180025ce8  mov     [rsp+arg_0], rbx
0x180025ced  mov     [rsp+arg_10], r8
0x180025cf2  push    rbp
0x180025cf3  push    rsi
0x180025cf4  push    rdi
0x180025cf5  sub     rsp, 40h
0x180025cf9  mov     rdi, r9
0x180025cfc  mov     rbp, rdx
0x180025cff  mov     rsi, rcx
0x180025d02  test    r9, r9
0x180025d05  jnz     short loc_180025D10
0x180025d07  lea     eax, [r9+57h]
0x180025d0b  jmp     loc_180025E07
0x180025d10  xor     edx, edx; dwCoInit
0x180025d12  mov     byte ptr [r9], 0
0x180025d16  xor     ecx, ecx; pvReserved
0x180025d18  call    cs:__imp_CoInitializeEx
0x180025d1e  mov     ebx, eax
0x180025d20  test    eax, eax
0x180025d22  js      loc_180025DF3
0x180025d28  xor     edx, edx; pUnkOuter
0x180025d2a  mov     [rsp+58h+var_28], 0
0x180025d33  lea     rax, [rsp+58h+var_28]
0x180025d38  mov     [rsp+58h+arg_18], 0
0x180025d41  lea     r9, _GUID_9a12b667_ddbe_4fe9_9279_520c986e61d4; riid
0x180025d48  mov     [rsp+58h+ppv], rax; ppv
0x180025d4d  lea     rcx, _GUID_d648fea1_ea00_4ff4_b8bd_034bd2b25a23; rclsid
0x180025d54  lea     r8d, [rdx+1]; dwClsContext
0x180025d58  call    cs:__imp_CoCreateInstance
0x180025d5e  mov     ebx, eax
0x180025d60  test    eax, eax
0x180025d62  js      loc_180025DED
0x180025d68  mov     rcx, [rsp+58h+var_28]
0x180025d6d  lea     rdx, [rsp+58h+arg_18]
0x180025d72  mov     [rsp+58h+ppv], rdx
0x180025d77  lea     r9, _GUID_428d4ddd_3462_43df_9395_1eff13ae7a4b
0x180025d7e  lea     r8, SID_BackgroundAccessManagerService
0x180025d85  mov     rdx, rsi
0x180025d88  mov     rax, [rcx]
0x180025d8b  mov     rax, [rax+18h]
0x180025d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d94  mov     ebx, eax
0x180025d96  test    eax, eax
0x180025d98  js      short loc_180025DDC
0x180025d9a  mov     rcx, [rsp+58h+arg_18]
0x180025d9f  lea     r9, [rsp+58h+arg_10]
0x180025da4  mov     dword ptr [rsp+58h+arg_10], 0
0x180025dac  mov     r8, rbp
0x180025daf  mov     rdx, rsi
0x180025db2  mov     rax, [rcx]
0x180025db5  mov     rax, [rax+28h]
0x180025db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dbe  mov     rcx, [rsp+58h+arg_18]
0x180025dc3  mov     ebx, eax
0x180025dc5  mov     eax, dword ptr [rsp+58h+arg_10]
0x180025dc9  shr     eax, 3
0x180025dcc  and     al, 1
0x180025dce  mov     [rdi], al
0x180025dd0  mov     rax, [rcx]
0x180025dd3  mov     rax, [rax+10h]
0x180025dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ddc  mov     rcx, [rsp+58h+var_28]
0x180025de1  mov     rax, [rcx]
0x180025de4  mov     rax, [rax+10h]
0x180025de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ded  call    cs:__imp_CoUninitialize
0x180025df3  mov     ecx, ebx
0x180025df5  movzx   eax, bx
0x180025df8  and     ecx, 1FFF0000h
0x180025dfe  cmp     ecx, 70000h
0x180025e04  cmovnz  eax, ebx
0x180025e07  mov     rbx, [rsp+58h+arg_0]
0x180025e0c  add     rsp, 40h
0x180025e10  pop     rdi
0x180025e11  pop     rsi
0x180025e12  pop     rbp
0x180025e13  retn
```
