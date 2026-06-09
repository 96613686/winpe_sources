# CStandardCollectorService::SendBytesToNamedPipe(ushort const *,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1400086fc`
- end: `0x140008a28`
- name: `?SendBytesToNamedPipe@CStandardCollectorService@@AEAAJPEBGAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `812`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140009030`

## callees

- `0x140001fac`
- `0x140003494`
- `0x1400086fc`
- `0x1400090c8`
- `0x14000918c`
- `0x1400093b4`
- `0x1400094c0`
- `0x140011b04`
- `0x1400137e0`
- `0x140014bc6`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14000880e`
- `KERNEL32!CreateEventW` at `0x14000880e`
- `KERNEL32!CreateNamedPipeW` at `0x1400087e7`
- `KERNEL32!CreateNamedPipeW` at `0x1400087e7`
- `KERNEL32!ConnectNamedPipe` at `0x1400088ad`
- `KERNEL32!ConnectNamedPipe` at `0x1400088ad`
- `KERNEL32!WaitForMultipleObjects` at `0x1400088e9`
- `KERNEL32!WaitForMultipleObjects` at `0x1400088e9`
- `KERNEL32!GetOverlappedResult` at `0x140008937`
- `KERNEL32!GetOverlappedResult` at `0x140008937`
- `KERNEL32!DisconnectNamedPipe` at `0x140008980`
- `KERNEL32!DisconnectNamedPipe` at `0x140008a0f`
- `KERNEL32!DisconnectNamedPipe` at `0x140008980`
- `KERNEL32!DisconnectNamedPipe` at `0x140008a0f`
- `KERNEL32!WriteFile` at `0x14000895b`
- `KERNEL32!WriteFile` at `0x14000895b`
- `KERNEL32!FlushFileBuffers` at `0x140008977`
- `KERNEL32!FlushFileBuffers` at `0x140008977`
- `KERNEL32!IsThreadpoolTimerSet` at `0x1400088fd`
- `KERNEL32!IsThreadpoolTimerSet` at `0x1400088fd`
- `KERNEL32!SetThreadpoolTimer` at `0x140008916`
- `KERNEL32!SetThreadpoolTimer` at `0x140008916`
- `KERNEL32!GetLastError` at `0x140008820`
- `KERNEL32!GetLastError` at `0x1400088bb`
- `KERNEL32!GetLastError` at `0x140008965`
- `KERNEL32!GetLastError` at `0x14000898e`
- `KERNEL32!GetLastError` at `0x140008820`
- `KERNEL32!GetLastError` at `0x1400088bb`
- `KERNEL32!GetLastError` at `0x140008965`
- `KERNEL32!GetLastError` at `0x14000898e`
- `KERNEL32!CloseHandle` at `0x1400089bb`
- `KERNEL32!CloseHandle` at `0x1400089ca`
- `KERNEL32!CloseHandle` at `0x1400089bb`
- `KERNEL32!CloseHandle` at `0x1400089ca`

## string_xrefs

- `0x1400087e0`: `\\.\pipe\StandardCollector.Service170`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CStandardCollectorService::SendBytesToNamedPipe(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // ecx
  unsigned int v7; // r8d
  signed int v8; // esi
  HANDLE v9; // rbx
  __int64 v10; // rdx
  HANDLE EventW; // rdi
  __int64 v12; // r8
  signed int LastError; // eax
  DWORD v14; // eax
  DWORD v15; // esi
  struct _TP_TIMER *v16; // rcx
  signed int v17; // eax
  HANDLE *lpHandles; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE *v19; // [rsp+48h] [rbp-B8h]
  HANDLE *v20; // [rsp+50h] [rbp-B0h]
  _QWORD Src[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v22[128]; // [rsp+70h] [rbp-90h] BYREF
  _OVERLAPPED Overlapped; // [rsp+F0h] [rbp-10h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+110h] [rbp+10h] BYREF
  DWORD NumberOfBytesTransferred[2]; // [rsp+118h] [rbp+18h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v27[2]; // [rsp+138h] [rbp+38h] BYREF

  if ( *(_QWORD *)(a3 + 8) - *(_QWORD *)a3 >= 0x100u )
    return 2147942413LL;
  v27[0] = &ATL::CSecurityDesc::`vftable';
  v27[1] = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  ATL::CSid::CSid(
    (ATL::CSid *)v22,
    (const struct _SID_IDENTIFIER_AUTHORITY *)&ATL::Sids::SecurityNTAuthority,
    2u,
    32,
    545);
  v8 = DiagHubCommon::Security::InitializeSecurityAttributes(
         v6,
         (const struct ATL::CSid *)v22,
         v7,
         (struct ATL::CSecurityAttributes *)&SecurityAttributes);
  ATL::CSid::~CSid((ATL::CSid *)v22);
  if ( v8 < 0 )
    goto LABEL_31;
  v9 = CreateNamedPipeW(
         L"\\\\.\\pipe\\StandardCollector.Service170",
         0x40080002u,
         0,
         1u,
         0x100u,
         0,
         0,
         &SecurityAttributes);
  *(_QWORD *)NumberOfBytesWritten = v9;
  if ( v9 == (HANDLE)-1LL )
  {
    v8 = -518979551;
    goto LABEL_29;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)NumberOfBytesTransferred = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v8 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v8 = LastError;
    goto LABEL_27;
  }
  Src[0] = *(_QWORD *)(a1 + 48);
  Src[1] = EventW;
  _mm_lfence();
  lpHandles = (HANDLE *)std::_Allocate<16,std::_Default_allocate_traits>(16, v10, v12);
  v20 = lpHandles + 2;
  memmove_0(lpHandles, Src, 0x10u);
  v19 = lpHandles + 2;
  *(_QWORD *)NumberOfBytesWritten = 0;
  std::_Tidy_guard<std::vector<void *>>::~_Tidy_guard<std::vector<void *>>(NumberOfBytesWritten);
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = EventW;
  while ( 1 )
  {
    if ( !ConnectNamedPipe(v9, &Overlapped) )
    {
      v14 = GetLastError();
      if ( v14 != 535 )
      {
        if ( v14 != 997 )
          goto LABEL_23;
        v15 = WaitForMultipleObjects(v19 - lpHandles, lpHandles, 0, 0xFFFFFFFF);
        v16 = *(struct _TP_TIMER **)(a1 + 192);
        if ( v16 && IsThreadpoolTimerSet(v16) )
          SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 192), 0, 0, 0);
        if ( !v15 )
        {
          v8 = 0;
          goto LABEL_26;
        }
        if ( v15 != 1 || !GetOverlappedResult(v9, &Overlapped, NumberOfBytesTransferred, 1) )
          goto LABEL_23;
      }
    }
    if ( !WriteFile(v9, *(LPCVOID *)a3, *(_DWORD *)(a3 + 8) - *(_DWORD *)a3, NumberOfBytesWritten, 0)
      && GetLastError() != 997 )
    {
      break;
    }
    FlushFileBuffers(v9);
