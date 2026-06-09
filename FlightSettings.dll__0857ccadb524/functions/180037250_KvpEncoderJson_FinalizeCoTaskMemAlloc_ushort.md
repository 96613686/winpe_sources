# KvpEncoderJson::FinalizeCoTaskMemAlloc(ushort * *)

- ea: `0x180037250`
- end: `0x18003734f`
- name: `?FinalizeCoTaskMemAlloc@KvpEncoderJson@@UEAAJPEAPEAG@Z`
- size: `255`
- prototype: `__int64 __fastcall(KvpEncoderJson *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001ec78`
- `0x180037250`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037273`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003733e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037273`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003733e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800372d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800372d1`

## string_xrefs

- `0x18003729d`: `onecore\base\flighting\common\inc\KvpEncoder.h`
- `0x1800372f4`: `onecore\base\flighting\common\inc\KvpEncoder.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KvpEncoderJson::FinalizeCoTaskMemAlloc(KvpEncoderJson *this, unsigned __int16 **a2)
{
  __int64 (__fastcall *v4)(KvpEncoderJson *, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  PCWSTR StringRawBuffer; // rax
  int v8; // eax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v11; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+28h] [rbp-20h]
  __int64 v13; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  HSTRING string; // [rsp+70h] [rbp+28h] BYREF

  string = 0;
  v4 = *(__int64 (__fastcall **)(KvpEncoderJson *, HSTRING *))(*(_QWORD *)this + 40LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(this, &string);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v11 = 0;
    v12 = 0;
    v13 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
           &v11,
           StringRawBuffer,
           -1);
    v6 = v8;
    if ( v8 >= 0 )
    {
      v9 = v11;
      v11 = 0;
      v13 = 0;
      v12 = 0;
      *a2 = v9;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v11);
      v6 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
        (const char *)(unsigned int)v8,
        (int)v11);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
      (const char *)(unsigned int)v5,
      (int)v11);
  }
  WindowsDeleteString(string);
  return v6;
}

```

## disassembly

```asm
0x180037250  push    rbp
0x180037252  push    rbx
0x180037253  push    rsi
0x180037254  push    rdi
0x180037255  mov     rbp, rsp
0x180037258  sub     rsp, 48h
0x18003725c  mov     rsi, rdx
0x18003725f  mov     rdi, rcx
0x180037262  mov     [rbp+string], 0
0x18003726a  mov     rax, [rcx]
0x18003726d  mov     rbx, [rax+28h]
0x180037271  xor     ecx, ecx; string
0x180037273  call    cs:__imp_WindowsDeleteString
0x180037279  mov     [rbp+string], 0
0x180037281  lea     rdx, [rbp+string]
0x180037285  mov     rcx, rdi
0x180037288  mov     rax, rbx
0x18003728b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037290  mov     ebx, eax
0x180037292  test    eax, eax
0x180037294  jns     short loc_1800372B3
0x180037296  mov     rcx, [rbp+20h]; this
0x18003729a  mov     r9d, eax; char *
0x18003729d  lea     r8, aOnecoreBaseFli_23; "onecore\\base\\flighting\\common\\inc\\"...
0x1800372a4  mov     edx, 0E3h; void *
0x1800372a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800372ae  jmp     loc_18003733A
0x1800372b3  mov     [rbp+var_28], 0
0x1800372bb  mov     [rbp+var_20], 0
0x1800372c3  mov     [rbp+var_18], 0
0x1800372cb  xor     edx, edx; length
0x1800372cd  mov     rcx, [rbp+string]; string
0x1800372d1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800372d7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800372db  mov     rdx, rax
0x1800372de  lea     rcx, [rbp+var_28]
0x1800372e2  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800372e7  mov     ebx, eax
0x1800372e9  test    eax, eax
0x1800372eb  jns     short loc_180037310
0x1800372ed  mov     rcx, [rbp+20h]; this
0x1800372f1  mov     r9d, eax; char *
0x1800372f4  lea     r8, aOnecoreBaseFli_23; "onecore\\base\\flighting\\common\\inc\\"...
0x1800372fb  mov     edx, 0E7h; void *
0x180037300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037305  lea     rcx, [rbp+var_28]
0x180037309  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003730e  jmp     short loc_18003733A
0x180037310  mov     rax, [rbp+var_28]
0x180037314  mov     [rbp+var_28], 0
0x18003731c  mov     [rbp+var_18], 0
0x180037324  mov     [rbp+var_20], 0
0x18003732c  mov     [rsi], rax
0x18003732f  lea     rcx, [rbp+var_28]
0x180037333  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180037338  xor     ebx, ebx
0x18003733a  mov     rcx, [rbp+string]; string
0x18003733e  call    cs:__imp_WindowsDeleteString
0x180037344  mov     eax, ebx
0x180037346  add     rsp, 48h
0x18003734a  pop     rdi
0x18003734b  pop     rsi
0x18003734c  pop     rbx
0x18003734d  pop     rbp
0x18003734e  retn
```
