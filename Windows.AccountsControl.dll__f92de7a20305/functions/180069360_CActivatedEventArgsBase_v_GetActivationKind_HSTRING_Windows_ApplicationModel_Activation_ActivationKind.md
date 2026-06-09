# CActivatedEventArgsBase::v_GetActivationKind(HSTRING__ *,Windows::ApplicationModel::Activation::ActivationKind *)

- ea: `0x180069360`
- end: `0x18006943b`
- name: `?v_GetActivationKind@CActivatedEventArgsBase@@EEAAJPEAUHSTRING__@@PEAW4ActivationKind@Activation@ApplicationModel@Windows@@@Z`
- size: `219`
- prototype: `int(CActivatedEventArgsBase *__hidden this, HSTRING, enum Windows::ApplicationModel::Activation::ActivationKind *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180068cc8`
- `0x180068dbc`
- `0x180069360`
- `0x180069444`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069393`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069426`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069393`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069426`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180069388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800693c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180069388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800693c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800693f8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800693f8`

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
    if ( CompareStringOrdinal(StringRawBuffer, -1, (&off_1800890E0)[2 * i], -1, 0) == 2 )
    {
      *(_DWORD *)a3 = *((_DWORD *)&off_1800890E0 + 4 * i + 2);
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
0x180069360  push    rbx
0x180069362  push    rbp
0x180069363  push    rsi
0x180069364  push    rdi
0x180069365  push    r12
0x180069367  push    r14
0x180069369  sub     rsp, 38h
0x18006936d  mov     rdi, r8
0x180069370  mov     rbx, rdx
0x180069373  test    r8, r8
0x180069376  jnz     short loc_18006937D
0x180069378  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006937d  xor     edx, edx; length
0x18006937f  mov     dword ptr [rdi], 0
0x180069385  mov     rcx, rbx; string
0x180069388  call    cs:__imp_WindowsGetStringRawBuffer
0x18006938e  xor     ecx, ecx; string
0x180069390  mov     rsi, rax
0x180069393  call    cs:__imp_WindowsDeleteString
0x180069399  lea     rdx, [rsp+68h+string]; HSTRING *
0x1800693a1  mov     [rsp+68h+string], 0
0x1800693ad  mov     rcx, rbx; string
0x1800693b0  call    ?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z; SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x1800693b5  mov     ebp, eax
0x1800693b7  test    eax, eax
0x1800693b9  js      short loc_1800693CE
0x1800693bb  mov     rcx, [rsp+68h+string]; string
0x1800693c3  xor     edx, edx; length
0x1800693c5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800693cb  mov     rsi, rax
0x1800693ce  xor     ebx, ebx
0x1800693d0  lea     r12, off_1800890E0; "Windows.Launch"
0x1800693d7  mov     rcx, rsi; String1
0x1800693da  cmp     ebx, 2Eh ; '.'
0x1800693dd  jnb     short loc_180069410
0x1800693df  or      r9d, 0FFFFFFFFh; cchCount2
0x1800693e3  mov     r14d, ebx
0x1800693e6  add     r14, r14
0x1800693e9  mov     [rsp+68h+bIgnoreCase], 0; bIgnoreCase
0x1800693f1  or      edx, r9d; cchCount1
0x1800693f4  mov     r8, [r12+r14*8]; lpString2
0x1800693f8  call    cs:__imp_CompareStringOrdinal
0x1800693fe  cmp     eax, 2
0x180069401  jz      short loc_180069407
0x180069403  inc     ebx
0x180069405  jmp     short loc_1800693D7
0x180069407  mov     eax, [r12+r14*8+8]
0x18006940c  mov     [rdi], eax
0x18006940e  jmp     short loc_18006941E
0x180069410  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x180069415  test    al, al
0x180069417  jnz     short loc_18006941E
0x180069419  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006941e  mov     rcx, [rsp+68h+string]; string
0x180069426  call    cs:__imp_WindowsDeleteString
0x18006942c  mov     eax, ebp
0x18006942e  add     rsp, 38h
0x180069432  pop     r14
0x180069434  pop     r12
0x180069436  pop     rdi
0x180069437  pop     rsi
0x180069438  pop     rbp
0x180069439  pop     rbx
0x18006943a  retn
```
