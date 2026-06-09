# DevhlprGetReaderBitmapBlobInternal(ushort *,uchar *,ulong,ulong *)

- ea: `0x180029ca4`
- end: `0x180029e49`
- name: `?DevhlprGetReaderBitmapBlobInternal@@YA?AV?$scoped_error@Utag@hresult_error@@@errorlib@@PEAGPEAEKPEAK@Z`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180029b9c`

## callees

- `0x180029a60`
- `0x180029a88`
- `0x180029abc`
- `0x180029ae8`
- `0x180029b20`
- `0x180029c60`
- `0x180029ca4`
- `0x180029f84`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180029dfe`
- `msvcrt!memcpy_s` at `0x180029dfe`
- `WinSCard!SCardGetReaderIconW` at `0x180029d7e`
- `WinSCard!SCardGetReaderIconW` at `0x180029d7e`
- `WinSCard!SCardEstablishContext` at `0x180029d38`
- `WinSCard!SCardEstablishContext` at `0x180029d38`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int *__fastcall DevhlprGetReaderBitmapBlobInternal(int *a1, __int64 a2, void *a3, unsigned int a4, _DWORD *a5)
{
  rsize_t v5; // rdi
  _DWORD *v10; // rsi
  int v11; // eax
  rsize_t v12; // rax
  LONG ReaderIconW; // [rsp+20h] [rbp-48h] BYREF
  int v14; // [rsp+28h] [rbp-40h] BYREF
  int v15; // [rsp+2Ch] [rbp-3Ch]
  SCARDCONTEXT phContext; // [rsp+30h] [rbp-38h] BYREF
  void *Source; // [rsp+38h] [rbp-30h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-28h] BYREF
  __int16 v19; // [rsp+50h] [rbp-18h]
  rsize_t SourceSize; // [rsp+B0h] [rbp+48h] BYREF

  v5 = a4;
  errorlib::scoped_error<hresult_error::tag>::scoped_error<hresult_error::tag>(&v14);
  phContext = 0;
  if ( a3 )
  {
    if ( !(_DWORD)v5 )
      goto LABEL_3;
LABEL_6:
    if ( !a2 )
      goto LABEL_3;
    v10 = a5;
    if ( !a5 )
      goto LABEL_3;
    phContext = 0;
    ReaderIconW = SCardEstablishContext(2u, 0, 0, &phContext);
    errorlib::scoped_error<hresult_error::tag>::receive<long>(&v14, &ReaderIconW);
    v15 = 3;
    v11 = v14;
    if ( v14 < 0
      || (Source = 0,
          LODWORD(SourceSize) = -1,
          ReaderIconW = SCardGetReaderIconW(phContext, a2, &Source, &SourceSize),
          errorlib::scoped_error<hresult_error::tag>::receive<long>(&v14, &ReaderIconW),
          v15 = 3,
          v11 = v14,
          v14 < 0) )
    {
      *a1 = v11;
      a1[1] = 2;
      v15 = 5;
      errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
      goto LABEL_4;
    }
    v18[0] = &phContext;
    v18[1] = &Source;
    v19 = 256;
    v12 = (unsigned int)SourceSize;
    *v10 = SourceSize;
    if ( a3 )
    {
      if ( (unsigned int)v5 >= (unsigned int)v12 )
      {
        memcpy_s(a3, v5, Source, v12);
        *a1 = v14;
        a1[1] = 2;
        v15 = 5;
        errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
        goto LABEL_13;
      }
      ReaderIconW = -2146435064;
    }
    else
    {
      ReaderIconW = 0;
    }
    errorlib::scoped_error<hresult_error::tag>::make_initiated<long>(a1, &ReaderIconW);
LABEL_13:
    wil::details::ScopeExitFnGuard__lambda_38cbbc084cd607496c2708d4d1fe6080___::operator()(v18);
    goto LABEL_4;
  }
  if ( !(_DWORD)v5 )
    goto LABEL_6;
LABEL_3:
  ReaderIconW = -2146435068;
  errorlib::scoped_error<hresult_error::tag>::make_initiated<long>(a1, &ReaderIconW);
LABEL_4:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phContext);
  errorlib::scoped_error<hresult_error::tag>::~scoped_error<hresult_error::tag>(&v14);
  return a1;
}

