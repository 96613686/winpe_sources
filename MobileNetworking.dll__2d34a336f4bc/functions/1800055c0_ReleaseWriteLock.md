# ReleaseWriteLock

- ea: `0x1800055c0`
- end: `0x18000569f`
- name: `ReleaseWriteLock`
- size: `223`
- prototype: `void __fastcall(char, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005320`

## callees

- `0x1800055c0`
- `0x180008ff0`
- `0x180009130`
- `0x18000b628`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000565a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000565a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000561a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000561a`

## pseudocode

```c
void __fastcall ReleaseWriteLock(char a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v8; // rdi
  DWORD CurrentThreadId; // eax
  int v10; // r8d

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_ae89183a349339de188038c4f0a19280_Traceguids);
  _InterlockedIncrement((volatile signed __int32 *)(a2 + 48));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_Dsdqq(v8, 27, v10, CurrentThreadId, a3, a4, a1, a2);
  }
  *(_DWORD *)(a2 + 80) = a4;
  *(_QWORD *)(a2 + 88) = a3;
  *(_DWORD *)(a2 + 96) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_ae89183a349339de188038c4f0a19280_Traceguids, 0);
}

```

## disassembly

```asm
0x1800055c0  push    rbx
0x1800055c2  push    rbp
0x1800055c3  push    rsi
0x1800055c4  push    rdi
0x1800055c5  push    r14
0x1800055c7  push    r15
0x1800055c9  sub     rsp, 48h
0x1800055cd  mov     esi, r9d
0x1800055d0  mov     rbp, r8
0x1800055d3  mov     rbx, rdx
0x1800055d6  mov     r14, rcx
0x1800055d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055e0  lea     r15, WPP_GLOBAL_Control
0x1800055e7  cmp     rcx, r15
0x1800055ea  jz      short loc_1800055F2
0x1800055ec  test    byte ptr [rcx+1Ch], 8
0x1800055f0  jnz     short loc_18000563F
0x1800055f2  lock inc dword ptr [rbx+30h]
0x1800055f6  mov     rdi, cs:WPP_GLOBAL_Control
0x1800055fd  cmp     rdi, r15
0x180005600  jz      short loc_180005608
0x180005602  test    byte ptr [rdi+1Ch], 2
0x180005606  jnz     short loc_180005656
0x180005608  lea     rcx, [rbx+8]; lpCriticalSection
0x18000560c  mov     [rbx+50h], esi
0x18000560f  mov     [rbx+58h], rbp
0x180005613  mov     dword ptr [rbx+60h], 0
0x18000561a  call    cs:__imp_LeaveCriticalSection
0x180005620  mov     rcx, cs:WPP_GLOBAL_Control
0x180005627  cmp     rcx, r15
0x18000562a  jz      short loc_180005632
0x18000562c  test    byte ptr [rcx+1Ch], 8
0x180005630  jnz     short loc_180005685
0x180005632  add     rsp, 48h
0x180005636  pop     r15
0x180005638  pop     r14
0x18000563a  pop     rdi
0x18000563b  pop     rsi
0x18000563c  pop     rbp
0x18000563d  pop     rbx
0x18000563e  retn
0x18000563f  mov     rcx, [rcx+10h]
0x180005643  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x18000564a  mov     edx, 1Ah
0x18000564f  call    WPP_SF_
0x180005654  jmp     short loc_1800055F2
0x180005656  mov     rdi, [rdi+10h]
0x18000565a  call    cs:__imp_GetCurrentThreadId
0x180005660  mov     [rsp+78h+var_40], rbx
0x180005665  mov     edx, 1Bh
0x18000566a  mov     [rsp+78h+var_48], r14
0x18000566f  mov     r9d, eax
0x180005672  mov     [rsp+78h+var_50], esi
0x180005676  mov     rcx, rdi
0x180005679  mov     [rsp+78h+var_58], rbp
0x18000567e  call    WPP_SF_Dsdqq
0x180005683  jmp     short loc_180005608
0x180005685  mov     rcx, [rcx+10h]
0x180005689  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x180005690  mov     edx, 1Ch
0x180005695  xor     r9d, r9d
0x180005698  call    WPP_SF_L
0x18000569d  jmp     short loc_180005632
```
