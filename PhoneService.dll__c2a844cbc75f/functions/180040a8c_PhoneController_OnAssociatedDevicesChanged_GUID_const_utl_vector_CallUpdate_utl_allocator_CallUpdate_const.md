# PhoneController::_OnAssociatedDevicesChanged(_GUID const &,utl::vector<CallUpdate,utl::allocator<CallUpdate>> const &)

- ea: `0x180040a8c`
- end: `0x180040ddd`
- name: `?_OnAssociatedDevicesChanged@PhoneController@@IEAAJAEBU_GUID@@AEBV?$vector@UCallUpdate@@V?$allocator@UCallUpdate@@@utl@@@utl@@@Z`
- size: `849`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180040de4`

## callees

- `0x180003e88`
- `0x1800056a0`
- `0x180006e94`
- `0x180023a24`
- `0x18002888c`
- `0x18002c574`
- `0x18002c580`
- `0x180040a8c`
- `0x18004ef10`
- `0x18004f76c`
- `0x180051e44`
- `0x1800524c8`
- `0x18007f9ec`
- `0x18008d936`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040abf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040ae0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040abf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040ae0`

## string_xrefs

- `0x180040ad4`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180040b25`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180040c59`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180040d75`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_OnAssociatedDevicesChanged(__int64 a1, const struct _GUID *a2, __int64 *a3)
{
  __int64 v6; // rcx
  PhoneLineStorage *v7; // rcx
  int PhoneLine; // eax
  BackTraceCollection *v9; // rcx
  unsigned int v10; // ebx
  __int64 v12; // rsi
  char v13; // r12
  struct PhoneLine *v14; // rbx
  __int64 v15; // rcx
  CallInfo *v16; // rdi
  CallInfo *v17; // r14
  int v18; // eax
  PhoneController *v19; // rcx
  const unsigned __int16 *v20; // rax
  __int128 v21; // xmm0
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  int v25; // eax
  BackTraceCollection *v26; // rcx
  unsigned int v27; // edi
  CallInfo *v28; // [rsp+50h] [rbp-49h] BYREF
  struct PhoneLine *v29; // [rsp+58h] [rbp-41h] BYREF
  struct _GUID Buf2; // [rsp+60h] [rbp-39h] BYREF
  const unsigned __int16 *v31; // [rsp+70h] [rbp-29h] BYREF
  __int128 Buf1; // [rsp+78h] [rbp-21h] BYREF
  __int128 v33; // [rsp+88h] [rbp-11h] BYREF
  void *Block[2]; // [rsp+98h] [rbp-1h] BYREF
  __int16 v35; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v36; // [rsp+AAh] [rbp+11h]
  int v37; // [rsp+B2h] [rbp+19h]
  __int16 v38; // [rsp+B6h] [rbp+1Dh]

  if ( *(_DWORD *)(a1 + 240) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2205);
    if ( *(_DWORD *)(a1 + 240) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v7 = *(PhoneLineStorage **)(a1 + 152);
  v29 = 0;
  PhoneLine = PhoneLineStorage::GetPhoneLine(v7, a2, &v29, 0);
  v10 = PhoneLine;
  if ( PhoneLine >= 0 )
  {
    v12 = *a3;
    v13 = 0;
    v14 = v29;
    while ( v12 != a3[1] )
    {
      v15 = *(_QWORD *)(a1 + 96);
      v28 = 0;
      PhoneCallStorage::FindCall(v15, &v28, v12, 0);
      v16 = v28;
      if ( v28 )
      {
        v28 = 0;
        CallInfo::GetPhoneLine(v16, &v28);
        v17 = v28;
        Buf1 = *(_OWORD *)((char *)v14 + 88);
        Buf2 = *(struct _GUID *)((char *)v28 + 88);
        if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
        {
          if ( *(_QWORD *)(v12 + 8) == 0x8000000000000LL
            && (Buf2 = (struct _GUID)*((_OWORD *)v14 + 7), !memcmp_0(&Buf2, VoipLineType, 0x10u)) )
          {
            v37 = 0;
            v38 = 0;
            v36 = 0;
            Block[0] = &v35;
            Block[1] = &v35;
            v35 = 0;
            v18 = GetDeviceIdsListFromCallUpdateAsString(v12, Block);
            if ( v18 < 0 )
              Log_HREvent_7(
                (unsigned int)v18,
                0,
                "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
                2251);
            if ( (unsigned int)dword_1800B3200 > 4 )
            {
              v28 = (CallInfo *)Block[0];
              LODWORD(v29) = *((_DWORD *)v16 + 767);
              Buf2 = (struct _GUID)*((_OWORD *)v14 + 7);
              v20 = PhoneController::ConvertLineTypeToString(v19, &Buf2);
              v21 = *(_OWORD *)((char *)v14 + 88);
              v31 = v20;
              *(_QWORD *)&Buf1 = &v33;
              *(_QWORD *)&Buf2.Data1 = "Associated devices change";
              v33 = v21;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                v22,
                (int)byte_1800A85E9,
                v23,
                v24,
                (const unsigned __int16 **)&Buf2,
                (__int64 *)&Buf1,
                &v31,
                (__int64)&v29,
                (const unsigned __int16 **)&v28);
            }
            CallInfo::UpdateCall(v16, (const struct CallUpdate *)v12, 0);
            v13 = 1;
            if ( Block[0] != &v35 )
              operator delete(Block[0]);
          }
          else
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
        }
        (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v17 + 16LL))(v17);
        (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v16 + 16LL))(v16);
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      v12 += 3904;
    }
    if ( v13 && (v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 880LL))(a1), v27 = v25, v25 < 0) )
    {
      BackTraceCollection::Capture(v26, v25);
      Log_HREvent_7(v27, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2271);
      if ( v14 )
        (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v14 + 16LL))(v14);
      return v27;
    }
    else
    {
      if ( v14 )
        (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v14 + 16LL))(v14);
      return 0;
    }
  }
  else
  {
    BackTraceCollection::Capture(v9, PhoneLine);
    Log_HREvent_7(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2210);
    if ( v29 )
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v29 + 16LL))(v29);
    return v10;
  }
}

```

