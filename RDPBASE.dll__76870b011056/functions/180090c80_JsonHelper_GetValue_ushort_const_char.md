# JsonHelper::GetValue(ushort const *,char * *)

- ea: `0x180090c80`
- end: `0x180090dce`
- name: `?GetValue@JsonHelper@@UEAAJPEBGPEAPEAD@Z`
- size: `334`
- prototype: `int(JsonHelper *__hidden this, const unsigned __int16 *, char **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800711c8`
- `0x180071a60`
- `0x180078c20`
- `0x18008fbdc`
- `0x180090c80`
- `0x180091fa8`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090cbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090db1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090cbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090db1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090d3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090d3d`

## string_xrefs

- `0x180090d2a`: `m_spJsonObj->GetNamedString failed!`

## pseudocode

```c
__int64 __fastcall JsonHelper::GetValue(JsonHelper *this, const unsigned __int16 *a2, char **a3)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v6; // rax
  __int64 v7; // rdx
  int v8; // ebx
  __int64 v9; // r8
  int ActivityIdPrefix; // eax
  int v11; // edx
  const char *v12; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  JsonHelper *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  int *v18; // [rsp+20h] [rbp-68h]
  UINT32 length; // [rsp+30h] [rbp-58h] BYREF
  HSTRING string; // [rsp+38h] [rbp-50h] BYREF
  const unsigned __int16 *v21; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v22[32]; // [rsp+48h] [rbp-40h] BYREF

  v3 = *((_QWORD *)this + 7);
  string = 0;
  length = 0;
  v21 = a2;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v3 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v22, &v21);
  v8 = v5(v3, *(_QWORD *)(v6 + 24), &string);
  if ( v8 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v8 = JsonHelper::WideCharToUTF8(v14, StringRawBuffer, length, a3, v18);
    if ( v8 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v15, v16);
      v11 = 38;
      v12 = "WideCharToUTF8  failed!";
      goto LABEL_11;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v7, v9);
    v11 = 37;
    v12 = "m_spJsonObj->GetNamedString failed!";
LABEL_11:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      ActivityIdPrefix,
      (__int64)v12,
      v8);
  }
  WindowsDeleteString(string);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180090c80  push    rbx
0x180090c82  push    rsi
0x180090c83  push    rdi
0x180090c84  sub     rsp, 70h
0x180090c88  mov     rax, cs:__security_cookie
0x180090c8f  xor     rax, rsp
0x180090c92  mov     [rsp+88h+var_20], rax
0x180090c97  mov     rdi, [rcx+38h]
0x180090c9b  mov     rsi, r8
0x180090c9e  mov     [rsp+88h+string], 0
0x180090ca7  xor     ecx, ecx; string
0x180090ca9  mov     [rsp+88h+length], 0
0x180090cb1  mov     [rsp+88h+var_48], rdx
0x180090cb6  mov     rax, [rdi]
0x180090cb9  mov     rbx, [rax+50h]
0x180090cbd  call    cs:__imp_WindowsDeleteString
0x180090cc3  lea     rdx, [rsp+88h+var_48]
0x180090cc8  mov     [rsp+88h+string], 0
0x180090cd1  lea     rcx, [rsp+88h+var_40]
0x180090cd6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180090cdb  lea     r8, [rsp+88h+string]
0x180090ce0  mov     rcx, rdi
0x180090ce3  mov     rdx, [rax+18h]
0x180090ce7  mov     rax, rbx
0x180090cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090cef  mov     ebx, eax
0x180090cf1  test    eax, eax
0x180090cf3  jns     short loc_180090D33
0x180090cf5  mov     rax, cs:WPP_GLOBAL_Control
0x180090cfc  lea     rcx, WPP_GLOBAL_Control
0x180090d03  cmp     rax, rcx
0x180090d06  jz      loc_180090DAC
0x180090d0c  test    byte ptr [rax+1Ch], 8
0x180090d10  jz      loc_180090DAC
0x180090d16  cmp     byte ptr [rax+19h], 2
0x180090d1a  jb      loc_180090DAC
0x180090d20  call    RdpX_GetActivityIdPrefix
0x180090d25  mov     edx, 25h ; '%'
0x180090d2a  lea     rcx, aMSpjsonobjGetn; "m_spJsonObj->GetNamedString failed!"
0x180090d31  jmp     short loc_180090D89
0x180090d33  mov     rcx, [rsp+88h+string]; string
0x180090d38  lea     rdx, [rsp+88h+length]; length
0x180090d3d  call    cs:__imp_WindowsGetStringRawBuffer
0x180090d43  mov     r8d, [rsp+88h+length]; int
0x180090d48  mov     r9, rsi; char **
0x180090d4b  mov     rdx, rax; unsigned __int16 *
0x180090d4e  call    ?WideCharToUTF8@JsonHelper@@AEAAJPEBGHPEAPEADPEAH@Z; JsonHelper::WideCharToUTF8(ushort const *,int,char * *,int *)
0x180090d53  mov     ebx, eax
0x180090d55  test    eax, eax
0x180090d57  jns     short loc_180090DAC
0x180090d59  mov     rax, cs:WPP_GLOBAL_Control
0x180090d60  lea     rcx, WPP_GLOBAL_Control
0x180090d67  cmp     rax, rcx
0x180090d6a  jz      short loc_180090DAC
0x180090d6c  test    byte ptr [rax+1Ch], 8
0x180090d70  jz      short loc_180090DAC
0x180090d72  cmp     byte ptr [rax+19h], 2
0x180090d76  jb      short loc_180090DAC
0x180090d78  call    RdpX_GetActivityIdPrefix
0x180090d7d  mov     edx, 26h ; '&'
0x180090d82  lea     rcx, aWidechartoutf8_0; "WideCharToUTF8  failed!"
0x180090d89  mov     [rsp+88h+var_60], ebx
0x180090d8d  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180090d94  mov     [rsp+88h+var_68], rcx
0x180090d99  mov     r9d, eax
0x180090d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180090da3  mov     rcx, [rcx+10h]
0x180090da7  call    WPP_SF_DsD
0x180090dac  mov     rcx, [rsp+88h+string]; string
0x180090db1  call    cs:__imp_WindowsDeleteString
0x180090db7  mov     eax, ebx
0x180090db9  mov     rcx, [rsp+88h+var_20]
0x180090dbe  xor     rcx, rsp; StackCookie
0x180090dc1  call    __security_check_cookie
0x180090dc6  add     rsp, 70h
0x180090dca  pop     rdi
0x180090dcb  pop     rsi
0x180090dcc  pop     rbx
0x180090dcd  retn
```
