# SoftwareBitmapState::SoftwareBitmapState(Microsoft::WRL::ComPtr<IWICBitmap> const &)

- ea: `0x180012660`
- end: `0x180012936`
- name: `??0SoftwareBitmapState@@QEAA@AEBV?$ComPtr@UIWICBitmap@@@WRL@Microsoft@@@Z`
- size: `726`
- prototype: `SoftwareBitmapState *__fastcall(SoftwareBitmapState *this, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180012580`

## callees

- `0x180012660`
- `0x1800148e0`
- `0x180015290`
- `0x180015920`
- `0x18001b790`
- `0x18001c710`
- `0x180026920`
- `0x18002749c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001278f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001278f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001284c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001284c`

## pseudocode

```c
SoftwareBitmapState *__fastcall SoftwareBitmapState::SoftwareBitmapState(SoftwareBitmapState *this, _QWORD *a2)
{
  int v4; // eax
  struct IErrorInfo *v5; // r8
  bool v6; // r9
  int v7; // eax
  struct IErrorInfo *v8; // r8
  bool v9; // r9
  unsigned int v10; // ecx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  struct IErrorInfo *v14; // r8
  bool v15; // r9
  unsigned int v17; // [rsp+50h] [rbp-59h] BYREF
  int v18; // [rsp+54h] [rbp-55h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-51h] BYREF
  _QWORD v20[3]; // [rsp+78h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-19h] BYREF
  int *v22; // [rsp+A0h] [rbp-9h]
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
  v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, int *))(*(_QWORD *)*a2 + 24LL))(*a2, &v17, &v18);
  if ( v4 < 0 )
  {
    _com_error::_com_error((_com_error *)&EventDescriptor, v4, v5, v6);
    throw (_com_error *)&EventDescriptor;
  }
  *((_DWORD *)this + 6) = v17;
  v18 = 0;
  v17 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, int *, unsigned int *))(*(_QWORD *)*a2 + 24LL))(*a2, &v18, &v17);
  if ( v7 < 0 )
  {
    _com_error::_com_error((_com_error *)&EventDescriptor, v7, v8, v9);
    throw (_com_error *)&EventDescriptor;
  }
  v10 = v17;
  *((_DWORD *)this + 7) = v17;
  v11 = *((_DWORD *)this + 6);
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = v11;
  *((_DWORD *)this + 11) = v10;
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
    v22 = &dword_180065964;
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
      10,
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
0x180012660  mov     [rsp-8+arg_10], rbx
0x180012665  push    rbp
0x180012666  push    rsi
0x180012667  push    rdi
0x180012668  push    r14
0x18001266a  push    r15
0x18001266c  lea     rbp, [rsp-37h]
0x180012671  sub     rsp, 0E0h
0x180012678  mov     rax, cs:__security_cookie
0x18001267f  xor     rax, rsp
0x180012682  mov     [rbp+57h+var_30], rax
0x180012686  mov     rdi, rdx
0x180012689  mov     rbx, rcx
0x18001268c  mov     [rbp+57h+var_80], rcx
0x180012690  mov     dword ptr [rcx+0Ch], 1
0x180012697  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable'
0x18001269e  mov     [rcx], rax
0x1800126a1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800126a8  test    rcx, rcx
0x1800126ab  jz      short loc_1800126BA
0x1800126ad  mov     rax, [rcx]
0x1800126b0  mov     rax, [rax+8]
0x1800126b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126b9  nop
0x1800126ba  lea     rax, ??_7SoftwareBitmapState@@6B@; const SoftwareBitmapState::`vftable'
0x1800126c1  mov     [rbx], rax
0x1800126c4  mov     rcx, rdi
0x1800126c7  call    ?GetFormat@MediaFrameHelpers@@SA?AW4BitmapPixelFormat@Imaging@Graphics@Windows@@AEBV?$ComPtr@UIWICBitmap@@@WRL@Microsoft@@@Z; MediaFrameHelpers::GetFormat(Microsoft::WRL::ComPtr<IWICBitmap> const &)
0x1800126cc  mov     [rbx+10h], eax
0x1800126cf  mov     rcx, rdi
0x1800126d2  call    ?GetAlpha@MediaFrameHelpers@@SA?AW4BitmapAlphaMode@Imaging@Graphics@Windows@@AEBV?$ComPtr@UIWICBitmap@@@WRL@Microsoft@@@Z; MediaFrameHelpers::GetAlpha(Microsoft::WRL::ComPtr<IWICBitmap> const &)
0x1800126d7  mov     [rbx+14h], eax
0x1800126da  xor     r15d, r15d
0x1800126dd  mov     [rbp+57h+var_B0], r15d
0x1800126e1  mov     [rbp+57h+var_AC], r15d
0x1800126e5  mov     rcx, [rdi]
0x1800126e8  mov     rax, [rcx]
0x1800126eb  lea     r8, [rbp+57h+var_AC]
0x1800126ef  lea     rdx, [rbp+57h+var_B0]
0x1800126f3  mov     rax, [rax+18h]
0x1800126f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126fc  test    eax, eax
0x1800126fe  js      loc_1800128FE
0x180012704  mov     eax, [rbp+57h+var_B0]
0x180012707  mov     [rbx+18h], eax
0x18001270a  mov     [rbp+57h+var_AC], r15d
0x18001270e  mov     [rbp+57h+var_B0], r15d
0x180012712  mov     rcx, [rdi]
0x180012715  mov     rax, [rcx]
0x180012718  lea     r8, [rbp+57h+var_B0]
0x18001271c  lea     rdx, [rbp+57h+var_AC]
0x180012720  mov     rax, [rax+18h]
0x180012724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012729  test    eax, eax
0x18001272b  js      loc_18001291A
0x180012731  mov     ecx, [rbp+57h+var_B0]
0x180012734  mov     [rbx+1Ch], ecx
0x180012737  mov     eax, [rbx+18h]
0x18001273a  mov     [rbx+20h], r15
0x18001273e  mov     [rbx+28h], eax
0x180012741  mov     [rbx+2Ch], ecx
0x180012744  mov     rax, 4058000000000000h
0x18001274e  mov     [rbx+30h], rax
0x180012752  mov     [rbx+38h], rax
0x180012756  mov     [rbx+40h], r15d
0x18001275a  mov     [rbx+44h], r15b
0x18001275e  mov     [rbx+48h], r15
0x180012762  mov     [rbx+50h], r15
0x180012766  mov     [rbx+58h], r15
0x18001276a  mov     [rbx+60h], r15
0x18001276e  mov     rcx, [rdi]
0x180012771  mov     [rbx+68h], rcx
0x180012775  test    rcx, rcx
0x180012778  jz      short loc_180012787
0x18001277a  mov     rax, [rcx]
0x18001277d  mov     rax, [rax+8]
0x180012781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012786  nop
0x180012787  mov     [rbx+70h], r15
0x18001278b  lea     rcx, [rbx+78h]; SRWLock
0x18001278f  call    cs:__imp_InitializeSRWLock
0x180012795  mov     eax, cs:dword_1800710A0
0x18001279b  cmp     eax, 5
0x18001279e  jbe     loc_180012852
0x1800127a4  mov     eax, [rbx+10h]
0x1800127a7  mov     [rbp+57h+var_AC], eax
0x1800127aa  mov     [rbp+57h+var_88], rbx
0x1800127ae  lea     rax, [rbp+57h+var_AC]
0x1800127b2  mov     [rbp+57h+var_40], rax
0x1800127b6  mov     [rbp+57h+var_38], 4
0x1800127be  lea     rax, [rbp+57h+var_88]
0x1800127c2  mov     [rbp+57h+var_50], rax
0x1800127c6  mov     [rbp+57h+var_48], 8
0x1800127ce  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800127d5  movzx   eax, cs:word_18006595A
0x1800127dc  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800127df  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x1800127e3  mov     rax, cs:off_1800710A8
0x1800127ea  mov     [rbp+57h+var_70.Ptr], rax
0x1800127ee  movzx   eax, word ptr [rax]
0x1800127f1  mov     [rbp+57h+var_70.Size], eax
0x1800127f4  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x1800127fb  lea     rax, dword_180065964
0x180012802  mov     [rbp+57h+var_60], rax
0x180012806  mov     [rbp+57h+var_58], 30h ; '0'
0x18001280d  mov     [rbp+57h+var_54], 1
0x180012814  lea     rax, _TraceLoggingMetadataEnd
0x18001281b  lea     rcx, _TraceLoggingMetadata
0x180012822  sub     eax, ecx
0x180012824  mov     [rbp+57h+var_B0], eax
0x180012827  mov     eax, [rbp+57h+var_B0]
0x18001282a  lea     rax, [rbp+57h+var_70]
0x18001282e  mov     [rsp+100h+UserData], rax; UserData
0x180012833  mov     [rsp+100h+UserDataCount], 4; UserDataCount
0x18001283b  xor     r9d, r9d; RelatedActivityId
0x18001283e  xor     r8d, r8d; ActivityId
0x180012841  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180012845  mov     rcx, cs:RegHandle; RegHandle
0x18001284c  call    cs:__imp_EventWriteTransfer
0x180012852  mov     rcx, rbx; this
0x180012855  call    ?ValidateState@SoftwareBitmapState@@AEAAXXZ; SoftwareBitmapState::ValidateState(void)
0x18001285a  mov     rcx, [rdi]
0x18001285d  mov     rax, [rcx]
0x180012860  lea     r8, [rbx+38h]
0x180012864  lea     rdx, [rbx+30h]
0x180012868  mov     rax, [rax+28h]
0x18001286c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012871  test    eax, eax
0x180012873  js      short loc_1800128E2
0x180012875  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x18001287c  jb      short loc_1800128BC
0x18001287e  mov     edx, 0Ah
0x180012883  movups  xmm0, xmmword ptr [rbx+30h]
0x180012887  movups  [rsp+100h+var_C0], xmm0
0x18001288c  mov     ecx, [rbx+1Ch]
0x18001288f  mov     [rsp+100h+var_C8], ecx
0x180012893  mov     ecx, [rbx+18h]
0x180012896  mov     [rsp+100h+var_D0], ecx
0x18001289a  mov     ecx, [rbx+14h]
0x18001289d  mov     dword ptr [rsp+100h+UserData], ecx
0x1800128a1  mov     ecx, [rbx+10h]
0x1800128a4  mov     [rsp+100h+UserDataCount], ecx
0x1800128a8  mov     r9, rbx
0x1800128ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128b2  mov     rcx, [rcx+10h]
0x1800128b6  call    WPP_SF_qddddgg
0x1800128bb  nop
0x1800128bc  mov     rax, rbx
0x1800128bf  mov     rcx, [rbp+57h+var_30]
0x1800128c3  xor     rcx, rsp; StackCookie
0x1800128c6  call    __security_check_cookie
0x1800128cb  mov     rbx, [rsp+100h+arg_10]
0x1800128d3  add     rsp, 0E0h
0x1800128da  pop     r15
0x1800128dc  pop     r14
0x1800128de  pop     rdi
0x1800128df  pop     rsi
0x1800128e0  pop     rbp
0x1800128e1  retn
0x1800128e2  mov     edx, eax; int
0x1800128e4  lea     rcx, [rbp+57h+EventDescriptor]; this
0x1800128e8  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x1800128ed  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x1800128f4  lea     rcx, [rbp+57h+EventDescriptor]; pExceptionObject
0x1800128f8  call    _CxxThrowException_0
0x1800128fe  mov     edx, eax; int
0x180012900  lea     rcx, [rbp+57h+EventDescriptor]; this
0x180012904  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x180012909  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180012910  lea     rcx, [rbp+57h+EventDescriptor]; pExceptionObject
0x180012914  call    _CxxThrowException_0
0x18001291a  mov     edx, eax; int
0x18001291c  lea     rcx, [rbp+57h+EventDescriptor]; this
0x180012920  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x180012925  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18001292c  lea     rcx, [rbp+57h+EventDescriptor]; pExceptionObject
0x180012930  call    _CxxThrowException_0
```
