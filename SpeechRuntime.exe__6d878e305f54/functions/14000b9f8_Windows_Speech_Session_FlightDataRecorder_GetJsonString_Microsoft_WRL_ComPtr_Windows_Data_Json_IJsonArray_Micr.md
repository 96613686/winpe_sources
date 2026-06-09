# Windows::Speech::Session::FlightDataRecorder::GetJsonString(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>,Microsoft::WRL::Wrappers::HString *)

- ea: `0x14000b9f8`
- end: `0x14000bacf`
- name: `?GetJsonString@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEAVHString@Wrappers@67@@Z`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009f70`

## callees

- `0x14000b9f8`
- `0x14000c32c`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ba89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ba89`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Speech::Session::FlightDataRecorder::GetJsonString(
        __int64 a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, __int64 *),
        HSTRING *a3)
{
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  int v7; // ebx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rdi
  __int64 v11; // [rsp+60h] [rbp+30h] BYREF
  __int64 (__fastcall ****v12)(_QWORD, _QWORD, _QWORD); // [rsp+68h] [rbp+38h]
  __int64 v13; // [rsp+78h] [rbp+48h] BYREF

  v12 = (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))a2;
  v11 = a1;
  v13 = 0;
  v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))*a2;
  v6 = ***a2;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v13);
  v7 = v6(v5, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v13);
  if ( v7 >= 0 )
  {
    v8 = v13;
    v11 = v13;
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
      v8 = v11;
    }
    if ( a3 )
    {
      v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v8 + 56LL);
      WindowsDeleteString(*a3);
      *a3 = 0;
      v7 = v9(v8, a3);
    }
    else
    {
      v7 = -2147024809;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000b9f8  mov     [rsp-28h+arg_8], rdx
0x14000b9fd  mov     [rsp-28h+arg_0], rcx
0x14000ba02  push    rbp
0x14000ba03  push    rbx
0x14000ba04  push    rsi
0x14000ba05  push    rdi
0x14000ba06  push    r14
0x14000ba08  mov     rbp, rsp
0x14000ba0b  sub     rsp, 30h
0x14000ba0f  mov     rsi, r8
0x14000ba12  mov     r14, rdx
0x14000ba15  mov     [rbp+arg_18], 0
0x14000ba1d  mov     rdi, [rdx]
0x14000ba20  mov     rax, [rdi]
0x14000ba23  mov     rbx, [rax]
0x14000ba26  lea     rcx, [rbp+arg_18]
0x14000ba2a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000ba2f  lea     r8, [rbp+arg_18]
0x14000ba33  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x14000ba3a  mov     rcx, rdi
0x14000ba3d  mov     rax, rbx
0x14000ba40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba45  mov     ebx, eax
0x14000ba47  test    eax, eax
0x14000ba49  js      short loc_14000BAB0
0x14000ba4b  mov     rbx, [rbp+arg_18]
0x14000ba4f  mov     [rbp+arg_0], rbx
0x14000ba53  test    rbx, rbx
0x14000ba56  jz      short loc_14000BA6B
0x14000ba58  mov     rax, [rbx]
0x14000ba5b  mov     rcx, rbx
0x14000ba5e  mov     rax, [rax+8]
0x14000ba62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba67  mov     rbx, [rbp+arg_0]
0x14000ba6b  lea     rax, [rbp+arg_0]
0x14000ba6f  mov     [rbp+var_10], rax
0x14000ba73  test    rsi, rsi
0x14000ba76  jnz     short loc_14000BA7F
0x14000ba78  mov     ebx, 80070057h
0x14000ba7d  jmp     short loc_14000BAA6
0x14000ba7f  mov     rax, [rbx]
0x14000ba82  mov     rdi, [rax+38h]
0x14000ba86  mov     rcx, [rsi]; string
0x14000ba89  call    cs:__imp_WindowsDeleteString
0x14000ba8f  mov     qword ptr [rsi], 0
0x14000ba96  mov     rdx, rsi
0x14000ba99  mov     rcx, rbx
0x14000ba9c  mov     rax, rdi
0x14000ba9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000baa4  mov     ebx, eax
0x14000baa6  lea     rcx, [rbp+arg_0]
0x14000baaa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000baaf  nop
0x14000bab0  lea     rcx, [rbp+arg_18]
0x14000bab4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000bab9  nop
0x14000baba  mov     rcx, r14
0x14000babd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000bac2  mov     eax, ebx
0x14000bac4  add     rsp, 30h
0x14000bac8  pop     r14
0x14000baca  pop     rdi
0x14000bacb  pop     rsi
0x14000bacc  pop     rbx
0x14000bacd  pop     rbp
0x14000bace  retn
```
