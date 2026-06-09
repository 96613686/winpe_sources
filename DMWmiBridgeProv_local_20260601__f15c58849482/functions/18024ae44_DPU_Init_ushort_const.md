# DPU::Init(ushort const *)

- ea: `0x18024ae44`
- end: `0x18024b0bd`
- name: `?Init@DPU@@QEAAJPEBG@Z`
- size: `633`
- prototype: `__int64 __fastcall(DPU *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18023fe24`
- `0x18024bf6c`

## callees

- `0x18000104c`
- `0x180001310`
- `0x1800014f0`
- `0x1800097e4`
- `0x180009f1c`
- `0x180244d34`
- `0x18024ae44`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `DMCmnUtils!DmInitializeCVForLocalConfigSession` at `0x18024b050`
- `DMCmnUtils!DmInitializeCVForLocalConfigSession` at `0x18024b050`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18024b079`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18024b079`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18024b033`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18024b033`

## string_xrefs

- `0x18024b001`: `OMADM::TargetedUserSID`
- `0x18024af69`: `No Enrollment available to complete operation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DPU::Init(LPVOID *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rsi
  HRESULT WmiBridgeEnrollmentId; // ebx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v9; // r9d
  const unsigned __int16 *v10; // r8
  const char *v11; // [rsp+30h] [rbp-D0h] BYREF
  const char *v12; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v13; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v15; // [rsp+58h] [rbp-A8h]
  __int128 v16; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v17; // [rsp+70h] [rbp-90h]
  const wchar_t **v18; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v19[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v20; // [rsp+98h] [rbp-68h]
  unsigned __int64 v21; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v22; // [rsp+B0h] [rbp-50h] BYREF
  char v23; // [rsp+B2h] [rbp-4Eh] BYREF
  __int16 v24; // [rsp+FAh] [rbp-6h]

  v2 = a2;
  v21 = 7;
  v20 = 0;
  LOWORD(v19[0]) = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  if ( a2 )
  {
    WmiBridgeEnrollmentId = GetWmiBridgeEnrollmentId(v19);
    if ( WmiBridgeEnrollmentId >= 0 )
    {
      if ( v20 )
      {
        v10 = (const unsigned __int16 *)v19;
        if ( v21 >= 8 )
          v10 = v19[0];
        WmiBridgeEnrollmentId = StringCchCopyW(&v22, 0x27u, v10);
        if ( WmiBridgeEnrollmentId >= 0 )
        {
          v13 = L"OMADM::AccountID";
          if ( v22 == 123 )
          {
            *(_QWORD *)&v14 = &v23;
            v24 = 0;
          }
          else
          {
            *(_QWORD *)&v14 = &v22;
          }
          *((_QWORD *)&v14 + 1) = L"OMADM::TargetedUserSID";
          v15 = v2;
          *((_QWORD *)&v16 + 1) = L"WMI_Bridge_SCCM_Server";
          HIDWORD(v17) = 2;
          v18 = &v13;
          WmiBridgeEnrollmentId = CoInitializeEx(0, 0);
          if ( WmiBridgeEnrollmentId >= 0 )
          {
            DmInitializeCVForLocalConfigSession((struct TraceLoggingCorrelationVector *)qword_1803A2300);
            WmiBridgeEnrollmentId = CoCreateInstance(
                                      &GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8,
                                      0,
                                      1u,
                                      &GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd,
                                      this + 1);
            if ( WmiBridgeEnrollmentId >= 0 )
            {
              WmiBridgeEnrollmentId = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64))(*(_QWORD *)this[1] + 24LL))(
                                        this[1],
                                        &v16,
                                        40);
              if ( WmiBridgeEnrollmentId >= 0 )
              {
                *((_BYTE *)this + 16) = 1;
                goto LABEL_6;
              }
            }
          }
        }
      }
      else
      {
        if ( (unsigned int)dword_180380B68 > 5 )
        {
          v11 = "No Enrollment available to complete operation";
          v12 = "Init";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (unsigned int)&dword_180380B68,
            (unsigned int)byte_180370D85,
            0,
            v9,
            (__int64)&v12,
            (__int64)&v11);
        }
        WmiBridgeEnrollmentId = -2147467259;
      }
    }
  }
  else
  {
    WmiBridgeEnrollmentId = -2147024809;
  }
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    LODWORD(v11) = WmiBridgeEnrollmentId;
    v12 = "Init";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)&byte_180370D57,
      v6,
      v7,
      (__int64)&v12,
      (__int64)&v11);
  }
LABEL_6:
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(v19, a2, 0);
  return (unsigned int)WmiBridgeEnrollmentId;
}

```

