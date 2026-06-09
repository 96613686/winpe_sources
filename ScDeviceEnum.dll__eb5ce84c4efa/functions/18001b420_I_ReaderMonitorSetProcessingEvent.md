# I_ReaderMonitorSetProcessingEvent

- ea: `0x18001b420`
- end: `0x18001b533`
- name: `I_ReaderMonitorSetProcessingEvent`
- size: `275`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001b00c`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x18001b420`
- `0x18001cbdc`
- `0x18001cc6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b49c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b49c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b492`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b492`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b473`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4a8`

## pseudocode

```c
__int64 __fastcall I_ReaderMonitorSetProcessingEvent(__int64 a1)
{
  __int64 v2; // rsi
  PVOID v3; // rcx
  unsigned int v4; // ebx
  char LastError; // di
  __int64 v6; // rcx
  int v7; // r8d
  int v8; // r9d

  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v2 = ++*(_QWORD *)(a1 + 264);
  *(_QWORD *)(a1 + 128) = v2;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v4 = SetEvent(*(HANDLE *)(a1 + 104));
  if ( !v4 )
  {
    LastError = GetLastError();
    WppTraceIndent(v6, 2);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent,
        LastError);
    }
  }
  WppTraceIndent(v3, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_slI(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v7, v8, v4, v2);
  }
  return v4;
}

```

## disassembly

```asm
0x18001b420  push    rbx
0x18001b422  push    rsi
0x18001b423  push    rdi
0x18001b424  push    r14
0x18001b426  sub     rsp, 38h
0x18001b42a  xor     edx, edx
0x18001b42c  mov     rdi, rcx
0x18001b42f  call    WppTraceIndent
0x18001b434  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b43b  lea     r14, WPP_GLOBAL_Control
0x18001b442  cmp     rcx, r14
0x18001b445  jz      short loc_18001B46F
0x18001b447  test    byte ptr [rcx+1Ch], 2
0x18001b44b  jz      short loc_18001B46F
0x18001b44d  cmp     byte ptr [rcx+19h], 5
0x18001b451  jb      short loc_18001B46F
0x18001b453  mov     r9, cs:WPP_pszIndent
0x18001b45a  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b461  mov     rcx, [rcx+10h]
0x18001b465  mov     edx, 0Ah
0x18001b46a  call    WPP_SF_s
0x18001b46f  lea     rcx, [rdi+30h]; lpCriticalSection
0x18001b473  call    cs:__imp_EnterCriticalSection
0x18001b479  inc     qword ptr [rdi+108h]
0x18001b480  lea     rcx, [rdi+30h]; lpCriticalSection
0x18001b484  mov     rsi, [rdi+108h]
0x18001b48b  mov     [rdi+80h], rsi
0x18001b492  call    cs:__imp_LeaveCriticalSection
0x18001b498  mov     rcx, [rdi+68h]; hEvent
0x18001b49c  call    cs:__imp_SetEvent
0x18001b4a2  mov     ebx, eax
0x18001b4a4  test    eax, eax
0x18001b4a6  jnz     short loc_18001B4EE
0x18001b4a8  call    cs:__imp_GetLastError
0x18001b4ae  lea     edx, [rbx+2]
0x18001b4b1  mov     edi, eax
0x18001b4b3  call    WppTraceIndent
0x18001b4b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4bf  cmp     rcx, r14
0x18001b4c2  jz      short loc_18001B4EE
0x18001b4c4  test    byte ptr [rcx+1Ch], 1
0x18001b4c8  jz      short loc_18001B4EE
0x18001b4ca  cmp     byte ptr [rcx+19h], 2
0x18001b4ce  jb      short loc_18001B4EE
0x18001b4d0  mov     r9, cs:WPP_pszIndent
0x18001b4d7  lea     edx, [rbx+0Bh]
0x18001b4da  mov     rcx, [rcx+10h]
0x18001b4de  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b4e5  mov     [rsp+58h+var_38], edi
0x18001b4e9  call    WPP_SF_sd
0x18001b4ee  mov     edx, 1
0x18001b4f3  call    WppTraceIndent
0x18001b4f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4ff  cmp     rcx, r14
0x18001b502  jz      short loc_18001B527
0x18001b504  test    byte ptr [rcx+1Ch], 2
0x18001b508  jz      short loc_18001B527
0x18001b50a  cmp     byte ptr [rcx+19h], 5
0x18001b50e  jb      short loc_18001B527
0x18001b510  mov     rcx, [rcx+10h]
0x18001b514  mov     edx, 0Ch
0x18001b519  mov     [rsp+58h+var_30], rsi
0x18001b51e  mov     [rsp+58h+var_38], ebx
0x18001b522  call    WPP_SF_slI
0x18001b527  mov     eax, ebx
0x18001b529  add     rsp, 38h
0x18001b52d  pop     r14
0x18001b52f  pop     rdi
0x18001b530  pop     rsi
0x18001b531  pop     rbx
0x18001b532  retn
```