LABEL_23:
    if ( !DisconnectNamedPipe(v9) )
      goto LABEL_24;
  }
  if ( DisconnectNamedPipe(v9) )
  {
    v8 = -518979547;
    goto LABEL_26;
  }
LABEL_24:
  v17 = GetLastError();
  v8 = (unsigned __int16)v17 | 0x80070000;
  if ( v17 <= 0 )
    v8 = v17;
LABEL_26:
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>(&lpHandles);
LABEL_27:
  if ( EventW )
    CloseHandle(EventW);
LABEL_29:
  if ( v9 )
    CloseHandle(v9);
LABEL_31:
  v27[0] = &ATL::CSecurityDesc::`vftable';
  ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400086fc  mov     [rsp-8+arg_8], rbx
0x140008701  mov     [rsp-8+arg_18], rsi
0x140008706  push    rbp
0x140008707  push    rdi
0x140008708  push    r12
0x14000870a  push    r14
0x14000870c  push    r15
0x14000870e  lea     rbp, [rsp-50h]
0x140008713  sub     rsp, 150h
0x14000871a  mov     rax, cs:__security_cookie
0x140008721  xor     rax, rsp
0x140008724  mov     [rbp+70h+var_28], rax
0x140008728  mov     r14, r8
0x14000872b  mov     r15, rcx
0x14000872e  mov     rax, [r8+8]
0x140008732  sub     rax, [r8]
0x140008735  mov     ebx, 100h
0x14000873a  cmp     rax, rbx
0x14000873d  jb      short loc_140008749
0x14000873f  mov     eax, 8007000Dh
0x140008744  jmp     loc_1400089E0
0x140008749  xorps   xmm0, xmm0
0x14000874c  xor     eax, eax
0x14000874e  movups  xmmword ptr [rbp+70h+SecurityAttributes.nLength], xmm0
0x140008752  movups  xmmword ptr [rbp+70h+SecurityAttributes.bInheritHandle], xmm0
0x140008756  lea     r12, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x14000875d  mov     qword ptr [rbp+70h+var_38], r12
0x140008761  mov     [rbp+70h+var_30], rax
0x140008765  mov     [rbp+70h+SecurityAttributes.nLength], eax
0x140008768  mov     [rbp+70h+SecurityAttributes.lpSecurityDescriptor], rax
0x14000876c  mov     [rbp+70h+SecurityAttributes.bInheritHandle], eax
0x14000876f  mov     [rsp+170h+nOutBufferSize], 221h
0x140008777  lea     r9d, [rax+20h]
0x14000877b  lea     r8d, [rax+2]; unsigned __int8
0x14000877f  lea     rdx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B; struct _SID_IDENTIFIER_AUTHORITY *
0x140008786  lea     rcx, [rsp+170h+var_100]; this
0x14000878b  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x140008790  nop
0x140008791  lea     r9, [rbp+70h+SecurityAttributes]; struct ATL::CSecurityAttributes *
0x140008795  lea     rdx, [rsp+170h+var_100]; struct ATL::CSid *
0x14000879a  call    ?InitializeSecurityAttributes@Security@DiagHubCommon@@SAJKAEBVCSid@ATL@@KPEAVCSecurityAttributes@4@@Z; DiagHubCommon::Security::InitializeSecurityAttributes(ulong,ATL::CSid const &,ulong,ATL::CSecurityAttributes *)
0x14000879f  mov     esi, eax
0x1400087a1  lea     rcx, [rsp+170h+var_100]; this
0x1400087a6  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1400087ab  test    esi, esi
0x1400087ad  js      loc_1400089D1
0x1400087b3  lea     rax, [rbp+70h+SecurityAttributes]
0x1400087b7  mov     [rsp+170h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1400087bc  mov     [rsp+170h+nDefaultTimeOut], 0; nDefaultTimeOut
0x1400087c4  mov     [rsp+170h+nInBufferSize], 0; nInBufferSize
0x1400087cc  mov     [rsp+170h+nOutBufferSize], ebx; nOutBufferSize
0x1400087d0  mov     edi, 1
0x1400087d5  mov     r9d, edi; nMaxInstances
0x1400087d8  xor     r8d, r8d; dwPipeMode
0x1400087db  mov     edx, 40080002h; dwOpenMode
0x1400087e0  lea     rcx, FileName; "\\\\.\\pipe\\StandardCollector.Service1"...
0x1400087e7  call    cs:__imp_CreateNamedPipeW
0x1400087ed  mov     rbx, rax
0x1400087f0  mov     qword ptr [rbp+70h+NumberOfBytesWritten], rax
0x1400087f4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400087f8  jnz     short loc_140008804
0x1400087fa  mov     esi, 0E1110021h
0x1400087ff  jmp     loc_1400089C2
0x140008804  xor     r9d, r9d; lpName
0x140008807  xor     r8d, r8d; bInitialState
0x14000880a  mov     edx, edi; bManualReset
0x14000880c  xor     ecx, ecx; lpEventAttributes
0x14000880e  call    cs:__imp_CreateEventW
0x140008814  mov     rdi, rax
0x140008817  mov     qword ptr [rbp+70h+NumberOfBytesTransferred], rax
0x14000881b  test    rax, rax
0x14000881e  jnz     short loc_140008839
0x140008820  call    cs:__imp_GetLastError
0x140008826  movzx   esi, ax
0x140008829  or      esi, 80070000h
0x14000882f  test    eax, eax
0x140008831  cmovle  esi, eax
0x140008834  jmp     loc_1400089B3
0x140008839  mov     rax, [r15+30h]
0x14000883d  mov     [rsp+170h+Src], rax
0x140008842  mov     [rsp+170h+var_110], rdi
0x140008847  lfence
0x14000884a  mov     r12d, 10h
0x140008850  mov     ecx, r12d
0x140008853  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x140008858  mov     [rsp+170h+lpHandles], rax
0x14000885d  lea     rsi, [rax+10h]
0x140008861  mov     [rsp+170h+var_120], rsi
0x140008866  mov     r8d, r12d; Size
0x140008869  lea     rdx, [rsp+170h+Src]; Src
0x14000886e  mov     rcx, rax; void *
0x140008871  call    memmove_0
0x140008876  mov     [rsp+170h+var_128], rsi
0x14000887b  mov     qword ptr [rbp+70h+NumberOfBytesWritten], 0
0x140008883  lea     rcx, [rbp+70h+NumberOfBytesWritten]
0x140008887  call    ??1?$_Tidy_guard@V?$vector@PEAXV?$allocator@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<void *>>::~_Tidy_guard<std::vector<void *>>(void)
0x14000888c  mov     [rbp+70h+Overlapped.Internal], 0
0x140008894  xorps   xmm0, xmm0
0x140008897  movdqu  xmmword ptr [rbp+70h+Overlapped.InternalHigh], xmm0
0x14000889c  mov     [rbp+70h+Overlapped.hEvent], rdi
0x1400088a0  mov     r12d, 3E5h
0x1400088a6  lea     rdx, [rbp+70h+Overlapped]; lpOverlapped
0x1400088aa  mov     rcx, rbx; hNamedPipe
0x1400088ad  call    cs:__imp_ConnectNamedPipe
0x1400088b3  test    eax, eax
0x1400088b5  jnz     loc_140008941
0x1400088bb  call    cs:__imp_GetLastError
0x1400088c1  cmp     eax, 217h
0x1400088c6  jz      short loc_140008941
0x1400088c8  cmp     eax, r12d
0x1400088cb  jnz     loc_14000897D
0x1400088d1  mov     rdx, [rsp+170h+lpHandles]; lpHandles
0x1400088d6  mov     rcx, [rsp+170h+var_128]
0x1400088db  sub     rcx, rdx
0x1400088de  sar     rcx, 3; nCount
0x1400088e2  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1400088e6  xor     r8d, r8d; bWaitAll
0x1400088e9  call    cs:__imp_WaitForMultipleObjects
0x1400088ef  mov     esi, eax
0x1400088f1  mov     rcx, [r15+0C0h]; pti
0x1400088f8  test    rcx, rcx
0x1400088fb  jz      short loc_14000891C
0x1400088fd  call    cs:__imp_IsThreadpoolTimerSet
0x140008903  test    eax, eax
0x140008905  jz      short loc_14000891C
0x140008907  xor     r9d, r9d; msWindowLength
0x14000890a  xor     r8d, r8d; msPeriod
0x14000890d  xor     edx, edx; pftDueTime
0x14000890f  mov     rcx, [r15+0C0h]; pti
0x140008916  call    cs:__imp_SetThreadpoolTimer
0x14000891c  test    esi, esi
0x14000891e  jz      loc_140008A08
0x140008924  cmp     esi, 1
0x140008927  jnz     short loc_14000897D
0x140008929  mov     r9d, esi; bWait
0x14000892c  lea     r8, [rbp+70h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x140008930  lea     rdx, [rbp+70h+Overlapped]; lpOverlapped
0x140008934  mov     rcx, rbx; hFile
0x140008937  call    cs:__imp_GetOverlappedResult
0x14000893d  test    eax, eax
0x14000893f  jz      short loc_14000897D
0x140008941  mov     r8d, [r14+8]
0x140008945  sub     r8d, [r14]; nNumberOfBytesToWrite
0x140008948  mov     qword ptr [rsp+170h+nOutBufferSize], 0; lpOverlapped
0x140008951  lea     r9, [rbp+70h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140008955  mov     rdx, [r14]; lpBuffer
0x140008958  mov     rcx, rbx; hFile
0x14000895b  call    cs:__imp_WriteFile
0x140008961  test    eax, eax
0x140008963  jnz     short loc_140008974
0x140008965  call    cs:__imp_GetLastError
0x14000896b  cmp     eax, r12d
0x14000896e  jnz     loc_140008A0C
0x140008974  mov     rcx, rbx; hFile
0x140008977  call    cs:__imp_FlushFileBuffers
0x14000897d  mov     rcx, rbx; hNamedPipe
0x140008980  call    cs:__imp_DisconnectNamedPipe
0x140008986  test    eax, eax
0x140008988  jnz     loc_1400088A6
0x14000898e  call    cs:__imp_GetLastError
0x140008994  movzx   esi, ax
0x140008997  or      esi, 80070000h
0x14000899d  test    eax, eax
0x14000899f  cmovle  esi, eax
0x1400089a2  lea     rcx, [rsp+170h+lpHandles]
0x1400089a7  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>(void)
0x1400089ac  lea     r12, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x1400089b3  test    rdi, rdi
0x1400089b6  jz      short loc_1400089C2
0x1400089b8  mov     rcx, rdi; hObject
0x1400089bb  call    cs:__imp_CloseHandle
0x1400089c1  nop
0x1400089c2  test    rbx, rbx
0x1400089c5  jz      short loc_1400089D1
0x1400089c7  mov     rcx, rbx; hObject
0x1400089ca  call    cs:__imp_CloseHandle
0x1400089d0  nop
0x1400089d1  mov     qword ptr [rbp+70h+var_38], r12
0x1400089d5  lea     rcx, [rbp+70h+var_38]; this
0x1400089d9  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x1400089de  mov     eax, esi
0x1400089e0  mov     rcx, [rbp+70h+var_28]
0x1400089e4  xor     rcx, rsp; StackCookie
0x1400089e7  call    __security_check_cookie
0x1400089ec  lea     r11, [rsp+170h+var_20]
0x1400089f4  mov     rbx, [r11+38h]
0x1400089f8  mov     rsi, [r11+48h]
0x1400089fc  mov     rsp, r11
0x1400089ff  pop     r15
0x140008a01  pop     r14
0x140008a03  pop     r12
0x140008a05  pop     rdi
0x140008a06  pop     rbp
0x140008a07  retn
0x140008a08  xor     esi, esi
0x140008a0a  jmp     short loc_1400089A2
0x140008a0c  mov     rcx, rbx; hNamedPipe
0x140008a0f  call    cs:__imp_DisconnectNamedPipe
0x140008a15  test    eax, eax
0x140008a17  jz      loc_14000898E
0x140008a1d  mov     esi, 0E1110025h
0x140008a22  jmp     loc_1400089A2
```
