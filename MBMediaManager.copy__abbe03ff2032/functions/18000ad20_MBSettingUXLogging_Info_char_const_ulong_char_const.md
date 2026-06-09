# MBSettingUXLogging::Info(char const *,ulong,char const *,...)

- ea: `0x18000ad20`
- end: `0x18000b18f`
- name: `?Info@MBSettingUXLogging@@SAXPEBDK0ZZ`
- size: `1135`
- prototype: `void(const char *, unsigned int, const char *, ...)`
- caller_count: `177`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180003e48`
- `0x180005d3c`
- `0x1800069f8`
- `0x1800075a8`
- `0x1800079a0`
- `0x180007aac`
- `0x18000853c`
- `0x180008880`
- `0x180008da0`
- `0x180008f00`
- `0x180009290`
- `0x180009c10`
- `0x180009f08`
- `0x180009f60`
- `0x18000a460`
- `0x18000b500`
- `0x18000c50c`
- `0x18000c890`
- `0x18000da00`
- `0x18000dea0`
- `0x18000e538`
- `0x18000ead4`
- `0x18000ef40`
- `0x180011450`
- `0x180014490`
- `0x1800158dc`
- `0x1800160e4`
- `0x180017280`
- `0x18001803c`
- `0x180018304`
- `0x1800189c4`
- `0x180019940`
- `0x180019e2c`
- `0x18001a1ec`
- `0x18001a494`
- `0x18001a864`
- `0x18001a9e0`
- `0x18001ac24`
- `0x18001accc`
- `0x18001addc`
- `0x18001b458`
- `0x18001bb28`
- `0x18001c0cc`
- `0x18001d3d0`
- `0x18001d450`
- `0x18001dc70`
- `0x18001f0dc`
- `0x18001f600`
- `0x18001f7ec`
- `0x1800205e8`

## callees

- `0x18000ad20`
- `0x180010250`
- `0x180010b94`
- `0x18002cd20`
- `0x18002d1ac`
- `0x18002d8e0`
- `0x180055dd0`
- `0x180059010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b16c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b16c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ad90`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000afa0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ad90`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000afa0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000ae35`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000b045`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000ae35`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000b045`

## pseudocode