## disassembly

```asm
0x18024ae44  mov     [rsp-8+arg_8], rbx
0x18024ae49  mov     [rsp-8+arg_10], rsi
0x18024ae4e  push    rbp
0x18024ae4f  push    rdi
0x18024ae50  push    r15
0x18024ae52  lea     rbp, [rsp-10h]
0x18024ae57  sub     rsp, 110h
0x18024ae5e  mov     rax, cs:__security_cookie
0x18024ae65  xor     rax, rsp
0x18024ae68  mov     [rbp+20h+var_20], rax
0x18024ae6c  mov     rsi, rdx
0x18024ae6f  mov     rdi, rcx
0x18024ae72  mov     [rbp+20h+var_80], 7
0x18024ae7a  mov     [rbp+20h+var_88], 0
0x18024ae82  xor     eax, eax
0x18024ae84  mov     word ptr [rbp+20h+var_98], ax
0x18024ae88  mov     [rsp+120h+var_E0], rax
0x18024ae8d  xorps   xmm0, xmm0
0x18024ae90  movups  [rsp+120h+var_D8], xmm0
0x18024ae95  mov     [rsp+120h+var_C8], rax
0x18024ae9a  xorps   xmm1, xmm1
0x18024ae9d  movups  [rsp+120h+var_C0], xmm1
0x18024aea2  movups  [rsp+120h+var_B0], xmm1
0x18024aea7  mov     [rbp+20h+var_A0], rax
0x18024aeab  lea     r15, aInit; "Init"
0x18024aeb2  test    rdx, rdx
0x18024aeb5  jnz     loc_18024AF44
0x18024aebb  mov     ebx, 80070057h
0x18024aec0  mov     eax, cs:dword_180380B68
0x18024aec6  cmp     eax, 5
0x18024aec9  jbe     short loc_18024AF0F
0x18024aecb  mov     rdx, 200000000000h
0x18024aed5  lea     rcx, dword_180380B68
0x18024aedc  call    _tlgKeywordOn
0x18024aee1  test    al, al
0x18024aee3  jz      short loc_18024AF0F
0x18024aee5  mov     dword ptr [rsp+120h+var_F0], ebx
0x18024aee9  mov     [rsp+120h+var_E8], r15
0x18024aeee  lea     rax, [rsp+120h+var_F0]
0x18024aef3  mov     [rsp+120h+var_F8], rax
0x18024aef8  lea     rax, [rsp+120h+var_E8]
0x18024aefd  mov     [rsp+120h+ppv], rax
0x18024af02  lea     rdx, byte_180370D57
0x18024af09  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18024af0e  nop
0x18024af0f  xor     r8d, r8d
0x18024af12  mov     dl, 1
0x18024af14  lea     rcx, [rbp+20h+var_98]
0x18024af18  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18024af1d  mov     eax, ebx
0x18024af1f  mov     rcx, [rbp+20h+var_20]
0x18024af23  xor     rcx, rsp; StackCookie
0x18024af26  call    __security_check_cookie
0x18024af2b  lea     r11, [rsp+120h+var_10]
0x18024af33  mov     rbx, [r11+28h]
0x18024af37  mov     rsi, [r11+30h]
0x18024af3b  mov     rsp, r11
0x18024af3e  pop     r15
0x18024af40  pop     rdi
0x18024af41  pop     rbp
0x18024af42  retn
0x18024af44  lea     rcx, [rbp+20h+var_98]
0x18024af48  call    ?GetWmiBridgeEnrollmentId@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWmiBridgeEnrollmentId(std::wstring &)
0x18024af4d  mov     ebx, eax
0x18024af4f  test    eax, eax
0x18024af51  js      loc_18024AEC0
0x18024af57  cmp     [rbp+20h+var_88], 0
0x18024af5c  jnz     short loc_18024AFAE
0x18024af5e  mov     eax, cs:dword_180380B68
0x18024af64  cmp     eax, 5
0x18024af67  jbe     short loc_18024AFA4
0x18024af69  lea     rax, aNoEnrollmentAv; "No Enrollment available to complete ope"...
0x18024af70  mov     [rsp+120h+var_F0], rax
0x18024af75  mov     [rsp+120h+var_E8], r15
0x18024af7a  lea     rax, [rsp+120h+var_F0]
0x18024af7f  mov     [rsp+120h+var_F8], rax
0x18024af84  lea     rax, [rsp+120h+var_E8]
0x18024af89  mov     [rsp+120h+ppv], rax
0x18024af8e  xor     r8d, r8d
0x18024af91  lea     rdx, byte_180370D85
0x18024af98  lea     rcx, dword_180380B68
0x18024af9f  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18024afa4  mov     ebx, 80004005h
0x18024afa9  jmp     loc_18024AEC0
0x18024afae  lea     r8, [rbp+20h+var_98]
0x18024afb2  cmp     [rbp+20h+var_80], 8
0x18024afb7  cmovnb  r8, [rbp+20h+var_98]; unsigned __int16 *
0x18024afbc  mov     edx, 27h ; '''; unsigned __int64
0x18024afc1  lea     rcx, [rbp+20h+var_70]; unsigned __int16 *
0x18024afc5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18024afca  mov     ebx, eax
0x18024afcc  test    eax, eax
0x18024afce  js      loc_18024AEC0
0x18024afd4  lea     rax, aOmadmAccountid; "OMADM::AccountID"
0x18024afdb  mov     [rsp+120h+var_E0], rax
0x18024afe0  cmp     [rbp+20h+var_70], 7Bh ; '{'
0x18024afe5  jnz     short loc_18024AFF8
0x18024afe7  lea     rax, [rbp+20h+var_6E]
0x18024afeb  mov     qword ptr [rsp+120h+var_D8], rax
0x18024aff0  xor     eax, eax
0x18024aff2  mov     [rbp+20h+var_26], ax
0x18024aff6  jmp     short loc_18024B001
0x18024aff8  lea     rax, [rbp+20h+var_70]
0x18024affc  mov     qword ptr [rsp+120h+var_D8], rax
0x18024b001  lea     rax, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x18024b008  mov     qword ptr [rsp+120h+var_D8+8], rax
0x18024b00d  mov     [rsp+120h+var_C8], rsi
0x18024b012  lea     rax, aWmiBridgeSccmS; "WMI_Bridge_SCCM_Server"
0x18024b019  mov     qword ptr [rsp+120h+var_C0+8], rax
0x18024b01e  mov     dword ptr [rsp+120h+var_B0+0Ch], 2
0x18024b026  lea     rax, [rsp+120h+var_E0]
0x18024b02b  mov     [rbp+20h+var_A0], rax
0x18024b02f  xor     edx, edx; dwCoInit
0x18024b031  xor     ecx, ecx; pvReserved
0x18024b033  call    cs:__imp_CoInitializeEx
0x18024b03a  nop     dword ptr [rax+rax+00h]
0x18024b03f  mov     ebx, eax
0x18024b041  test    eax, eax
0x18024b043  js      loc_18024AEC0
0x18024b049  mov     rcx, cs:qword_1803A2300
0x18024b050  call    cs:__imp_?DmInitializeCVForLocalConfigSession@@YAJPEAVTraceLoggingCorrelationVector@@@Z; DmInitializeCVForLocalConfigSession(TraceLoggingCorrelationVector *)
0x18024b057  nop     dword ptr [rax+rax+00h]
0x18024b05c  lea     rsi, [rdi+8]
0x18024b060  mov     [rsp+120h+ppv], rsi; ppv
0x18024b065  lea     r9, _GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd; riid
0x18024b06c  xor     edx, edx; pUnkOuter
0x18024b06e  lea     r8d, [rdx+1]; dwClsContext
0x18024b072  lea     rcx, _GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8; rclsid
0x18024b079  call    cs:__imp_CoCreateInstance
0x18024b080  nop     dword ptr [rax+rax+00h]
0x18024b085  mov     ebx, eax
0x18024b087  test    eax, eax
0x18024b089  js      loc_18024AEC0
0x18024b08f  mov     rcx, [rsi]
0x18024b092  mov     rax, [rcx]
0x18024b095  mov     r8d, 28h ; '('
0x18024b09b  lea     rdx, [rsp+120h+var_C0]
0x18024b0a0  mov     rax, [rax+18h]
0x18024b0a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b0a9  mov     ebx, eax
0x18024b0ab  test    eax, eax
0x18024b0ad  js      loc_18024AEC0
0x18024b0b3  mov     byte ptr [rdi+10h], 1
0x18024b0b7  jmp     loc_18024AF0F
```
