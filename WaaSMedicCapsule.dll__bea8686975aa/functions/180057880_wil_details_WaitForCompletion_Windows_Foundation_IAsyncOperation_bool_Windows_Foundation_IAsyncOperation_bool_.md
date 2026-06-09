# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180057880`
- end: `0x180057b0d`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180057e74`

## callees

- `0x180003c18`
- `0x180008578`
- `0x180009a54`
- `0x18000ab48`
- `0x180057880`
- `0x180057b14`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800578db`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800578db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800578ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800578fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800578ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800578fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005791d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005791d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057908`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057908`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180057a23`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180057a23`

## string_xrefs

- `0x180057974`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x1800579b3`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x1800579e1`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x180057a36`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(
        __int64 a1,
        DWORD a2,
        int a3,
        ...)
{
  void *v4; // rax
  unsigned int v5; // edi
  _QWORD *v6; // rbx
  wil::details *v7; // rcx
  HANDLE Event; // rsi
  void *v9; // rdi
  DWORD LastError; // r15d
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  int LastErrorFailHr; // eax
  HRESULT v16; // eax
  __int64 v17; // rcx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  int lpdwindexa; // [rsp+20h] [rbp-20h]
  HANDLE pHandles; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD dwindex; // [rsp+78h] [rbp+38h] BYREF
  int v23; // [rsp+80h] [rbp+40h] BYREF
  __int64 v24; // [rsp+88h] [rbp+48h] BYREF
  va_list va; // [rsp+88h] [rbp+48h]
  va_list va1; // [rsp+90h] [rbp+50h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v24 = va_arg(va1, _QWORD);
  v23 = a3;
  dwindex = a2;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v5 = -2147024882;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)v5,
      lpdwindex);
    return v5;
  }
  v6 = (_QWORD *)`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>'::`2'::CompletionDelegate::CompletionDelegate(v4);
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v9 = (void *)v6[7];
    if ( v9 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v9) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v11, v12);
      SetLastError(LastError);
    }
    v6[7] = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v7);
    v5 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
        (const char *)(unsigned int)LastErrorFailHr,
        lpdwindex);
      if ( v6 )
        (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
      goto LABEL_17;
    }
  }
  if ( v6 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v6 + 8LL))(v6);
    (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
  }
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 48LL))(a1, v6);
  v5 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v13,
      lpdwindex);
    if ( v6 )
      (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
    return v5;
  }
  pHandles = (HANDLE)v6[7];
  dwindex = 0;
  v16 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  v5 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x655,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v16,
      lpdwindexa);
    (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
    return v5;
  }
  if ( *((_DWORD *)v6 + 12) != 1 )
  {
    v24 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
           a1,
           &GUID_00000036_0000_0000_c000_000000000046,
           (__int64 *)va);
    if ( (v5 & 0x80000000) == 0 )
    {
      v23 = -2147418113;
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 64LL))(v24, &v23);
      if ( (v5 & 0x80000000) == 0 )
        v5 = v23;
    }
    v17 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
    return v5;
  }
  (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
  return 0;
}