```c
void MBSettingUXLogging::Info(const char *a1, WINBOOL a2, const char *a3, ...)
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
  __int64 *v19; // [rsp+60h] [rbp-A0h]
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
    if ( *(_DWORD *)v5 > 4u )
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
      *(_DWORD *)&EventDescriptor.Level = 4;
      UserData.Ptr = *(_QWORD *)(v5 + 8);
      v23 = v14;
      v22 = a1;
      v24 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v19 = (__int64 *)byte_1800717A9;
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
    if ( *(_DWORD *)v5 > 4u )
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
      *(_DWORD *)&EventDescriptor.Level = 4;
      UserData.Ptr = *(_QWORD *)(v5 + 8);
      v23 = v10;
      v22 = a1;
      v24 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v19 = qword_1800717E0;
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
0x18000ad20  mov     [rsp-8+arg_10], r8
0x18000ad25  mov     qword ptr [rsp-8+Args], r9
0x18000ad2a  push    rbp
0x18000ad2b  push    rbx
0x18000ad2c  push    rsi
0x18000ad2d  push    rdi
0x18000ad2e  push    r14
0x18000ad30  lea     rbp, [rsp-0FB0h]
0x18000ad38  mov     eax, 10B0h
0x18000ad3d  call    _alloca_probe
0x18000ad42  sub     rsp, rax
0x18000ad45  mov     rax, cs:__security_cookie
0x18000ad4c  xor     rax, rsp
0x18000ad4f  mov     [rbp+0FD0h+var_30], rax
0x18000ad56  xor     r14d, r14d
0x18000ad59  lea     rdi, [rbp+0FD0h+Args]
0x18000ad60  mov     [rsp+10D0h+Context], r14
0x18000ad65  mov     esi, edx
0x18000ad67  mov     rbx, rcx
0x18000ad6a  test    rdi, rdi
0x18000ad6d  jnz     loc_18000AF40
0x18000ad73  lea     r9, [rsp+10D0h+Context]; lpContext
0x18000ad78  mov     [rsp+10D0h+Context], r14
0x18000ad7d  lea     r8, [rsp+10D0h+fPending]; fPending
0x18000ad82  mov     [rsp+10D0h+fPending], r14d
0x18000ad87  xor     edx, edx; dwFlags
0x18000ad89  lea     rcx, ?wrapper@?1??Instance@MBSettingUXLogging@@KAPEAV2@XZ@4V?$static_lazy@VMBSettingUXLogging@@@details@wil@@A; lpInitOnce
0x18000ad90  call    cs:__imp_InitOnceBeginInitialize
0x18000ad96  test    eax, eax
0x18000ad98  jz      loc_18000AE3B
0x18000ad9e  cmp     [rsp+10D0h+fPending], r14d
0x18000ada3  jz      loc_18000AE3B
0x18000ada9  lea     rdi, qword_18007EE28
0x18000adb0  mov     cs:qword_18007EE30, r14
0x18000adb7  lea     rax, ??_7MBSettingUXLogging@@6B@; const MBSettingUXLogging::`vftable'
0x18000adbe  mov     [rsp+10D0h+Context], rdi
0x18000adc3  mov     cs:qword_18007EE28, rax
0x18000adca  mov     cs:byte_18007EE38, r14b
0x18000add1  mov     cs:dword_18007EE3C, r14d
0x18000add8  lea     rax, ?__hInner@?1???0StaticHandle@MBSettingUXLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MBSettingUXLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000addf  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MBSettingUXLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000ade6  mov     cs:CallbackContext, rax
0x18000aded  call    atexit
0x18000adf2  mov     rcx, cs:CallbackContext; CallbackContext
0x18000adf9  mov     cs:qword_18007EE30, rcx
0x18000ae00  mov     cs:byte_18007EE38, 1
0x18000ae07  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000ae0c  mov     rax, cs:qword_18007EE28
0x18000ae13  mov     rcx, rdi
0x18000ae16  mov     cs:dword_18007EE3C, 1
0x18000ae20  mov     rax, [rax+8]
0x18000ae24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae29  mov     r8, rdi; lpContext
0x18000ae2c  lea     rcx, ?wrapper@?1??Instance@MBSettingUXLogging@@KAPEAV2@XZ@4V?$static_lazy@VMBSettingUXLogging@@@details@wil@@A; lpInitOnce
0x18000ae33  xor     edx, edx; dwFlags
0x18000ae35  call    cs:__imp_InitOnceComplete
0x18000ae3b  mov     rax, [rsp+10D0h+Context]
0x18000ae40  mov     r10, [rax+8]
0x18000ae44  mov     eax, [r10]
0x18000ae47  cmp     eax, 4
0x18000ae4a  jbe     loc_18000B172
0x18000ae50  mov     rdx, [rbp+0FD0h+arg_10]
0x18000ae57  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ae5e  mov     [rsp+10D0h+fPending], esi
0x18000ae62  test    rdx, rdx
0x18000ae65  jz      short loc_18000AE7D
0x18000ae67  mov     rax, rcx
0x18000ae6a  nop     word ptr [rax+rax+00h]
0x18000ae70  inc     rax
0x18000ae73  cmp     [rdx+rax], r14b
0x18000ae77  jnz     short loc_18000AE70
0x18000ae79  inc     eax
0x18000ae7b  jmp     short loc_18000AE89
0x18000ae7d  lea     rdx, qword_180060D60
0x18000ae84  mov     eax, 1
0x18000ae89  mov     [rbp+0FD0h+var_1038], eax
0x18000ae8c  lea     rax, [rsp+10D0h+fPending]
0x18000ae91  mov     [rbp+0FD0h+var_1050], rax
0x18000ae95  mov     [rbp+0FD0h+var_1040], rdx
0x18000ae99  mov     [rbp+0FD0h+var_1034], r14d
0x18000ae9d  mov     [rbp+0FD0h+var_1048], 4
0x18000aea5  test    rbx, rbx
0x18000aea8  jz      short loc_18000AEBD
0x18000aeaa  nop     word ptr [rax+rax+00h]
0x18000aeb0  inc     rcx
0x18000aeb3  cmp     [rbx+rcx], r14b
0x18000aeb7  jnz     short loc_18000AEB0
0x18000aeb9  inc     ecx
0x18000aebb  jmp     short loc_18000AEC9
0x18000aebd  lea     rbx, qword_180060D60
0x18000aec4  mov     ecx, 1
0x18000aec9  movzx   eax, cs:word_1800717D6
0x18000aed0  mov     dword ptr [rsp+10D0h+EventDescriptor.Level], eax
0x18000aed4  mov     rax, [r10+8]
0x18000aed8  mov     [rsp+10D0h+var_1080.Ptr], rax
0x18000aedd  mov     [rsp+10D0h+var_1058], ecx
0x18000aee1  lea     rcx, _TraceLoggingMetadata
0x18000aee8  mov     [rsp+10D0h+var_1060], rbx
0x18000aeed  mov     [rsp+10D0h+var_1054], r14d
0x18000aef2  mov     dword ptr [rsp+10D0h+EventDescriptor.Id], 0B000000h
0x18000aefa  mov     [rsp+10D0h+EventDescriptor.Keyword], r14
0x18000aeff  movzx   eax, word ptr [rax]
0x18000af02  mov     [rsp+10D0h+var_1080.Size], eax
0x18000af06  lea     rax, qword_1800717E0
0x18000af0d  mov     [rsp+10D0h+var_1070], rax
0x18000af12  lea     rax, _TraceLoggingMetadataEnd
0x18000af19  sub     eax, ecx
0x18000af1b  mov     dword ptr [rsp+10D0h+var_1080.0Ch], 2
0x18000af23  mov     [rsp+10D0h+var_1068], 2Bh ; '+'
0x18000af2b  mov     [rsp+10D0h+var_1064], 1
0x18000af33  mov     dword ptr [rsp+10D0h+Context], eax
0x18000af37  mov     eax, dword ptr [rsp+10D0h+Context]
0x18000af3b  jmp     loc_18000B14B
0x18000af40  mov     r9, r8
0x18000af43  lea     rcx, [rbp+0FD0h+Format]; unsigned __int16 *
0x18000af47  lea     r8, aHs_0; "%hs"
0x18000af4e  mov     edx, 200h; unsigned __int64
0x18000af53  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000af58  mov     r9, rdi; Args
0x18000af5b  lea     r8, [rbp+0FD0h+Format]; Format
0x18000af5f  mov     edx, 5FFh; BufferCount
0x18000af64  lea     rcx, [rbp+0FD0h+Buffer]; Buffer
0x18000af6b  call    _vsnwprintf
0x18000af70  test    eax, eax
0x18000af72  js      short loc_18000AF7B
0x18000af74  cmp     eax, 5FFh
0x18000af79  jb      short loc_18000AF83
0x18000af7b  mov     [rbp+0FD0h+var_32], r14w
0x18000af83  lea     r9, [rsp+10D0h+Context]; lpContext
0x18000af88  mov     [rsp+10D0h+Context], r14
0x18000af8d  lea     r8, [rsp+10D0h+fPending]; fPending
0x18000af92  mov     [rsp+10D0h+fPending], r14d
0x18000af97  xor     edx, edx; dwFlags
0x18000af99  lea     rcx, ?wrapper@?1??Instance@MBSettingUXLogging@@KAPEAV2@XZ@4V?$static_lazy@VMBSettingUXLogging@@@details@wil@@A; lpInitOnce
0x18000afa0  call    cs:__imp_InitOnceBeginInitialize
0x18000afa6  test    eax, eax
0x18000afa8  jz      loc_18000B04B
0x18000afae  cmp     [rsp+10D0h+fPending], r14d
0x18000afb3  jz      loc_18000B04B
0x18000afb9  lea     rdi, qword_18007EE28
0x18000afc0  mov     cs:qword_18007EE30, r14
0x18000afc7  lea     rax, ??_7MBSettingUXLogging@@6B@; const MBSettingUXLogging::`vftable'
0x18000afce  mov     [rsp+10D0h+Context], rdi
0x18000afd3  mov     cs:qword_18007EE28, rax
0x18000afda  mov     cs:byte_18007EE38, r14b
0x18000afe1  mov     cs:dword_18007EE3C, r14d
0x18000afe8  lea     rax, ?__hInner@?1???0StaticHandle@MBSettingUXLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MBSettingUXLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000afef  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MBSettingUXLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000aff6  mov     cs:CallbackContext, rax
0x18000affd  call    atexit
0x18000b002  mov     rcx, cs:CallbackContext; CallbackContext
0x18000b009  mov     cs:qword_18007EE30, rcx
0x18000b010  mov     cs:byte_18007EE38, 1
0x18000b017  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000b01c  mov     rax, cs:qword_18007EE28
0x18000b023  mov     rcx, rdi
0x18000b026  mov     cs:dword_18007EE3C, 1
0x18000b030  mov     rax, [rax+8]
0x18000b034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b039  mov     r8, rdi; lpContext
0x18000b03c  lea     rcx, ?wrapper@?1??Instance@MBSettingUXLogging@@KAPEAV2@XZ@4V?$static_lazy@VMBSettingUXLogging@@@details@wil@@A; lpInitOnce
0x18000b043  xor     edx, edx; dwFlags
0x18000b045  call    cs:__imp_InitOnceComplete
0x18000b04b  mov     rax, [rsp+10D0h+Context]
0x18000b050  mov     r10, [rax+8]
0x18000b054  mov     eax, [r10]
0x18000b057  cmp     eax, 4
0x18000b05a  jbe     loc_18000B172
0x18000b060  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b067  mov     dword ptr [rsp+10D0h+Context], esi
0x18000b06b  mov     rax, rcx
0x18000b06e  lea     rdx, [rbp+0FD0h+Buffer]
0x18000b075  nop     word ptr [rax+rax+00000000h]
0x18000b080  cmp     [rdx+rax*2+2], r14w
0x18000b086  lea     rax, [rax+1]
0x18000b08a  jnz     short loc_18000B080
0x18000b08c  mov     [rbp+0FD0h+var_1034], r14d
0x18000b090  lea     eax, ds:2[rax*2]
0x18000b097  mov     [rbp+0FD0h+var_1038], eax
0x18000b09a  lea     rax, [rsp+10D0h+Context]
0x18000b09f  mov     [rbp+0FD0h+var_1050], rax
0x18000b0a3  lea     rdx, [rbp+0FD0h+Buffer]
0x18000b0aa  mov     [rbp+0FD0h+var_1040], rdx
0x18000b0ae  mov     [rbp+0FD0h+var_1048], 4
0x18000b0b6  test    rbx, rbx
0x18000b0b9  jz      short loc_18000B0CD
0x18000b0bb  nop     dword ptr [rax+rax+00h]
0x18000b0c0  inc     rcx
0x18000b0c3  cmp     [rbx+rcx], r14b
0x18000b0c7  jnz     short loc_18000B0C0
0x18000b0c9  inc     ecx
0x18000b0cb  jmp     short loc_18000B0D9
0x18000b0cd  lea     rbx, qword_180060D60
0x18000b0d4  mov     ecx, 1
0x18000b0d9  movzx   eax, cs:word_18007179F
0x18000b0e0  mov     dword ptr [rsp+10D0h+EventDescriptor.Level], eax
0x18000b0e4  mov     rax, [r10+8]
0x18000b0e8  mov     [rsp+10D0h+var_1080.Ptr], rax
0x18000b0ed  mov     [rsp+10D0h+var_1058], ecx
0x18000b0f1  lea     rcx, _TraceLoggingMetadata
0x18000b0f8  mov     [rsp+10D0h+var_1060], rbx
0x18000b0fd  mov     [rsp+10D0h+var_1054], r14d
0x18000b102  mov     dword ptr [rsp+10D0h+EventDescriptor.Id], 0B000000h
0x18000b10a  mov     [rsp+10D0h+EventDescriptor.Keyword], r14
0x18000b10f  movzx   eax, word ptr [rax]
0x18000b112  mov     [rsp+10D0h+var_1080.Size], eax
0x18000b116  lea     rax, byte_1800717A9
0x18000b11d  mov     [rsp+10D0h+var_1070], rax
0x18000b122  lea     rax, _TraceLoggingMetadataEnd
0x18000b129  sub     eax, ecx
0x18000b12b  mov     dword ptr [rsp+10D0h+var_1080.0Ch], 2
0x18000b133  mov     [rsp+10D0h+var_1068], 2Bh ; '+'
0x18000b13b  mov     [rsp+10D0h+var_1064], 1
0x18000b143  mov     [rsp+10D0h+fPending], eax
0x18000b147  mov     eax, [rsp+10D0h+fPending]
0x18000b14b  mov     rcx, [r10+20h]; RegHandle
0x18000b14f  lea     rax, [rsp+10D0h+var_1080]
0x18000b154  mov     [rsp+10D0h+UserData], rax; UserData
0x18000b159  lea     rdx, [rsp+10D0h+EventDescriptor]; EventDescriptor
0x18000b15e  xor     r9d, r9d; RelatedActivityId
0x18000b161  mov     [rsp+10D0h+UserDataCount], 5; UserDataCount
0x18000b169  xor     r8d, r8d; ActivityId
0x18000b16c  call    cs:__imp_EventWriteTransfer
0x18000b172  mov     rcx, [rbp+0FD0h+var_30]
0x18000b179  xor     rcx, rsp; StackCookie
0x18000b17c  call    __security_check_cookie
0x18000b181  add     rsp, 10B0h
0x18000b188  pop     r14
0x18000b18a  pop     rdi
0x18000b18b  pop     rsi
0x18000b18c  pop     rbx
0x18000b18d  pop     rbp
0x18000b18e  retn
```
