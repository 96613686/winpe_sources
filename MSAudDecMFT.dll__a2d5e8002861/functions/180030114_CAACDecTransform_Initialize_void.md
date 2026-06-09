# CAACDecTransform::Initialize(void)

- ea: `0x180030114`
- end: `0x180030339`
- name: `?Initialize@CAACDecTransform@@QEAAJXZ`
- size: `549`
- prototype: `__int64 __fastcall(CAACDecTransform *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002fd3c`

## callees

- `0x180003af0`
- `0x180003ca4`
- `0x180003d64`
- `0x180030114`
- `0x180030404`
- `0x1800305d4`
- `0x180031298`
- `0x18004dd14`
- `0x1800960c0`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180030258`
- `MFPlat!MFCreateAttributes` at `0x180030258`

## pseudocode

```c
__int64 __fastcall CAACDecTransform::Initialize(CAACDecTransform *this)
{
  TraceLoggingHelperBase *v1; // rbp
  _QWORD *v3; // rsi
  int v4; // edi

  v1 = (CAACDecTransform *)((char *)this + 246664);
  TraceLoggingHelperBase::TraceVA(
    (CAACDecTransform *)((char *)this + 246664),
    4u,
    "CAACDecTransform::Initialize",
    0x100u,
    "CAACDecTransform::Initialize()");
  v3 = (_QWORD *)((char *)this + 246200);
  *((_QWORD *)this + 30775) = 0;
  *((_QWORD *)this + 32020) = 0;
  CAACDecTransform::_UnLockInputBuffer(this);
  *((_QWORD *)this + 32023) = 0;
  CAACDecTransform::_UnLockOutputBuffer(this);
  v4 = CAACDec::InitializeAACDec((CAACDecTransform *)((char *)this + 176));
  if ( v4 >= 0 )
  {
    if ( !(unsigned int)IsLicensedComponentAAC_Internal() )
    {
      v4 = -1073418223;
LABEL_11:
      TraceLoggingHelperBase::TraceVA(
        v1,
        2u,
        "CAACDecTransform::Initialize",
        0x18Eu,
        "Error %08X returned: File: %s, Line: %d",
        v4,
        "avcore\\codecdsp\\audio\\aacdec\\current\\mft\\aacdectransformxheaac.cpp",
        398);
      return (unsigned int)v4;
    }
    *((_DWORD *)this + 42) = 0;
    *((_DWORD *)this + 28) = 1;
    *((_QWORD *)this + 30763) = 1;
    *((_DWORD *)this + 61528) = 1;
    *((_QWORD *)this + 9) = 15;
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
    *((_DWORD *)this + 29) = 49152;
    *((_QWORD *)this + 32026) = 0;
    *((_QWORD *)this + 27) = 0;
    *((_DWORD *)this + 56) = 0;
    *((_QWORD *)this + 29) = 0;
    *((_QWORD *)this + 30) = 0;
    *((_QWORD *)this + 31) = 0;
    *(_QWORD *)((char *)this + 260) = 0;
    *((_BYTE *)this + 246116) = 0;
    *((_BYTE *)this + 256216) = 0;
    *(_QWORD *)((char *)this + 300) = 0;
    *((_DWORD *)this + 64065) = 0;
    *((_DWORD *)this + 64055) = 0;
    memset_0((char *)this + 246208, 0, 0x1C4u);
    v4 = CAACDecTransform::_ConfigInputTypes(this);
    if ( v4 >= 0 )
    {
      if ( MFCreateAttributes((IMFAttributes **)this + 30775, 3u) || !*v3 )
      {
        *v3 = 0;
        v4 = -2147467259;
        goto LABEL_11;
      }
      v4 = (*(__int64 (__fastcall **)(_QWORD, const GUID *, _QWORD))(*(_QWORD *)*v3 + 168LL))(
             *v3,
             &MFT_SUPPORT_DYNAMIC_FORMAT_CHANGE,
             0);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD))(*(_QWORD *)*v3 + 168LL))(
               *v3,
               &GUID_a5106186_cc94_4bc9_8cd9_aa2f61f6807e,
               *((unsigned int *)this + 61526));
        if ( v4 >= 0 )
          v4 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD))(*(_QWORD *)*v3 + 168LL))(
                 *v3,
                 &GUID_4a52cda8_30f8_4216_be0f_ba0b2025921d,
                 *((unsigned int *)this + 61527));
      }
    }
  }
  if ( v4 )
    goto LABEL_11;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180030114  push    rbx
