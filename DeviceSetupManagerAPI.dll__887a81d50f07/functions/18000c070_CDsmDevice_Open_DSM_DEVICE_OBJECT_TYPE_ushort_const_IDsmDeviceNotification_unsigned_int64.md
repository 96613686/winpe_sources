# CDsmDevice::Open(DSM_DEVICE_OBJECT_TYPE,ushort const *,IDsmDeviceNotification *,unsigned __int64)

- ea: `0x18000c070`
- end: `0x18000c20c`
- name: `?Open@CDsmDevice@@UEAAJW4DSM_DEVICE_OBJECT_TYPE@@PEBGPEAUIDsmDeviceNotification@@_K@Z`
- size: `412`
- prototype: `__int64 __fastcall(__int64, __int64, const unsigned __int16 *, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180009d20`
- `0x18000c070`
- `0x18000c32c`
- `0x18000ca1c`
- `0x18000ccb0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c0b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c1b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c0b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c1b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c0d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c1cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c0d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c1cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c175`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c175`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c162`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c162`

## pseudocode

```c
__int64 __fastcall CDsmDevice::Open(__int64 a1, __int64 a2, const unsigned __int16 *a3, __int64 a4, __int64 a5)
{
  int v8; // ebx
  char v9; // bp
  __int64 v10; // rcx
  __int64 v11; // rcx
  HANDLE Thread; // rax
  signed int LastError; // eax
  __int64 v14; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a3);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 64));
  v8 = -2147467259;
  v9 = 0;
  if ( *(_DWORD *)(a1 + 16) == 3 )
  {
    v9 = 1;
    *(_DWORD *)(a1 + 16) = 1;
  }
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 64));
  if ( v9 )
  {
    v8 = CDsmDevice::_DsmOpenDevice((CDsmDevice *)a1, a3);
    if ( v8 >= 0 )
    {
      v10 = *(_QWORD *)(a1 + 24);
      if ( v10 != a4 )
      {
        if ( a4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4);
        v11 = *(_QWORD *)(a1 + 24);
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        *(_QWORD *)(a1 + 24) = a4;
        v10 = a4;
      }
      *(_QWORD *)(a1 + 32) = a5;
      if ( v10 )
      {
        Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CDsmDevice::_DsmNotificationThreadEntry, (LPVOID)a1, 0, 0);
        *(_QWORD *)(a1 + 88) = Thread;
        if ( Thread )
        {
          v8 = 0;
        }
        else
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          if ( v8 < 0 )
          {
            v14 = *(_QWORD *)(a1 + 24);
            if ( v14 )
            {
              *(_QWORD *)(a1 + 24) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
            }
            CDsmDevice::_DsmCloseDevice((CDsmDevice *)a1);
          }
        }
      }
    }
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 64));
    *(_DWORD *)(a1 + 16) = (v8 >> 31) & 3;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 64));
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_78fa114223f63f16ae43484342ae4301_Traceguids,
      (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c070  push    rbx
0x18000c072  push    rbp
0x18000c073  push    rsi
0x18000c074  push    rdi
0x18000c075  push    r13
0x18000c077  push    r14
0x18000c079  push    r15
0x18000c07b  sub     rsp, 30h
0x18000c07f  mov     rsi, r9
0x18000c082  mov     r14, r8
0x18000c085  mov     rdi, rcx
0x18000c088  lea     r13, WPP_GLOBAL_Control
0x18000c08f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c096  cmp     rcx, r13
0x18000c099  jz      short loc_18000C0AD
0x18000c09b  test    byte ptr [rcx+1Ch], 1
0x18000c09f  jz      short loc_18000C0AD
0x18000c0a1  mov     r9, r8
0x18000c0a4  mov     rcx, [rcx+10h]
0x18000c0a8  call    WPP_SF_S
0x18000c0ad  lea     r15, [rdi+40h]
0x18000c0b1  mov     rcx, r15; SRWLock
0x18000c0b4  call    cs:__imp_AcquireSRWLockExclusive
0x18000c0ba  mov     ebx, 80004005h
0x18000c0bf  xor     bpl, bpl
0x18000c0c2  cmp     dword ptr [rdi+10h], 3
0x18000c0c6  jnz     short loc_18000C0D2
0x18000c0c8  mov     bpl, 1
0x18000c0cb  mov     dword ptr [rdi+10h], 1
0x18000c0d2  mov     rcx, r15; SRWLock
0x18000c0d5  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c0db  test    bpl, bpl
0x18000c0de  jz      loc_18000C1D1
0x18000c0e4  mov     rdx, r14; unsigned __int16 *
0x18000c0e7  mov     rcx, rdi; this
0x18000c0ea  call    ?_DsmOpenDevice@CDsmDevice@@AEAAJPEBG@Z; CDsmDevice::_DsmOpenDevice(ushort const *)
0x18000c0ef  mov     ebx, eax
0x18000c0f1  test    eax, eax
0x18000c0f3  js      loc_18000C1B4
0x18000c0f9  mov     rcx, [rdi+18h]
0x18000c0fd  cmp     rcx, rsi
0x18000c100  jz      short loc_18000C132
0x18000c102  test    rsi, rsi
0x18000c105  jz      short loc_18000C116
0x18000c107  mov     rax, [rsi]
0x18000c10a  mov     rcx, rsi
0x18000c10d  mov     rax, [rax+8]
0x18000c111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c116  mov     rcx, [rdi+18h]
0x18000c11a  test    rcx, rcx
0x18000c11d  jz      short loc_18000C12B
0x18000c11f  mov     rax, [rcx]
0x18000c122  mov     rax, [rax+10h]
0x18000c126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c12b  mov     [rdi+18h], rsi
0x18000c12f  mov     rcx, rsi
0x18000c132  mov     rax, [rsp+68h+arg_20]
0x18000c13a  mov     [rdi+20h], rax
0x18000c13e  test    rcx, rcx
0x18000c141  jz      short loc_18000C1B4
0x18000c143  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18000c14c  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18000c154  mov     r9, rdi; lpParameter
0x18000c157  lea     r8, ?_DsmNotificationThreadEntry@CDsmDevice@@CAKPEAX@Z; lpStartAddress
0x18000c15e  xor     edx, edx; dwStackSize
0x18000c160  xor     ecx, ecx; lpThreadAttributes
0x18000c162  call    cs:__imp_CreateThread
0x18000c168  mov     [rdi+58h], rax
0x18000c16c  test    rax, rax
0x18000c16f  jz      short loc_18000C175
0x18000c171  xor     ebx, ebx
0x18000c173  jmp     short loc_18000C1B4
0x18000c175  call    cs:__imp_GetLastError
0x18000c17b  mov     ebx, eax
0x18000c17d  test    eax, eax
0x18000c17f  jle     short loc_18000C18A
0x18000c181  movzx   ebx, ax
0x18000c184  or      ebx, 80070000h
0x18000c18a  test    ebx, ebx
0x18000c18c  jns     short loc_18000C1B4
0x18000c18e  mov     rcx, [rdi+18h]
0x18000c192  test    rcx, rcx
0x18000c195  jz      short loc_18000C1AC
0x18000c197  mov     qword ptr [rdi+18h], 0
0x18000c19f  mov     rax, [rcx]
0x18000c1a2  mov     rax, [rax+10h]
0x18000c1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1ab  nop
0x18000c1ac  mov     rcx, rdi; this
0x18000c1af  call    ?_DsmCloseDevice@CDsmDevice@@AEAAXXZ; CDsmDevice::_DsmCloseDevice(void)
0x18000c1b4  mov     rcx, r15; SRWLock
0x18000c1b7  call    cs:__imp_AcquireSRWLockExclusive
0x18000c1bd  mov     eax, ebx
0x18000c1bf  sar     eax, 1Fh
0x18000c1c2  and     eax, 3
0x18000c1c5  mov     [rdi+10h], eax
0x18000c1c8  mov     rcx, r15; SRWLock
0x18000c1cb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c1d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1d8  cmp     rcx, r13
0x18000c1db  jz      short loc_18000C1FB
0x18000c1dd  test    byte ptr [rcx+1Ch], 1
0x18000c1e1  jz      short loc_18000C1FB
0x18000c1e3  mov     edx, 0Bh
0x18000c1e8  mov     r9d, ebx
0x18000c1eb  lea     r8, WPP_78fa114223f63f16ae43484342ae4301_Traceguids
0x18000c1f2  mov     rcx, [rcx+10h]
0x18000c1f6  call    WPP_SF_D
0x18000c1fb  mov     eax, ebx
0x18000c1fd  add     rsp, 30h
0x18000c201  pop     r15
0x18000c203  pop     r14
0x18000c205  pop     r13
0x18000c207  pop     rdi
0x18000c208  pop     rsi
0x18000c209  pop     rbp
0x18000c20a  pop     rbx
0x18000c20b  retn
```
