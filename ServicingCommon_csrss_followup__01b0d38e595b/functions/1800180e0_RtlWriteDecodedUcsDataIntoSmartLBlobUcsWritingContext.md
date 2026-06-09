# RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext

- ea: `0x1800180e0`
- end: `0x1800183fb`
- name: `RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext`
- size: `795`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180018030`
- `0x1800642cc`
- `0x18006a8b0`
- `0x18006a980`

## callees

- `0x180017af0`
- `0x1800180e0`
- `0x180019fa8`
- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x18009e020`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x1800183ab`
- `ntdll!RtlRaiseStatus` at `0x1800183ab`

## string_xrefs

- `0x18001826b`: `RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext`
- `0x1800182a8`: `RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext`
- `0x1800182e8`: `RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext`
- `0x180018323`: `RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext`
- `0x18001834d`: `RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext`
- `0x1800183d2`: `RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext`

## pseudocode

```c
__int64 __fastcall RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext(
        int a1,
        _QWORD *a2,
        __int64 (__fastcall *a3)(),
        __int64 a4)
{
  __int64 v6; // rbx
  __int64 v7; // rdi
  int (*v8)(const unsigned int *const, unsigned __int64, struct _RTL_SMART_LBLOB_WRITING_CONTEXT *); // r12
  unsigned int *v9; // rsi
  __int64 v10; // rax
  __int64 result; // rax
  const char *v12; // rax
  int v13; // eax
  unsigned int v14; // ecx
  const char *v15; // [rsp+20h] [rbp-99h] BYREF
  const char *v16; // [rsp+28h] [rbp-91h]
  __int64 v17; // [rsp+30h] [rbp-89h]
  const char *v18; // [rsp+38h] [rbp-81h]
  _DWORD v19[4]; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v20[32]; // [rsp+50h] [rbp-69h] BYREF
  __int64 v21; // [rsp+D0h] [rbp+17h] BYREF

  v19[0] = 0;
  if ( a1 )
  {
    v17 = 238;
    v15 = "onecore\\base\\lstring\\lblob_encoders.cpp";
    v16 = "RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext";
    v18 = "Valid flags check failed: Flags";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             v19,
             &v15);
  }
  if ( !a2 )
  {
    v17 = 239;
    v15 = "onecore\\base\\lstring\\lblob_encoders.cpp";
    v16 = "RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext";
    v18 = "Not-null check failed: Data";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             v19,
             &v15);
  }
  v6 = a2[2];
  if ( !v6 && *a2 || *a2 > a2[1] )
  {
    v17 = 240;
    v15 = "onecore\\base\\lstring\\lblob_encoders.cpp";
    v16 = "RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext";
    v18 = "::RtlIsLBlobValid(Data)";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             v19,
             &v15);
  }
  if ( !a3 )
  {
    v17 = 241;
    v15 = "onecore\\base\\lstring\\lblob_encoders.cpp";
    v16 = "RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext";
    v12 = "Not-null check failed: Decoder";
LABEL_25:
    v18 = v12;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             v19,
             &v15);
  }
  if ( !a4 )
  {
    v17 = 242;
    v15 = "onecore\\base\\lstring\\lblob_encoders.cpp";
    v16 = "RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext";
    v12 = "Not-null check failed: WritingContext";
    goto LABEL_25;
  }
  if ( a3 == RtlDecodeUtf16LE && *(__int64 (__fastcall **)())(a4 + 88) == RtlSmartUcsEncoder_Utf16LE )
  {
    v13 = RtlWriteDataIntoSmartLBlobWritingContext((__int64)a2, (char **)a4);
    v14 = 0;
    if ( v13 < 0 )
      return (unsigned int)v13;
    return v14;
  }
  else
  {
    v7 = *a2 + v6;
    v8 = *(int (**)(const unsigned int *const, unsigned __int64, struct _RTL_SMART_LBLOB_WRITING_CONTEXT *))(a4 + 96);
    while ( 2 )
    {
      v9 = v20;
      do
      {
        if ( v6 == v7 )
        {
          if ( v9 == v20 )
            return 0;
          result = ((__int64 (__fastcall *)(unsigned int *, signed __int64, __int64))v8)(v20, v9 - v20, a4);
          if ( (int)result >= 0 )
            return 0;
          return result;
        }
        v10 = ((__int64 (__fastcall *)(const char **, __int64, __int64))a3)(&v15, v6, v7);
        v6 = *(_QWORD *)(v10 + 8);
        if ( *(_DWORD *)v10 == -1 )
        {
          if ( (int)v6 >= 0 )
            RtlRaiseStatus(-1073741595);
          v17 = 269;
          v15 = "onecore\\base\\lstring\\lblob_encoders.cpp";
          v16 = "RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext";
          v18 = "__rv.UcsCharacter != (0xffffffff)";
          return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                   v19,
                   &v15,
                   (unsigned int)v6);
        }
        *v9++ = *(_DWORD *)v10;
      }
      while ( v9 != (unsigned int *)&v21 );
      result = RtlWriteUcsDataIntoSmartLBlobUcsWritingContext_NOCFG(
                 v8,
                 v20,
                 0x20u,
                 (struct _RTL_SMART_LBLOB_UCSCHAR_WRITING_CONTEXT *)a4);
      if ( (int)result >= 0 )
        continue;
      break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800180e0  push    rbp
0x1800180e2  push    r14
0x1800180e4  push    r15
0x1800180e6  lea     rbp, [rsp-47h]
0x1800180eb  sub     rsp, 100h
0x1800180f2  mov     rax, cs:__security_cookie
0x1800180f9  xor     rax, rsp
0x1800180fc  mov     [rbp+57h+var_40], rax
0x180018100  mov     [rbp+57h+var_D0], 0
0x180018107  mov     r15, r9
0x18001810a  mov     r14, r8
0x18001810d  mov     rax, rdx
0x180018110  test    ecx, ecx
0x180018112  jnz     loc_18001828E
0x180018118  test    rdx, rdx
0x18001811b  jz      loc_1800182CE
0x180018121  mov     [rsp+110h+var_18], rbx
0x180018129  mov     rbx, [rdx+10h]
0x18001812d  test    rbx, rbx
0x180018130  jz      loc_180018247
0x180018136  mov     rcx, [rdx]
0x180018139  cmp     rcx, [rdx+8]
0x18001813d  ja      loc_180018251
0x180018143  test    r14, r14
0x180018146  jz      loc_18001830E
0x18001814c  test    r15, r15
0x18001814f  jz      loc_180018338
0x180018155  lea     rdx, RtlDecodeUtf16LE
0x18001815c  cmp     r14, rdx
0x18001815f  jz      loc_180018378
0x180018165  mov     [rsp+110h+var_20], rsi
0x18001816d  mov     [rsp+110h+var_28], rdi
0x180018175  lea     rdi, [rcx+rbx]
0x180018179  mov     [rsp+110h+var_30], r12
0x180018181  mov     r12, [r9+60h]
0x180018185  lea     rsi, [rbp+57h+var_C0]
0x180018189  nop     dword ptr [rax+00000000h]
0x180018190  cmp     rbx, rdi
0x180018193  jz      short loc_1800181E1
0x180018195  mov     r8, rdi
0x180018198  lea     rcx, [rsp+110h+var_F0]
0x18001819d  mov     rdx, rbx
0x1800181a0  mov     rax, r14
0x1800181a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181a8  mov     ecx, [rax]
0x1800181aa  mov     rbx, [rax+8]
0x1800181ae  cmp     ecx, 0FFFFFFFFh
0x1800181b1  jz      loc_1800183A2
0x1800181b7  mov     [rsi], ecx
0x1800181b9  lea     rax, [rbp+57h+var_40]
0x1800181bd  add     rsi, 4
0x1800181c1  cmp     rsi, rax
0x1800181c4  jnz     short loc_180018190
0x1800181c6  mov     r9, r15; struct _RTL_SMART_LBLOB_UCSCHAR_WRITING_CONTEXT *
0x1800181c9  lea     rdx, [rbp+57h+var_C0]; unsigned int *
0x1800181cd  mov     r8d, 20h ; ' '; unsigned __int64
0x1800181d3  mov     rcx, r12; int (*)(const unsigned int *const, unsigned __int64, struct _RTL_SMART_LBLOB_WRITING_CONTEXT *)
0x1800181d6  call    ?RtlWriteUcsDataIntoSmartLBlobUcsWritingContext_NOCFG@@YAJP6AJQEBK_KPEAU_RTL_SMART_LBLOB_WRITING_CONTEXT@@@Z01PEAU_RTL_SMART_LBLOB_UCSCHAR_WRITING_CONTEXT@@@Z; RtlWriteUcsDataIntoSmartLBlobUcsWritingContext_NOCFG(long (*)(ulong const * const,unsigned __int64,_RTL_SMART_LBLOB_WRITING_CONTEXT *),ulong const * const,unsigned __int64,_RTL_SMART_LBLOB_UCSCHAR_WRITING_CONTEXT *)
0x1800181db  test    eax, eax
0x1800181dd  jns     short loc_180018185
0x1800181df  jmp     short loc_18001820D
0x1800181e1  lea     rax, [rbp+57h+var_C0]
0x1800181e5  cmp     rsi, rax
0x1800181e8  jz      short loc_18001820B
0x1800181ea  lea     rax, [rbp+57h+var_C0]
0x1800181ee  mov     r8, r15
0x1800181f1  sub     rsi, rax
0x1800181f4  lea     rcx, [rbp+57h+var_C0]
0x1800181f8  sar     rsi, 2
0x1800181fc  mov     rax, r12
0x1800181ff  mov     rdx, rsi
0x180018202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018207  test    eax, eax
0x180018209  js      short loc_18001820D
0x18001820b  xor     eax, eax
0x18001820d  mov     rdi, [rsp+110h+var_28]
0x180018215  mov     rsi, [rsp+110h+var_20]
0x18001821d  mov     r12, [rsp+110h+var_30]
0x180018225  mov     rbx, [rsp+110h+var_18]
0x18001822d  mov     rcx, [rbp+57h+var_40]
0x180018231  xor     rcx, rsp; StackCookie
0x180018234  call    __security_check_cookie
0x180018239  add     rsp, 100h
0x180018240  pop     r15
0x180018242  pop     r14
0x180018244  pop     rbp
0x180018245  retn
0x180018247  cmp     qword ptr [rdx], 0
0x18001824b  jz      loc_180018136
0x180018251  lea     rax, aOnecoreBaseLst_5; "onecore\\base\\lstring\\lblob_encoders."...
0x180018258  mov     [rsp+110h+var_E0], 0F0h
0x180018261  mov     [rsp+110h+var_F0], rax
0x180018266  lea     rdx, [rsp+110h+var_F0]
0x18001826b  lea     rax, aRtlwritedecode_0; "RtlWriteDecodedUcsDataIntoSmartLBlobUcs"...
0x180018272  mov     [rsp+110h+var_E8], rax
0x180018277  lea     rcx, [rbp+57h+var_D0]
0x18001827b  lea     rax, aRtlislblobvali_2; "::RtlIsLBlobValid(Data)"
0x180018282  mov     [rsp+110h+var_D8], rax
0x180018287  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001828c  jmp     short loc_180018225
0x18001828e  lea     rax, aOnecoreBaseLst_5; "onecore\\base\\lstring\\lblob_encoders."...
0x180018295  mov     [rsp+110h+var_E0], 0EEh
0x18001829e  mov     [rsp+110h+var_F0], rax
0x1800182a3  lea     rdx, [rsp+110h+var_F0]
0x1800182a8  lea     rax, aRtlwritedecode_0; "RtlWriteDecodedUcsDataIntoSmartLBlobUcs"...
0x1800182af  mov     [rsp+110h+var_E8], rax
0x1800182b4  lea     rcx, [rbp+57h+var_D0]
0x1800182b8  lea     rax, aValidFlagsChec; "Valid flags check failed: Flags"
0x1800182bf  mov     [rsp+110h+var_D8], rax
0x1800182c4  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800182c9  jmp     loc_18001822D
0x1800182ce  lea     rax, aOnecoreBaseLst_5; "onecore\\base\\lstring\\lblob_encoders."...
0x1800182d5  mov     [rsp+110h+var_E0], 0EFh
0x1800182de  mov     [rsp+110h+var_F0], rax
0x1800182e3  lea     rdx, [rsp+110h+var_F0]
0x1800182e8  lea     rax, aRtlwritedecode_0; "RtlWriteDecodedUcsDataIntoSmartLBlobUcs"...
0x1800182ef  mov     [rsp+110h+var_E8], rax
0x1800182f4  lea     rcx, [rbp+57h+var_D0]
0x1800182f8  lea     rax, aNotNullCheckFa_15; "Not-null check failed: Data"
0x1800182ff  mov     [rsp+110h+var_D8], rax
0x180018304  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180018309  jmp     loc_18001822D
0x18001830e  lea     rax, aOnecoreBaseLst_5; "onecore\\base\\lstring\\lblob_encoders."...
0x180018315  mov     [rsp+110h+var_E0], 0F1h
0x18001831e  mov     [rsp+110h+var_F0], rax
0x180018323  lea     rax, aRtlwritedecode_0; "RtlWriteDecodedUcsDataIntoSmartLBlobUcs"...
0x18001832a  mov     [rsp+110h+var_E8], rax
0x18001832f  lea     rax, aNotNullCheckFa_84; "Not-null check failed: Decoder"
0x180018336  jmp     short loc_180018360
0x180018338  lea     rax, aOnecoreBaseLst_5; "onecore\\base\\lstring\\lblob_encoders."...
0x18001833f  mov     [rsp+110h+var_E0], 0F2h
0x180018348  mov     [rsp+110h+var_F0], rax
0x18001834d  lea     rax, aRtlwritedecode_0; "RtlWriteDecodedUcsDataIntoSmartLBlobUcs"...
0x180018354  mov     [rsp+110h+var_E8], rax
0x180018359  lea     rax, aNotNullCheckFa_13; "Not-null check failed: WritingContext"
0x180018360  lea     rdx, [rsp+110h+var_F0]
0x180018365  mov     [rsp+110h+var_D8], rax
0x18001836a  lea     rcx, [rbp+57h+var_D0]
0x18001836e  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180018373  jmp     loc_180018225
0x180018378  lea     rdx, RtlSmartUcsEncoder_Utf16LE
0x18001837f  cmp     [r9+58h], rdx
0x180018383  jnz     loc_180018165
0x180018389  mov     rdx, r15
0x18001838c  mov     rcx, rax
0x18001838f  call    RtlWriteDataIntoSmartLBlobWritingContext
0x180018394  xor     ecx, ecx
0x180018396  test    eax, eax
0x180018398  cmovs   ecx, eax
0x18001839b  mov     eax, ecx
0x18001839d  jmp     loc_180018225
0x1800183a2  test    ebx, ebx
0x1800183a4  js      short loc_1800183B8
0x1800183a6  mov     ecx, 0C00000E5h; Status
0x1800183ab  call    cs:__imp_RtlRaiseStatus
0x1800183b2  nop     dword ptr [rax+rax+00h]
0x1800183b7  int     3; Trap to Debugger
0x1800183b8  lea     rax, aOnecoreBaseLst_5; "onecore\\base\\lstring\\lblob_encoders."...
0x1800183bf  mov     [rsp+110h+var_E0], 10Dh
0x1800183c8  mov     [rsp+110h+var_F0], rax
0x1800183cd  lea     rdx, [rsp+110h+var_F0]
0x1800183d2  lea     rax, aRtlwritedecode_0; "RtlWriteDecodedUcsDataIntoSmartLBlobUcs"...
0x1800183d9  mov     r8d, ebx
0x1800183dc  mov     [rsp+110h+var_E8], rax
0x1800183e1  lea     rcx, [rbp+57h+var_D0]
0x1800183e5  lea     rax, aRvUcscharacter_0; "__rv.UcsCharacter != (0xffffffff)"
0x1800183ec  mov     [rsp+110h+var_D8], rax
0x1800183f1  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800183f6  jmp     loc_18001820D
```
