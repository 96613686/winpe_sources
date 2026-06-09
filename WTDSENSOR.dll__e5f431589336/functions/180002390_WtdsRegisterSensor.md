# WtdsRegisterSensor

- ea: `0x180002390`
- end: `0x18000262f`
- name: `WtdsRegisterSensor`
- size: `671`
- prototype: `__int64 __fastcall(unsigned int, RTL_CONDITION_VARIABLE **, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x18000108c`
- `0x180001550`
- `0x180002390`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000248a`
- `ntdll!RtlAllocateHeap` at `0x18000248a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800024c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800024c6`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x1800024a4`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x1800024a4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180002455`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180002455`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002407`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000245f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000245f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025ff`

## pseudocode

```c
__int64 __fastcall WtdsRegisterSensor(unsigned int a1, RTL_CONDITION_VARIABLE **a2, __int64 a3, __int64 a4)
{
  HANDLE FileW; // rdi
  DWORD LastError; // ebx
  RTL_CONDITION_VARIABLE *Heap; // rax
  RTL_CONDITION_VARIABLE *v8; // rsi
  RTL_CONDITION_VARIABLE **v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int InBuffer; // [rsp+40h] [rbp-49h] BYREF
  DWORD v15; // [rsp+48h] [rbp-41h] BYREF
  unsigned int v16; // [rsp+4Ch] [rbp-3Dh] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-39h] BYREF
  __int64 v18; // [rsp+58h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+60h] [rbp-29h] BYREF
  DWORD *v20; // [rsp+80h] [rbp-9h]
  __int64 v21; // [rsp+88h] [rbp-1h]
  DWORD *v22; // [rsp+90h] [rbp+7h]
  __int64 v23; // [rsp+98h] [rbp+Fh]
  __int64 *v24; // [rsp+A0h] [rbp+17h]
  __int64 v25; // [rsp+A8h] [rbp+1Fh]

  InBuffer = a1;
  BytesReturned = 0;
  FileW = 0;
  if ( a1 > 9 || !a2 )
  {
    LastError = 87;
    goto LABEL_18;
  }
  FileW = CreateFileW(L"\\\\.\\DD9ADAAA-2585-41C5-9847-28A19BA9F344", 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    FileW = 0;
    if ( LastError )
      goto LABEL_18;
  }
  else
  {
    LastError = 0;
  }
  if ( !DeviceIoControl(FileW, 0x228801u, &InBuffer, 4u, 0, 0, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    if ( !LastError )
    {
LABEL_22:
      if ( FileW )
        CloseHandle(FileW);
      return LastError;
    }
LABEL_18:
    if ( (unsigned int)dword_180006000 > 2
      && (qword_180006010 & 0x400000000000LL) != 0
      && (*(_QWORD *)&qword_180006018 & 0x400000000000LL) == *(_QWORD *)&qword_180006018 )
    {
      v16 = InBuffer;
      v20 = &v16;
      v22 = &v15;
      v24 = &v18;
      v21 = 4;
      v15 = LastError;
      v23 = 4;
      v18 = 0x1000000;
      v25 = 8;
      sub_18000108C(*(__int64 *)&qword_180006018, (unsigned __int8 *)&word_18000476A, a3, a4, 5u, &v19);
    }
    goto LABEL_22;
  }
  Heap = (RTL_CONDITION_VARIABLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x38u);
  v8 = Heap;
  if ( !Heap )
  {
    LastError = 8;
    goto LABEL_18;
  }
  InitializeConditionVariable(Heap + 5);
  HIDWORD(v8[2].Ptr) = -559038737;
  v8[4].Ptr = FileW;
  LODWORD(v8[3].Ptr) = InBuffer;
  LOBYTE(v8[2].Ptr) = 1;
  EnterCriticalSection(&CriticalSection);
  v9 = (RTL_CONDITION_VARIABLE **)off_180006040;
  if ( *off_180006040 != (_UNKNOWN *)&off_180006038 )
    __fastfail(3u);
  v8->Ptr = &off_180006038;
  v8[1].Ptr = v9;
  *v9 = v8;
  off_180006040 = (_UNKNOWN **)v8;
  LeaveCriticalSection(&CriticalSection);
  if ( (unsigned int)dword_180006000 > 4 )
  {
    v15 = InBuffer;
    v20 = &v15;
    v22 = &v16;
    v24 = &v18;
    v21 = 4;
    v16 = (unsigned int)FileW;
    v23 = 4;
    v18 = (__int64)v8;
    v25 = 8;
    sub_18000108C(v10, (unsigned __int8 *)&byte_1800045E9, v11, v12, 5u, &v19);
  }
  *a2 = v8;
  return LastError;
}

```

