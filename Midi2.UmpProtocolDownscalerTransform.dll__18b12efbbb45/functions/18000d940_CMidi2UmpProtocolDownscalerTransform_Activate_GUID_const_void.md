# CMidi2UmpProtocolDownscalerTransform::Activate(_GUID const &,void * *)

- ea: `0x18000d940`
- end: `0x18000db97`
- name: `?Activate@CMidi2UmpProtocolDownscalerTransform@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `599`
- prototype: `__int64 __fastcall(CMidi2UmpProtocolDownscalerTransform *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000163c`
- `0x180002e70`
- `0x1800033bc`
- `0x180008924`
- `0x18000a798`
- `0x18000d940`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000da8d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000da8d`

## string_xrefs

- `0x18000d982`: `avcore\midi2\transform\umpprotocoldownscaler\midi2.umpprotocoldownscalermiditransform.cpp`
- `0x18000db37`: `avcore\midi2\transform\umpprotocoldownscaler\midi2.umpprotocoldownscalermiditransform.cpp`
- `0x18000d9f2`: `CMidi2UmpProtocolDownscalerTransform::Activate`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMidi2UmpProtocolDownscalerTransform::Activate(
        CMidi2UmpProtocolDownscalerTransform *this,
        const struct _GUID *a2,
        void **a3)
{
  _DWORD *v6; // rcx
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // edi
  int v10; // [rsp+20h] [rbp-39h]
  void *v11; // [rsp+30h] [rbp-29h] BYREF
  CMidi2UmpProtocolDownscalerTransform *v12; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+40h] [rbp-19h] BYREF
  const char *v14; // [rsp+60h] [rbp+7h]
  __int64 v15; // [rsp+68h] [rbp+Fh]
  CMidi2UmpProtocolDownscalerTransform **v16; // [rsp+70h] [rbp+17h]
  __int64 v17; // [rsp+78h] [rbp+1Fh]
  const wchar_t *v18; // [rsp+80h] [rbp+27h]
  __int64 v19; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x149,
      (unsigned int)"avcore\\midi2\\transform\\umpprotocoldownscaler\\midi2.umpprotocoldownscalermiditransform.cpp",
      (const char *)0x80070057LL,
      v10);
    return 2147942487LL;
  }
  if ( *(_QWORD *)&GUID_5d2400f0_f2ee_4a51_a3be_0ac9a19c09c4.Data1 != *(_QWORD *)&a2->Data1
    || *(_QWORD *)GUID_5d2400f0_f2ee_4a51_a3be_0ac9a19c09c4.Data4 != *(_QWORD *)a2->Data4 )
  {
    return 2147500034LL;
  }
  v6 = (_DWORD *)*((_QWORD *)MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v12 = this;
    v18 = L"IMidiDataTransform";
    v19 = 38;
    v16 = &v12;
    v17 = 8;
    v14 = "CMidi2UmpProtocolDownscalerTransform::Activate";
    v15 = 47;
    tlgWriteTransfer_EventWriteTransfer((__int64)v6, (unsigned __int8 *)word_1800171BA, 0, 0, 5u, &v13);
  }
  v11 = 0;
  v7 = operator new(0xD0u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    v7[3] = 1;
    *(_QWORD *)v7 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiDataTransform>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v8 = &CMidi2UmpProtocolDownscalerMidiTransform::`vftable';
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v8 + 4), 0, 0);
    *((_BYTE *)v8 + 64) = 0;
    *(_QWORD *)(v8 + 17) = 0;
    *(_QWORD *)(v8 + 19) = 0;
    *(_QWORD *)(v8 + 21) = 0;
    v8[23] = 0;
    v8[24] = 1;
    *(_OWORD *)(v8 + 26) = 0;
    *((_QWORD *)v8 + 15) = 0;
    *((_QWORD *)v8 + 16) = 7;
    *((_WORD *)v8 + 52) = 0;
    *((_QWORD *)v8 + 17) = 0;
    *((_QWORD *)v8 + 19) = 0;
    *((_QWORD *)v8 + 20) = 0;
    *((_QWORD *)v8 + 21) = 0;
    *((_QWORD *)v8 + 22) = 0;
    *((_QWORD *)v8 + 23) = 0;
    *((_QWORD *)v8 + 24) = 0;
    *((_QWORD *)v8 + 25) = 0;
    v9 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, void **))v8)(
           v8,
           &GUID_5d2400f0_f2ee_4a51_a3be_0ac9a19c09c4,
           &v11);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v9 >= 0 )
    {
      *a3 = v11;
      return 0;
    }
  }
  else
  {
    v9 = -2147024882;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x157,
    (unsigned int)"avcore\\midi2\\transform\\umpprotocoldownscaler\\midi2.umpprotocoldownscalermiditransform.cpp",
    (const char *)(unsigned int)v9,
    v10);
  if ( v11 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000d940  mov     [rsp-8+arg_0], rbx
0x18000d945  mov     [rsp-8+arg_8], rsi
0x18000d94a  push    rbp
0x18000d94b  push    rdi
0x18000d94c  push    r14
0x18000d94e  lea     rbp, [rsp-47h]
0x18000d953  sub     rsp, 0A0h
0x18000d95a  mov     rax, cs:__security_cookie
0x18000d961  xor     rax, rsp
0x18000d964  mov     [rbp+57h+var_20], rax
0x18000d968  mov     rsi, r8
0x18000d96b  mov     rbx, rcx
0x18000d96e  xor     r14d, r14d
0x18000d971  test    r8, r8
0x18000d974  jnz     short loc_18000D99A
0x18000d976  mov     rcx, [rbp+5Fh]; this
0x18000d97a  mov     ebx, 80070057h
0x18000d97f  mov     r9d, ebx; char *
0x18000d982  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transform\\umpprotocoldo"...
0x18000d989  mov     edx, 149h; void *
0x18000d98e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d993  mov     eax, ebx
0x18000d995  jmp     loc_18000DB73
0x18000d99a  mov     rax, qword ptr cs:_GUID_5d2400f0_f2ee_4a51_a3be_0ac9a19c09c4.Data1
0x18000d9a1  cmp     rax, [rdx]
0x18000d9a4  jnz     loc_18000DB6E
0x18000d9aa  mov     rax, qword ptr cs:_GUID_5d2400f0_f2ee_4a51_a3be_0ac9a19c09c4.Data4
0x18000d9b1  cmp     rax, [rdx+8]
0x18000d9b5  jnz     loc_18000DB6E
0x18000d9bb  call    ?Instance@MidiUmpProtocolDownscalerTransformTelemetryProvider@@KAPEAV1@XZ; MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance(void)
0x18000d9c0  mov     rcx, [rax+8]
0x18000d9c4  mov     eax, [rcx]
0x18000d9c6  cmp     eax, 4
0x18000d9c9  jbe     short loc_18000DA29
0x18000d9cb  mov     [rbp+57h+var_78], rbx
0x18000d9cf  lea     rax, aImididatatrans; "IMidiDataTransform"
0x18000d9d6  mov     [rbp+57h+var_30], rax
0x18000d9da  mov     [rbp+57h+var_28], 26h ; '&'
0x18000d9e2  lea     rax, [rbp+57h+var_78]
0x18000d9e6  mov     [rbp+57h+var_40], rax
0x18000d9ea  mov     [rbp+57h+var_38], 8
0x18000d9f2  lea     rax, aCmidi2umpproto_2; "CMidi2UmpProtocolDownscalerTransform::A"...
0x18000d9f9  mov     [rbp+57h+var_50], rax
0x18000d9fd  mov     [rbp+57h+var_48], 2Fh ; '/'
0x18000da05  lea     rax, [rbp+57h+var_70]
0x18000da09  mov     [rsp+0B0h+var_88], rax
0x18000da0e  mov     [rsp+0B0h+var_90], 5; int
0x18000da16  xor     r9d, r9d
0x18000da19  xor     r8d, r8d
0x18000da1c  lea     rdx, word_1800171BA
0x18000da23  call    _tlgWriteTransfer_EventWriteTransfer
0x18000da28  nop
0x18000da29  mov     [rbp+57h+var_80], r14
0x18000da2d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000da34  mov     ecx, 0D0h; unsigned __int64
0x18000da39  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000da3e  mov     rbx, rax
0x18000da41  test    rax, rax
0x18000da44  jnz     short loc_18000DA50
0x18000da46  mov     edi, 8007000Eh
0x18000da4b  jmp     loc_18000DB30
0x18000da50  mov     dword ptr [rax+0Ch], 1
0x18000da57  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiDataTransform@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiDataTransform>::`vftable'
0x18000da5e  mov     [rbx], rax
0x18000da61  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000da68  test    rcx, rcx
0x18000da6b  jz      short loc_18000DA7A
0x18000da6d  mov     rax, [rcx]
0x18000da70  mov     rax, [rax+8]
0x18000da74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da79  nop
0x18000da7a  lea     rax, ??_7CMidi2UmpProtocolDownscalerMidiTransform@@6B@; const CMidi2UmpProtocolDownscalerMidiTransform::`vftable'
0x18000da81  mov     [rbx], rax
0x18000da84  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000da88  xor     r8d, r8d; Flags
0x18000da8b  xor     edx, edx; dwSpinCount
0x18000da8d  call    cs:__imp_InitializeCriticalSectionEx
0x18000da93  mov     [rbx+40h], r14b
0x18000da97  mov     [rbx+44h], r14
0x18000da9b  mov     [rbx+4Ch], r14
0x18000da9f  mov     [rbx+54h], r14
0x18000daa3  mov     [rbx+5Ch], r14d
0x18000daa7  mov     dword ptr [rbx+60h], 1
0x18000daae  xorps   xmm0, xmm0
0x18000dab1  movups  xmmword ptr [rbx+68h], xmm0
0x18000dab5  mov     [rbx+78h], r14
0x18000dab9  mov     qword ptr [rbx+80h], 7
0x18000dac4  mov     [rbx+68h], r14w
0x18000dac9  mov     [rbx+88h], r14
0x18000dad0  mov     [rbx+98h], r14
0x18000dad7  mov     [rbx+0A0h], r14
0x18000dade  mov     [rbx+0A8h], r14
0x18000dae5  mov     [rbx+0B0h], r14
0x18000daec  mov     [rbx+0B8h], r14
0x18000daf3  mov     [rbx+0C0h], r14
0x18000dafa  mov     [rbx+0C8h], r14
0x18000db01  mov     rax, [rbx]
0x18000db04  lea     r8, [rbp+57h+var_80]
0x18000db08  lea     rdx, _GUID_5d2400f0_f2ee_4a51_a3be_0ac9a19c09c4
0x18000db0f  mov     rcx, rbx
0x18000db12  mov     rax, [rax]
0x18000db15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db1a  mov     edi, eax
0x18000db1c  mov     rax, [rbx]
0x18000db1f  mov     rcx, rbx
0x18000db22  mov     rax, [rax+10h]
0x18000db26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db2b  nop
0x18000db2c  test    edi, edi
0x18000db2e  jns     short loc_18000DB63
0x18000db30  mov     rcx, [rbp+5Fh]; this
0x18000db34  mov     r9d, edi; char *
0x18000db37  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transform\\umpprotocoldo"...
0x18000db3e  mov     edx, 157h; void *
0x18000db43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db48  nop
0x18000db49  mov     rcx, [rbp+57h+var_80]
0x18000db4d  test    rcx, rcx
0x18000db50  jz      short loc_18000DB5F
0x18000db52  mov     rdx, [rcx]
0x18000db55  mov     rax, [rdx+10h]
0x18000db59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db5e  nop
0x18000db5f  mov     eax, edi
0x18000db61  jmp     short loc_18000DB73
0x18000db63  mov     rax, [rbp+57h+var_80]
0x18000db67  mov     [rsi], rax
0x18000db6a  xor     eax, eax
0x18000db6c  jmp     short loc_18000DB73
0x18000db6e  mov     eax, 80004002h
0x18000db73  mov     rcx, [rbp+57h+var_20]
0x18000db77  xor     rcx, rsp; StackCookie
0x18000db7a  call    __security_check_cookie
0x18000db7f  lea     r11, [rsp+0B0h+var_10]
0x18000db87  mov     rbx, [r11+20h]
0x18000db8b  mov     rsi, [r11+28h]
0x18000db8f  mov     rsp, r11
0x18000db92  pop     r14
0x18000db94  pop     rdi
0x18000db95  pop     rbp
0x18000db96  retn
```