## disassembly

```asm
0x180040a8c  mov     [rsp-8+arg_10], rbx
0x180040a91  push    rbp
0x180040a92  push    rsi
0x180040a93  push    rdi
0x180040a94  push    r12
0x180040a96  push    r13
0x180040a98  push    r14
0x180040a9a  push    r15
0x180040a9c  lea     rbp, [rsp-27h]
0x180040aa1  sub     rsp, 0C0h
0x180040aa8  mov     rax, cs:__security_cookie
0x180040aaf  xor     rax, rsp
0x180040ab2  mov     [rbp+57h+var_38], rax
0x180040ab6  mov     r13, r8
0x180040ab9  mov     rbx, rdx
0x180040abc  mov     r15, rcx
0x180040abf  call    cs:__imp_GetCurrentThreadId
0x180040ac5  cmp     [r15+0F0h], eax
0x180040acc  jz      short loc_180040AF4
0x180040ace  mov     r8d, 89Dh
0x180040ad4  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180040adb  call    Log_AssertionEvent_3
0x180040ae0  call    cs:__imp_GetCurrentThreadId
0x180040ae6  cmp     [r15+0F0h], eax
0x180040aed  jz      short loc_180040AF4
0x180040aef  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180040af4  mov     rcx, [r15+98h]; this
0x180040afb  lea     r8, [rbp+57h+var_98]; struct PhoneLine **
0x180040aff  xor     r9d, r9d; struct ISecurityToken *
0x180040b02  mov     [rbp+57h+var_98], 0
0x180040b0a  mov     rdx, rbx; struct _GUID *
0x180040b0d  call    ?GetPhoneLine@PhoneLineStorage@@QEAAJAEBU_GUID@@PEAPEAVPhoneLine@@PEAUISecurityToken@@@Z; PhoneLineStorage::GetPhoneLine(_GUID const &,PhoneLine * *,ISecurityToken *)
0x180040b12  mov     ebx, eax
0x180040b14  test    eax, eax
0x180040b16  jns     short loc_180040B54
0x180040b18  mov     edx, eax; int
0x180040b1a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180040b1f  mov     r9d, 8A2h
0x180040b25  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180040b2c  mov     edx, 1
0x180040b31  mov     ecx, ebx
0x180040b33  call    Log_HREvent_7
0x180040b38  mov     rcx, [rbp+57h+var_98]
0x180040b3c  test    rcx, rcx
0x180040b3f  jz      short loc_180040B4D
0x180040b41  mov     rax, [rcx]
0x180040b44  mov     rax, [rax+10h]
0x180040b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b4d  mov     eax, ebx
0x180040b4f  jmp     loc_180040DB6
0x180040b54  mov     rsi, [r13+0]
0x180040b58  xor     r12b, r12b
0x180040b5b  mov     rbx, [rbp+57h+var_98]
0x180040b5f  cmp     rsi, [r13+8]
0x180040b63  jz      loc_180040D4B
0x180040b69  mov     rcx, [r15+60h]
0x180040b6d  lea     rdx, [rbp+57h+var_A0]
0x180040b71  xor     r9d, r9d
0x180040b74  mov     [rbp+57h+var_A0], 0
0x180040b7c  mov     r8, rsi
0x180040b7f  call    ?FindCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@AEBIPEAUISecurityToken@@@Z; PhoneCallStorage::FindCall(uint const &,ISecurityToken *)
0x180040b84  mov     rdi, [rbp+57h+var_A0]
0x180040b88  test    rdi, rdi
0x180040b8b  jnz     short loc_180040B97
0x180040b8d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180040b92  jmp     loc_180040D3F
0x180040b97  lea     rdx, [rbp+57h+var_A0]; struct PhoneLine **
0x180040b9b  mov     [rbp+57h+var_A0], 0
0x180040ba3  mov     rcx, rdi; this
0x180040ba6  call    ?GetPhoneLine@CallInfo@@QEAAXPEAPEAVPhoneLine@@@Z; CallInfo::GetPhoneLine(PhoneLine * *)
0x180040bab  movups  xmm1, xmmword ptr [rbx+58h]
0x180040baf  mov     r14, [rbp+57h+var_A0]
0x180040bb3  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180040bb7  mov     r8d, 10h; Size
0x180040bbd  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180040bc1  movdqu  [rbp+57h+Buf1], xmm1
0x180040bc6  movups  xmm0, xmmword ptr [r14+58h]
0x180040bcb  movdqu  [rbp+57h+Buf2], xmm0
0x180040bd0  call    memcmp_0
0x180040bd5  test    eax, eax
0x180040bd7  jnz     loc_180040D21
0x180040bdd  mov     rax, 8000000000000h
0x180040be7  cmp     [rsi+8], rax
0x180040beb  jz      short loc_180040BF7
0x180040bed  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180040bf2  jmp     loc_180040D21
0x180040bf7  movups  xmm0, xmmword ptr [rbx+70h]
0x180040bfb  mov     r8d, 10h; Size
0x180040c01  lea     rdx, VoipLineType; Buf2
0x180040c08  lea     rcx, [rbp+57h+Buf2]; Buf1
0x180040c0c  movdqu  [rbp+57h+Buf2], xmm0
0x180040c11  call    memcmp_0
0x180040c16  test    eax, eax
0x180040c18  jnz     loc_180040D1C
0x180040c1e  mov     [rbp+57h+var_3E], eax
0x180040c21  lea     rdx, [rbp+57h+Block]
0x180040c25  mov     [rbp+57h+var_3A], ax
0x180040c29  mov     rcx, rsi
0x180040c2c  lea     rax, [rbp+57h+var_48]
0x180040c30  mov     [rbp+57h+var_46], 0
0x180040c38  mov     [rbp+57h+Block], rax
0x180040c3c  lea     rax, [rbp+57h+var_48]
0x180040c40  mov     [rbp+57h+var_50], rax
0x180040c44  xor     eax, eax
0x180040c46  mov     [rbp+57h+var_48], ax
0x180040c4a  call    ?GetDeviceIdsListFromCallUpdateAsString@@YAJAEBUCallUpdate@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetDeviceIdsListFromCallUpdateAsString(CallUpdate const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180040c4f  test    eax, eax
0x180040c51  jns     short loc_180040C69
0x180040c53  mov     r9d, 8CBh
0x180040c59  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180040c60  xor     edx, edx
0x180040c62  mov     ecx, eax
0x180040c64  call    Log_HREvent_7
0x180040c69  mov     eax, cs:dword_1800B3200
0x180040c6f  cmp     eax, 4
0x180040c72  jbe     short loc_180040CF0
0x180040c74  mov     rax, [rbp+57h+Block]
0x180040c78  lea     rdx, [rbp+57h+Buf2]; struct _GUID
0x180040c7c  mov     [rbp+57h+var_A0], rax
0x180040c80  mov     eax, [rdi+0BFCh]
0x180040c86  mov     dword ptr [rbp+57h+var_98], eax
0x180040c89  movups  xmm0, xmmword ptr [rbx+70h]
0x180040c8d  movdqu  [rbp+57h+Buf2], xmm0
0x180040c92  call    ?ConvertLineTypeToString@PhoneController@@AEAAPEBGU_GUID@@@Z; PhoneController::ConvertLineTypeToString(_GUID)
0x180040c97  movups  xmm0, xmmword ptr [rbx+58h]
0x180040c9b  mov     [rbp+57h+var_80], rax
0x180040c9f  lea     rdx, byte_1800A85E9
0x180040ca6  lea     rax, [rbp+57h+var_68]
0x180040caa  mov     qword ptr [rbp+57h+Buf1], rax
0x180040cae  lea     rax, aAssociatedDevi; "Associated devices change"
0x180040cb5  mov     qword ptr [rbp+57h+Buf2], rax
0x180040cb9  lea     rax, [rbp+57h+var_A0]
0x180040cbd  mov     [rsp+0F0h+var_B0], rax
0x180040cc2  lea     rax, [rbp+57h+var_98]
0x180040cc6  mov     [rsp+0F0h+var_B8], rax
0x180040ccb  lea     rax, [rbp+57h+var_80]
0x180040ccf  mov     [rsp+0F0h+var_C0], rax
0x180040cd4  lea     rax, [rbp+57h+Buf1]
0x180040cd8  mov     [rsp+0F0h+var_C8], rax
0x180040cdd  lea     rax, [rbp+57h+Buf2]
0x180040ce1  mov     [rsp+0F0h+var_D0], rax
0x180040ce6  movdqu  [rbp+57h+var_68], xmm0
0x180040ceb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180040cf0  xor     r8d, r8d; int
0x180040cf3  mov     rdx, rsi; struct CallUpdate *
0x180040cf6  mov     rcx, rdi; this
0x180040cf9  call    ?UpdateCall@CallInfo@@QEAAJPEBUCallUpdate@@H@Z; CallInfo::UpdateCall(CallUpdate const *,int)
0x180040cfe  mov     rcx, [rbp+57h+Block]; Block
0x180040d02  lea     rax, [rbp+57h+var_48]
0x180040d06  mov     r12b, 1
0x180040d09  cmp     rcx, rax
0x180040d0c  jz      short loc_180040D21
0x180040d0e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180040d15  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040d1a  jmp     short loc_180040D21
0x180040d1c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180040d21  mov     rax, [r14]
0x180040d24  mov     rcx, r14
0x180040d27  mov     rax, [rax+10h]
0x180040d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d30  mov     rax, [rdi]
0x180040d33  mov     rcx, rdi
0x180040d36  mov     rax, [rax+10h]
0x180040d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d3f  add     rsi, 0F40h
0x180040d46  jmp     loc_180040B5F
0x180040d4b  test    r12b, r12b
0x180040d4e  jz      short loc_180040DA0
0x180040d50  mov     rax, [r15]
0x180040d53  mov     rcx, r15
0x180040d56  mov     rax, [rax+370h]
0x180040d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d62  mov     edi, eax
0x180040d64  test    eax, eax
0x180040d66  jns     short loc_180040DA0
0x180040d68  mov     edx, eax; int
0x180040d6a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180040d6f  mov     r9d, 8DFh
0x180040d75  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180040d7c  mov     edx, 1
0x180040d81  mov     ecx, edi
0x180040d83  call    Log_HREvent_7
0x180040d88  test    rbx, rbx
0x180040d8b  jz      short loc_180040D9C
0x180040d8d  mov     rcx, [rbx]
0x180040d90  mov     rax, [rcx+10h]
0x180040d94  mov     rcx, rbx
0x180040d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d9c  mov     eax, edi
0x180040d9e  jmp     short loc_180040DB6
0x180040da0  test    rbx, rbx
0x180040da3  jz      short loc_180040DB4
0x180040da5  mov     rax, [rbx]
0x180040da8  mov     rcx, rbx
0x180040dab  mov     rax, [rax+10h]
0x180040daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040db4  xor     eax, eax
0x180040db6  mov     rcx, [rbp+57h+var_38]
0x180040dba  xor     rcx, rsp; StackCookie
0x180040dbd  call    __security_check_cookie
0x180040dc2  mov     rbx, [rsp+0F0h+arg_10]
0x180040dca  add     rsp, 0C0h
0x180040dd1  pop     r15
0x180040dd3  pop     r14
0x180040dd5  pop     r13
0x180040dd7  pop     r12
0x180040dd9  pop     rdi
0x180040dda  pop     rsi
0x180040ddb  pop     rbp
0x180040ddc  retn
```
