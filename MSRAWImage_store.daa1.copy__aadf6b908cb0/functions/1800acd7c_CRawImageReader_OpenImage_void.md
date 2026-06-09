# CRawImageReader::OpenImage(void)

- ea: `0x1800acd7c`
- end: `0x1800ad16c`
- name: `?OpenImage@CRawImageReader@@AEAAJXZ`
- size: `1008`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1800ad600`

## callees

- `0x180001220`
- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x180008de0`
- `0x18009b9e4`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a5b90`
- `0x1800acd7c`
- `0x1800aede4`
- `0x1800b4010`

## string_xrefs

- `0x1800acdb3`: `CRawImageReader::OpenImage`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRawImageReader::OpenImage(CRawImageReader *this)
{
  int *v2; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v4; // ebx
  unsigned int *v5; // r14
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ebx
  void ***v10; // rcx
  struct CallStackContext *v11; // rax
  int v12; // r8d
  int v13; // ecx
  int v14; // ebx
  int v15; // r8d
  int v16; // r9d
  PVOID *v17; // rcx
  void ***v18; // rcx
  LibRaw *v19; // rcx
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // r8
  __int64 v22; // rcx
  int v23; // eax
  void ***v24; // rcx
  int v26; // [rsp+20h] [rbp-78h]
  _BYTE v27[8]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v28; // [rsp+38h] [rbp-60h]
  _BYTE v29[32]; // [rsp+40h] [rbp-58h] BYREF
  _QWORD v30[2]; // [rsp+60h] [rbp-38h] BYREF

  v28 = -2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v27, "CRawImageReader::OpenImage", 863);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v30);
    *((_DWORD *)ThreadRelativeContext + 504) = v4;
  }
  v5 = (unsigned int *)((char *)this + 56);
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v29,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    "CRawImageReader::OpenImage",
    v2,
    v26);
  if ( *((_BYTE *)this + 108) )
  {
    v9 = -2147418113;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *v5,
        -2147418113);
    }
    v10 = (void ***)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v11 + 499) != -2147418113 )
      {
        v12 = 865;
LABEL_14:
        CallStackContext::TraceFailure(v11, "CRawImageReader::OpenImage", v12, v9);
      }
    }
  }
  else
  {
    if ( (unsigned int)dword_1800E50F0 > 4 )
    {
      v30[0] = this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        v6,
        (unsigned int)byte_1800D7429,
        v7,
        v8,
        (__int64)v30);
    }
    v14 = (***((__int64 (__fastcall ****)(_QWORD, _QWORD))this + 18))(
            *((_QWORD *)this + 18),
            (*((_QWORD *)this + 33) + 16LL) & ((unsigned __int128)-(__int128)*((unsigned __int64 *)this + 33) >> 64));
    if ( (unsigned int)dword_1800E50F0 > 4 )
    {
      v30[0] = this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        v13,
        (unsigned int)&word_1800D73F6,
        v15,
        v16,
        (__int64)v30);
    }
    if ( v14 )
    {
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v5, v14);
        v17 = (PVOID *)WPP_GLOBAL_Control;
      }
      v9 = -2003292320;
      if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 && *((_BYTE *)v17 + 25) >= 4u )
        WPP_SF_Dd(v17[2], 76, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v5, -2003292320);
      v18 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v11 + 499) != -2003292320 )
        {
          v12 = 888;
          goto LABEL_14;
        }
      }
    }
    else
    {
      v19 = (LibRaw *)*((_QWORD *)this + 18);
      *((_DWORD *)this + 30) = *((_DWORD *)v19 + 12);
      LibRaw::adjust_sizes_info_only(v19);
      v20 = -1;
      if ( *((_QWORD *)this + 18) != -204 )
      {
        v21 = -1;
        do
          ++v21;
        while ( *(_BYTE *)(*((_QWORD *)this + 18) + 204LL + v21) );
        if ( v21 > 0x7FFFFFFF )
          *((_DWORD *)this + 71) = -2147024785;
        else
          CMFBaseStringT<char>::_Append((char *)this + 280);
      }
      if ( *((_QWORD *)this + 18) != -268 )
      {
        do
          ++v20;
        while ( *(_BYTE *)(*((_QWORD *)this + 18) + 268LL + v20) );
        if ( v20 > 0x7FFFFFFF )
          *((_DWORD *)this + 109) = -2147024785;
        else
          CMFBaseStringT<char>::_Append((char *)this + 432);
      }
      v22 = *((_QWORD *)this + 18);
      *((_DWORD *)this + 28) = *(unsigned __int16 *)(v22 + 30);
      *((_DWORD *)this + 29) = *(unsigned __int16 *)(v22 + 28);
      v23 = CRawImageReader::AddMissingIFDEntries(this);
      v9 = v23;
      if ( v23 >= 0 )
      {
        *((_BYTE *)this + 108) = 1;
        goto LABEL_55;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v5, v23);
      }
      v24 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v11 + 499) != v9 )
        {
          v12 = 902;
          goto LABEL_14;
        }
      }
    }
  }
LABEL_55:
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v29);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v27);
  return v9;
}

```

