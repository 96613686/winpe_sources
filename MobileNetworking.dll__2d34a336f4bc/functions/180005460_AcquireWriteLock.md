# AcquireWriteLock

- ea: `0x180005460`
- end: `0x1800055ad`
- name: `AcquireWriteLock`
- size: `333`
- prototype: `DWORD __fastcall(char, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005320`

## callees

- `0x180005460`
- `0x180008ff0`
- `0x180009130`
- `0x18000b628`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005479`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005479`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800054ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800054ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000555c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000555c`

## pseudocode

```c
DWORD __fastcall AcquireWriteLock(char a1, __int64 a2, __int64 a3, int a4)
{
  DWORD CurrentThreadId; // ebp
  int v9; // r8d
  PVOID *v10; // rcx
  int v11; // r8d
  DWORD result; // eax

  CurrentThreadId = GetCurrentThreadId();
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_ae89183a349339de188038c4f0a19280_Traceguids);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
      WPP_SF_Dsdqq((unsigned int)v10[2], 23, v9, CurrentThreadId, a3, a4, a1, a2);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  result = _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 48), 0xFFFFFFFF);
  if ( (int)(result - 1) >= 0 )
    result = WaitForSingleObject(*(HANDLE *)(a2 + 56), 0xFFFFFFFF);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    result = WPP_SF_Dsdqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v11, CurrentThreadId, a3, a4, a1, a2);
  *(_DWORD *)(a2 + 96) = CurrentThreadId;
  *(_DWORD *)(a2 + 64) = a4;
  *(_QWORD *)(a2 + 72) = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    return WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ae89183a349339de188038c4f0a19280_Traceguids, 0);
  return result;
}

```

## disassembly

```asm
0x180005460  push    rbx
0x180005462  push    rbp
0x180005463  push    rsi
0x180005464  push    rdi
0x180005465  push    r14
0x180005467  push    r15
0x180005469  sub     rsp, 48h
0x18000546d  mov     edi, r9d
0x180005470  mov     rsi, r8
0x180005473  mov     rbx, rdx
0x180005476  mov     r14, rcx
0x180005479  call    cs:__imp_GetCurrentThreadId
0x18000547f  mov     ebp, eax
0x180005481  mov     rcx, cs:WPP_GLOBAL_Control
0x180005488  lea     r15, WPP_GLOBAL_Control
0x18000548f  cmp     rcx, r15
0x180005492  jz      short loc_1800054A9
0x180005494  test    byte ptr [rcx+1Ch], 8
0x180005498  jnz     short loc_180005509
0x18000549a  cmp     rcx, r15
0x18000549d  jz      short loc_1800054A9
0x18000549f  test    byte ptr [rcx+1Ch], 2
0x1800054a3  jnz     loc_18000552A
0x1800054a9  lea     rcx, [rbx+8]; lpCriticalSection
0x1800054ad  call    cs:__imp_EnterCriticalSection
0x1800054b3  mov     eax, 0FFFFFFFFh
0x1800054b8  lock xadd [rbx+30h], eax
0x1800054bd  cmp     eax, 1
0x1800054c0  jns     loc_180005553
0x1800054c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054cd  cmp     rcx, r15
0x1800054d0  jz      short loc_1800054DC
0x1800054d2  test    byte ptr [rcx+1Ch], 2
0x1800054d6  jnz     loc_180005567
0x1800054dc  mov     [rbx+60h], ebp
0x1800054df  mov     [rbx+40h], edi
0x1800054e2  mov     [rbx+48h], rsi
0x1800054e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054ed  cmp     rcx, r15
0x1800054f0  jz      short loc_1800054FC
0x1800054f2  test    byte ptr [rcx+1Ch], 8
0x1800054f6  jnz     loc_180005590
0x1800054fc  add     rsp, 48h
0x180005500  pop     r15
0x180005502  pop     r14
0x180005504  pop     rdi
0x180005505  pop     rsi
0x180005506  pop     rbp
0x180005507  pop     rbx
0x180005508  retn
0x180005509  mov     rcx, [rcx+10h]
0x18000550d  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x180005514  mov     edx, 16h
0x180005519  call    WPP_SF_
0x18000551e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005525  jmp     loc_18000549A
0x18000552a  mov     rcx, [rcx+10h]
0x18000552e  mov     edx, 17h
0x180005533  mov     [rsp+78h+var_40], rbx
0x180005538  mov     r9d, ebp
0x18000553b  mov     [rsp+78h+var_48], r14
0x180005540  mov     [rsp+78h+var_50], edi
0x180005544  mov     [rsp+78h+var_58], rsi
0x180005549  call    WPP_SF_Dsdqq
0x18000554e  jmp     loc_1800054A9
0x180005553  mov     rcx, [rbx+38h]; hHandle
0x180005557  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000555c  call    cs:__imp_WaitForSingleObject
0x180005562  jmp     loc_1800054C6
0x180005567  mov     rcx, [rcx+10h]
0x18000556b  mov     edx, 18h
0x180005570  mov     [rsp+78h+var_40], rbx
0x180005575  mov     r9d, ebp
0x180005578  mov     [rsp+78h+var_48], r14
0x18000557d  mov     [rsp+78h+var_50], edi
0x180005581  mov     [rsp+78h+var_58], rsi
0x180005586  call    WPP_SF_Dsdqq
0x18000558b  jmp     loc_1800054DC
0x180005590  mov     rcx, [rcx+10h]
0x180005594  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x18000559b  mov     edx, 19h
0x1800055a0  xor     r9d, r9d
0x1800055a3  call    WPP_SF_L
0x1800055a8  jmp     loc_1800054FC
```
