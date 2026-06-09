# CQuietHoursManager::_UpdateTimers(QuietHoursTimerId)

- ea: `0x1800731a4`
- end: `0x180073401`
- name: `?_UpdateTimers@CQuietHoursManager@@AEAAXW4QuietHoursTimerId@@@Z`
- size: `605`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180072c10`
- `0x180072c70`
- `0x180072f08`
- `0x1802d5f00`

## callees

- `0x1800731a4`
- `0x180142e10`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007324f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180073320`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007337e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800733f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007324f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180073320`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007337e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800733f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180073210`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800732ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007333f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800733c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180073210`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800732ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007333f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800733c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800731df`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800731df`

## pseudocode

```c
void __fastcall CQuietHoursManager::_UpdateTimers(__int64 a1, int a2)
{
  int v4; // r14d
  int v5; // ebx
  int v6; // eax
  struct _TP_TIMER *v7; // rcx
  int v8; // ebx
  int v9; // r8d
  int v10; // ecx
  int v11; // edx
  int v12; // ebx
  struct _TP_TIMER *v13; // rcx
  int v14; // ebx
  int v15; // eax
  struct _TP_TIMER *v16; // rcx
  struct _TP_TIMER *v17; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-18h] BYREF

  SystemTimeAsFileTime = 0;
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v4 = (unsigned __int16)(SystemTime.wMinute + 60 * SystemTime.wHour);
  if ( (a2 & 0xFFFFFFFB) == 0 )
  {
    v5 = *(unsigned __int16 *)(a1 + 192) - v4;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v6 = v5 + 1440;
    if ( v5 > 0 )
      v6 = v5;
    v7 = *(struct _TP_TIMER **)(a1 + 200);
    *(_QWORD *)&SystemTimeAsFileTime += 600000000LL * v6;
    SetThreadpoolTimer(v7, &SystemTimeAsFileTime, 0, 0x7530u);
    if ( a2 == 4 )
      goto LABEL_9;
  }
  if ( a2 == 1 )
  {
LABEL_9:
    v8 = *(unsigned __int16 *)(a1 + 194);
    v9 = *(unsigned __int16 *)(a1 + 192);
    v10 = *(unsigned __int16 *)(a1 + 196);
    v11 = v8 - v9;
    if ( (unsigned __int16)v9 >= (unsigned __int16)v8 )
    {
      if ( v10 >= v11 + 1440 )
        LOWORD(v10) = v8 - v9 + 1440;
    }
    else if ( v10 >= v11 )
    {
      LOWORD(v10) = v8 - v9;
    }
    v12 = v8 - (unsigned __int16)v10 - v4;
    if ( v12 > -1440 )
    {
      if ( v12 <= 0 )
        v12 += 1440;
    }
    else
    {
      v12 += 2880;
    }
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v13 = *(struct _TP_TIMER **)(a1 + 208);
    *(_QWORD *)&SystemTimeAsFileTime += 600000000LL * v12;
    SetThreadpoolTimer(v13, &SystemTimeAsFileTime, 0, 0x7530u);
  }
  if ( ((a2 - 2) & 0xFFFFFFFD) == 0 )
  {
    v14 = *(unsigned __int16 *)(a1 + 194) - v4;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v15 = v14 + 1440;
    if ( v14 > 0 )
      v15 = v14;
    v16 = *(struct _TP_TIMER **)(a1 + 216);
    *(_QWORD *)&SystemTimeAsFileTime += 600000000LL * v15;
    SetThreadpoolTimer(v16, &SystemTimeAsFileTime, 0, 0x7530u);
  }
  if ( a2 == 3 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v17 = *(struct _TP_TIMER **)(a1 + 224);
    *(_QWORD *)&SystemTimeAsFileTime += 600000000LL;
    SetThreadpoolTimer(v17, &SystemTimeAsFileTime, 0, 0x7530u);
  }
}

