# I_ReaderMonitorSetReaderActionEvent

- ea: `0x18001b53c`
- end: `0x18001b64c`
- name: `I_ReaderMonitorSetReaderActionEvent`
- size: `272`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001ba4c`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x18001b53c`
- `0x18001cbdc`
- `0x18001cc6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b5b5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b5b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b5ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b5ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b58f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b58f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b5c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b5c1`

## pseudocode

```c
__int64 __fastcall I_ReaderMonitorSetReaderActionEvent(__int64 a1)
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
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v2 = ++*(_QWORD *)(a1 + 264);
  *(_QWORD *)(a1 + 120) = v2;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v4 = SetEvent(*(HANDLE *)(a1 + 88));
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
        14,
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
    WPP_SF_slI(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v7, v8, v4, v2);
  }
  return v4;
}

```

## disassembly

```asm
0x18001b53c  push    rbx
0x18001b53e  push    rsi
0x18001b53f  push    rdi
0x18001b540  push    r14
0x18001b542  sub     rsp, 38h
0x18001b546  xor     edx, edx
0x18001b548  mov     rdi, rcx
0x18001b54b  call    WppTraceIndent
0x18001b550  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b557  lea     r14, WPP_GLOBAL_Control
0x18001b55e  cmp     rcx, r14
0x18001b561  jz      short loc_18001B58B
0x18001b563  test    byte ptr [rcx+1Ch], 2
0x18001b567  jz      short loc_18001B58B
0x18001b569  cmp     byte ptr [rcx+19h], 5
0x18001b56d  jb      short loc_18001B58B
0x18001b56f  mov     r9, cs:WPP_pszIndent
0x18001b576  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b57d  mov     rcx, [rcx+10h]
0x18001b581  mov     edx, 0Dh
0x18001b586  call    WPP_SF_s
0x18001b58b  lea     rcx, [rdi+30h]; lpCriticalSection
0x18001b58f  call    cs:__imp_EnterCriticalSection
0x18001b595  inc     qword ptr [rdi+108h]
0x18001b59c  lea     rcx, [rdi+30h]; lpCriticalSection
0x18001b5a0  mov     rsi, [rdi+108h]
0x18001b5a7  mov     [rdi+78h], rsi
0x18001b5ab  call    cs:__imp_LeaveCriticalSection
0x18001b5b1  mov     rcx, [rdi+58h]; hEvent
0x18001b5b5  call    cs:__imp_SetEvent
0x18001b5bb  mov     ebx, eax
0x18001b5bd  test    eax, eax
0x18001b5bf  jnz     short loc_18001B607
0x18001b5c1  call    cs:__imp_GetLastError
0x18001b5c7  lea     edx, [rbx+2]
0x18001b5ca  mov     edi, eax
0x18001b5cc  call    WppTraceIndent
0x18001b5d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5d8  cmp     rcx, r14
0x18001b5db  jz      short loc_18001B607
0x18001b5dd  test    byte ptr [rcx+1Ch], 1
0x18001b5e1  jz      short loc_18001B607
0x18001b5e3  cmp     byte ptr [rcx+19h], 2
0x18001b5e7  jb      short loc_18001B607
0x18001b5e9  mov     r9, cs:WPP_pszIndent
0x18001b5f0  lea     edx, [rbx+0Eh]
0x18001b5f3  mov     rcx, [rcx+10h]
0x18001b5f7  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b5fe  mov     [rsp+58h+var_38], edi
0x18001b602  call    WPP_SF_sd
0x18001b607  mov     edx, 1
0x18001b60c  call    WppTraceIndent
0x18001b611  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b618  cmp     rcx, r14
0x18001b61b  jz      short loc_18001B640
0x18001b61d  test    byte ptr [rcx+1Ch], 2
0x18001b621  jz      short loc_18001B640
0x18001b623  cmp     byte ptr [rcx+19h], 5
0x18001b627  jb      short loc_18001B640
0x18001b629  mov     rcx, [rcx+10h]
0x18001b62d  mov     edx, 0Fh
0x18001b632  mov     [rsp+58h+var_30], rsi
0x18001b637  mov     [rsp+58h+var_38], ebx
0x18001b63b  call    WPP_SF_slI
0x18001b640  mov     eax, ebx
0x18001b642  add     rsp, 38h
0x18001b646  pop     r14
0x18001b648  pop     rdi
0x18001b649  pop     rsi
0x18001b64a  pop     rbx
0x18001b64b  retn
```
