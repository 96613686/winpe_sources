# midiOutOpen

- ea: `0x180019920`
- end: `0x180019b25`
- name: `midiOutOpen`
- size: `517`
- prototype: `MMRESULT __stdcall(LPHMIDIOUT phmo, UINT uDeviceID, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180019920`
- `0x18001e5a0`

## callees

- `0x180001b70`
- `0x1800065d0`
- `0x180007d70`
- `0x18000aef0`
- `0x18000e0d0`
- `0x18000e828`
- `0x1800106c0`
- `0x180019920`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019a6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019a6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019ad9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019ad9`

## pseudocode

```c
MMRESULT __stdcall midiOutOpen(
        LPHMIDIOUT phmo,
        UINT uDeviceID,
        DWORD_PTR dwCallback,
        DWORD_PTR dwInstance,
        DWORD fdwOpen)
{
  MMRESULT result; // eax
  struct _MMDRV *v10; // rbx
  MMRESULT v11; // edi
  unsigned int v12; // esi
  UINT i; // ebx
  struct _RTL_CRITICAL_SECTION *v14; // rax
  struct _RTL_CRITICAL_SECTION *v15; // rdi
  MMRESULT v16; // esi
  LONG v17; // [rsp+30h] [rbp-41h] BYREF
  struct _MMDRV *v18; // [rsp+38h] [rbp-39h] BYREF
  _OWORD v19[3]; // [rsp+48h] [rbp-29h] BYREF

  v18 = 0;
  v17 = 0;
  memset(v19, 0, 44);
  if ( !phmo )
    return 11;
  if ( uDeviceID != -1 )
  {
    if ( (fdwOpen & 0x3FF3) == 0 )
      goto LABEL_4;
    return 10;
  }
  if ( (fdwOpen & 0xBFF3) != 0 )
    return 10;
LABEL_4:
  if ( dwCallback && !(unsigned int)ValidateCallbackType(dwCallback, HIWORD(fdwOpen)) )
    return 11;
  *phmo = 0;
  ClientUpdatePnpInfo();
  result = midiReferenceDriverById(&midioutdrvZ, uDeviceID, &v18, &v17);
  if ( result )
    return result;
  v10 = v18;
  if ( uDeviceID == -1 )
  {
    if ( !*((_QWORD *)v18 + 10) )
    {
      v11 = 6;
      mregDecUsagePtr(v18);
      v12 = wTotalMidiOutDevs;
      for ( i = 0; i < v12; ++i )
      {
        v11 = midiOutOpen(phmo, i, dwCallback, dwInstance, fdwOpen);
        if ( !v11 )
          break;
      }
      return v11;
    }
  }
  else if ( !*((_QWORD *)v18 + 10) )
  {
    v11 = 6;
LABEL_19:
    mregDecUsagePtr(v10);
    return v11;
  }
  v14 = NewHandle(3, *((_QWORD *)v18 + 12), 0x30u);
  v15 = v14;
  if ( !v14 )
  {
    v11 = 7;
    goto LABEL_19;
  }
  EnterCriticalSection(v14 - 1);
  v15[-2].RecursionCount |= 2u;
  LeaveCriticalSection(&HandleListCritSec);
  v15->LockCount = v17;
  v15->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v10;
  LODWORD(v15->LockSemaphore) = uDeviceID;
  HIDWORD(v15->LockSemaphore) = 0;
  *(_QWORD *)&v19[0] = v15;
  *(_QWORD *)&v19[1] = dwInstance;
  *((_QWORD *)&v19[0] + 1) = dwCallback;
  *((_QWORD *)&v19[1] + 1) = v15->DebugInfo[2].CriticalSection;
  v16 = (*((__int64 (__fastcall **)(_QWORD, __int64, HANDLE *, _OWORD *, _QWORD))v10 + 10))(
          (unsigned int)v15->LockCount,
          3,
          &v15->OwningThread,
          v19,
          fdwOpen);
  if ( !v16 )
    v15[-2].RecursionCount &= ~2u;
  LeaveCriticalSection(v15 - 1);
  if ( v16 )
  {
    FreeHandle((__int64)v15);
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)v10 + 23);
    *phmo = (HMIDIOUT)v15;
  }
  mregDecUsagePtr(v10);
  return v16;
}