```

## disassembly

```asm
0x1800731a4  mov     [rsp-18h+arg_8], rbx
0x1800731a9  mov     [rsp-18h+arg_10], rsi
0x1800731ae  push    rbp
0x1800731af  push    rdi
0x1800731b0  push    r14
0x1800731b2  mov     rbp, rsp
0x1800731b5  sub     rsp, 40h
0x1800731b9  mov     rax, cs:__security_cookie
0x1800731c0  xor     rax, rsp
0x1800731c3  mov     [rbp+var_8], rax
0x1800731c7  mov     rdi, rcx
0x1800731ca  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800731d2  xorps   xmm0, xmm0
0x1800731d5  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800731d9  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800731dd  mov     esi, edx
0x1800731df  call    cs:__imp_GetLocalTime
0x1800731e6  nop     dword ptr [rax+rax+00h]
0x1800731eb  movzx   eax, [rbp+SystemTime.wHour]
0x1800731ef  imul    ecx, eax, 3Ch ; '<'
0x1800731f2  add     cx, [rbp+SystemTime.wMinute]
0x1800731f6  movzx   r14d, cx
0x1800731fa  test    esi, 0FFFFFFFBh
0x180073200  jnz     short loc_180073260
0x180073202  movzx   ebx, word ptr [rdi+0C0h]
0x180073209  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18007320d  sub     ebx, r14d
0x180073210  call    cs:__imp_GetSystemTimeAsFileTime
0x180073217  nop     dword ptr [rax+rax+00h]
0x18007321c  lea     eax, [rbx+5A0h]
0x180073222  test    ebx, ebx
0x180073224  mov     r9d, 7530h; msWindowLength
0x18007322a  lea     rdx, [rbp+SystemTimeAsFileTime]; pftDueTime
0x18007322e  cmovg   eax, ebx
0x180073231  xor     r8d, r8d; msPeriod
0x180073234  imul    eax, 0EA60h
0x18007323a  movsxd  rcx, eax
0x18007323d  imul    rax, rcx, 2710h
0x180073244  mov     rcx, [rdi+0C8h]; pti
0x18007324b  add     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18007324f  call    cs:__imp_SetThreadpoolTimer
0x180073256  nop     dword ptr [rax+rax+00h]
0x18007325b  cmp     esi, 4
0x18007325e  jz      short loc_18007329C
0x180073260  cmp     esi, 1
0x180073263  jz      short loc_18007329C
0x180073265  lea     eax, [rsi-2]
0x180073268  test    eax, 0FFFFFFFDh
0x18007326d  jz      loc_180073331
0x180073273  cmp     esi, 3
0x180073276  jz      loc_1800733C4
0x18007327c  mov     rcx, [rbp+var_8]
0x180073280  xor     rcx, rsp; StackCookie
0x180073283  call    __security_check_cookie
0x180073288  mov     rbx, [rsp+40h+arg_8]
0x18007328d  mov     rsi, [rsp+40h+arg_10]
0x180073292  add     rsp, 40h
0x180073296  pop     r14
0x180073298  pop     rdi
0x180073299  pop     rbp
0x18007329a  retn
0x18007329c  movzx   ebx, word ptr [rdi+0C2h]
0x1800732a3  movzx   r8d, word ptr [rdi+0C0h]
0x1800732ab  mov     edx, ebx
0x1800732ad  movzx   ecx, word ptr [rdi+0C4h]
0x1800732b4  sub     edx, r8d
0x1800732b7  cmp     r8w, bx
0x1800732bb  jnb     loc_18007338F
0x1800732c1  movzx   eax, bx
0x1800732c4  sub     ax, r8w
0x1800732c8  cmp     ecx, edx
0x1800732ca  cmovge  cx, ax
0x1800732ce  movzx   eax, cx
0x1800732d1  sub     ebx, eax
0x1800732d3  sub     ebx, r14d
0x1800732d6  cmp     ebx, 0FFFFFA60h
0x1800732dc  jg      loc_1800733B1
0x1800732e2  add     ebx, 0B40h
0x1800732e8  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800732ec  call    cs:__imp_GetSystemTimeAsFileTime
0x1800732f3  nop     dword ptr [rax+rax+00h]
0x1800732f8  imul    eax, ebx, 0EA60h
0x1800732fe  lea     rdx, [rbp+SystemTimeAsFileTime]; pftDueTime
0x180073302  mov     r9d, 7530h; msWindowLength
0x180073308  xor     r8d, r8d; msPeriod
0x18007330b  movsxd  rcx, eax
0x18007330e  imul    rax, rcx, 2710h
0x180073315  mov     rcx, [rdi+0D0h]; pti
0x18007331c  add     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180073320  call    cs:__imp_SetThreadpoolTimer
0x180073327  nop     dword ptr [rax+rax+00h]
0x18007332c  jmp     loc_180073265
0x180073331  movzx   ebx, word ptr [rdi+0C2h]
0x180073338  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18007333c  sub     ebx, r14d
0x18007333f  call    cs:__imp_GetSystemTimeAsFileTime
0x180073346  nop     dword ptr [rax+rax+00h]
0x18007334b  test    ebx, ebx
0x18007334d  lea     eax, [rbx+5A0h]
0x180073353  mov     r9d, 7530h; msWindowLength
0x180073359  lea     rdx, [rbp+SystemTimeAsFileTime]; pftDueTime
0x18007335d  cmovg   eax, ebx
0x180073360  xor     r8d, r8d; msPeriod
0x180073363  imul    eax, 0EA60h
0x180073369  movsxd  rcx, eax
0x18007336c  imul    rax, rcx, 2710h
0x180073373  mov     rcx, [rdi+0D8h]; pti
0x18007337a  add     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18007337e  call    cs:__imp_SetThreadpoolTimer
0x180073385  nop     dword ptr [rax+rax+00h]
0x18007338a  jmp     loc_180073273
0x18007338f  lea     eax, [rdx+5A0h]
0x180073395  cmp     ecx, eax
0x180073397  jl      loc_1800732CE
0x18007339d  movzx   eax, bx
0x1800733a0  mov     ecx, 5A0h
0x1800733a5  sub     ax, r8w
0x1800733a9  add     cx, ax
0x1800733ac  jmp     loc_1800732CE
0x1800733b1  test    ebx, ebx
0x1800733b3  jg      loc_1800732E8
0x1800733b9  add     ebx, 5A0h
0x1800733bf  jmp     loc_1800732E8
0x1800733c4  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800733c8  call    cs:__imp_GetSystemTimeAsFileTime
0x1800733cf  nop     dword ptr [rax+rax+00h]
0x1800733d4  mov     rcx, [rdi+0E0h]; pti
0x1800733db  lea     rdx, [rbp+SystemTimeAsFileTime]; pftDueTime
0x1800733df  add     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 23C34600h
0x1800733e7  mov     r9d, 7530h; msWindowLength
0x1800733ed  xor     r8d, r8d; msPeriod
0x1800733f0  call    cs:__imp_SetThreadpoolTimer
0x1800733f7  nop     dword ptr [rax+rax+00h]
0x1800733fc  jmp     loc_18007327C
```