```

## disassembly

```asm
0x180057880  mov     rax, rsp
0x180057883  mov     [rax+8], rbx
0x180057887  mov     [rax+20h], r9
0x18005788b  mov     [rax+18h], r8d
0x18005788f  mov     [rax+10h], edx
0x180057892  push    rbp
0x180057893  push    rsi
0x180057894  push    rdi
0x180057895  push    r14
0x180057897  push    r15
0x180057899  mov     rbp, rsp
0x18005789c  sub     rsp, 40h
0x1800578a0  mov     r14, rcx
0x1800578a3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800578aa  mov     ecx, 40h ; '@'; unsigned __int64
0x1800578af  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800578b4  test    rax, rax
0x1800578b7  jnz     short loc_1800578C3
0x1800578b9  mov     edi, 8007000Eh
0x1800578be  jmp     loc_1800579DA
0x1800578c3  mov     rcx, rax
0x1800578c6  call    ??0CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@QEAA@XZ; `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::CompletionDelegate(void)
0x1800578cb  mov     rbx, rax
0x1800578ce  mov     r9d, 1F0003h; dwDesiredAccess
0x1800578d4  xor     r8d, r8d; dwFlags
0x1800578d7  xor     edx, edx; lpName
0x1800578d9  xor     ecx, ecx; lpEventAttributes
0x1800578db  call    cs:__imp_CreateEventExW
0x1800578e1  mov     rsi, rax
0x1800578e4  test    rax, rax
0x1800578e7  jz      loc_18005799D
0x1800578ed  call    cs:__imp_GetLastError
0x1800578f3  mov     rdi, [rbx+38h]
0x1800578f7  test    rdi, rdi
0x1800578fa  jz      short loc_180057923
0x1800578fc  call    cs:__imp_GetLastError
0x180057902  mov     r15d, eax
0x180057905  mov     rcx, rdi; hObject
0x180057908  call    cs:__imp_CloseHandle
0x18005790e  mov     rcx, [rbp+28h]; this
0x180057912  test    eax, eax
0x180057914  jz      loc_180057B02
0x18005791a  mov     ecx, r15d; dwErrCode
0x18005791d  call    cs:__imp_SetLastError
0x180057923  mov     [rbx+38h], rsi
0x180057927  test    rbx, rbx
0x18005792a  jz      short loc_18005793C
0x18005792c  mov     rax, [rbx]
0x18005792f  mov     rcx, rbx
0x180057932  mov     rax, [rax+8]
0x180057936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005793b  nop
0x18005793c  test    rbx, rbx
0x18005793f  jz      short loc_180057951
0x180057941  mov     rax, [rbx]
0x180057944  mov     rcx, rbx
0x180057947  mov     rax, [rax+10h]
0x18005794b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057950  nop
0x180057951  mov     rax, [r14]
0x180057954  mov     rdx, rbx
0x180057957  mov     rcx, r14
0x18005795a  mov     rax, [rax+30h]
0x18005795e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057963  mov     edi, eax
0x180057965  test    eax, eax
0x180057967  jns     loc_1800579FA
0x18005796d  mov     rcx, [rbp+28h]; this
0x180057971  mov     r9d, eax; char *
0x180057974  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005797b  mov     edx, 649h; void *
0x180057980  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057985  nop
0x180057986  test    rbx, rbx
0x180057989  jz      short loc_18005799B
0x18005798b  mov     rcx, [rbx]
0x18005798e  mov     rax, [rcx+10h]
0x180057992  mov     rcx, rbx
0x180057995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005799a  nop
0x18005799b  jmp     short loc_1800579F3
0x18005799d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800579a2  mov     edi, eax
0x1800579a4  test    eax, eax
0x1800579a6  jns     loc_180057927
0x1800579ac  mov     rcx, [rbp+28h]; this
0x1800579b0  mov     r9d, eax; char *
0x1800579b3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800579ba  mov     edx, 62Bh; void *
0x1800579bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800579c4  nop
0x1800579c5  test    rbx, rbx
0x1800579c8  jz      short loc_1800579DA
0x1800579ca  mov     rax, [rbx]
0x1800579cd  mov     rcx, rbx
0x1800579d0  mov     rax, [rax+10h]
0x1800579d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800579d9  nop
0x1800579da  mov     rcx, [rbp+28h]; this
0x1800579de  mov     r9d, edi; char *
0x1800579e1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800579e8  mov     edx, 648h; void *
0x1800579ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800579f2  nop
0x1800579f3  mov     eax, edi
0x1800579f5  jmp     loc_180057AF1
0x1800579fa  mov     rax, [rbx+38h]
0x1800579fe  mov     [rbp+pHandles], rax
0x180057a02  mov     [rbp+dwindex], 0
0x180057a09  lea     rax, [rbp+dwindex]
0x180057a0d  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x180057a12  lea     r9, [rbp+pHandles]; pHandles
0x180057a16  mov     r8d, 1; cHandles
0x180057a1c  or      edx, 0FFFFFFFFh; dwTimeout
0x180057a1f  lea     ecx, [r8+7]; dwFlags
0x180057a23  call    cs:__imp_CoWaitForMultipleHandles
0x180057a29  mov     edi, eax
0x180057a2b  test    eax, eax
0x180057a2d  jns     short loc_180057A5A
0x180057a2f  mov     rcx, [rbp+28h]; this
0x180057a33  mov     r9d, eax; char *
0x180057a36  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180057a3d  mov     edx, 655h; void *
0x180057a42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057a47  nop
0x180057a48  mov     rcx, [rbx]
0x180057a4b  mov     rax, [rcx+10h]
0x180057a4f  mov     rcx, rbx
0x180057a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a57  nop
0x180057a58  jmp     short loc_1800579F3
0x180057a5a  mov     eax, [rbx+30h]
0x180057a5d  cmp     eax, 1
0x180057a60  jz      short loc_180057ADF
0x180057a62  mov     [rbp+arg_18], 0
0x180057a6a  mov     rax, [r14]
0x180057a6d  lea     r8, [rbp+arg_18]
0x180057a71  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180057a78  mov     rcx, r14
0x180057a7b  mov     rax, [rax]
0x180057a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a83  mov     edi, eax
0x180057a85  test    eax, eax
0x180057a87  js      short loc_180057AAC
0x180057a89  mov     [rbp+arg_10], 8000FFFFh
0x180057a90  mov     rcx, [rbp+arg_18]
0x180057a94  mov     rax, [rcx]
0x180057a97  lea     rdx, [rbp+arg_10]
0x180057a9b  mov     rax, [rax+40h]
0x180057a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057aa4  mov     edi, eax
0x180057aa6  test    eax, eax
0x180057aa8  cmovns  edi, [rbp+arg_10]
0x180057aac  mov     rcx, [rbp+arg_18]
0x180057ab0  test    rcx, rcx
0x180057ab3  jz      short loc_180057ACA
0x180057ab5  mov     [rbp+arg_18], 0
0x180057abd  mov     rax, [rcx]
0x180057ac0  mov     rax, [rax+10h]
0x180057ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057ac9  nop
0x180057aca  mov     rax, [rbx]
0x180057acd  mov     rcx, rbx
0x180057ad0  mov     rax, [rax+10h]
0x180057ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057ad9  nop
0x180057ada  jmp     loc_1800579F3
0x180057adf  mov     rax, [rbx]
0x180057ae2  mov     rcx, rbx
0x180057ae5  mov     rax, [rax+10h]
0x180057ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057aee  nop
0x180057aef  xor     eax, eax
0x180057af1  mov     rbx, [rsp+40h+arg_0]
0x180057af6  add     rsp, 40h
0x180057afa  pop     r15
0x180057afc  pop     r14
0x180057afe  pop     rdi
0x180057aff  pop     rsi
0x180057b00  pop     rbp
0x180057b01  retn
0x180057b02  mov     edx, 0A0Bh; void *
0x180057b07  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
