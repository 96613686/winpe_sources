# CWICRAWDecoderFrame::LogMemoryStatus(void)

- ea: `0x1800a22f4`
- end: `0x1800a25b2`
- name: `?LogMemoryStatus@CWICRAWDecoderFrame@@AEAAXXZ`
- size: `702`
- prototype: `void __fastcall(CWICRAWDecoderFrame *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1800a13d0`
- `0x1800a2030`

## callees

- `0x180002a00`
- `0x18009e8b8`
- `0x1800a22f4`
- `0x1800a2d70`
- `0x1800a2e14`
- `0x1800a2ee4`
- `0x1800a2fb0`
- `0x1800b0b00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a2403`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a2403`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a23f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a23f4`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800a233b`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800a233b`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1800a242a`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1800a242a`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1800a24de`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1800a24de`

## pseudocode

```c
void __fastcall CWICRAWDecoderFrame::LogMemoryStatus(CWICRAWDecoderFrame *this)
{
  HANDLE CurrentProcess; // rsi
  DWORD CurrentProcessId; // edi
  const char *v3; // r8
  _WORD v4[2]; // [rsp+78h] [rbp-90h] BYREF
  _WORD v5[6]; // [rsp+7Ch] [rbp-8Ch] BYREF
  _MEMORYSTATUSEX Buffer; // [rsp+88h] [rbp-80h] BYREF
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+C8h] [rbp-40h] BYREF

  memset(&Buffer, 0, sizeof(Buffer));
  Buffer.dwLength = 64;
  if ( GlobalMemoryStatusEx(&Buffer) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Ddiiiiii(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids, 0);
  }
  CurrentProcess = GetCurrentProcess();
  v5[0] = 0;
  v4[0] = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( (unsigned int)IsWow64Process2(CurrentProcess, v5, v4) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v3 = "Not WOW64";
      if ( v5[0] )
        v3 = "WOW64";
      WPP_SF_DdDsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4[0],
        (_DWORD)v3,
        (unsigned int)"WOW64",
        CurrentProcessId,
        v5[0],
        (__int64)v3,
        v4[0]);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      &WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids,
      0,
      CurrentProcessId);
  }
  memset(&ppsmemCounters, 0, sizeof(ppsmemCounters));
  if ( K32GetProcessMemoryInfo(CurrentProcess, &ppsmemCounters, 0x48u) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dddddddddd(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids, 0);
  }
}

```

## disassembly

