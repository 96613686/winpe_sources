# ExecuteRemoveWwanNotification(WiFiTaskOpcode,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x14000f338`
- end: `0x14000f456`
- name: `?ExecuteRemoveWwanNotification@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z`
- size: `286`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006b40`

## callees

- `0x14000f338`
- `0x140010178`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000f377`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000f377`

## pseudocode

```c
__int64 __fastcall ExecuteRemoveWwanNotification(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v3; // rdi
  HRESULT v4; // ebx
  int v5; // r8d
  LPVOID v7; // [rsp+58h] [rbp+10h] BYREF
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF

  v8 = a3;
  v3 = *a2;
  v7 = 0;
  v8 = 0;
  v4 = CoCreateInstance(
         &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
         0,
         4u,
         &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
         &v7);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v7 + 24LL))(v7, &v8);
    if ( v4 >= 0 )
      v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v8 + 80LL))(
             v8,
             v3 + 18,
             v3 + 274,
             0,
             v3,
             0);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v5, v3, v4);
  }
  if ( v4 < 0 )
  {
    if ( (v4 & 0x1FFF0000) == 0x70000 )
      v4 = (unsigned __int16)v4;
  }
  else
  {
    v4 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v7 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000f338  mov     r11, rsp
0x14000f33b  mov     [r11+8], rbx
0x14000f33f  mov     [r11+18h], r8
0x14000f343  push    rdi
0x14000f344  sub     rsp, 40h
0x14000f348  mov     rdi, [rdx]
0x14000f34b  mov     qword ptr [r11+10h], 0
0x14000f353  mov     qword ptr [r11+18h], 0
0x14000f35b  lea     rax, [r11+10h]
0x14000f35f  mov     [r11-28h], rax
0x14000f363  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x14000f36a  xor     edx, edx; pUnkOuter
0x14000f36c  lea     r8d, [rdx+4]; dwClsContext
0x14000f370  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x14000f377  call    cs:__imp_CoCreateInstance
0x14000f37d  mov     ebx, eax
0x14000f37f  test    eax, eax
0x14000f381  js      short loc_14000F3CE
0x14000f383  mov     rcx, [rsp+48h+arg_8]
0x14000f388  mov     rax, [rcx]
0x14000f38b  lea     rdx, [rsp+48h+arg_10]
0x14000f390  mov     rax, [rax+18h]
0x14000f394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f399  mov     ebx, eax
0x14000f39b  test    eax, eax
0x14000f39d  js      short loc_14000F3CE
0x14000f39f  mov     rcx, [rsp+48h+arg_10]
0x14000f3a4  mov     rax, [rcx]
0x14000f3a7  lea     r8, [rdi+112h]
0x14000f3ae  lea     rdx, [rdi+12h]
0x14000f3b2  mov     [rsp+48h+var_20], 0
0x14000f3bb  mov     [rsp+48h+var_28], rdi
0x14000f3c0  xor     r9d, r9d
0x14000f3c3  mov     rax, [rax+50h]
0x14000f3c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f3cc  mov     ebx, eax
0x14000f3ce  lea     rax, WPP_GLOBAL_Control
0x14000f3d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f3dc  cmp     rcx, rax
0x14000f3df  jz      short loc_14000F402
0x14000f3e1  cmp     byte ptr [rcx+19h], 4
0x14000f3e5  jb      short loc_14000F402
0x14000f3e7  test    byte ptr [rcx+1Ch], 1
0x14000f3eb  jz      short loc_14000F402
0x14000f3ed  mov     edx, 19h
0x14000f3f2  mov     dword ptr [rsp+48h+var_28], ebx
0x14000f3f6  mov     r9, rdi
0x14000f3f9  mov     rcx, [rcx+10h]
0x14000f3fd  call    WPP_SF_SD
0x14000f402  test    ebx, ebx
0x14000f404  js      short loc_14000F40A
0x14000f406  xor     ebx, ebx
0x14000f408  jmp     short loc_14000F41B
0x14000f40a  mov     eax, ebx
0x14000f40c  and     eax, 1FFF0000h
0x14000f411  cmp     eax, 70000h
0x14000f416  jnz     short loc_14000F41B
0x14000f418  movzx   ebx, bx
0x14000f41b  mov     rcx, [rsp+48h+arg_10]
0x14000f420  test    rcx, rcx
0x14000f423  jz      short loc_14000F432
0x14000f425  mov     rax, [rcx]
0x14000f428  mov     rax, [rax+10h]
0x14000f42c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f431  nop
0x14000f432  mov     rcx, [rsp+48h+arg_8]
0x14000f437  test    rcx, rcx
0x14000f43a  jz      short loc_14000F449
0x14000f43c  mov     rdx, [rcx]
0x14000f43f  mov     rax, [rdx+10h]
0x14000f443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f448  nop
0x14000f449  mov     eax, ebx
0x14000f44b  mov     rbx, [rsp+48h+arg_0]
0x14000f450  add     rsp, 40h
0x14000f454  pop     rdi
0x14000f455  retn
```
