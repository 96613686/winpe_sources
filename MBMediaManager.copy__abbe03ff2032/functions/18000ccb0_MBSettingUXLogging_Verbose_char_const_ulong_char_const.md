# MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)

- ea: `0x18000ccb0`
- end: `0x18000d11f`
- name: `?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ`
- size: `1135`
- prototype: `void(const char *, unsigned int, const char *, ...)`
- caller_count: `161`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180009d30`
- `0x18000c260`
- `0x18000c420`
- `0x18000c50c`
- `0x18000c6ac`
- `0x18000c724`
- `0x18000c7c0`
- `0x18000c890`
- `0x18000cc50`
- `0x18000d130`
- `0x18000d390`
- `0x18000d5d0`
- `0x18000d8d0`
- `0x18000dc54`
- `0x18000dea0`
- `0x18000e02c`
- `0x18000e180`
- `0x18000e26c`
- `0x18000e3e8`
- `0x18000e538`
- `0x18000ea3c`
- `0x18000ecbc`
- `0x18000ed60`
- `0x18000ee50`
- `0x18000f5e0`
- `0x1800187e4`
- `0x1800189c4`
- `0x1800191f0`
- `0x18001a048`
- `0x18001a14c`
- `0x18001a494`
- `0x18001a6e8`
- `0x18001a9e0`
- `0x18001aeec`
- `0x18001baa0`
- `0x18001bb28`
- `0x18001bfa8`
- `0x18001c0cc`
- `0x18001c268`
- `0x18002381c`
- `0x180023b84`
- `0x1800242fc`
- `0x1800244b0`
- `0x180026b34`
- `0x180026c60`
- `0x180026df0`
- `0x180027f20`
- `0x180028384`
- `0x18002a970`
- `0x18002ade0`

## callees

- `0x18000ccb0`
- `0x180010250`
- `0x180010b94`
- `0x18002cd20`
- `0x18002d1ac`
- `0x18002d8e0`
- `0x180055dd0`
- `0x180059010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d0fc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d0fc`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000cd20`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000cf30`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000cd20`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000cf30`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cdc5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cfd5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cdc5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cfd5`

## pseudocode

