# WinSAT::DiskProfiler::Start(WinSAT::OpStatus &,CSmartPtr<mlib::MEvent>)

- ea: `0x14006d680`
- end: `0x14006d938`
- name: `?Start@DiskProfiler@WinSAT@@UEAA_NAEAVOpStatus@2@V?$CSmartPtr@VMEvent@mlib@@@@@Z`
- size: `696`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x14000f858`
- `0x140016588`
- `0x140046f94`
- `0x14004fe00`
- `0x1400530a8`
- `0x14005ef98`
- `0x140060888`
- `0x14006d498`
- `0x14006d680`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14006d7d7`
- `KERNEL32!GetLastError` at `0x14006d88a`
- `KERNEL32!GetLastError` at `0x14006d7d7`
- `KERNEL32!GetLastError` at `0x14006d88a`
- `KERNEL32!CreateEventW` at `0x14006d72f`
- `KERNEL32!CreateEventW` at `0x14006d72f`
- `KERNEL32!ResumeThread` at `0x14006d8ef`
- `KERNEL32!ResumeThread` at `0x14006d8ef`
- `KERNEL32!GetThreadId` at `0x14006d8d9`
- `KERNEL32!GetThreadId` at `0x14006d8d9`
- `KERNEL32!SetProcessWorkingSetSize` at `0x14006d851`
- `KERNEL32!SetProcessWorkingSetSize` at `0x14006d851`
- `KERNEL32!GetProcessWorkingSetSize` at `0x14006d7cd`
- `KERNEL32!GetProcessWorkingSetSize` at `0x14006d7cd`
- `KERNEL32!GetCurrentProcess` at `0x14006d7ba`
- `KERNEL32!GetCurrentProcess` at `0x14006d842`
- `KERNEL32!GetCurrentProcess` at `0x14006d7ba`
- `KERNEL32!GetCurrentProcess` at `0x14006d842`
- `msvcrt!_beginthreadex` at `0x14006d878`
- `msvcrt!_beginthreadex` at `0x14006d878`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall WinSAT::DiskProfiler::Start(__int64 a1, __int64 a2, ULONG_PTR a3)
{
  char v6; // di
  __int64 v7; // rdx
  _QWORD *v8; // rax
  char *EventW; // rax
  int PhysicalDiskSize; // edx
  HANDLE CurrentProcess; // rax
  unsigned __int16 v12; // r9
  const unsigned __int16 *v13; // r8
  unsigned int v14; // eax
  SIZE_T v15; // rbx
  HANDLE v16; // rax
  void *v17; // rax
  ULONG_PTR MaximumWorkingSetSize; // [rsp+30h] [rbp-D0h] BYREF
  ULONG_PTR MinimumWorkingSetSize[3]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[256]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD LastError; // [rsp+250h] [rbp+150h]
  char v23; // [rsp+254h] [rbp+154h]
  __int64 v24; // [rsp+258h] [rbp+158h]

  MinimumWorkingSetSize[1] = a3;
  MinimumWorkingSetSize[0] = 0;
  MaximumWorkingSetSize = 0;
  WinSAT::DiskProfiler::Reset((WinSAT::DiskProfiler *)(a1 - 8), 0);
  v6 = 1;
  if ( !*(_QWORD *)(a1 + 184) )
  {
    LastError = 87;
    v24 = 0;
LABEL_3:
    v23 = 1;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    *(_DWORD *)(a1 + 56) = 3;
    v7 = 3;
LABEL_19:
    v13 = 0;
    goto LABEL_20;
  }
  v8 = *(_QWORD **)(a3 + 8);
  if ( v8 )
  {
    *(_QWORD *)(a1 + 88) = *v8;
  }
  else
  {
    EventW = (char *)CreateEventW(0, 0, 0, 0);
    *(_QWORD *)(a1 + 88) = EventW;
    if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      *(_DWORD *)(a1 + 236) = 1;
  }
  PhysicalDiskSize = GetPhysicalDiskSize(*(_DWORD *)(a1 + 204), (unsigned __int64 *)(a1 + 256));
  if ( PhysicalDiskSize < 0 )
  {
    v24 = 0;
    Buffer[0] = 0;
    if ( (PhysicalDiskSize & 0x1FFF0000) == 0x70000 )
    {
      LastError = (unsigned __int16)PhysicalDiskSize;
    }
    else
    {
      LastError = 8;
      if ( PhysicalDiskSize != -2147024882 )
        LastError = 1;
    }
    goto LABEL_3;
  }
  CurrentProcess = GetCurrentProcess();
  if ( GetProcessWorkingSetSize(CurrentProcess, MinimumWorkingSetSize, &MaximumWorkingSetSize) )
  {
    v14 = *(_DWORD *)(a1 + 220);
    if ( v14 <= *(_DWORD *)(a1 + 228) )
      v14 = *(_DWORD *)(a1 + 228);
    v15 = MaximumWorkingSetSize + 2LL * v14;
    v16 = GetCurrentProcess();
    SetProcessWorkingSetSize(v16, v15, v15);
    v17 = (void *)_beginthreadex(0, 0, WinSAT::DiskProfiler::DiskProfilerThreadProc, (void *)(a1 - 8), 4u, 0);
    *(_QWORD *)(a1 + 168) = v17;
    if ( v17 )
    {
      *(_DWORD *)(a1 + 176) = GetThreadId(v17);
      *(_DWORD *)(a1 + 56) = 4;
      ResumeThread(*(HANDLE *)(a1 + 168));
      *(_DWORD *)a2 = *(_DWORD *)(a1 + 56);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a2 + 8);
      *(_BYTE *)(a2 + 16) = 0;
      v6 = 0;
      goto LABEL_22;
    }
    LastError = GetLastError();
    v23 = 1;
    v24 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    v7 = 5;
    *(_DWORD *)(a1 + 56) = 5;
    goto LABEL_19;
  }
  LastError = GetLastError();
  v23 = 1;
  v24 = 0;
  mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
  *(_DWORD *)(a1 + 56) = 3;
  v13 = mlib::MUIStr_((mlib *)"base\\winsat\\storage\\diskprof.cpp", (const char *)0x1DA, 406, v12);
  v7 = *(unsigned int *)(a1 + 56);