```

## disassembly

```asm
0x180029ca4  push    rbp
0x180029ca6  push    rbx
0x180029ca7  push    rsi
0x180029ca8  push    rdi
0x180029ca9  push    r14
0x180029cab  push    r15
0x180029cad  mov     rbp, rsp
0x180029cb0  sub     rsp, 68h
0x180029cb4  mov     edi, r9d
0x180029cb7  mov     r14, r8
0x180029cba  mov     r15, rdx
0x180029cbd  mov     rbx, rcx
0x180029cc0  lea     rcx, [rbp+var_40]
0x180029cc4  call    ??0?$scoped_error@Utag@hresult_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<hresult_error::tag>::scoped_error<hresult_error::tag>(void)
0x180029cc9  nop
0x180029cca  mov     [rbp+phContext], 0
0x180029cd2  test    r14, r14
0x180029cd5  jnz     short loc_180029D12
0x180029cd7  test    edi, edi
0x180029cd9  jz      short loc_180029D16
0x180029cdb  mov     [rbp+var_48], 80100004h
0x180029ce2  lea     rdx, [rbp+var_48]
0x180029ce6  mov     rcx, rbx
0x180029ce9  call    ??$make_initiated@J@?$scoped_error@Utag@hresult_error@@@errorlib@@SA?AV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::make_initiated<long>(long &&)
0x180029cee  nop
0x180029cef  lea     rcx, [rbp+phContext]
0x180029cf3  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?SCardReleaseContext@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180029cf8  nop
0x180029cf9  lea     rcx, [rbp+var_40]
0x180029cfd  call    ??1?$scoped_error@Utag@hresult_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<hresult_error::tag>::~scoped_error<hresult_error::tag>(void)
0x180029d02  mov     rax, rbx
0x180029d05  add     rsp, 68h
0x180029d09  pop     r15
0x180029d0b  pop     r14
0x180029d0d  pop     rdi
0x180029d0e  pop     rsi
0x180029d0f  pop     rbx
0x180029d10  pop     rbp
0x180029d11  retn
0x180029d12  test    edi, edi
0x180029d14  jz      short loc_180029CDB
0x180029d16  test    r15, r15
0x180029d19  jz      short loc_180029CDB
0x180029d1b  mov     rsi, [rbp+arg_20]
0x180029d1f  test    rsi, rsi
0x180029d22  jz      short loc_180029CDB
0x180029d24  mov     [rbp+phContext], 0
0x180029d2c  lea     r9, [rbp+phContext]; phContext
0x180029d30  xor     r8d, r8d; pvReserved2
0x180029d33  xor     edx, edx; pvReserved1
0x180029d35  lea     ecx, [rdx+2]; dwScope
0x180029d38  call    cs:__imp_SCardEstablishContext
0x180029d3e  mov     [rbp+var_48], eax
0x180029d41  lea     rdx, [rbp+var_48]
0x180029d45  lea     rcx, [rbp+var_40]
0x180029d49  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x180029d4e  mov     [rbp+var_3C], 3
0x180029d55  mov     eax, [rbp+var_40]
0x180029d58  test    eax, eax
0x180029d5a  js      loc_180029E26
0x180029d60  mov     [rbp+Source], 0
0x180029d68  mov     dword ptr [rbp+SourceSize], 0FFFFFFFFh
0x180029d6f  lea     r9, [rbp+SourceSize]
0x180029d73  lea     r8, [rbp+Source]
0x180029d77  mov     rdx, r15
0x180029d7a  mov     rcx, [rbp+phContext]
0x180029d7e  call    cs:__imp_SCardGetReaderIconW
0x180029d84  mov     [rbp+var_48], eax
0x180029d87  lea     rdx, [rbp+var_48]
0x180029d8b  lea     rcx, [rbp+var_40]
0x180029d8f  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x180029d94  mov     [rbp+var_3C], 3
0x180029d9b  mov     eax, [rbp+var_40]
0x180029d9e  test    eax, eax
0x180029da0  js      loc_180029E26
0x180029da6  lea     rax, [rbp+phContext]
0x180029daa  mov     [rbp+var_28], rax
0x180029dae  lea     rax, [rbp+Source]
0x180029db2  mov     [rbp+var_20], rax
0x180029db6  mov     [rbp+var_18], 100h
0x180029dbc  mov     eax, dword ptr [rbp+SourceSize]
0x180029dbf  mov     [rsi], eax
0x180029dc1  test    r14, r14
0x180029dc4  jnz     short loc_180029DE4
0x180029dc6  mov     [rbp+var_48], r14d
0x180029dca  lea     rdx, [rbp+var_48]
0x180029dce  mov     rcx, rbx
0x180029dd1  call    ??$make_initiated@J@?$scoped_error@Utag@hresult_error@@@errorlib@@SA?AV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::make_initiated<long>(long &&)
0x180029dd6  lea     rcx, [rbp+var_28]
0x180029dda  call    wil__details__ScopeExitFnGuard__lambda_38cbbc084cd607496c2708d4d1fe6080_____operator__
0x180029ddf  jmp     loc_180029CEF
0x180029de4  cmp     edi, eax
0x180029de6  jnb     short loc_180029DF1
0x180029de8  mov     [rbp+var_48], 80100008h
0x180029def  jmp     short loc_180029DCA
0x180029df1  mov     r9, rax; SourceSize
0x180029df4  mov     rdx, rdi; DestinationSize
0x180029df7  mov     r8, [rbp+Source]; Source
0x180029dfb  mov     rcx, r14; Destination
0x180029dfe  call    cs:__imp_memcpy_s
0x180029e04  mov     eax, [rbp+var_40]
0x180029e07  mov     [rbx], eax
0x180029e09  mov     dword ptr [rbx+4], 2
0x180029e10  mov     [rbp+var_3C], 5
0x180029e17  mov     edx, 3
0x180029e1c  mov     rcx, rbx
0x180029e1f  call    ?report@?$scoped_error@Utag@hresult_error@@@errorlib@@AEAAXW4type@ErrorSource@2@@Z; errorlib::scoped_error<hresult_error::tag>::report(errorlib::ErrorSource::type)
0x180029e24  jmp     short loc_180029DD6
0x180029e26  mov     [rbx], eax
0x180029e28  mov     dword ptr [rbx+4], 2
0x180029e2f  mov     [rbp+var_3C], 5
0x180029e36  mov     edx, 3
0x180029e3b  mov     rcx, rbx
0x180029e3e  call    ?report@?$scoped_error@Utag@hresult_error@@@errorlib@@AEAAXW4type@ErrorSource@2@@Z; errorlib::scoped_error<hresult_error::tag>::report(errorlib::ErrorSource::type)
0x180029e43  jmp     loc_180029CEF
```
