# UbpmpSleepStudyStartReportingBlocker

- ea: `0x180030ea4`
- end: `0x1800310d6`
- name: `UbpmpSleepStudyStartReportingBlocker`
- size: `562`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180030bb4`
- `0x180031150`

## callees

- `0x180001424`
- `0x18000a880`
- `0x18000fbf0`
- `0x1800150c0`
- `0x18002b910`
- `0x18002d620`
- `0x180030ea4`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180030f85`
- `ntdll!RtlInitUnicodeString` at `0x180030f85`
- `UMPDC!SleepstudyHelperBuildBlocker` at `0x180030fd5`
- `UMPDC!SleepstudyHelperBuildBlocker` at `0x180030fd5`
- `UMPDC!SleepstudyHelperCreateBlockerFromGuid` at `0x180030fb2`
- `UMPDC!SleepstudyHelperCreateBlockerFromGuid` at `0x180030fb2`
- `UMPDC!SleepstudyHelperBlockerActiveReference` at `0x180030ffc`
- `UMPDC!SleepstudyHelperBlockerActiveReference` at `0x180030ffc`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x180031027`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x180031027`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x18003103d`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x18003103d`

## pseudocode

```c
__int64 __fastcall UbpmpSleepStudyStartReportingBlocker(
        __int64 a1,
        __int128 *a2,
        const WCHAR *a3,
        __int64 a4,
        _QWORD *a5)
{
  __int128 v9; // xmm0
  PCNZWCH ConsumerFriendlyName; // rbx
  __int64 v11; // rdx
  unsigned __int16 *v12; // rsi
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // edi
  int v16; // ebx
  int v17; // eax
  __int64 v18; // rcx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  __int64 v23; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v24; // [rsp+48h] [rbp-99h] BYREF
  int v25; // [rsp+50h] [rbp-91h] BYREF
  int v26; // [rsp+54h] [rbp-8Dh] BYREF
  __int64 v27; // [rsp+58h] [rbp-89h] BYREF
  const WCHAR *v28; // [rsp+60h] [rbp-81h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-79h] BYREF
  _DWORD v30[2]; // [rsp+78h] [rbp-69h] BYREF
  __int64 v31; // [rsp+80h] [rbp-61h]
  __int128 v32; // [rsp+88h] [rbp-59h] BYREF
  _BYTE v33[80]; // [rsp+A0h] [rbp-41h] BYREF

  v24 = 0;
  v23 = 0;
  DestinationString = 0;
  memset_0(v33, 0, 0x4Eu);
  v9 = *a2;
  v30[0] = -1428313379;
  v30[1] = 4;
  v32 = v9;
  v31 = 35;
  ConsumerFriendlyName = UbpmpGetConsumerFriendlyName(a3);
  v12 = (unsigned __int16 *)UbpmAlloc(0x1FEu);
  if ( v12 )
  {
    v17 = RtlStringCbPrintfW(v12, 0x1FEu, L"%s:%s", ConsumerFriendlyName, v33);
    if ( (int)(v17 + 0x80000000) >= 0 && v17 != -2147483643 )
      __int2c();
    RtlInitUnicodeString(&DestinationString, v12);
    v16 = SleepstudyHelperCreateBlockerFromGuid(a1, v30, &v32, &DestinationString, 4, &v24);
    if ( v16 >= 0 )
    {
      v16 = SleepstudyHelperBuildBlocker(v24, &v23);
      if ( v16 >= 0 )
      {
        v24 = 0;
        SleepstudyHelperBlockerActiveReference(v23);
        *a5 = v23;
        v15 = 0;
        v16 = 0;
        v23 = 0;
      }
      else
      {
        v15 = 30;
      }
    }
    else
    {
      v15 = 20;
    }
  }
  else
  {
    v15 = 10;
    v16 = -1073741664;
  }
  if ( v23 )
    SleepstudyHelperDestroyBlocker(v23);
  v18 = v24;
  if ( v24 )
    SleepstudyHelperDestroyBlockerBuilder();
  if ( v12 )
    UBPM_MIDL_user_free(v12, v11, v13, v14);
  if ( (unsigned int)dword_18004F0F0 > 5 && (unsigned __int8)tlgKeywordOn(v18, 4) )
  {
    v25 = v16;
    v26 = v15;
    v27 = a4;
    v28 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v19,
      (unsigned int)byte_1800473B3,
      v20,
      v21,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180030ea4  push    rbp
0x180030ea6  push    rbx
0x180030ea7  push    rsi
0x180030ea8  push    rdi
0x180030ea9  push    r12
0x180030eab  push    r14
0x180030ead  push    r15
0x180030eaf  lea     rbp, [rsp-1Fh]
0x180030eb4  sub     rsp, 100h
0x180030ebb  mov     rax, cs:__security_cookie
0x180030ec2  xor     rax, rsp
0x180030ec5  mov     [rbp+4Fh+var_40], rax
0x180030ec9  mov     rdi, [rbp+4Fh+arg_20]
0x180030ecd  mov     rbx, rdx
0x180030ed0  xor     edx, edx; Val
0x180030ed2  mov     [rsp+130h+var_E8], 0
0x180030edb  mov     r15, r8
0x180030ede  mov     [rsp+130h+var_F0], 0
0x180030ee7  mov     r14, rcx
0x180030eea  xorps   xmm0, xmm0
0x180030eed  lea     rcx, [rbp+4Fh+var_90]; void *
0x180030ef1  mov     r12, r9
0x180030ef4  lea     r8d, [rdx+4Eh]; Size
0x180030ef8  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x180030efc  call    memset_0
0x180030f01  movups  xmm0, xmmword ptr [rbx]
0x180030f04  mov     rcx, r15; lpString1
0x180030f07  mov     [rbp+4Fh+var_B8], 0AADDAADDh
0x180030f0e  mov     [rbp+4Fh+var_B4], 4
0x180030f15  movdqu  [rbp+4Fh+var_A8], xmm0
0x180030f1a  mov     [rbp+4Fh+var_B0], 23h ; '#'
0x180030f22  call    ?UbpmpGetConsumerFriendlyName@@YAPEBGPEBG@Z; UbpmpGetConsumerFriendlyName(ushort const *)
0x180030f27  mov     ecx, 1FEh; Size
0x180030f2c  mov     rbx, rax
0x180030f2f  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180030f34  mov     rsi, rax
0x180030f37  test    rax, rax
0x180030f3a  jnz     short loc_180030F49
0x180030f3c  lea     edi, [rax+0Ah]
0x180030f3f  mov     ebx, 0C00000A0h
0x180030f44  jmp     loc_18003101D
0x180030f49  lea     rax, [rbp+4Fh+var_90]
0x180030f4d  mov     r9, rbx
0x180030f50  lea     r8, aSS; "%s:%s"
0x180030f57  mov     [rsp+130h+var_110], rax
0x180030f5c  mov     edx, 1FEh; unsigned __int64
0x180030f61  mov     rcx, rsi; unsigned __int16 *
0x180030f64  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030f69  mov     edx, 80000000h
0x180030f6e  lea     ecx, [rax+rdx]
0x180030f71  test    edx, ecx
0x180030f73  jnz     short loc_180030F7E
0x180030f75  cmp     eax, 80000005h
0x180030f7a  jz      short loc_180030F7E
0x180030f7c  int     2Ch; Windows NT - assertion failure
0x180030f7e  mov     rdx, rsi; SourceString
0x180030f81  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x180030f85  call    cs:__imp_RtlInitUnicodeString
0x180030f8c  nop     dword ptr [rax+rax+00h]
0x180030f91  lea     rax, [rsp+130h+var_E8]
0x180030f96  mov     rcx, r14
0x180030f99  mov     [rsp+130h+var_108], rax
0x180030f9e  lea     r9, [rbp+4Fh+DestinationString]
0x180030fa2  lea     r8, [rbp+4Fh+var_A8]
0x180030fa6  mov     dword ptr [rsp+130h+var_110], 4
0x180030fae  lea     rdx, [rbp+4Fh+var_B8]
0x180030fb2  call    cs:__imp_SleepstudyHelperCreateBlockerFromGuid
0x180030fb9  nop     dword ptr [rax+rax+00h]
0x180030fbe  mov     ebx, eax
0x180030fc0  test    eax, eax
0x180030fc2  jns     short loc_180030FCB
0x180030fc4  mov     edi, 14h
0x180030fc9  jmp     short loc_18003101D
0x180030fcb  mov     rcx, [rsp+130h+var_E8]
0x180030fd0  lea     rdx, [rsp+130h+var_F0]
0x180030fd5  call    cs:__imp_SleepstudyHelperBuildBlocker
0x180030fdc  nop     dword ptr [rax+rax+00h]
0x180030fe1  mov     ebx, eax
0x180030fe3  test    eax, eax
0x180030fe5  jns     short loc_180030FEE
0x180030fe7  mov     edi, 1Eh
0x180030fec  jmp     short loc_18003101D
0x180030fee  mov     rcx, [rsp+130h+var_F0]
0x180030ff3  mov     [rsp+130h+var_E8], 0
0x180030ffc  call    cs:__imp_SleepstudyHelperBlockerActiveReference
0x180031003  nop     dword ptr [rax+rax+00h]
0x180031008  mov     rax, [rsp+130h+var_F0]
0x18003100d  mov     [rdi], rax
0x180031010  xor     edi, edi
0x180031012  xor     ebx, ebx
0x180031014  mov     [rsp+130h+var_F0], 0
0x18003101d  mov     rcx, [rsp+130h+var_F0]
0x180031022  test    rcx, rcx
0x180031025  jz      short loc_180031033
0x180031027  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x18003102e  nop     dword ptr [rax+rax+00h]
0x180031033  mov     rcx, [rsp+130h+var_E8]
0x180031038  test    rcx, rcx
0x18003103b  jz      short loc_180031049
0x18003103d  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x180031044  nop     dword ptr [rax+rax+00h]
0x180031049  test    rsi, rsi
0x18003104c  jz      short loc_180031056
0x18003104e  mov     rcx, rsi
0x180031051  call    UBPM_MIDL_user_free
0x180031056  mov     eax, cs:dword_18004F0F0
0x18003105c  cmp     eax, 5
0x18003105f  jbe     short loc_1800310B5
0x180031061  mov     edx, 4
0x180031066  call    _tlgKeywordOn
0x18003106b  test    al, al
0x18003106d  jz      short loc_1800310B5
0x18003106f  lea     rax, [rsp+130h+var_E0]
0x180031074  mov     [rsp+130h+var_E0], ebx
0x180031078  mov     [rsp+130h+var_F8], rax
0x18003107d  lea     rdx, byte_1800473B3
0x180031084  lea     rax, [rsp+130h+var_DC]
0x180031089  mov     [rsp+130h+var_DC], edi
0x18003108d  mov     [rsp+130h+var_100], rax
0x180031092  lea     rax, [rsp+130h+var_D8]
0x180031097  mov     [rsp+130h+var_108], rax
0x18003109c  lea     rax, [rsp+130h+var_D0]
0x1800310a1  mov     [rsp+130h+var_110], rax
0x1800310a6  mov     [rsp+130h+var_D8], r12
0x1800310ab  mov     [rsp+130h+var_D0], r15
0x1800310b0  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800310b5  mov     eax, ebx
0x1800310b7  mov     rcx, [rbp+4Fh+var_40]
0x1800310bb  xor     rcx, rsp; StackCookie
0x1800310be  call    __security_check_cookie
0x1800310c3  add     rsp, 100h
0x1800310ca  pop     r15
0x1800310cc  pop     r14
0x1800310ce  pop     r12
0x1800310d0  pop     rdi
0x1800310d1  pop     rsi
0x1800310d2  pop     rbx
0x1800310d3  pop     rbp
0x1800310d4  retn
```
