# CActivatedEventArgsBase::v_GetActivationKind(HSTRING__ *,Windows::ApplicationModel::Activation::ActivationKind *)

- ea: `0x1800469c0`
- end: `0x180046a9b`
- name: `?v_GetActivationKind@CActivatedEventArgsBase@@EEAAJPEAUHSTRING__@@PEAW4ActivationKind@Activation@ApplicationModel@Windows@@@Z`
- size: `219`
- prototype: `int(CActivatedEventArgsBase *__hidden this, HSTRING, enum Windows::ApplicationModel::Activation::ActivationKind *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180044e64`
- `0x180046120`
- `0x1800469c0`
- `0x18004b5c4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046a58`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046a58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800469e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046a25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800469e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046a25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800469f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046a86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800469f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046a86`

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
    if ( CompareStringOrdinal(StringRawBuffer, -1, (&off_180051F70)[2 * i], -1, 0) == 2 )
    {
      *(_DWORD *)a3 = *((_DWORD *)&off_180051F70 + 4 * i + 2);
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
0x1800469c0  push    rbx
0x1800469c2  push    rbp
0x1800469c3  push    rsi
0x1800469c4  push    rdi
0x1800469c5  push    r12
0x1800469c7  push    r14
0x1800469c9  sub     rsp, 38h
0x1800469cd  mov     rdi, r8
0x1800469d0  mov     rbx, rdx
0x1800469d3  test    r8, r8
0x1800469d6  jnz     short loc_1800469DD
0x1800469d8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800469dd  xor     edx, edx; length
0x1800469df  mov     dword ptr [rdi], 0
0x1800469e5  mov     rcx, rbx; string
0x1800469e8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800469ee  xor     ecx, ecx; string
0x1800469f0  mov     rsi, rax
0x1800469f3  call    cs:__imp_WindowsDeleteString
0x1800469f9  lea     rdx, [rsp+68h+string]; HSTRING *
0x180046a01  mov     [rsp+68h+string], 0
0x180046a0d  mov     rcx, rbx; string
0x180046a10  call    ?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z; SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x180046a15  mov     ebp, eax
0x180046a17  test    eax, eax
0x180046a19  js      short loc_180046A2E
0x180046a1b  mov     rcx, [rsp+68h+string]; string
0x180046a23  xor     edx, edx; length
0x180046a25  call    cs:__imp_WindowsGetStringRawBuffer
0x180046a2b  mov     rsi, rax
0x180046a2e  xor     ebx, ebx
0x180046a30  lea     r12, off_180051F70; "Windows.Launch"
0x180046a37  mov     rcx, rsi; unsigned __int16 *
0x180046a3a  cmp     ebx, 2Eh ; '.'
0x180046a3d  jnb     short loc_180046A70
0x180046a3f  or      r9d, 0FFFFFFFFh; cchCount2
0x180046a43  mov     r14d, ebx
0x180046a46  add     r14, r14
0x180046a49  mov     [rsp+68h+bIgnoreCase], 0; bIgnoreCase
0x180046a51  or      edx, r9d; cchCount1
0x180046a54  mov     r8, [r12+r14*8]; lpString2
0x180046a58  call    cs:__imp_CompareStringOrdinal
0x180046a5e  cmp     eax, 2
0x180046a61  jz      short loc_180046A67
0x180046a63  inc     ebx
0x180046a65  jmp     short loc_180046A37
0x180046a67  mov     eax, [r12+r14*8+8]
0x180046a6c  mov     [rdi], eax
0x180046a6e  jmp     short loc_180046A7E
0x180046a70  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x180046a75  test    al, al
0x180046a77  jnz     short loc_180046A7E
0x180046a79  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180046a7e  mov     rcx, [rsp+68h+string]; string
0x180046a86  call    cs:__imp_WindowsDeleteString
0x180046a8c  mov     eax, ebp
0x180046a8e  add     rsp, 38h
0x180046a92  pop     r14
0x180046a94  pop     r12
0x180046a96  pop     rdi
0x180046a97  pop     rsi
0x180046a98  pop     rbp
0x180046a99  pop     rbx
0x180046a9a  retn
```