LABEL_20:
  WinSAT::OpStatus::SetResult(a2, v7, v13, Buffer);
  WinSAT::StorageDevice::Close((WinSAT::StorageDevice *)(a1 + 280));
LABEL_22:
  CSmartPtr<mlib::MEvent>::Release(a3);
  return v6;
}

```

## disassembly

```asm
0x14006d680  push    rbp
0x14006d682  push    rbx
0x14006d683  push    rsi
0x14006d684  push    rdi
0x14006d685  push    r12
0x14006d687  push    r14
0x14006d689  push    r15
0x14006d68b  lea     rbp, [rsp-170h]
0x14006d693  sub     rsp, 270h
0x14006d69a  mov     rax, cs:__security_cookie
0x14006d6a1  xor     rax, rsp
0x14006d6a4  mov     [rbp+1A0h+var_40], rax
0x14006d6ab  mov     r15, r8
0x14006d6ae  mov     r14, rdx
0x14006d6b1  mov     rsi, rcx
0x14006d6b4  mov     [rsp+2A0h+var_260], r8
0x14006d6b9  mov     [rsp+2A0h+MinimumWorkingSetSize], 0
0x14006d6c2  mov     [rsp+2A0h+MaximumWorkingSetSize], 0
0x14006d6cb  xor     edx, edx; int
0x14006d6cd  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x14006d6d1  call    ?Reset@DiskProfiler@WinSAT@@AEAAXH@Z; WinSAT::DiskProfiler::Reset(int)
0x14006d6d6  mov     edi, 1
0x14006d6db  cmp     qword ptr [rsi+0B8h], 0
0x14006d6e3  jnz     short loc_14006D71C
0x14006d6e5  mov     [rbp+1A0h+var_50], 57h ; 'W'
0x14006d6ef  mov     [rbp+1A0h+var_48], 0
0x14006d6fa  mov     [rbp+1A0h+var_4C], dil
0x14006d701  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x14006d706  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14006d70b  mov     dword ptr [rsi+38h], 3
0x14006d712  mov     edx, 3
0x14006d717  jmp     loc_14006D8B8
0x14006d71c  mov     rax, [r15+8]
0x14006d720  test    rax, rax
0x14006d723  jnz     short loc_14006D74A
0x14006d725  xor     r9d, r9d; lpName
0x14006d728  xor     r8d, r8d; bInitialState
0x14006d72b  xor     edx, edx; bManualReset
0x14006d72d  xor     ecx, ecx; lpEventAttributes
0x14006d72f  call    cs:__imp_CreateEventW
0x14006d735  mov     [rsi+58h], rax
0x14006d739  dec     rax
0x14006d73c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14006d740  ja      short loc_14006D751
0x14006d742  mov     [rsi+0ECh], edi
0x14006d748  jmp     short loc_14006D751
0x14006d74a  mov     rax, [rax]
0x14006d74d  mov     [rsi+58h], rax
0x14006d751  lea     rdx, [rsi+100h]; unsigned __int64 *
0x14006d758  mov     ecx, [rsi+0CCh]; unsigned int
0x14006d75e  call    ?GetPhysicalDiskSize@@YAJKAEA_K@Z; GetPhysicalDiskSize(ulong,unsigned __int64 &)
0x14006d763  mov     edx, eax
0x14006d765  test    eax, eax
0x14006d767  jns     short loc_14006D7BA
0x14006d769  mov     [rbp+1A0h+var_48], 0
0x14006d774  xor     eax, eax
0x14006d776  mov     [rsp+2A0h+Buffer], ax
0x14006d77b  mov     ecx, edx
0x14006d77d  and     ecx, 1FFF0000h
0x14006d783  cmp     ecx, 70000h
0x14006d789  jnz     short loc_14006D799
0x14006d78b  movzx   eax, dx
0x14006d78e  mov     [rbp+1A0h+var_50], eax
0x14006d794  jmp     loc_14006D6FA
0x14006d799  cmp     edx, 8007000Eh
0x14006d79f  mov     [rbp+1A0h+var_50], 8
0x14006d7a9  jz      loc_14006D6FA
0x14006d7af  mov     [rbp+1A0h+var_50], edi
0x14006d7b5  jmp     loc_14006D6FA
0x14006d7ba  call    cs:__imp_GetCurrentProcess
0x14006d7c0  mov     rcx, rax; hProcess
0x14006d7c3  lea     r8, [rsp+2A0h+MaximumWorkingSetSize]; lpMaximumWorkingSetSize
0x14006d7c8  lea     rdx, [rsp+2A0h+MinimumWorkingSetSize]; lpMinimumWorkingSetSize
0x14006d7cd  call    cs:__imp_GetProcessWorkingSetSize
0x14006d7d3  test    eax, eax
0x14006d7d5  jnz     short loc_14006D826
0x14006d7d7  call    cs:__imp_GetLastError
0x14006d7dd  mov     [rbp+1A0h+var_50], eax
0x14006d7e3  mov     [rbp+1A0h+var_4C], dil
0x14006d7ea  mov     [rbp+1A0h+var_48], 0
0x14006d7f5  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x14006d7fa  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14006d7ff  mov     dword ptr [rsi+38h], 3
0x14006d806  mov     edx, 1DAh; char *
0x14006d80b  lea     r8d, [rdx-44h]; int
0x14006d80f  lea     rcx, aBaseWinsatStor; "base\\winsat\\storage\\diskprof.cpp"
0x14006d816  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14006d81b  mov     r8, rax
0x14006d81e  mov     edx, [rsi+38h]
0x14006d821  jmp     loc_14006D8BB
0x14006d826  mov     ecx, [rsi+0E4h]
0x14006d82c  mov     eax, [rsi+0DCh]
0x14006d832  cmp     eax, ecx
0x14006d834  cmovbe  eax, ecx
0x14006d837  mov     ecx, eax
0x14006d839  mov     rax, [rsp+2A0h+MaximumWorkingSetSize]
0x14006d83e  lea     rbx, [rax+rcx*2]
0x14006d842  call    cs:__imp_GetCurrentProcess
0x14006d848  mov     rcx, rax; hProcess
0x14006d84b  mov     r8, rbx; dwMaximumWorkingSetSize
0x14006d84e  mov     rdx, rbx; dwMinimumWorkingSetSize
0x14006d851  call    cs:__imp_SetProcessWorkingSetSize
0x14006d857  mov     [rsp+2A0h+ThrdAddr], 0; ThrdAddr
0x14006d860  mov     ebx, 4
0x14006d865  mov     [rsp+2A0h+InitFlag], ebx; InitFlag
0x14006d869  lea     r9, [rsi-8]; ArgList
0x14006d86d  lea     r8, ?DiskProfilerThreadProc@DiskProfiler@WinSAT@@CAIPEAX@Z; StartAddress
0x14006d874  xor     edx, edx; StackSize
0x14006d876  xor     ecx, ecx; Security
0x14006d878  call    cs:__imp__beginthreadex
0x14006d87e  mov     [rsi+0A8h], rax
0x14006d885  test    rax, rax
0x14006d888  jnz     short loc_14006D8D6
0x14006d88a  call    cs:__imp_GetLastError
0x14006d890  mov     [rbp+1A0h+var_50], eax
0x14006d896  mov     [rbp+1A0h+var_4C], dil
0x14006d89d  mov     [rbp+1A0h+var_48], 0
0x14006d8a8  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x14006d8ad  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14006d8b2  lea     edx, [rbx+1]
0x14006d8b5  mov     [rsi+38h], edx
0x14006d8b8  xor     r8d, r8d
0x14006d8bb  lea     r9, [rsp+2A0h+Buffer]
0x14006d8c0  mov     rcx, r14
0x14006d8c3  call    ?SetResult@OpStatus@WinSAT@@QEAAXW4OpStatusCode@2@PEBGAEBV?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@@Z; WinSAT::OpStatus::SetResult(WinSAT::OpStatusCode,ushort const *,mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>> const &)
0x14006d8c8  lea     rcx, [rsi+118h]; this
0x14006d8cf  call    ?Close@StorageDevice@WinSAT@@QEAAXXZ; WinSAT::StorageDevice::Close(void)
0x14006d8d4  jmp     short loc_14006D90C
0x14006d8d6  mov     rcx, rax; Thread
0x14006d8d9  call    cs:__imp_GetThreadId
0x14006d8df  mov     [rsi+0B0h], eax
0x14006d8e5  mov     [rsi+38h], ebx
0x14006d8e8  mov     rcx, [rsi+0A8h]; hThread
0x14006d8ef  call    cs:__imp_ResumeThread
0x14006d8f5  mov     eax, [rsi+38h]
0x14006d8f8  mov     [r14], eax
0x14006d8fb  lea     rcx, [r14+8]
0x14006d8ff  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x14006d904  mov     byte ptr [r14+10h], 0
0x14006d909  xor     dil, dil
0x14006d90c  mov     rcx, r15
0x14006d90f  call    ?Release@?$CSmartPtr@VMEvent@mlib@@@@AEAAXXZ; CSmartPtr<mlib::MEvent>::Release(void)
0x14006d914  mov     al, dil
0x14006d917  mov     rcx, [rbp+1A0h+var_40]
0x14006d91e  xor     rcx, rsp; StackCookie
0x14006d921  call    __security_check_cookie
0x14006d926  add     rsp, 270h
0x14006d92d  pop     r15
0x14006d92f  pop     r14
0x14006d931  pop     r12
0x14006d933  pop     rdi
0x14006d934  pop     rsi
0x14006d935  pop     rbx
0x14006d936  pop     rbp
0x14006d937  retn
```
