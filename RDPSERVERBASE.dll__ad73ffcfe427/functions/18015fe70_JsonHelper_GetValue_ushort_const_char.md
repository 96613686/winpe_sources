# JsonHelper::GetValue(ushort const *,char * *)

- ea: `0x18015fe70`
- end: `0x18015ffc0`
- name: `?GetValue@JsonHelper@@UEAAJPEBGPEAPEAD@Z`
- size: `336`
- prototype: `int(JsonHelper *__hidden this, const unsigned __int16 *, char **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180076090`
- `0x18007e9e0`
- `0x18015ede4`
- `0x18015fe70`
- `0x18016119c`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015ff10`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015ff69`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015ff10`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015ff69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015ff2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015ff2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015fead`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015ffa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015fead`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015ffa3`

## string_xrefs

- `0x18015ff1b`: `m_spJsonObj->GetNamedString failed!`

## pseudocode

```c
__int64 __fastcall JsonHelper::GetValue(JsonHelper *this, const unsigned __int16 *a2, char **a3)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v6; // rax
  __int64 v7; // rdx
  int v8; // ebx
  int ActivityIdPrefix; // eax
  int v10; // edx
  const char *v11; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  JsonHelper *v13; // rcx
  __int64 v14; // rdx
  int *v16; // [rsp+20h] [rbp-68h]
  UINT32 length; // [rsp+30h] [rbp-58h] BYREF
  HSTRING string; // [rsp+38h] [rbp-50h] BYREF
  const unsigned __int16 *v19; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v20[32]; // [rsp+48h] [rbp-40h] BYREF

  v3 = *((_QWORD *)this + 7);
  string = 0;
  length = 0;
  v19 = a2;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v3 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, &v19);
  v8 = v5(v3, *(_QWORD *)(v6 + 24), &string);
  if ( v8 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v8 = JsonHelper::WideCharToUTF8(v13, StringRawBuffer, length, a3, v16);
    if ( v8 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v14);
      v10 = 38;
      v11 = "WideCharToUTF8  failed!";
      goto LABEL_11;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v7);
    v10 = 37;
    v11 = "m_spJsonObj->GetNamedString failed!";
LABEL_11:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      ActivityIdPrefix,
      (__int64)v11,
      v8);
  }
  WindowsDeleteString(string);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18015fe70  push    rbx
0x18015fe72  push    rsi
0x18015fe73  push    rdi
0x18015fe74  sub     rsp, 70h
0x18015fe78  mov     rax, cs:__security_cookie
0x18015fe7f  xor     rax, rsp
0x18015fe82  mov     [rsp+88h+var_20], rax
0x18015fe87  mov     rdi, [rcx+38h]
0x18015fe8b  mov     rsi, r8
0x18015fe8e  mov     [rsp+88h+string], 0
0x18015fe97  xor     ecx, ecx; string
0x18015fe99  mov     [rsp+88h+length], 0
0x18015fea1  mov     [rsp+88h+var_48], rdx
0x18015fea6  mov     rax, [rdi]
0x18015fea9  mov     rbx, [rax+50h]
0x18015fead  call    cs:__imp_WindowsDeleteString
0x18015feb3  lea     rdx, [rsp+88h+var_48]
0x18015feb8  mov     [rsp+88h+string], 0
0x18015fec1  lea     rcx, [rsp+88h+var_40]
0x18015fec6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18015fecb  lea     r8, [rsp+88h+string]
0x18015fed0  mov     rcx, rdi
0x18015fed3  mov     rdx, [rax+18h]
0x18015fed7  mov     rax, rbx
0x18015feda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fedf  mov     ebx, eax
0x18015fee1  test    eax, eax
0x18015fee3  jns     short loc_18015FF24
0x18015fee5  mov     rax, cs:WPP_GLOBAL_Control
0x18015feec  lea     rcx, WPP_GLOBAL_Control
0x18015fef3  cmp     rax, rcx
0x18015fef6  jz      loc_18015FF9E
0x18015fefc  test    byte ptr [rax+1Ch], 8
0x18015ff00  jz      loc_18015FF9E
0x18015ff06  cmp     byte ptr [rax+19h], 2
0x18015ff0a  jb      loc_18015FF9E
0x18015ff10  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18015ff16  mov     edx, 25h ; '%'
0x18015ff1b  lea     rcx, aMSpjsonobjGetn; "m_spJsonObj->GetNamedString failed!"
0x18015ff22  jmp     short loc_18015FF7B
0x18015ff24  mov     rcx, [rsp+88h+string]; string
0x18015ff29  lea     rdx, [rsp+88h+length]; length
0x18015ff2e  call    cs:__imp_WindowsGetStringRawBuffer
0x18015ff34  mov     r8d, [rsp+88h+length]; int
0x18015ff39  mov     r9, rsi; char **
0x18015ff3c  mov     rdx, rax; unsigned __int16 *
0x18015ff3f  call    ?WideCharToUTF8@JsonHelper@@AEAAJPEBGHPEAPEADPEAH@Z; JsonHelper::WideCharToUTF8(ushort const *,int,char * *,int *)
0x18015ff44  mov     ebx, eax
0x18015ff46  test    eax, eax
0x18015ff48  jns     short loc_18015FF9E
0x18015ff4a  mov     rax, cs:WPP_GLOBAL_Control
0x18015ff51  lea     rcx, WPP_GLOBAL_Control
0x18015ff58  cmp     rax, rcx
0x18015ff5b  jz      short loc_18015FF9E
0x18015ff5d  test    byte ptr [rax+1Ch], 8
0x18015ff61  jz      short loc_18015FF9E
0x18015ff63  cmp     byte ptr [rax+19h], 2
0x18015ff67  jb      short loc_18015FF9E
0x18015ff69  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18015ff6f  mov     edx, 26h ; '&'
0x18015ff74  lea     rcx, aWidechartoutf8_0; "WideCharToUTF8  failed!"
0x18015ff7b  mov     [rsp+88h+var_60], ebx
0x18015ff7f  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18015ff86  mov     [rsp+88h+var_68], rcx
0x18015ff8b  mov     r9d, eax
0x18015ff8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18015ff95  mov     rcx, [rcx+10h]
0x18015ff99  call    WPP_SF_DsD
0x18015ff9e  mov     rcx, [rsp+88h+string]; string
0x18015ffa3  call    cs:__imp_WindowsDeleteString
0x18015ffa9  mov     eax, ebx
0x18015ffab  mov     rcx, [rsp+88h+var_20]
0x18015ffb0  xor     rcx, rsp; StackCookie
0x18015ffb3  call    __security_check_cookie
0x18015ffb8  add     rsp, 70h
0x18015ffbc  pop     rdi
0x18015ffbd  pop     rsi
0x18015ffbe  pop     rbx
0x18015ffbf  retn
```
