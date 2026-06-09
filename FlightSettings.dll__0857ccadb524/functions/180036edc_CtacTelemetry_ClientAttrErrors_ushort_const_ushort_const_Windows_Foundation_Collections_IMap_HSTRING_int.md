# CtacTelemetry::ClientAttrErrors(ushort const *,ushort const *,Windows::Foundation::Collections::IMap<HSTRING__ *,int> *)

- ea: `0x180036edc`
- end: `0x180036fc0`
- name: `?ClientAttrErrors@CtacTelemetry@@SAXPEBG0PEAU?$IMap@PEAUHSTRING__@@H@Collections@Foundation@Windows@@@Z`
- size: `228`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180032ba0`
- `0x180032e60`

## callees

- `0x180002718`
- `0x180033314`
- `0x180036edc`
- `0x180039100`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036f2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036f2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036f5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036f5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall CtacTelemetry::ClientAttrErrors(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT result; // eax
  const struct _tlgProvider_t *v7; // rax
  int v8; // ebx
  int v9; // r8d
  PCWSTR StringRawBuffer; // [rsp+40h] [rbp-20h] BYREF
  __int64 v11; // [rsp+48h] [rbp-18h] BYREF
  __int64 v12; // [rsp+50h] [rbp-10h] BYREF
  __int64 v13; // [rsp+58h] [rbp-8h] BYREF
  int v14; // [rsp+90h] [rbp+30h] BYREF
  HSTRING string; // [rsp+98h] [rbp+38h] BYREF

  v14 = 0;
  result = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a3 + 56LL))(a3, &v14);
  if ( result >= 0 && v14 )
  {
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    if ( (int)KvpEncoder::EncodeMapToJson<int>(&string, a3) >= 0 )
    {
      v7 = CtacTelemetry::Provider();
      v8 = (int)v7;
      if ( *(_DWORD *)v7 > 5u )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v11 = a2;
        v12 = a1;
        v13 = 1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v8,
          (unsigned int)&byte_1800FDEFF,
          v9,
          (unsigned int)&v13,
          (__int64)&v12,
          (__int64)&v11,
          (__int64)&StringRawBuffer);
      }
    }
    return WindowsDeleteString(string);
  }
  return result;
}

```

## disassembly

```asm
0x180036edc  mov     [rsp-18h+arg_0], rbx
0x180036ee1  push    rbp
0x180036ee2  push    rsi
0x180036ee3  push    rdi
0x180036ee4  mov     rbp, rsp
0x180036ee7  sub     rsp, 60h
0x180036eeb  mov     rbx, r8
0x180036eee  mov     rdi, rdx
0x180036ef1  mov     rsi, rcx
0x180036ef4  mov     [rbp+arg_10], 0
0x180036efb  mov     rax, [r8]
0x180036efe  lea     rdx, [rbp+arg_10]
0x180036f02  mov     rcx, r8
0x180036f05  mov     rax, [rax+38h]
0x180036f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f0e  test    eax, eax
0x180036f10  js      loc_180036FB0
0x180036f16  cmp     [rbp+arg_10], 0
0x180036f1a  jz      loc_180036FB0
0x180036f20  mov     [rbp+string], 0
0x180036f28  xor     ecx, ecx; string
0x180036f2a  call    cs:__imp_WindowsDeleteString
0x180036f30  mov     [rbp+string], 0
0x180036f38  mov     rdx, rbx
0x180036f3b  lea     rcx, [rbp+string]
0x180036f3f  call    ??$EncodeMapToJson@H@KvpEncoder@@SAJPEAPEAUHSTRING__@@PEAU?$IMap@PEAUHSTRING__@@H@Collections@Foundation@Windows@@@Z; KvpEncoder::EncodeMapToJson<int>(HSTRING__ * *,Windows::Foundation::Collections::IMap<HSTRING__ *,int> *)
0x180036f44  test    eax, eax
0x180036f46  js      short loc_180036FA6
0x180036f48  call    ?Provider@CtacTelemetry@@SAPEBU_tlgProvider_t@@XZ; CtacTelemetry::Provider(void)
0x180036f4d  mov     rbx, rax
0x180036f50  mov     ecx, [rax]
0x180036f52  cmp     ecx, 5
0x180036f55  jbe     short loc_180036FA6
0x180036f57  xor     edx, edx; length
0x180036f59  mov     rcx, [rbp+string]; string
0x180036f5d  call    cs:__imp_WindowsGetStringRawBuffer
0x180036f63  mov     [rbp+var_20], rax
0x180036f67  mov     [rbp+var_18], rdi
0x180036f6b  mov     [rbp+var_10], rsi
0x180036f6f  mov     [rbp+var_8], 1
0x180036f77  lea     rax, [rbp+var_20]
0x180036f7b  mov     [rsp+60h+var_30], rax
0x180036f80  lea     rax, [rbp+var_18]
0x180036f84  mov     [rsp+60h+var_38], rax
0x180036f89  lea     rax, [rbp+var_10]
0x180036f8d  mov     [rsp+60h+var_40], rax
0x180036f92  lea     r9, [rbp+var_8]
0x180036f96  lea     rdx, byte_1800FDEFF
0x180036f9d  mov     rcx, rbx
0x180036fa0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180036fa5  nop
0x180036fa6  mov     rcx, [rbp+string]; string
0x180036faa  call    cs:__imp_WindowsDeleteString
0x180036fb0  mov     rbx, [rsp+60h+arg_0]
0x180036fb8  add     rsp, 60h
0x180036fbc  pop     rdi
0x180036fbd  pop     rsi
0x180036fbe  pop     rbp
0x180036fbf  retn
```
