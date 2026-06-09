# CPowerManager::CPowerManager(ITpThreadManager *)

- ea: `0x180151c4c`
- end: `0x180151f46`
- name: `??0CPowerManager@@QEAA@PEAUITpThreadManager@@@Z`
- size: `762`
- prototype: `CPowerManager *__fastcall(CPowerManager *__hidden this, struct ITpThreadManager *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18014af6c`

## callees

- `0x180151c4c`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x180151c91`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180151cd4`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180151d02`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180151c91`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180151cd4`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180151d02`
- `KERNEL32!GetTickCount64` at `0x180151ea4`
- `KERNEL32!GetTickCount64` at `0x180151ea4`
- `KERNEL32!CloseHandle` at `0x180151dc0`
- `KERNEL32!CloseHandle` at `0x180151df5`
- `KERNEL32!CloseHandle` at `0x180151e70`
- `KERNEL32!CloseHandle` at `0x180151e90`
- `KERNEL32!CloseHandle` at `0x180151dc0`
- `KERNEL32!CloseHandle` at `0x180151df5`
- `KERNEL32!CloseHandle` at `0x180151e70`
- `KERNEL32!CloseHandle` at `0x180151e90`
- `KERNEL32!CreateEventW` at `0x180151da4`
- `KERNEL32!CreateEventW` at `0x180151dd9`
- `KERNEL32!CreateEventW` at `0x180151da4`
- `KERNEL32!CreateEventW` at `0x180151dd9`

## pseudocode

```c
CPowerManager *__fastcall CPowerManager::CPowerManager(CPowerManager *this, struct ITpThreadManager *a2)
{
  HANDLE EventW; // rax
  void *v5; // rcx
  HANDLE v6; // rbx
  HANDLE v7; // rax
  void *v8; // rcx
  HANDLE v9; // rbx
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  void *v12; // rcx
  void *v13; // rcx
  ULONGLONG TickCount64; // rax
  volatile __int64 *v15; // rdx
  __int64 v16; // r8
  CPowerManager *result; // rax

  *(_QWORD *)this = &CPowerManager::`vftable'{for `ITpPowerManagerInternal'};
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 1) = &CPowerManager::`vftable'{for `ITpPowerManagerDebug'};
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 56), 0, 0);
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 62) = 0;
  *((_QWORD *)this + 63) = 0;
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_QWORD *)this + 69) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)this + 14, 0, 0);
  *((_QWORD *)this + 75) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 632), 0, 0);
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 92) = 0;
  *((_QWORD *)this + 94) = 0x8000000000000000uLL;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 95) = 0;
  *((_QWORD *)this + 96) = 0;
  *((_DWORD *)this + 4) = 1;
  *((_QWORD *)this + 20) = a2;
  (*(void (__fastcall **)(struct ITpThreadManager *))(*(_QWORD *)a2 + 8LL))(a2);
  *((_DWORD *)this + 100) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v5 = (void *)*((_QWORD *)this + 22);
  v6 = EventW;
  if ( v5 )
  {
    *((_QWORD *)this + 22) = 0;
    CloseHandle(v5);
  }
  *((_QWORD *)this + 22) = v6;
  v7 = CreateEventW(0, 1, 0, 0);
  v8 = (void *)*((_QWORD *)this + 23);
  v9 = v7;
  if ( v8 )
  {
    *((_QWORD *)this + 23) = 0;
    CloseHandle(v8);
  }
  *((_QWORD *)this + 23) = v9;
  *((_QWORD *)this + 52) = -1;
  *((_QWORD *)this + 53) = -1;
  *((_QWORD *)this + 54) = -1;
  *((_DWORD *)this + 102) = 4149;
  *((_BYTE *)this + 412) = 0;
  v10 = *(_OWORD *)((char *)this + 408);
  *((_QWORD *)this + 21) = 0;
  v11 = *(_OWORD *)((char *)this + 424);
  *((_BYTE *)this + 404) = 0;
  *(_OWORD *)((char *)this + 440) = v10;
  *((_QWORD *)this + 59) = 0;
  *(_OWORD *)((char *)this + 456) = v11;
  v12 = (void *)*((_QWORD *)this + 62);
  if ( v12 )
  {
    *((_QWORD *)this + 62) = 0;
    CloseHandle(v12);
  }
  *((_QWORD *)this + 62) = 0;
  v13 = (void *)*((_QWORD *)this + 63);
  if ( v13 )
  {
    *((_QWORD *)this + 63) = 0;
    CloseHandle(v13);
  }
  *((_QWORD *)this + 63) = 0;
  *((_QWORD *)this + 64) = 0;
  TickCount64 = GetTickCount64();
  *((_BYTE *)this + 728) = 0;
  v15 = (volatile __int64 *)((char *)this + 296);
  *((_QWORD *)this + 68) = TickCount64;
  v16 = 13;
  *((_BYTE *)this + 696) = 0;
  *((_QWORD *)this + 88) = 0x7FFFFFFFFFFFFFFFLL;
  *((_BYTE *)this + 697) = 0;
  *((_QWORD *)this + 89) = 0;
  *((_QWORD *)this + 90) = 0;
  do
  {
    _InterlockedExchange64(v15 - 13, 0);
    _InterlockedExchange64(v15++, 0);
    --v16;
  }
  while ( v16 );
  _InterlockedExchange64((volatile __int64 *)this + 34, *((_QWORD *)this + 68));
  _InterlockedExchange64((volatile __int64 *)this + 36, *((_QWORD *)this + 68));
  result = this;
  *((_QWORD *)this + 67) = 0;
  *((_QWORD *)this + 99) = 0;
  return result;
}

