# CRepubCacheBackingStore::InitializeTTLExpiryPruning(void)

- ea: `0x18004866c`
- end: `0x18004884d`
- name: `?InitializeTTLExpiryPruning@CRepubCacheBackingStore@@QEAAKXZ`
- size: `481`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180047224`
- `0x18004fe1c`
- `0x18006f000`

## callees

- `0x180004374`
- `0x180008290`
- `0x1800082d0`
- `0x18004866c`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048728`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800486f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800486f7`
- `KERNEL32!GetSystemTime` at `0x180048710`
- `KERNEL32!GetSystemTime` at `0x180048710`
- `KERNEL32!SystemTimeToFileTime` at `0x18004871e`
- `KERNEL32!SystemTimeToFileTime` at `0x18004871e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800487ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004882c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800487ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004882c`

## pseudocode

```c
__int64 __fastcall CRepubCacheBackingStore::InitializeTTLExpiryPruning(CRepubCacheBackingStore *this)
{
  CHostedCacheMsgEncoding *v2; // rcx
  unsigned __int64 v3; // rdi
  int wHour; // esi
  int wMinute; // r14d
  DWORD LastError; // eax
  DWORD v7; // ebx
  unsigned __int64 v9; // rdi
  struct _TP_TIMER *v10; // rcx
  struct _TP_TIMER *v11; // rcx
  struct _FILETIME FileTime; // [rsp+20h] [rbp-38h] BYREF
  struct _FILETIME pftDueTime; // [rsp+28h] [rbp-30h] BYREF
  struct _FILETIME v14; // [rsp+30h] [rbp-28h]
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-20h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      234,
      WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
      *((unsigned int *)this + 12586));
    v2 = WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)this + 12586) )
  {
    if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v2 + 108) & 4) != 0
      && *((_BYTE *)v2 + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)v2 + 12), 237, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
    }
    v11 = (struct _TP_TIMER *)*((_QWORD *)this + 6324);
    if ( v11 )
      SetThreadpoolTimer(v11, 0, 0, 0);
    return 0;
  }
  FileTime = 0;
  pftDueTime = 0;
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v3 = *((unsigned int *)this + 12586);
  wHour = SystemTime.wHour;
  wMinute = SystemTime.wMinute;
  GetSystemTime(&SystemTime);
  if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    v9 = v3 - (unsigned int)(wMinute + 60 * wHour) % v3;
    v14 = FileTime;
    if ( (signed __int64)(*(_QWORD *)&FileTime + 600000000 * v9) < *(_QWORD *)&FileTime )
      return 534;
    v10 = (struct _TP_TIMER *)*((_QWORD *)this + 6324);
    pftDueTime = (struct _FILETIME)(*(_QWORD *)&FileTime + 600000000 * v9);
    SetThreadpoolTimer(v10, &pftDueTime, 0, 0);
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 236, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
    }
    return 0;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 235, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, LastError);
  }
  return v7;
}

