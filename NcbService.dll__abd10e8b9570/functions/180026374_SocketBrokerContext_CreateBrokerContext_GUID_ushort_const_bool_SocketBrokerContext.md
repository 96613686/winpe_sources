# SocketBrokerContext::CreateBrokerContext(_GUID *,ushort const *,bool,SocketBrokerContext * *)

- ea: `0x180026374`
- end: `0x180026487`
- name: `?CreateBrokerContext@SocketBrokerContext@@SAKPEAU_GUID@@PEBG_NPEAPEAV1@@Z`
- size: `275`
- prototype: `__int64 __fastcall(struct _GUID *, const unsigned __int16 *, char, struct SocketBrokerContext **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018670`

## callees

- `0x180001ebc`
- `0x18000a0a0`
- `0x18000e380`
- `0x18001dd2c`
- `0x1800261d8`
- `0x180026374`
- `0x180026724`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180026450`
- `ntdll!RtlPublishWnfStateData` at `0x180026450`

## string_xrefs

- `0x1800263d3`: `CreateBrokerContext: Failed to allocate Socket Broker Context`
- `0x18002640d`: `CreateBrokerContext: Failed to initialize broker context`
- `0x180026466`: `CreateBrokerContext: Failed to publish WNF_NCB_APP_AVAILABLE event. Ignore`

## pseudocode

```c
__int64 __fastcall SocketBrokerContext::CreateBrokerContext(
        struct _GUID *a1,
        const unsigned __int16 *a2,
        char a3,
        struct SocketBrokerContext **a4)
{
  SocketBrokerContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  SocketBrokerContext *v11; // rdi
  unsigned int v12; // ebx
  __int64 v13; // r9
  const wchar_t *v14; // r8
  unsigned int v15; // eax
  __int64 v16; // rdx
  SocketBrokerTable *v17; // rcx
  int v18; // eax
  SocketBrokerContext *v20; // [rsp+30h] [rbp-28h]
  int v21; // [rsp+78h] [rbp+20h] BYREF

  v21 = 0;
  *a4 = 0;
  v20 = (SocketBrokerContext *)operator new(0x98u);
  v8 = SocketBrokerContext::SocketBrokerContext(v20);
  v11 = v8;
  if ( v8 )
  {
    v15 = SocketBrokerContext::Initialize(v8, a1, a2);
    v12 = v15;
    if ( v15 || (v15 = SocketBrokerTable::Add(v17, v11), (v12 = v15) != 0) )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v17, v16, L"CreateBrokerContext: Failed to initialize broker context", v15);
      SocketBrokerContext::ReleaseRef(v11);
    }
    else
    {
      *a4 = v11;
      if ( !a3 )
      {
        v21 = 1;
        v18 = RtlPublishWnfStateData(WNF_NCB_APP_AVAILABLE, 0, &v21, 4, 0);
        if ( v18 < 0 && (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        {
          v13 = (unsigned int)v18;
          v14 = L"CreateBrokerContext: Failed to publish WNF_NCB_APP_AVAILABLE event. Ignore";
          goto LABEL_13;
        }
      }
    }
  }
  else
  {
    v12 = 8;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      v13 = 8;
      v14 = L"CreateBrokerContext: Failed to allocate Socket Broker Context";
LABEL_13:
      McTemplateU0zq_EventWriteTransfer(v10, v9, v14, v13);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180026374  mov     [rsp+arg_0], rbx
0x180026379  mov     [rsp+arg_8], rbp
0x18002637e  push    rsi
0x18002637f  push    rdi
0x180026380  push    r14
0x180026382  sub     rsp, 40h
0x180026386  mov     rsi, r9
0x180026389  mov     bpl, r8b
0x18002638c  mov     rbx, rdx
0x18002638f  mov     r14, rcx
0x180026392  mov     [rsp+58h+arg_18], 0
0x18002639a  mov     qword ptr [r9], 0
0x1800263a1  mov     ecx, 98h; Size
0x1800263a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800263ab  mov     [rsp+58h+var_28], rax
0x1800263b0  mov     rcx, rax; this
0x1800263b3  call    ??0SocketBrokerContext@@QEAA@XZ; SocketBrokerContext::SocketBrokerContext(void)
0x1800263b8  mov     rdi, rax
0x1800263bb  test    rax, rax
0x1800263be  jnz     short loc_1800263DF
0x1800263c0  lea     ebx, [rax+8]
0x1800263c3  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800263ca  jz      loc_180026472
0x1800263d0  mov     r9d, ebx
0x1800263d3  lea     r8, aCreatebrokerco; "CreateBrokerContext: Failed to allocate"...
0x1800263da  jmp     loc_18002646D
0x1800263df  mov     r8, rbx; unsigned __int16 *
0x1800263e2  mov     rdx, r14; struct _GUID *
0x1800263e5  mov     rcx, rdi; this
0x1800263e8  call    ?Initialize@SocketBrokerContext@@QEAAKPEAU_GUID@@PEBG@Z; SocketBrokerContext::Initialize(_GUID *,ushort const *)
0x1800263ed  mov     ebx, eax
0x1800263ef  test    eax, eax
0x1800263f1  jnz     short loc_180026401
0x1800263f3  mov     rdx, rdi; struct SocketBrokerContext *
0x1800263f6  call    ?Add@SocketBrokerTable@@QEAAKPEAVSocketBrokerContext@@@Z; SocketBrokerTable::Add(SocketBrokerContext *)
0x1800263fb  mov     ebx, eax
0x1800263fd  test    eax, eax
0x1800263ff  jz      short loc_180026423
0x180026401  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180026408  jz      short loc_180026419
0x18002640a  mov     r9d, eax
0x18002640d  lea     r8, aCreatebrokerco_0; "CreateBrokerContext: Failed to initiali"...
0x180026414  call    McTemplateU0zq_EventWriteTransfer
0x180026419  mov     rcx, rdi; this
0x18002641c  call    ?ReleaseRef@SocketBrokerContext@@QEAAXXZ; SocketBrokerContext::ReleaseRef(void)
0x180026421  jmp     short loc_180026472
0x180026423  mov     [rsi], rdi
0x180026426  test    bpl, bpl
0x180026429  jnz     short loc_180026472
0x18002642b  mov     [rsp+58h+arg_18], 1
0x180026433  mov     [rsp+58h+var_38], 0
0x18002643c  mov     r9d, 4
0x180026442  lea     r8, [rsp+58h+arg_18]
0x180026447  xor     edx, edx
0x180026449  mov     rcx, cs:WNF_NCB_APP_AVAILABLE
0x180026450  call    cs:__imp_RtlPublishWnfStateData
0x180026456  test    eax, eax
0x180026458  jns     short loc_180026472
0x18002645a  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180026461  jz      short loc_180026472
0x180026463  mov     r9d, eax
0x180026466  lea     r8, aCreatebrokerco_1; "CreateBrokerContext: Failed to publish "...
0x18002646d  call    McTemplateU0zq_EventWriteTransfer
0x180026472  mov     eax, ebx
0x180026474  mov     rbx, [rsp+58h+arg_0]
0x180026479  mov     rbp, [rsp+58h+arg_8]
0x18002647e  add     rsp, 40h
0x180026482  pop     r14
0x180026484  pop     rdi
0x180026485  pop     rsi
0x180026486  retn
```
