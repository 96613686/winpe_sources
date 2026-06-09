# SoftwareBitmapState::SoftwareBitmapState(Microsoft::WRL::ComPtr<IMF2DBuffer2> const &,_GUID const &,int,int,tagRECT const &)

- ea: `0x180007110`
- end: `0x180007635`
- name: `??0SoftwareBitmapState@@QEAA@AEBV?$ComPtr@UIMF2DBuffer2@@@WRL@Microsoft@@AEBU_GUID@@HHAEBUtagRECT@@@Z`
- size: `1317`
- prototype: `__int64 __usercall@<rax>(SoftwareBitmapState *this@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180006ed8`

## callees

- `0x180004060`
- `0x180007110`
- `0x180015920`
- `0x18001b790`
- `0x18001c710`
- `0x180026920`
- `0x18002749c`
- `0x180034888`
- `0x180038b78`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800073c8`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800073c8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007485`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007485`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
SoftwareBitmapState *__fastcall SoftwareBitmapState::SoftwareBitmapState(
        SoftwareBitmapState *this,
        _QWORD *a2,
        _QWORD *a3,
        int a4,
        int a5,
        _OWORD *a6)
{
  int v10; // eax
  int v11; // eax
  int (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  int v13; // eax
  struct IErrorInfo *v14; // r8
  bool v15; // r9
  int v16; // eax
  struct IErrorInfo *v17; // r8
  bool v18; // r9
  int v19; // eax
  bool v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rcx
  _DWORD v24[2]; // [rsp+50h] [rbp-79h] BYREF
  __int64 v25; // [rsp+58h] [rbp-71h] BYREF
  int v26; // [rsp+60h] [rbp-69h] BYREF
  __int64 v27; // [rsp+68h] [rbp-61h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-59h] BYREF
  _QWORD v29[2]; // [rsp+90h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-29h] BYREF
  int *v31; // [rsp+B0h] [rbp-19h]
  int v32; // [rsp+B8h] [rbp-11h]
  int v33; // [rsp+BCh] [rbp-Dh]
  _QWORD *v34; // [rsp+C0h] [rbp-9h]
  __int64 v35; // [rsp+C8h] [rbp-1h]
  int *v36; // [rsp+D0h] [rbp+7h]
  __int64 v37; // [rsp+D8h] [rbp+Fh]

  v29[1] = this;
  *((_DWORD *)this + 3) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &SoftwareBitmapState::`vftable';
  if ( *a3 == *(_QWORD *)&MFVideoFormat_ARGB32.Data1 && a3[1] == *(_QWORD *)MFVideoFormat_ARGB32.Data4
    || *a3 == *(_QWORD *)&MFVideoFormat_RGB32.Data1 && a3[1] == *(_QWORD *)MFVideoFormat_RGB32.Data4 )
  {
    v10 = 87;
  }
  else if ( *a3 == *(_QWORD *)&MFVideoFormat_NV12.Data1 && a3[1] == *(_QWORD *)MFVideoFormat_NV12.Data4 )
  {
    v10 = 103;
  }
  else if ( *a3 == *(_QWORD *)&MFVideoFormat_P010.Data1 && a3[1] == *(_QWORD *)MFVideoFormat_P010.Data4 )
  {
    v10 = 104;
  }
  else if ( *a3 == *(_QWORD *)&MFVideoFormat_YUY2.Data1 && a3[1] == *(_QWORD *)MFVideoFormat_YUY2.Data4 )
  {
    v10 = 107;
  }
  else if ( *a3 == *(_QWORD *)&MFVideoFormat_L8.Data1 && a3[1] == *(_QWORD *)MFVideoFormat_L8.Data4 )
  {
    v10 = 62;
  }
  else
  {
    if ( (*a3 != *(_QWORD *)&MFVideoFormat_L16.Data1 || a3[1] != *(_QWORD *)MFVideoFormat_L16.Data4)
      && (*a3 != *(_QWORD *)&MFVideoFormat_D16.Data1 || a3[1] != *(_QWORD *)MFVideoFormat_D16.Data4) )
    {
      MF::ThrowOriginateError<16>();
    }
    v10 = 57;
  }
  *((_DWORD *)this + 4) = v10;
  if ( *a3 == *(_QWORD *)&MFVideoFormat_ARGB32.Data1 && a3[1] == *(_QWORD *)MFVideoFormat_ARGB32.Data4 )
  {
    v11 = 1;
  }
  else
  {
    if ( (*a3 != *(_QWORD *)&MFVideoFormat_RGB32.Data1 || a3[1] != *(_QWORD *)MFVideoFormat_RGB32.Data4)
      && (*a3 != *(_QWORD *)&MFVideoFormat_NV12.Data1 || a3[1] != *(_QWORD *)MFVideoFormat_NV12.Data4)
      && (*a3 != *(_QWORD *)&MFVideoFormat_P010.Data1 || a3[1] != *(_QWORD *)MFVideoFormat_P010.Data4)
      && (*a3 != *(_QWORD *)&MFVideoFormat_YUY2.Data1 || a3[1] != *(_QWORD *)MFVideoFormat_YUY2.Data4)
      && (*a3 != *(_QWORD *)&MFVideoFormat_L8.Data1 || a3[1] != *(_QWORD *)MFVideoFormat_L8.Data4)
      && (*a3 != *(_QWORD *)&MFVideoFormat_L16.Data1 || a3[1] != *(_QWORD *)MFVideoFormat_L16.Data4)
      && (*a3 != *(_QWORD *)&MFVideoFormat_D16.Data1 || a3[1] != *(_QWORD *)MFVideoFormat_D16.Data4) )
    {
      MF::ThrowOriginateError<16>();
    }
    v11 = 2;
  }
  *((_DWORD *)this + 5) = v11;
  *((_DWORD *)this + 6) = a4;
  *((_DWORD *)this + 7) = a5;
  *((_OWORD *)this + 2) = *a6;
  *((_QWORD *)this + 6) = 0x4058000000000000LL;
  *((_QWORD *)this + 7) = 0x4058000000000000LL;
  *((_DWORD *)this + 16) = 0;
  *((_BYTE *)this + 68) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  v12 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*a2;
  *((_QWORD *)this + 11) = *a2;
  if ( v12 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v12)[1])(v12);
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  InitializeSRWLock((PSRWLOCK)this + 15);
  if ( (unsigned int)dword_1800710A0 > 5 )
  {
    v26 = *((_DWORD *)this + 4);
    v29[0] = this;
    v36 = &v26;
    v37 = 4;
    v34 = v29;
    v35 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 261;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_1800710A8;
    UserData.Size = *(unsigned __int16 *)off_1800710A8;
    UserData.Reserved = 2;
    v31 = &dword_1800658EC;
    v32 = 48;
    v33 = 1;
    v24[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  SoftwareBitmapState::ValidateState(this);
  v27 = 0;
  if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*a2)(*a2, &GUID_e7174cfa_1c9e_48b1_8866_626226bfc258, &v27) >= 0 )
    MF::ThrowOriginateError<29>(2147942487LL, L"MF DXGI buffer not supported");
  MF::As<IMFMediaBuffer,IMF2DBuffer2>(&v25, a2);
  v24[0] = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v25 + 40LL))(v25, v24);
  if ( v13 < 0 )
  {
    _com_error::_com_error((_com_error *)&EventDescriptor, v13, v14, v15);
    throw (_com_error *)&EventDescriptor;
  }
  if ( !v24[0] )
  {
    v16 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(*(_QWORD *)*a2 + 56LL))(*a2, v24);
    if ( v16 < 0 )
    {
      _com_error::_com_error((_com_error *)&EventDescriptor, v16, v17, v18);
      throw (_com_error *)&EventDescriptor;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 48LL))(v25, v24[0]);
    if ( v19 < 0 )
    {
      _com_error::_com_error((_com_error *)&EventDescriptor, v19, v14, v20);
      throw (_com_error *)&EventDescriptor;
    }
  }
  if ( g_wppLevels >= 0x20u )
    WPP_SF_qddddgg(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      v14,
      this,
      *((_DWORD *)this + 4),
      *((_DWORD *)this + 5),
      *((_DWORD *)this + 6),
      *((_DWORD *)this + 7),
      *((_QWORD *)this + 6),
      *((_QWORD *)this + 7));
  v21 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return this;
}

