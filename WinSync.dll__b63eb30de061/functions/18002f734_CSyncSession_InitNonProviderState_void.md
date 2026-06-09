# CSyncSession::InitNonProviderState(void)

- ea: `0x18002f734`
- end: `0x18002f82c`
- name: `?InitNonProviderState@CSyncSession@@AEAAJXZ`
- size: `248`
- prototype: `__int64 __fastcall(CSyncSession *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002f664`

## callees

- `0x1800089d0`
- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002d6e0`
- `0x18002f734`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f78d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f78d`

## pseudocode

```c
__int64 __fastcall CSyncSession::InitNonProviderState(CSyncSession *this)
{
  HANDLE EventW; // rax
  int v3; // ebx
  CSyncSessionStateData *v4; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      58,
      WPP_24b986413345305da18a80c41c45e189_Traceguids,
      "CSyncSession::InitNonProviderState");
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 17) = EventW;
  if ( EventW )
  {
    v3 = Lock::Initialize((CSyncSession *)((char *)this + 88));
    if ( v3 < 0 )
      goto LABEL_12;
    v4 = (CSyncSessionStateData *)SeAlloc(0x68u);
    if ( v4 )
      v4 = CSyncSessionStateData::CSyncSessionStateData(v4);
    *((_QWORD *)this + 21) = v4;
    if ( v4 )
    {
      *((_DWORD *)this + 37) = 1;
      goto LABEL_12;
    }
  }
  v3 = -2147024882;
LABEL_12:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      (unsigned int)WPP_24b986413345305da18a80c41c45e189_Traceguids,
      (unsigned int)"CSyncSession::InitNonProviderState",
      v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002f734  mov     [rsp+arg_0], rbx
0x18002f739  mov     [rsp+arg_8], rsi
0x18002f73e  push    rdi
0x18002f73f  sub     rsp, 30h
0x18002f743  mov     rdi, rcx
0x18002f746  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f74d  lea     rsi, WPP_GLOBAL_Control
0x18002f754  cmp     rcx, rsi
0x18002f757  jz      short loc_18002F781
0x18002f759  test    byte ptr [rcx+1Ch], 4
0x18002f75d  jz      short loc_18002F781
0x18002f75f  cmp     byte ptr [rcx+19h], 5
0x18002f763  jb      short loc_18002F781
0x18002f765  mov     rcx, [rcx+10h]
0x18002f769  lea     r9, aCsyncsessionIn; "CSyncSession::InitNonProviderState"
0x18002f770  mov     edx, 3Ah ; ':'
0x18002f775  lea     r8, WPP_24b986413345305da18a80c41c45e189_Traceguids
0x18002f77c  call    WPP_SF_s
0x18002f781  xor     r9d, r9d; lpName
0x18002f784  xor     r8d, r8d; bInitialState
0x18002f787  xor     ecx, ecx; lpEventAttributes
0x18002f789  lea     edx, [r9+1]; bManualReset
0x18002f78d  call    cs:__imp_CreateEventW
0x18002f793  mov     [rdi+88h], rax
0x18002f79a  test    rax, rax
0x18002f79d  jnz     short loc_18002F7A6
0x18002f79f  mov     ebx, 8007000Eh
0x18002f7a4  jmp     short loc_18002F7E2
0x18002f7a6  lea     rcx, [rdi+58h]; this
0x18002f7aa  call    ?Initialize@Lock@@QEAAJXZ; Lock::Initialize(void)
0x18002f7af  mov     ebx, eax
0x18002f7b1  test    eax, eax
0x18002f7b3  js      short loc_18002F7E2
0x18002f7b5  mov     ecx, 68h ; 'h'; unsigned __int64
0x18002f7ba  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18002f7bf  test    rax, rax
0x18002f7c2  jz      short loc_18002F7CC
0x18002f7c4  mov     rcx, rax; this
0x18002f7c7  call    ??0CSyncSessionStateData@@QEAA@XZ; CSyncSessionStateData::CSyncSessionStateData(void)
0x18002f7cc  mov     [rdi+0A8h], rax
0x18002f7d3  test    rax, rax
0x18002f7d6  jz      short loc_18002F79F
0x18002f7d8  mov     dword ptr [rdi+94h], 1
0x18002f7e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7e9  cmp     rcx, rsi
0x18002f7ec  jz      short loc_18002F81A
0x18002f7ee  test    byte ptr [rcx+1Ch], 4
0x18002f7f2  jz      short loc_18002F81A
0x18002f7f4  cmp     byte ptr [rcx+19h], 5
0x18002f7f8  jb      short loc_18002F81A
0x18002f7fa  mov     rcx, [rcx+10h]
0x18002f7fe  lea     r9, aCsyncsessionIn; "CSyncSession::InitNonProviderState"
0x18002f805  mov     edx, 3Bh ; ';'
0x18002f80a  mov     [rsp+38h+var_18], ebx
0x18002f80e  lea     r8, WPP_24b986413345305da18a80c41c45e189_Traceguids
0x18002f815  call    WPP_SF_sD
0x18002f81a  mov     rsi, [rsp+38h+arg_8]
0x18002f81f  mov     eax, ebx
0x18002f821  mov     rbx, [rsp+38h+arg_0]
0x18002f826  add     rsp, 30h
0x18002f82a  pop     rdi
0x18002f82b  retn
```
