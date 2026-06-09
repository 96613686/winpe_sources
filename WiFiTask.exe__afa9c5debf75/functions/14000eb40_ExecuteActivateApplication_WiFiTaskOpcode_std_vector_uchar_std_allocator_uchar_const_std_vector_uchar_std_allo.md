# ExecuteActivateApplication(WiFiTaskOpcode,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x14000eb40`
- end: `0x14000ec2d`
- name: `?ExecuteActivateApplication@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z`
- size: `237`
- prototype: `__int64 __fastcall(int, __int64 *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140006b40`

## callees

- `0x14000bf20`
- `0x14000eb40`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000eb7b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000eb7b`

## pseudocode

```c
__int64 __fastcall ExecuteActivateApplication(int a1, __int64 *a2, void *a3)
{
  __int64 v3; // rdi
  HRESULT v4; // ebx
  int v6; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  ppv = a3;
  v6 = a1;
  v3 = *a2;
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_ApplicationActivationManager, 0, 1u, &GUID_2e941141_7f97_4756_ba1d_9decde894a3d, &ppv);
  if ( v4 >= 0 )
  {
    v6 = 0;
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, _QWORD, int *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           v3,
           v3 + 256,
           0,
           &v6);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      &WPP_d7e0deef0d8c389735c42bf67fb2c31a_Traceguids,
      (unsigned int)v4);
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
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000eb40  mov     rax, rsp
0x14000eb43  mov     [rax+10h], rbx
0x14000eb47  mov     [rax+18h], r8
0x14000eb4b  mov     [rax+8], ecx
0x14000eb4e  push    rdi
0x14000eb4f  sub     rsp, 30h
0x14000eb53  mov     rdi, [rdx]
0x14000eb56  mov     qword ptr [rax+18h], 0
0x14000eb5e  lea     rax, [rax+18h]
0x14000eb62  mov     [rsp+38h+ppv], rax; ppv
0x14000eb67  lea     r9, _GUID_2e941141_7f97_4756_ba1d_9decde894a3d; riid
0x14000eb6e  xor     edx, edx; pUnkOuter
0x14000eb70  lea     r8d, [rdx+1]; dwClsContext
0x14000eb74  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x14000eb7b  call    cs:__imp_CoCreateInstance
0x14000eb81  mov     ebx, eax
0x14000eb83  test    eax, eax
0x14000eb85  js      short loc_14000EBB9
0x14000eb87  mov     [rsp+38h+arg_0], 0
0x14000eb8f  mov     rcx, [rsp+38h+arg_10]
0x14000eb94  mov     rax, [rcx]
0x14000eb97  lea     r8, [rdi+100h]
0x14000eb9e  lea     rdx, [rsp+38h+arg_0]
0x14000eba3  mov     [rsp+38h+ppv], rdx
0x14000eba8  xor     r9d, r9d
0x14000ebab  mov     rdx, rdi
0x14000ebae  mov     rax, [rax+18h]
0x14000ebb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ebb7  mov     ebx, eax
0x14000ebb9  lea     rax, WPP_GLOBAL_Control
0x14000ebc0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ebc7  cmp     rcx, rax
0x14000ebca  jz      short loc_14000EBF0
0x14000ebcc  cmp     byte ptr [rcx+19h], 4
0x14000ebd0  jb      short loc_14000EBF0
0x14000ebd2  test    byte ptr [rcx+1Ch], 1
0x14000ebd6  jz      short loc_14000EBF0
0x14000ebd8  mov     edx, 1Bh
0x14000ebdd  mov     r9d, ebx
0x14000ebe0  lea     r8, WPP_d7e0deef0d8c389735c42bf67fb2c31a_Traceguids
0x14000ebe7  mov     rcx, [rcx+10h]
0x14000ebeb  call    WPP_SF_d
0x14000ebf0  test    ebx, ebx
0x14000ebf2  js      short loc_14000EBF8
0x14000ebf4  xor     ebx, ebx
0x14000ebf6  jmp     short loc_14000EC09
0x14000ebf8  mov     eax, ebx
0x14000ebfa  and     eax, 1FFF0000h
0x14000ebff  cmp     eax, 70000h
0x14000ec04  jnz     short loc_14000EC09
0x14000ec06  movzx   ebx, bx
0x14000ec09  mov     rcx, [rsp+38h+arg_10]
0x14000ec0e  test    rcx, rcx
0x14000ec11  jz      short loc_14000EC20
0x14000ec13  mov     rdx, [rcx]
0x14000ec16  mov     rax, [rdx+10h]
0x14000ec1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec1f  nop
0x14000ec20  mov     eax, ebx
0x14000ec22  mov     rbx, [rsp+38h+arg_8]
0x14000ec27  add     rsp, 30h
0x14000ec2b  pop     rdi
0x14000ec2c  retn
```
