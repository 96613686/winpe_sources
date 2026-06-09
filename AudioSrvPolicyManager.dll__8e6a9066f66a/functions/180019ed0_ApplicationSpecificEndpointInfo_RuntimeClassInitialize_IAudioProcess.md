# ApplicationSpecificEndpointInfo::RuntimeClassInitialize(IAudioProcess *)

- ea: `0x180019ed0`
- end: `0x180019fe7`
- name: `?RuntimeClassInitialize@ApplicationSpecificEndpointInfo@@QEAAJPEAUIAudioProcess@@@Z`
- size: `279`
- prototype: `int(ApplicationSpecificEndpointInfo *__hidden this, struct IAudioProcess *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180019d24`

## callees

- `0x18000a384`
- `0x180012844`
- `0x1800197d0`
- `0x180019ed0`
- `0x180019ff0`
- `0x18001a134`
- `0x180025db0`
- `0x1800272f8`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019ef9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019f69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019ef9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019f69`
- `RPCRT4!RpcRevertToSelf` at `0x180019fd5`
- `RPCRT4!RpcRevertToSelf` at `0x180019fd5`
- `RPCRT4!RpcImpersonateClient` at `0x180019fa2`
- `RPCRT4!RpcImpersonateClient` at `0x180019fa2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ApplicationSpecificEndpointInfo::RuntimeClassInitialize(
        ApplicationSpecificEndpointInfo *this,
        struct IAudioProcess *a2)
{
  _QWORD *v4; // rsi
  void *v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // edi
  __int64 v10; // rdx
  _QWORD *v12; // rdi
  void *v13; // rsi
  const unsigned __int16 *ApplicationName; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned int v17; // eax
  unsigned int v18; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v20; // [rsp+50h] [rbp+8h] BYREF
  char v21; // [rsp+51h] [rbp+9h]

  v4 = (_QWORD *)((char *)this + 88);
  v5 = (void *)*((_QWORD *)this + 11);
  if ( v5 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v20);
    CoTaskMemFree(v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v20);
  }
  *v4 = 0;
  v6 = (*(__int64 (__fastcall **)(struct IAudioProcess *))(*(_QWORD *)a2 + 56LL))(a2);
  v9 = _AllocString<CTCoAllocPolicy>(v8, v7, v6, v4);
  if ( v9 < 0 )
  {
    v10 = 25;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
      (const char *)(unsigned int)v9,
      v18);
    return (unsigned int)v9;
  }
  v12 = (_QWORD *)((char *)this + 80);
  v13 = (void *)*((_QWORD *)this + 10);
  if ( v13 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v20);
    CoTaskMemFree(v13);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v20);
  }
  *v12 = 0;
  ApplicationName = ApplicationSpecificEndpointInfo::GetApplicationName(a2);
  v9 = _AllocString<CTCoAllocPolicy>(v16, v15, ApplicationName, v12);
  if ( v9 < 0 )
  {
    v10 = 29;
    goto LABEL_5;
  }
  v17 = RpcImpersonateClient(0);
  if ( v17 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x20,
             (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
             (const char *)v17,
             v18);
  v21 = 1;
  ApplicationSpecificEndpointInfo::LoadApplicationDefaultEndpoints(this);
  RpcRevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x180019ed0  push    rbx
0x180019ed2  push    rsi
0x180019ed3  push    rdi
0x180019ed4  push    r14
0x180019ed6  sub     rsp, 28h
0x180019eda  mov     r14, rdx
0x180019edd  mov     rbx, rcx
0x180019ee0  lea     rsi, [rcx+58h]
0x180019ee4  mov     rdi, [rsi]
0x180019ee7  test    rdi, rdi
0x180019eea  jz      short loc_180019F09
0x180019eec  lea     rcx, [rsp+48h+arg_0]; this
0x180019ef1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180019ef6  mov     rcx, rdi; pv
0x180019ef9  call    cs:__imp_CoTaskMemFree
0x180019eff  lea     rcx, [rsp+48h+arg_0]; this
0x180019f04  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180019f09  mov     qword ptr [rsi], 0
0x180019f10  mov     rax, [r14]
0x180019f13  mov     rcx, r14
0x180019f16  mov     rax, [rax+38h]
0x180019f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f1f  mov     r9, rsi
0x180019f22  mov     r8, rax
0x180019f25  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180019f2a  mov     edi, eax
0x180019f2c  test    eax, eax
0x180019f2e  jns     short loc_180019F50
0x180019f30  mov     edx, 19h; void *
0x180019f35  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x180019f3c  mov     r9d, edi; char *
0x180019f3f  mov     rcx, [rsp+48h]; this
0x180019f44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f49  mov     eax, edi
0x180019f4b  jmp     loc_180019FDD
0x180019f50  lea     rdi, [rbx+50h]
0x180019f54  mov     rsi, [rdi]
0x180019f57  test    rsi, rsi
0x180019f5a  jz      short loc_180019F79
0x180019f5c  lea     rcx, [rsp+48h+arg_0]; this
0x180019f61  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180019f66  mov     rcx, rsi; pv
0x180019f69  call    cs:__imp_CoTaskMemFree
0x180019f6f  lea     rcx, [rsp+48h+arg_0]; this
0x180019f74  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180019f79  mov     qword ptr [rdi], 0
0x180019f80  mov     rcx, r14; struct IAudioProcess *
0x180019f83  call    ?GetApplicationName@ApplicationSpecificEndpointInfo@@SAPEBGPEAUIAudioProcess@@@Z; ApplicationSpecificEndpointInfo::GetApplicationName(IAudioProcess *)
0x180019f88  mov     r9, rdi
0x180019f8b  mov     r8, rax
0x180019f8e  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180019f93  mov     edi, eax
0x180019f95  test    eax, eax
0x180019f97  jns     short loc_180019FA0
0x180019f99  mov     edx, 1Dh
0x180019f9e  jmp     short loc_180019F35
0x180019fa0  xor     ecx, ecx; BindingHandle
0x180019fa2  call    cs:__imp_RpcImpersonateClient
0x180019fa8  test    eax, eax
0x180019faa  jz      short loc_180019FC7
0x180019fac  mov     rcx, [rsp+48h]; this
0x180019fb1  mov     r9d, eax; char *
0x180019fb4  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x180019fbb  mov     edx, 20h ; ' '; void *
0x180019fc0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180019fc5  jmp     short loc_180019FDD
0x180019fc7  mov     [rsp+48h+arg_1], 1
0x180019fcc  mov     rcx, rbx; this
0x180019fcf  call    ?LoadApplicationDefaultEndpoints@ApplicationSpecificEndpointInfo@@AEAAJXZ; ApplicationSpecificEndpointInfo::LoadApplicationDefaultEndpoints(void)
0x180019fd4  nop
0x180019fd5  call    cs:__imp_RpcRevertToSelf
0x180019fdb  xor     eax, eax
0x180019fdd  add     rsp, 28h
0x180019fe1  pop     r14
0x180019fe3  pop     rdi
0x180019fe4  pop     rsi
0x180019fe5  pop     rbx
0x180019fe6  retn
```
