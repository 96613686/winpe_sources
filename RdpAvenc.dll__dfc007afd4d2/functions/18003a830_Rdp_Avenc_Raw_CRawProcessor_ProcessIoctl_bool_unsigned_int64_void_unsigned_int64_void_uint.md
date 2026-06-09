# Rdp::Avenc::Raw::CRawProcessor::ProcessIoctl(bool,unsigned __int64,void *,unsigned __int64,void *,uint *)

- ea: `0x18003a830`
- end: `0x18003aa75`
- name: `?ProcessIoctl@CRawProcessor@Raw@Avenc@Rdp@@UEAAJ_N_KPEAX12PEAI@Z`
- size: `581`
- prototype: `__int64 __fastcall(Rdp::Avenc::Raw::CRawProcessor *this, __int64, unsigned __int64, struct Rdp::Avenc::Umrdp::_RDPAVENC_OPCODE_TEST_FILEIO_PACKETS *, unsigned __int64, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18001143c`
- `0x1800146bc`
- `0x180014710`
- `0x180015480`
- `0x18003a830`
- `0x18003aa7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a89d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a9af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a89d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a9af`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::Raw::CRawProcessor::ProcessIoctl(
        Rdp::Avenc::Raw::CRawProcessor *this,
        __int64 a2,
        unsigned __int64 a3,
        struct Rdp::Avenc::Umrdp::_RDPAVENC_OPCODE_TEST_FILEIO_PACKETS *a4,
        unsigned __int64 a5,
        void *a6,
        unsigned int *a7)
{
  char v10; // bl
  bool v11; // di
  bool v12; // si
  char CurrentThreadId; // al
  int v14; // r8d
  int v15; // edx
  const char *v16; // r9
  bool v17; // di
  char v18; // al
  int v19; // r8d
  int v20; // edx
  __int64 result; // rax
  int v22; // [rsp+20h] [rbp-58h]
  int v23; // [rsp+28h] [rbp-50h]
  char *v24; // [rsp+28h] [rbp-50h]
  char *v25; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v10 = 1;
  v11 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v12 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v14) = v12;
    LOBYTE(v15) = v11;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      v14,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v22,
      v23,
      18,
      &WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v22) = *((_BYTE *)this + 176) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v22,
      (bool)"Processor is not started",
      v25);
    v24 = "BytesWritten can't ne null";
    wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
      retaddr,
      263,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
      2147500035LL);
    if ( a3 < 0xC )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x10D,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
        (const char *)0xC0000023LL,
        (int)"Input buffer size is too small to cast to RDPAVENC_OPCODE_HEADER",
        "BytesWritten can't ne null");
    *a7 = 0;
    if ( *((_DWORD *)a4 + 2) != 4 )
    {
      LODWORD(v24) = *((_DWORD *)a4 + 2);
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x123,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
        (const char *)0xC00000BBLL,
        (int)"Unknown Ioctl 0x%lx",
        v24);
    }
    if ( a3 < 0x18 )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x11B,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
        (const char *)0xC0000023LL,
        (int)"Input buffer size is too small to cast to RDPAVENC_OPCODE_TEST_FILEIO_PACKETS",
        "BytesWritten can't ne null");
    Rdp::Avenc::Raw::CRawProcessor::ProcessTestFileIo((Rdp::Avenc::Raw::CRawProcessor *)((char *)this - 80), a4);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v10 = 0;
    }
    v17 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v18 = GetCurrentThreadId();
      LOBYTE(v19) = v17;
      LOBYTE(v20) = v10;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        v19,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)a7,
        (int)"BytesWritten can't ne null",
        19,
        &WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids,
        v18);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x12E,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x18003a830  mov     [rsp+arg_8], rbx
