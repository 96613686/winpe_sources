# I_ReaderMonitorInitializeLocalWorkerState

- ea: `0x18001b284`
- end: `0x18001b41a`
- name: `I_ReaderMonitorInitializeLocalWorkerState`
- size: `406`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ba4c`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x18001b284`
- `0x18001cc6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b388`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b3a4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b388`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b3a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b362`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001b350`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001b350`

## pseudocode

```c
__int64 __fastcall I_ReaderMonitorInitializeLocalWorkerState(__int64 a1)
{
  PVOID v2; // rcx
  DWORD LastError; // edi
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  HANDLE EventW; // rax
  HANDLE v6; // rax

  WppTraceIndent(a1, 0);
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( a1 )
  {
    *(_DWORD *)(a1 + 272) = 3;
    *(_QWORD *)(a1 + 280) = 0;
    *(_QWORD *)(a1 + 288) = 0;
    *(_QWORD *)(a1 + 296) = 0;
    *(_QWORD *)(a1 + 304) = 0;
    *(_QWORD *)(a1 + 312) = 0;
    *(_QWORD *)(a1 + 320) = 0;
    *(_DWORD *)(a1 + 328) = 0;
    *(_DWORD *)(a1 + 332) = 1;
    *(_DWORD *)(a1 + 336) = 72;
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    *(_QWORD *)(a1 + 344) = ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup
      && (*(_QWORD *)(a1 + 288) = ThreadpoolCleanupGroup,
          *(_QWORD *)(a1 + 296) = 0,
          EventW = CreateEventW(0, 0, 0, 0),
          (*(_QWORD *)(a1 + 352) = EventW) != 0)
      && (v6 = CreateEventW(0, 0, 0, 0), (*(_QWORD *)(a1 + 360) = v6) != 0) )
    {
      LastError = 0;
      *(_QWORD *)(a1 + 368) = 0;
      *(_DWORD *)(a1 + 384) = 0;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 87;
  }
  WppTraceIndent(v2, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      199,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18001b284  mov     [rsp+arg_0], rbx
0x18001b289  mov     [rsp+arg_8], rdi
0x18001b28e  push    r14
0x18001b290  sub     rsp, 30h
0x18001b294  xor     edx, edx
0x18001b296  mov     rbx, rcx
0x18001b299  call    WppTraceIndent
0x18001b29e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2a5  lea     r14, WPP_GLOBAL_Control
0x18001b2ac  cmp     rcx, r14
0x18001b2af  jz      short loc_18001B2D9
0x18001b2b1  test    byte ptr [rcx+1Ch], 2
0x18001b2b5  jz      short loc_18001B2D9
0x18001b2b7  cmp     byte ptr [rcx+19h], 5
0x18001b2bb  jb      short loc_18001B2D9
0x18001b2bd  mov     r9, cs:WPP_pszIndent
0x18001b2c4  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b2cb  mov     rcx, [rcx+10h]
0x18001b2cf  mov     edx, 0C6h
0x18001b2d4  call    WPP_SF_s
0x18001b2d9  test    rbx, rbx
0x18001b2dc  jnz     short loc_18001B2E6
0x18001b2de  lea     edi, [rbx+57h]
0x18001b2e1  jmp     loc_18001B3C5
0x18001b2e6  mov     dword ptr [rbx+110h], 3
0x18001b2f0  mov     qword ptr [rbx+118h], 0
0x18001b2fb  mov     qword ptr [rbx+120h], 0
0x18001b306  mov     qword ptr [rbx+128h], 0
0x18001b311  mov     qword ptr [rbx+130h], 0
0x18001b31c  mov     qword ptr [rbx+138h], 0
0x18001b327  mov     qword ptr [rbx+140h], 0
0x18001b332  mov     dword ptr [rbx+148h], 0
0x18001b33c  mov     dword ptr [rbx+14Ch], 1
0x18001b346  mov     dword ptr [rbx+150h], 48h ; 'H'
0x18001b350  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18001b356  mov     [rbx+158h], rax
0x18001b35d  test    rax, rax
0x18001b360  jnz     short loc_18001B36C
0x18001b362  call    cs:__imp_GetLastError
0x18001b368  mov     edi, eax
0x18001b36a  jmp     short loc_18001B3C5
0x18001b36c  xor     r9d, r9d; lpName
0x18001b36f  mov     [rbx+120h], rax
0x18001b376  xor     r8d, r8d; bInitialState
0x18001b379  mov     qword ptr [rbx+128h], 0
0x18001b384  xor     edx, edx; bManualReset
0x18001b386  xor     ecx, ecx; lpEventAttributes
0x18001b388  call    cs:__imp_CreateEventW
0x18001b38e  mov     [rbx+160h], rax
0x18001b395  test    rax, rax
0x18001b398  jz      short loc_18001B362
0x18001b39a  xor     r9d, r9d; lpName
0x18001b39d  xor     r8d, r8d; bInitialState
0x18001b3a0  xor     edx, edx; bManualReset
0x18001b3a2  xor     ecx, ecx; lpEventAttributes
0x18001b3a4  call    cs:__imp_CreateEventW
0x18001b3aa  mov     [rbx+168h], rax
0x18001b3b1  test    rax, rax
0x18001b3b4  jz      short loc_18001B362
0x18001b3b6  xor     edi, edi
0x18001b3b8  mov     [rbx+170h], rdi
0x18001b3bf  mov     [rbx+180h], edi
0x18001b3c5  mov     edx, 1
0x18001b3ca  call    WppTraceIndent
0x18001b3cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3d6  cmp     rcx, r14
0x18001b3d9  jz      short loc_18001B407
0x18001b3db  test    byte ptr [rcx+1Ch], 2
0x18001b3df  jz      short loc_18001B407
0x18001b3e1  cmp     byte ptr [rcx+19h], 5
0x18001b3e5  jb      short loc_18001B407
0x18001b3e7  mov     r9, cs:WPP_pszIndent
0x18001b3ee  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b3f5  mov     rcx, [rcx+10h]
0x18001b3f9  mov     edx, 0C7h
0x18001b3fe  mov     [rsp+38h+var_18], edi
0x18001b402  call    WPP_SF_sd
0x18001b407  mov     rbx, [rsp+38h+arg_0]
0x18001b40c  mov     eax, edi
0x18001b40e  mov     rdi, [rsp+38h+arg_8]
0x18001b413  add     rsp, 30h
0x18001b417  pop     r14
0x18001b419  retn
```
