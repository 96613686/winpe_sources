# ??$_Invoke@V?$tuple@P8CMidiEndpointProtocolWorker@@EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001@@@_EV?$shared_ptr@VCMidiEndpointProtocolWorker@@@std@@U2@@std@@$0A@$00$01@thread@std@@CAIPEAX@Z

- ea: `0x140036170`
- end: `0x1400361bb`
- name: `??$_Invoke@V?$tuple@P8CMidiEndpointProtocolWorker@@EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001@@@_EV?$shared_ptr@VCMidiEndpointProtocolWorker@@@std@@U2@@std@@$0A@$00$01@thread@std@@CAIPEAX@Z`
- size: `75`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140036614`
- `0x14005a010`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x1400361a4`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x1400361a4`

## pseudocode

```c
__int64 __fastcall ____Invoke_V__tuple_P8CMidiEndpointProtocolWorker__EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001____EV__shared_ptr_VCMidiEndpointProtocolWorker___std__U2__std___0A__00_01_thread_std__CAIPEAX_Z(
        __int64 *a1)
{
  __int64 v2; // [rsp+20h] [rbp-18h] BYREF
  int v3; // [rsp+28h] [rbp-10h]
  __int64 *v4; // [rsp+40h] [rbp+8h] BYREF

  v4 = a1;
  v2 = *a1;
  v3 = *((_DWORD *)a1 + 2);
  ((void (__fastcall *)(__int64, __int64 *))a1[4])(a1[2] + *((int *)a1 + 10), &v2);
  _Cnd_do_broadcast_at_thread_exit();
  __1__unique_ptr_V__tuple_P8CMidiEndpointProtocolWorker__EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001____EV__shared_ptr_VCMidiEndpointProtocolWorker___std__U2__std__U__default_delete_V__tuple_P8CMidiEndpointProtocolWorker__EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001____EV__shared_ptr_VCMidiEndpointProtocolWorker___std__U2__std___2__std__QEAA_XZ(&v4);
  return 0;
}

```

## disassembly

```asm
0x140036170  sub     rsp, 38h
0x140036174  mov     r8, rcx
0x140036177  mov     [rsp+38h+arg_0], rcx
0x14003617c  movsd   xmm0, qword ptr [rcx]
0x140036180  movsd   [rsp+38h+var_18], xmm0
0x140036186  mov     eax, [rcx+8]
0x140036189  mov     [rsp+38h+var_10], eax
0x14003618d  movsxd  rcx, dword ptr [rcx+28h]
0x140036191  add     rcx, [r8+10h]
0x140036195  lea     rdx, [rsp+38h+var_18]
0x14003619a  mov     rax, [r8+20h]
0x14003619e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400361a3  nop
0x1400361a4  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x1400361aa  lea     rcx, [rsp+38h+arg_0]
0x1400361af  call    ??1?$unique_ptr@V?$tuple@P8CMidiEndpointProtocolWorker@@EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001@@@_EV?$shared_ptr@VCMidiEndpointProtocolWorker@@@std@@U2@@std@@U?$default_delete@V?$tuple@P8CMidiEndpointProtocolWorker@@EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001@@@_EV?$shared_ptr@VCMidiEndpointProtocolWorker@@@std@@U2@@std@@@2@@std@@QEAA@XZ
0x1400361b4  xor     eax, eax
0x1400361b6  add     rsp, 38h
0x1400361ba  retn
```
