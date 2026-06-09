# AuthHostWebInstance::UpdateBrokerLogo(void)

- ea: `0x14000bb4c`
- end: `0x14000bd1f`
- name: `?UpdateBrokerLogo@AuthHostWebInstance@@AEAAXXZ`
- size: `467`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140005940`
- `0x14000a4b0`
- `0x14000b6f0`

## callees

- `0x140002c98`
- `0x140008b30`
- `0x14000a858`
- `0x14000b630`
- `0x14000bb4c`
- `0x14000cddc`
- `0x14001189c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14000bbef`
- `msvcrt!_wcsicmp` at `0x14000bbef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000bb74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000bcd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000bb74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000bcd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000bcb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000bcb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000bca0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000bca0`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x14000bc04`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x14000bc04`

## string_xrefs

- `0x14000bbfd`: `AuthHost_DownloadComplete`

## pseudocode

```c
void __fastcall AuthHostWebInstance::UpdateBrokerLogo(HSTRING *this)
{
  Windows::Internal::String *v1; // rsi
  PCWSTR StringRawBuffer; // rax
  int v4; // r14d
  const wchar_t *v5; // rbx
  const wchar_t *v6; // rdx
  UINT v7; // eax
  const WCHAR *v8; // rcx
  int v9; // eax
  const WCHAR *v10; // rcx
  unsigned __int64 v11; // rdx
  HSTRING v12; // rcx
  PCWSTR v13; // rax
  struct _GUID v14; // [rsp+30h] [rbp-10h] BYREF
  HSTRING string; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int8 *v16; // [rsp+78h] [rbp+38h] BYREF

  v1 = (Windows::Internal::String *)(this + 60);
  StringRawBuffer = WindowsGetStringRawBuffer(this[60], 0);
  v4 = 1;
  v5 = StringRawBuffer;
  if ( StringRawBuffer )
    v5 = (const wchar_t *)(-(__int64)(*StringRawBuffer != 0) & (unsigned __int64)StringRawBuffer);
  v6 = (const wchar_t *)this[25];
  if ( !v6 )
    goto LABEL_4;
  if ( v5 && !_wcsicmp(v5, v6) )
    goto LABEL_25;
  v7 = RegisterWindowMessageW(L"AuthHost_DownloadComplete");
  v8 = (const WCHAR *)this[25];
  v16 = 0;
  LODWORD(string) = 0;
  if ( (int)GetWebDialogMetaTagLogoImage(v8, v7, &v16, (unsigned int *)&string) < 0 )
  {
LABEL_4:
    if ( v5 )
    {
      Windows::Internal::String::Release(v1);
      v14 = GUID_NULL;
      AuthHostWebInstance::OnLogoDownloaded((AuthHostWebInstance *)this, 0, 0, &v14, 0, 0);
      goto LABEL_20;
    }
LABEL_25:
    v4 = 0;
    goto LABEL_20;
  }
  v9 = AuthHostWebInstance::DecodeAndMarshalImage((AuthHostWebInstance *)this, v16, (unsigned int)string);
  if ( v9 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      28,
      &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids,
      (unsigned int)v9);
  }
  v10 = (const WCHAR *)this[25];
  if ( v10 )
  {
    string = 0;
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    if ( v11 <= 0xFFFFFFFF && WindowsCreateString(v10, v11, &string) >= 0 )
    {
      v12 = *(HSTRING *)v1;
      *(_QWORD *)v1 = string;
      WindowsDeleteString(v12);
    }
  }
LABEL_20:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    v13 = WindowsGetStringRawBuffer(*(HSTRING *)v1, 0);
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      29,
      (unsigned int)&WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids,
      v4,
      (__int64)v13);
  }
}