0x180030116  push    rbp
0x180030117  push    rsi
0x180030118  push    rdi
0x180030119  push    r14
0x18003011b  sub     rsp, 40h
0x18003011f  lea     rbp, [rcx+3C388h]
0x180030126  mov     rbx, rcx
0x180030129  lea     rax, aCaacdectransfo_45; "CAACDecTransform::Initialize()"
0x180030130  mov     rcx, rbp; this
0x180030133  mov     r9d, 100h; unsigned int
0x180030139  mov     [rsp+68h+Format], rax; Format
0x18003013e  lea     r8, aCaacdectransfo_14; "CAACDecTransform::Initialize"
0x180030145  mov     edx, 4; unsigned __int8
0x18003014a  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18003014f  xor     r14d, r14d
0x180030152  lea     rsi, [rbx+3C1B8h]
0x180030159  mov     rcx, rbx; this
0x18003015c  mov     [rsi], r14
0x18003015f  mov     [rbx+3E8A0h], r14
0x180030166  call    ?_UnLockInputBuffer@CAACDecTransform@@AEAAJXZ; CAACDecTransform::_UnLockInputBuffer(void)
0x18003016b  mov     rcx, rbx; this
0x18003016e  mov     [rbx+3E8B8h], r14
0x180030175  call    ?_UnLockOutputBuffer@CAACDecTransform@@AEAAJXZ; CAACDecTransform::_UnLockOutputBuffer(void)
0x18003017a  lea     rcx, [rbx+0B0h]; this
0x180030181  call    ?InitializeAACDec@CAACDec@@QEAAJXZ; CAACDec::InitializeAACDec(void)
0x180030186  mov     edi, eax
0x180030188  test    eax, eax
0x18003018a  js      loc_1800302E2
0x180030190  call    ?IsLicensedComponentAAC_Internal@@YAHXZ; IsLicensedComponentAAC_Internal(void)
0x180030195  test    eax, eax
0x180030197  jnz     short loc_1800301A3
0x180030199  mov     edi, 0C004F011h
0x18003019e  jmp     loc_1800302E6
0x1800301a3  mov     eax, 1
0x1800301a8  mov     [rbx+0A8h], r14d
0x1800301af  lea     rcx, [rbx+3C1C0h]; void *
0x1800301b6  mov     [rbx+70h], eax
0x1800301b9  xor     edx, edx; Val
0x1800301bb  mov     [rbx+3C158h], rax
0x1800301c2  mov     r8d, 1C4h; Size
0x1800301c8  mov     [rbx+3C160h], eax
0x1800301ce  mov     qword ptr [rbx+48h], 0Fh
0x1800301d6  mov     [rbx+50h], r14
0x1800301da  mov     [rbx+58h], r14
0x1800301de  mov     dword ptr [rbx+74h], 0C000h
0x1800301e5  mov     [rbx+3E8D0h], r14
0x1800301ec  mov     [rbx+0D8h], r14
0x1800301f3  mov     [rbx+0E0h], r14d
0x1800301fa  mov     [rbx+0E8h], r14
0x180030201  mov     [rbx+0F0h], r14
0x180030208  mov     [rbx+0F8h], r14
0x18003020f  mov     [rbx+104h], r14
0x180030216  mov     [rbx+3C164h], r14b
0x18003021d  mov     [rbx+3E8D8h], r14b
0x180030224  mov     [rbx+12Ch], r14
0x18003022b  mov     [rbx+3E904h], r14d
0x180030232  mov     [rbx+3E8DCh], r14d
0x180030239  call    memset_0
0x18003023e  mov     rcx, rbx; this
0x180030241  call    ?_ConfigInputTypes@CAACDecTransform@@AEAAJXZ; CAACDecTransform::_ConfigInputTypes(void)
0x180030246  mov     edi, eax
0x180030248  test    eax, eax
0x18003024a  js      loc_1800302E2
0x180030250  mov     edx, 3; cInitialSize
0x180030255  mov     rcx, rsi; ppMFAttributes
0x180030258  call    cs:__imp_MFCreateAttributes
0x18003025f  nop     dword ptr [rax+rax+00h]
0x180030264  test    eax, eax
0x180030266  jnz     loc_18003032F
0x18003026c  mov     rcx, [rsi]
0x18003026f  test    rcx, rcx
0x180030272  jz      loc_18003032F
0x180030278  mov     rax, [rcx]
0x18003027b  lea     rdx, MFT_SUPPORT_DYNAMIC_FORMAT_CHANGE
0x180030282  xor     r8d, r8d
0x180030285  mov     rax, [rax+0A8h]
0x18003028c  call    cs:__guard_dispatch_icall_fptr
0x180030292  mov     edi, eax
0x180030294  test    eax, eax
0x180030296  js      short loc_1800302E2
0x180030298  mov     rcx, [rsi]
0x18003029b  lea     rdx, _GUID_a5106186_cc94_4bc9_8cd9_aa2f61f6807e
0x1800302a2  mov     r8d, [rbx+3C158h]
0x1800302a9  mov     rax, [rcx]
0x1800302ac  mov     rax, [rax+0A8h]
0x1800302b3  call    cs:__guard_dispatch_icall_fptr
0x1800302b9  mov     edi, eax
0x1800302bb  test    eax, eax
0x1800302bd  js      short loc_1800302E2
0x1800302bf  mov     rcx, [rsi]
0x1800302c2  lea     rdx, _GUID_4a52cda8_30f8_4216_be0f_ba0b2025921d
0x1800302c9  mov     r8d, [rbx+3C15Ch]
0x1800302d0  mov     rax, [rcx]
0x1800302d3  mov     rax, [rax+0A8h]
0x1800302da  call    cs:__guard_dispatch_icall_fptr
0x1800302e0  mov     edi, eax
0x1800302e2  test    edi, edi
0x1800302e4  jz      short loc_180030321
0x1800302e6  mov     r9d, 18Eh; unsigned int
0x1800302ec  lea     rax, aAvcoreCodecdsp_0; "avcore\\codecdsp\\audio\\aacdec\\curren"...
0x1800302f3  mov     [rsp+68h+var_30], r9d
0x1800302f8  lea     r8, aCaacdectransfo_14; "CAACDecTransform::Initialize"
0x1800302ff  mov     [rsp+68h+var_38], rax
0x180030304  mov     edx, 2; unsigned __int8
0x180030309  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x180030310  mov     [rsp+68h+var_40], edi
0x180030314  mov     rcx, rbp; this
0x180030317  mov     [rsp+68h+Format], rax; Format
0x18003031c  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180030321  mov     eax, edi
0x180030323  add     rsp, 40h
0x180030327  pop     r14
0x180030329  pop     rdi
0x18003032a  pop     rsi
0x18003032b  pop     rbp
0x18003032c  pop     rbx
0x18003032d  retn
0x18003032f  mov     [rsi], r14
0x180030332  mov     edi, 80004005h
0x180030337  jmp     short loc_1800302E6
```
