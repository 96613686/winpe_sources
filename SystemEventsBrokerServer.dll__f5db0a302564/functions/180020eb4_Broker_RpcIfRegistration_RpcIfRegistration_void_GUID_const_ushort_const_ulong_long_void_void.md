# Broker::RpcIfRegistration::RpcIfRegistration(void *,_GUID const *,ushort const *,ulong,long (*)(void *,void *))

- ea: `0x180020eb4`
- end: `0x180020fbb`
- name: `??0RpcIfRegistration@Broker@@QEAA@PEAXPEBU_GUID@@PEBGKP6AJ00@Z@Z`
- size: `263`
- prototype: `Broker::RpcIfRegistration *__fastcall(Broker::RpcIfRegistration *this, void *, const struct _GUID *, const unsigned __int16 *, unsigned int, int (*)(void *, void *))`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020fc4`

## callees

- `0x1800030e0`
- `0x180016090`
- `0x1800195e0`
- `0x18001d9ac`
- `0x180020eb4`

## import_xrefs

- `RPCRT4!RpcServerRegisterIf3` at `0x180020f23`
- `RPCRT4!RpcServerRegisterIf3` at `0x180020f23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020fa6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020fa6`

## pseudocode

```c
Broker::RpcIfRegistration *__fastcall Broker::RpcIfRegistration::RpcIfRegistration(
        Broker::RpcIfRegistration *this,
        void *a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int (*a6)(void *, void *))
{
  struct _GUID *v9; // rdx
  unsigned int v10; // eax
  void **v12; // [rsp+40h] [rbp-29h] BYREF
  __int128 v13; // [rsp+48h] [rbp-21h]
  int v14; // [rsp+58h] [rbp-11h]
  unsigned int v15; // [rsp+60h] [rbp-9h]
  _QWORD pExceptionObject[3]; // [rsp+68h] [rbp-1h] BYREF
  int v17; // [rsp+80h] [rbp+17h]
  unsigned int v18; // [rsp+88h] [rbp+1Fh]
  HLOCAL hMem; // [rsp+C0h] [rbp+57h] BYREF

  *(_QWORD *)this = a2;
  Broker::StringSecurityDescriptor::StringSecurityDescriptor(&hMem, a4);
  v9 = (struct _GUID *)((char *)this + 8);
  if ( a3 )
    *v9 = *a3;
  else
    *v9 = 0;
  v10 = RpcServerRegisterIf3(a2, v9, 0, 33, 1234, a5, a6, hMem);
  if ( v10 )
  {
    v13 = 0;
    v14 = 1;
    v12 = &Broker::Win32Error::`vftable';
    v15 = v10;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v10);
    std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)&v12);
    v17 = v14;
    pExceptionObject[0] = &Broker::Win32Error::`vftable';
    v18 = v15;
    throw (Broker::Win32Error *)pExceptionObject;
  }
  LocalFree(hMem);
  return this;
}

```

## disassembly

```asm
0x180020eb4  push    rbp
0x180020eb6  push    rbx
0x180020eb7  push    rsi
0x180020eb8  push    rdi
0x180020eb9  lea     rbp, [rsp-2Fh]
0x180020ebe  sub     rsp, 98h
0x180020ec5  mov     rdi, r8
0x180020ec8  mov     rsi, rdx
0x180020ecb  mov     rbx, rcx
0x180020ece  mov     [rcx], rdx
0x180020ed1  mov     rdx, r9; StringSecurityDescriptor
0x180020ed4  lea     rcx, [rbp+47h+hMem]; SecurityDescriptor
0x180020ed8  call    ??0StringSecurityDescriptor@Broker@@QEAA@PEBG@Z; Broker::StringSecurityDescriptor::StringSecurityDescriptor(ushort const *)
0x180020edd  nop
0x180020ede  lea     rdx, [rbx+8]
0x180020ee2  test    rdi, rdi
0x180020ee5  jz      short loc_180020EF0
0x180020ee7  movups  xmm0, xmmword ptr [rdi]
0x180020eea  movdqu  xmmword ptr [rdx], xmm0
0x180020eee  jmp     short loc_180020EF6
0x180020ef0  xorps   xmm0, xmm0
0x180020ef3  movups  xmmword ptr [rdx], xmm0
0x180020ef6  mov     rax, [rbp+47h+hMem]
0x180020efa  mov     [rsp+0B0h+var_78], rax
0x180020eff  mov     rax, [rbp+47h+arg_28]
0x180020f03  mov     [rsp+0B0h+var_80], rax
0x180020f08  mov     eax, [rbp+47h+arg_20]
0x180020f0b  mov     [rsp+0B0h+var_88], eax
0x180020f0f  mov     [rsp+0B0h+var_90], 4D2h
0x180020f17  mov     r9d, 21h ; '!'
0x180020f1d  xor     r8d, r8d
0x180020f20  mov     rcx, rsi
0x180020f23  call    cs:__imp_RpcServerRegisterIf3
0x180020f29  test    eax, eax
0x180020f2b  jz      short loc_180020FA2
0x180020f2d  xorps   xmm0, xmm0
0x180020f30  movups  [rbp+47h+var_68], xmm0
0x180020f34  mov     [rbp+47h+var_58], 1
0x180020f3b  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180020f42  mov     [rbp+47h+var_70], rbx
0x180020f46  mov     [rbp+47h+var_50], eax
0x180020f49  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f50  test    byte ptr [rcx+1Ch], 8
0x180020f54  jz      short loc_180020F74
0x180020f56  cmp     byte ptr [rcx+19h], 2
0x180020f5a  jb      short loc_180020F74
0x180020f5c  mov     edx, 0Ch
0x180020f61  mov     r9d, eax
0x180020f64  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180020f6b  mov     rcx, [rcx+10h]
0x180020f6f  call    WPP_SF_d
0x180020f74  lea     rdx, [rbp+47h+var_70]; struct std::exception *
0x180020f78  lea     rcx, [rbp+47h+pExceptionObject]; this
0x180020f7c  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180020f81  mov     eax, [rbp+47h+var_58]
0x180020f84  mov     [rbp+47h+var_30], eax
0x180020f87  mov     [rbp+47h+pExceptionObject], rbx
0x180020f8b  mov     eax, [rbp+47h+var_50]
0x180020f8e  mov     [rbp+47h+var_28], eax
0x180020f91  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180020f98  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x180020f9c  call    _CxxThrowException_0
0x180020fa2  mov     rcx, [rbp+47h+hMem]; hMem
0x180020fa6  call    cs:__imp_LocalFree
0x180020fac  mov     rax, rbx
0x180020faf  add     rsp, 98h
0x180020fb6  pop     rdi
0x180020fb7  pop     rsi
0x180020fb8  pop     rbx
0x180020fb9  pop     rbp
0x180020fba  retn
```