```

## disassembly

```asm
0x18004866c  push    rbp
0x18004866e  push    rbx
0x18004866f  push    rsi
0x180048670  push    rdi
0x180048671  push    r13
0x180048673  push    r14
0x180048675  mov     rbp, rsp
0x180048678  sub     rsp, 58h
0x18004867c  mov     rax, cs:__security_cookie
0x180048683  xor     rax, rsp
0x180048686  mov     [rbp+var_10], rax
0x18004868a  mov     rbx, rcx
0x18004868d  mov     rcx, cs:WPP_GLOBAL_Control
0x180048694  lea     r13, WPP_GLOBAL_Control
0x18004869b  cmp     rcx, r13
0x18004869e  jz      short loc_1800486CF
0x1800486a0  test    byte ptr [rcx+6Ch], 4
0x1800486a4  jz      short loc_1800486CF
0x1800486a6  cmp     byte ptr [rcx+69h], 4
0x1800486aa  jb      short loc_1800486CF
0x1800486ac  mov     r9d, [rbx+0C4A8h]
0x1800486b3  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x1800486ba  mov     rcx, [rcx+60h]
0x1800486be  mov     edx, 0EAh
0x1800486c3  call    WPP_SF_d
0x1800486c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800486cf  cmp     dword ptr [rbx+0C4A8h], 0
0x1800486d6  jbe     loc_1800487F2
0x1800486dc  xorps   xmm0, xmm0
0x1800486df  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x1800486e7  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800486eb  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], 0
0x1800486f3  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800486f7  call    cs:__imp_GetLocalTime
0x1800486fd  mov     edi, [rbx+0C4A8h]
0x180048703  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180048707  movzx   esi, [rbp+SystemTime.wHour]
0x18004870b  movzx   r14d, [rbp+SystemTime.wMinute]
0x180048710  call    cs:__imp_GetSystemTime
0x180048716  lea     rdx, [rbp+FileTime]; lpFileTime
0x18004871a  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18004871e  call    cs:__imp_SystemTimeToFileTime
0x180048724  test    eax, eax
0x180048726  jnz     short loc_180048767
0x180048728  call    cs:__imp_GetLastError
0x18004872e  mov     ebx, eax
0x180048730  mov     rcx, cs:WPP_GLOBAL_Control
0x180048737  cmp     rcx, r13
0x18004873a  jz      short loc_180048760
0x18004873c  test    byte ptr [rcx+6Ch], 4
0x180048740  jz      short loc_180048760
0x180048742  cmp     byte ptr [rcx+69h], 1
0x180048746  jb      short loc_180048760
0x180048748  mov     rcx, [rcx+60h]
0x18004874c  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180048753  mov     edx, 0EBh
0x180048758  mov     r9d, eax
0x18004875b  call    WPP_SF_d
0x180048760  mov     eax, ebx
0x180048762  jmp     loc_180048834
0x180048767  xor     edx, edx
0x180048769  imul    eax, esi, 3Ch ; '<'
0x18004876c  add     eax, r14d
0x18004876f  div     rdi
0x180048772  mov     eax, [rbp+FileTime.dwHighDateTime]
0x180048775  sub     rdi, rdx
0x180048778  mov     dword ptr [rbp+var_28+4], eax
0x18004877b  mov     eax, [rbp+FileTime.dwLowDateTime]
0x18004877e  imul    rdx, rdi, 23C34600h
0x180048785  mov     dword ptr [rbp+var_28], eax
0x180048788  add     rdx, [rbp+var_28]
0x18004878c  cmp     rdx, [rbp+var_28]
0x180048790  jge     short loc_18004879C
0x180048792  mov     eax, 216h
0x180048797  jmp     loc_180048834
0x18004879c  mov     rcx, [rbx+0C5A0h]; pti
0x1800487a3  mov     rax, rdx
0x1800487a6  sar     rax, 20h
0x1800487aa  xor     r9d, r9d; msWindowLength
0x1800487ad  mov     [rbp+pftDueTime.dwLowDateTime], edx
0x1800487b0  xor     r8d, r8d; msPeriod
0x1800487b3  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x1800487b7  mov     [rbp+pftDueTime.dwHighDateTime], eax
0x1800487ba  call    cs:__imp_SetThreadpoolTimer
0x1800487c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800487c7  cmp     rcx, r13
0x1800487ca  jz      short loc_180048832
0x1800487cc  test    byte ptr [rcx+6Ch], 4
0x1800487d0  jz      short loc_180048832
0x1800487d2  cmp     byte ptr [rcx+69h], 4
0x1800487d6  jb      short loc_180048832
0x1800487d8  mov     rcx, [rcx+60h]
0x1800487dc  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x1800487e3  mov     edx, 0ECh
0x1800487e8  mov     r9, rdi
0x1800487eb  call    WPP_SF_q
0x1800487f0  jmp     short loc_180048832
0x1800487f2  cmp     rcx, r13
0x1800487f5  jz      short loc_180048818
0x1800487f7  test    byte ptr [rcx+6Ch], 4
0x1800487fb  jz      short loc_180048818
0x1800487fd  cmp     byte ptr [rcx+69h], 4
0x180048801  jb      short loc_180048818
0x180048803  mov     rcx, [rcx+60h]
0x180048807  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004880e  mov     edx, 0EDh
0x180048813  call    WPP_SF_
0x180048818  mov     rcx, [rbx+0C5A0h]; pti
0x18004881f  test    rcx, rcx
0x180048822  jz      short loc_180048832
0x180048824  xor     r9d, r9d; msWindowLength
0x180048827  xor     r8d, r8d; msPeriod
0x18004882a  xor     edx, edx; pftDueTime
0x18004882c  call    cs:__imp_SetThreadpoolTimer
0x180048832  xor     eax, eax
0x180048834  mov     rcx, [rbp+var_10]
0x180048838  xor     rcx, rsp; StackCookie
0x18004883b  call    __security_check_cookie
0x180048840  add     rsp, 58h
0x180048844  pop     r14
0x180048846  pop     r13
0x180048848  pop     rdi
0x180048849  pop     rsi
0x18004884a  pop     rbx
0x18004884b  pop     rbp
0x18004884c  retn
```
