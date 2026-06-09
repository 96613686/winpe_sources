# CMidi2LoopbackMidiConfigurationManager::Initialize(_GUID,IMidiDeviceManager *,IMidiServiceConfigurationManager *)

- ea: `0x1800171d0`
- end: `0x1800172cd`
- name: `?Initialize@CMidi2LoopbackMidiConfigurationManager@@UEAAJU_GUID@@PEAUIMidiDeviceManager@@PEAUIMidiServiceConfigurationManager@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(CMidi2LoopbackMidiConfigurationManager *__hidden this, struct _GUID *__struct_ptr, struct IMidiDeviceManager *, struct IMidiServiceConfigurationManager *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180001a38`
- `0x18000a024`
- `0x18000ccd8`
- `0x1800171d0`
- `0x180032010`

## string_xrefs

- `0x180017200`: `CMidi2LoopbackMidiConfigurationManager::Initialize`
- `0x18001723e`: `avcore\midi2\transport\loopbackmiditransport\midi2.loopbackmidiconfigurationmanager.cpp`
- `0x18001729a`: `avcore\midi2\transport\loopbackmiditransport\midi2.loopbackmidiconfigurationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2LoopbackMidiConfigurationManager::Initialize(
        CMidi2LoopbackMidiConfigurationManager *this,
        struct _GUID *a2,
        __int64 (__fastcall ***a3)(struct IMidiDeviceManager *, GUID *, char *),
        struct IMidiServiceConfigurationManager *a4)
{
  _DWORD *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  __int64 (__fastcall *v11)(struct IMidiDeviceManager *, GUID *, char *); // r14
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // edi
  int v15; // [rsp+20h] [rbp-38h]
  int v16[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  CMidi2LoopbackMidiConfigurationManager *v18; // [rsp+70h] [rbp+18h] BYREF

  v7 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v7 > 4u )
  {
    v18 = this;
    *(_QWORD *)v16 = "CMidi2LoopbackMidiConfigurationManager::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v7,
      (unsigned int)byte_1800583C5,
      v8,
      v9,
      (__int64)v16,
      (__int64)&v18);
  }
  if ( a3 )
  {
    v11 = **a3;
    v12 = *((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = 0;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v13 = v11((struct IMidiDeviceManager *)a3, &GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f, (char *)this + 16);
    v14 = v13;
    if ( v13 >= 0 )
    {
      *(struct _GUID *)((char *)this + 24) = *a2;
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22,
        (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiconfigurationmanager.cpp",
        (const char *)(unsigned int)v13,
        v15);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiconfigurationmanager.cpp",
      (const char *)0x80070057LL,
      v15);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800171d0  mov     [rsp+arg_0], rbx
0x1800171d5  mov     [rsp+arg_8], rbp
0x1800171da  push    rsi
0x1800171db  push    rdi
0x1800171dc  push    r14
0x1800171de  sub     rsp, 40h
0x1800171e2  mov     rsi, r8
0x1800171e5  mov     rbp, rdx
0x1800171e8  mov     rbx, rcx
0x1800171eb  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x1800171f0  mov     rcx, [rax+8]
0x1800171f4  mov     eax, [rcx]
0x1800171f6  cmp     eax, 4
0x1800171f9  jbe     short loc_18001722C
0x1800171fb  mov     [rsp+58h+arg_10], rbx
0x180017200  lea     rax, aCmidi2loopback_12; "CMidi2LoopbackMidiConfigurationManager:"...
0x180017207  mov     qword ptr [rsp+58h+var_28], rax
0x18001720c  lea     rax, [rsp+58h+arg_10]
0x180017211  mov     [rsp+58h+var_30], rax
0x180017216  lea     rax, [rsp+58h+var_28]
0x18001721b  mov     qword ptr [rsp+58h+var_38], rax; int
0x180017220  lea     rdx, byte_1800583C5
0x180017227  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001722c  test    rsi, rsi
0x18001722f  jnz     short loc_180017251
0x180017231  mov     rcx, [rsp+58h]; this
0x180017236  mov     ebx, 80070057h
0x18001723b  mov     r9d, ebx; char *
0x18001723e  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transport\\loopbackmidit"...
0x180017245  lea     edx, [rsi+21h]; void *
0x180017248  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001724d  mov     eax, ebx
0x18001724f  jmp     short loc_1800172BA
0x180017251  mov     rax, [rsi]
0x180017254  mov     r14, [rax]
0x180017257  lea     rdi, [rbx+10h]
0x18001725b  mov     rcx, [rdi]
0x18001725e  mov     qword ptr [rdi], 0
0x180017265  test    rcx, rcx
0x180017268  jz      short loc_180017277
0x18001726a  mov     rdx, [rcx]
0x18001726d  mov     rax, [rdx+10h]
0x180017271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017276  nop
0x180017277  mov     r8, rdi
0x18001727a  lea     rdx, _GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f
0x180017281  mov     rcx, rsi
0x180017284  mov     rax, r14
0x180017287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001728c  mov     edi, eax
0x18001728e  test    eax, eax
0x180017290  jns     short loc_1800172AF
0x180017292  mov     rcx, [rsp+58h]; this
0x180017297  mov     r9d, eax; char *
0x18001729a  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transport\\loopbackmidit"...
0x1800172a1  mov     edx, 22h ; '"'; void *
0x1800172a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800172ab  mov     eax, edi
0x1800172ad  jmp     short loc_1800172BA
0x1800172af  movups  xmm0, xmmword ptr [rbp+0]
0x1800172b3  movdqu  xmmword ptr [rbx+18h], xmm0
0x1800172b8  xor     eax, eax
0x1800172ba  mov     rbx, [rsp+58h+arg_0]
0x1800172bf  mov     rbp, [rsp+58h+arg_8]
0x1800172c4  add     rsp, 40h
0x1800172c8  pop     r14
0x1800172ca  pop     rdi
0x1800172cb  pop     rsi
0x1800172cc  retn
```
