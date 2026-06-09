# CPnpxPairingHandler::BeginCallback(void)

- ea: `0x18000d7d8`
- end: `0x18000d870`
- name: `?BeginCallback@CPnpxPairingHandler@@IEAAXXZ`
- size: `152`
- prototype: `void __fastcall(CPnpxPairingHandler *__hidden this)`
- caller_count: `7`
- callee_count: `2`
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
- `0x18000d7d8`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000d82e`
- `KERNEL32!LeaveCriticalSection` at `0x18000d82e`
- `KERNEL32!EnterCriticalSection` at `0x18000d821`
- `KERNEL32!EnterCriticalSection` at `0x18000d821`

## pseudocode

```c
void __fastcall CPnpxPairingHandler::BeginCallback(CPnpxPairingHandler *this)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  ++*((_DWORD *)this + 26);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
}

```

## disassembly

```asm
0x18000d7d8  mov     [rsp+arg_0], rbx
0x18000d7dd  mov     [rsp+arg_8], rsi
0x18000d7e2  push    rdi
0x18000d7e3  sub     rsp, 30h
0x18000d7e7  mov     rdi, rcx
0x18000d7ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7f1  lea     rsi, WPP_GLOBAL_Control
0x18000d7f8  cmp     rcx, rsi
0x18000d7fb  jz      short loc_18000D81D
0x18000d7fd  cmp     byte ptr [rcx+19h], 4
0x18000d801  jb      short loc_18000D81D
0x18000d803  mov     rcx, [rcx+10h]
0x18000d807  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000d80e  mov     edx, 28h ; '('
0x18000d813  mov     [rsp+38h+var_18], rdi
0x18000d818  call    WPP_SF_sq
0x18000d81d  lea     rcx, [rdi+20h]; lpCriticalSection
0x18000d821  call    cs:__imp_EnterCriticalSection
0x18000d827  inc     dword ptr [rdi+68h]
0x18000d82a  lea     rcx, [rdi+20h]; lpCriticalSection
0x18000d82e  call    cs:__imp_LeaveCriticalSection
0x18000d834  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d83b  cmp     rcx, rsi
0x18000d83e  jz      short loc_18000D860
0x18000d840  cmp     byte ptr [rcx+19h], 4
0x18000d844  jb      short loc_18000D860
0x18000d846  mov     rcx, [rcx+10h]
0x18000d84a  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000d851  mov     edx, 29h ; ')'
0x18000d856  mov     [rsp+38h+var_18], rdi
0x18000d85b  call    WPP_SF_sq
0x18000d860  mov     rbx, [rsp+38h+arg_0]
0x18000d865  mov     rsi, [rsp+38h+arg_8]
0x18000d86a  add     rsp, 30h
0x18000d86e  pop     rdi
0x18000d86f  retn
```
