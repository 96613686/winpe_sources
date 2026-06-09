# Rdp::Avenc::Ic3::CVirtualFrame::GetService(_VirtualVideoFrameTypeService,void * *)

- ea: `0x180059aa0`
- end: `0x180059d76`
- name: `?GetService@CVirtualFrame@Ic3@Avenc@Rdp@@UEAA_NW4_VirtualVideoFrameTypeService@@PEAPEAX@Z`
- size: `726`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x1800058c8`
- `0x1800059f0`
- `0x180006580`
- `0x18000ec04`
- `0x1800444f0`
- `0x180059aa0`
- `0x180059e7c`
- `0x180089010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180059ae5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180059b02`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180059c29`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180059ae5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180059b02`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180059c29`

## string_xrefs

- `0x180059d64`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180059b93`: `Rdp::Avenc::Ic3::CVirtualFrame::GetService`
- `0x180059cd6`: `Rdp::Avenc::Ic3::CVirtualFrame::GetService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Rdp::Avenc::Ic3::CVirtualFrame::GetService(__int64 a1, int a2, __int64 *a3)
{
  Rdp::Avenc::Ic3::CMonitorContext *v7; // rsi
  unsigned __int64 v8; // rbx
  __int64 v9; // rax
  int v10; // r8d
  int v11; // r9d
  Rdp::Avenc::Ic3::CMonitorContext *v12; // rsi
  unsigned __int64 v13; // rbx
  __int64 v14; // rax
  int v15; // r8d
  int v16; // r9d
  int v17; // eax
  int v18; // [rsp+20h] [rbp-49h]
  int v19; // [rsp+60h] [rbp-9h] BYREF
  int v20; // [rsp+64h] [rbp-5h] BYREF
  int v21[2]; // [rsp+68h] [rbp-1h] BYREF
  const char *v22; // [rsp+70h] [rbp+7h] BYREF
  const char *v23; // [rsp+78h] [rbp+Fh] BYREF
  const char *v24; // [rsp+80h] [rbp+17h] BYREF
  __int64 v25; // [rsp+88h] [rbp+1Fh] BYREF
  GUID ActivityId; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  ActivityId = *(GUID *)&xmmword_1800C21A0;
  EventActivityIdControl(4u, &ActivityId);
  if ( a2 )
  {
    if ( a2 != 7 )
    {
      EventActivityIdControl(2u, &ActivityId);
      return 0;
    }
    v7 = *(Rdp::Avenc::Ic3::CMonitorContext **)(a1 + 144);
    if ( v7 )
    {
      v8 = *(_QWORD *)(a1 + 192);
      v9 = (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)(a1 + 16) + 200LL))(**(_QWORD **)(a1 + 16));
      Rdp::Avenc::Ic3::CMonitorContext::OnFirstGraphicsFrame(v7, v9 + *(_QWORD *)(a1 + 80), v8);
    }
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v19 = *(_DWORD *)(a1 + 56);
      v25 = *(_QWORD *)(a1 + 192);
      *(_QWORD *)v21 = *(_QWORD *)(a1 + 80)
                     + (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)(a1 + 16) + 200LL))(**(_QWORD **)(a1 + 16));
      v22 = "FenceGet";
      v23 = "Rdp::Avenc::Ic3::CVirtualFrame::GetService";
      v20 = 265;
      v24 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\virtualframe.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)word_1800B3BBA,
        v10,
        v11,
        (__int64)&v24,
        (__int64)&v20,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)v21,
        (__int64)&v25,
        (__int64)&v19);
    }
    (**(void (__fastcall ***)(__int64))a1)(a1);
    *a3 = (a1 + 8) & -(__int64)(a1 != 0);
  }
  else
  {
    v12 = *(Rdp::Avenc::Ic3::CMonitorContext **)(a1 + 144);
    if ( v12 )
    {
      v13 = *(_QWORD *)(a1 + 192);
      v14 = (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)(a1 + 16) + 200LL))(**(_QWORD **)(a1 + 16));
      Rdp::Avenc::Ic3::CMonitorContext::OnFirstGraphicsFrame(v12, v14 + *(_QWORD *)(a1 + 80), v13);
    }
    Rdp::Avenc::Ic3::CVirtualFrame::WaitForFenceReached((Rdp::Avenc::Ic3::CVirtualFrame *)a1);
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v20 = *(_DWORD *)(a1 + 56);
      v24 = (const char *)(*(_QWORD *)(a1 + 80)
                         + (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)(a1 + 16) + 200LL))(**(_QWORD **)(a1 + 16)));
      v23 = "TextureGet";
      v22 = "Rdp::Avenc::Ic3::CVirtualFrame::GetService";
      v19 = 246;
      *(_QWORD *)v21 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\virtualframe.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)word_1800B3B5A,
        v15,
        v16,
        (__int64)v21,
        (__int64)&v19,
        (__int64)&v22,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)&v20);
    }
    v17 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(a1 + 32))(
            *(_QWORD *)(a1 + 32),
            &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c,
            a3);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v17,
        v18);
  }
  EventActivityIdControl(2u, &ActivityId);
  return 1;
}

