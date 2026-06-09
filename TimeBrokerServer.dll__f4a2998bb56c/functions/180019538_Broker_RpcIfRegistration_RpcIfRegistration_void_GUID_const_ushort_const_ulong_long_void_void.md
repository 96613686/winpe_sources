# Broker::RpcIfRegistration::RpcIfRegistration(void *,_GUID const *,ushort const *,ulong,long (*)(void *,void *))

- ea: `0x180019538`
- end: `0x18001963f`
- name: `??0RpcIfRegistration@Broker@@QEAA@PEAXPEBU_GUID@@PEBGKP6AJ00@Z@Z`
- size: `263`
- prototype: `Broker::RpcIfRegistration *__fastcall(Broker::RpcIfRegistration *this, void *, const struct _GUID *, const unsigned __int16 *, unsigned int, int (*)(void *, void *))`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e8c4`

## callees

- `0x180003800`
- `0x180003eac`
- `0x180011240`
- `0x180013978`
- `0x180019538`

## import_xrefs

- `RPCRT4!RpcServerRegisterIf3` at `0x1800195a7`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800195a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001962a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001962a`

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
0x180019538  push    rbp
0x18001953a  push    rbx
0x18001953b  push    rsi
0x18001953c  push    rdi
0x18001953d  lea     rbp, [rsp-2Fh]
0x180019542  sub     rsp, 98h
0x180019549  mov     rdi, r8
0x18001954c  mov     rsi, rdx
0x18001954f  mov     rbx, rcx
0x180019552  mov     [rcx], rdx
0x180019555  mov     rdx, r9; StringSecurityDescriptor
0x180019558  lea     rcx, [rbp+47h+hMem]; SecurityDescriptor
0x18001955c  call    ??0StringSecurityDescriptor@Broker@@QEAA@PEBG@Z; Broker::StringSecurityDescriptor::StringSecurityDescriptor(ushort const *)
0x180019561  nop
0x180019562  lea     rdx, [rbx+8]
0x180019566  test    rdi, rdi
0x180019569  jz      short loc_180019574
0x18001956b  movups  xmm0, xmmword ptr [rdi]
0x18001956e  movdqu  xmmword ptr [rdx], xmm0
0x180019572  jmp     short loc_18001957A
0x180019574  xorps   xmm0, xmm0
0x180019577  movups  xmmword ptr [rdx], xmm0
0x18001957a  mov     rax, [rbp+47h+hMem]
0x18001957e  mov     [rsp+0B0h+var_78], rax
0x180019583  mov     rax, [rbp+47h+arg_28]
0x180019587  mov     [rsp+0B0h+var_80], rax
0x18001958c  mov     eax, [rbp+47h+arg_20]
0x18001958f  mov     [rsp+0B0h+var_88], eax
0x180019593  mov     [rsp+0B0h+var_90], 4D2h
0x18001959b  mov     r9d, 21h ; '!'
0x1800195a1  xor     r8d, r8d
0x1800195a4  mov     rcx, rsi
0x1800195a7  call    cs:__imp_RpcServerRegisterIf3
0x1800195ad  test    eax, eax
0x1800195af  jz      short loc_180019626
0x1800195b1  xorps   xmm0, xmm0
0x1800195b4  movups  [rbp+47h+var_68], xmm0
0x1800195b8  mov     [rbp+47h+var_58], 1
0x1800195bf  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800195c6  mov     [rbp+47h+var_70], rbx
0x1800195ca  mov     [rbp+47h+var_50], eax
0x1800195cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195d4  test    byte ptr [rcx+1Ch], 8
0x1800195d8  jz      short loc_1800195F8
0x1800195da  cmp     byte ptr [rcx+19h], 2
0x1800195de  jb      short loc_1800195F8
0x1800195e0  mov     edx, 0Ch
0x1800195e5  mov     r9d, eax
0x1800195e8  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x1800195ef  mov     rcx, [rcx+10h]
0x1800195f3  call    WPP_SF_d
0x1800195f8  lea     rdx, [rbp+47h+var_70]; struct std::exception *
0x1800195fc  lea     rcx, [rbp+47h+pExceptionObject]; this
0x180019600  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180019605  mov     eax, [rbp+47h+var_58]
0x180019608  mov     [rbp+47h+var_30], eax
0x18001960b  mov     [rbp+47h+pExceptionObject], rbx
0x18001960f  mov     eax, [rbp+47h+var_50]
0x180019612  mov     [rbp+47h+var_28], eax
0x180019615  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001961c  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x180019620  call    _CxxThrowException_0
0x180019626  mov     rcx, [rbp+47h+hMem]; hMem
0x18001962a  call    cs:__imp_LocalFree
0x180019630  mov     rax, rbx
0x180019633  add     rsp, 98h
0x18001963a  pop     rdi
0x18001963b  pop     rsi
0x18001963c  pop     rbx
0x18001963d  pop     rbp
0x18001963e  retn
```
