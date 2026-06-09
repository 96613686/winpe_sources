# DPU::Init(ushort const *)

- ea: `0x18024b390`
- end: `0x18024b5f6`
- name: `?Init@DPU@@QEAAJPEBG@Z`
- size: `614`
- prototype: `__int64 __fastcall(LPVOID *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180240ae0`
- `0x18024c418`

## callees

- `0x18000104c`
- `0x180001308`
- `0x1800014e8`
- `0x1800093c8`
- `0x180009af8`
- `0x1802458b8`
- `0x18024b390`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `DMCmnUtils!DmInitializeCVForLocalConfigSession` at `0x18024b595`
- `DMCmnUtils!DmInitializeCVForLocalConfigSession` at `0x18024b595`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18024b5b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18024b5b8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18024b57e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18024b57e`

## string_xrefs

- `0x18024b54c`: `OMADM::TargetedUserSID`
- `0x18024b4b4`: `No Enrollment available to complete operation`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x18024b390  mov     [rsp-8+arg_8], rbx
0x18024b395  mov     [rsp-8+arg_10], rsi
0x18024b39a  push    rbp
0x18024b39b  push    rdi
0x18024b39c  push    r15
0x18024b39e  lea     rbp, [rsp-10h]
0x18024b3a3  sub     rsp, 110h
0x18024b3aa  mov     rax, cs:__security_cookie
0x18024b3b1  xor     rax, rsp
0x18024b3b4  mov     [rbp+20h+var_20], rax
0x18024b3b8  mov     rsi, rdx
0x18024b3bb  mov     rdi, rcx
0x18024b3be  mov     [rbp+20h+var_80], 7
0x18024b3c6  mov     [rbp+20h+var_88], 0
0x18024b3ce  xor     eax, eax
0x18024b3d0  mov     word ptr [rbp+20h+var_98], ax
0x18024b3d4  mov     [rsp+120h+var_E0], rax
0x18024b3d9  xorps   xmm0, xmm0
0x18024b3dc  movups  [rsp+120h+var_D8], xmm0
0x18024b3e1  mov     [rsp+120h+var_C8], rax
0x18024b3e6  xorps   xmm1, xmm1
0x18024b3e9  movups  [rsp+120h+var_C0], xmm1
0x18024b3ee  movups  [rsp+120h+var_B0], xmm1
0x18024b3f3  mov     [rbp+20h+var_A0], rax
0x18024b3f7  lea     r15, aInit; "Init"
0x18024b3fe  test    rdx, rdx
0x18024b401  jnz     loc_18024B48F
0x18024b407  mov     ebx, 80070057h
0x18024b40c  mov     eax, cs:dword_180380B68
0x18024b412  cmp     eax, 5
0x18024b415  jbe     short loc_18024B45B
0x18024b417  mov     rdx, 200000000000h
0x18024b421  lea     rcx, dword_180380B68
0x18024b428  call    _tlgKeywordOn
0x18024b42d  test    al, al
0x18024b42f  jz      short loc_18024B45B
0x18024b431  mov     dword ptr [rsp+120h+var_F0], ebx
0x18024b435  mov     [rsp+120h+var_E8], r15
0x18024b43a  lea     rax, [rsp+120h+var_F0]
0x18024b43f  mov     [rsp+120h+var_F8], rax
0x18024b444  lea     rax, [rsp+120h+var_E8]
0x18024b449  mov     [rsp+120h+ppv], rax
0x18024b44e  lea     rdx, byte_180370D57
0x18024b455  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18024b45a  nop
0x18024b45b  xor     r8d, r8d
0x18024b45e  mov     dl, 1
0x18024b460  lea     rcx, [rbp+20h+var_98]
0x18024b464  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18024b469  mov     eax, ebx
0x18024b46b  mov     rcx, [rbp+20h+var_20]
0x18024b46f  xor     rcx, rsp; StackCookie
0x18024b472  call    __security_check_cookie
0x18024b477  lea     r11, [rsp+120h+var_10]
0x18024b47f  mov     rbx, [r11+28h]
0x18024b483  mov     rsi, [r11+30h]
0x18024b487  mov     rsp, r11
0x18024b48a  pop     r15
0x18024b48c  pop     rdi
0x18024b48d  pop     rbp
0x18024b48e  retn
0x18024b48f  lea     rcx, [rbp+20h+var_98]
0x18024b493  call    ?GetWmiBridgeEnrollmentId@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWmiBridgeEnrollmentId(std::wstring &)
0x18024b498  mov     ebx, eax
0x18024b49a  test    eax, eax
0x18024b49c  js      loc_18024B40C
0x18024b4a2  cmp     [rbp+20h+var_88], 0
0x18024b4a7  jnz     short loc_18024B4F9
0x18024b4a9  mov     eax, cs:dword_180380B68
0x18024b4af  cmp     eax, 5
0x18024b4b2  jbe     short loc_18024B4EF
0x18024b4b4  lea     rax, aNoEnrollmentAv; "No Enrollment available to complete ope"...
0x18024b4bb  mov     [rsp+120h+var_F0], rax
0x18024b4c0  mov     [rsp+120h+var_E8], r15
0x18024b4c5  lea     rax, [rsp+120h+var_F0]
0x18024b4ca  mov     [rsp+120h+var_F8], rax
0x18024b4cf  lea     rax, [rsp+120h+var_E8]
0x18024b4d4  mov     [rsp+120h+ppv], rax
0x18024b4d9  xor     r8d, r8d
0x18024b4dc  lea     rdx, byte_180370D85
0x18024b4e3  lea     rcx, dword_180380B68
0x18024b4ea  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18024b4ef  mov     ebx, 80004005h
0x18024b4f4  jmp     loc_18024B40C
0x18024b4f9  lea     r8, [rbp+20h+var_98]
0x18024b4fd  cmp     [rbp+20h+var_80], 8
0x18024b502  cmovnb  r8, [rbp+20h+var_98]; unsigned __int16 *
0x18024b507  mov     edx, 27h ; '''; unsigned __int64
0x18024b50c  lea     rcx, [rbp+20h+var_70]; unsigned __int16 *
0x18024b510  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18024b515  mov     ebx, eax
0x18024b517  test    eax, eax
0x18024b519  js      loc_18024B40C
0x18024b51f  lea     rax, aOmadmAccountid; "OMADM::AccountID"
0x18024b526  mov     [rsp+120h+var_E0], rax
0x18024b52b  cmp     [rbp+20h+var_70], 7Bh ; '{'
0x18024b530  jnz     short loc_18024B543
0x18024b532  lea     rax, [rbp+20h+var_6E]
0x18024b536  mov     qword ptr [rsp+120h+var_D8], rax
0x18024b53b  xor     eax, eax
0x18024b53d  mov     [rbp+20h+var_26], ax
0x18024b541  jmp     short loc_18024B54C
0x18024b543  lea     rax, [rbp+20h+var_70]
0x18024b547  mov     qword ptr [rsp+120h+var_D8], rax
0x18024b54c  lea     rax, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x18024b553  mov     qword ptr [rsp+120h+var_D8+8], rax
0x18024b558  mov     [rsp+120h+var_C8], rsi
0x18024b55d  lea     rax, aWmiBridgeSccmS; "WMI_Bridge_SCCM_Server"
0x18024b564  mov     qword ptr [rsp+120h+var_C0+8], rax
0x18024b569  mov     dword ptr [rsp+120h+var_B0+0Ch], 2
0x18024b571  lea     rax, [rsp+120h+var_E0]
0x18024b576  mov     [rbp+20h+var_A0], rax
0x18024b57a  xor     edx, edx; dwCoInit
0x18024b57c  xor     ecx, ecx; pvReserved
0x18024b57e  call    cs:__imp_CoInitializeEx
0x18024b584  mov     ebx, eax
0x18024b586  test    eax, eax
0x18024b588  js      loc_18024B40C
0x18024b58e  mov     rcx, cs:qword_1803A2300
0x18024b595  call    cs:__imp_?DmInitializeCVForLocalConfigSession@@YAJPEAVTraceLoggingCorrelationVector@@@Z; DmInitializeCVForLocalConfigSession(TraceLoggingCorrelationVector *)
0x18024b59b  lea     rsi, [rdi+8]
0x18024b59f  mov     [rsp+120h+ppv], rsi; ppv
0x18024b5a4  lea     r9, _GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd; riid
0x18024b5ab  xor     edx, edx; pUnkOuter
0x18024b5ad  lea     r8d, [rdx+1]; dwClsContext
0x18024b5b1  lea     rcx, _GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8; rclsid
0x18024b5b8  call    cs:__imp_CoCreateInstance
0x18024b5be  mov     ebx, eax
0x18024b5c0  test    eax, eax
0x18024b5c2  js      loc_18024B40C
0x18024b5c8  mov     rcx, [rsi]
0x18024b5cb  mov     rax, [rcx]
0x18024b5ce  mov     r8d, 28h ; '('
0x18024b5d4  lea     rdx, [rsp+120h+var_C0]
0x18024b5d9  mov     rax, [rax+18h]
0x18024b5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b5e2  mov     ebx, eax
0x18024b5e4  test    eax, eax
0x18024b5e6  js      loc_18024B40C
0x18024b5ec  mov     byte ptr [rdi+10h], 1
0x18024b5f0  jmp     loc_18024B45B
```