```asm
0x1800a22f4  mov     rax, rsp
0x1800a22f7  mov     [rax+8], rbx
0x1800a22fb  mov     [rax+10h], rsi
0x1800a22ff  mov     [rax+18h], rdi
0x1800a2303  mov     [rax+20h], r12
0x1800a2307  push    rbp
0x1800a2308  lea     rbp, [rax-28h]
0x1800a230c  sub     rsp, 120h
0x1800a2313  mov     rax, cs:__security_cookie
0x1800a231a  xor     rax, rsp
0x1800a231d  mov     [rbp+20h+var_10], rax
0x1800a2321  mov     ebx, 40h ; '@'
0x1800a2326  lea     rcx, [rbp+20h+Buffer]; void *
0x1800a232a  mov     r8d, ebx; Size
0x1800a232d  xor     edx, edx; Val
0x1800a232f  call    memset
0x1800a2334  lea     rcx, [rbp+20h+Buffer]; lpBuffer
0x1800a2338  mov     [rbp+20h+Buffer.dwLength], ebx
0x1800a233b  call    cs:__imp_GlobalMemoryStatusEx
0x1800a2342  nop     dword ptr [rax+rax+00h]
0x1800a2347  xor     r12d, r12d
0x1800a234a  test    eax, eax
0x1800a234c  jz      short loc_1800A23BD
0x1800a234e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2355  lea     rbx, WPP_GLOBAL_Control
0x1800a235c  cmp     rcx, rbx
0x1800a235f  jz      loc_1800A23F4
0x1800a2365  test    byte ptr [rcx+1Ch], 1
0x1800a2369  jz      loc_1800A23F4
0x1800a236f  cmp     byte ptr [rcx+19h], 4
0x1800a2373  jb      short loc_1800A23F4
0x1800a2375  mov     rax, [rbp+20h+Buffer.ullAvailVirtual]
0x1800a2379  mov     rcx, [rcx+10h]
0x1800a237d  mov     qword ptr [rsp+120h+var_D0], rax
0x1800a2382  mov     rax, [rbp+20h+Buffer.ullTotalVirtual]
0x1800a2386  mov     [rsp+120h+var_D8], rax
0x1800a238b  mov     rax, [rbp+20h+Buffer.ullAvailPageFile]
0x1800a238f  mov     [rsp+120h+var_E0], rax
0x1800a2394  mov     rax, [rbp+20h+Buffer.ullTotalPageFile]
0x1800a2398  mov     [rsp+120h+var_E8], rax
0x1800a239d  mov     rax, [rbp+20h+Buffer.ullAvailPhys]
0x1800a23a1  mov     [rsp+120h+var_F0], rax
0x1800a23a6  mov     rax, [rbp+20h+Buffer.ullTotalPhys]
0x1800a23aa  mov     [rsp+120h+var_F8], rax
0x1800a23af  mov     eax, [rbp+20h+Buffer.dwMemoryLoad]
0x1800a23b2  mov     dword ptr [rsp+120h+var_100], eax
0x1800a23b6  call    WPP_SF_Ddiiiiii
0x1800a23bb  jmp     short loc_1800A23F4
0x1800a23bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a23c4  lea     rbx, WPP_GLOBAL_Control
0x1800a23cb  cmp     rcx, rbx
0x1800a23ce  jz      short loc_1800A23F4
0x1800a23d0  test    byte ptr [rcx+1Ch], 1
0x1800a23d4  jz      short loc_1800A23F4
0x1800a23d6  cmp     byte ptr [rcx+19h], 4
0x1800a23da  jb      short loc_1800A23F4
0x1800a23dc  mov     rcx, [rcx+10h]
0x1800a23e0  lea     r8, WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids
0x1800a23e7  mov     edx, 12h
0x1800a23ec  xor     r9d, r9d
0x1800a23ef  call    WPP_SF_D
0x1800a23f4  call    cs:__imp_GetCurrentProcess
0x1800a23fb  nop     dword ptr [rax+rax+00h]
0x1800a2400  mov     rsi, rax
0x1800a2403  call    cs:__imp_GetCurrentProcessId
0x1800a240a  nop     dword ptr [rax+rax+00h]
0x1800a240f  lea     r8, [rsp+120h+var_B0]
0x1800a2414  mov     [rsp+120h+var_AC], r12w
0x1800a241a  lea     rdx, [rsp+120h+var_AC]
0x1800a241f  mov     [rsp+120h+var_B0], r12w
0x1800a2425  mov     rcx, rsi
0x1800a2428  mov     edi, eax
0x1800a242a  call    cs:__imp_IsWow64Process2
0x1800a2431  nop     dword ptr [rax+rax+00h]
0x1800a2436  test    eax, eax
0x1800a2438  jz      short loc_1800A248D
0x1800a243a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2441  cmp     rcx, rbx
0x1800a2444  jz      short loc_1800A24C1
0x1800a2446  test    byte ptr [rcx+1Ch], 1
0x1800a244a  jz      short loc_1800A24C1
0x1800a244c  cmp     byte ptr [rcx+19h], 4
0x1800a2450  jb      short loc_1800A24C1
0x1800a2452  movzx   eax, [rsp+120h+var_AC]
0x1800a2457  lea     r9, aWow64; "WOW64"
0x1800a245e  movzx   edx, [rsp+120h+var_B0]
0x1800a2463  lea     r8, aNotWow64; "Not WOW64"
0x1800a246a  mov     rcx, [rcx+10h]
0x1800a246e  test    ax, ax
0x1800a2471  mov     dword ptr [rsp+120h+var_E8], edx
0x1800a2475  cmovnz  r8, r9
0x1800a2479  mov     [rsp+120h+var_F0], r8
0x1800a247e  mov     dword ptr [rsp+120h+var_F8], eax
0x1800a2482  mov     dword ptr [rsp+120h+var_100], edi
0x1800a2486  call    WPP_SF_DdDsD
0x1800a248b  jmp     short loc_1800A24C1
0x1800a248d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2494  cmp     rcx, rbx
0x1800a2497  jz      short loc_1800A24C1
0x1800a2499  test    byte ptr [rcx+1Ch], 1
0x1800a249d  jz      short loc_1800A24C1
0x1800a249f  cmp     byte ptr [rcx+19h], 4
0x1800a24a3  jb      short loc_1800A24C1
0x1800a24a5  mov     rcx, [rcx+10h]
0x1800a24a9  lea     r8, WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids
0x1800a24b0  mov     edx, 14h
0x1800a24b5  mov     dword ptr [rsp+120h+var_100], edi
0x1800a24b9  xor     r9d, r9d
0x1800a24bc  call    WPP_SF_Dd
0x1800a24c1  mov     edi, 48h ; 'H'
0x1800a24c6  lea     rcx, [rbp+20h+ppsmemCounters]; void *
0x1800a24ca  mov     r8d, edi; Size
0x1800a24cd  xor     edx, edx; Val
0x1800a24cf  call    memset
0x1800a24d4  mov     r8d, edi; cb
0x1800a24d7  lea     rdx, [rbp+20h+ppsmemCounters]; ppsmemCounters
0x1800a24db  mov     rcx, rsi; Process
0x1800a24de  call    cs:__imp_K32GetProcessMemoryInfo
0x1800a24e5  nop     dword ptr [rax+rax+00h]
0x1800a24ea  test    eax, eax
0x1800a24ec  jz      short loc_1800A2558
0x1800a24ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a24f5  cmp     rcx, rbx
0x1800a24f8  jz      loc_1800A2588
0x1800a24fe  test    byte ptr [rcx+1Ch], 1
0x1800a2502  jz      loc_1800A2588
0x1800a2508  cmp     byte ptr [rcx+19h], 4
0x1800a250c  jb      short loc_1800A2588
0x1800a250e  mov     eax, dword ptr [rbp+20h+ppsmemCounters.PeakPagefileUsage]
0x1800a2511  mov     rcx, [rcx+10h]
0x1800a2515  mov     [rsp+120h+var_C0], eax
0x1800a2519  mov     eax, dword ptr [rbp+20h+ppsmemCounters.PagefileUsage]
0x1800a251c  mov     [rsp+120h+var_C8], eax
0x1800a2520  mov     eax, dword ptr [rbp+20h+ppsmemCounters.QuotaNonPagedPoolUsage]
0x1800a2523  mov     [rsp+120h+var_D0], eax
0x1800a2527  mov     eax, dword ptr [rbp+20h+ppsmemCounters.QuotaPeakNonPagedPoolUsage]
0x1800a252a  mov     dword ptr [rsp+120h+var_D8], eax
0x1800a252e  mov     eax, dword ptr [rbp+20h+ppsmemCounters.QuotaPagedPoolUsage]
0x1800a2531  mov     dword ptr [rsp+120h+var_E0], eax
0x1800a2535  mov     eax, dword ptr [rbp+20h+ppsmemCounters.QuotaPeakPagedPoolUsage]
0x1800a2538  mov     dword ptr [rsp+120h+var_E8], eax
0x1800a253c  mov     eax, dword ptr [rbp+20h+ppsmemCounters.WorkingSetSize]
0x1800a253f  mov     dword ptr [rsp+120h+var_F0], eax
0x1800a2543  mov     eax, dword ptr [rbp+20h+ppsmemCounters.PeakWorkingSetSize]
0x1800a2546  mov     dword ptr [rsp+120h+var_F8], eax
0x1800a254a  mov     eax, [rbp+20h+ppsmemCounters.PageFaultCount]
0x1800a254d  mov     dword ptr [rsp+120h+var_100], eax
0x1800a2551  call    WPP_SF_Dddddddddd
0x1800a2556  jmp     short loc_1800A2588
0x1800a2558  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a255f  cmp     rcx, rbx
0x1800a2562  jz      short loc_1800A2588
0x1800a2564  test    byte ptr [rcx+1Ch], 1
0x1800a2568  jz      short loc_1800A2588
0x1800a256a  cmp     byte ptr [rcx+19h], 4
0x1800a256e  jb      short loc_1800A2588
0x1800a2570  mov     rcx, [rcx+10h]
0x1800a2574  lea     r8, WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids
0x1800a257b  mov     edx, 16h
0x1800a2580  xor     r9d, r9d
0x1800a2583  call    WPP_SF_D
0x1800a2588  mov     rcx, [rbp+20h+var_10]
0x1800a258c  xor     rcx, rsp; StackCookie
0x1800a258f  call    __security_check_cookie
0x1800a2594  lea     r11, [rsp+120h+var_s0]
0x1800a259c  mov     rbx, [r11+10h]
0x1800a25a0  mov     rsi, [r11+18h]
0x1800a25a4  mov     rdi, [r11+20h]
0x1800a25a8  mov     r12, [r11+28h]
0x1800a25ac  mov     rsp, r11
0x1800a25af  pop     rbp
0x1800a25b0  retn
```