```

## disassembly

```asm
0x180151c4c  mov     [rsp+arg_0], rbx
0x180151c51  mov     [rsp+arg_8], rsi
0x180151c56  push    rdi
0x180151c57  sub     rsp, 20h
0x180151c5b  xor     esi, esi
0x180151c5d  lea     rax, ??_7CPowerManager@@6BITpPowerManagerInternal@@@; const CPowerManager::`vftable'{for `ITpPowerManagerInternal'}
0x180151c64  mov     [rcx], rax
0x180151c67  mov     rbx, rdx
0x180151c6a  lea     rax, ??_7CPowerManager@@6BITpPowerManagerDebug@@@; const CPowerManager::`vftable'{for `ITpPowerManagerDebug'}
0x180151c71  mov     [rcx+18h], rsi
0x180151c75  mov     [rcx+8], rax
0x180151c79  mov     rdi, rcx
0x180151c7c  mov     [rcx+20h], rsi
0x180151c80  xor     r8d, r8d; Flags
0x180151c83  mov     [rcx+28h], rsi
0x180151c87  xor     edx, edx; dwSpinCount
0x180151c89  mov     [rcx+30h], rsi
0x180151c8d  add     rcx, 38h ; '8'; lpCriticalSection
0x180151c91  call    cs:__imp_InitializeCriticalSectionEx
0x180151c97  lea     rcx, [rdi+230h]; lpCriticalSection
0x180151c9e  mov     [rdi+0B0h], rsi
0x180151ca5  xor     r8d, r8d; Flags
0x180151ca8  mov     [rdi+0B8h], rsi
0x180151caf  xor     edx, edx; dwSpinCount
0x180151cb1  mov     [rdi+1F0h], rsi
0x180151cb8  mov     [rdi+1F8h], rsi
0x180151cbf  mov     [rdi+208h], rsi
0x180151cc6  mov     [rdi+210h], rsi
0x180151ccd  mov     [rdi+228h], rsi
0x180151cd4  call    cs:__imp_InitializeCriticalSectionEx
0x180151cda  lea     rcx, [rdi+278h]; lpCriticalSection
0x180151ce1  mov     [rdi+258h], rsi
0x180151ce8  xor     r8d, r8d; Flags
0x180151ceb  mov     [rdi+260h], rsi
0x180151cf2  xor     edx, edx; dwSpinCount
0x180151cf4  mov     [rdi+268h], rsi
0x180151cfb  mov     [rdi+270h], rsi
0x180151d02  call    cs:__imp_InitializeCriticalSectionEx
0x180151d08  mov     [rdi+2A0h], rsi
0x180151d0f  mov     rax, 8000000000000000h
0x180151d19  mov     [rdi+2A8h], rsi
0x180151d20  mov     rcx, rbx
0x180151d23  mov     [rdi+2B0h], rsi
0x180151d2a  mov     [rdi+2E0h], rsi
0x180151d31  mov     [rdi+2F0h], rax
0x180151d38  mov     [rdi+2E8h], rsi
0x180151d3f  mov     [rdi+2F8h], rsi
0x180151d46  mov     [rdi+300h], rsi
0x180151d4d  mov     dword ptr [rdi+10h], 1
0x180151d54  mov     [rdi+0A0h], rbx
0x180151d5b  mov     rax, [rbx]
0x180151d5e  mov     rax, [rax+8]
0x180151d62  call    cs:__guard_dispatch_icall_fptr
0x180151d68  xor     r9d, r9d; lpName
0x180151d6b  mov     [rdi+190h], esi
0x180151d71  xor     r8d, r8d; bInitialState
0x180151d74  mov     [rdi+60h], esi
0x180151d77  lea     edx, [rsi+1]; bManualReset
0x180151d7a  mov     [rdi+68h], rsi
0x180151d7e  xor     ecx, ecx; lpEventAttributes
0x180151d80  mov     [rdi+70h], rsi
0x180151d84  mov     [rdi+78h], rsi
0x180151d88  mov     [rdi+80h], rsi
0x180151d8f  mov     [rdi+88h], rsi
0x180151d96  mov     [rdi+90h], rsi
0x180151d9d  mov     [rdi+98h], rsi
0x180151da4  call    cs:__imp_CreateEventW
0x180151daa  mov     rcx, [rdi+0B0h]; hObject
0x180151db1  mov     rbx, rax
0x180151db4  test    rcx, rcx
0x180151db7  jz      short loc_180151DC6
0x180151db9  mov     [rdi+0B0h], rsi
0x180151dc0  call    cs:__imp_CloseHandle
0x180151dc6  xor     r9d, r9d; lpName
0x180151dc9  mov     [rdi+0B0h], rbx
0x180151dd0  xor     r8d, r8d; bInitialState
0x180151dd3  xor     ecx, ecx; lpEventAttributes
0x180151dd5  lea     edx, [r9+1]; bManualReset
0x180151dd9  call    cs:__imp_CreateEventW
0x180151ddf  mov     rcx, [rdi+0B8h]; hObject
0x180151de6  mov     rbx, rax
0x180151de9  test    rcx, rcx
0x180151dec  jz      short loc_180151DFB
0x180151dee  mov     [rdi+0B8h], rsi
0x180151df5  call    cs:__imp_CloseHandle
0x180151dfb  mov     [rdi+0B8h], rbx
0x180151e02  or      rax, 0FFFFFFFFFFFFFFFFh
0x180151e06  mov     [rdi+1A0h], rax
0x180151e0d  mov     [rdi+1A8h], rax
0x180151e14  mov     [rdi+1B0h], rax
0x180151e1b  mov     dword ptr [rdi+198h], 1035h
0x180151e25  mov     [rdi+19Ch], sil
0x180151e2c  movups  xmm0, xmmword ptr [rdi+198h]
0x180151e33  mov     [rdi+0A8h], rsi
0x180151e3a  movups  xmm1, xmmword ptr [rdi+1A8h]
0x180151e41  mov     [rdi+194h], sil
0x180151e48  movups  xmmword ptr [rdi+1B8h], xmm0
0x180151e4f  mov     [rdi+1D8h], rsi
0x180151e56  movups  xmmword ptr [rdi+1C8h], xmm1
0x180151e5d  mov     rcx, [rdi+1F0h]; hObject
0x180151e64  test    rcx, rcx
0x180151e67  jz      short loc_180151E76
0x180151e69  mov     [rdi+1F0h], rsi
0x180151e70  call    cs:__imp_CloseHandle
0x180151e76  mov     [rdi+1F0h], rsi
0x180151e7d  mov     rcx, [rdi+1F8h]; hObject
0x180151e84  test    rcx, rcx
0x180151e87  jz      short loc_180151E96
0x180151e89  mov     [rdi+1F8h], rsi
0x180151e90  call    cs:__imp_CloseHandle
0x180151e96  mov     [rdi+1F8h], rsi
0x180151e9d  mov     [rdi+200h], rsi
0x180151ea4  call    cs:__imp_GetTickCount64
0x180151eaa  mov     [rdi+2D8h], sil
0x180151eb1  lea     rdx, [rdi+128h]
0x180151eb8  mov     [rdi+220h], rax
0x180151ebf  mov     r8d, 0Dh
0x180151ec5  mov     rax, 7FFFFFFFFFFFFFFFh
0x180151ecf  mov     [rdi+2B8h], sil
0x180151ed6  mov     [rdi+2C0h], rax
0x180151edd  mov     [rdi+2B9h], sil
0x180151ee4  mov     [rdi+2C8h], rsi
0x180151eeb  mov     [rdi+2D0h], rsi
0x180151ef2  mov     rax, rsi
0x180151ef5  mov     rcx, rsi
0x180151ef8  xchg    rax, [rdx-68h]
0x180151efc  xchg    rcx, [rdx]
0x180151eff  lea     rdx, [rdx+8]
0x180151f03  sub     r8, 1
0x180151f07  jnz     short loc_180151EF2
0x180151f09  mov     rax, [rdi+220h]
0x180151f10  xchg    rax, [rdi+110h]
0x180151f17  mov     rax, [rdi+220h]
0x180151f1e  xchg    rax, [rdi+120h]
0x180151f25  mov     rbx, [rsp+28h+arg_0]
0x180151f2a  mov     rax, rdi
0x180151f2d  mov     [rdi+218h], rsi
0x180151f34  mov     [rdi+318h], rsi
0x180151f3b  mov     rsi, [rsp+28h+arg_8]
0x180151f40  add     rsp, 20h
0x180151f44  pop     rdi
0x180151f45  retn
```
