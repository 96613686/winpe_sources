# SoftwareBitmapState::SoftwareBitmapState(Microsoft::WRL::ComPtr<IWICBitmap> const &,tagRECT const &)

- ea: `0x180003cf0`
- end: `0x180003fc3`
- name: `??0SoftwareBitmapState@@QEAA@AEBV?$ComPtr@UIWICBitmap@@@WRL@Microsoft@@AEBUtagRECT@@@Z`
- size: `723`
- prototype: `__int64 __fastcall(SoftwareBitmapState *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180003c00`

## callees

- `0x180003cf0`
- `0x1800148e0`
- `0x180015290`
- `0x180015920`
- `0x18001b790`
- `0x18001c710`
- `0x180026920`
- `0x18002749c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180003e1c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180003e1c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180003ed9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180003ed9`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
SoftwareBitmapState *__fastcall SoftwareBitmapState::SoftwareBitmapState(
        SoftwareBitmapState *this,
        _QWORD *a2,
        _OWORD *a3)
{
  int v6; // eax
  struct IErrorInfo *v7; // r8
  bool v8; // r9
  int v9; // eax
  struct IErrorInfo *v10; // r8
  bool v11; // r9
  __int64 v12; // rcx
  int v13; // eax
  struct IErrorInfo *v14; // r8
  bool v15; // r9
  unsigned int v17; // [rsp+50h] [rbp-59h] BYREF
  int v18; // [rsp+54h] [rbp-55h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-51h] BYREF
  _QWORD v20[3]; // [rsp+78h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-19h] BYREF
  void *v22; // [rsp+A0h] [rbp-9h]
  int v23; // [rsp+A8h] [rbp-1h]
  int v24; // [rsp+ACh] [rbp+3h]
  _QWORD *v25; // [rsp+B0h] [rbp+7h]
  __int64 v26; // [rsp+B8h] [rbp+Fh]
  int *v27; // [rsp+C0h] [rbp+17h]
  __int64 v28; // [rsp+C8h] [rbp+1Fh]

  v20[1] = this;
  *((_DWORD *)this + 3) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &SoftwareBitmapState::`vftable';
  *((_DWORD *)this + 4) = MediaFrameHelpers::GetFormat(a2);
  *((_DWORD *)this + 5) = MediaFrameHelpers::GetAlpha(a2);
  v17 = 0;
  v18 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, int *))(*(_QWORD *)*a2 + 24LL))(*a2, &v17, &v18);
  if ( v6 < 0 )
  {
    _com_error::_com_error((_com_error *)&EventDescriptor, v6, v7, v8);
    throw (_com_error *)&EventDescriptor;
  }
  *((_DWORD *)this + 6) = v17;
  v18 = 0;
  v17 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, int *, unsigned int *))(*(_QWORD *)*a2 + 24LL))(*a2, &v18, &v17);
  if ( v9 < 0 )
  {
    _com_error::_com_error((_com_error *)&EventDescriptor, v9, v10, v11);
    throw (_com_error *)&EventDescriptor;
  }
  *((_DWORD *)this + 7) = v17;
  *((_OWORD *)this + 2) = *a3;
  *((_QWORD *)this + 6) = 0x4058000000000000LL;
  *((_QWORD *)this + 7) = 0x4058000000000000LL;
  *((_DWORD *)this + 16) = 0;
  *((_BYTE *)this + 68) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  v12 = *a2;
  *((_QWORD *)this + 13) = *a2;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  *((_QWORD *)this + 14) = 0;
  InitializeSRWLock((PSRWLOCK)this + 15);
  if ( (unsigned int)dword_1800710A0 > 5 )
  {
    v18 = *((_DWORD *)this + 4);
    v20[0] = this;
    v27 = &v18;
    v28 = 4;
    v25 = v20;
    v26 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 261;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_1800710A8;
    UserData.Size = *(unsigned __int16 *)off_1800710A8;
    UserData.Reserved = 2;
    v22 = &unk_180065928;
    v23 = 48;
    v24 = 1;
    v17 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  SoftwareBitmapState::ValidateState(this);
  v13 = (*(__int64 (__fastcall **)(_QWORD, char *, char *))(*(_QWORD *)*a2 + 40LL))(
          *a2,
          (char *)this + 48,
          (char *)this + 56);
  if ( v13 < 0 )
  {
    _com_error::_com_error((_com_error *)&EventDescriptor, v13, v14, v15);
    throw (_com_error *)&EventDescriptor;
  }
  if ( g_wppLevels >= 0x20u )
    WPP_SF_qddddgg(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      v14,
      this,
      *((_DWORD *)this + 4),
      *((_DWORD *)this + 5),
      *((_DWORD *)this + 6),
      *((_DWORD *)this + 7),
      *((_QWORD *)this + 6),
      *((_QWORD *)this + 7));
  return this;
}

```

## disassembly

```asm
0x180003cf0  mov     [rsp-8+arg_10], rbx
0x180003cf5  push    rbp
0x180003cf6  push    rsi
0x180003cf7  push    rdi
0x180003cf8  push    r14
0x180003cfa  push    r15
0x180003cfc  lea     rbp, [rsp-37h]
0x180003d01  sub     rsp, 0E0h
0x180003d08  mov     rax, cs:__security_cookie
0x180003d0f  xor     rax, rsp
0x180003d12  mov     [rbp+57h+var_30], rax
0x180003d16  mov     rsi, r8
0x180003d19  mov     rdi, rdx
0x180003d1c  mov     rbx, rcx
0x180003d1f  mov     [rbp+57h+var_80], rcx
0x180003d23  mov     dword ptr [rcx+0Ch], 1
0x180003d2a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable'
0x180003d31  mov     [rcx], rax
0x180003d34  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180003d3b  test    rcx, rcx
0x180003d3e  jz      short loc_180003D4D
0x180003d40  mov     rax, [rcx]
0x180003d43  mov     rax, [rax+8]
0x180003d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d4c  nop
0x180003d4d  lea     rax, ??_7SoftwareBitmapState@@6B@; const SoftwareBitmapState::`vftable'
0x180003d54  mov     [rbx], rax
0x180003d57  mov     rcx, rdi
0x180003d5a  call    ?GetFormat@MediaFrameHelpers@@SA?AW4BitmapPixelFormat@Imaging@Graphics@Windows@@AEBV?$ComPtr@UIWICBitmap@@@WRL@Microsoft@@@Z; MediaFrameHelpers::GetFormat(Microsoft::WRL::ComPtr<IWICBitmap> const &)
0x180003d5f  mov     [rbx+10h], eax
0x180003d62  mov     rcx, rdi
0x180003d65  call    ?GetAlpha@MediaFrameHelpers@@SA?AW4BitmapAlphaMode@Imaging@Graphics@Windows@@AEBV?$ComPtr@UIWICBitmap@@@WRL@Microsoft@@@Z; MediaFrameHelpers::GetAlpha(Microsoft::WRL::ComPtr<IWICBitmap> const &)
0x180003d6a  mov     [rbx+14h], eax
0x180003d6d  xor     r15d, r15d
0x180003d70  mov     [rbp+57h+var_B0], r15d
0x180003d74  mov     [rbp+57h+var_AC], r15d
0x180003d78  mov     rcx, [rdi]
0x180003d7b  mov     rax, [rcx]
0x180003d7e  lea     r8, [rbp+57h+var_AC]
0x180003d82  lea     rdx, [rbp+57h+var_B0]
0x180003d86  mov     rax, [rax+18h]
0x180003d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d8f  test    eax, eax
0x180003d91  js      loc_180003F8B
0x180003d97  mov     eax, [rbp+57h+var_B0]
0x180003d9a  mov     [rbx+18h], eax
0x180003d9d  mov     [rbp+57h+var_AC], r15d
0x180003da1  mov     [rbp+57h+var_B0], r15d
0x180003da5  mov     rcx, [rdi]
0x180003da8  mov     rax, [rcx]
0x180003dab  lea     r8, [rbp+57h+var_B0]
0x180003daf  lea     rdx, [rbp+57h+var_AC]
0x180003db3  mov     rax, [rax+18h]
0x180003db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dbc  test    eax, eax
0x180003dbe  js      loc_180003FA7
0x180003dc4  mov     eax, [rbp+57h+var_B0]
0x180003dc7  mov     [rbx+1Ch], eax
0x180003dca  movups  xmm0, xmmword ptr [rsi]
0x180003dcd  movups  xmmword ptr [rbx+20h], xmm0
0x180003dd1  mov     rax, 4058000000000000h
0x180003ddb  mov     [rbx+30h], rax
0x180003ddf  mov     [rbx+38h], rax
0x180003de3  mov     [rbx+40h], r15d
0x180003de7  mov     [rbx+44h], r15b
0x180003deb  mov     [rbx+48h], r15
0x180003def  mov     [rbx+50h], r15
0x180003df3  mov     [rbx+58h], r15
0x180003df7  mov     [rbx+60h], r15
0x180003dfb  mov     rcx, [rdi]
0x180003dfe  mov     [rbx+68h], rcx
0x180003e02  test    rcx, rcx
0x180003e05  jz      short loc_180003E14
0x180003e07  mov     rax, [rcx]
0x180003e0a  mov     rax, [rax+8]
0x180003e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e13  nop
0x180003e14  mov     [rbx+70h], r15
0x180003e18  lea     rcx, [rbx+78h]; SRWLock
0x180003e1c  call    cs:__imp_InitializeSRWLock
0x180003e22  mov     eax, cs:dword_1800710A0
0x180003e28  cmp     eax, 5
0x180003e2b  jbe     loc_180003EDF
0x180003e31  mov     eax, [rbx+10h]
0x180003e34  mov     [rbp+57h+var_AC], eax
0x180003e37  mov     [rbp+57h+var_88], rbx
0x180003e3b  lea     rax, [rbp+57h+var_AC]
0x180003e3f  mov     [rbp+57h+var_40], rax
0x180003e43  mov     [rbp+57h+var_38], 4
0x180003e4b  lea     rax, [rbp+57h+var_88]
0x180003e4f  mov     [rbp+57h+var_50], rax
0x180003e53  mov     [rbp+57h+var_48], 8
0x180003e5b  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180003e62  movzx   eax, cs:word_18006591E
0x180003e69  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180003e6c  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x180003e70  mov     rax, cs:off_1800710A8
0x180003e77  mov     [rbp+57h+var_70.Ptr], rax
0x180003e7b  movzx   eax, word ptr [rax]
0x180003e7e  mov     [rbp+57h+var_70.Size], eax
0x180003e81  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x180003e88  lea     rax, unk_180065928
0x180003e8f  mov     [rbp+57h+var_60], rax
0x180003e93  mov     [rbp+57h+var_58], 30h ; '0'
0x180003e9a  mov     [rbp+57h+var_54], 1
0x180003ea1  lea     rax, _TraceLoggingMetadataEnd
0x180003ea8  lea     rcx, _TraceLoggingMetadata
0x180003eaf  sub     eax, ecx
0x180003eb1  mov     [rbp+57h+var_B0], eax
0x180003eb4  mov     eax, [rbp+57h+var_B0]
0x180003eb7  lea     rax, [rbp+57h+var_70]
0x180003ebb  mov     [rsp+100h+UserData], rax; UserData
0x180003ec0  mov     [rsp+100h+UserDataCount], 4; UserDataCount
0x180003ec8  xor     r9d, r9d; RelatedActivityId
0x180003ecb  xor     r8d, r8d; ActivityId
0x180003ece  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180003ed2  mov     rcx, cs:RegHandle; RegHandle
0x180003ed9  call    cs:__imp_EventWriteTransfer
0x180003edf  mov     rcx, rbx; this
0x180003ee2  call    ?ValidateState@SoftwareBitmapState@@AEAAXXZ; SoftwareBitmapState::ValidateState(void)
0x180003ee7  mov     rcx, [rdi]
0x180003eea  mov     rax, [rcx]
0x180003eed  lea     r8, [rbx+38h]
0x180003ef1  lea     rdx, [rbx+30h]
0x180003ef5  mov     rax, [rax+28h]
0x180003ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003efe  test    eax, eax
0x180003f00  js      short loc_180003F6F
0x180003f02  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180003f09  jb      short loc_180003F49
0x180003f0b  mov     edx, 0Bh
0x180003f10  movups  xmm0, xmmword ptr [rbx+30h]
0x180003f14  movups  [rsp+100h+var_C0], xmm0
0x180003f19  mov     ecx, [rbx+1Ch]
0x180003f1c  mov     [rsp+100h+var_C8], ecx
0x180003f20  mov     ecx, [rbx+18h]
0x180003f23  mov     [rsp+100h+var_D0], ecx
0x180003f27  mov     ecx, [rbx+14h]
0x180003f2a  mov     dword ptr [rsp+100h+UserData], ecx
0x180003f2e  mov     ecx, [rbx+10h]
0x180003f31  mov     [rsp+100h+UserDataCount], ecx
0x180003f35  mov     r9, rbx
0x180003f38  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f3f  mov     rcx, [rcx+10h]
0x180003f43  call    WPP_SF_qddddgg
0x180003f48  nop
0x180003f49  mov     rax, rbx
0x180003f4c  mov     rcx, [rbp+57h+var_30]
0x180003f50  xor     rcx, rsp; StackCookie
0x180003f53  call    __security_check_cookie
0x180003f58  mov     rbx, [rsp+100h+arg_10]
0x180003f60  add     rsp, 0E0h
0x180003f67  pop     r15
0x180003f69  pop     r14
0x180003f6b  pop     rdi
0x180003f6c  pop     rsi
0x180003f6d  pop     rbp
0x180003f6e  retn
0x180003f6f  mov     edx, eax; int
0x180003f71  lea     rcx, [rbp+57h+EventDescriptor]; this
0x180003f75  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x180003f7a  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180003f81  lea     rcx, [rbp+57h+EventDescriptor]; pExceptionObject
0x180003f85  call    _CxxThrowException_0
0x180003f8b  mov     edx, eax; int
0x180003f8d  lea     rcx, [rbp+57h+EventDescriptor]; this
0x180003f91  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x180003f96  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180003f9d  lea     rcx, [rbp+57h+EventDescriptor]; pExceptionObject
0x180003fa1  call    _CxxThrowException_0
0x180003fa7  mov     edx, eax; int
0x180003fa9  lea     rcx, [rbp+57h+EventDescriptor]; this
0x180003fad  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x180003fb2  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180003fb9  lea     rcx, [rbp+57h+EventDescriptor]; pExceptionObject
0x180003fbd  call    _CxxThrowException_0
```
