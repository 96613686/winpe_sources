# WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)

- ea: `0x18001e6e0`
- end: `0x18001ea50`
- name: `?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ`
- size: `880`
- prototype: `void(WindowsPerformanceRecorder *__hidden this, unsigned __int8, const char *, unsigned int, char *Format, const char *, ...)`
- caller_count: `121`
- callee_count: `4`
- tags: ``

## callers

- `0x180001cc4`
- `0x180001d74`
- `0x180002f00`
- `0x1800091b0`
- `0x180009820`
- `0x18000e3d0`
- `0x180013f6c`
- `0x18001656c`
- `0x180018f80`
- `0x1800191d0`
- `0x1800193a8`
- `0x1800195b0`
- `0x18001a92c`
- `0x18001bf98`
- `0x18001c5dc`
- `0x18001c8bc`
- `0x18001cdd0`
- `0x18001d1bc`
- `0x18001d3d8`
- `0x18001da90`
- `0x18001db70`
- `0x18001e2b8`
- `0x18001ed98`
- `0x18001f170`
- `0x18001fbc0`
- `0x180023090`
- `0x1800236b0`
- `0x180023b34`
- `0x180024074`
- `0x180024270`
- `0x180024de0`
- `0x18002f230`
- `0x18002f5c4`
- `0x18002f980`
- `0x18002fce0`
- `0x180031374`
- `0x180032450`
- `0x1800326e0`
- `0x1800329bc`
- `0x180032adc`
- `0x180034bec`
- `0x1800368dc`
- `0x1800374dc`
- `0x1800385d4`
- `0x1800389b8`
- `0x180039084`
- `0x180039d24`
- `0x18003a1f0`
- `0x18003af80`
- `0x18003bcd0`

## callees

- `0x180001008`
- `0x18001e6e0`
- `0x18004ece0`
- `0x18004fb34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001e755`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001e755`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e8d8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e8d8`

## pseudocode

```c
void WindowsPerformanceRecorder::TraceHR(
        WindowsPerformanceRecorder *this,
        const char *a2,
        const char *a3,
        unsigned int a4,
        char *Format,
        const char *ArgList,
        ...)
{
  int v7; // r12d
  int v8; // r14d
  __int64 v10; // rbx
  char *v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  int v17; // eax
  int v18; // ebx
  __int64 v19; // rcx
  __int16 *v20; // rdx
  const char **v21; // rax
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+40h] [rbp-C0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v24; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  char *v26; // [rsp+60h] [rbp-A0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-98h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-80h] BYREF
  char *v29; // [rsp+90h] [rbp-70h]
  int v30; // [rsp+98h] [rbp-68h]
  int v31; // [rsp+9Ch] [rbp-64h]
  const char *v32; // [rsp+A0h] [rbp-60h]
  int v33; // [rsp+A8h] [rbp-58h]
  int v34; // [rsp+ACh] [rbp-54h]
  int *v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  char *v37; // [rsp+C0h] [rbp-40h]
  int v38; // [rsp+C8h] [rbp-38h]
  int v39; // [rsp+CCh] [rbp-34h]
  __int64 *v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  char Buffer[256]; // [rsp+E0h] [rbp-20h] BYREF

  v7 = (unsigned __int8)this;
  v8 = (int)a3;
  v10 = -1;
  v11 = Buffer;
  *(_QWORD *)&EventDescriptor.Id = 0;
  if ( vsnprintf_s(Buffer, 0x100u, 0xFFFFFFFFFFFFFFFFuLL, Format, (va_list)&ArgList) < 0
    && *(_DWORD *)_o__errno(v13, v12) == 22 )
  {
    v11 = Format;
  }
  switch ( v7 )
  {
    case 1:
      if ( (unsigned int)dword_1800BDC60 <= 1 )
        return;
      v19 = qword_1800BDC78;
      if ( (qword_1800BDC70 & 0x10000000) == 0 || (qword_1800BDC78 & 0x10000000) != qword_1800BDC78 )
        return;
      v20 = &word_1800A53F6;
      goto LABEL_33;
    case 2:
      if ( (unsigned int)dword_1800BDC60 <= 2 )
        return;
      v19 = qword_1800BDC78;
      if ( (qword_1800BDC70 & 0x20000000) == 0 || (qword_1800BDC78 & 0x20000000) != qword_1800BDC78 )
        return;
      v20 = (__int16 *)byte_1800A53B3;
LABEL_33:
      v25 = (__int64)a2;
      p_EventDescriptor = &EventDescriptor;
      v21 = (const char **)&v25;
      *(_QWORD *)&EventDescriptor.Id = 0x1000000;
      goto LABEL_34;
    case 3:
      if ( (unsigned int)dword_1800BDC60 <= 3 )
        return;
      v19 = qword_1800BDC78;
      if ( (qword_1800BDC70 & 0x40000000) == 0 || (qword_1800BDC78 & 0x40000000) != qword_1800BDC78 )
        return;
      v25 = 0x1000000;
      p_EventDescriptor = (EVENT_DESCRIPTOR *)&v25;
      v20 = (__int16 *)qword_1800A5370;
      *(_QWORD *)&EventDescriptor.Id = a2;
      v21 = (const char **)&EventDescriptor;
LABEL_34:
      v24 = a4;
      v26 = v11;
      v23 = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v19,
        (__int64)v20,
        v14,
        v15,
        v21,
        (__int64)&v23,
        (const char **)&v26,
        (__int64)&v24,
        (__int64)p_EventDescriptor);
      return;
  }
  if ( v7 == 4
    && (unsigned int)dword_1800BDC60 > 4
    && (qword_1800BDC70 & 0x80000000) != 0
    && (qword_1800BDC78 & 0x80000000) == qword_1800BDC78 )
  {
    v25 = 0x1000000;
    v40 = &v25;
    v23 = v8;
    v41 = 8;
    if ( v11 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v11[v16] );
      v17 = v16 + 1;
    }
    else
    {
      v11 = (char *)&byte_1800986EF;
      v17 = 1;
    }
    v38 = v17;
    v35 = &v23;
    v37 = v11;
    v39 = 0;
    v36 = 4;
    if ( a2 )
    {
      do
        ++v10;
      while ( a2[v10] );
      v18 = v10 + 1;
    }
    else
    {
      a2 = &byte_1800986EF;
      v18 = 1;
    }
    *(_DWORD *)&EventDescriptor.Level = 4;
    UserData.Ptr = (ULONGLONG)off_1800BDC68;
    EventDescriptor.Keyword = 0x80000000LL;
    v32 = a2;
    v33 = v18;
    v34 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = (unsigned __int16)*off_1800BDC68;
    v29 = byte_1800A5341;
    UserData.Reserved = 2;
    v30 = 46;
    v31 = 1;
    v24 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
  }
}

```

