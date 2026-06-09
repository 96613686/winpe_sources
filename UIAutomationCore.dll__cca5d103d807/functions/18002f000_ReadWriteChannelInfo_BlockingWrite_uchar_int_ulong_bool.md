# ReadWriteChannelInfo::BlockingWrite(uchar *,int,ulong,bool)

- ea: `0x18002f000`
- end: `0x18002f2db`
- name: `?BlockingWrite@ReadWriteChannelInfo@@UEAAJPEAEHK_N@Z`
- size: `731`
- prototype: `int(ReadWriteChannelInfo *__hidden this, unsigned __int8 *, int, unsigned int, bool)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18002f000`
- `0x18002f580`
- `0x1800fa0ec`
- `0x1800fa184`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002f02a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002f02a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f0fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f1a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f204`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f237`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f279`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f2c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f0fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f1a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f204`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f237`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f279`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f2c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f146`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002f0e2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002f0e2`

## string_xrefs

- `0x18002f12d`: `onecore\windows\accessibletech\uiautomationcore\overlappediomanager.cpp`
- `0x18002f18f`: `onecore\windows\accessibletech\uiautomationcore\overlappediomanager.cpp`
- `0x18002f1ef`: `onecore\windows\accessibletech\uiautomationcore\overlappediomanager.cpp`
- `0x18002f222`: `onecore\windows\accessibletech\uiautomationcore\overlappediomanager.cpp`
- `0x18002f264`: `onecore\windows\accessibletech\uiautomationcore\overlappediomanager.cpp`
- `0x18002f2ad`: `onecore\windows\accessibletech\uiautomationcore\overlappediomanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadWriteChannelInfo::BlockingWrite(
        RTL_SRWLOCK *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int a4,
        bool a5)
{
  RTL_SRWLOCK *v9; // rbx
  HANDLE *p_Ptr; // r15
  _QWORD **Ptr; // rcx
  DWORD v12; // esi
  const char *v13; // r9
  __int64 result; // rax
  signed int LastError; // eax
  bool v16; // sf
  int v17; // eax
  unsigned int v18; // edi
  int lpOverlapped; // [rsp+20h] [rbp-68h]
  int lpOverlappeda; // [rsp+20h] [rbp-68h]
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-58h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+38h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned int v24; // [rsp+90h] [rbp+8h]

  v9 = this + 7;
  AcquireSRWLockExclusive(this + 7);
  try
  {
    if ( !v9 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x121,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\overlappediomanager.cpp",
        (const char *)0x80004005LL,
        lpOverlapped);
      return 2147500037LL;
    }
    p_Ptr = &this[-4].Ptr;
    Ptr = (_QWORD **)this[6].Ptr;
    if ( Ptr && (*(unsigned int (__fastcall **)(_QWORD *))(*Ptr[8] + 32LL))(Ptr[8]) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12C,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\overlappediomanager.cpp",
        (const char *)0x80040201LL,
        lpOverlapped);
      ReleaseSRWLockExclusive(v9);
      return 2147746305LL;
    }
    if ( a3 > 0x2000000 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13B,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\overlappediomanager.cpp",
        (const char *)0x80040205LL,
        lpOverlapped);
      ReleaseSRWLockExclusive(v9);
      result = 2147746309LL;
    }
    else
    {
      if ( a5
        || ((*(void (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)this[4].Ptr + 40LL))(this[4].Ptr, a4),
            (*(unsigned __int8 (__fastcall **)(PVOID))(*(_QWORD *)this[4].Ptr + 48LL))(this[4].Ptr)) )
      {
        while ( 1 )
        {
          if ( !a3 )
            goto LABEL_12;
          v12 = a3;
          if ( a3 > 0xFFFF )
            v12 = 0xFFFF;
          memset(&Overlapped, 0, 24);
          Overlapped.hEvent = p_Ptr[7];
          NumberOfBytesWritten = 0;
          if ( !WriteFile(p_Ptr[9], a2, v12, &NumberOfBytesWritten, &Overlapped) )
            break;
LABEL_11:
          a2 += v12;
          a3 -= v12;
        }
        LastError = GetLastError();
        v24 = LastError;
        if ( LastError == 997 )
        {
          LastError = ReadWriteChannelInfo::WaitForOverlappedResult(
                        (ReadWriteChannelInfo *)p_Ptr,
                        p_Ptr[9],
                        &Overlapped,
                        &NumberOfBytesWritten,
                        a4);
        }
        else
        {
          v16 = LastError < 0;
          if ( LastError <= 0 )
          {
LABEL_17:
            if ( v16 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x15B,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\overlappediomanager.cpp",
                (const char *)(unsigned int)LastError,
                lpOverlappeda);
              ReleaseSRWLockExclusive(v9);
              return v24;
            }
            goto LABEL_11;
          }
          LastError = (unsigned __int16)LastError | 0x80070000;
        }
        v24 = LastError;
        v16 = LastError < 0;
        goto LABEL_17;
      }
      if ( a3 - 4 <= 0xFFFF )
      {
        v17 = ReadWriteChannelInfo::WriteSingleMessage((ReadWriteChannelInfo *)&this[-4], a2 + 4, a3 - 4, a4);
        v18 = v17;
        if ( v17 >= 0 )
        {
LABEL_12:
          ReleaseSRWLockExclusive(v9);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x172,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\overlappediomanager.cpp",
            (const char *)(unsigned int)v17,
            lpOverlapped);
          ReleaseSRWLockExclusive(v9);
          result = v18;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16F,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\overlappediomanager.cpp",
          (const char *)0x80040205LL,
          lpOverlapped);
        ReleaseSRWLockExclusive(v9);
        result = 2147746309LL;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x177,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\overlappediomanager.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x18002f000  mov     [rsp+arg_8], rbx
0x18002f005  mov     [rsp+arg_10], rsi
0x18002f00a  push    rdi
0x18002f00b  push    r12
0x18002f00d  push    r13
0x18002f00f  push    r14
0x18002f011  push    r15
0x18002f013  sub     rsp, 60h
0x18002f017  mov     r13d, r9d
0x18002f01a  mov     edi, r8d
0x18002f01d  mov     r14, rdx
0x18002f020  mov     rsi, rcx
0x18002f023  lea     rbx, [rcx+38h]
0x18002f027  mov     rcx, rbx; SRWLock
0x18002f02a  call    cs:__imp_AcquireSRWLockExclusive
0x18002f030  mov     [rsp+88h+arg_0], rbx
0x18002f038  test    rbx, rbx
0x18002f03b  jz      loc_18002F11F
0x18002f041  lea     r15, [rsi-20h]
0x18002f045  mov     rcx, [r15+50h]
0x18002f049  test    rcx, rcx
0x18002f04c  jnz     loc_18002F1C9
0x18002f052  cmp     edi, 2000000h
0x18002f058  ja      loc_18002F214
0x18002f05e  cmp     [rsp+88h+arg_20], 0
0x18002f066  jnz     short loc_18002F093
0x18002f068  mov     rcx, [rsi+20h]
0x18002f06c  mov     rax, [rcx]
0x18002f06f  mov     edx, r13d
0x18002f072  mov     rax, [rax+28h]
0x18002f076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f07b  mov     rcx, [rsi+20h]
0x18002f07f  mov     rax, [rcx]
0x18002f082  mov     rax, [rax+30h]
0x18002f086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f08b  test    al, al
0x18002f08d  jz      loc_18002F247
0x18002f093  mov     r12d, 0FFFFh
0x18002f099  test    edi, edi
0x18002f09b  jz      short loc_18002F0F5
0x18002f09d  mov     esi, edi
0x18002f09f  cmp     edi, r12d
0x18002f0a2  cmova   esi, r12d
0x18002f0a6  mov     [rsp+88h+Overlapped.Internal], 0
0x18002f0af  xorps   xmm0, xmm0
0x18002f0b2  movdqu  xmmword ptr [rsp+88h+Overlapped.InternalHigh], xmm0
0x18002f0b8  mov     rax, [r15+38h]
0x18002f0bc  mov     [rsp+88h+Overlapped.hEvent], rax
0x18002f0c1  mov     [rsp+88h+NumberOfBytesWritten], 0
0x18002f0c9  lea     rax, [rsp+88h+Overlapped]
0x18002f0ce  mov     qword ptr [rsp+88h+lpOverlapped], rax; lpOverlapped
0x18002f0d3  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002f0d8  mov     r8d, esi; nNumberOfBytesToWrite
0x18002f0db  mov     rdx, r14; lpBuffer
0x18002f0de  mov     rcx, [r15+48h]; hFile
0x18002f0e2  call    cs:__imp_WriteFile
0x18002f0e8  test    eax, eax
0x18002f0ea  jz      short loc_18002F146
0x18002f0ec  mov     eax, esi
0x18002f0ee  add     r14, rax
0x18002f0f1  sub     edi, esi
0x18002f0f3  jmp     short loc_18002F099
0x18002f0f5  test    rbx, rbx
0x18002f0f8  jz      short loc_18002F103
0x18002f0fa  mov     rcx, rbx; SRWLock
0x18002f0fd  call    cs:__imp_ReleaseSRWLockExclusive
0x18002f103  xor     eax, eax
0x18002f105  lea     r11, [rsp+88h+var_28]
0x18002f10a  mov     rbx, [r11+38h]
0x18002f10e  mov     rsi, [r11+40h]
0x18002f112  mov     rsp, r11
0x18002f115  pop     r15
0x18002f117  pop     r14
0x18002f119  pop     r13
0x18002f11b  pop     r12
0x18002f11d  pop     rdi
0x18002f11e  retn
0x18002f11f  mov     rcx, [rsp+88h]; this
0x18002f127  mov     r9d, 80004005h; char *
0x18002f12d  lea     r8, aOnecoreWindows_101; "onecore\\windows\\accessibletech\\uiaut"...
0x18002f134  mov     edx, 121h; void *
0x18002f139  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f13e  nop
0x18002f13f  mov     eax, 80004005h
0x18002f144  jmp     short loc_18002F105
0x18002f146  call    cs:__imp_GetLastError
0x18002f14c  mov     dword ptr [rsp+88h+arg_0], eax
0x18002f153  cmp     eax, 3E5h
0x18002f158  jnz     short loc_18002F1BB
0x18002f15a  mov     [rsp+88h+lpOverlapped], r13d; int
0x18002f15f  lea     r9, [rsp+88h+NumberOfBytesWritten]; unsigned int *
0x18002f164  lea     r8, [rsp+88h+Overlapped]; struct _OVERLAPPED *
0x18002f169  mov     rdx, [r15+48h]; void *
0x18002f16d  mov     rcx, r15; this
0x18002f170  call    ?WaitForOverlappedResult@ReadWriteChannelInfo@@AEAAJPEAXPEAU_OVERLAPPED@@PEAKK@Z; ReadWriteChannelInfo::WaitForOverlappedResult(void *,_OVERLAPPED *,ulong *,ulong)
0x18002f175  mov     dword ptr [rsp+88h+arg_0], eax
0x18002f17c  test    eax, eax
0x18002f17e  jns     loc_18002F0EC
0x18002f184  mov     rcx, [rsp+88h]; this
0x18002f18c  mov     r9d, eax; char *
0x18002f18f  lea     r8, aOnecoreWindows_101; "onecore\\windows\\accessibletech\\uiaut"...
0x18002f196  mov     edx, 15Bh; void *
0x18002f19b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f1a0  nop
0x18002f1a1  test    rbx, rbx
0x18002f1a4  jz      short loc_18002F1AF
0x18002f1a6  mov     rcx, rbx; SRWLock
0x18002f1a9  call    cs:__imp_ReleaseSRWLockExclusive
0x18002f1af  mov     eax, dword ptr [rsp+88h+arg_0]
0x18002f1b6  jmp     loc_18002F105
0x18002f1bb  test    eax, eax
0x18002f1bd  jle     short loc_18002F17E
0x18002f1bf  movzx   eax, ax
0x18002f1c2  or      eax, 80070000h
0x18002f1c7  jmp     short loc_18002F175
0x18002f1c9  mov     rcx, [rcx+40h]
0x18002f1cd  mov     rax, [rcx]
0x18002f1d0  mov     rax, [rax+20h]
0x18002f1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1d9  test    eax, eax
0x18002f1db  jz      loc_18002F052
0x18002f1e1  mov     rcx, [rsp+88h]; this
0x18002f1e9  mov     r9d, 80040201h; char *
0x18002f1ef  lea     r8, aOnecoreWindows_101; "onecore\\windows\\accessibletech\\uiaut"...
0x18002f1f6  mov     edx, 12Ch; void *
0x18002f1fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f200  nop
0x18002f201  mov     rcx, rbx; SRWLock
0x18002f204  call    cs:__imp_ReleaseSRWLockExclusive
0x18002f20a  mov     eax, 80040201h
0x18002f20f  jmp     loc_18002F105
0x18002f214  mov     rcx, [rsp+88h]; this
0x18002f21c  mov     r9d, 80040205h; char *
0x18002f222  lea     r8, aOnecoreWindows_101; "onecore\\windows\\accessibletech\\uiaut"...
0x18002f229  mov     edx, 13Bh; void *
0x18002f22e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f233  nop
0x18002f234  mov     rcx, rbx; SRWLock
0x18002f237  call    cs:__imp_ReleaseSRWLockExclusive
0x18002f23d  mov     eax, 80040205h
0x18002f242  jmp     loc_18002F105
0x18002f247  lea     r8d, [rdi-4]; unsigned int
0x18002f24b  mov     r12d, 0FFFFh
0x18002f251  cmp     r8d, r12d
0x18002f254  jbe     short loc_18002F289
0x18002f256  mov     rcx, [rsp+88h]; this
0x18002f25e  mov     r9d, 80040205h; char *
0x18002f264  lea     r8, aOnecoreWindows_101; "onecore\\windows\\accessibletech\\uiaut"...
0x18002f26b  mov     edx, 16Fh; void *
0x18002f270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f275  nop
0x18002f276  mov     rcx, rbx; SRWLock
0x18002f279  call    cs:__imp_ReleaseSRWLockExclusive
0x18002f27f  mov     eax, 80040205h
0x18002f284  jmp     loc_18002F105
0x18002f289  lea     rdx, [r14+4]; unsigned __int8 *
0x18002f28d  mov     r9d, r13d; unsigned int
0x18002f290  mov     rcx, r15; this
0x18002f293  call    ?WriteSingleMessage@ReadWriteChannelInfo@@AEAAJPEAEIK@Z; ReadWriteChannelInfo::WriteSingleMessage(uchar *,uint,ulong)
0x18002f298  mov     edi, eax
0x18002f29a  test    eax, eax
0x18002f29c  jns     loc_18002F0F5
0x18002f2a2  mov     rcx, [rsp+88h]; this
0x18002f2aa  mov     r9d, eax; char *
0x18002f2ad  lea     r8, aOnecoreWindows_101; "onecore\\windows\\accessibletech\\uiaut"...
0x18002f2b4  mov     edx, 172h; void *
0x18002f2b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f2be  nop
0x18002f2bf  mov     rcx, rbx; SRWLock
0x18002f2c2  call    cs:__imp_ReleaseSRWLockExclusive
0x18002f2c8  mov     eax, edi
0x18002f2ca  jmp     loc_18002F105
0x18002f2cf  mov     eax, dword ptr [rsp+88h+arg_0]
0x18002f2d6  jmp     loc_18002F105
```