## disassembly

```asm
0x1800acd7c  mov     r11, rsp
0x1800acd7f  push    rdi
0x1800acd80  push    r14
0x1800acd82  push    r15
0x1800acd84  sub     rsp, 80h
0x1800acd8b  mov     qword ptr [r11-60h], 0FFFFFFFFFFFFFFFEh
0x1800acd93  mov     [r11+10h], rbx
0x1800acd97  mov     [r11+18h], rsi
0x1800acd9b  mov     rax, cs:__security_cookie
0x1800acda2  xor     rax, rsp
0x1800acda5  mov     [rsp+98h+var_28], rax
0x1800acdaa  mov     rsi, rcx
0x1800acdad  mov     r8d, 35Fh; int
0x1800acdb3  lea     r15, aCrawimagereade_19; "CRawImageReader::OpenImage"
0x1800acdba  mov     rdx, r15; char *
0x1800acdbd  lea     rcx, [r11-68h]; this
0x1800acdc1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800acdc6  nop
0x1800acdc7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800acdce  cmp     byte ptr [rcx+8], 0
0x1800acdd2  jz      short loc_1800ACE2A
0x1800acdd4  cmp     qword ptr [rsi+110h], 0
0x1800acddc  jz      short loc_1800ACE2A
0x1800acdde  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800acde3  mov     rdi, rax
0x1800acde6  mov     rcx, [rsi+110h]
0x1800acded  mov     rdx, [rcx]
0x1800acdf0  mov     rax, [rdx+128h]
0x1800acdf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acdfc  mov     ebx, eax
0x1800acdfe  mov     rcx, [rsi+110h]
0x1800ace05  mov     rdx, [rcx]
0x1800ace08  mov     rax, [rdx+118h]
0x1800ace0f  lea     rdx, [rsp+98h+var_38]
0x1800ace14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ace19  movups  xmm0, xmmword ptr [rax]
0x1800ace1c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800ace24  mov     [rdi+7E0h], ebx
0x1800ace2a  lea     r14, [rsi+38h]
0x1800ace2e  mov     rax, rsi
0x1800ace31  neg     rax
0x1800ace34  sbb     rdx, rdx
0x1800ace37  and     rdx, r14; struct CTraceBase *
0x1800ace3a  mov     r8, r15; char *
0x1800ace3d  lea     rcx, [rsp+98h+var_58]; this
0x1800ace42  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800ace47  nop
0x1800ace48  cmp     byte ptr [rsi+6Ch], 0
0x1800ace4c  jz      loc_1800ACEE0
0x1800ace52  mov     ebx, 8000FFFFh
0x1800ace57  lea     rdi, WPP_GLOBAL_Control
0x1800ace5e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ace65  cmp     rcx, rdi
0x1800ace68  jz      short loc_1800ACE92
0x1800ace6a  test    byte ptr [rcx+1Ch], 1
0x1800ace6e  jz      short loc_1800ACE92
0x1800ace70  cmp     byte ptr [rcx+19h], 4
0x1800ace74  jb      short loc_1800ACE92
0x1800ace76  mov     edx, 4Ah ; 'J'
0x1800ace7b  mov     [rsp+98h+var_78], ebx
0x1800ace7f  mov     r9d, [r14]
0x1800ace82  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ace89  mov     rcx, [rcx+10h]
0x1800ace8d  call    WPP_SF_Dd
0x1800ace92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ace99  test    rcx, rcx
0x1800ace9c  jnz     short loc_1800ACEAC
0x1800ace9e  lea     rcx, off_1800E5190; this
0x1800acea5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aceac  cmp     byte ptr [rcx+8], 0
0x1800aceb0  jz      loc_1800AD12E
0x1800aceb6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800acebb  cmp     [rax+7CCh], ebx
0x1800acec1  jz      loc_1800AD12E
0x1800acec7  mov     r8d, 361h; int
0x1800acecd  mov     r9d, ebx; int
0x1800aced0  mov     rdx, r15; char *
0x1800aced3  mov     rcx, rax; this
0x1800aced6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800acedb  jmp     loc_1800AD12E
0x1800acee0  cmp     cs:dword_1800E50F0, 4
0x1800acee7  jbe     short loc_1800ACF04
0x1800acee9  mov     [rsp+98h+var_38], rsi
0x1800aceee  lea     rax, [rsp+98h+var_38]
0x1800acef3  mov     qword ptr [rsp+98h+var_78], rax
0x1800acef8  lea     rdx, byte_1800D7429
0x1800aceff  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800acf04  mov     rcx, [rsi+90h]
0x1800acf0b  mov     rax, [rsi+108h]
0x1800acf12  lea     r8, [rax+10h]
0x1800acf16  neg     rax
0x1800acf19  sbb     rdx, rdx
0x1800acf1c  and     rdx, r8
0x1800acf1f  mov     rax, [rcx]
0x1800acf22  mov     rax, [rax]
0x1800acf25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acf2a  mov     ebx, eax
0x1800acf2c  cmp     cs:dword_1800E50F0, 4
0x1800acf33  jbe     short loc_1800ACF50
0x1800acf35  mov     [rsp+98h+var_38], rsi
0x1800acf3a  lea     rax, [rsp+98h+var_38]
0x1800acf3f  mov     qword ptr [rsp+98h+var_78], rax
0x1800acf44  lea     rdx, word_1800D73F6
0x1800acf4b  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800acf50  test    ebx, ebx
0x1800acf52  jz      loc_1800AD00C
0x1800acf58  lea     rdi, WPP_GLOBAL_Control
0x1800acf5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acf66  cmp     rcx, rdi
0x1800acf69  jz      short loc_1800ACF9A
0x1800acf6b  test    byte ptr [rcx+1Ch], 1
0x1800acf6f  jz      short loc_1800ACF9A
0x1800acf71  cmp     byte ptr [rcx+19h], 4
0x1800acf75  jb      short loc_1800ACF9A
0x1800acf77  mov     edx, 4Bh ; 'K'
0x1800acf7c  mov     [rsp+98h+var_78], ebx
0x1800acf80  mov     r9d, [r14]
0x1800acf83  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800acf8a  mov     rcx, [rcx+10h]
0x1800acf8e  call    WPP_SF_Dd
0x1800acf93  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acf9a  mov     ebx, 88982F60h
0x1800acf9f  cmp     rcx, rdi
0x1800acfa2  jz      short loc_1800ACFCC
0x1800acfa4  test    byte ptr [rcx+1Ch], 1
0x1800acfa8  jz      short loc_1800ACFCC
0x1800acfaa  cmp     byte ptr [rcx+19h], 4
0x1800acfae  jb      short loc_1800ACFCC
0x1800acfb0  mov     edx, 4Ch ; 'L'
0x1800acfb5  mov     [rsp+98h+var_78], ebx
0x1800acfb9  mov     r9d, [r14]
0x1800acfbc  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800acfc3  mov     rcx, [rcx+10h]
0x1800acfc7  call    WPP_SF_Dd
0x1800acfcc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800acfd3  test    rcx, rcx
0x1800acfd6  jnz     short loc_1800ACFE6
0x1800acfd8  lea     rcx, off_1800E5190; this
0x1800acfdf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800acfe6  cmp     byte ptr [rcx+8], 0
0x1800acfea  jz      loc_1800AD12E
0x1800acff0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800acff5  cmp     [rax+7CCh], ebx
0x1800acffb  jz      loc_1800AD12E
0x1800ad001  mov     r8d, 378h
0x1800ad007  jmp     loc_1800ACECD
0x1800ad00c  mov     rcx, [rsi+90h]; this
0x1800ad013  mov     eax, [rcx+30h]
0x1800ad016  mov     [rsi+78h], eax
0x1800ad019  call    ?adjust_sizes_info_only@LibRaw@@QEAAHXZ; LibRaw::adjust_sizes_info_only(void)
0x1800ad01e  lea     rcx, [rsi+118h]
0x1800ad025  mov     rdx, [rsi+90h]
0x1800ad02c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800ad030  mov     edi, 8007006Fh
0x1800ad035  add     rdx, 0CCh
0x1800ad03c  jz      short loc_1800AD05E
0x1800ad03e  mov     r8, rbx
0x1800ad041  inc     r8
0x1800ad044  cmp     byte ptr [rdx+r8], 0
0x1800ad049  jnz     short loc_1800AD041
0x1800ad04b  cmp     r8, 7FFFFFFFh
0x1800ad052  ja      short loc_1800AD05B
0x1800ad054  call    ?_Append@?$CMFBaseStringT@D@@IEAAJPEBDJ@Z; CMFBaseStringT<char>::_Append(char const *,long)
0x1800ad059  jmp     short loc_1800AD05E
0x1800ad05b  mov     [rcx+4], edi
0x1800ad05e  lea     rcx, [rsi+1B0h]
0x1800ad065  mov     rdx, [rsi+90h]
0x1800ad06c  add     rdx, 10Ch
0x1800ad073  jz      short loc_1800AD094
0x1800ad075  inc     rbx
0x1800ad078  cmp     byte ptr [rdx+rbx], 0
0x1800ad07c  jnz     short loc_1800AD075
0x1800ad07e  cmp     rbx, 7FFFFFFFh
0x1800ad085  ja      short loc_1800AD091
0x1800ad087  mov     r8d, ebx
0x1800ad08a  call    ?_Append@?$CMFBaseStringT@D@@IEAAJPEBDJ@Z; CMFBaseStringT<char>::_Append(char const *,long)
0x1800ad08f  jmp     short loc_1800AD094
0x1800ad091  mov     [rcx+4], edi
0x1800ad094  mov     rcx, [rsi+90h]
0x1800ad09b  movzx   eax, word ptr [rcx+1Eh]
0x1800ad09f  mov     [rsi+70h], eax
0x1800ad0a2  movzx   eax, word ptr [rcx+1Ch]
0x1800ad0a6  mov     [rsi+74h], eax
0x1800ad0a9  mov     rcx, rsi; this
0x1800ad0ac  call    ?AddMissingIFDEntries@CRawImageReader@@AEAAJXZ; CRawImageReader::AddMissingIFDEntries(void)
0x1800ad0b1  mov     ebx, eax
0x1800ad0b3  test    eax, eax
0x1800ad0b5  jns     short loc_1800AD12A
0x1800ad0b7  lea     rdi, WPP_GLOBAL_Control
0x1800ad0be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad0c5  cmp     rcx, rdi
0x1800ad0c8  jz      short loc_1800AD0F2
0x1800ad0ca  test    byte ptr [rcx+1Ch], 1
0x1800ad0ce  jz      short loc_1800AD0F2
0x1800ad0d0  cmp     byte ptr [rcx+19h], 4
0x1800ad0d4  jb      short loc_1800AD0F2
0x1800ad0d6  mov     edx, 4Dh ; 'M'
0x1800ad0db  mov     [rsp+98h+var_78], eax
0x1800ad0df  mov     r9d, [r14]
0x1800ad0e2  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ad0e9  mov     rcx, [rcx+10h]
0x1800ad0ed  call    WPP_SF_Dd
0x1800ad0f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad0f9  test    rcx, rcx
0x1800ad0fc  jnz     short loc_1800AD10C
0x1800ad0fe  lea     rcx, off_1800E5190; this
0x1800ad105  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad10c  cmp     byte ptr [rcx+8], 0
0x1800ad110  jz      short loc_1800AD12E
0x1800ad112  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ad117  cmp     [rax+7CCh], ebx
0x1800ad11d  jz      short loc_1800AD12E
0x1800ad11f  mov     r8d, 386h
0x1800ad125  jmp     loc_1800ACECD
0x1800ad12a  mov     byte ptr [rsi+6Ch], 1
0x1800ad12e  lea     rcx, [rsp+98h+var_58]; this
0x1800ad133  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800ad138  nop
0x1800ad139  lea     rcx, [rsp+98h+var_68]; this
0x1800ad13e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ad143  mov     eax, ebx
0x1800ad145  mov     rcx, [rsp+98h+var_28]
0x1800ad14a  xor     rcx, rsp; StackCookie
0x1800ad14d  call    __security_check_cookie
0x1800ad152  lea     r11, [rsp+98h+var_18]
0x1800ad15a  mov     rbx, [r11+28h]
0x1800ad15e  mov     rsi, [r11+30h]
0x1800ad162  mov     rsp, r11
0x1800ad165  pop     r15
0x1800ad167  pop     r14
0x1800ad169  pop     rdi
0x1800ad16a  retn
```
