# Broker::RpcServerRegistration::RpcServerRegistration(void *,_GUID const *,_GUID const *,ushort const *,ushort const *,ushort const *,ulong,long (*)(void *,void *),bool)

- ea: `0x180010d68`
- end: `0x180010fd0`
- name: `??0RpcServerRegistration@Broker@@QEAA@PEAXPEBU_GUID@@1PEBG22KP6AJ00@Z_N@Z`
- size: `616`
- prototype: `_QWORD(Broker::RpcServerRegistration *__hidden this, void *, const struct _GUID *, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int (*)(void *, void *), bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010b84`

## callees

- `0x180009e94`
- `0x180010d68`
- `0x180010fd8`
- `0x180015f48`
- `0x1800165da`

## import_xrefs

- `RPCRT4!RpcServerUseProtseqW` at `0x180010dc8`
- `RPCRT4!RpcServerUseProtseqW` at `0x180010dc8`
- `RPCRT4!RpcObjectSetType` at `0x180010e3a`
- `RPCRT4!RpcObjectSetType` at `0x180010e3a`
- `RPCRT4!RpcBindingVectorFree` at `0x180010f7c`
- `RPCRT4!RpcBindingVectorFree` at `0x180010f7c`
- `RPCRT4!RpcServerInqBindings` at `0x180010ed1`
- `RPCRT4!RpcServerInqBindings` at `0x180010ed1`
- `RPCRT4!RpcEpRegisterW` at `0x180010f42`
- `RPCRT4!RpcEpRegisterW` at `0x180010f42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010fb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010fb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Broker::RpcServerRegistration *__fastcall Broker::RpcServerRegistration::RpcServerRegistration(
        Broker::RpcServerRegistration *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct _GUID *a4)
{
  RPC_BINDING_VECTOR **v6; // r15
  unsigned int v7; // eax
  unsigned int v8; // esi
  unsigned int v9; // eax
  unsigned int v10; // esi
  _DWORD *v11; // rax
  unsigned int v12; // eax
  unsigned int v13; // esi
  unsigned int v14; // eax
  unsigned int v15; // esi
  void **pExceptionObject; // [rsp+20h] [rbp-30h] BYREF
  __int128 v18; // [rsp+28h] [rbp-28h]
  int v19; // [rsp+38h] [rbp-18h]
  unsigned int v20; // [rsp+40h] [rbp-10h]
  void *SecurityDescriptor; // [rsp+80h] [rbp+30h] BYREF

  SecurityDescriptor = a3;
  *(_QWORD *)this = &unk_18001F250;
  v6 = (RPC_BINDING_VECTOR **)((char *)this + 16);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 1) = 0;
  Broker::StringSecurityDescriptor::StringSecurityDescriptor(&SecurityDescriptor, a2);
  v7 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
  v8 = v7;
  if ( v7 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v7);
    v18 = 0;
    v19 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v20 = v8;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  if ( a4 )
  {
    v9 = RpcObjectSetType(a4, 0);
    v10 = v9;
    if ( v9 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v9);
      v18 = 0;
      v19 = 1;
      pExceptionObject = &Broker::Win32Error::`vftable';
      v20 = v10;
      throw (Broker::Win32Error *)&pExceptionObject;
    }
    v11 = operator new[](0x20u);
    *((_QWORD *)this + 3) = v11;
    *v11 = 1;
    *(_QWORD *)(*((_QWORD *)this + 3) + 8LL) = *((_QWORD *)this + 3) + 16LL;
    *(struct _GUID *)*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) = *a4;
  }
  v12 = RpcServerInqBindings(v6);
  v13 = v12;
  if ( v12 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v12);
    v18 = 0;
    v19 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v20 = v13;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  v14 = RpcEpRegisterW(*(RPC_IF_HANDLE *)this, *v6, *((UUID_VECTOR **)this + 3), 0);
  v15 = v14;
  if ( v14 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v14);
    RpcBindingVectorFree(v6);
    v18 = 0;
    v19 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v20 = v15;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  LocalFree(SecurityDescriptor);
  return this;
}

