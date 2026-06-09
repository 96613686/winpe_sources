# ??$?0P8CMidiEndpointProtocolWorker@@EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001@@@_EAEAV?$shared_ptr@VCMidiEndpointProtocolWorker@@@std@@AEAU1@$0A@@thread@std@@QEAA@$$QEAP8CMidiEndpointProtocolWorker@@EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001@@@_EAEAV?$shared_ptr@VCMidiEndpointProtocolWorker@@@1@AEAU3@@Z

- ea: `0x140035e6c`
- end: `0x140035f37`
- name: `??$?0P8CMidiEndpointProtocolWorker@@EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001@@@_EAEAV?$shared_ptr@VCMidiEndpointProtocolWorker@@@std@@AEAU1@$0A@@thread@std@@QEAA@$$QEAP8CMidiEndpointProtocolWorker@@EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001@@@_EAEAV?$shared_ptr@VCMidiEndpointProtocolWorker@@@1@AEAU3@@Z`
- size: `203`
- prototype: `__int64 __fastcall(__int64, _OWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140036a90`

## callees

- `0x1400054e4`
- `0x140035e6c`
- `0x140036614`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140035f30`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140035f30`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x140035ef8`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x140035ef8`

## pseudocode

```c
__int64 __fastcall ____0P8CMidiEndpointProtocolWorker__EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001____EAEAV__shared_ptr_VCMidiEndpointProtocolWorker___std__AEAU1__0A__thread_std__QEAA___QEAP8CMidiEndpointProtocolWorker__EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001____EAEAV__shared_ptr_VCMidiEndpointProtocolWorker___1_AEAU3__Z(
        __int64 a1,
        _OWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  _DWORD *v8; // r10
  __int64 v9; // rax
  __int64 v10; // rax
  _DWORD *v12; // [rsp+60h] [rbp+8h] BYREF

  v8 = operator new(0x30u);
  *(_QWORD *)v8 = *(_QWORD *)a4;
  v8[2] = *(_DWORD *)(a4 + 8);
  *((_QWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 3) = 0;
  v9 = a3[1];
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
  *((_QWORD *)v8 + 2) = *a3;
  *((_QWORD *)v8 + 3) = a3[1];
  *((_OWORD *)v8 + 2) = *a2;
  v12 = v8;
  v10 = _o__beginthreadex(
          0,
          0,
          ____Invoke_V__tuple_P8CMidiEndpointProtocolWorker__EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001____EV__shared_ptr_VCMidiEndpointProtocolWorker___std__U2__std___0A__00_01_thread_std__CAIPEAX_Z,
          v8,
          0,
          a1 + 8);
  *(_QWORD *)a1 = v10;
  if ( !v10 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x140035F36LL);
  }
  v12 = 0;
  __1__unique_ptr_V__tuple_P8CMidiEndpointProtocolWorker__EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001____EV__shared_ptr_VCMidiEndpointProtocolWorker___std__U2__std__U__default_delete_V__tuple_P8CMidiEndpointProtocolWorker__EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001____EV__shared_ptr_VCMidiEndpointProtocolWorker___std__U2__std___2__std__QEAA_XZ(&v12);
  return a1;
}

```

## disassembly

```asm
0x140035e6c  push    rbx
0x140035e6e  push    rbp
0x140035e6f  push    rsi
0x140035e70  push    rdi
0x140035e71  sub     rsp, 38h
0x140035e75  mov     rbx, r9
0x140035e78  mov     rsi, r8
0x140035e7b  mov     rbp, rdx
0x140035e7e  mov     rdi, rcx
0x140035e81  mov     ecx, 30h ; '0'; Size
0x140035e86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140035e8b  mov     r10, rax
0x140035e8e  movsd   xmm0, qword ptr [rbx]
0x140035e92  movsd   qword ptr [rax], xmm0
0x140035e96  mov     r9d, [rbx+8]
0x140035e9a  mov     [rax+8], r9d
0x140035e9e  mov     qword ptr [rax+10h], 0
0x140035ea6  mov     qword ptr [rax+18h], 0
0x140035eae  mov     rax, [rsi+8]
0x140035eb2  test    rax, rax
0x140035eb5  jz      short loc_140035EBB
0x140035eb7  lock inc dword ptr [rax+8]
0x140035ebb  mov     rax, [rsi]
0x140035ebe  mov     [r10+10h], rax
0x140035ec2  mov     rax, [rsi+8]
0x140035ec6  mov     [r10+18h], rax
0x140035eca  movups  xmm0, xmmword ptr [rbp+0]
0x140035ece  movdqu  xmmword ptr [r10+20h], xmm0
0x140035ed4  mov     [rsp+58h+arg_0], r10
0x140035ed9  lea     rbx, [rdi+8]
0x140035edd  mov     [rsp+58h+var_30], rbx
0x140035ee2  mov     [rsp+58h+var_38], 0
0x140035eea  mov     r9, r10
0x140035eed  lea     r8, ??$_Invoke@V?$tuple@P8CMidiEndpointProtocolWorker@@EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001@@@_EV?$shared_ptr@VCMidiEndpointProtocolWorker@@@std@@U2@@std@@$0A@$00$01@thread@std@@CAIPEAX@Z
0x140035ef4  xor     edx, edx
0x140035ef6  xor     ecx, ecx
0x140035ef8  call    cs:__imp__o__beginthreadex
0x140035efe  mov     [rdi], rax
0x140035f01  test    rax, rax
0x140035f04  jz      short loc_140035F25
0x140035f06  mov     [rsp+58h+arg_0], 0
0x140035f0f  lea     rcx, [rsp+58h+arg_0]
0x140035f14  call    ??1?$unique_ptr@V?$tuple@P8CMidiEndpointProtocolWorker@@EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001@@@_EV?$shared_ptr@VCMidiEndpointProtocolWorker@@@std@@U2@@std@@U?$default_delete@V?$tuple@P8CMidiEndpointProtocolWorker@@EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001@@@_EV?$shared_ptr@VCMidiEndpointProtocolWorker@@@std@@U2@@std@@@2@@std@@QEAA@XZ
0x140035f19  mov     rax, rdi
0x140035f1c  add     rsp, 38h
0x140035f20  pop     rdi
0x140035f21  pop     rsi
0x140035f22  pop     rbp
0x140035f23  pop     rbx
0x140035f24  retn
0x140035f25  mov     dword ptr [rbx], 0
0x140035f2b  mov     ecx, 6
0x140035f30  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
