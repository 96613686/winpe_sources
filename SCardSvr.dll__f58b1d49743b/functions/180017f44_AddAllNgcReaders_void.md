# AddAllNgcReaders(void)

- ea: `0x180017f44`
- end: `0x1800181b7`
- name: `?AddAllNgcReaders@@YAXXZ`
- size: `627`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180011410`

## callees

- `0x1800022b0`
- `0x1800075d0`
- `0x180017db0`
- `0x180017f44`
- `0x1800181c0`
- `0x1800181dc`
- `0x180018244`
- `0x18002a150`
- `0x18002c43c`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018149`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180018181`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180018181`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x180018072`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x180018072`

## string_xrefs

- `0x180017f72`: `AddAllNgcReaders`

## pseudocode

```c
void AddAllNgcReaders(void)
{
  signed int Objects; // eax
  const unsigned __int8 *v1; // rcx
  unsigned int i; // ebx
  __int64 v3; // rdi
  unsigned int v4; // eax
  __int64 v5; // rcx
  char v6; // si
  int v7; // r8d
  int v8; // r9d
  struct _TP_WORK *AsyncReaderHandlingWork; // rax
  signed int LastError; // ebx
  const unsigned __int8 *v11; // rcx
  unsigned int v12; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v13; // [rsp+44h] [rbp-BCh] BYREF
  signed int v14; // [rsp+48h] [rbp-B8h] BYREF
  int v15; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v17; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v18[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v19; // [rsp+70h] [rbp-90h]
  _QWORD v20[3]; // [rsp+78h] [rbp-88h] BYREF
  int v21; // [rsp+90h] [rbp-70h] BYREF
  DEVPROPKEY v22; // [rsp+98h] [rbp-68h]
  int v23; // [rsp+ACh] [rbp-54h]
  __int64 v24; // [rsp+B0h] [rbp-50h]
  int v25; // [rsp+B8h] [rbp-48h]
  int v26; // [rsp+BCh] [rbp-44h]
  GUID *v27; // [rsp+C0h] [rbp-40h]
  int v28; // [rsp+C8h] [rbp-38h]
  DEVPROPKEY v29; // [rsp+D0h] [rbp-30h]
  int v30; // [rsp+E4h] [rbp-1Ch]
  __int64 v31; // [rsp+E8h] [rbp-18h]
  int v32; // [rsp+F0h] [rbp-10h]
  int v33; // [rsp+F4h] [rbp-Ch]
  unsigned int *v34; // [rsp+F8h] [rbp-8h]
  char v35[24]; // [rsp+100h] [rbp+0h] BYREF

  v14 = 0;
  v15 = 0;
  strcpy(v35, "AddAllNgcReaders");
  v20[0] = v35;
  v20[1] = &v15;
  v20[2] = &v14;
  lambda_29dc355c359e902416a08dad320d4f96_::operator()(v20);
  v15 = 1;
  v17 = v20;
  LOBYTE(v12) = -1;
  v21 = 2;
  v22 = DEVPKEY_DeviceInterface_ClassGuid;
  v23 = 0;
  v24 = 0;
  v25 = 13;
  v26 = 16;
  v27 = &GUID_DEVINTERFACE_NGC_CONTAINER;
  v28 = 2;
  v29 = DEVPKEY_DeviceInterface_Enabled;
  v30 = 0;
  v31 = 0;
  v32 = 17;
  v33 = 1;
  v34 = &v12;
  v16 = 0;
  Objects = DevGetObjects(1, 0, 0, 0, 2, &v21, &v13, &v16, v12);
  v14 = Objects;
  if ( Objects >= 0 )
  {
    v18[0] = &v16;
    v18[1] = &v13;
    v19 = 256;
    for ( i = 0; i < v13; ++i )
    {
      v3 = 32LL * i;
      v4 = CalaisAsyncAddReader(
             (unsigned int (*)(const unsigned __int16 *, unsigned int))AddNgcReader,
             *(const unsigned __int16 **)(v3 + v16 + 8),
             0);
      v6 = v4;
      if ( v4 )
      {
        WppTraceIndent(v5, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_sSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *(_QWORD *)(v3 + v16 + 8),
            v7,
            v8,
            *(_QWORD *)(v3 + v16 + 8),
            v6);
        }
      }
    }
    AsyncReaderHandlingWork = CalaisCreateAsyncReaderHandlingWork((PTP_WORK_CALLBACK)RefreshNgcReadersWorkCallback, 0);
    if ( AsyncReaderHandlingWork )
    {
      SubmitThreadpoolWork(AsyncReaderHandlingWork);
    }
    else
    {
      LastError = GetLastError();
      CalaisError(v11, 0x263u, LastError, 0, 0, 0);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v14 = LastError;
    }
    wil::details::ScopeExitFnGuard__lambda_599649aa7b5756262005fbe025ac213a___::operator()(v18);
  }
  else
  {
    CalaisError(v1, 0x263u, Objects, 0, 0, 0);
  }
  WppTraceUnwinder__lambda_29dc355c359e902416a08dad320d4f96____::_WppTraceUnwinder__lambda_29dc355c359e902416a08dad320d4f96____(&v17);
}

```

