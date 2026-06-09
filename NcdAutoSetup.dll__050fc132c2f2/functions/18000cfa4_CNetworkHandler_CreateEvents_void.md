# CNetworkHandler::_CreateEvents(void)

- ea: `0x18000cfa4`
- end: `0x18000d08d`
- name: `?_CreateEvents@CNetworkHandler@@AEAAJXZ`
- size: `233`
- prototype: `__int64 __fastcall(CNetworkHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c218`

## callees

- `0x18000a644`
- `0x18000cfa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d03a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d03a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000cfeb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d009`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d027`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000cfeb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d009`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d027`

## pseudocode

```c
__int64 __fastcall CNetworkHandler::_CreateEvents(CNetworkHandler *this)
{
  HANDLE EventW; // rax
  signed int v3; // ebx
  signed int LastError; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  g_ahNetworkSizeCalculationCancelEvents = CreateEventW(0, 1, 0, 0);
  if ( g_ahNetworkSizeCalculationCancelEvents
    && (*(&g_ahNetworkSizeCalculationCancelEvents + 1) = CreateEventW(0, 1, 0, 0)) != 0
    && (EventW = CreateEventW(0, 1, 0, 0), (*((_QWORD *)this + 7) = EventW) != 0) )
  {
    v3 = 0;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000cfa4  mov     [rsp+arg_0], rbx
0x18000cfa9  push    rsi
0x18000cfaa  sub     rsp, 20h
0x18000cfae  mov     rbx, rcx
0x18000cfb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfb8  lea     rsi, WPP_GLOBAL_Control
0x18000cfbf  cmp     rcx, rsi
0x18000cfc2  jz      short loc_18000CFDF
0x18000cfc4  test    byte ptr [rcx+1Ch], 20h
0x18000cfc8  jz      short loc_18000CFDF
0x18000cfca  mov     rcx, [rcx+10h]
0x18000cfce  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000cfd5  mov     edx, 66h ; 'f'
0x18000cfda  call    WPP_SF_
0x18000cfdf  xor     r9d, r9d; lpName
0x18000cfe2  xor     r8d, r8d; bInitialState
0x18000cfe5  xor     ecx, ecx; lpEventAttributes
0x18000cfe7  lea     edx, [r9+1]; bManualReset
0x18000cfeb  call    cs:__imp_CreateEventW
0x18000cff1  mov     qword ptr cs:?g_ahNetworkSizeCalculationCancelEvents@@3PAPEAXA, rax; void * near * g_ahNetworkSizeCalculationCancelEvents
0x18000cff8  test    rax, rax
0x18000cffb  jz      short loc_18000D03A
0x18000cffd  xor     r9d, r9d; lpName
0x18000d000  xor     r8d, r8d; bInitialState
0x18000d003  xor     ecx, ecx; lpEventAttributes
0x18000d005  lea     edx, [r9+1]; bManualReset
0x18000d009  call    cs:__imp_CreateEventW
0x18000d00f  mov     qword ptr cs:?g_ahNetworkSizeCalculationCancelEvents@@3PAPEAXA+8, rax; void * near * g_ahNetworkSizeCalculationCancelEvents
0x18000d016  test    rax, rax
0x18000d019  jz      short loc_18000D03A
0x18000d01b  xor     r9d, r9d; lpName
0x18000d01e  xor     r8d, r8d; bInitialState
0x18000d021  xor     ecx, ecx; lpEventAttributes
0x18000d023  lea     edx, [r9+1]; bManualReset
0x18000d027  call    cs:__imp_CreateEventW
0x18000d02d  mov     [rbx+38h], rax
0x18000d031  test    rax, rax
0x18000d034  jz      short loc_18000D03A
0x18000d036  xor     ebx, ebx
0x18000d038  jmp     short loc_18000D059
0x18000d03a  call    cs:__imp_GetLastError
0x18000d040  mov     ebx, eax
0x18000d042  test    eax, eax
0x18000d044  jle     short loc_18000D04F
0x18000d046  movzx   ebx, ax
0x18000d049  or      ebx, 80070000h
0x18000d04f  test    ebx, ebx
0x18000d051  mov     eax, 80004005h
0x18000d056  cmovns  ebx, eax
0x18000d059  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d060  cmp     rcx, rsi
0x18000d063  jz      short loc_18000D080
0x18000d065  test    byte ptr [rcx+1Ch], 20h
0x18000d069  jz      short loc_18000D080
0x18000d06b  mov     rcx, [rcx+10h]
0x18000d06f  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000d076  mov     edx, 67h ; 'g'
0x18000d07b  call    WPP_SF_
0x18000d080  mov     eax, ebx
0x18000d082  mov     rbx, [rsp+28h+arg_0]
0x18000d087  add     rsp, 20h
0x18000d08b  pop     rsi
0x18000d08c  retn
```
