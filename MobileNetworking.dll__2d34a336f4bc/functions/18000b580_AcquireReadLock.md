# AcquireReadLock

- ea: `0x18000b580`
- end: `0x18000b61f`
- name: `AcquireReadLock`
- size: `159`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008ff0`
- `0x180009130`
- `0x18000b580`
- `0x1800116f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b5ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b5ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b5d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b5d8`

## pseudocode

```c
void __fastcall AcquireReadLock(__int64 a1)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ae89183a349339de188038c4f0a19280_Traceguids);
  if ( *(_DWORD *)(a1 + 4) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 48));
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ae89183a349339de188038c4f0a19280_Traceguids, 0);
}

```

## disassembly

```asm
0x18000b580  mov     [rsp+arg_0], rbx
0x18000b585  mov     [rsp+arg_8], rsi
0x18000b58a  push    rdi
0x18000b58b  sub     rsp, 20h
0x18000b58f  mov     rdi, rcx
0x18000b592  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b599  lea     rsi, WPP_GLOBAL_Control
0x18000b5a0  cmp     rcx, rsi
0x18000b5a3  jz      short loc_18000B5C0
0x18000b5a5  test    byte ptr [rcx+1Ch], 8
0x18000b5a9  jz      short loc_18000B5C0
0x18000b5ab  mov     rcx, [rcx+10h]
0x18000b5af  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x18000b5b6  mov     edx, 12h
0x18000b5bb  call    WPP_SF_
0x18000b5c0  cmp     dword ptr [rdi+4], 0
0x18000b5c4  jz      short loc_18000B5E0
0x18000b5c6  lea     rcx, [rdi+8]; lpCriticalSection
0x18000b5ca  call    cs:__imp_EnterCriticalSection
0x18000b5d0  lock inc dword ptr [rdi+30h]
0x18000b5d4  lea     rcx, [rdi+8]; lpCriticalSection
0x18000b5d8  call    cs:__imp_LeaveCriticalSection
0x18000b5de  jmp     short loc_18000B5E5
0x18000b5e0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b5e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5ec  cmp     rcx, rsi
0x18000b5ef  jz      short loc_18000B60F
0x18000b5f1  test    byte ptr [rcx+1Ch], 8
0x18000b5f5  jz      short loc_18000B60F
0x18000b5f7  mov     rcx, [rcx+10h]
0x18000b5fb  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x18000b602  mov     edx, 13h
0x18000b607  xor     r9d, r9d
0x18000b60a  call    WPP_SF_L
0x18000b60f  mov     rbx, [rsp+28h+arg_0]
0x18000b614  mov     rsi, [rsp+28h+arg_8]
0x18000b619  add     rsp, 20h
0x18000b61d  pop     rdi
0x18000b61e  retn
```
