# ReceiveTextMessageTask::CreateInstance(Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *,ITransportTaskCallback *,ReceiveTextMessageTask * *)

- ea: `0x180007c48`
- end: `0x180007d44`
- name: `?CreateInstance@ReceiveTextMessageTask@@SAJPEAUISmsMessageReceivedTriggerDetails@Sms@Devices@Windows@@PEAUITransportTaskCallback@@PEAPEAV1@@Z`
- size: `252`
- prototype: `__int64 __fastcall(struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *, struct ITransportTaskCallback *, struct ReceiveTextMessageTask **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007594`

## callees

- `0x180001730`
- `0x1800044dc`
- `0x180007c48`
- `0x180008d68`
- `0x18000c010`

## string_xrefs

- `0x180007d23`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`

## pseudocode

```c
__int64 __fastcall ReceiveTextMessageTask::CreateInstance(
        struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *a1,
        struct ITransportTaskCallback *a2,
        struct ReceiveTextMessageTask **a3)
{
  char *v6; // rax
  ReceiveTextMessageTask *v7; // rbx
  struct ATL::CAtlModule *v8; // rcx
  int v9; // edi
  __int64 v10; // rax

  *a3 = 0;
  v6 = (char *)operator new(0x30u);
  v7 = (ReceiveTextMessageTask *)v6;
  if ( v6 )
  {
    *(_QWORD *)(v6 + 12) = 0;
    *((_DWORD *)v6 + 5) = 0;
    v8 = ATL::_pAtlModule;
    *((_DWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 3) = 0;
    *((_QWORD *)v6 + 4) = 0;
    *((_QWORD *)v6 + 5) = 0;
    *(_QWORD *)v6 = &ATL::CComObject<ReceiveTextMessageTask>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v8 + 8LL))(v8);
    (*(void (__fastcall **)(ReceiveTextMessageTask *))(*(_QWORD *)v7 + 8LL))(v7);
    v9 = ReceiveTextMessageTask::_Initialize(v7, a1, a2);
    v10 = *(_QWORD *)v7;
    if ( v9 >= 0 )
    {
      (*(void (__fastcall **)(ReceiveTextMessageTask *))(v10 + 8))(v7);
      *a3 = v7;
      (*(void (__fastcall **)(ReceiveTextMessageTask *))(*(_QWORD *)v7 + 16LL))(v7);
      return 0;
    }
    (*(void (__fastcall **)(ReceiveTextMessageTask *))(v10 + 16))(v7);
  }
  else
  {
    v9 = -2147024882;
  }
  Log_HREvent_0(
    (unsigned int)v9,
    1,
    "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007c48  mov     [rsp+arg_18], rbx
0x180007c4d  push    rbp
0x180007c4e  push    rsi
0x180007c4f  push    rdi
0x180007c50  sub     rsp, 30h
0x180007c54  mov     rdi, rcx
0x180007c57  mov     qword ptr [r8], 0
0x180007c5e  mov     ecx, 30h ; '0'; Size
0x180007c63  mov     rsi, r8
0x180007c66  mov     rbp, rdx
0x180007c69  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007c6e  mov     rbx, rax
0x180007c71  test    rax, rax
0x180007c74  jz      loc_180007D18
0x180007c7a  mov     qword ptr [rax+0Ch], 0
0x180007c82  mov     dword ptr [rax+14h], 0
0x180007c89  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007c90  mov     dword ptr [rax+8], 0
0x180007c97  mov     qword ptr [rax+18h], 0
0x180007c9f  mov     qword ptr [rax+20h], 0
0x180007ca7  mov     qword ptr [rax+28h], 0
0x180007caf  lea     rax, ??_7?$CComObject@VReceiveTextMessageTask@@@ATL@@6B@; const ATL::CComObject<ReceiveTextMessageTask>::`vftable'
0x180007cb6  mov     [rbx], rax
0x180007cb9  mov     r9, [rcx]
0x180007cbc  mov     rax, [r9+8]
0x180007cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cc5  mov     rax, [rbx]
0x180007cc8  mov     rcx, rbx
0x180007ccb  mov     rax, [rax+8]
0x180007ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cd4  mov     r8, rbp; struct ITransportTaskCallback *
0x180007cd7  mov     rdx, rdi; struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *
0x180007cda  mov     rcx, rbx; this
0x180007cdd  call    ?_Initialize@ReceiveTextMessageTask@@AEAAJPEAUISmsMessageReceivedTriggerDetails@Sms@Devices@Windows@@PEAUITransportTaskCallback@@@Z; ReceiveTextMessageTask::_Initialize(Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *,ITransportTaskCallback *)
0x180007ce2  mov     edi, eax
0x180007ce4  test    eax, eax
0x180007ce6  mov     rax, [rbx]
0x180007ce9  mov     rcx, rbx
0x180007cec  jns     short loc_180007CF9
0x180007cee  mov     rax, [rax+10h]
0x180007cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cf7  jmp     short loc_180007D1D
0x180007cf9  mov     rax, [rax+8]
0x180007cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d02  mov     [rsi], rbx
0x180007d05  mov     rcx, rbx
0x180007d08  mov     rax, [rbx]
0x180007d0b  mov     rax, [rax+10h]
0x180007d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d14  xor     eax, eax
0x180007d16  jmp     short loc_180007D37
0x180007d18  mov     edi, 8007000Eh
0x180007d1d  mov     r9d, 0Bh
0x180007d23  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180007d2a  mov     ecx, edi
0x180007d2c  lea     edx, [r9-0Ah]
0x180007d30  call    Log_HREvent_0
0x180007d35  mov     eax, edi
0x180007d37  mov     rbx, [rsp+48h+arg_18]
0x180007d3c  add     rsp, 30h
0x180007d40  pop     rdi
0x180007d41  pop     rsi
0x180007d42  pop     rbp
0x180007d43  retn
```