0x18003a835  mov     [rsp+arg_10], rsi
0x18003a83a  push    rdi
0x18003a83b  push    r12
0x18003a83d  push    r13
0x18003a83f  push    r14
0x18003a841  push    r15
0x18003a843  sub     rsp, 50h
0x18003a847  mov     r15, r9
0x18003a84a  mov     r14, r8
0x18003a84d  mov     r13, rcx
0x18003a850  lea     rcx, WPP_GLOBAL_Control
0x18003a857  mov     rax, cs:WPP_GLOBAL_Control
0x18003a85e  mov     bl, 1
0x18003a860  cmp     rax, rcx
0x18003a863  jz      short loc_18003A875
0x18003a865  test    [rax+1Ch], bl
0x18003a868  jz      short loc_18003A875
0x18003a86a  cmp     byte ptr [rax+19h], 4
0x18003a86e  jb      short loc_18003A875
0x18003a870  mov     dil, bl
0x18003a873  jmp     short loc_18003A878
0x18003a875  xor     dil, dil
0x18003a878  lea     rax, WPP_RECORDER_INITIALIZED
0x18003a87f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003a886  setnz   sil
0x18003a88a  test    dil, dil
0x18003a88d  jnz     short loc_18003A89D
0x18003a88f  test    sil, sil
0x18003a892  jnz     short loc_18003A89D
0x18003a894  lea     r12, WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids
0x18003a89b  jmp     short loc_18003A8D4
0x18003a89d  call    cs:__imp_GetCurrentThreadId
0x18003a8a3  mov     dword ptr [rsp+78h+var_38], eax; char
0x18003a8a7  lea     r12, WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids
0x18003a8ae  mov     [rsp+78h+MessageGuid], r12; MessageGuid
0x18003a8b3  mov     word ptr [rsp+78h+var_48], 12h; char *
0x18003a8ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a8c1  mov     r9, [rcx+28h]; int
0x18003a8c5  mov     r8b, sil; int
0x18003a8c8  mov     dl, dil; int
0x18003a8cb  mov     rcx, [rcx+10h]; int
0x18003a8cf  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003a8d4  lea     rsi, [r13-50h]
0x18003a8d8  cmp     byte ptr [rsi+100h], 0
0x18003a8df  setz    al
0x18003a8e2  mov     rcx, [rsp+78h]; this
0x18003a8e7  lea     rdx, aProcessorIsNot; "Processor is not started"
0x18003a8ee  mov     [rsp+78h+var_50], rdx; bool
0x18003a8f3  mov     byte ptr [rsp+78h+var_58], al; int
0x18003a8f7  mov     r9d, 8000FFFFh; char *
0x18003a8fd  lea     r13, aOnecoreuapTerm_42; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003a904  mov     r8, r13; unsigned int
0x18003a907  mov     edx, 106h; void *
0x18003a90c  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003a911  mov     rcx, [rsp+78h]
0x18003a916  lea     rax, aByteswrittenCa_0; "BytesWritten can't ne null"
0x18003a91d  mov     [rsp+78h+var_50], rax; char *
0x18003a922  mov     rdi, [rsp+78h+arg_30]
0x18003a92a  mov     qword ptr [rsp+78h+var_58], rdi; int
0x18003a92f  mov     r9d, 80004003h
0x18003a935  mov     r8, r13
0x18003a938  mov     edx, 107h
0x18003a93d  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003a942  cmp     r14, 0Ch
0x18003a946  jb      loc_18003AA03
0x18003a94c  mov     dword ptr [rdi], 0
0x18003a952  mov     eax, [r15+8]
0x18003a956  cmp     eax, 4
0x18003a959  jnz     loc_18003AA27
0x18003a95f  cmp     r14, 18h
0x18003a963  jb      loc_18003AA4F
0x18003a969  mov     rdx, r15; struct Rdp::Avenc::Umrdp::_RDPAVENC_OPCODE_TEST_FILEIO_PACKETS *
0x18003a96c  mov     rcx, rsi; this
0x18003a96f  call    ?ProcessTestFileIo@CRawProcessor@Raw@Avenc@Rdp@@AEAAXQEAU_RDPAVENC_OPCODE_TEST_FILEIO_PACKETS@Umrdp@34@@Z; Rdp::Avenc::Raw::CRawProcessor::ProcessTestFileIo(Rdp::Avenc::Umrdp::_RDPAVENC_OPCODE_TEST_FILEIO_PACKETS * const)
0x18003a974  mov     rax, cs:WPP_GLOBAL_Control
0x18003a97b  lea     rcx, WPP_GLOBAL_Control
0x18003a982  cmp     rax, rcx
0x18003a985  jz      short loc_18003A992
0x18003a987  test    [rax+1Ch], bl
0x18003a98a  jz      short loc_18003A992
0x18003a98c  cmp     byte ptr [rax+19h], 4
0x18003a990  jnb     short loc_18003A994
0x18003a992  xor     bl, bl
0x18003a994  lea     rax, WPP_RECORDER_INITIALIZED
0x18003a99b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003a9a2  setnz   dil
0x18003a9a6  test    bl, bl
0x18003a9a8  jnz     short loc_18003A9AF
0x18003a9aa  test    dil, dil
0x18003a9ad  jz      short loc_18003A9DE
0x18003a9af  call    cs:__imp_GetCurrentThreadId
0x18003a9b5  mov     dword ptr [rsp+78h+var_38], eax; char
0x18003a9b9  mov     [rsp+78h+MessageGuid], r12; MessageGuid
0x18003a9be  mov     word ptr [rsp+78h+var_48], 13h; __int16
0x18003a9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a9cc  mov     r9, [rcx+28h]; int
0x18003a9d0  mov     r8b, dil; int
0x18003a9d3  mov     dl, bl; int
0x18003a9d5  mov     rcx, [rcx+10h]; int
0x18003a9d9  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003a9de  xor     eax, eax
0x18003a9e0  jmp     short loc_18003A9E9
0x18003a9e2  mov     eax, [rsp+78h+arg_0]
0x18003a9e9  lea     r11, [rsp+78h+var_28]
0x18003a9ee  mov     rbx, [r11+38h]
0x18003a9f2  mov     rsi, [r11+40h]
0x18003a9f6  mov     rsp, r11
0x18003a9f9  pop     r15
0x18003a9fb  pop     r14
0x18003a9fd  pop     r13
0x18003a9ff  pop     r12
0x18003aa01  pop     rdi
0x18003aa02  retn
0x18003aa03  mov     rcx, [rsp+78h]; this
0x18003aa08  lea     rax, aInputBufferSiz_1; "Input buffer size is too small to cast "...
0x18003aa0f  mov     qword ptr [rsp+78h+var_58], rax; int
0x18003aa14  mov     r9d, 0C0000023h; char *
0x18003aa1a  mov     r8, r13; unsigned int
0x18003aa1d  mov     edx, 10Dh; void *
0x18003aa22  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18003aa27  mov     rcx, [rsp+78h]; this
0x18003aa2c  mov     dword ptr [rsp+78h+var_50], eax; char *
0x18003aa30  lea     rax, aUnknownIoctl0x; "Unknown Ioctl 0x%lx"
0x18003aa37  mov     qword ptr [rsp+78h+var_58], rax; int
0x18003aa3c  mov     r9d, 0C00000BBh; char *
0x18003aa42  mov     r8, r13; unsigned int
0x18003aa45  mov     edx, 123h; void *
0x18003aa4a  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18003aa4f  mov     rcx, [rsp+78h]; this
0x18003aa54  lea     rax, aInputBufferSiz_6; "Input buffer size is too small to cast "...
0x18003aa5b  mov     qword ptr [rsp+78h+var_58], rax; int
0x18003aa60  mov     r9d, 0C0000023h; char *
0x18003aa66  mov     r8, r13; unsigned int
0x18003aa69  mov     edx, 11Bh; void *
0x18003aa6e  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
```