## disassembly

```asm
0x180017f44  push    rbp
0x180017f46  push    rbx
0x180017f47  push    rsi
0x180017f48  push    rdi
0x180017f49  push    r14
0x180017f4b  lea     rbp, [rsp-20h]
0x180017f50  sub     rsp, 120h
0x180017f57  mov     rax, cs:__security_cookie
0x180017f5e  xor     rax, rsp
0x180017f61  mov     [rbp+40h+var_28], rax
0x180017f65  xor     r14d, r14d
0x180017f68  mov     [rsp+140h+var_F8], r14d
0x180017f6d  mov     [rsp+140h+var_F4], r14d
0x180017f72  movups  xmm0, xmmword ptr cs:aAddallngcreade; "AddAllNgcReaders"
0x180017f79  movups  xmmword ptr [rbp+40h+var_40], xmm0
0x180017f7d  mov     al, byte ptr cs:aAddallngcreade+10h; ""
0x180017f83  mov     [rbp+40h+var_40+10h], al
0x180017f86  lea     rax, [rbp+40h+var_40]
0x180017f8a  mov     [rsp+140h+var_C8], rax
0x180017f8f  lea     rax, [rsp+140h+var_F4]
0x180017f94  mov     [rbp+40h+var_C0], rax
0x180017f98  lea     rax, [rsp+140h+var_F8]
0x180017f9d  mov     [rbp+40h+var_B8], rax
0x180017fa1  lea     rcx, [rsp+140h+var_C8]
0x180017fa6  call    _lambda_29dc355c359e902416a08dad320d4f96___operator__
0x180017fab  mov     [rsp+140h+var_F4], 1
0x180017fb3  lea     rax, [rsp+140h+var_C8]
0x180017fb8  mov     [rsp+140h+var_E8], rax
0x180017fbd  mov     byte ptr [rsp+140h+var_100], 0FFh
0x180017fc2  mov     [rbp+40h+var_B0], 2
0x180017fc9  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x180017fd0  movups  [rbp+40h+var_A8], xmm0
0x180017fd4  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x180017fda  mov     [rbp+40h+var_98], eax
0x180017fdd  mov     [rbp+40h+var_94], r14d
0x180017fe1  mov     [rbp+40h+var_90], r14
0x180017fe5  mov     [rbp+40h+var_88], 0Dh
0x180017fec  mov     [rbp+40h+var_84], 10h
0x180017ff3  lea     rax, GUID_DEVINTERFACE_NGC_CONTAINER
0x180017ffa  mov     [rbp+40h+var_80], rax
0x180017ffe  mov     [rbp+40h+var_78], 2
0x180018005  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x18001800c  movaps  [rbp+40h+var_70], xmm0
0x180018010  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x180018016  mov     [rbp+40h+var_60], eax
0x180018019  mov     [rbp+40h+var_5C], r14d
0x18001801d  mov     [rbp+40h+var_58], r14
0x180018021  mov     [rbp+40h+var_50], 11h
0x180018028  mov     [rbp+40h+var_4C], 1
0x18001802f  lea     rax, [rsp+140h+var_100]
0x180018034  mov     [rbp+40h+var_48], rax
0x180018038  mov     [rsp+140h+var_F0], r14
0x18001803d  mov     [rsp+140h+var_FC], r14d
0x180018042  lea     rax, [rsp+140h+var_F0]
0x180018047  mov     [rsp+140h+var_108], rax
0x18001804c  lea     rax, [rsp+140h+var_FC]
0x180018051  mov     [rsp+140h+var_110], rax
0x180018056  lea     rax, [rbp+40h+var_B0]
0x18001805a  mov     [rsp+140h+var_118], rax
0x18001805f  mov     dword ptr [rsp+140h+var_120], 2
0x180018067  xor     r9d, r9d
0x18001806a  xor     r8d, r8d
0x18001806d  xor     edx, edx
0x18001806f  lea     ecx, [rdx+1]
0x180018072  call    cs:__imp_DevGetObjects
0x180018078  mov     [rsp+140h+var_F8], eax
0x18001807c  test    eax, eax
0x18001807e  jns     short loc_18001809F
0x180018080  mov     [rsp+140h+var_118], r14; unsigned __int16 *
0x180018085  mov     [rsp+140h+var_120], r14; unsigned __int16 *
0x18001808a  xor     r9d, r9d; unsigned __int16 *
0x18001808d  mov     r8d, eax; unsigned int
0x180018090  mov     edx, 263h; unsigned int
0x180018095  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001809a  jmp     loc_180018193
0x18001809f  lea     rax, [rsp+140h+var_F0]
0x1800180a4  mov     [rsp+140h+var_E0], rax
0x1800180a9  lea     rax, [rsp+140h+var_FC]
0x1800180ae  mov     [rsp+140h+var_D8], rax
0x1800180b3  mov     [rsp+140h+var_D0], 100h
0x1800180ba  mov     ebx, r14d
0x1800180bd  cmp     [rsp+140h+var_FC], r14d
0x1800180c2  jbe     short loc_180018136
0x1800180c4  mov     edi, ebx
0x1800180c6  shl     rdi, 5
0x1800180ca  xor     r8d, r8d; unsigned int
0x1800180cd  mov     rdx, [rsp+140h+var_F0]
0x1800180d2  mov     rdx, [rdi+rdx+8]; unsigned __int16 *
0x1800180d7  lea     rcx, ?AddNgcReader@@YAKPEBGK@Z; unsigned int (*)(const unsigned __int16 *, unsigned int)
0x1800180de  call    ?CalaisAsyncAddReader@@YAKP6AKPEBGK@Z0K@Z; CalaisAsyncAddReader(ulong (*)(ushort const *,ulong),ushort const *,ulong)
0x1800180e3  mov     esi, eax
0x1800180e5  test    eax, eax
0x1800180e7  jz      short loc_18001812E
0x1800180e9  mov     edx, 2
0x1800180ee  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800180f3  lea     rax, WPP_GLOBAL_Control
0x1800180fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180018101  cmp     rcx, rax
0x180018104  jz      short loc_18001812E
0x180018106  test    byte ptr [rcx+1Ch], 1
0x18001810a  jz      short loc_18001812E
0x18001810c  cmp     byte ptr [rcx+19h], 3
0x180018110  jb      short loc_18001812E
0x180018112  mov     dword ptr [rsp+140h+var_118], esi
0x180018116  mov     rax, [rsp+140h+var_F0]
0x18001811b  mov     rdx, [rdi+rax+8]
0x180018120  mov     [rsp+140h+var_120], rdx
0x180018125  mov     rcx, [rcx+10h]
0x180018129  call    WPP_SF_sSD
0x18001812e  inc     ebx
0x180018130  cmp     ebx, [rsp+140h+var_FC]
0x180018134  jb      short loc_1800180C4
0x180018136  xor     edx, edx; pv
0x180018138  lea     rcx, ?RefreshNgcReadersWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001813f  call    ?CalaisCreateAsyncReaderHandlingWork@@YAPEAU_TP_WORK@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU1@@Z1@Z; CalaisCreateAsyncReaderHandlingWork(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x180018144  test    rax, rax
0x180018147  jnz     short loc_18001817E
0x180018149  call    cs:__imp_GetLastError
0x18001814f  mov     ebx, eax
0x180018151  mov     [rsp+140h+var_118], r14; unsigned __int16 *
0x180018156  mov     [rsp+140h+var_120], r14; unsigned __int16 *
0x18001815b  xor     r9d, r9d; unsigned __int16 *
0x18001815e  mov     r8d, eax; unsigned int
0x180018161  mov     edx, 263h; unsigned int
0x180018166  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001816b  test    ebx, ebx
0x18001816d  jle     short loc_180018178
0x18001816f  movzx   ebx, bx
0x180018172  or      ebx, 80070000h
0x180018178  mov     [rsp+140h+var_F8], ebx
0x18001817c  jmp     short loc_180018188
0x18001817e  mov     rcx, rax; pwk
0x180018181  call    cs:__imp_SubmitThreadpoolWork
0x180018187  nop
0x180018188  lea     rcx, [rsp+140h+var_E0]
0x18001818d  call    wil__details__ScopeExitFnGuard__lambda_599649aa7b5756262005fbe025ac213a_____operator__
0x180018192  nop
0x180018193  lea     rcx, [rsp+140h+var_E8]
0x180018198  call    WppTraceUnwinder__lambda_29dc355c359e902416a08dad320d4f96_______WppTraceUnwinder__lambda_29dc355c359e902416a08dad320d4f96____
0x18001819d  mov     rcx, [rbp+40h+var_28]
0x1800181a1  xor     rcx, rsp; StackCookie
0x1800181a4  call    __security_check_cookie
0x1800181a9  add     rsp, 120h
0x1800181b0  pop     r14
0x1800181b2  pop     rdi
0x1800181b3  pop     rsi
0x1800181b4  pop     rbx
0x1800181b5  pop     rbp
0x1800181b6  retn
```
