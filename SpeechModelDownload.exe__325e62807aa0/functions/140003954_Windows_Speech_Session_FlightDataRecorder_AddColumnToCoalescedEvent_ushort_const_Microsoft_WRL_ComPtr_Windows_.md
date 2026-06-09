# Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,ushort const *)

- ea: `0x140003954`
- end: `0x140003b0a`
- name: `??$AddColumnToCoalescedEvent@PEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBG1@Z`
- size: `438`
- prototype: `__int64 __fastcall(Windows::Speech::Session::FlightDataRecorder *, __int64 **, const WCHAR *, const WCHAR *)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003840`
- `0x14000a26c`
- `0x14000a4ac`
- `0x140013e8c`

## callees

- `0x140002600`
- `0x140003954`
- `0x140005ea0`
- `0x140007870`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400039f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140003a5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400039f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140003a5a`

## pseudocode

```c
__int64 __fastcall Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<unsigned short const *>(
        Windows::Speech::Session::FlightDataRecorder *a1,
        __int64 **a2,
        const WCHAR *a3,
        const WCHAR *a4)
{
  int v8; // ebx
  __int64 *v9; // rbx
  __int64 v10; // r13
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // rdx
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  int v16; // edx
  unsigned int v17; // r8d
  __int64 *v18; // rbx
  __int64 v19; // r13
  __int64 v20; // r14
  HRESULT v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  __int64 v24; // rcx
  __int64 *v25; // rcx
  _QWORD v27[2]; // [rsp+20h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF

  v27[1] = a2;
  if ( !*a2 || !a3 || (v8 = Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(a1), v8 >= 0) && !a4 )
    v8 = -2147024809;
  v27[0] = 0;
  if ( v8 >= 0 )
  {
    v9 = (__int64 *)*((_QWORD *)a1 + 10);
    v10 = *v9;
    string = 0;
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( a4[v12] );
    if ( v12 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v12, (unsigned int)a3);
      __debugbreak();
    }
    if ( (int)v12 + 1 < (unsigned int)v12 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v12, (unsigned int)a3);
      __debugbreak();
    }
    v13 = WindowsCreateStringReference(a4, v12, &hstringHeader, &string);
    if ( v13 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
      __debugbreak();
    }
    v8 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD *))(v10 + 80))(v9, string, v27);
    if ( v8 >= 0 )
    {
      v18 = *a2;
      v19 = **a2;
      string = 0;
      do
        ++v11;
      while ( a3[v11] );
      if ( v11 > 0xFFFFFFFF )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v16, v17);
        __debugbreak();
      }
      if ( (int)v11 + 1 < (unsigned int)v11 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v16, v17);
        __debugbreak();
      }
      v20 = v27[0];
      v21 = WindowsCreateStringReference(a3, v11, &hstringHeader, &string);
      if ( v21 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
        JUMPOUT(0x140003B09LL);
      }
      v8 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64))(v19 + 56))(v18, string, v20);
    }
  }
  v24 = v27[0];
  if ( v27[0] )
  {
    v27[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64 *))(*v25 + 16))(v25);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140003954  push    rbp
