# CMessagingNode::_JsonObjectToString(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray> &,tagVARIANT *)

- ea: `0x1800b697c`
- end: `0x1800b6a8f`
- name: `?_JsonObjectToString@CMessagingNode@@AEBAJAEAV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEAUtagVARIANT@@@Z`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b6220`

## callees

- `0x180030bd0`
- `0x1800848b4`
- `0x1800b60b8`
- `0x1800b697c`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800b6a37`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b6a37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b6a2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b6a2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b69e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b6a1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b6a5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b69e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b6a1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b6a5b`

## pseudocode

```c
__int64 __fastcall CMessagingNode::_JsonObjectToString(
        __int64 a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, __int64),
        __int64 a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  int v9; // ecx
  HSTRING v10; // rcx
  const OLECHAR *StringRawBuffer; // rax
  BSTR v12; // rax
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  __int64 v15; // [rsp+38h] [rbp-18h] BYREF

  v15 = 0;
  v4 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(a2, (__int64)&v15);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = v15;
    string = 0;
    v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v8 = v7(v6, &string);
    v5 = v8;
    if ( v8 >= 0 )
    {
      v10 = string;
      *(_WORD *)a3 = 8;
      StringRawBuffer = WindowsGetStringRawBuffer(v10, 0);
      v12 = SysAllocString(StringRawBuffer);
      *(_QWORD *)(a3 + 8) = v12;
      if ( v12 )
      {
        WindowsDeleteString(string);
        v5 = 0;
        goto LABEL_9;
      }
      v5 = -2147024882;
      v9 = -2147024882;
    }
    else
    {
      v9 = v8;
    }
    Log_HREvent_99(v9);
    WindowsDeleteString(string);
LABEL_9:
    string = 0;
    goto LABEL_10;
  }
  Log_HREvent_99(v4);
LABEL_10:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return v5;
}

```

## disassembly

```asm
0x1800b697c  mov     [rsp-18h+arg_0], rbx
0x1800b6981  push    rbp
0x1800b6982  push    rsi
0x1800b6983  push    rdi
0x1800b6984  mov     rbp, rsp
0x1800b6987  sub     rsp, 50h
0x1800b698b  mov     rax, cs:__security_cookie
0x1800b6992  xor     rax, rsp
0x1800b6995  mov     [rbp+var_10], rax
0x1800b6999  mov     rcx, rdx
0x1800b699c  mov     [rbp+var_18], 0
0x1800b69a4  lea     rdx, [rbp+var_18]
0x1800b69a8  mov     rsi, r8
0x1800b69ab  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800b69b0  mov     ebx, eax
0x1800b69b2  test    eax, eax
0x1800b69b4  jns     short loc_1800B69CD
0x1800b69b6  mov     edx, 1
0x1800b69bb  mov     r9d, 253h
0x1800b69c1  mov     ecx, eax; int
0x1800b69c3  call    Log_HREvent_99
0x1800b69c8  jmp     loc_1800B6A6B
0x1800b69cd  mov     rdi, [rbp+var_18]
0x1800b69d1  xor     ecx, ecx; string
0x1800b69d3  mov     [rbp+string], 0
0x1800b69db  mov     rax, [rdi]
0x1800b69de  mov     rbx, [rax+38h]
0x1800b69e2  call    cs:__imp_WindowsDeleteString
0x1800b69e8  lea     rdx, [rbp+string]
0x1800b69ec  mov     [rbp+string], 0
0x1800b69f4  mov     rcx, rdi
0x1800b69f7  mov     rax, rbx
0x1800b69fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b69ff  mov     ebx, eax
0x1800b6a01  test    eax, eax
0x1800b6a03  jns     short loc_1800B6A23
0x1800b6a05  mov     edx, 1
0x1800b6a0a  mov     r9d, 256h
0x1800b6a10  mov     ecx, eax; int
0x1800b6a12  call    Log_HREvent_99
0x1800b6a17  mov     rcx, [rbp+string]; string
0x1800b6a1b  call    cs:__imp_WindowsDeleteString
0x1800b6a21  jmp     short loc_1800B6A63
0x1800b6a23  mov     rcx, [rbp+string]; string
0x1800b6a27  xor     edx, edx; length
0x1800b6a29  mov     word ptr [rsi], 8
0x1800b6a2e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b6a34  mov     rcx, rax; psz
0x1800b6a37  call    cs:__imp_SysAllocString
0x1800b6a3d  mov     [rsi+8], rax
0x1800b6a41  test    rax, rax
0x1800b6a44  jnz     short loc_1800B6A57
0x1800b6a46  mov     ebx, 8007000Eh
0x1800b6a4b  xor     edx, edx
0x1800b6a4d  mov     ecx, ebx
0x1800b6a4f  mov     r9d, 25Ah
0x1800b6a55  jmp     short loc_1800B6A12
0x1800b6a57  mov     rcx, [rbp+string]; string
0x1800b6a5b  call    cs:__imp_WindowsDeleteString
0x1800b6a61  xor     ebx, ebx
0x1800b6a63  mov     [rbp+string], 0
0x1800b6a6b  lea     rcx, [rbp+var_18]
0x1800b6a6f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b6a74  mov     eax, ebx
0x1800b6a76  mov     rcx, [rbp+var_10]
0x1800b6a7a  xor     rcx, rsp; StackCookie
0x1800b6a7d  call    __security_check_cookie
0x1800b6a82  mov     rbx, [rsp+50h+arg_0]
0x1800b6a87  add     rsp, 50h
0x1800b6a8b  pop     rdi
0x1800b6a8c  pop     rsi
0x1800b6a8d  pop     rbp
0x1800b6a8e  retn
```