```

## disassembly

```asm
0x180010d68  mov     [rsp-18h+arg_0], rsi
0x180010d6d  mov     [rsp-18h+arg_8], rdi
0x180010d72  mov     [rsp-18h+SecurityDescriptor], r8
0x180010d77  push    rbp
0x180010d78  push    r14
0x180010d7a  push    r15
0x180010d7c  mov     rbp, rsp
0x180010d7f  sub     rsp, 50h
0x180010d83  mov     r14, r9
0x180010d86  mov     rdi, rcx
0x180010d89  lea     rax, unk_18001F250
0x180010d90  mov     [rcx], rax
0x180010d93  lea     r15, [rcx+10h]
0x180010d97  mov     qword ptr [r15], 0
0x180010d9e  mov     qword ptr [rcx+18h], 0
0x180010da6  mov     qword ptr [rcx+8], 0
0x180010dae  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180010db2  call    ??0StringSecurityDescriptor@Broker@@QEAA@PEBG@Z; Broker::StringSecurityDescriptor::StringSecurityDescriptor(ushort const *)
0x180010db7  nop
0x180010db8  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180010dbc  mov     edx, 0Ah; MaxCalls
0x180010dc1  lea     rcx, Protseq; "ncalrpc"
0x180010dc8  call    cs:__imp_RpcServerUseProtseqW
0x180010dce  mov     esi, eax
0x180010dd0  test    eax, eax
0x180010dd2  jz      short loc_180010E2C
0x180010dd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ddb  test    byte ptr [rcx+1Ch], 8
0x180010ddf  jz      short loc_180010DFF
0x180010de1  cmp     byte ptr [rcx+19h], 2
0x180010de5  jb      short loc_180010DFF
0x180010de7  mov     edx, 1Bh
0x180010dec  mov     r9d, eax
0x180010def  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180010df6  mov     rcx, [rcx+10h]
0x180010dfa  call    WPP_SF_d
0x180010dff  xorps   xmm0, xmm0
0x180010e02  movups  [rbp+var_28], xmm0
0x180010e06  mov     [rbp+var_18], 1
0x180010e0d  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180010e14  mov     [rbp+pExceptionObject], rax
0x180010e18  mov     [rbp+var_10], esi
0x180010e1b  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180010e22  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010e26  call    _CxxThrowException_0
0x180010e2c  test    r14, r14
0x180010e2f  jz      loc_180010ECE
0x180010e35  xor     edx, edx; TypeUuid
0x180010e37  mov     rcx, r14; ObjUuid
0x180010e3a  call    cs:__imp_RpcObjectSetType
0x180010e40  mov     esi, eax
0x180010e42  test    eax, eax
0x180010e44  jz      short loc_180010E9E
0x180010e46  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e4d  test    byte ptr [rcx+1Ch], 8
0x180010e51  jz      short loc_180010E71
0x180010e53  cmp     byte ptr [rcx+19h], 2
0x180010e57  jb      short loc_180010E71
0x180010e59  mov     edx, 1Ch
0x180010e5e  mov     r9d, eax
0x180010e61  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180010e68  mov     rcx, [rcx+10h]
0x180010e6c  call    WPP_SF_d
0x180010e71  xorps   xmm0, xmm0
0x180010e74  movups  [rbp+var_28], xmm0
0x180010e78  mov     [rbp+var_18], 1
0x180010e7f  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180010e86  mov     [rbp+pExceptionObject], rax
0x180010e8a  mov     [rbp+var_10], esi
0x180010e8d  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180010e94  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010e98  call    _CxxThrowException_0
0x180010e9e  mov     ecx, 20h ; ' '; unsigned __int64
0x180010ea3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010ea8  mov     [rdi+18h], rax
0x180010eac  mov     dword ptr [rax], 1
0x180010eb2  mov     rcx, [rdi+18h]
0x180010eb6  lea     rax, [rcx+10h]
0x180010eba  mov     [rcx+8], rax
0x180010ebe  mov     rax, [rdi+18h]
0x180010ec2  mov     rcx, [rax+8]
0x180010ec6  movups  xmm0, xmmword ptr [r14]
0x180010eca  movdqu  xmmword ptr [rcx], xmm0
0x180010ece  mov     rcx, r15; BindingVector
0x180010ed1  call    cs:__imp_RpcServerInqBindings
0x180010ed7  mov     esi, eax
0x180010ed9  test    eax, eax
0x180010edb  jz      short loc_180010F35
0x180010edd  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ee4  test    byte ptr [rcx+1Ch], 8
0x180010ee8  jz      short loc_180010F08
0x180010eea  cmp     byte ptr [rcx+19h], 2
0x180010eee  jb      short loc_180010F08
0x180010ef0  mov     edx, 1Eh
0x180010ef5  mov     r9d, eax
0x180010ef8  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180010eff  mov     rcx, [rcx+10h]
0x180010f03  call    WPP_SF_d
0x180010f08  xorps   xmm0, xmm0
0x180010f0b  movups  [rbp+var_28], xmm0
0x180010f0f  mov     [rbp+var_18], 1
0x180010f16  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180010f1d  mov     [rbp+pExceptionObject], rax
0x180010f21  mov     [rbp+var_10], esi
0x180010f24  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180010f2b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010f2f  call    _CxxThrowException_0
0x180010f35  xor     r9d, r9d; Annotation
0x180010f38  mov     r8, [rdi+18h]; UuidVector
0x180010f3c  mov     rdx, [r15]; BindingVector
0x180010f3f  mov     rcx, [rdi]; IfSpec
0x180010f42  call    cs:__imp_RpcEpRegisterW
0x180010f48  mov     esi, eax
0x180010f4a  test    eax, eax
0x180010f4c  jz      short loc_180010FAF
0x180010f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f55  test    byte ptr [rcx+1Ch], 8
0x180010f59  jz      short loc_180010F79
0x180010f5b  cmp     byte ptr [rcx+19h], 2
0x180010f5f  jb      short loc_180010F79
0x180010f61  mov     edx, 1Fh
0x180010f66  mov     r9d, eax
0x180010f69  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180010f70  mov     rcx, [rcx+10h]
0x180010f74  call    WPP_SF_d
0x180010f79  mov     rcx, r15; BindingVector
0x180010f7c  call    cs:__imp_RpcBindingVectorFree
0x180010f82  xorps   xmm0, xmm0
0x180010f85  movups  [rbp+var_28], xmm0
0x180010f89  mov     [rbp+var_18], 1
0x180010f90  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180010f97  mov     [rbp+pExceptionObject], rax
0x180010f9b  mov     [rbp+var_10], esi
0x180010f9e  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180010fa5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010fa9  call    _CxxThrowException_0
0x180010faf  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180010fb3  call    cs:__imp_LocalFree
0x180010fb9  mov     rax, rdi
0x180010fbc  mov     rsi, [rsp+50h+arg_0]
0x180010fc1  mov     rdi, [rsp+50h+arg_8]
0x180010fc6  add     rsp, 50h
0x180010fca  pop     r15
0x180010fcc  pop     r14
0x180010fce  pop     rbp
0x180010fcf  retn
```
