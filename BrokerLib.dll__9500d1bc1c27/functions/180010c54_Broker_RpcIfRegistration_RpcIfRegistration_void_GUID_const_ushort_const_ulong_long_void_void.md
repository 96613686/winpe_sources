# Broker::RpcIfRegistration::RpcIfRegistration(void *,_GUID const *,ushort const *,ulong,long (*)(void *,void *))

- ea: `0x180010c54`
- end: `0x180010d5f`
- name: `??0RpcIfRegistration@Broker@@QEAA@PEAXPEBU_GUID@@PEBGKP6AJ00@Z@Z`
- size: `267`
- prototype: `__int64 __fastcall(Broker::RpcIfRegistration *__hidden this, void *, const struct _GUID *, const unsigned __int16 *, unsigned int, int (*)(void *, void *))`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018004`

## callees

- `0x180009e94`
- `0x180010c54`
- `0x180010fd8`
- `0x1800139f8`
- `0x1800165da`

## import_xrefs

- `RPCRT4!RpcServerRegisterIf3` at `0x180010cbe`
- `RPCRT4!RpcServerRegisterIf3` at `0x180010cbe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d41`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Broker::RpcIfRegistration *__fastcall Broker::RpcIfRegistration::RpcIfRegistration(
        Broker::RpcIfRegistration *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        int (*a6)(void *, void *))
{
  unsigned int v7; // eax
  void **v9; // [rsp+48h] [rbp-9h] BYREF
  __int128 v10; // [rsp+50h] [rbp-1h]
  int v11; // [rsp+60h] [rbp+Fh]
  unsigned int v12; // [rsp+68h] [rbp+17h]
  _QWORD pExceptionObject[3]; // [rsp+70h] [rbp+1Fh] BYREF
  int v14; // [rsp+88h] [rbp+37h]
  unsigned int v15; // [rsp+90h] [rbp+3Fh]
  HLOCAL hMem; // [rsp+C0h] [rbp+6Fh] BYREF

  hMem = a4;
  *(_QWORD *)this = &unk_18001F250;
  Broker::StringSecurityDescriptor::StringSecurityDescriptor(&hMem, a2);
  *(_OWORD *)((char *)this + 8) = 0;
  v7 = RpcServerRegisterIf3(&unk_18001F250, (char *)this + 8, 0, 33, 1234, -1, a6, hMem);
  if ( v7 )
  {
    v10 = 0;
    v11 = 1;
    v9 = &Broker::Win32Error::`vftable';
    v12 = v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v7);
    std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)&v9);
    v14 = v11;
    pExceptionObject[0] = &Broker::Win32Error::`vftable';
    v15 = v12;
    throw (Broker::Win32Error *)pExceptionObject;
  }
  LocalFree(hMem);
  return this;
}

```

## disassembly

```asm
0x180010c54  mov     rax, rsp
0x180010c57  mov     [rax+8], rbx
0x180010c5b  mov     [rax+10h], rdi
0x180010c5f  mov     [rax+20h], r9
0x180010c63  push    rbp
0x180010c64  lea     rbp, [rax-4Fh]
0x180010c68  sub     rsp, 90h
0x180010c6f  mov     rbx, rcx
0x180010c72  lea     rdi, unk_18001F250
0x180010c79  mov     [rcx], rdi
0x180010c7c  lea     rcx, [rbp+47h+hMem]; SecurityDescriptor
0x180010c80  call    ??0StringSecurityDescriptor@Broker@@QEAA@PEBG@Z; Broker::StringSecurityDescriptor::StringSecurityDescriptor(ushort const *)
0x180010c85  nop
0x180010c86  lea     rdx, [rbx+8]
0x180010c8a  xorps   xmm0, xmm0
0x180010c8d  movups  xmmword ptr [rdx], xmm0
0x180010c90  mov     rax, [rbp+47h+hMem]
0x180010c94  mov     [rsp+90h+var_58], rax
0x180010c99  mov     rax, [rbp+47h+arg_28]
0x180010c9d  mov     [rsp+90h+var_60], rax
0x180010ca2  mov     dword ptr [rsp+90h+var_68], 0FFFFFFFFh
0x180010caa  mov     [rsp+90h+var_70], 4D2h
0x180010cb2  mov     r9d, 21h ; '!'
0x180010cb8  xor     r8d, r8d
0x180010cbb  mov     rcx, rdi
0x180010cbe  call    cs:__imp_RpcServerRegisterIf3
0x180010cc4  test    eax, eax
0x180010cc6  jz      short loc_180010D3D
0x180010cc8  xorps   xmm0, xmm0
0x180010ccb  movups  [rbp+47h+var_48], xmm0
0x180010ccf  mov     [rbp+47h+var_38], 1
0x180010cd6  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180010cdd  mov     [rbp+47h+var_50], rbx
0x180010ce1  mov     [rbp+47h+var_30], eax
0x180010ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ceb  test    byte ptr [rcx+1Ch], 8
0x180010cef  jz      short loc_180010D0F
0x180010cf1  cmp     byte ptr [rcx+19h], 2
0x180010cf5  jb      short loc_180010D0F
0x180010cf7  mov     edx, 0Ch
0x180010cfc  mov     r9d, eax
0x180010cff  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180010d06  mov     rcx, [rcx+10h]
0x180010d0a  call    WPP_SF_d
0x180010d0f  lea     rdx, [rbp+47h+var_50]; struct std::exception *
0x180010d13  lea     rcx, [rbp+47h+pExceptionObject]; this
0x180010d17  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180010d1c  mov     eax, [rbp+47h+var_38]
0x180010d1f  mov     [rbp+47h+var_10], eax
0x180010d22  mov     [rbp+47h+pExceptionObject], rbx
0x180010d26  mov     eax, [rbp+47h+var_30]
0x180010d29  mov     [rbp+47h+var_8], eax
0x180010d2c  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180010d33  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x180010d37  call    _CxxThrowException_0
0x180010d3d  mov     rcx, [rbp+47h+hMem]; hMem
0x180010d41  call    cs:__imp_LocalFree
0x180010d47  mov     rax, rbx
0x180010d4a  lea     r11, [rsp+90h+var_s0]
0x180010d52  mov     rbx, [r11+10h]
0x180010d56  mov     rdi, [r11+18h]
0x180010d5a  mov     rsp, r11
0x180010d5d  pop     rbp
0x180010d5e  retn
```
