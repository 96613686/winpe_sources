# MBSettingUXLogging::Warn(char const *,ulong,char const *,...)

- ea: `0x18000bde0`
- end: `0x18000c24f`
- name: `?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ`
- size: `1135`
- prototype: `void(const char *, unsigned int, const char *, ...)`
- caller_count: `31`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180008da0`
- `0x180009c10`
- `0x18000a460`
- `0x18000b500`
- `0x18000bce0`
- `0x180014490`
- `0x180014fec`
- `0x180018304`
- `0x18001a1ec`
- `0x18001a9e0`
- `0x18001addc`
- `0x18001c0cc`
- `0x18001dc70`
- `0x180020ec0`
- `0x1800211a8`
- `0x1800215a0`
- `0x180022064`
- `0x180024e38`
- `0x18003d630`
- `0x180048440`
- `0x18004b580`
- `0x18004e4b0`
- `0x1800504d0`
- `0x180050510`
- `0x180050690`
- `0x180050820`
- `0x180050950`
- `0x180050af0`
- `0x180050c50`
- `0x180050d70`
- `0x180050e80`

## callees

- `0x18000bde0`
- `0x180010250`
- `0x180010b94`
- `0x18002cd20`
- `0x18002d1ac`
- `0x18002d8e0`
- `0x180055dd0`
- `0x180059010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c22c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c22c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000be50`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000c060`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000be50`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000c060`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000bef5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c105`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000bef5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c105`

## pseudocode

