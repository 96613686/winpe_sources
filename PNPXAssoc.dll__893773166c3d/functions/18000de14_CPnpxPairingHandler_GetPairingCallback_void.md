# CPnpxPairingHandler::GetPairingCallback(void)

- ea: `0x18000de14`
- end: `0x18000dec7`
- name: `?GetPairingCallback@CPnpxPairingHandler@@IEAAPEAUIPairingCallback@@XZ`
- size: `179`
- prototype: `struct IPairingCallback *__fastcall(CPnpxPairingHandler *__hidden this)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000d880`
- `0x18000d9d0`
- `0x18000e340`
- `0x18000e540`
- `0x18000e6e0`
- `0x18000e870`
- `0x18000e9d0`

## callees

- `0x18000bce4`
- `0x18000d4a4`
- `0x18000de14`
- `0x180014010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000de6c`
- `KERNEL32!LeaveCriticalSection` at `0x18000de6c`
- `KERNEL32!EnterCriticalSection` at `0x18000de59`
- `KERNEL32!EnterCriticalSection` at `0x18000de59`

## pseudocode

```c
struct IPairingCallback *__fastcall CPnpxPairingHandler::GetPairingCallback(CPnpxPairingHandler *this)
{
  __int64 v2; // rdi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( *((_QWORD *)this + 11) )
    v2 = *((_QWORD *)this + 11);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sqP(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
  return (struct IPairingCallback *)v2;
}

```

## disassembly

```asm
0x18000de14  push    rbx
0x18000de16  push    rbp
0x18000de17  push    rsi
0x18000de18  push    rdi
0x18000de19  sub     rsp, 38h
0x18000de1d  mov     rsi, rcx
0x18000de20  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de27  lea     rbp, WPP_GLOBAL_Control
0x18000de2e  cmp     rcx, rbp
0x18000de31  jz      short loc_18000DE53
0x18000de33  cmp     byte ptr [rcx+19h], 4
0x18000de37  jb      short loc_18000DE53
0x18000de39  mov     rcx, [rcx+10h]
0x18000de3d  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000de44  mov     edx, 26h ; '&'
0x18000de49  mov     [rsp+58h+var_38], rsi
0x18000de4e  call    WPP_SF_sq
0x18000de53  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000de57  xor     edi, edi
0x18000de59  call    cs:__imp_EnterCriticalSection
0x18000de5f  cmp     [rsi+58h], rdi
0x18000de63  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000de67  cmovnz  rdi, [rsi+58h]
0x18000de6c  call    cs:__imp_LeaveCriticalSection
0x18000de72  test    rdi, rdi
0x18000de75  jz      short loc_18000DE86
0x18000de77  mov     rax, [rdi]
0x18000de7a  mov     rcx, rdi
0x18000de7d  mov     rax, [rax+8]
0x18000de81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de8d  cmp     rcx, rbp
0x18000de90  jz      short loc_18000DEBB
0x18000de92  cmp     byte ptr [rcx+19h], 4
0x18000de96  jb      short loc_18000DEBB
0x18000de98  mov     rcx, [rcx+10h]
0x18000de9c  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000dea3  mov     edx, 27h ; '''
0x18000dea8  mov     [rsp+58h+var_30], 0
0x18000deb1  mov     [rsp+58h+var_38], rsi
0x18000deb6  call    WPP_SF_sqP
0x18000debb  mov     rax, rdi
0x18000debe  add     rsp, 38h
0x18000dec2  pop     rdi
0x18000dec3  pop     rsi
0x18000dec4  pop     rbp
0x18000dec5  pop     rbx
0x18000dec6  retn
```