0x140003956  push    rbx
0x140003957  push    rsi
0x140003958  push    rdi
0x140003959  push    r12
0x14000395b  push    r13
0x14000395d  push    r14
0x14000395f  push    r15
0x140003961  mov     rbp, rsp
0x140003964  sub     rsp, 68h
0x140003968  mov     rax, cs:__security_cookie
0x14000396f  xor     rax, rsp
0x140003972  mov     [rbp+var_18], rax
0x140003976  mov     r14, r9
0x140003979  mov     r15, r8
0x14000397c  mov     rsi, rdx
0x14000397f  mov     rdi, rcx
0x140003982  mov     [rbp+var_40], rdx
0x140003986  xor     r12d, r12d
0x140003989  cmp     [rdx], r12
0x14000398c  jz      short loc_1400039A3
0x14000398e  test    r8, r8
0x140003991  jz      short loc_1400039A3
0x140003993  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x140003998  mov     ebx, eax
0x14000399a  test    eax, eax
0x14000399c  js      short loc_1400039A8
0x14000399e  test    r14, r14
0x1400039a1  jnz     short loc_1400039A8
0x1400039a3  mov     ebx, 80070057h
0x1400039a8  mov     [rbp+var_48], r12
0x1400039ac  test    ebx, ebx
0x1400039ae  js      loc_140003A7D
0x1400039b4  mov     rbx, [rdi+50h]
0x1400039b8  mov     r13, [rbx]
0x1400039bb  mov     [rbp+string], r12
0x1400039bf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400039c3  mov     rdx, rdi
0x1400039c6  inc     rdx; int
0x1400039c9  cmp     [r14+rdx*2], r12w
0x1400039ce  jnz     short loc_1400039C6
0x1400039d0  mov     eax, 0FFFFFFFFh
0x1400039d5  cmp     rdx, rax
0x1400039d8  ja      loc_140003AD9
0x1400039de  lea     eax, [rdx+1]
0x1400039e1  cmp     eax, edx
0x1400039e3  jb      loc_140003AE4
0x1400039e9  lea     r9, [rbp+string]; string
0x1400039ed  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1400039f1  mov     rcx, r14; sourceString
0x1400039f4  call    cs:__imp_WindowsCreateStringReference
0x1400039fa  test    eax, eax
0x1400039fc  js      loc_140003AEF
0x140003a02  lea     r8, [rbp+var_48]
0x140003a06  mov     rdx, [rbp+string]
0x140003a0a  mov     rcx, rbx
0x140003a0d  mov     rax, [r13+50h]
0x140003a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a16  mov     ebx, eax
0x140003a18  test    eax, eax
0x140003a1a  js      short loc_140003A7D
0x140003a1c  mov     rbx, [rsi]
0x140003a1f  mov     r13, [rbx]
0x140003a22  mov     [rbp+string], r12
0x140003a26  inc     rdi
0x140003a29  cmp     [r15+rdi*2], r12w
0x140003a2e  jnz     short loc_140003A26
0x140003a30  mov     eax, 0FFFFFFFFh
0x140003a35  cmp     rdi, rax
0x140003a38  ja      loc_140003ACE
0x140003a3e  lea     eax, [rdi+1]
0x140003a41  cmp     eax, edi
0x140003a43  jb      loc_140003AF7
0x140003a49  mov     r14, [rbp+var_48]
0x140003a4d  lea     r9, [rbp+string]; string
0x140003a51  lea     r8, [rbp+hstringHeader]; hstringHeader
0x140003a55  mov     edx, edi; length
0x140003a57  mov     rcx, r15; sourceString
0x140003a5a  call    cs:__imp_WindowsCreateStringReference
0x140003a60  test    eax, eax
0x140003a62  js      loc_140003B02
0x140003a68  mov     r8, r14
0x140003a6b  mov     rdx, [rbp+string]
0x140003a6f  mov     rcx, rbx
0x140003a72  mov     rax, [r13+38h]
0x140003a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a7b  mov     ebx, eax
0x140003a7d  mov     rcx, [rbp+var_48]
0x140003a81  test    rcx, rcx
0x140003a84  jz      short loc_140003A97
0x140003a86  mov     [rbp+var_48], r12
0x140003a8a  mov     rax, [rcx]
0x140003a8d  mov     rax, [rax+10h]
0x140003a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a96  nop
0x140003a97  mov     rcx, [rsi]
0x140003a9a  test    rcx, rcx
0x140003a9d  jz      short loc_140003AAF
0x140003a9f  mov     [rsi], r12
0x140003aa2  mov     rax, [rcx]
0x140003aa5  mov     rax, [rax+10h]
0x140003aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003aae  nop
0x140003aaf  mov     eax, ebx
0x140003ab1  mov     rcx, [rbp+var_18]
0x140003ab5  xor     rcx, rsp; StackCookie
0x140003ab8  call    __security_check_cookie
0x140003abd  add     rsp, 68h
0x140003ac1  pop     r15
0x140003ac3  pop     r14
0x140003ac5  pop     r13
0x140003ac7  pop     r12
0x140003ac9  pop     rdi
0x140003aca  pop     rsi
0x140003acb  pop     rbx
0x140003acc  pop     rbp
0x140003acd  retn
0x140003ace  mov     ecx, 80070216h; this
0x140003ad3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140003ad8  int     3; Trap to Debugger
0x140003ad9  mov     ecx, 80070216h; this
0x140003ade  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140003ae3  int     3; Trap to Debugger
0x140003ae4  mov     ecx, 80070216h; this
0x140003ae9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140003aee  int     3; Trap to Debugger
0x140003aef  mov     ecx, eax; this
0x140003af1  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140003af6  int     3; Trap to Debugger
0x140003af7  mov     ecx, 80070216h; this
0x140003afc  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140003b01  int     3; Trap to Debugger
0x140003b02  mov     ecx, eax; this
0x140003b04  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
