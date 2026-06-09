# JsonHelper::GetValue(ushort const *,ushort * *)

- ea: `0x180090de0`
- end: `0x180090fe6`
- name: `?GetValue@JsonHelper@@UEAAJPEBGPEAPEAG@Z`
- size: `518`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180038984`
- `0x1800711c8`
- `0x180071a60`
- `0x1800787d4`
- `0x180078820`
- `0x180078c20`
- `0x18008fbdc`
- `0x180090de0`
- `0x1800923f8`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090e20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090fc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090e20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090fc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090ec0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090ec0`

## string_xrefs

- `0x180090f82`: `StringCchCopy failed!`
- `0x180090e84`: `m_spJsonObj->GetNamedString failed!`

## pseudocode

```c
__int64 __fastcall JsonHelper::GetValue(JsonHelper *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v6; // rax
  __int64 v7; // rdx
  int v8; // ebx
  __int64 v9; // r8
  int v10; // eax
  const unsigned __int16 *StringRawBuffer; // rbx
  unsigned __int16 *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned __int16 *v15; // rdi
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  int ActivityIdPrefix; // eax
  UINT32 length; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  const unsigned __int16 *v23; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v24[32]; // [rsp+48h] [rbp-28h] BYREF

  v3 = *((_QWORD *)this + 7);
  string = 0;
  length = 0;
  v23 = a2;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v3 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v24, &v23);
  v8 = v5(v3, *(_QWORD *)(v6 + 24), &string);
  if ( v8 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v12 = (unsigned __int16 *)operator new(saturated_mul(++length, 2u));
    v15 = v12;
    if ( v12 )
    {
      v8 = StringCchCopyW(v12, length, StringRawBuffer);
      if ( v8 >= 0 )
      {
        *a3 = v15;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v17, v18);
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
            ActivityIdPrefix,
            (__int64)"StringCchCopy failed!",
            v8);
        }
        operator delete(v15);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v13, v14);
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
          v16,
          (__int64)"WCHAR[]");
      }
      v8 = -2147024882;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v7, v9);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      v10,
      (__int64)"m_spJsonObj->GetNamedString failed!",
      v8);
  }
  WindowsDeleteString(string);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180090de0  mov     [rsp-18h+arg_18], rbx
0x180090de5  push    rbp
0x180090de6  push    rsi
0x180090de7  push    rdi
0x180090de8  mov     rbp, rsp
0x180090deb  sub     rsp, 70h
0x180090def  mov     rax, cs:__security_cookie
0x180090df6  xor     rax, rsp
0x180090df9  mov     [rbp+var_8], rax
0x180090dfd  mov     rdi, [rcx+38h]
0x180090e01  mov     rsi, r8
0x180090e04  mov     [rbp+string], 0
0x180090e0c  xor     ecx, ecx; string
0x180090e0e  mov     [rbp+length], 0
0x180090e15  mov     [rbp+var_30], rdx
0x180090e19  mov     rax, [rdi]
0x180090e1c  mov     rbx, [rax+50h]
0x180090e20  call    cs:__imp_WindowsDeleteString
0x180090e26  lea     rdx, [rbp+var_30]
0x180090e2a  mov     [rbp+string], 0
0x180090e32  lea     rcx, [rbp+var_28]
0x180090e36  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180090e3b  lea     r8, [rbp+string]
0x180090e3f  mov     rcx, rdi
0x180090e42  mov     rdx, [rax+18h]
0x180090e46  mov     rax, rbx
0x180090e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090e4e  mov     ebx, eax
0x180090e50  test    eax, eax
0x180090e52  jns     short loc_180090EB8
0x180090e54  mov     rax, cs:WPP_GLOBAL_Control
0x180090e5b  lea     rcx, WPP_GLOBAL_Control
0x180090e62  cmp     rax, rcx
0x180090e65  jz      loc_180090FBE
0x180090e6b  test    byte ptr [rax+1Ch], 8
0x180090e6f  jz      loc_180090FBE
0x180090e75  cmp     byte ptr [rax+19h], 2
0x180090e79  jb      loc_180090FBE
0x180090e7f  call    RdpX_GetActivityIdPrefix
0x180090e84  lea     rcx, aMSpjsonobjGetn; "m_spJsonObj->GetNamedString failed!"
0x180090e8b  mov     [rsp+70h+var_48], ebx
0x180090e8f  mov     [rsp+70h+var_50], rcx
0x180090e94  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180090e9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180090ea2  mov     edx, 22h ; '"'
0x180090ea7  mov     r9d, eax
0x180090eaa  mov     rcx, [rcx+10h]
0x180090eae  call    WPP_SF_DsD
0x180090eb3  jmp     loc_180090FBE
0x180090eb8  mov     rcx, [rbp+string]; string
0x180090ebc  lea     rdx, [rbp+length]; length
0x180090ec0  call    cs:__imp_WindowsGetStringRawBuffer
0x180090ec6  mov     ecx, [rbp+length]
0x180090ec9  mov     rbx, rax
0x180090ecc  inc     ecx
0x180090ece  mov     eax, 2
0x180090ed3  mov     edx, ecx
0x180090ed5  mov     [rbp+length], ecx
0x180090ed8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180090edf  mul     rdx
0x180090ee2  cmovb   rax, rcx
0x180090ee6  mov     rcx, rax; Size
0x180090ee9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180090eee  mov     rdi, rax
0x180090ef1  test    rax, rax
0x180090ef4  jnz     short loc_180090F4A
0x180090ef6  mov     rax, cs:WPP_GLOBAL_Control
0x180090efd  lea     rcx, WPP_GLOBAL_Control
0x180090f04  cmp     rax, rcx
0x180090f07  jz      short loc_180090F43
0x180090f09  test    byte ptr [rax+1Ch], 8
0x180090f0d  jz      short loc_180090F43
0x180090f0f  cmp     byte ptr [rax+19h], 2
0x180090f13  jb      short loc_180090F43
0x180090f15  call    RdpX_GetActivityIdPrefix
0x180090f1a  lea     rcx, aWchar; "WCHAR[]"
0x180090f21  mov     r9d, eax
0x180090f24  mov     [rsp+70h+var_50], rcx
0x180090f29  lea     edx, [rdi+23h]
0x180090f2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180090f33  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180090f3a  mov     rcx, [rcx+10h]
0x180090f3e  call    WPP_SF_Ds
0x180090f43  mov     ebx, 8007000Eh
0x180090f48  jmp     short loc_180090FBE
0x180090f4a  mov     edx, [rbp+length]; unsigned __int64
0x180090f4d  mov     r8, rbx; unsigned __int16 *
0x180090f50  mov     rcx, rdi; unsigned __int16 *
0x180090f53  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180090f58  mov     ebx, eax
0x180090f5a  test    eax, eax
0x180090f5c  jns     short loc_180090FBB
0x180090f5e  mov     rax, cs:WPP_GLOBAL_Control
0x180090f65  lea     rcx, WPP_GLOBAL_Control
0x180090f6c  cmp     rax, rcx
0x180090f6f  jz      short loc_180090FB1
0x180090f71  test    byte ptr [rax+1Ch], 8
0x180090f75  jz      short loc_180090FB1
0x180090f77  cmp     byte ptr [rax+19h], 2
0x180090f7b  jb      short loc_180090FB1
0x180090f7d  call    RdpX_GetActivityIdPrefix
0x180090f82  lea     rcx, aStringcchcopyF; "StringCchCopy failed!"
0x180090f89  mov     [rsp+70h+var_48], ebx
0x180090f8d  mov     [rsp+70h+var_50], rcx
0x180090f92  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180090f99  mov     rcx, cs:WPP_GLOBAL_Control
0x180090fa0  mov     edx, 24h ; '$'
0x180090fa5  mov     r9d, eax
0x180090fa8  mov     rcx, [rcx+10h]
0x180090fac  call    WPP_SF_DsD
0x180090fb1  mov     rcx, rdi; Block
0x180090fb4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180090fb9  jmp     short loc_180090FBE
0x180090fbb  mov     [rsi], rdi
0x180090fbe  mov     rcx, [rbp+string]; string
0x180090fc2  call    cs:__imp_WindowsDeleteString
0x180090fc8  mov     eax, ebx
0x180090fca  mov     rcx, [rbp+var_8]
0x180090fce  xor     rcx, rsp; StackCookie
0x180090fd1  call    __security_check_cookie
0x180090fd6  mov     rbx, [rsp+70h+arg_18]
0x180090fde  add     rsp, 70h
0x180090fe2  pop     rdi
0x180090fe3  pop     rsi
0x180090fe4  pop     rbp
0x180090fe5  retn
```