```

## disassembly

```asm
0x180007110  mov     [rsp-8+arg_10], rbx
0x180007115  push    rbp
0x180007116  push    rsi
0x180007117  push    rdi
0x180007118  push    r14
0x18000711a  push    r15
0x18000711c  lea     rbp, [rsp-27h]
0x180007121  sub     rsp, 0F0h
0x180007128  mov     rax, cs:__security_cookie
0x18000712f  xor     rax, rsp
0x180007132  mov     [rbp+47h+var_30], rax
0x180007136  mov     r14d, r9d
0x180007139  mov     rbx, r8
0x18000713c  mov     rsi, rdx
0x18000713f  mov     rdi, rcx
0x180007142  mov     [rbp+47h+var_78], rcx
0x180007146  xor     r15d, r15d
0x180007149  mov     dword ptr [rcx+0Ch], 1
0x180007150  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable'
0x180007157  mov     [rcx], rax
0x18000715a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007161  test    rcx, rcx
0x180007164  jz      short loc_180007173
0x180007166  mov     rax, [rcx]
0x180007169  mov     rax, [rax+8]
0x18000716d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007172  nop
0x180007173  lea     rax, ??_7SoftwareBitmapState@@6B@; const SoftwareBitmapState::`vftable'
0x18000717a  mov     [rdi], rax
0x18000717d  mov     rax, [rbx]
0x180007180  cmp     rax, qword ptr cs:MFVideoFormat_ARGB32.Data1
0x180007187  jnz     short loc_180007196
0x180007189  mov     rax, [rbx+8]
0x18000718d  cmp     rax, qword ptr cs:MFVideoFormat_ARGB32.Data4
0x180007194  jz      short loc_1800071AF
0x180007196  mov     rax, [rbx]
0x180007199  cmp     rax, qword ptr cs:MFVideoFormat_RGB32.Data1
0x1800071a0  jnz     short loc_1800071B9
0x1800071a2  mov     rax, [rbx+8]
0x1800071a6  cmp     rax, qword ptr cs:MFVideoFormat_RGB32.Data4
0x1800071ad  jnz     short loc_1800071B9
0x1800071af  mov     eax, 57h ; 'W'
0x1800071b4  jmp     loc_18000727B
0x1800071b9  mov     rax, [rbx]
0x1800071bc  cmp     rax, qword ptr cs:MFVideoFormat_NV12.Data1
0x1800071c3  jnz     short loc_1800071DC
0x1800071c5  mov     rax, [rbx+8]
0x1800071c9  cmp     rax, qword ptr cs:MFVideoFormat_NV12.Data4
0x1800071d0  jnz     short loc_1800071DC
0x1800071d2  mov     eax, 67h ; 'g'
0x1800071d7  jmp     loc_18000727B
0x1800071dc  mov     rax, [rbx]
0x1800071df  cmp     rax, qword ptr cs:MFVideoFormat_P010.Data1
0x1800071e6  jnz     short loc_1800071FC
0x1800071e8  mov     rax, [rbx+8]
0x1800071ec  cmp     rax, qword ptr cs:MFVideoFormat_P010.Data4
0x1800071f3  jnz     short loc_1800071FC
0x1800071f5  mov     eax, 68h ; 'h'
0x1800071fa  jmp     short loc_18000727B
0x1800071fc  mov     rax, [rbx]
0x1800071ff  cmp     rax, qword ptr cs:MFVideoFormat_YUY2.Data1
0x180007206  jnz     short loc_18000721C
0x180007208  mov     rax, [rbx+8]
0x18000720c  cmp     rax, qword ptr cs:MFVideoFormat_YUY2.Data4
0x180007213  jnz     short loc_18000721C
0x180007215  mov     eax, 6Bh ; 'k'
0x18000721a  jmp     short loc_18000727B
0x18000721c  mov     rax, [rbx]
0x18000721f  cmp     rax, qword ptr cs:MFVideoFormat_L8.Data1
0x180007226  jnz     short loc_18000723C
0x180007228  mov     rax, [rbx+8]
0x18000722c  cmp     rax, qword ptr cs:MFVideoFormat_L8.Data4
0x180007233  jnz     short loc_18000723C
0x180007235  mov     eax, 3Eh ; '>'
0x18000723a  jmp     short loc_18000727B
0x18000723c  mov     rax, [rbx]
0x18000723f  cmp     rax, qword ptr cs:MFVideoFormat_L16.Data1
0x180007246  jnz     short loc_180007255
0x180007248  mov     rax, [rbx+8]
0x18000724c  cmp     rax, qword ptr cs:MFVideoFormat_L16.Data4
0x180007253  jz      short loc_180007276
0x180007255  mov     rax, [rbx]
0x180007258  cmp     rax, qword ptr cs:MFVideoFormat_D16.Data1
0x18000725f  jnz     loc_1800075C9
0x180007265  mov     rax, [rbx+8]
0x180007269  cmp     rax, qword ptr cs:MFVideoFormat_D16.Data4
0x180007270  jnz     loc_1800075C9
0x180007276  mov     eax, 39h ; '9'
0x18000727b  mov     [rdi+10h], eax
0x18000727e  mov     rax, [rbx]
0x180007281  cmp     rax, qword ptr cs:MFVideoFormat_ARGB32.Data1
0x180007288  jnz     short loc_1800072A1
0x18000728a  mov     rax, [rbx+8]
0x18000728e  cmp     rax, qword ptr cs:MFVideoFormat_ARGB32.Data4
0x180007295  jnz     short loc_1800072A1
0x180007297  mov     eax, 1
0x18000729c  jmp     loc_180007365
0x1800072a1  mov     rax, [rbx]
0x1800072a4  cmp     rax, qword ptr cs:MFVideoFormat_RGB32.Data1
0x1800072ab  jnz     short loc_1800072BE
0x1800072ad  mov     rax, [rbx+8]
0x1800072b1  cmp     rax, qword ptr cs:MFVideoFormat_RGB32.Data4
0x1800072b8  jz      loc_180007360
0x1800072be  mov     rax, [rbx]
0x1800072c1  cmp     rax, qword ptr cs:MFVideoFormat_NV12.Data1
0x1800072c8  jnz     short loc_1800072DB
0x1800072ca  mov     rax, [rbx+8]
0x1800072ce  cmp     rax, qword ptr cs:MFVideoFormat_NV12.Data4
0x1800072d5  jz      loc_180007360
0x1800072db  mov     rax, [rbx]
0x1800072de  cmp     rax, qword ptr cs:MFVideoFormat_P010.Data1
0x1800072e5  jnz     short loc_1800072F4
0x1800072e7  mov     rax, [rbx+8]
0x1800072eb  cmp     rax, qword ptr cs:MFVideoFormat_P010.Data4
0x1800072f2  jz      short loc_180007360
0x1800072f4  mov     rax, [rbx]
0x1800072f7  cmp     rax, qword ptr cs:MFVideoFormat_YUY2.Data1
0x1800072fe  jnz     short loc_18000730D
0x180007300  mov     rax, [rbx+8]
0x180007304  cmp     rax, qword ptr cs:MFVideoFormat_YUY2.Data4
0x18000730b  jz      short loc_180007360
0x18000730d  mov     rax, [rbx]
0x180007310  cmp     rax, qword ptr cs:MFVideoFormat_L8.Data1
0x180007317  jnz     short loc_180007326
0x180007319  mov     rax, [rbx+8]
0x18000731d  cmp     rax, qword ptr cs:MFVideoFormat_L8.Data4
0x180007324  jz      short loc_180007360
0x180007326  mov     rax, [rbx]
0x180007329  cmp     rax, qword ptr cs:MFVideoFormat_L16.Data1
0x180007330  jnz     short loc_18000733F
0x180007332  mov     rax, [rbx+8]
0x180007336  cmp     rax, qword ptr cs:MFVideoFormat_L16.Data4
0x18000733d  jz      short loc_180007360
0x18000733f  mov     rax, [rbx]
0x180007342  cmp     rax, qword ptr cs:MFVideoFormat_D16.Data1
0x180007349  jnz     loc_1800075C3
0x18000734f  mov     rax, [rbx+8]
0x180007353  cmp     rax, qword ptr cs:MFVideoFormat_D16.Data4
0x18000735a  jnz     loc_1800075C3
0x180007360  mov     eax, 2
0x180007365  mov     [rdi+14h], eax
0x180007368  mov     [rdi+18h], r14d
0x18000736c  mov     eax, [rbp+47h+arg_20]
0x18000736f  mov     [rdi+1Ch], eax
0x180007372  mov     rax, [rbp+47h+arg_28]
0x180007376  movups  xmm0, xmmword ptr [rax]
0x180007379  movups  xmmword ptr [rdi+20h], xmm0
0x18000737d  mov     rax, 4058000000000000h
0x180007387  mov     [rdi+30h], rax
0x18000738b  mov     [rdi+38h], rax
0x18000738f  mov     [rdi+40h], r15d
0x180007393  mov     byte ptr [rdi+44h], 0
0x180007397  mov     [rdi+48h], r15
0x18000739b  mov     [rdi+50h], r15
0x18000739f  mov     rcx, [rsi]
0x1800073a2  mov     [rdi+58h], rcx
0x1800073a6  test    rcx, rcx
0x1800073a9  jz      short loc_1800073B8
0x1800073ab  mov     rax, [rcx]
0x1800073ae  mov     rax, [rax+8]
0x1800073b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073b7  nop
0x1800073b8  mov     [rdi+60h], r15
0x1800073bc  mov     [rdi+68h], r15
0x1800073c0  mov     [rdi+70h], r15
0x1800073c4  lea     rcx, [rdi+78h]; SRWLock
0x1800073c8  call    cs:__imp_InitializeSRWLock
0x1800073ce  mov     eax, cs:dword_1800710A0
0x1800073d4  cmp     eax, 5
0x1800073d7  jbe     loc_18000748B
0x1800073dd  mov     eax, [rdi+10h]
0x1800073e0  mov     [rbp+47h+var_B0], eax
0x1800073e3  mov     [rbp+47h+var_80], rdi
0x1800073e7  lea     rax, [rbp+47h+var_B0]
0x1800073eb  mov     [rbp+47h+var_40], rax
0x1800073ef  mov     [rbp+47h+var_38], 4
0x1800073f7  lea     rax, [rbp+47h+var_80]
0x1800073fb  mov     [rbp+47h+var_50], rax
0x1800073ff  mov     [rbp+47h+var_48], 8
0x180007407  mov     dword ptr [rbp+47h+EventDescriptor.Id], 0B000000h
0x18000740e  movzx   eax, cs:word_1800658E2
0x180007415  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x180007418  mov     [rbp+47h+EventDescriptor.Keyword], r15
0x18000741c  mov     rax, cs:off_1800710A8
0x180007423  mov     [rbp+47h+var_70.Ptr], rax
0x180007427  movzx   eax, word ptr [rax]
0x18000742a  mov     [rbp+47h+var_70.Size], eax
0x18000742d  mov     dword ptr [rbp+47h+var_70.0Ch], 2
0x180007434  lea     rax, dword_1800658EC
0x18000743b  mov     [rbp+47h+var_60], rax
0x18000743f  mov     [rbp+47h+var_58], 30h ; '0'
0x180007446  mov     [rbp+47h+var_54], 1
0x18000744d  lea     rax, _TraceLoggingMetadataEnd
0x180007454  lea     rcx, _TraceLoggingMetadata
0x18000745b  sub     eax, ecx
0x18000745d  mov     [rbp+47h+var_BC], eax
0x180007460  mov     eax, [rbp+47h+var_BC]
0x180007463  lea     rax, [rbp+47h+var_70]
0x180007467  mov     [rsp+110h+UserData], rax; UserData
0x18000746c  mov     [rsp+110h+UserDataCount], 4; UserDataCount
0x180007474  xor     r9d, r9d; RelatedActivityId
0x180007477  xor     r8d, r8d; ActivityId
0x18000747a  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x18000747e  mov     rcx, cs:RegHandle; RegHandle
0x180007485  call    cs:__imp_EventWriteTransfer
0x18000748b  mov     rcx, rdi; this
0x18000748e  call    ?ValidateState@SoftwareBitmapState@@AEAAXXZ; SoftwareBitmapState::ValidateState(void)
0x180007493  mov     [rbp+47h+var_A8], r15
0x180007497  mov     rcx, [rsi]
0x18000749a  mov     rax, [rcx]
0x18000749d  lea     r8, [rbp+47h+var_A8]
0x1800074a1  lea     rdx, _GUID_e7174cfa_1c9e_48b1_8866_626226bfc258
0x1800074a8  mov     rax, [rax]
0x1800074ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074b0  nop
0x1800074b1  test    eax, eax
0x1800074b3  jns     loc_1800075CF
0x1800074b9  mov     rdx, rsi
0x1800074bc  lea     rcx, [rbp+47h+var_B8]
0x1800074c0  call    ??$As@UIMFMediaBuffer@@UIMF2DBuffer2@@@MF@@YA?AV?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@AEBV?$ComPtr@UIMF2DBuffer2@@@23@@Z; MF::As<IMFMediaBuffer,IMF2DBuffer2>(Microsoft::WRL::ComPtr<IMF2DBuffer2> const &)
0x1800074c5  nop
0x1800074c6  mov     [rbp+47h+var_C0], r15d
0x1800074ca  mov     rcx, [rbp+47h+var_B8]
0x1800074ce  mov     rax, [rcx]
0x1800074d1  lea     rdx, [rbp+47h+var_C0]
0x1800074d5  mov     rax, [rax+28h]
0x1800074d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074de  test    eax, eax
0x1800074e0  js      loc_1800075E1
0x1800074e6  cmp     [rbp+47h+var_C0], 0
0x1800074ea  jnz     short loc_180007522
0x1800074ec  mov     rcx, [rsi]
0x1800074ef  mov     rax, [rcx]
0x1800074f2  lea     rdx, [rbp+47h+var_C0]
0x1800074f6  mov     rax, [rax+38h]
0x1800074fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074ff  test    eax, eax
0x180007501  js      loc_1800075FD
0x180007507  mov     rcx, [rbp+47h+var_B8]
0x18000750b  mov     rax, [rcx]
0x18000750e  mov     edx, [rbp+47h+var_C0]
0x180007511  mov     rax, [rax+30h]
0x180007515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000751a  test    eax, eax
0x18000751c  js      loc_180007619
0x180007522  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180007529  jb      short loc_180007569
0x18000752b  mov     edx, 0Ch
0x180007530  movups  xmm0, xmmword ptr [rdi+30h]
0x180007534  movups  [rsp+110h+var_D0], xmm0
0x180007539  mov     eax, [rdi+1Ch]
0x18000753c  mov     [rsp+110h+var_D8], eax
0x180007540  mov     eax, [rdi+18h]
0x180007543  mov     [rsp+110h+var_E0], eax
0x180007547  mov     eax, [rdi+14h]
0x18000754a  mov     dword ptr [rsp+110h+UserData], eax
0x18000754e  mov     eax, [rdi+10h]
0x180007551  mov     [rsp+110h+UserDataCount], eax
0x180007555  mov     r9, rdi
0x180007558  mov     rcx, cs:WPP_GLOBAL_Control
0x18000755f  mov     rcx, [rcx+10h]
0x180007563  call    WPP_SF_qddddgg
0x180007568  nop
0x180007569  mov     rcx, [rbp+47h+var_B8]
0x18000756d  test    rcx, rcx
0x180007570  jz      short loc_180007583
0x180007572  mov     [rbp+47h+var_B8], r15
0x180007576  mov     rax, [rcx]
0x180007579  mov     rax, [rax+10h]
0x18000757d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007582  nop
0x180007583  mov     rcx, [rbp+47h+var_A8]
0x180007587  test    rcx, rcx
0x18000758a  jz      short loc_18000759D
0x18000758c  mov     [rbp+47h+var_A8], r15
0x180007590  mov     rdx, [rcx]
0x180007593  mov     rax, [rdx+10h]
0x180007597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000759c  nop
0x18000759d  mov     rax, rdi
0x1800075a0  mov     rcx, [rbp+47h+var_30]
0x1800075a4  xor     rcx, rsp; StackCookie
0x1800075a7  call    __security_check_cookie
0x1800075ac  mov     rbx, [rsp+110h+arg_10]
0x1800075b4  add     rsp, 0F0h
0x1800075bb  pop     r15
0x1800075bd  pop     r14
0x1800075bf  pop     rdi
0x1800075c0  pop     rsi
0x1800075c1  pop     rbp
0x1800075c2  retn
0x1800075c3  call    ??$ThrowOriginateError@$0BA@@MF@@YAXJAEAY0BA@$$CBG@Z; MF::ThrowOriginateError<16>(long,ushort const (&)[16])
0x1800075c9  call    ??$ThrowOriginateError@$0BA@@MF@@YAXJAEAY0BA@$$CBG@Z; MF::ThrowOriginateError<16>(long,ushort const (&)[16])
0x1800075cf  lea     rdx, aMfDxgiBufferNo; "MF DXGI buffer not supported"
0x1800075d6  mov     ecx, 80070057h
0x1800075db  call    ??$ThrowOriginateError@$0BN@@MF@@YAXJAEAY0BN@$$CBG@Z; MF::ThrowOriginateError<29>(long,ushort const (&)[29])
0x1800075e1  mov     edx, eax; int
0x1800075e3  lea     rcx, [rbp+47h+EventDescriptor]; this
0x1800075e7  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x1800075ec  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
  ... truncated ...
```