```

## disassembly

```asm
0x180019920  push    rbp
0x180019922  push    rbx
0x180019923  push    rsi
0x180019924  push    rdi
0x180019925  push    r12
0x180019927  push    r13
0x180019929  push    r14
0x18001992b  push    r15
0x18001992d  lea     rbp, [rsp-17h]
0x180019932  sub     rsp, 88h
0x180019939  mov     rax, cs:__security_cookie
0x180019940  xor     rax, rsp
0x180019943  mov     [rbp+4Fh+var_48], rax
0x180019947  xorps   xmm0, xmm0
0x18001994a  xor     edi, edi
0x18001994c  mov     [rbp+4Fh+var_88], rdi
0x180019950  mov     r13, r9
0x180019953  mov     [rbp+4Fh+var_90], edi
0x180019956  mov     r12, r8
0x180019959  mov     esi, edx
0x18001995b  mov     r14, rcx
0x18001995e  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x180019962  movups  xmmword ptr [rbp+4Fh+var_68+0Ch], xmm0
0x180019966  movups  [rbp+4Fh+var_78], xmm0
0x18001996a  test    rcx, rcx
0x18001996d  jz      loc_180019B00
0x180019973  mov     r15d, [rbp+4Fh+fdwOpen]
0x180019977  movzx   eax, r15w
0x18001997b  cmp     edx, 0FFFFFFFFh
0x18001997e  jnz     loc_180019A1E
0x180019984  test    eax, 0FFFFBFF3h
0x180019989  jnz     loc_180019A29
0x18001998f  test    r12, r12
0x180019992  jz      short loc_1800199AA
0x180019994  mov     edx, r15d
0x180019997  mov     rcx, r12
0x18001999a  shr     edx, 10h
0x18001999d  call    ValidateCallbackType
0x1800199a2  test    eax, eax
0x1800199a4  jz      loc_180019B00
0x1800199aa  mov     [r14], rdi
0x1800199ad  call    ClientUpdatePnpInfo
0x1800199b2  lea     r9, [rbp+4Fh+var_90]
0x1800199b6  mov     edx, esi
0x1800199b8  lea     r8, [rbp+4Fh+var_88]
0x1800199bc  lea     rcx, midioutdrvZ
0x1800199c3  call    midiReferenceDriverById
0x1800199c8  test    eax, eax
0x1800199ca  jnz     loc_180019B05
0x1800199d0  mov     rbx, [rbp+4Fh+var_88]
0x1800199d4  cmp     esi, 0FFFFFFFFh
0x1800199d7  jnz     short loc_180019A33
0x1800199d9  cmp     [rbx+50h], rdi
0x1800199dd  jnz     short loc_180019A40
0x1800199df  mov     rcx, rbx; struct _MMDRV *
0x1800199e2  lea     edi, [rax+6]
0x1800199e5  call    mregDecUsagePtr
0x1800199ea  mov     esi, cs:wTotalMidiOutDevs
0x1800199f0  xor     ebx, ebx
0x1800199f2  test    esi, esi
0x1800199f4  jz      short loc_180019A17
0x1800199f6  mov     r9, r13; dwInstance
0x1800199f9  mov     [rsp+0C0h+var_A0], r15d; fdwOpen
0x1800199fe  mov     r8, r12; dwCallback
0x180019a01  mov     edx, ebx; uDeviceID
0x180019a03  mov     rcx, r14; phmo
0x180019a06  call    midiOutOpen
0x180019a0b  mov     edi, eax
0x180019a0d  test    eax, eax
0x180019a0f  jz      short loc_180019A17
0x180019a11  inc     ebx
0x180019a13  cmp     ebx, esi
0x180019a15  jb      short loc_1800199F6
0x180019a17  mov     eax, edi
0x180019a19  jmp     loc_180019B05
0x180019a1e  test    eax, 0FFFF3FF3h
0x180019a23  jz      loc_18001998F
0x180019a29  mov     eax, 0Ah
0x180019a2e  jmp     loc_180019B05
0x180019a33  cmp     [rbx+50h], rdi
0x180019a37  jnz     short loc_180019A40
0x180019a39  mov     edi, 6
0x180019a3e  jmp     short loc_180019A5E
0x180019a40  mov     rdx, [rbx+60h]
0x180019a44  mov     r8d, 30h ; '0'
0x180019a4a  lea     ecx, [r8-2Dh]
0x180019a4e  call    NewHandle
0x180019a53  mov     rdi, rax
0x180019a56  test    rax, rax
0x180019a59  jnz     short loc_180019A68
0x180019a5b  lea     edi, [rax+7]
0x180019a5e  mov     rcx, rbx; struct _MMDRV *
0x180019a61  call    mregDecUsagePtr
0x180019a66  jmp     short loc_180019A17
0x180019a68  lea     rcx, [rax-28h]; lpCriticalSection
0x180019a6c  call    cs:__imp_EnterCriticalSection
0x180019a72  or      dword ptr [rdi-44h], 2
0x180019a76  lea     rcx, HandleListCritSec; lpCriticalSection
0x180019a7d  call    cs:__imp_LeaveCriticalSection
0x180019a83  mov     eax, [rbp+4Fh+var_90]
0x180019a86  lea     r8, [rdi+10h]
0x180019a8a  mov     [rdi+8], eax
0x180019a8d  lea     r9, [rbp+4Fh+var_78]
0x180019a91  mov     [rdi], rbx
0x180019a94  mov     edx, 3
0x180019a99  mov     [rdi+18h], esi
0x180019a9c  mov     dword ptr [rdi+1Ch], 0
0x180019aa3  mov     qword ptr [rbp+4Fh+var_78], rdi
0x180019aa7  mov     qword ptr [rbp+4Fh+var_68], r13
0x180019aab  mov     qword ptr [rbp+4Fh+var_78+8], r12
0x180019aaf  mov     rax, [rdi]
0x180019ab2  mov     qword ptr [rsp+0C0h+var_A0], r15
0x180019ab7  mov     rcx, [rax+68h]
0x180019abb  mov     qword ptr [rbp+4Fh+var_68+8], rcx
0x180019abf  mov     ecx, [rdi+8]
0x180019ac2  mov     rax, [rbx+50h]
0x180019ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019acb  mov     esi, eax
0x180019acd  test    eax, eax
0x180019acf  jnz     short loc_180019AD5
0x180019ad1  and     dword ptr [rdi-44h], 0FFFFFFFDh
0x180019ad5  lea     rcx, [rdi-28h]; lpCriticalSection
0x180019ad9  call    cs:__imp_LeaveCriticalSection
0x180019adf  test    esi, esi
0x180019ae1  jz      short loc_180019AED
0x180019ae3  mov     rcx, rdi
0x180019ae6  call    FreeHandle
0x180019aeb  jmp     short loc_180019AF4
0x180019aed  lock inc dword ptr [rbx+5Ch]
0x180019af1  mov     [r14], rdi
0x180019af4  mov     rcx, rbx; struct _MMDRV *
0x180019af7  call    mregDecUsagePtr
0x180019afc  mov     eax, esi
0x180019afe  jmp     short loc_180019B05
0x180019b00  mov     eax, 0Bh
0x180019b05  mov     rcx, [rbp+4Fh+var_48]
0x180019b09  xor     rcx, rsp; StackCookie
0x180019b0c  call    __security_check_cookie
0x180019b11  add     rsp, 88h
0x180019b18  pop     r15
0x180019b1a  pop     r14
0x180019b1c  pop     r13
0x180019b1e  pop     r12
0x180019b20  pop     rdi
0x180019b21  pop     rsi
0x180019b22  pop     rbx
0x180019b23  pop     rbp
0x180019b24  retn
```