## disassembly

```asm
0x180002390  mov     [rsp-8+arg_10], rbx
0x180002395  mov     [rsp-8+arg_18], rsi
0x18000239a  push    rbp
0x18000239b  push    rdi
0x18000239c  push    r13
0x18000239e  push    r14
0x1800023a0  push    r15
0x1800023a2  lea     rbp, [rsp-37h]
0x1800023a7  sub     rsp, 0C0h
0x1800023ae  mov     rax, cs:__security_cookie
0x1800023b5  xor     rax, rsp
0x1800023b8  mov     [rbp+57h+var_30], rax
0x1800023bc  xor     r15d, r15d
0x1800023bf  mov     [rbp+57h+InBuffer], ecx
0x1800023c2  mov     [rbp+57h+BytesReturned], r15d
0x1800023c6  mov     r14, rdx
0x1800023c9  mov     edi, r15d
0x1800023cc  lea     r13d, [r15+4]
0x1800023d0  cmp     ecx, 9
0x1800023d3  ja      loc_180002569
0x1800023d9  test    rdx, rdx
0x1800023dc  jz      loc_180002569
0x1800023e2  mov     [rsp+0E0h+hTemplateFile], r15; hTemplateFile
0x1800023e7  lea     r8d, [r15+3]; dwShareMode
0x1800023eb  mov     [rsp+0E0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1800023f0  lea     rcx, FileName; "\\\\.\\DD9ADAAA-2585-41C5-9847-28A19BA9"...
0x1800023f7  xor     r9d, r9d; lpSecurityAttributes
0x1800023fa  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180002402  mov     edx, 0C0000000h; dwDesiredAccess
0x180002407  call    cs:CreateFileW
0x18000240d  mov     rdi, rax
0x180002410  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002414  jnz     short loc_18000242B
0x180002416  call    cs:GetLastError
0x18000241c  mov     ebx, eax
0x18000241e  mov     edi, r15d
0x180002421  test    eax, eax
0x180002423  jnz     loc_18000256E
0x180002429  jmp     short loc_18000242E
0x18000242b  mov     ebx, r15d
0x18000242e  mov     [rsp+0E0h+lpOverlapped], r15; lpOverlapped
0x180002433  lea     rax, [rbp+57h+BytesReturned]
0x180002437  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x18000243c  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180002440  mov     [rsp+0E0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x180002445  mov     r9d, r13d; nInBufferSize
0x180002448  mov     edx, 228801h; dwIoControlCode
0x18000244d  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r15; lpOutBuffer
0x180002452  mov     rcx, rdi; hDevice
0x180002455  call    cs:DeviceIoControl
0x18000245b  test    eax, eax
0x18000245d  jnz     short loc_180002474
0x18000245f  call    cs:GetLastError
0x180002465  mov     ebx, eax
0x180002467  test    eax, eax
0x180002469  jz      loc_1800025F7
0x18000246f  jmp     loc_18000256E
0x180002474  mov     rcx, gs:60h
0x18000247d  mov     edx, 8; Flags
0x180002482  mov     rcx, [rcx+30h]; HeapHandle
0x180002486  lea     r8d, [rdx+30h]; Size
0x18000248a  call    cs:RtlAllocateHeap
0x180002490  mov     rsi, rax
0x180002493  test    rax, rax
0x180002496  jnz     short loc_1800024A0
0x180002498  lea     ebx, [rax+8]
0x18000249b  jmp     loc_18000256E
0x1800024a0  lea     rcx, [rax+28h]; ConditionVariable
0x1800024a4  call    cs:InitializeConditionVariable
0x1800024aa  mov     dword ptr [rsi+14h], 0DEADBEEFh
0x1800024b1  lea     rcx, CriticalSection; lpCriticalSection
0x1800024b8  mov     [rsi+20h], rdi
0x1800024bc  mov     eax, [rbp+57h+InBuffer]
0x1800024bf  mov     [rsi+18h], eax
0x1800024c2  mov     byte ptr [rsi+10h], 1
0x1800024c6  call    cs:EnterCriticalSection
0x1800024cc  mov     rax, cs:off_180006040
0x1800024d3  lea     rcx, off_180006038
0x1800024da  cmp     [rax], rcx
0x1800024dd  jz      short loc_1800024E6
0x1800024df  mov     ecx, 3
0x1800024e4  int     29h; Win8: RtlFailFast(ecx)
0x1800024e6  mov     [rsi], rcx
0x1800024e9  lea     rcx, CriticalSection; lpCriticalSection
0x1800024f0  mov     [rsi+8], rax
0x1800024f4  mov     [rax], rsi
0x1800024f7  mov     cs:off_180006040, rsi
0x1800024fe  call    cs:LeaveCriticalSection
0x180002504  mov     eax, cs:dword_180006000
0x18000250a  cmp     eax, r13d
0x18000250d  jbe     short loc_180002561
0x18000250f  mov     eax, [rbp+57h+InBuffer]
0x180002512  lea     rdx, byte_1800045E9; int
0x180002519  mov     [rbp+57h+var_98], eax
0x18000251c  lea     rax, [rbp+57h+var_98]
0x180002520  mov     [rbp+57h+var_60], rax
0x180002524  lea     rax, [rbp+57h+var_94]
0x180002528  mov     [rbp+57h+var_50], rax
0x18000252c  lea     rax, [rbp+57h+var_88]
0x180002530  mov     [rbp+57h+var_40], rax
0x180002534  lea     rax, [rbp+57h+var_80]
0x180002538  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; PEVENT_DATA_DESCRIPTOR
0x18000253d  mov     [rsp+0E0h+dwCreationDisposition], 5; ULONG
0x180002545  mov     [rbp+57h+var_58], r13
0x180002549  mov     [rbp+57h+var_94], edi
0x18000254c  mov     [rbp+57h+var_48], r13
0x180002550  mov     [rbp+57h+var_88], rsi
0x180002554  mov     [rbp+57h+var_38], 8
0x18000255c  call    sub_18000108C
0x180002561  mov     [r14], rsi
0x180002564  jmp     loc_180002605
0x180002569  mov     ebx, 57h ; 'W'
0x18000256e  mov     eax, cs:dword_180006000
0x180002574  cmp     eax, 2
0x180002577  jbe     short loc_1800025F7
0x180002579  mov     rcx, cs:qword_180006018; int
0x180002580  mov     rdx, 400000000000h
0x18000258a  mov     rax, cs:qword_180006010
0x180002591  test    rdx, rax
0x180002594  jz      short loc_1800025F7
0x180002596  mov     rax, rcx
0x180002599  and     rax, rdx
0x18000259c  cmp     rax, rcx
0x18000259f  jnz     short loc_1800025F7
0x1800025a1  mov     eax, [rbp+57h+InBuffer]
0x1800025a4  lea     rdx, word_18000476A; int
0x1800025ab  mov     [rbp+57h+var_94], eax
0x1800025ae  lea     rax, [rbp+57h+var_94]
0x1800025b2  mov     [rbp+57h+var_60], rax
0x1800025b6  lea     rax, [rbp+57h+var_98]
0x1800025ba  mov     [rbp+57h+var_50], rax
0x1800025be  lea     rax, [rbp+57h+var_88]
0x1800025c2  mov     [rbp+57h+var_40], rax
0x1800025c6  lea     rax, [rbp+57h+var_80]
0x1800025ca  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; PEVENT_DATA_DESCRIPTOR
0x1800025cf  mov     [rsp+0E0h+dwCreationDisposition], 5; ULONG
0x1800025d7  mov     [rbp+57h+var_58], r13
0x1800025db  mov     [rbp+57h+var_98], ebx
0x1800025de  mov     [rbp+57h+var_48], r13
0x1800025e2  mov     [rbp+57h+var_88], 1000000h
0x1800025ea  mov     [rbp+57h+var_38], 8
0x1800025f2  call    sub_18000108C
0x1800025f7  test    rdi, rdi
0x1800025fa  jz      short loc_180002605
0x1800025fc  mov     rcx, rdi; hObject
0x1800025ff  call    cs:CloseHandle
0x180002605  mov     eax, ebx
0x180002607  mov     rcx, [rbp+57h+var_30]
0x18000260b  xor     rcx, rsp; StackCookie
0x18000260e  call    __security_check_cookie
0x180002613  lea     r11, [rsp+0E0h+var_20]
0x18000261b  mov     rbx, [r11+40h]
0x18000261f  mov     rsi, [r11+48h]
0x180002623  mov     rsp, r11
0x180002626  pop     r15
0x180002628  pop     r14
0x18000262a  pop     r13
0x18000262c  pop     rdi
0x18000262d  pop     rbp
0x18000262e  retn
```
