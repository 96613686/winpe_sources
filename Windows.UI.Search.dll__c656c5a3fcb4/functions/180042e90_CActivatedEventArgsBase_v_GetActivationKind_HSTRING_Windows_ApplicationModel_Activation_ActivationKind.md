# CActivatedEventArgsBase::v_GetActivationKind(HSTRING__ *,Windows::ApplicationModel::Activation::ActivationKind *)

- ea: `0x180042e90`
- end: `0x180042f6b`
- name: `?v_GetActivationKind@CActivatedEventArgsBase@@EEAAJPEAUHSTRING__@@PEAW4ActivationKind@Activation@ApplicationModel@Windows@@@Z`
- size: `219`
- prototype: `int(CActivatedEventArgsBase *__hidden this, HSTRING, enum Windows::ApplicationModel::Activation::ActivationKind *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180040664`
- `0x180042628`
- `0x180042e90`
- `0x18004c724`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042ec3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042f56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042ec3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042f56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042eb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042ef5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042eb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042ef5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180042f28`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180042f28`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsBase::v_GetActivationKind(
        CActivatedEventArgsBase *this,
        HSTRING a2,
        enum Windows::ApplicationModel::Activation::ActivationKind *a3)
{
  WCHAR *StringRawBuffer; // rsi
  HSTRING *v6; // r8
  int v7; // ebp
  unsigned int i; // ebx
  __int64 v9; // rcx
  HSTRING string; // [rsp+80h] [rbp+18h] BYREF

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  *(_DWORD *)a3 = 0;
  StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(a2, 0);
  WindowsDeleteString(0);
  string = 0;
  v7 = SplitActionAndServiceId(a2, &string, v6);
  if ( v7 >= 0 )
    StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
  for ( i = 0; i < 0x2E; ++i )
  {
    if ( CompareStringOrdinal(StringRawBuffer, -1, (&off_180083F30)[2 * i], -1, 0) == 2 )
    {
      *(_DWORD *)a3 = *((_DWORD *)&off_180083F30 + 4 * i + 2);
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
0x180042e90  push    rbx
0x180042e92  push    rbp
0x180042e93  push    rsi
0x180042e94  push    rdi
0x180042e95  push    r12
0x180042e97  push    r14
0x180042e99  sub     rsp, 38h
0x180042e9d  mov     rdi, r8
0x180042ea0  mov     rbx, rdx
0x180042ea3  test    r8, r8
0x180042ea6  jnz     short loc_180042EAD
0x180042ea8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180042ead  xor     edx, edx; length
0x180042eaf  mov     dword ptr [rdi], 0
0x180042eb5  mov     rcx, rbx; string
0x180042eb8  call    cs:__imp_WindowsGetStringRawBuffer
0x180042ebe  xor     ecx, ecx; string
0x180042ec0  mov     rsi, rax
0x180042ec3  call    cs:__imp_WindowsDeleteString
0x180042ec9  lea     rdx, [rsp+68h+string]; HSTRING *
0x180042ed1  mov     [rsp+68h+string], 0
0x180042edd  mov     rcx, rbx; string
0x180042ee0  call    ?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z; SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x180042ee5  mov     ebp, eax
0x180042ee7  test    eax, eax
0x180042ee9  js      short loc_180042EFE
0x180042eeb  mov     rcx, [rsp+68h+string]; string
0x180042ef3  xor     edx, edx; length
0x180042ef5  call    cs:__imp_WindowsGetStringRawBuffer
0x180042efb  mov     rsi, rax
0x180042efe  xor     ebx, ebx
0x180042f00  lea     r12, off_180083F30; "Windows.Launch"
0x180042f07  mov     rcx, rsi; String1
0x180042f0a  cmp     ebx, 2Eh ; '.'
0x180042f0d  jnb     short loc_180042F40
0x180042f0f  or      r9d, 0FFFFFFFFh; cchCount2
0x180042f13  mov     r14d, ebx
0x180042f16  add     r14, r14
0x180042f19  mov     [rsp+68h+bIgnoreCase], 0; bIgnoreCase
0x180042f21  or      edx, r9d; cchCount1
0x180042f24  mov     r8, [r12+r14*8]; lpString2
0x180042f28  call    cs:__imp_CompareStringOrdinal
0x180042f2e  cmp     eax, 2
0x180042f31  jz      short loc_180042F37
0x180042f33  inc     ebx
0x180042f35  jmp     short loc_180042F07
0x180042f37  mov     eax, [r12+r14*8+8]
0x180042f3c  mov     [rdi], eax
0x180042f3e  jmp     short loc_180042F4E
0x180042f40  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x180042f45  test    al, al
0x180042f47  jnz     short loc_180042F4E
0x180042f49  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180042f4e  mov     rcx, [rsp+68h+string]; string
0x180042f56  call    cs:__imp_WindowsDeleteString
0x180042f5c  mov     eax, ebp
0x180042f5e  add     rsp, 38h
0x180042f62  pop     r14
0x180042f64  pop     r12
0x180042f66  pop     rdi
0x180042f67  pop     rsi
0x180042f68  pop     rbp
0x180042f69  pop     rbx
0x180042f6a  retn
```