## disassembly

```asm
0x18001e6e0  push    rbp
0x18001e6e2  push    rbx
0x18001e6e3  push    rsi
0x18001e6e4  push    rdi
0x18001e6e5  push    r12
0x18001e6e7  push    r13
0x18001e6e9  push    r14
0x18001e6eb  push    r15
0x18001e6ed  lea     rbp, [rsp-0F8h]
0x18001e6f5  sub     rsp, 1F8h
0x18001e6fc  mov     rax, cs:__security_cookie
0x18001e703  xor     rax, rsp
0x18001e706  mov     [rbp+130h+var_50], rax
0x18001e70d  mov     r15d, r9d
0x18001e710  movzx   r12d, cl
0x18001e714  mov     r9, [rbp+130h+Format]; Format
0x18001e71b  lea     rax, [rbp+130h+arg_28]
0x18001e722  mov     r14d, r8d
0x18001e725  mov     [rsp+230h+ArgList], rax; ArgList
0x18001e72a  mov     rsi, rdx
0x18001e72d  lea     rcx, [rbp+130h+Buffer]; Buffer
0x18001e731  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001e738  lea     rdi, [rbp+130h+Buffer]
0x18001e73c  xor     r13d, r13d
0x18001e73f  mov     r8, rbx; MaxCount
0x18001e742  mov     edx, 100h; BufferCount
0x18001e747  mov     qword ptr [rsp+230h+EventDescriptor.Id], r13
0x18001e74c  call    _vsnprintf_s
0x18001e751  test    eax, eax
0x18001e753  jns     short loc_18001E766
0x18001e755  call    cs:__imp__o__errno
0x18001e75b  cmp     dword ptr [rax], 16h
0x18001e75e  cmovz   rdi, [rbp+130h+Format]
0x18001e766  mov     ecx, r12d
0x18001e769  sub     ecx, 1
0x18001e76c  jz      loc_18001E9A5
0x18001e772  sub     ecx, 1
0x18001e775  jz      loc_18001E963
0x18001e77b  sub     ecx, 1
0x18001e77e  jz      loc_18001E8E3
0x18001e784  cmp     ecx, 1
0x18001e787  jnz     loc_18001EA2D
0x18001e78d  mov     eax, cs:dword_1800BDC60
0x18001e793  cmp     eax, 4
0x18001e796  jbe     loc_18001EA2D
0x18001e79c  mov     rcx, cs:qword_1800BDC78
0x18001e7a3  mov     edx, 80000000h
0x18001e7a8  mov     rax, cs:qword_1800BDC70
0x18001e7af  test    rdx, rax
0x18001e7b2  jz      loc_18001EA2D
0x18001e7b8  mov     rax, rcx
0x18001e7bb  and     rax, rdx
0x18001e7be  cmp     rax, rcx
0x18001e7c1  jnz     loc_18001EA2D
0x18001e7c7  mov     [rsp+230h+var_1D8], 1000000h
0x18001e7d0  lea     rax, [rsp+230h+var_1D8]
0x18001e7d5  mov     [rbp+130h+var_160], rax
0x18001e7d9  mov     [rsp+230h+var_1E0], r14d
0x18001e7de  mov     [rbp+130h+var_158], 8
0x18001e7e6  test    rdi, rdi
0x18001e7e9  jz      short loc_18001E7FD
0x18001e7eb  mov     rax, rbx
0x18001e7ee  xchg    ax, ax
0x18001e7f0  inc     rax
0x18001e7f3  cmp     [rdi+rax], r13b
0x18001e7f7  jnz     short loc_18001E7F0
0x18001e7f9  inc     eax
0x18001e7fb  jmp     short loc_18001E809
0x18001e7fd  lea     rdi, byte_1800986EF
0x18001e804  mov     eax, 1
0x18001e809  mov     [rbp+130h+var_168], eax
0x18001e80c  lea     rax, [rsp+230h+var_1E0]
0x18001e811  mov     [rbp+130h+var_180], rax
0x18001e815  mov     [rbp+130h+var_170], rdi
0x18001e819  mov     [rbp+130h+var_164], r13d
0x18001e81d  mov     [rbp+130h+var_178], 4
0x18001e825  test    rsi, rsi
0x18001e828  jz      short loc_18001E83D
0x18001e82a  nop     word ptr [rax+rax+00h]
0x18001e830  inc     rbx
0x18001e833  cmp     [rsi+rbx], r13b
0x18001e837  jnz     short loc_18001E830
0x18001e839  inc     ebx
0x18001e83b  jmp     short loc_18001E849
0x18001e83d  lea     rsi, byte_1800986EF
0x18001e844  mov     ebx, 1
0x18001e849  movzx   eax, cs:word_1800A5337
0x18001e850  lea     rcx, _TraceLoggingMetadata
0x18001e857  mov     dword ptr [rsp+230h+EventDescriptor.Level], eax
0x18001e85b  xor     r9d, r9d; RelatedActivityId
0x18001e85e  mov     rax, cs:off_1800BDC68
0x18001e865  xor     r8d, r8d; ActivityId
0x18001e868  mov     [rbp+130h+var_1B0.Ptr], rax
0x18001e86c  mov     [rsp+230h+EventDescriptor.Keyword], rdx
0x18001e871  lea     rdx, [rsp+230h+EventDescriptor]; EventDescriptor
0x18001e876  mov     [rbp+130h+var_190], rsi
0x18001e87a  mov     [rbp+130h+var_188], ebx
0x18001e87d  mov     [rbp+130h+var_184], r13d
0x18001e881  mov     dword ptr [rsp+230h+EventDescriptor.Id], 0B000000h
0x18001e889  movzx   eax, word ptr [rax]
0x18001e88c  mov     [rbp+130h+var_1B0.Size], eax
0x18001e88f  lea     rax, byte_1800A5341
0x18001e896  mov     [rbp+130h+var_1A0], rax
0x18001e89a  lea     rax, _TraceLoggingMetadataEnd
0x18001e8a1  sub     eax, ecx
0x18001e8a3  mov     dword ptr [rbp+130h+var_1B0.0Ch], 2
0x18001e8aa  mov     [rbp+130h+var_198], 2Eh ; '.'
0x18001e8b1  mov     [rbp+130h+var_194], 1
0x18001e8b8  mov     [rsp+230h+var_1DC], eax
0x18001e8bc  mov     eax, [rsp+230h+var_1DC]
0x18001e8c0  mov     rcx, cs:RegHandle; RegHandle
0x18001e8c7  lea     rax, [rbp+130h+var_1B0]
0x18001e8cb  mov     [rsp+230h+UserData], rax; UserData
0x18001e8d0  mov     dword ptr [rsp+230h+ArgList], 6; UserDataCount
0x18001e8d8  call    cs:__imp_EventWriteTransfer
0x18001e8de  jmp     loc_18001EA2D
0x18001e8e3  mov     eax, cs:dword_1800BDC60
0x18001e8e9  cmp     eax, 3
0x18001e8ec  jbe     loc_18001EA2D
0x18001e8f2  mov     rcx, cs:qword_1800BDC78
0x18001e8f9  mov     rax, cs:qword_1800BDC70
0x18001e900  bt      rax, 1Eh
0x18001e905  jnb     loc_18001EA2D
0x18001e90b  mov     rax, rcx
0x18001e90e  and     eax, 40000000h
0x18001e913  cmp     rax, rcx
0x18001e916  jnz     loc_18001EA2D
0x18001e91c  lea     rax, [rsp+230h+var_1D8]
0x18001e921  mov     [rsp+230h+var_1D8], 1000000h
0x18001e92a  mov     [rsp+230h+var_1F0], rax
0x18001e92f  lea     rdx, qword_1800A5370
0x18001e936  lea     rax, [rsp+230h+var_1DC]
0x18001e93b  mov     qword ptr [rsp+230h+EventDescriptor.Id], rsi
0x18001e940  mov     [rsp+230h+var_1F8], rax
0x18001e945  lea     rax, [rsp+230h+var_1D0]
0x18001e94a  mov     [rsp+230h+var_200], rax
0x18001e94f  lea     rax, [rsp+230h+var_1E0]
0x18001e954  mov     [rsp+230h+UserData], rax
0x18001e959  lea     rax, [rsp+230h+EventDescriptor]
0x18001e95e  jmp     loc_18001EA14
0x18001e963  mov     eax, cs:dword_1800BDC60
0x18001e969  cmp     eax, 2
0x18001e96c  jbe     loc_18001EA2D
0x18001e972  mov     rcx, cs:qword_1800BDC78
0x18001e979  mov     rax, cs:qword_1800BDC70
0x18001e980  bt      rax, 1Dh
0x18001e985  jnb     loc_18001EA2D
0x18001e98b  mov     rax, rcx
0x18001e98e  and     eax, 20000000h
0x18001e993  cmp     rax, rcx
0x18001e996  jnz     loc_18001EA2D
0x18001e99c  lea     rdx, byte_1800A53B3
0x18001e9a3  jmp     short loc_18001E9D9
0x18001e9a5  mov     eax, cs:dword_1800BDC60
0x18001e9ab  cmp     eax, 1
0x18001e9ae  jbe     short loc_18001EA2D
0x18001e9b0  mov     rcx, cs:qword_1800BDC78
0x18001e9b7  mov     rax, cs:qword_1800BDC70
0x18001e9be  bt      rax, 1Ch
0x18001e9c3  jnb     short loc_18001EA2D
0x18001e9c5  mov     rax, rcx
0x18001e9c8  and     eax, 10000000h
0x18001e9cd  cmp     rax, rcx
0x18001e9d0  jnz     short loc_18001EA2D
0x18001e9d2  lea     rdx, word_1800A53F6
0x18001e9d9  lea     rax, [rsp+230h+EventDescriptor]
0x18001e9de  mov     [rsp+230h+var_1D8], rsi
0x18001e9e3  mov     [rsp+230h+var_1F0], rax
0x18001e9e8  lea     rax, [rsp+230h+var_1DC]
0x18001e9ed  mov     [rsp+230h+var_1F8], rax
0x18001e9f2  lea     rax, [rsp+230h+var_1D0]
0x18001e9f7  mov     [rsp+230h+var_200], rax
0x18001e9fc  lea     rax, [rsp+230h+var_1E0]
0x18001ea01  mov     [rsp+230h+UserData], rax
0x18001ea06  lea     rax, [rsp+230h+var_1D8]
0x18001ea0b  mov     qword ptr [rsp+230h+EventDescriptor.Id], 1000000h
0x18001ea14  mov     [rsp+230h+ArgList], rax
0x18001ea19  mov     [rsp+230h+var_1DC], r15d
0x18001ea1e  mov     [rsp+230h+var_1D0], rdi
0x18001ea23  mov     [rsp+230h+var_1E0], r14d
0x18001ea28  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001ea2d  mov     rcx, [rbp+130h+var_50]
0x18001ea34  xor     rcx, rsp; StackCookie
0x18001ea37  call    __security_check_cookie
0x18001ea3c  add     rsp, 1F8h
0x18001ea43  pop     r15
0x18001ea45  pop     r14
0x18001ea47  pop     r13
0x18001ea49  pop     r12
0x18001ea4b  pop     rdi
0x18001ea4c  pop     rsi
0x18001ea4d  pop     rbx
0x18001ea4e  pop     rbp
0x18001ea4f  retn
```
