# CActivatedEventArgsBase::v_GetActivationKind(HSTRING__ *,Windows::ApplicationModel::Activation::ActivationKind *)

- ea: `0x180055520`
- end: `0x1800555fb`
- name: `?v_GetActivationKind@CActivatedEventArgsBase@@EEAAJPEAUHSTRING__@@PEAW4ActivationKind@Activation@ApplicationModel@Windows@@@Z`
- size: `219`
- prototype: `int(CActivatedEventArgsBase *__hidden this, HSTRING, enum Windows::ApplicationModel::Activation::ActivationKind *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180054e24`
- `0x180054f18`
- `0x180055520`
- `0x180056c24`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055548`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055585`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055548`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055585`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800555e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800555e6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800555b8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800555b8`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsBase::v_GetActivationKind(
        CActivatedEventArgsBase *this,
        HSTRING a2,
        enum Windows::ApplicationModel::Activation::ActivationKind *a3)
{
  const WCHAR *StringRawBuffer; // rsi
  HSTRING *v6; // r8
  int v7; // ebp
  unsigned int i; // ebx
  __int64 v9; // rcx
  HSTRING string; // [rsp+80h] [rbp+18h] BYREF

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  *(_DWORD *)a3 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  WindowsDeleteString(0);
  string = 0;
  v7 = SplitActionAndServiceId(a2, &string, v6);
  if ( v7 >= 0 )
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  for ( i = 0; i < 0x2E; ++i )
  {
    if ( CompareStringOrdinal(StringRawBuffer, -1, (&off_180063FE0)[2 * i], -1, 0) == 2 )
    {
      *(_DWORD *)a3 = *((_DWORD *)&off_180063FE0 + 4 * i + 2);
      goto LABEL_12;
    }
  }
  if ( !IsBackgroundExtensionContract(StringRawBuffer) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
LABEL_12:
  WindowsDeleteString(string);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180055520  push    rbx
0x180055522  push    rbp
0x180055523  push    rsi
0x180055524  push    rdi
0x180055525  push    r12
0x180055527  push    r14
0x180055529  sub     rsp, 38h
0x18005552d  mov     rdi, r8
0x180055530  mov     rbx, rdx
0x180055533  test    r8, r8
0x180055536  jnz     short loc_18005553D
0x180055538  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pKind")
0x18005553d  xor     edx, edx; length
0x18005553f  mov     dword ptr [rdi], 0
0x180055545  mov     rcx, rbx; string
0x180055548  call    cs:__imp_WindowsGetStringRawBuffer
0x18005554e  xor     ecx, ecx; string
0x180055550  mov     rsi, rax
0x180055553  call    cs:__imp_WindowsDeleteString
0x180055559  lea     rdx, [rsp+68h+string]; HSTRING *
0x180055561  mov     [rsp+68h+string], 0
0x18005556d  mov     rcx, rbx; string
0x180055570  call    ?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z; SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x180055575  mov     ebp, eax
0x180055577  test    eax, eax
0x180055579  js      short loc_18005558E
0x18005557b  mov     rcx, [rsp+68h+string]; string
0x180055583  xor     edx, edx; length
0x180055585  call    cs:__imp_WindowsGetStringRawBuffer
0x18005558b  mov     rsi, rax
0x18005558e  xor     ebx, ebx
0x180055590  lea     r12, off_180063FE0; "Windows.Launch"
0x180055597  mov     rcx, rsi; unsigned __int16 *
0x18005559a  cmp     ebx, 2Eh ; '.'
0x18005559d  jnb     short loc_1800555D0
0x18005559f  or      r9d, 0FFFFFFFFh; cchCount2
0x1800555a3  mov     r14d, ebx
0x1800555a6  add     r14, r14
0x1800555a9  mov     [rsp+68h+bIgnoreCase], 0; bIgnoreCase
0x1800555b1  or      edx, r9d; cchCount1
0x1800555b4  mov     r8, [r12+r14*8]; lpString2
0x1800555b8  call    cs:__imp_CompareStringOrdinal
0x1800555be  cmp     eax, 2
0x1800555c1  jz      short loc_1800555C7
0x1800555c3  inc     ebx
0x1800555c5  jmp     short loc_180055597
0x1800555c7  mov     eax, [r12+r14*8+8]
0x1800555cc  mov     [rdi], eax
0x1800555ce  jmp     short loc_1800555DE
0x1800555d0  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x1800555d5  test    al, al
0x1800555d7  jnz     short loc_1800555DE
0x1800555d9  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "fFound || IsBackgroundExtensionContract(pszContractId)")
0x1800555de  mov     rcx, [rsp+68h+string]; string
0x1800555e6  call    cs:__imp_WindowsDeleteString
0x1800555ec  mov     eax, ebp
0x1800555ee  add     rsp, 38h
0x1800555f2  pop     r14
0x1800555f4  pop     r12
0x1800555f6  pop     rdi
0x1800555f7  pop     rsi
0x1800555f8  pop     rbp
0x1800555f9  pop     rbx
0x1800555fa  retn
```