```c
void MBSettingUXLogging::Warn(const char *a1, WINBOOL a2, const char *a3, ...)
{
  __int64 v5; // r10
  const unsigned __int16 *v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  int v10; // ecx
  __int64 v11; // rcx
  __int64 v12; // rax
  int v14; // ecx
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-C8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  __int16 *v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+6Ch] [rbp-94h]
  const char *v22; // [rsp+70h] [rbp-90h]
  int v23; // [rsp+78h] [rbp-88h]
  int v24; // [rsp+7Ch] [rbp-84h]
  void *p_Context; // [rsp+80h] [rbp-80h]
  __int64 v26; // [rsp+88h] [rbp-78h]
  wchar_t *v27; // [rsp+90h] [rbp-70h]
  int v28; // [rsp+98h] [rbp-68h]
  int v29; // [rsp+9Ch] [rbp-64h]
  wchar_t Format[512]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Buffer[1536]; // [rsp+4A0h] [rbp+3A0h] BYREF
  va_list Args; // [rsp+10F8h] [rbp+FF8h] BYREF

  va_start(Args, a3);
  Context = 0;
  if ( Args )
  {
    StringCchPrintfW(Format, 0x200u, L"%hs", a3);
    if ( (unsigned int)vsnwprintf(Buffer, 0x5FFu, Format, Args) > 0x5FE )
      Buffer[1535] = 0;
    Context = 0;
    fPending = 0;
    if ( InitOnceBeginInitialize(&`MBSettingUXLogging::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
    {
      qword_18007EE30 = 0;
      Context = &qword_18007EE28;
      qword_18007EE28 = (__int64)&MBSettingUXLogging::`vftable';
      byte_18007EE38 = 0;
      dword_18007EE3C = 0;
      CallbackContext = &`MBSettingUXLogging::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(`MBSettingUXLogging::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
      qword_18007EE30 = (__int64)CallbackContext;
      byte_18007EE38 = 1;
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
      dword_18007EE3C = 1;
      (*(void (__fastcall **)(__int64 *))(qword_18007EE28 + 8))(&qword_18007EE28);
      InitOnceComplete(&`MBSettingUXLogging::Instance'::`2'::wrapper, 0, &qword_18007EE28);
    }
    v5 = *((_QWORD *)Context + 1);
    if ( *(_DWORD *)v5 > 3u )
    {
      v11 = -1;
      LODWORD(Context) = a2;
      v12 = -1;
      while ( Buffer[++v12] != 0 )
        ;
      v29 = 0;
      v28 = 2 * v12 + 2;
      p_Context = &Context;
      v27 = Buffer;
      v26 = 4;
      if ( a1 )
      {
        do
          ++v11;
        while ( a1[v11] );
        v14 = v11 + 1;
      }
      else
      {
        a1 = (const char *)&qword_180060D60;
        v14 = 1;
      }
      *(_DWORD *)&EventDescriptor.Level = 3;
      UserData.Ptr = *(_QWORD *)(v5 + 8);
      v23 = v14;
      v22 = a1;
      v24 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v19 = (__int16 *)&byte_180071817;
      UserData.Reserved = 2;
      v20 = 43;
      v21 = 1;
      fPending = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      goto LABEL_29;
    }
  }
  else
  {
    Context = 0;
    fPending = 0;
    if ( InitOnceBeginInitialize(&`MBSettingUXLogging::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
    {
      qword_18007EE30 = 0;
      Context = &qword_18007EE28;
      qword_18007EE28 = (__int64)&MBSettingUXLogging::`vftable';
      byte_18007EE38 = 0;
      dword_18007EE3C = 0;
      CallbackContext = &`MBSettingUXLogging::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(`MBSettingUXLogging::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
      qword_18007EE30 = (__int64)CallbackContext;
      byte_18007EE38 = 1;
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
      dword_18007EE3C = 1;
      (*(void (__fastcall **)(__int64 *))(qword_18007EE28 + 8))(&qword_18007EE28);
      InitOnceComplete(&`MBSettingUXLogging::Instance'::`2'::wrapper, 0, &qword_18007EE28);
    }
    v5 = *((_QWORD *)Context + 1);
    if ( *(_DWORD *)v5 > 3u )
    {
      v6 = (const unsigned __int16 *)a3;
      v7 = -1;
      fPending = a2;
      if ( a3 )
      {
        v8 = -1;
        do
          ++v8;
        while ( a3[v8] );
        v9 = v8 + 1;
      }
      else
      {
        v6 = &qword_180060D60;
        v9 = 1;
      }
      v28 = v9;
      p_Context = &fPending;
      v27 = (wchar_t *)v6;
      v29 = 0;
      v26 = 4;
      if ( a1 )
      {
        do
          ++v7;
        while ( a1[v7] );
        v10 = v7 + 1;
      }
      else
      {
        a1 = (const char *)&qword_180060D60;
        v10 = 1;
      }
      *(_DWORD *)&EventDescriptor.Level = 3;
      UserData.Ptr = *(_QWORD *)(v5 + 8);
      v23 = v10;
      v22 = a1;
      v24 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v19 = &word_18007184E;
      UserData.Reserved = 2;
      v20 = 43;
      v21 = 1;
      LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
LABEL_29:
      EventWriteTransfer(*(_QWORD *)(v5 + 32), &EventDescriptor, 0, 0, 5u, &UserData);
    }
  }
}

```

## disassembly

```asm
0x18000bde0  mov     [rsp-8+arg_10], r8
0x18000bde5  mov     qword ptr [rsp-8+Args], r9
0x18000bdea  push    rbp
0x18000bdeb  push    rbx
0x18000bdec  push    rsi
0x18000bded  push    rdi
0x18000bdee  push    r14
0x18000bdf0  lea     rbp, [rsp-0FB0h]
0x18000bdf8  mov     eax, 10B0h
0x18000bdfd  call    _alloca_probe
0x18000be02  sub     rsp, rax
0x18000be05  mov     rax, cs:__security_cookie
0x18000be0c  xor     rax, rsp
0x18000be0f  mov     [rbp+0FD0h+var_30], rax
0x18000be16  xor     r14d, r14d
0x18000be19  lea     rdi, [rbp+0FD0h+Args]
0x18000be20  mov     [rsp+10D0h+Context], r14
0x18000be25  mov     esi, edx
0x18000be27  mov     rbx, rcx
0x18000be2a  test    rdi, rdi
0x18000be2d  jnz     loc_18000C000
0x18000be33  lea     r9, [rsp+10D0h+Context]; lpContext
0x18000be38  mov     [rsp+10D0h+Context], r14
0x18000be3d  lea     r8, [rsp+10D0h+fPending]; fPending
0x18000be42  mov     [rsp+10D0h+fPending], r14d
0x18000be47  xor     edx, edx; dwFlags
0x18000be49  lea     rcx, ?wrapper@?1??Instance@MBSettingUXLogging@@KAPEAV2@XZ@4V?$static_lazy@VMBSettingUXLogging@@@details@wil@@A; lpInitOnce
0x18000be50  call    cs:__imp_InitOnceBeginInitialize
0x18000be56  test    eax, eax
0x18000be58  jz      loc_18000BEFB
0x18000be5e  cmp     [rsp+10D0h+fPending], r14d
0x18000be63  jz      loc_18000BEFB
0x18000be69  lea     rdi, qword_18007EE28
0x18000be70  mov     cs:qword_18007EE30, r14
0x18000be77  lea     rax, ??_7MBSettingUXLogging@@6B@; const MBSettingUXLogging::`vftable'
0x18000be7e  mov     [rsp+10D0h+Context], rdi
0x18000be83  mov     cs:qword_18007EE28, rax
0x18000be8a  mov     cs:byte_18007EE38, r14b
0x18000be91  mov     cs:dword_18007EE3C, r14d
0x18000be98  lea     rax, ?__hInner@?1???0StaticHandle@MBSettingUXLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MBSettingUXLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000be9f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MBSettingUXLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000bea6  mov     cs:CallbackContext, rax
0x18000bead  call    atexit
0x18000beb2  mov     rcx, cs:CallbackContext; CallbackContext
0x18000beb9  mov     cs:qword_18007EE30, rcx
0x18000bec0  mov     cs:byte_18007EE38, 1
0x18000bec7  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000becc  mov     rax, cs:qword_18007EE28
0x18000bed3  mov     rcx, rdi
0x18000bed6  mov     cs:dword_18007EE3C, 1
0x18000bee0  mov     rax, [rax+8]
0x18000bee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee9  mov     r8, rdi; lpContext
0x18000beec  lea     rcx, ?wrapper@?1??Instance@MBSettingUXLogging@@KAPEAV2@XZ@4V?$static_lazy@VMBSettingUXLogging@@@details@wil@@A; lpInitOnce
0x18000bef3  xor     edx, edx; dwFlags
0x18000bef5  call    cs:__imp_InitOnceComplete
0x18000befb  mov     rax, [rsp+10D0h+Context]
0x18000bf00  mov     r10, [rax+8]
0x18000bf04  mov     eax, [r10]
0x18000bf07  cmp     eax, 3
0x18000bf0a  jbe     loc_18000C232
0x18000bf10  mov     rdx, [rbp+0FD0h+arg_10]
0x18000bf17  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000bf1e  mov     [rsp+10D0h+fPending], esi
0x18000bf22  test    rdx, rdx
0x18000bf25  jz      short loc_18000BF3D
0x18000bf27  mov     rax, rcx
0x18000bf2a  nop     word ptr [rax+rax+00h]
0x18000bf30  inc     rax
0x18000bf33  cmp     [rdx+rax], r14b
0x18000bf37  jnz     short loc_18000BF30
0x18000bf39  inc     eax
0x18000bf3b  jmp     short loc_18000BF49
0x18000bf3d  lea     rdx, qword_180060D60
0x18000bf44  mov     eax, 1
0x18000bf49  mov     [rbp+0FD0h+var_1038], eax
0x18000bf4c  lea     rax, [rsp+10D0h+fPending]
0x18000bf51  mov     [rbp+0FD0h+var_1050], rax
0x18000bf55  mov     [rbp+0FD0h+var_1040], rdx
0x18000bf59  mov     [rbp+0FD0h+var_1034], r14d
0x18000bf5d  mov     [rbp+0FD0h+var_1048], 4
0x18000bf65  test    rbx, rbx
0x18000bf68  jz      short loc_18000BF7D
0x18000bf6a  nop     word ptr [rax+rax+00h]
0x18000bf70  inc     rcx
0x18000bf73  cmp     [rbx+rcx], r14b
0x18000bf77  jnz     short loc_18000BF70
0x18000bf79  inc     ecx
0x18000bf7b  jmp     short loc_18000BF89
0x18000bf7d  lea     rbx, qword_180060D60
0x18000bf84  mov     ecx, 1
0x18000bf89  movzx   eax, cs:word_180071844
0x18000bf90  mov     dword ptr [rsp+10D0h+EventDescriptor.Level], eax
0x18000bf94  mov     rax, [r10+8]
0x18000bf98  mov     [rsp+10D0h+var_1080.Ptr], rax
0x18000bf9d  mov     [rsp+10D0h+var_1058], ecx
0x18000bfa1  lea     rcx, _TraceLoggingMetadata
0x18000bfa8  mov     [rsp+10D0h+var_1060], rbx
0x18000bfad  mov     [rsp+10D0h+var_1054], r14d
0x18000bfb2  mov     dword ptr [rsp+10D0h+EventDescriptor.Id], 0B000000h
0x18000bfba  mov     [rsp+10D0h+EventDescriptor.Keyword], r14
0x18000bfbf  movzx   eax, word ptr [rax]
0x18000bfc2  mov     [rsp+10D0h+var_1080.Size], eax
0x18000bfc6  lea     rax, word_18007184E
0x18000bfcd  mov     [rsp+10D0h+var_1070], rax
0x18000bfd2  lea     rax, _TraceLoggingMetadataEnd
0x18000bfd9  sub     eax, ecx
0x18000bfdb  mov     dword ptr [rsp+10D0h+var_1080.0Ch], 2
0x18000bfe3  mov     [rsp+10D0h+var_1068], 2Bh ; '+'
0x18000bfeb  mov     [rsp+10D0h+var_1064], 1
0x18000bff3  mov     dword ptr [rsp+10D0h+Context], eax
0x18000bff7  mov     eax, dword ptr [rsp+10D0h+Context]
0x18000bffb  jmp     loc_18000C20B
0x18000c000  mov     r9, r8
0x18000c003  lea     rcx, [rbp+0FD0h+Format]; unsigned __int16 *
0x18000c007  lea     r8, aHs_0; "%hs"
0x18000c00e  mov     edx, 200h; unsigned __int64
0x18000c013  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c018  mov     r9, rdi; Args
0x18000c01b  lea     r8, [rbp+0FD0h+Format]; Format
0x18000c01f  mov     edx, 5FFh; BufferCount
0x18000c024  lea     rcx, [rbp+0FD0h+Buffer]; Buffer
0x18000c02b  call    _vsnwprintf
0x18000c030  test    eax, eax
0x18000c032  js      short loc_18000C03B
0x18000c034  cmp     eax, 5FFh
0x18000c039  jb      short loc_18000C043
0x18000c03b  mov     [rbp+0FD0h+var_32], r14w
0x18000c043  lea     r9, [rsp+10D0h+Context]; lpContext
0x18000c048  mov     [rsp+10D0h+Context], r14
0x18000c04d  lea     r8, [rsp+10D0h+fPending]; fPending
0x18000c052  mov     [rsp+10D0h+fPending], r14d
0x18000c057  xor     edx, edx; dwFlags
0x18000c059  lea     rcx, ?wrapper@?1??Instance@MBSettingUXLogging@@KAPEAV2@XZ@4V?$static_lazy@VMBSettingUXLogging@@@details@wil@@A; lpInitOnce
0x18000c060  call    cs:__imp_InitOnceBeginInitialize
0x18000c066  test    eax, eax
0x18000c068  jz      loc_18000C10B
0x18000c06e  cmp     [rsp+10D0h+fPending], r14d
0x18000c073  jz      loc_18000C10B
0x18000c079  lea     rdi, qword_18007EE28
0x18000c080  mov     cs:qword_18007EE30, r14
0x18000c087  lea     rax, ??_7MBSettingUXLogging@@6B@; const MBSettingUXLogging::`vftable'
0x18000c08e  mov     [rsp+10D0h+Context], rdi
0x18000c093  mov     cs:qword_18007EE28, rax
0x18000c09a  mov     cs:byte_18007EE38, r14b
0x18000c0a1  mov     cs:dword_18007EE3C, r14d
0x18000c0a8  lea     rax, ?__hInner@?1???0StaticHandle@MBSettingUXLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MBSettingUXLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000c0af  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MBSettingUXLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000c0b6  mov     cs:CallbackContext, rax
0x18000c0bd  call    atexit
0x18000c0c2  mov     rcx, cs:CallbackContext; CallbackContext
0x18000c0c9  mov     cs:qword_18007EE30, rcx
0x18000c0d0  mov     cs:byte_18007EE38, 1
0x18000c0d7  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000c0dc  mov     rax, cs:qword_18007EE28
0x18000c0e3  mov     rcx, rdi
0x18000c0e6  mov     cs:dword_18007EE3C, 1
0x18000c0f0  mov     rax, [rax+8]
0x18000c0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0f9  mov     r8, rdi; lpContext
0x18000c0fc  lea     rcx, ?wrapper@?1??Instance@MBSettingUXLogging@@KAPEAV2@XZ@4V?$static_lazy@VMBSettingUXLogging@@@details@wil@@A; lpInitOnce
0x18000c103  xor     edx, edx; dwFlags
0x18000c105  call    cs:__imp_InitOnceComplete
0x18000c10b  mov     rax, [rsp+10D0h+Context]
0x18000c110  mov     r10, [rax+8]
0x18000c114  mov     eax, [r10]
0x18000c117  cmp     eax, 3
0x18000c11a  jbe     loc_18000C232
0x18000c120  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c127  mov     dword ptr [rsp+10D0h+Context], esi
0x18000c12b  mov     rax, rcx
0x18000c12e  lea     rdx, [rbp+0FD0h+Buffer]
0x18000c135  nop     word ptr [rax+rax+00000000h]
0x18000c140  cmp     [rdx+rax*2+2], r14w
0x18000c146  lea     rax, [rax+1]
0x18000c14a  jnz     short loc_18000C140
0x18000c14c  mov     [rbp+0FD0h+var_1034], r14d
0x18000c150  lea     eax, ds:2[rax*2]
0x18000c157  mov     [rbp+0FD0h+var_1038], eax
0x18000c15a  lea     rax, [rsp+10D0h+Context]
0x18000c15f  mov     [rbp+0FD0h+var_1050], rax
0x18000c163  lea     rdx, [rbp+0FD0h+Buffer]
0x18000c16a  mov     [rbp+0FD0h+var_1040], rdx
0x18000c16e  mov     [rbp+0FD0h+var_1048], 4
0x18000c176  test    rbx, rbx
0x18000c179  jz      short loc_18000C18D
0x18000c17b  nop     dword ptr [rax+rax+00h]
0x18000c180  inc     rcx
0x18000c183  cmp     [rbx+rcx], r14b
0x18000c187  jnz     short loc_18000C180
0x18000c189  inc     ecx
0x18000c18b  jmp     short loc_18000C199
0x18000c18d  lea     rbx, qword_180060D60
0x18000c194  mov     ecx, 1
0x18000c199  movzx   eax, cs:word_18007180D
0x18000c1a0  mov     dword ptr [rsp+10D0h+EventDescriptor.Level], eax
0x18000c1a4  mov     rax, [r10+8]
0x18000c1a8  mov     [rsp+10D0h+var_1080.Ptr], rax
0x18000c1ad  mov     [rsp+10D0h+var_1058], ecx
0x18000c1b1  lea     rcx, _TraceLoggingMetadata
0x18000c1b8  mov     [rsp+10D0h+var_1060], rbx
0x18000c1bd  mov     [rsp+10D0h+var_1054], r14d
0x18000c1c2  mov     dword ptr [rsp+10D0h+EventDescriptor.Id], 0B000000h
0x18000c1ca  mov     [rsp+10D0h+EventDescriptor.Keyword], r14
0x18000c1cf  movzx   eax, word ptr [rax]
0x18000c1d2  mov     [rsp+10D0h+var_1080.Size], eax
0x18000c1d6  lea     rax, byte_180071817
0x18000c1dd  mov     [rsp+10D0h+var_1070], rax
0x18000c1e2  lea     rax, _TraceLoggingMetadataEnd
0x18000c1e9  sub     eax, ecx
0x18000c1eb  mov     dword ptr [rsp+10D0h+var_1080.0Ch], 2
0x18000c1f3  mov     [rsp+10D0h+var_1068], 2Bh ; '+'
0x18000c1fb  mov     [rsp+10D0h+var_1064], 1
0x18000c203  mov     [rsp+10D0h+fPending], eax
0x18000c207  mov     eax, [rsp+10D0h+fPending]
0x18000c20b  mov     rcx, [r10+20h]; RegHandle
0x18000c20f  lea     rax, [rsp+10D0h+var_1080]
0x18000c214  mov     [rsp+10D0h+UserData], rax; UserData
0x18000c219  lea     rdx, [rsp+10D0h+EventDescriptor]; EventDescriptor
0x18000c21e  xor     r9d, r9d; RelatedActivityId
0x18000c221  mov     [rsp+10D0h+UserDataCount], 5; UserDataCount
0x18000c229  xor     r8d, r8d; ActivityId
0x18000c22c  call    cs:__imp_EventWriteTransfer
0x18000c232  mov     rcx, [rbp+0FD0h+var_30]
0x18000c239  xor     rcx, rsp; StackCookie
0x18000c23c  call    __security_check_cookie
0x18000c241  add     rsp, 10B0h
0x18000c248  pop     r14
0x18000c24a  pop     rdi
0x18000c24b  pop     rsi
0x18000c24c  pop     rbx
0x18000c24d  pop     rbp
0x18000c24e  retn
```