```

## disassembly

```asm
0x14000bb4c  mov     [rsp-28h+arg_10], rbx
0x14000bb51  mov     [rsp-28h+arg_18], rsi
0x14000bb56  push    rbp
0x14000bb57  push    rdi
0x14000bb58  push    r12
0x14000bb5a  push    r14
0x14000bb5c  push    r15
0x14000bb5e  mov     rbp, rsp
0x14000bb61  sub     rsp, 40h
0x14000bb65  lea     rsi, [rcx+1E0h]
0x14000bb6c  mov     rdi, rcx
0x14000bb6f  mov     rcx, [rsi]; string
0x14000bb72  xor     edx, edx; length
0x14000bb74  call    cs:__imp_WindowsGetStringRawBuffer
0x14000bb7a  xor     r15d, r15d
0x14000bb7d  mov     r14d, 1
0x14000bb83  mov     rbx, rax
0x14000bb86  test    rax, rax
0x14000bb89  jz      short loc_14000BB97
0x14000bb8b  movzx   edx, word ptr [rax]
0x14000bb8e  neg     dx
0x14000bb91  sbb     rcx, rcx
0x14000bb94  and     rbx, rcx
0x14000bb97  mov     rdx, [rdi+0C8h]; String2
0x14000bb9e  lea     r12, WPP_GLOBAL_Control
0x14000bba5  test    rdx, rdx
0x14000bba8  jnz     short loc_14000BBE7
0x14000bbaa  test    rbx, rbx
0x14000bbad  jz      loc_14000BD1A
0x14000bbb3  mov     rcx, rsi; this
0x14000bbb6  call    ?Release@String@Internal@Windows@@QEAAXXZ; Windows::Internal::String::Release(void)
0x14000bbbb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000bbc2  mov     [rsp+40h+var_18], r15; struct Windows::Storage::Streams::IBuffer *
0x14000bbc7  lea     r9, [rbp+var_10]; struct _GUID *
0x14000bbcb  xor     r8d, r8d; unsigned int
0x14000bbce  mov     [rsp+40h+var_20], r15d; unsigned int
0x14000bbd3  xor     edx, edx; unsigned int
0x14000bbd5  mov     rcx, rdi; this
0x14000bbd8  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x14000bbdd  call    ?OnLogoDownloaded@AuthHostWebInstance@@AEAAJIIU_GUID@@IPEAUIBuffer@Streams@Storage@Windows@@@Z; AuthHostWebInstance::OnLogoDownloaded(uint,uint,_GUID,uint,Windows::Storage::Streams::IBuffer *)
0x14000bbe2  jmp     loc_14000BCBA
0x14000bbe7  test    rbx, rbx
0x14000bbea  jz      short loc_14000BBFD
0x14000bbec  mov     rcx, rbx; String1
0x14000bbef  call    cs:__imp__wcsicmp
0x14000bbf5  test    eax, eax
0x14000bbf7  jz      loc_14000BD1A
0x14000bbfd  lea     rcx, aAuthhostDownlo; "AuthHost_DownloadComplete"
0x14000bc04  call    cs:__imp_RegisterWindowMessageW
0x14000bc0a  mov     rcx, [rdi+0C8h]; psz
0x14000bc11  lea     r9, [rbp+string]; unsigned int *
0x14000bc15  mov     edx, eax; unsigned int
0x14000bc17  mov     [rbp+arg_8], r15
0x14000bc1b  lea     r8, [rbp+arg_8]; unsigned __int8 **
0x14000bc1f  mov     dword ptr [rbp+string], r15d
0x14000bc23  call    ?GetWebDialogMetaTagLogoImage@@YAJPEBGIPEAPEAEPEAK@Z; GetWebDialogMetaTagLogoImage(ushort const *,uint,uchar * *,ulong *)
0x14000bc28  test    eax, eax
0x14000bc2a  js      loc_14000BBAA
0x14000bc30  mov     r8d, dword ptr [rbp+string]; unsigned int
0x14000bc34  mov     rcx, rdi; this
0x14000bc37  mov     rdx, [rbp+arg_8]; unsigned __int8 *
0x14000bc3b  call    ?DecodeAndMarshalImage@AuthHostWebInstance@@AEAAJPEAEI@Z; AuthHostWebInstance::DecodeAndMarshalImage(uchar *,uint)
0x14000bc40  test    eax, eax
0x14000bc42  jns     short loc_14000BC74
0x14000bc44  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc4b  cmp     rcx, r12
0x14000bc4e  jz      short loc_14000BC74
0x14000bc50  test    byte ptr [rcx+44h], 4
0x14000bc54  jz      short loc_14000BC74
0x14000bc56  cmp     byte ptr [rcx+41h], 2
0x14000bc5a  jb      short loc_14000BC74
0x14000bc5c  mov     rcx, [rcx+38h]
0x14000bc60  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000bc67  mov     edx, 1Ch
0x14000bc6c  mov     r9d, eax
0x14000bc6f  call    WPP_SF_d
0x14000bc74  mov     rcx, [rdi+0C8h]; sourceString
0x14000bc7b  test    rcx, rcx
0x14000bc7e  jz      short loc_14000BCBA
0x14000bc80  mov     [rbp+string], r15
0x14000bc84  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000bc88  inc     rdx; length
0x14000bc8b  cmp     [rcx+rdx*2], r15w
0x14000bc90  jnz     short loc_14000BC88
0x14000bc92  mov     eax, 0FFFFFFFFh
0x14000bc97  cmp     rdx, rax
0x14000bc9a  ja      short loc_14000BCBA
0x14000bc9c  lea     r8, [rbp+string]; string
0x14000bca0  call    cs:__imp_WindowsCreateString
0x14000bca6  test    eax, eax
0x14000bca8  js      short loc_14000BCBA
0x14000bcaa  mov     rax, [rbp+string]
0x14000bcae  mov     rcx, [rsi]; string
0x14000bcb1  mov     [rsi], rax
0x14000bcb4  call    cs:__imp_WindowsDeleteString
0x14000bcba  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bcc1  cmp     rcx, r12
0x14000bcc4  jz      short loc_14000BD01
0x14000bcc6  test    byte ptr [rcx+44h], 4
0x14000bcca  jz      short loc_14000BD01
0x14000bccc  cmp     byte ptr [rcx+41h], 5
0x14000bcd0  jb      short loc_14000BD01
0x14000bcd2  mov     rcx, [rsi]; string
0x14000bcd5  xor     edx, edx; length
0x14000bcd7  call    cs:__imp_WindowsGetStringRawBuffer
0x14000bcdd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bce4  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000bceb  mov     edx, 1Dh
0x14000bcf0  mov     qword ptr [rsp+40h+var_20], rax
0x14000bcf5  mov     r9d, r14d
0x14000bcf8  mov     rcx, [rcx+38h]
0x14000bcfc  call    WPP_SF_dS
0x14000bd01  lea     r11, [rsp+40h+var_s0]
0x14000bd06  mov     rbx, [r11+40h]
0x14000bd0a  mov     rsi, [r11+48h]
0x14000bd0e  mov     rsp, r11
0x14000bd11  pop     r15
0x14000bd13  pop     r14
0x14000bd15  pop     r12
0x14000bd17  pop     rdi
0x14000bd18  pop     rbp
0x14000bd19  retn
0x14000bd1a  mov     r14d, r15d
0x14000bd1d  jmp     short loc_14000BCBA
```
