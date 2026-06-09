# DriverKeyformProperties::Initialize(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,DriverKeyformProperties::InitializeFlags)

- ea: `0x18011692c`
- end: `0x180116ac6`
- name: `?Initialize@DriverKeyformProperties@@QEAAJAEBU_UNICODE_STRING@@000W4InitializeFlags@1@@Z`
- size: `410`
- prototype: `int __high(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, enum DriverKeyformProperties::InitializeFlags)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ba494`
- `0x180116c34`

## callees

- `0x180068c4c`
- `0x18006fab0`
- `0x1801164ac`
- `0x18011692c`
- `0x180116acc`
- `0x1801a1604`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180116968`
- `ntdll!RtlCompareUnicodeString` at `0x18011698f`
- `ntdll!RtlCompareUnicodeString` at `0x1801169b1`
- `ntdll!RtlCompareUnicodeString` at `0x1801169d3`
- `ntdll!RtlCompareUnicodeString` at `0x180116968`
- `ntdll!RtlCompareUnicodeString` at `0x18011698f`
- `ntdll!RtlCompareUnicodeString` at `0x1801169b1`
- `ntdll!RtlCompareUnicodeString` at `0x1801169d3`

## pseudocode

```c
__int64 __fastcall DriverKeyformProperties::Initialize(
        __int64 a1,
        __int64 a2,
        const UNICODE_STRING *a3,
        unsigned __int16 *a4,
        __int64 a5,
        unsigned int a6)
{
  __int64 v7; // rbx
  Windows::WCP::Implementation::Rtl *v11; // rcx
  unsigned __int16 v12; // di
  __int64 v13; // rdx
  const unsigned __int8 *v14; // r8
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rcx
  int v18; // eax
  int v20; // [rsp+20h] [rbp-58h]
  bool *v21; // [rsp+38h] [rbp-40h]
  int v22; // [rsp+40h] [rbp-38h] BYREF
  __int64 v23; // [rsp+48h] [rbp-30h] BYREF
  int v24; // [rsp+90h] [rbp+18h] BYREF

  v7 = 0;
  v23 = 0;
  LOBYTE(a6) = 0;
  v24 = 0;
  if ( RtlCompareUnicodeString(a3, &`GetProcArchFromNtArchNameUnicodeString'::`2'::X86_STRING, 1u) )
  {
    if ( RtlCompareUnicodeString(a3, &`GetProcArchFromNtArchNameUnicodeString'::`2'::AMD64_STRING, 1u) )
    {
      if ( RtlCompareUnicodeString(a3, &`GetProcArchFromNtArchNameUnicodeString'::`2'::ARM_STRING, 1u) )
      {
        if ( RtlCompareUnicodeString(a3, &`GetProcArchFromNtArchNameUnicodeString'::`2'::ARM64_STRING, 1u) )
          v12 = -1;
        else
          v12 = 12;
      }
      else
      {
        v12 = 5;
      }
    }
    else
    {
      v12 = 9;
    }
  }
  else
  {
    v12 = 0;
  }
  if ( a3->Length >= 2u && v12 == 0xFFFF )
    goto LABEL_17;
  LOBYTE(v11) = 0;
  if ( *a4 >= 2u )
  {
    v13 = *((_QWORD *)a4 + 1);
    v14 = (const unsigned __int8 *)(v13 + *a4);
    v22 = 0;
    v15 = Windows::WCP::Implementation::Rtl::ParseDottedVersion(
            v11,
            v13,
            v14,
            (const unsigned __int8 *)RtlDecodeUtf16LE,
            (struct _RTL_UCSCHAR_DECODER_RETURN_VALUE (__high *)(const unsigned __int8 *, const unsigned __int8 *))&v23,
            (union _FOUR_PART_VERSION *)&v22,
            &a6,
            v21);
    if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(v15, &v24) )
    {
      v16 = v24;
LABEL_15:
      v17 = v16;
LABEL_21:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v17);
      goto LABEL_22;
    }
    LOBYTE(v11) = 1;
    if ( !(_BYTE)a6 )
    {
LABEL_17:
      v16 = -2147024883;
      goto LABEL_15;
    }
    v7 = v23;
  }
  LOBYTE(v20) = (_BYTE)v11;
  v18 = DriverKeyformProperties::Initialize(a1, a2, v12, v7, v20, a5);
  v16 = v18;
  if ( v18 < 0 )
  {
    v17 = (unsigned int)v18;
    goto LABEL_21;
  }
LABEL_22:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v16);
  return v16;
}

```

## disassembly

```asm
0x18011692c  mov     rax, rsp
0x18011692f  mov     [rax+8], rbx
0x180116933  mov     [rax+10h], rbp
0x180116937  push    rsi
0x180116938  push    rdi
0x180116939  push    r13
0x18011693b  push    r14
0x18011693d  push    r15
0x18011693f  sub     rsp, 50h
0x180116943  mov     rsi, r8
0x180116946  xor     ebx, ebx
0x180116948  mov     r14, rdx
0x18011694b  mov     [rax-30h], rbx
0x18011694f  mov     r15, rcx
0x180116952  mov     [rax+30h], bl
0x180116955  mov     rcx, rsi; String1
0x180116958  mov     [rax+18h], ebx
0x18011695b  mov     r8b, 1; CaseInsensitive
0x18011695e  lea     rdx, ?X86_STRING@?1??GetProcArchFromNtArchNameUnicodeString@@9@4U_UNICODE_STRING@@A; String2
0x180116965  mov     rbp, r9
0x180116968  call    cs:__imp_RtlCompareUnicodeString
0x18011696f  nop     dword ptr [rax+rax+00h]
0x180116974  mov     r13d, 0FFFFh
0x18011697a  test    eax, eax
0x18011697c  jnz     short loc_180116982
0x18011697e  xor     edi, edi
0x180116980  jmp     short loc_1801169EC
0x180116982  mov     r8b, 1; CaseInsensitive
0x180116985  lea     rdx, ?AMD64_STRING@?1??GetProcArchFromNtArchNameUnicodeString@@9@4U_UNICODE_STRING@@A; String2
0x18011698c  mov     rcx, rsi; String1
0x18011698f  call    cs:__imp_RtlCompareUnicodeString
0x180116996  nop     dword ptr [rax+rax+00h]
0x18011699b  test    eax, eax
0x18011699d  jnz     short loc_1801169A4
0x18011699f  lea     edi, [rax+9]
0x1801169a2  jmp     short loc_1801169EC
0x1801169a4  mov     r8b, 1; CaseInsensitive
0x1801169a7  lea     rdx, ?ARM_STRING@?1??GetProcArchFromNtArchNameUnicodeString@@9@4U_UNICODE_STRING@@A; String2
0x1801169ae  mov     rcx, rsi; String1
0x1801169b1  call    cs:__imp_RtlCompareUnicodeString
0x1801169b8  nop     dword ptr [rax+rax+00h]
0x1801169bd  test    eax, eax
0x1801169bf  jnz     short loc_1801169C6
0x1801169c1  lea     edi, [rax+5]
0x1801169c4  jmp     short loc_1801169EC
0x1801169c6  mov     r8b, 1; CaseInsensitive
0x1801169c9  lea     rdx, ?ARM64_STRING@?1??GetProcArchFromNtArchNameUnicodeString@@9@4U_UNICODE_STRING@@A; String2
0x1801169d0  mov     rcx, rsi; String1
0x1801169d3  call    cs:__imp_RtlCompareUnicodeString
0x1801169da  nop     dword ptr [rax+rax+00h]
0x1801169df  test    eax, eax
0x1801169e1  jnz     short loc_1801169E8
0x1801169e3  lea     edi, [rax+0Ch]
0x1801169e6  jmp     short loc_1801169EC
0x1801169e8  movzx   edi, r13w
0x1801169ec  cmp     word ptr [rsi], 2
0x1801169f0  jb      short loc_1801169F8
0x1801169f2  cmp     di, r13w
0x1801169f6  jz      short loc_180116A67
0x1801169f8  xor     cl, cl; this
0x1801169fa  cmp     word ptr [rbp+0], 2
0x1801169ff  jb      short loc_180116A73
0x180116a01  mov     rdx, [rbp+8]; unsigned int
0x180116a05  lea     rax, [rsp+78h+arg_28]
0x180116a0d  movzx   r8d, word ptr [rbp+0]
0x180116a12  lea     r9, RtlDecodeUtf16LE; unsigned __int8 *
0x180116a19  mov     [rsp+78h+var_48], rax; unsigned int *
0x180116a1e  add     r8, rdx; unsigned __int8 *
0x180116a21  lea     rax, [rsp+78h+var_38]
0x180116a26  mov     [rsp+78h+var_38], ebx
0x180116a2a  mov     [rsp+78h+var_50], rax; union _FOUR_PART_VERSION *
0x180116a2f  lea     rax, [rsp+78h+var_30]
0x180116a34  mov     [rsp+78h+var_58], rax; struct _RTL_UCSCHAR_DECODER_RETURN_VALUE (__high *)(const unsigned __int8 *, const unsigned __int8 *)
0x180116a39  call    ?ParseDottedVersion@Rtl@Implementation@WCP@Windows@@YAJKPEBE0P6A?AU_RTL_UCSCHAR_DECODER_RETURN_VALUE@@00@ZPEAT_FOUR_PART_VERSION@@PEAKPEA_N@Z; Windows::WCP::Implementation::Rtl::ParseDottedVersion(ulong,uchar const *,uchar const *,_RTL_UCSCHAR_DECODER_RETURN_VALUE (*)(uchar const *,uchar const *),_FOUR_PART_VERSION *,ulong *,bool *)
0x180116a3e  lea     rdx, [rsp+78h+arg_10]; int *
0x180116a46  mov     ecx, eax; int
0x180116a48  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180116a4d  test    eax, eax
0x180116a4f  jnz     short loc_180116A5C
0x180116a51  mov     ebx, [rsp+78h+arg_10]
0x180116a58  mov     ecx, ebx
0x180116a5a  jmp     short loc_180116A9E
0x180116a5c  mov     cl, 1
0x180116a5e  cmp     byte ptr [rsp+78h+arg_28], bl
0x180116a65  jnz     short loc_180116A6E
0x180116a67  mov     ebx, 8007000Dh
0x180116a6c  jmp     short loc_180116A58
0x180116a6e  mov     rbx, [rsp+78h+var_30]
0x180116a73  mov     rax, [rsp+78h+arg_20]
0x180116a7b  mov     r9, rbx
0x180116a7e  mov     [rsp+78h+var_50], rax
0x180116a83  movzx   r8d, di
0x180116a87  mov     byte ptr [rsp+78h+var_58], cl
0x180116a8b  mov     rdx, r14
0x180116a8e  mov     rcx, r15
0x180116a91  call    ?Initialize@DriverKeyformProperties@@QEAAJAEBU_UNICODE_STRING@@GT_FOUR_PART_VERSION@@_N0W4InitializeFlags@1@@Z; DriverKeyformProperties::Initialize(_UNICODE_STRING const &,ushort,_FOUR_PART_VERSION,bool,_UNICODE_STRING const &,DriverKeyformProperties::InitializeFlags)
0x180116a96  mov     ebx, eax
0x180116a98  test    eax, eax
0x180116a9a  jns     short loc_180116AA3
0x180116a9c  mov     ecx, eax
0x180116a9e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180116aa3  mov     ecx, ebx
0x180116aa5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180116aaa  lea     r11, [rsp+78h+var_28]
0x180116aaf  mov     eax, ebx
0x180116ab1  mov     rbx, [r11+30h]
0x180116ab5  mov     rbp, [r11+38h]
0x180116ab9  mov     rsp, r11
0x180116abc  pop     r15
0x180116abe  pop     r14
0x180116ac0  pop     r13
0x180116ac2  pop     rdi
0x180116ac3  pop     rsi
0x180116ac4  retn
```
