# EnvironmentDefaultImpl::GetRegValue(HSTRING__ *,HSTRING__ * *)

- ea: `0x180028f50`
- end: `0x18002908e`
- name: `?GetRegValue@EnvironmentDefaultImpl@@UEAAJPEAUHSTRING__@@PEAPEAU2@@Z`
- size: `318`
- prototype: `__int64 __fastcall(EnvironmentDefaultImpl *__hidden this, HSTRING, HSTRING *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800153f8`
- `0x180018f24`
- `0x18001a540`
- `0x180028f50`
- `0x180029430`
- `0x1800d8c00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002903a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029064`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002903a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029064`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028f95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028f95`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180028fc9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180028fc9`

## string_xrefs

- `0x18002904b`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\environment.cpp`

## pseudocode

```c
__int64 __fastcall EnvironmentDefaultImpl::GetRegValue(EnvironmentDefaultImpl *this, HSTRING a2, HSTRING *a3)
{
  const WCHAR *StringRawBuffer; // rax
  LSTATUS ValueW; // eax
  bool v6; // sf
  unsigned __int64 v7; // rcx
  int v8; // ebx
  int pdwType; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 pvData[5464]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B28h] [rbp+2A28h]

  pcbData = 10922;
  string = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost",
             StringRawBuffer,
             2u,
             0,
             pvData,
             &pcbData);
  v6 = ValueW < 0;
  if ( ValueW )
  {
    pvData[0] = 0;
    if ( ValueW > 0 )
      v6 = 1;
  }
  if ( v6 )
    pvData[0] = 0;
  pcbData = 0;
  v7 = -1;
  do
    ++v7;
  while ( pvData[v7] );
  v8 = ULongLongToUInt(v7, &pcbData);
  if ( v8 < 0
    || (v8 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, pvData, pcbData),
        v8 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\environment.cpp",
      (const char *)(unsigned int)v8,
      pdwType);
    WindowsDeleteString(string);
    return (unsigned int)v8;
  }
  else
  {
    *a3 = string;
    string = 0;
    WindowsDeleteString(0);
    return 0;
  }
}

```

## disassembly

```asm
0x180028f50  mov     [rsp-8+arg_0], rbx
0x180028f55  push    rbp
0x180028f56  push    rsi
0x180028f57  push    rdi
0x180028f58  lea     rbp, [rsp-2A10h]
0x180028f60  mov     eax, 2B10h
0x180028f65  call    _alloca_probe
0x180028f6a  sub     rsp, rax
0x180028f6d  mov     rax, cs:__security_cookie
0x180028f74  xor     rax, rsp
0x180028f77  mov     [rbp+2A20h+var_20], rax
0x180028f7e  mov     rcx, rdx; string
0x180028f81  mov     [rsp+2B20h+var_2AE0], 2AAAh
0x180028f89  xor     esi, esi
0x180028f8b  xor     edx, edx; length
0x180028f8d  mov     [rsp+2B20h+string], rsi
0x180028f92  mov     rdi, r8
0x180028f95  call    cs:__imp_WindowsGetStringRawBuffer
0x180028f9b  lea     r9d, [rsi+2]; dwFlags
0x180028f9f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180028fa6  mov     r8, rax; lpValue
0x180028fa9  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180028fb0  lea     rax, [rsp+2B20h+var_2AE0]
0x180028fb5  mov     [rsp+2B20h+pcbData], rax; pcbData
0x180028fba  lea     rax, [rsp+2B20h+var_2AD0]
0x180028fbf  mov     [rsp+2B20h+pvData], rax; pvData
0x180028fc4  mov     [rsp+2B20h+pdwType], rsi; int
0x180028fc9  call    cs:__imp_RegGetValueW
0x180028fcf  test    eax, eax
0x180028fd1  jz      short loc_180028FE4
0x180028fd3  mov     [rsp+2B20h+var_2AD0], si
0x180028fd8  jle     short loc_180028FE4
0x180028fda  movzx   eax, ax
0x180028fdd  or      eax, 80070000h
0x180028fe2  test    eax, eax
0x180028fe4  jns     short loc_180028FEB
0x180028fe6  mov     [rsp+2B20h+var_2AD0], si
0x180028feb  mov     [rsp+2B20h+var_2AE0], esi
0x180028fef  lea     rax, [rsp+2B20h+var_2AD0]
0x180028ff4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180028ff8  inc     rcx; unsigned __int64
0x180028ffb  cmp     [rax+rcx*2], si
0x180028fff  jnz     short loc_180028FF8
0x180029001  lea     rdx, [rsp+2B20h+var_2AE0]; unsigned int *
0x180029006  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18002900b  mov     ebx, eax
0x18002900d  test    eax, eax
0x18002900f  js      short loc_180029044
0x180029011  mov     r8d, [rsp+2B20h+var_2AE0]; unsigned int
0x180029016  lea     rdx, [rsp+2B20h+var_2AD0]; unsigned __int16 *
0x18002901b  lea     rcx, [rsp+2B20h+string]; this
0x180029020  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180029025  mov     ebx, eax
0x180029027  test    eax, eax
0x180029029  js      short loc_180029044
0x18002902b  mov     rax, [rsp+2B20h+string]
0x180029030  xor     ecx, ecx; string
0x180029032  mov     [rdi], rax
0x180029035  mov     [rsp+2B20h+string], rsi
0x18002903a  call    cs:__imp_WindowsDeleteString
0x180029040  xor     eax, eax
0x180029042  jmp     short loc_18002906C
0x180029044  mov     rcx, [rbp+2A28h]; this
0x18002904b  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\cloudexperiencehost"...
0x180029052  mov     r9d, ebx; char *
0x180029055  mov     edx, 0BCh; void *
0x18002905a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002905f  mov     rcx, [rsp+2B20h+string]; string
0x180029064  call    cs:__imp_WindowsDeleteString
0x18002906a  mov     eax, ebx
0x18002906c  mov     rcx, [rbp+2A20h+var_20]
0x180029073  xor     rcx, rsp; StackCookie
0x180029076  call    __security_check_cookie
0x18002907b  mov     rbx, [rsp+2B20h+arg_0]
0x180029083  add     rsp, 2B10h
0x18002908a  pop     rdi
0x18002908b  pop     rsi
0x18002908c  pop     rbp
0x18002908d  retn
```
