# CChangeApplier::InitNonProviderState(void)

- ea: `0x180040434`
- end: `0x180040593`
- name: `?InitNonProviderState@CChangeApplier@@AEAAJXZ`
- size: `351`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18003fe48`
- `0x18004008c`

## callees

- `0x1800089d0`
- `0x18001a038`
- `0x18001ae20`
- `0x180040434`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004049c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800404bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800404e4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004049c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800404bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800404e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040507`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040520`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040507`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040520`

## pseudocode

```c
__int64 __fastcall CChangeApplier::InitNonProviderState(CChangeApplier *this)
{
  PVOID *v2; // rcx
  int v3; // ebx
  HANDLE EventW; // rax
  HANDLE *v5; // rdi
  HANDLE v6; // rax
  HANDLE v7; // rax
  void *v8; // rcx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      85,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::InitNonProviderState");
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( !*((_DWORD *)this + 106) )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 43) = EventW;
    v5 = (HANDLE *)((char *)this + 352);
    if ( EventW
      && (v6 = CreateEventW(0, 0, 0, 0), (*v5 = v6) != 0)
      && (*((_QWORD *)this + 23) || (v7 = CreateEventW(0, 0, 0, 0), (*((_QWORD *)this + 34) = v7) != 0)) )
    {
      v3 = Lock::Initialize((CChangeApplier *)((char *)this + 288));
      if ( v3 >= 0 )
      {
        *((_DWORD *)this + 106) = 1;
LABEL_15:
        v2 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_16;
      }
    }
    else
    {
      v3 = -2147024882;
    }
    v8 = (void *)*((_QWORD *)this + 43);
    if ( v8 )
    {
      CloseHandle(v8);
      *((_QWORD *)this + 43) = 0;
    }
    if ( *v5 )
    {
      CloseHandle(*v5);
      *v5 = 0;
    }
    goto LABEL_15;
  }
LABEL_16:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v2[2],
      86,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::InitNonProviderState",
      v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180040434  push    rbx
0x180040436  push    rsi
0x180040437  push    rdi
0x180040438  push    r15
0x18004043a  sub     rsp, 38h
0x18004043e  mov     rsi, rcx
0x180040441  mov     rcx, cs:WPP_GLOBAL_Control
0x180040448  lea     r15, WPP_GLOBAL_Control
0x18004044f  cmp     rcx, r15
0x180040452  jz      short loc_180040483
0x180040454  test    byte ptr [rcx+1Ch], 8
0x180040458  jz      short loc_180040483
0x18004045a  cmp     byte ptr [rcx+19h], 5
0x18004045e  jb      short loc_180040483
0x180040460  mov     rcx, [rcx+10h]
0x180040464  lea     r9, aCchangeapplier_108; "CChangeApplier::InitNonProviderState"
0x18004046b  mov     edx, 55h ; 'U'
0x180040470  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180040477  call    WPP_SF_s
0x18004047c  mov     rcx, cs:WPP_GLOBAL_Control
0x180040483  xor     ebx, ebx
0x180040485  cmp     [rsi+1A8h], ebx
0x18004048b  jnz     loc_180040534
0x180040491  xor     r9d, r9d; lpName
0x180040494  lea     edx, [rbx+1]; bManualReset
0x180040497  xor     r8d, r8d; bInitialState
0x18004049a  xor     ecx, ecx; lpEventAttributes
0x18004049c  call    cs:__imp_CreateEventW
0x1800404a2  mov     [rsi+158h], rax
0x1800404a9  lea     rdi, [rsi+160h]
0x1800404b0  test    rax, rax
0x1800404b3  jz      short loc_1800404F6
0x1800404b5  xor     r9d, r9d; lpName
0x1800404b8  xor     r8d, r8d; bInitialState
0x1800404bb  xor     edx, edx; bManualReset
0x1800404bd  xor     ecx, ecx; lpEventAttributes
0x1800404bf  call    cs:__imp_CreateEventW
0x1800404c5  mov     [rdi], rax
0x1800404c8  test    rax, rax
0x1800404cb  jz      short loc_1800404F6
0x1800404cd  cmp     [rsi+0B8h], rbx
0x1800404d4  jnz     loc_180040571
0x1800404da  xor     r9d, r9d; lpName
0x1800404dd  xor     r8d, r8d; bInitialState
0x1800404e0  xor     edx, edx; bManualReset
0x1800404e2  xor     ecx, ecx; lpEventAttributes
0x1800404e4  call    cs:__imp_CreateEventW
0x1800404ea  mov     [rsi+110h], rax
0x1800404f1  test    rax, rax
0x1800404f4  jnz     short loc_180040571
0x1800404f6  mov     ebx, 8007000Eh
0x1800404fb  mov     rcx, [rsi+158h]; hObject
0x180040502  test    rcx, rcx
0x180040505  jz      short loc_180040518
0x180040507  call    cs:__imp_CloseHandle
0x18004050d  mov     qword ptr [rsi+158h], 0
0x180040518  mov     rcx, [rdi]; hObject
0x18004051b  test    rcx, rcx
0x18004051e  jz      short loc_18004052D
0x180040520  call    cs:__imp_CloseHandle
0x180040526  mov     qword ptr [rdi], 0
0x18004052d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040534  cmp     rcx, r15
0x180040537  jz      short loc_180040565
0x180040539  test    byte ptr [rcx+1Ch], 8
0x18004053d  jz      short loc_180040565
0x18004053f  cmp     byte ptr [rcx+19h], 5
0x180040543  jb      short loc_180040565
0x180040545  mov     rcx, [rcx+10h]
0x180040549  lea     r9, aCchangeapplier_108; "CChangeApplier::InitNonProviderState"
0x180040550  mov     edx, 56h ; 'V'
0x180040555  mov     [rsp+58h+var_38], ebx
0x180040559  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180040560  call    WPP_SF_sD
0x180040565  mov     eax, ebx
0x180040567  add     rsp, 38h
0x18004056b  pop     r15
0x18004056d  pop     rdi
0x18004056e  pop     rsi
0x18004056f  pop     rbx
0x180040570  retn
0x180040571  lea     rcx, [rsi+120h]; this
0x180040578  call    ?Initialize@Lock@@QEAAJXZ; Lock::Initialize(void)
0x18004057d  mov     ebx, eax
0x18004057f  test    eax, eax
0x180040581  js      loc_1800404FB
0x180040587  mov     dword ptr [rsi+1A8h], 1
0x180040591  jmp     short loc_18004052D
```
