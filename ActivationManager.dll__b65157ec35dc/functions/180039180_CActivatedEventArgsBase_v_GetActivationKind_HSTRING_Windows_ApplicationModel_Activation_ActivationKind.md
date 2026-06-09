# CActivatedEventArgsBase::v_GetActivationKind(HSTRING__ *,Windows::ApplicationModel::Activation::ActivationKind *)

- ea: `0x180039180`
- end: `0x1800392e0`
- name: `?v_GetActivationKind@CActivatedEventArgsBase@@EEAAJPEAUHSTRING__@@PEAW4ActivationKind@Activation@ApplicationModel@Windows@@@Z`
- size: `352`
- prototype: `int(CActivatedEventArgsBase *__hidden this, HSTRING, enum Windows::ApplicationModel::Activation::ActivationKind *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180039180`
- `0x180048324`
- `0x1800960fc`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1800391e6`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1800391e6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180039290`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180039290`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800391c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800391fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039219`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039244`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003924e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800392c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800391c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800391fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039219`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039244`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003924e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800392c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003922a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003922a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180039211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180039211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800391b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800391d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003925d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800391b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800391d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003925d`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsBase::v_GetActivationKind(
        CActivatedEventArgsBase *this,
        HSTRING a2,
        enum Windows::ApplicationModel::Activation::ActivationKind *a3)
{
  const WCHAR *StringRawBuffer; // r12
  HSTRING v6; // rbx
  const wchar_t *v7; // rax
  size_t v8; // rax
  UINT32 v9; // esi
  HRESULT v10; // eax
  int v11; // edi
  unsigned int i; // esi
  __int64 v13; // rcx
  UINT32 length; // [rsp+70h] [rbp+40h] BYREF
  HSTRING string; // [rsp+78h] [rbp+48h] BYREF

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  *(_DWORD *)a3 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  WindowsDeleteString(0);
  v6 = 0;
  string = 0;
  length = 0;
  v7 = WindowsGetStringRawBuffer(a2, &length);
  v8 = wcscspn(v7, &c_szActionServiceDelimiter);
  v9 = v8;
  if ( v8 >= length )
  {
    WindowsDeleteString(string);
    string = 0;
    v10 = WindowsDuplicateString(a2, &string);
  }
  else
  {
    WindowsDeleteString(string);
    string = 0;
    v10 = WindowsSubstringWithSpecifiedLength(a2, 0, v9, &string);
  }
  v11 = v10;
  if ( v10 >= 0 )
  {
    v6 = string;
    string = 0;
  }
  WindowsDeleteString(0);
  WindowsDeleteString(string);
  if ( v11 >= 0 )
    StringRawBuffer = WindowsGetStringRawBuffer(v6, 0);
  for ( i = 0; i < 0x2E; ++i )
  {
    if ( CompareStringOrdinal(StringRawBuffer, -1, (&off_1800A24E0)[2 * i], -1, 0) == 2 )
    {
      *(_DWORD *)a3 = *((_DWORD *)&off_1800A24E0 + 4 * i + 2);
      goto LABEL_17;
    }
  }
  if ( !IsBackgroundExtensionContract(StringRawBuffer) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v13);
LABEL_17:
  WindowsDeleteString(v6);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180039180  mov     [rsp-28h+arg_0], rbx
0x180039185  mov     [rsp-28h+arg_8], rsi
0x18003918a  push    rbp
0x18003918b  push    rdi
0x18003918c  push    r12
0x18003918e  push    r14
0x180039190  push    r15
0x180039192  mov     rbp, rsp
0x180039195  sub     rsp, 30h
0x180039199  mov     r14, r8
0x18003919c  mov     rdi, rdx
0x18003919f  test    r8, r8
0x1800391a2  jnz     short loc_1800391A9
0x1800391a4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800391a9  xor     edx, edx; length
0x1800391ab  mov     dword ptr [r14], 0
0x1800391b2  mov     rcx, rdi; string
0x1800391b5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800391bb  xor     ecx, ecx; string
0x1800391bd  mov     r12, rax
0x1800391c0  call    cs:__imp_WindowsDeleteString
0x1800391c6  xor     ebx, ebx
0x1800391c8  lea     rdx, [rbp+length]; length
0x1800391cc  mov     rcx, rdi; string
0x1800391cf  mov     [rbp+string], rbx
0x1800391d3  mov     [rbp+length], ebx
0x1800391d6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800391dc  mov     rcx, rax; String
0x1800391df  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; Control
0x1800391e6  call    cs:__imp_wcscspn
0x1800391ec  mov     ecx, [rbp+length]
0x1800391ef  mov     rsi, rax
0x1800391f2  cmp     rax, rcx
0x1800391f5  mov     rcx, [rbp+string]; string
0x1800391f9  jnb     short loc_180039219
0x1800391fb  call    cs:__imp_WindowsDeleteString
0x180039201  mov     r8d, esi; length
0x180039204  mov     [rbp+string], rbx
0x180039208  lea     r9, [rbp+string]; newString
0x18003920c  xor     edx, edx; startIndex
0x18003920e  mov     rcx, rdi; string
0x180039211  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x180039217  jmp     short loc_180039230
0x180039219  call    cs:__imp_WindowsDeleteString
0x18003921f  lea     rdx, [rbp+string]; newString
0x180039223  mov     [rbp+string], rbx
0x180039227  mov     rcx, rdi; string
0x18003922a  call    cs:__imp_WindowsDuplicateString
0x180039230  mov     edi, eax
0x180039232  test    eax, eax
0x180039234  js      short loc_180039242
0x180039236  mov     rbx, [rbp+string]
0x18003923a  mov     [rbp+string], 0
0x180039242  xor     ecx, ecx; string
0x180039244  call    cs:__imp_WindowsDeleteString
0x18003924a  mov     rcx, [rbp+string]; string
0x18003924e  call    cs:__imp_WindowsDeleteString
0x180039254  test    edi, edi
0x180039256  js      short loc_180039266
0x180039258  xor     edx, edx; length
0x18003925a  mov     rcx, rbx; string
0x18003925d  call    cs:__imp_WindowsGetStringRawBuffer
0x180039263  mov     r12, rax
0x180039266  xor     esi, esi
0x180039268  lea     rax, off_1800A24E0; "Windows.Launch"
0x18003926f  mov     rcx, r12; unsigned __int16 *
0x180039272  cmp     esi, 2Eh ; '.'
0x180039275  jnb     short loc_1800392B0
0x180039277  or      r9d, 0FFFFFFFFh; cchCount2
0x18003927b  mov     r15d, esi
0x18003927e  add     r15, r15
0x180039281  mov     [rsp+30h+bIgnoreCase], 0; bIgnoreCase
0x180039289  or      edx, r9d; cchCount1
0x18003928c  mov     r8, [rax+r15*8]; lpString2
0x180039290  call    cs:__imp_CompareStringOrdinal
0x180039296  cmp     eax, 2
0x180039299  lea     rax, off_1800A24E0; "Windows.Launch"
0x1800392a0  jz      short loc_1800392A6
0x1800392a2  inc     esi
0x1800392a4  jmp     short loc_18003926F
0x1800392a6  mov     eax, [rax+r15*8+8]
0x1800392ab  mov     [r14], eax
0x1800392ae  jmp     short loc_1800392BE
0x1800392b0  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x1800392b5  test    al, al
0x1800392b7  jnz     short loc_1800392BE
0x1800392b9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800392be  mov     rcx, rbx; string
0x1800392c1  call    cs:__imp_WindowsDeleteString
0x1800392c7  mov     rbx, [rsp+30h+arg_0]
0x1800392cc  mov     eax, edi
0x1800392ce  mov     rsi, [rsp+30h+arg_8]
0x1800392d3  add     rsp, 30h
0x1800392d7  pop     r15
0x1800392d9  pop     r14
0x1800392db  pop     r12
0x1800392dd  pop     rdi
0x1800392de  pop     rbp
0x1800392df  retn
```
