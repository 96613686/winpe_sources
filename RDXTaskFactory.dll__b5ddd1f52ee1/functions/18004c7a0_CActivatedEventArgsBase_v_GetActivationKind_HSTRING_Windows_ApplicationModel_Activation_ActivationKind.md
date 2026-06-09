# CActivatedEventArgsBase::v_GetActivationKind(HSTRING__ *,Windows::ApplicationModel::Activation::ActivationKind *)

- ea: `0x18004c7a0`
- end: `0x18004c87b`
- name: `?v_GetActivationKind@CActivatedEventArgsBase@@EEAAJPEAUHSTRING__@@PEAW4ActivationKind@Activation@ApplicationModel@Windows@@@Z`
- size: `219`
- prototype: `int(CActivatedEventArgsBase *__hidden this, HSTRING, enum Windows::ApplicationModel::Activation::ActivationKind *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18004ac78`
- `0x18004bf34`
- `0x18004c7a0`
- `0x18004cde4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c838`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c838`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c7d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c866`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c7d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c866`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c7c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c805`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c7c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c805`

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
    if ( CompareStringOrdinal(StringRawBuffer, -1, (&off_180055600)[2 * i], -1, 0) == 2 )
    {
      *(_DWORD *)a3 = *((_DWORD *)&off_180055600 + 4 * i + 2);
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
0x18004c7a0  push    rbx
0x18004c7a2  push    rbp
0x18004c7a3  push    rsi
0x18004c7a4  push    rdi
0x18004c7a5  push    r12
0x18004c7a7  push    r14
0x18004c7a9  sub     rsp, 38h
0x18004c7ad  mov     rdi, r8
0x18004c7b0  mov     rbx, rdx
0x18004c7b3  test    r8, r8
0x18004c7b6  jnz     short loc_18004C7BD
0x18004c7b8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004c7bd  xor     edx, edx; length
0x18004c7bf  mov     dword ptr [rdi], 0
0x18004c7c5  mov     rcx, rbx; string
0x18004c7c8  call    cs:__imp_WindowsGetStringRawBuffer
0x18004c7ce  xor     ecx, ecx; string
0x18004c7d0  mov     rsi, rax
0x18004c7d3  call    cs:__imp_WindowsDeleteString
0x18004c7d9  lea     rdx, [rsp+68h+string]; HSTRING *
0x18004c7e1  mov     [rsp+68h+string], 0
0x18004c7ed  mov     rcx, rbx; string
0x18004c7f0  call    ?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z; SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x18004c7f5  mov     ebp, eax
0x18004c7f7  test    eax, eax
0x18004c7f9  js      short loc_18004C80E
0x18004c7fb  mov     rcx, [rsp+68h+string]; string
0x18004c803  xor     edx, edx; length
0x18004c805  call    cs:__imp_WindowsGetStringRawBuffer
0x18004c80b  mov     rsi, rax
0x18004c80e  xor     ebx, ebx
0x18004c810  lea     r12, off_180055600; "Windows.Launch"
0x18004c817  mov     rcx, rsi; unsigned __int16 *
0x18004c81a  cmp     ebx, 2Eh ; '.'
0x18004c81d  jnb     short loc_18004C850
0x18004c81f  or      r9d, 0FFFFFFFFh; cchCount2
0x18004c823  mov     r14d, ebx
0x18004c826  add     r14, r14
0x18004c829  mov     [rsp+68h+bIgnoreCase], 0; bIgnoreCase
0x18004c831  or      edx, r9d; cchCount1
0x18004c834  mov     r8, [r12+r14*8]; lpString2
0x18004c838  call    cs:__imp_CompareStringOrdinal
0x18004c83e  cmp     eax, 2
0x18004c841  jz      short loc_18004C847
0x18004c843  inc     ebx
0x18004c845  jmp     short loc_18004C817
0x18004c847  mov     eax, [r12+r14*8+8]
0x18004c84c  mov     [rdi], eax
0x18004c84e  jmp     short loc_18004C85E
0x18004c850  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x18004c855  test    al, al
0x18004c857  jnz     short loc_18004C85E
0x18004c859  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004c85e  mov     rcx, [rsp+68h+string]; string
0x18004c866  call    cs:__imp_WindowsDeleteString
0x18004c86c  mov     eax, ebp
0x18004c86e  add     rsp, 38h
0x18004c872  pop     r14
0x18004c874  pop     r12
0x18004c876  pop     rdi
0x18004c877  pop     rsi
0x18004c878  pop     rbp
0x18004c879  pop     rbx
0x18004c87a  retn
```
