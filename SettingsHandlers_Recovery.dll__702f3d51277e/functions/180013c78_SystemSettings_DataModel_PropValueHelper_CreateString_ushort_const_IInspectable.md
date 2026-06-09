# SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)

- ea: `0x180013c78`
- end: `0x180013d4c`
- name: `?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IInspectable **)`
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016bd0`
- `0x180016ea0`
- `0x1800171a0`
- `0x1800177a0`
- `0x180017de0`
- `0x180019c60`
- `0x180019fb0`

## callees

- `0x180002350`
- `0x180013c78`
- `0x18001d6bc`
- `0x180021a30`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013cd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013cd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::PropValueHelper::CreateString(
        const unsigned __int16 *a1,
        struct IInspectable **a2,
        unsigned int a3)
{
  unsigned __int64 v4; // rdx
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  HSTRING v8; // rdi
  __int64 result; // rax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h] BYREF

  if ( !a1 )
    a1 = &sourceString;
  string = 0;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  if ( v4 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v4, a3);
    __debugbreak();
  }
  if ( (int)v4 + 1 < (unsigned int)v4 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v4, a3);
    JUMPOUT(0x180013D4BLL);
  }
  v5 = WindowsCreateStringReference(a1, v4, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    __debugbreak();
  }
  v8 = string;
  result = SystemSettings::DataModel::PropValueHelper::_GetPVStatics();
  if ( (int)result < 0
    || (result = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValueStatics *, HSTRING, struct IInspectable **))(*(_QWORD *)SystemSettings::DataModel::PropValueHelper::_pPVStatics + 144LL))(
                   SystemSettings::DataModel::PropValueHelper::_pPVStatics,
                   v8,
                   a2),
        (int)result < 0) )
  {
    *a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180013c78  mov     [rsp+arg_10], rbx
0x180013c7d  mov     [rsp+arg_18], rsi
0x180013c82  push    rdi
0x180013c83  sub     rsp, 50h
0x180013c87  mov     rax, cs:__security_cookie
0x180013c8e  xor     rax, rsp
0x180013c91  mov     [rsp+58h+var_18], rax
0x180013c96  mov     rbx, rdx
0x180013c99  lea     rax, sourceString
0x180013ca0  xor     esi, esi
0x180013ca2  test    rcx, rcx
0x180013ca5  cmovz   rcx, rax; sourceString
0x180013ca9  mov     [rsp+58h+string], rsi
0x180013cae  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180013cb2  inc     rdx; int
0x180013cb5  cmp     [rcx+rdx*2], si
0x180013cb9  jnz     short loc_180013CB2
0x180013cbb  mov     eax, 0FFFFFFFFh
0x180013cc0  cmp     rdx, rax
0x180013cc3  ja      short loc_180013D36
0x180013cc5  lea     eax, [rdx+1]
0x180013cc8  cmp     eax, edx
0x180013cca  jb      short loc_180013D41
0x180013ccc  lea     r9, [rsp+58h+string]; string
0x180013cd1  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x180013cd6  call    cs:__imp_WindowsCreateStringReference
0x180013cdc  test    eax, eax
0x180013cde  js      short loc_180013D2E
0x180013ce0  mov     rdi, [rsp+58h+string]
0x180013ce5  call    ?_GetPVStatics@PropValueHelper@DataModel@SystemSettings@@CAJXZ; SystemSettings::DataModel::PropValueHelper::_GetPVStatics(void)
0x180013cea  test    eax, eax
0x180013cec  js      short loc_180013D0E
0x180013cee  mov     rcx, cs:?_pPVStatics@PropValueHelper@DataModel@SystemSettings@@0PEAUIPropertyValueStatics@Foundation@Windows@@EA; Windows::Foundation::IPropertyValueStatics * SystemSettings::DataModel::PropValueHelper::_pPVStatics
0x180013cf5  mov     rax, [rcx]
0x180013cf8  mov     r8, rbx
0x180013cfb  mov     rdx, rdi
0x180013cfe  mov     rax, [rax+90h]
0x180013d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d0a  test    eax, eax
0x180013d0c  jns     short loc_180013D11
0x180013d0e  mov     [rbx], rsi
0x180013d11  mov     rcx, [rsp+58h+var_18]
0x180013d16  xor     rcx, rsp; StackCookie
0x180013d19  call    __security_check_cookie
0x180013d1e  mov     rbx, [rsp+58h+arg_10]
0x180013d23  mov     rsi, [rsp+58h+arg_18]
0x180013d28  add     rsp, 50h
0x180013d2c  pop     rdi
0x180013d2d  retn
0x180013d2e  mov     ecx, eax; this
0x180013d30  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180013d35  int     3; Trap to Debugger
0x180013d36  mov     ecx, 80070216h; this
0x180013d3b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180013d40  int     3; Trap to Debugger
0x180013d41  mov     ecx, 80070216h; this
0x180013d46  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
