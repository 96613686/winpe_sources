# Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<bool>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,bool)

- ea: `0x140003b10`
- end: `0x140003c5e`
- name: `??$AddColumnToCoalescedEvent@_N@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBG_N@Z`
- size: `334`
- prototype: `__int64 __fastcall(Windows::Speech::Session::FlightDataRecorder *this, __int64 *, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400088c4`

## callees

- `0x140002600`
- `0x140003b10`
- `0x140005ea0`
- `0x140007870`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140003bc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140003bc2`

## pseudocode

```c
__int64 __fastcall Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<bool>(
        Windows::Speech::Session::FlightDataRecorder *this,
        __int64 *a2,
        __int64 a3,
        char a4)
{
  __int64 *v5; // rdi
  _QWORD *v7; // rcx
  int v8; // ebx
  _QWORD *v9; // rbx
  __int64 v10; // rsi
  __int64 v11; // r14
  HRESULT v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  __int64 v17; // rcx
  _QWORD *v19; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v20[3]; // [rsp+28h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF

  v5 = a2;
  v20[1] = a2;
  v7 = (_QWORD *)*a2;
  v19 = v7;
  if ( v7 )
    (*(void (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7);
  v20[2] = &v19;
  if ( v19 )
    v8 = Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(this);
  else
    v8 = -2147024809;
  v20[0] = 0;
  if ( v8 >= 0 )
  {
    LOBYTE(a2) = a4;
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD *))(**((_QWORD **)this + 10) + 64LL))(
           *((_QWORD *)this + 10),
           a2,
           v20);
    if ( v8 >= 0 )
    {
      v9 = v19;
      v10 = *v19;
      string = 0;
      v11 = v20[0];
      v12 = WindowsCreateStringReference(L"implicitStart", 0xDu, &hstringHeader, &string);
      if ( v12 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
        JUMPOUT(0x140003C5DLL);
      }
      v8 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64))(v10 + 56))(v9, string, v11);
    }
  }
  v15 = v20[0];
  if ( v20[0] )
  {
    v20[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
  }
  v17 = *v5;
  if ( *v5 )
  {
    *v5 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140003b10  push    rbp
0x140003b12  push    rbx
0x140003b13  push    rsi
0x140003b14  push    rdi
0x140003b15  push    r14
0x140003b17  mov     rbp, rsp
0x140003b1a  sub     rsp, 70h
0x140003b1e  mov     rax, cs:__security_cookie
0x140003b25  xor     rax, rsp
0x140003b28  mov     [rbp+var_10], rax
0x140003b2c  mov     r14b, r9b
0x140003b2f  mov     rdi, rdx
0x140003b32  mov     rsi, rcx
0x140003b35  mov     [rbp+var_40], rdx
0x140003b39  mov     rcx, [rdx]
0x140003b3c  mov     [rbp+var_50], rcx
0x140003b40  test    rcx, rcx
0x140003b43  jz      short loc_140003B52
0x140003b45  mov     rax, [rcx]
0x140003b48  mov     rax, [rax+8]
0x140003b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b51  nop
0x140003b52  lea     rax, [rbp+var_50]
0x140003b56  mov     [rbp+var_38], rax
0x140003b5a  cmp     [rbp+var_50], 0
0x140003b5f  jz      short loc_140003B6D
0x140003b61  mov     rcx, rsi; this
0x140003b64  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x140003b69  mov     ebx, eax
0x140003b6b  jmp     short loc_140003B72
0x140003b6d  mov     ebx, 80070057h
0x140003b72  mov     [rbp+var_48], 0
0x140003b7a  test    ebx, ebx
0x140003b7c  js      short loc_140003BE5
0x140003b7e  mov     rcx, [rsi+50h]
0x140003b82  mov     rax, [rcx]
0x140003b85  lea     r8, [rbp+var_48]
0x140003b89  mov     dl, r14b
0x140003b8c  mov     rax, [rax+40h]
0x140003b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b95  mov     ebx, eax
0x140003b97  test    eax, eax
0x140003b99  js      short loc_140003BE5
0x140003b9b  mov     rbx, [rbp+var_50]
0x140003b9f  mov     rsi, [rbx]
0x140003ba2  mov     [rbp+string], 0
0x140003baa  mov     r14, [rbp+var_48]
0x140003bae  lea     r9, [rbp+string]; string
0x140003bb2  lea     r8, [rbp+hstringHeader]; hstringHeader
0x140003bb6  mov     edx, 0Dh; length
0x140003bbb  lea     rcx, sourceString; "implicitStart"
0x140003bc2  call    cs:__imp_WindowsCreateStringReference
0x140003bc8  test    eax, eax
0x140003bca  js      loc_140003C56
0x140003bd0  mov     r8, r14
0x140003bd3  mov     rdx, [rbp+string]
0x140003bd7  mov     rcx, rbx
0x140003bda  mov     rax, [rsi+38h]
0x140003bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003be3  mov     ebx, eax
0x140003be5  mov     rcx, [rbp+var_48]
0x140003be9  test    rcx, rcx
0x140003bec  jz      short loc_140003C03
0x140003bee  mov     [rbp+var_48], 0
0x140003bf6  mov     rax, [rcx]
0x140003bf9  mov     rax, [rax+10h]
0x140003bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c02  nop
0x140003c03  mov     rcx, [rbp+var_50]
0x140003c07  test    rcx, rcx
0x140003c0a  jz      short loc_140003C21
0x140003c0c  mov     [rbp+var_50], 0
0x140003c14  mov     rax, [rcx]
0x140003c17  mov     rax, [rax+10h]
0x140003c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c20  nop
0x140003c21  mov     rcx, [rdi]
0x140003c24  test    rcx, rcx
0x140003c27  jz      short loc_140003C3D
0x140003c29  mov     qword ptr [rdi], 0
0x140003c30  mov     rax, [rcx]
0x140003c33  mov     rax, [rax+10h]
0x140003c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c3c  nop
0x140003c3d  mov     eax, ebx
0x140003c3f  mov     rcx, [rbp+var_10]
0x140003c43  xor     rcx, rsp; StackCookie
0x140003c46  call    __security_check_cookie
0x140003c4b  add     rsp, 70h
0x140003c4f  pop     r14
0x140003c51  pop     rdi
0x140003c52  pop     rsi
0x140003c53  pop     rbx
0x140003c54  pop     rbp
0x140003c55  retn
0x140003c56  mov     ecx, eax; this
0x140003c58  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