```c
void MBSettingUXLogging::Verbose(const char *a1, WINBOOL a2, const char *a3, ...)
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
  char *v19; // [rsp+60h] [rbp-A0h]
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
    if ( *(_DWORD *)v5 > 5u )
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
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = *(_QWORD *)(v5 + 8);
      v23 = v14;
      v22 = a1;
      v24 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v19 = byte_180071735;
      UserData.Reserved = 2;
      v20 = 46;
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
    if ( *(_DWORD *)v5 > 5u )
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
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = *(_QWORD *)(v5 + 8);
      v23 = v10;
      v22 = a1;
      v24 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v19 = &byte_18007176F;
      UserData.Reserved = 2;
      v20 = 46;
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
0x18000ccb0  mov     [rsp-8+arg_10], r8
0x18000ccb5  mov     qword ptr [rsp-8+Args], r9
0x18000ccba  push    rbp
0x18000ccbb  push    rbx
0x18000ccbc  push    rsi
0x18000ccbd  push    rdi
0x18000ccbe  push    r14
0x18000ccc0  lea     rbp, [rsp-0FB0h]
0x18000ccc8  mov     eax, 10B0h
0x18000cccd  call    _alloca_probe
0x18000ccd2  sub     rsp, rax
0x18000ccd5  mov     rax, cs:__security_cookie
0x18000ccdc  xor     rax, rsp
0x18000ccdf  mov     [rbp+0FD0h+var_30], rax
0x18000cce6  xor     r14d, r14d
0x18000cce9  lea     rdi, [rbp+0FD0h+Args]
0x18000ccf0  mov     [rsp+10D0h+Context], r14
0x18000ccf5  mov     esi, edx
0x18000ccf7  mov     rbx, rcx
0x18000ccfa  test    rdi, rdi
0x18000ccfd  jnz     loc_18000CED0
0x18000cd03  lea     r9, [rsp+10D0h+Context]; lpContext
0x18000cd08  mov     [rsp+10D0h+Context], r14
0x18000cd0d  lea     r8, [rsp+10D0h+fPending]; fPending
0x18000cd12  mov     [rsp+10D0h+fPending], r14d
0x18000cd17  xor     edx, edx; dwFlags
0x18000cd19  lea     rcx, ?wrapper@?1??Instance@MBSettingUXLogging@@KAPEAV2@XZ@4V?$static_lazy@VMBSettingUXLogging@@@details@wil@@A; lpInitOnce
0x18000cd20  call    cs:__imp_InitOnceBeginInitialize
0x18000cd26  test    eax, eax
0x18000cd28  jz      loc_18000CDCB
0x18000cd2e  cmp     [rsp+10D0h+fPending], r14d
0x18000cd33  jz      loc_18000CDCB
0x18000cd39  lea     rdi, qword_18007EE28
0x18000cd40  mov     cs:qword_18007EE30, r14
0x18000cd47  lea     rax, ??_7MBSettingUXLogging@@6B@; const MBSettingUXLogging::`vftable'
0x18000cd4e  mov     [rsp+10D0h+Context], rdi
0x18000cd53  mov     cs:qword_18007EE28, rax
0x18000cd5a  mov     cs:byte_18007EE38, r14b
0x18000cd61  mov     cs:dword_18007EE3C, r14d
0x18000cd68  lea     rax, ?__hInner@?1???0StaticHandle@MBSettingUXLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MBSettingUXLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000cd6f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MBSettingUXLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000cd76  mov     cs:CallbackContext, rax
0x18000cd7d  call    atexit
0x18000cd82  mov     rcx, cs:CallbackContext; CallbackContext
0x18000cd89  mov     cs:qword_18007EE30, rcx
0x18000cd90  mov     cs:byte_18007EE38, 1
0x18000cd97  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000cd9c  mov     rax, cs:qword_18007EE28
0x18000cda3  mov     rcx, rdi
0x18000cda6  mov     cs:dword_18007EE3C, 1
0x18000cdb0  mov     rax, [rax+8]
0x18000cdb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdb9  mov     r8, rdi; lpContext
0x18000cdbc  lea     rcx, ?wrapper@?1??Instance@MBSettingUXLogging@@KAPEAV2@XZ@4V?$static_lazy@VMBSettingUXLogging@@@details@wil@@A; lpInitOnce
0x18000cdc3  xor     edx, edx; dwFlags
0x18000cdc5  call    cs:__imp_InitOnceComplete
0x18000cdcb  mov     rax, [rsp+10D0h+Context]
0x18000cdd0  mov     r10, [rax+8]
0x18000cdd4  mov     eax, [r10]
0x18000cdd7  cmp     eax, 5
0x18000cdda  jbe     loc_18000D102
0x18000cde0  mov     rdx, [rbp+0FD0h+arg_10]
0x18000cde7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000cdee  mov     [rsp+10D0h+fPending], esi
0x18000cdf2  test    rdx, rdx
0x18000cdf5  jz      short loc_18000CE0D
0x18000cdf7  mov     rax, rcx
0x18000cdfa  nop     word ptr [rax+rax+00h]
0x18000ce00  inc     rax
0x18000ce03  cmp     [rdx+rax], r14b
0x18000ce07  jnz     short loc_18000CE00
0x18000ce09  inc     eax
0x18000ce0b  jmp     short loc_18000CE19
0x18000ce0d  lea     rdx, qword_180060D60
0x18000ce14  mov     eax, 1
0x18000ce19  mov     [rbp+0FD0h+var_1038], eax
0x18000ce1c  lea     rax, [rsp+10D0h+fPending]
0x18000ce21  mov     [rbp+0FD0h+var_1050], rax
0x18000ce25  mov     [rbp+0FD0h+var_1040], rdx
0x18000ce29  mov     [rbp+0FD0h+var_1034], r14d
0x18000ce2d  mov     [rbp+0FD0h+var_1048], 4
0x18000ce35  test    rbx, rbx
0x18000ce38  jz      short loc_18000CE4D
0x18000ce3a  nop     word ptr [rax+rax+00h]
0x18000ce40  inc     rcx
0x18000ce43  cmp     [rbx+rcx], r14b
0x18000ce47  jnz     short loc_18000CE40
0x18000ce49  inc     ecx
0x18000ce4b  jmp     short loc_18000CE59
0x18000ce4d  lea     rbx, qword_180060D60
0x18000ce54  mov     ecx, 1
0x18000ce59  movzx   eax, cs:word_180071765
0x18000ce60  mov     dword ptr [rsp+10D0h+EventDescriptor.Level], eax
0x18000ce64  mov     rax, [r10+8]
0x18000ce68  mov     [rsp+10D0h+var_1080.Ptr], rax
0x18000ce6d  mov     [rsp+10D0h+var_1058], ecx
0x18000ce71  lea     rcx, _TraceLoggingMetadata
0x18000ce78  mov     [rsp+10D0h+var_1060], rbx
0x18000ce7d  mov     [rsp+10D0h+var_1054], r14d
0x18000ce82  mov     dword ptr [rsp+10D0h+EventDescriptor.Id], 0B000000h
0x18000ce8a  mov     [rsp+10D0h+EventDescriptor.Keyword], r14
0x18000ce8f  movzx   eax, word ptr [rax]
0x18000ce92  mov     [rsp+10D0h+var_1080.Size], eax
0x18000ce96  lea     rax, byte_18007176F
0x18000ce9d  mov     [rsp+10D0h+var_1070], rax
0x18000cea2  lea     rax, _TraceLoggingMetadataEnd
0x18000cea9  sub     eax, ecx
0x18000ceab  mov     dword ptr [rsp+10D0h+var_1080.0Ch], 2
0x18000ceb3  mov     [rsp+10D0h+var_1068], 2Eh ; '.'
0x18000cebb  mov     [rsp+10D0h+var_1064], 1
0x18000cec3  mov     dword ptr [rsp+10D0h+Context], eax
0x18000cec7  mov     eax, dword ptr [rsp+10D0h+Context]
0x18000cecb  jmp     loc_18000D0DB
0x18000ced0  mov     r9, r8
0x18000ced3  lea     rcx, [rbp+0FD0h+Format]; unsigned __int16 *
0x18000ced7  lea     r8, aHs_0; "%hs"
0x18000cede  mov     edx, 200h; unsigned __int64
0x18000cee3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cee8  mov     r9, rdi; Args
0x18000ceeb  lea     r8, [rbp+0FD0h+Format]; Format
0x18000ceef  mov     edx, 5FFh; BufferCount
0x18000cef4  lea     rcx, [rbp+0FD0h+Buffer]; Buffer
0x18000cefb  call    _vsnwprintf
0x18000cf00  test    eax, eax
0x18000cf02  js      short loc_18000CF0B
0x18000cf04  cmp     eax, 5FFh
0x18000cf09  jb      short loc_18000CF13
0x18000cf0b  mov     [rbp+0FD0h+var_32], r14w
0x18000cf13  lea     r9, [rsp+10D0h+Context]; lpContext
0x18000cf18  mov     [rsp+10D0h+Context], r14
0x18000cf1d  lea     r8, [rsp+10D0h+fPending]; fPending
0x18000cf22  mov     [rsp+10D0h+fPending], r14d
0x18000cf27  xor     edx, edx; dwFlags
0x18000cf29  lea     rcx, ?wrapper@?1??Instance@MBSettingUXLogging@@KAPEAV2@XZ@4V?$static_lazy@VMBSettingUXLogging@@@details@wil@@A; lpInitOnce
0x18000cf30  call    cs:__imp_InitOnceBeginInitialize
0x18000cf36  test    eax, eax
0x18000cf38  jz      loc_18000CFDB
0x18000cf3e  cmp     [rsp+10D0h+fPending], r14d
0x18000cf43  jz      loc_18000CFDB
0x18000cf49  lea     rdi, qword_18007EE28
0x18000cf50  mov     cs:qword_18007EE30, r14
0x18000cf57  lea     rax, ??_7MBSettingUXLogging@@6B@; const MBSettingUXLogging::`vftable'
0x18000cf5e  mov     [rsp+10D0h+Context], rdi
0x18000cf63  mov     cs:qword_18007EE28, rax
0x18000cf6a  mov     cs:byte_18007EE38, r14b
0x18000cf71  mov     cs:dword_18007EE3C, r14d
0x18000cf78  lea     rax, ?__hInner@?1???0StaticHandle@MBSettingUXLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MBSettingUXLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000cf7f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MBSettingUXLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000cf86  mov     cs:CallbackContext, rax
0x18000cf8d  call    atexit
0x18000cf92  mov     rcx, cs:CallbackContext; CallbackContext
0x18000cf99  mov     cs:qword_18007EE30, rcx
0x18000cfa0  mov     cs:byte_18007EE38, 1
0x18000cfa7  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000cfac  mov     rax, cs:qword_18007EE28
0x18000cfb3  mov     rcx, rdi
0x18000cfb6  mov     cs:dword_18007EE3C, 1
0x18000cfc0  mov     rax, [rax+8]
0x18000cfc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfc9  mov     r8, rdi; lpContext
0x18000cfcc  lea     rcx, ?wrapper@?1??Instance@MBSettingUXLogging@@KAPEAV2@XZ@4V?$static_lazy@VMBSettingUXLogging@@@details@wil@@A; lpInitOnce
0x18000cfd3  xor     edx, edx; dwFlags
0x18000cfd5  call    cs:__imp_InitOnceComplete
0x18000cfdb  mov     rax, [rsp+10D0h+Context]
0x18000cfe0  mov     r10, [rax+8]
0x18000cfe4  mov     eax, [r10]
0x18000cfe7  cmp     eax, 5
0x18000cfea  jbe     loc_18000D102
0x18000cff0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000cff7  mov     dword ptr [rsp+10D0h+Context], esi
0x18000cffb  mov     rax, rcx
0x18000cffe  lea     rdx, [rbp+0FD0h+Buffer]
0x18000d005  nop     word ptr [rax+rax+00000000h]
0x18000d010  cmp     [rdx+rax*2+2], r14w
0x18000d016  lea     rax, [rax+1]
0x18000d01a  jnz     short loc_18000D010
0x18000d01c  mov     [rbp+0FD0h+var_1034], r14d
0x18000d020  lea     eax, ds:2[rax*2]
0x18000d027  mov     [rbp+0FD0h+var_1038], eax
0x18000d02a  lea     rax, [rsp+10D0h+Context]
0x18000d02f  mov     [rbp+0FD0h+var_1050], rax
0x18000d033  lea     rdx, [rbp+0FD0h+Buffer]
0x18000d03a  mov     [rbp+0FD0h+var_1040], rdx
0x18000d03e  mov     [rbp+0FD0h+var_1048], 4
0x18000d046  test    rbx, rbx
0x18000d049  jz      short loc_18000D05D
0x18000d04b  nop     dword ptr [rax+rax+00h]
0x18000d050  inc     rcx
0x18000d053  cmp     [rbx+rcx], r14b
0x18000d057  jnz     short loc_18000D050
0x18000d059  inc     ecx
0x18000d05b  jmp     short loc_18000D069
0x18000d05d  lea     rbx, qword_180060D60
0x18000d064  mov     ecx, 1
0x18000d069  movzx   eax, cs:word_18007172B
0x18000d070  mov     dword ptr [rsp+10D0h+EventDescriptor.Level], eax
0x18000d074  mov     rax, [r10+8]
0x18000d078  mov     [rsp+10D0h+var_1080.Ptr], rax
0x18000d07d  mov     [rsp+10D0h+var_1058], ecx
0x18000d081  lea     rcx, _TraceLoggingMetadata
0x18000d088  mov     [rsp+10D0h+var_1060], rbx
0x18000d08d  mov     [rsp+10D0h+var_1054], r14d
0x18000d092  mov     dword ptr [rsp+10D0h+EventDescriptor.Id], 0B000000h
0x18000d09a  mov     [rsp+10D0h+EventDescriptor.Keyword], r14
0x18000d09f  movzx   eax, word ptr [rax]
0x18000d0a2  mov     [rsp+10D0h+var_1080.Size], eax
0x18000d0a6  lea     rax, byte_180071735
0x18000d0ad  mov     [rsp+10D0h+var_1070], rax
0x18000d0b2  lea     rax, _TraceLoggingMetadataEnd
0x18000d0b9  sub     eax, ecx
0x18000d0bb  mov     dword ptr [rsp+10D0h+var_1080.0Ch], 2
0x18000d0c3  mov     [rsp+10D0h+var_1068], 2Eh ; '.'
0x18000d0cb  mov     [rsp+10D0h+var_1064], 1
0x18000d0d3  mov     [rsp+10D0h+fPending], eax
0x18000d0d7  mov     eax, [rsp+10D0h+fPending]
0x18000d0db  mov     rcx, [r10+20h]; RegHandle
0x18000d0df  lea     rax, [rsp+10D0h+var_1080]
0x18000d0e4  mov     [rsp+10D0h+UserData], rax; UserData
0x18000d0e9  lea     rdx, [rsp+10D0h+EventDescriptor]; EventDescriptor
0x18000d0ee  xor     r9d, r9d; RelatedActivityId
0x18000d0f1  mov     [rsp+10D0h+UserDataCount], 5; UserDataCount
0x18000d0f9  xor     r8d, r8d; ActivityId
0x18000d0fc  call    cs:__imp_EventWriteTransfer
0x18000d102  mov     rcx, [rbp+0FD0h+var_30]
0x18000d109  xor     rcx, rsp; StackCookie
0x18000d10c  call    __security_check_cookie
0x18000d111  add     rsp, 10B0h
0x18000d118  pop     r14
0x18000d11a  pop     rdi
0x18000d11b  pop     rsi
0x18000d11c  pop     rbx
0x18000d11d  pop     rbp
0x18000d11e  retn
```