```

## disassembly

```asm
0x180059aa0  mov     [rsp-8+arg_8], rbx
0x180059aa5  mov     [rsp-8+arg_18], rsi
0x180059aaa  push    rbp
0x180059aab  push    rdi
0x180059aac  push    r14
0x180059aae  lea     rbp, [rsp-47h]
0x180059ab3  sub     rsp, 0B0h
0x180059aba  mov     rax, cs:__security_cookie
0x180059ac1  xor     rax, rsp
0x180059ac4  mov     [rbp+57h+var_20], rax
0x180059ac8  mov     r14, r8
0x180059acb  mov     ebx, edx
0x180059acd  mov     rdi, rcx
0x180059ad0  movups  xmm0, cs:xmmword_1800C21A0
0x180059ad7  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180059adc  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180059ae0  mov     ecx, 4; ControlCode
0x180059ae5  call    cs:__imp_EventActivityIdControl
0x180059aeb  nop
0x180059aec  test    ebx, ebx
0x180059aee  jz      loc_180059C55
0x180059af4  cmp     ebx, 7
0x180059af7  jz      short loc_180059B0F
0x180059af9  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180059afd  mov     ecx, 2; ControlCode
0x180059b02  call    cs:__imp_EventActivityIdControl
0x180059b08  xor     al, al
0x180059b0a  jmp     loc_180059C31
0x180059b0f  mov     rsi, [rdi+90h]
0x180059b16  test    rsi, rsi
0x180059b19  jz      short loc_180059B4A
0x180059b1b  mov     rbx, [rdi+0C0h]
0x180059b22  mov     rax, [rdi+10h]
0x180059b26  mov     rcx, [rax]
0x180059b29  mov     rax, [rcx]
0x180059b2c  mov     rax, [rax+0C8h]
0x180059b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b38  mov     rdx, [rdi+50h]
0x180059b3c  add     rdx, rax; unsigned __int64
0x180059b3f  mov     r8, rbx; unsigned __int64
0x180059b42  mov     rcx, rsi; this
0x180059b45  call    ?OnFirstGraphicsFrame@CMonitorContext@Ic3@Avenc@Rdp@@QEAAX_K0@Z; Rdp::Avenc::Ic3::CMonitorContext::OnFirstGraphicsFrame(unsigned __int64,unsigned __int64)
0x180059b4a  mov     eax, cs:dword_1800C1058
0x180059b50  cmp     eax, 5
0x180059b53  jbe     loc_180059C02
0x180059b59  mov     eax, [rdi+38h]
0x180059b5c  mov     [rbp+57h+var_60], eax
0x180059b5f  mov     rax, [rdi+0C0h]
0x180059b66  mov     [rbp+57h+var_38], rax
0x180059b6a  mov     rax, [rdi+10h]
0x180059b6e  mov     rcx, [rax]
0x180059b71  mov     rax, [rcx]
0x180059b74  mov     rax, [rax+0C8h]
0x180059b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b80  add     rax, [rdi+50h]
0x180059b84  mov     qword ptr [rbp+57h+var_58], rax
0x180059b88  lea     rax, aFenceget; "FenceGet"
0x180059b8f  mov     [rbp+57h+var_50], rax
0x180059b93  lea     rax, aRdpAvencIc3Cvi_11; "Rdp::Avenc::Ic3::CVirtualFrame::GetServ"...
0x180059b9a  mov     [rbp+57h+var_48], rax
0x180059b9e  mov     [rbp+57h+var_5C], 109h
0x180059ba5  lea     rax, aOnecoreuapTerm_20; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180059bac  mov     [rbp+57h+var_40], rax
0x180059bb0  lea     rax, [rbp+57h+var_60]
0x180059bb4  mov     [rsp+0C0h+var_70], rax
0x180059bb9  lea     rax, [rbp+57h+var_38]
0x180059bbd  mov     [rsp+0C0h+var_78], rax
0x180059bc2  lea     rax, [rbp+57h+var_58]
0x180059bc6  mov     [rsp+0C0h+var_80], rax
0x180059bcb  lea     rax, [rbp+57h+var_50]
0x180059bcf  mov     [rsp+0C0h+var_88], rax
0x180059bd4  lea     rax, [rbp+57h+var_48]
0x180059bd8  mov     [rsp+0C0h+var_90], rax
0x180059bdd  lea     rax, [rbp+57h+var_5C]
0x180059be1  mov     [rsp+0C0h+var_98], rax
0x180059be6  lea     rax, [rbp+57h+var_40]
0x180059bea  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180059bef  lea     rdx, word_1800B3BBA
0x180059bf6  lea     rcx, dword_1800C1058
0x180059bfd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180059c02  mov     rax, [rdi]
0x180059c05  mov     rcx, rdi
0x180059c08  mov     rax, [rax]
0x180059c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c10  lea     rcx, [rdi+8]
0x180059c14  neg     rdi
0x180059c17  sbb     rax, rax
0x180059c1a  and     rax, rcx
0x180059c1d  mov     [r14], rax
0x180059c20  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180059c24  mov     ecx, 2; ControlCode
0x180059c29  call    cs:__imp_EventActivityIdControl
0x180059c2f  mov     al, 1
0x180059c31  mov     rcx, [rbp+57h+var_20]
0x180059c35  xor     rcx, rsp; StackCookie
0x180059c38  call    __security_check_cookie
0x180059c3d  lea     r11, [rsp+0C0h+var_10]
0x180059c45  mov     rbx, [r11+28h]
0x180059c49  mov     rsi, [r11+38h]
0x180059c4d  mov     rsp, r11
0x180059c50  pop     r14
0x180059c52  pop     rdi
0x180059c53  pop     rbp
0x180059c54  retn
0x180059c55  mov     rsi, [rdi+90h]
0x180059c5c  test    rsi, rsi
0x180059c5f  jz      short loc_180059C90
0x180059c61  mov     rbx, [rdi+0C0h]
0x180059c68  mov     rax, [rdi+10h]
0x180059c6c  mov     rcx, [rax]
0x180059c6f  mov     rax, [rcx]
0x180059c72  mov     rax, [rax+0C8h]
0x180059c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c7e  mov     rdx, [rdi+50h]
0x180059c82  add     rdx, rax; unsigned __int64
0x180059c85  mov     r8, rbx; unsigned __int64
0x180059c88  mov     rcx, rsi; this
0x180059c8b  call    ?OnFirstGraphicsFrame@CMonitorContext@Ic3@Avenc@Rdp@@QEAAX_K0@Z; Rdp::Avenc::Ic3::CMonitorContext::OnFirstGraphicsFrame(unsigned __int64,unsigned __int64)
0x180059c90  mov     rcx, rdi; this
0x180059c93  call    ?WaitForFenceReached@CVirtualFrame@Ic3@Avenc@Rdp@@AEAAXXZ; Rdp::Avenc::Ic3::CVirtualFrame::WaitForFenceReached(void)
0x180059c98  mov     eax, cs:dword_1800C1058
0x180059c9e  cmp     eax, 5
0x180059ca1  jbe     loc_180059D3C
0x180059ca7  mov     eax, [rdi+38h]
0x180059caa  mov     [rbp+57h+var_5C], eax
0x180059cad  mov     rax, [rdi+10h]
0x180059cb1  mov     rcx, [rax]
0x180059cb4  mov     rax, [rcx]
0x180059cb7  mov     rax, [rax+0C8h]
0x180059cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059cc3  add     rax, [rdi+50h]
0x180059cc7  mov     [rbp+57h+var_40], rax
0x180059ccb  lea     rax, aTextureget; "TextureGet"
0x180059cd2  mov     [rbp+57h+var_48], rax
0x180059cd6  lea     rax, aRdpAvencIc3Cvi_11; "Rdp::Avenc::Ic3::CVirtualFrame::GetServ"...
0x180059cdd  mov     [rbp+57h+var_50], rax
0x180059ce1  mov     [rbp+57h+var_60], 0F6h
0x180059ce8  lea     rax, aOnecoreuapTerm_20; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180059cef  mov     qword ptr [rbp+57h+var_58], rax
0x180059cf3  lea     rax, [rbp+57h+var_5C]
0x180059cf7  mov     [rsp+0C0h+var_78], rax
0x180059cfc  lea     rax, [rbp+57h+var_40]
0x180059d00  mov     [rsp+0C0h+var_80], rax
0x180059d05  lea     rax, [rbp+57h+var_48]
0x180059d09  mov     [rsp+0C0h+var_88], rax
0x180059d0e  lea     rax, [rbp+57h+var_50]
0x180059d12  mov     [rsp+0C0h+var_90], rax
0x180059d17  lea     rax, [rbp+57h+var_60]
0x180059d1b  mov     [rsp+0C0h+var_98], rax
0x180059d20  lea     rax, [rbp+57h+var_58]
0x180059d24  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180059d29  lea     rdx, word_1800B3B5A
0x180059d30  lea     rcx, dword_1800C1058
0x180059d37  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180059d3c  mov     rcx, [rdi+20h]
0x180059d40  mov     rax, [rcx]
0x180059d43  mov     r8, r14
0x180059d46  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x180059d4d  mov     rax, [rax]
0x180059d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d55  mov     rcx, [rbp+5Fh]; this
0x180059d59  test    eax, eax
0x180059d5b  jns     loc_180059C20
0x180059d61  mov     r9d, eax; char *
0x180059d64  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180059d6b  mov     edx, 1CBEh; void *
0x180059d70  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
