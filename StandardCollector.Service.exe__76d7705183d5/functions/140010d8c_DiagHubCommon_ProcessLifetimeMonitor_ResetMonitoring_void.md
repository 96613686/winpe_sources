# DiagHubCommon::ProcessLifetimeMonitor::ResetMonitoring(void)

- ea: `0x140010d8c`
- end: `0x140010fba`
- name: `?ResetMonitoring@ProcessLifetimeMonitor@DiagHubCommon@@QEAAXXZ`
- size: `558`
- prototype: `void __fastcall(DiagHubCommon::ProcessLifetimeMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140010a04`

## callees

- `0x140001fac`
- `0x140004b0c`
- `0x14000a278`
- `0x140010d8c`
- `0x1400111ac`
- `0x1400112f4`
- `0x140011854`
- `0x1400137e0`
- `0x140013834`
- `0x14001473e`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x140010f11`
- `KERNEL32!OpenProcess` at `0x140010f11`
- `KERNEL32!TerminateProcess` at `0x140010f38`
- `KERNEL32!TerminateProcess` at `0x140010f38`
- `KERNEL32!LeaveCriticalSection` at `0x140010ebe`
- `KERNEL32!LeaveCriticalSection` at `0x140010ebe`
- `KERNEL32!EnterCriticalSection` at `0x140010e23`
- `KERNEL32!EnterCriticalSection` at `0x140010e23`
- `KERNEL32!GetLastError` at `0x140010f23`
- `KERNEL32!GetLastError` at `0x140010f42`
- `KERNEL32!GetLastError` at `0x140010f23`
- `KERNEL32!GetLastError` at `0x140010f42`
- `KERNEL32!CloseHandle` at `0x140010f6e`
- `KERNEL32!CloseHandle` at `0x140010f6e`

## string_xrefs

- `0x140010efa`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\ProcessLifetimeMonitor.cpp`
- `0x140010f56`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\ProcessLifetimeMonitor.cpp`
- `0x140010f29`: `Failed to open process (%d) for termination. Error code: %#08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall DiagHubCommon::ProcessLifetimeMonitor::ResetMonitoring(DiagHubCommon::ProcessLifetimeMonitor *this)
{
  __int64 *v2; // rax
  __int64 *v3; // rax
  __int64 *v4; // r15
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 *i; // rbx
  unsigned int v12; // r14d
  HANDLE v13; // rax
  void *v14; // rdi
  DWORD LastError; // eax
  const unsigned __int16 *v16; // r8
  __int64 v17; // [rsp+20h] [rbp-39h]
  int v18; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v19; // [rsp+48h] [rbp-11h] BYREF
  __int64 v20; // [rsp+50h] [rbp-9h]
  __int64 v21; // [rsp+58h] [rbp-1h] BYREF
  __int128 v22; // [rsp+60h] [rbp+7h]
  __int64 v23; // [rsp+70h] [rbp+17h]
  __int64 v24; // [rsp+78h] [rbp+1Fh]

  memset_0(&v18, 0, 0x40u);
  v20 = 0;
  v2 = (__int64 *)operator new(0x40u);
  *v2 = (__int64)v2;
  v2[1] = (__int64)v2;
  v19 = v2;
  v21 = 0;
  v22 = 0;
  v23 = 7;
  v24 = 8;
  v18 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(
    &v21,
    16,
    v2);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( &v18 == (int *)this )
  {
    v4 = v19;
  }
  else
  {
    std::_Hash<std::_Umap_traits<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::clear(&v18);
    v18 = *(_DWORD *)this;
    v3 = v19;
    v4 = (__int64 *)*((_QWORD *)this + 1);
    v19 = v4;
    *((_QWORD *)this + 1) = v3;
    v5 = v20;
    v20 = *((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = v5;
    v6 = v21;
    v21 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v6;
    v7 = v22;
    *(_QWORD *)&v22 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = v7;
    v8 = *((_QWORD *)&v22 + 1);
    *((_QWORD *)&v22 + 1) = *((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = v8;
    v9 = v23;
    v23 = *((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = v9;
    v10 = v24;
    v24 = *((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = v10;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  for ( i = (__int64 *)*v4; i != v4; i = (__int64 *)*i )
  {
    v12 = *((_DWORD *)i + 6);
    DiagHubCommon::ProcessLifetimeMonitor::UnregisterWaitHandle_ExceptionSafe(this, (void *)i[4], v12);
    if ( !*((_BYTE *)i + 40) )
      continue;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::ProcessLifetimeMonitor *)((char *)this + 224),
      L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\ProcessLifetimeMonitor.cpp",
      L"Terminating target process ID: %d",
      v12);
    v13 = OpenProcess(1u, 0, v12);
    v14 = v13;
    if ( v13 )
    {
      if ( TerminateProcess(v13, 0xFFFFFFFF) )
        goto LABEL_11;
      LastError = GetLastError();
      v16 = L"Failed to terminate process ID: %d. Error code: %#08x";
    }
    else
    {
      LastError = GetLastError();
      v16 = L"Failed to open process (%d) for termination. Error code: %#08x";
    }
    LODWORD(v17) = LastError;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::ProcessLifetimeMonitor *)((char *)this + 224),
      L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\ProcessLifetimeMonitor.cpp",
      v16,
      v12,
      v17);
LABEL_11:
    if ( v14 )
      CloseHandle(v14);
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>(&v21);
  std::list<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>::~list<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>(&v19);
}

```

## disassembly

```asm
0x140010d8c  mov     [rsp-8+arg_8], rbx
0x140010d91  mov     [rsp-8+arg_10], rsi
0x140010d96  push    rbp
0x140010d97  push    rdi
0x140010d98  push    r12
0x140010d9a  push    r14
0x140010d9c  push    r15
0x140010d9e  lea     rbp, [rsp-37h]
0x140010da3  sub     rsp, 90h
0x140010daa  mov     rax, cs:__security_cookie
0x140010db1  xor     rax, rsp
0x140010db4  mov     [rbp+57h+var_30], rax
0x140010db8  mov     rsi, rcx
0x140010dbb  mov     ebx, 40h ; '@'
0x140010dc0  mov     r8d, ebx; Size
0x140010dc3  xor     edx, edx; Val
0x140010dc5  lea     rcx, [rbp+57h+var_70]; void *
0x140010dc9  call    memset_0
0x140010dce  mov     [rbp+57h+var_60], 0
0x140010dd6  mov     ecx, ebx; Size
0x140010dd8  call    ??2@YAPEAX_K@Z
0x140010ddd  mov     [rax], rax
0x140010de0  mov     [rax+8], rax
0x140010de4  mov     [rbp+57h+var_68], rax
0x140010de8  mov     [rbp+57h+var_58], 0
0x140010df0  xorps   xmm0, xmm0
0x140010df3  movdqa  [rbp+57h+var_50], xmm0
0x140010df8  mov     [rbp+57h+var_40], 7
0x140010e00  mov     [rbp+57h+var_38], 8
0x140010e08  mov     [rbp+57h+var_70], 3F800000h
0x140010e0f  mov     r8, rax
0x140010e12  lea     edx, [rbx-30h]
0x140010e15  lea     rcx, [rbp+57h+var_58]
0x140010e19  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@@Z
0x140010e1e  nop
0x140010e1f  lea     rcx, [rsi+40h]; lpCriticalSection
0x140010e23  call    cs:__imp_EnterCriticalSection
0x140010e29  lea     rax, [rbp+57h+var_70]
0x140010e2d  cmp     rax, rsi
0x140010e30  jz      loc_140010EB6
0x140010e36  lea     rcx, [rbp+57h+var_70]
0x140010e3a  call    ?clear@?$_Hash@V?$_Umap_traits@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@5@$0A@@std@@@std@@QEAAXXZ
0x140010e3f  mov     eax, [rsi]
0x140010e41  mov     [rbp+57h+var_70], eax
0x140010e44  mov     rax, [rbp+57h+var_68]
0x140010e48  mov     r15, [rsi+8]
0x140010e4c  mov     [rbp+57h+var_68], r15
0x140010e50  mov     [rsi+8], rax
0x140010e54  mov     rcx, [rbp+57h+var_60]
0x140010e58  mov     rax, [rsi+10h]
0x140010e5c  mov     [rbp+57h+var_60], rax
0x140010e60  mov     [rsi+10h], rcx
0x140010e64  mov     rcx, [rbp+57h+var_58]
0x140010e68  mov     rax, [rsi+18h]
0x140010e6c  mov     [rbp+57h+var_58], rax
0x140010e70  mov     [rsi+18h], rcx
0x140010e74  mov     rcx, qword ptr [rbp+57h+var_50]
0x140010e78  mov     rax, [rsi+20h]
0x140010e7c  mov     qword ptr [rbp+57h+var_50], rax
0x140010e80  mov     [rsi+20h], rcx
0x140010e84  mov     rcx, qword ptr [rbp+57h+var_50+8]
0x140010e88  mov     rax, [rsi+28h]
0x140010e8c  mov     qword ptr [rbp+57h+var_50+8], rax
0x140010e90  mov     [rsi+28h], rcx
0x140010e94  mov     rcx, [rbp+57h+var_40]
0x140010e98  mov     rax, [rsi+30h]
0x140010e9c  mov     [rbp+57h+var_40], rax
0x140010ea0  mov     [rsi+30h], rcx
0x140010ea4  mov     rcx, [rbp+57h+var_38]
0x140010ea8  mov     rax, [rsi+38h]
0x140010eac  mov     [rbp+57h+var_38], rax
0x140010eb0  mov     [rsi+38h], rcx
0x140010eb4  jmp     short loc_140010EBA
0x140010eb6  mov     r15, [rbp+57h+var_68]
0x140010eba  lea     rcx, [rsi+40h]; lpCriticalSection
0x140010ebe  call    cs:__imp_LeaveCriticalSection
0x140010ec4  mov     rbx, [r15]
0x140010ec7  jmp     loc_140010F77
0x140010ecc  mov     r14d, [rbx+18h]
0x140010ed0  mov     r8d, r14d; unsigned int
0x140010ed3  mov     rdx, [rbx+20h]; void *
0x140010ed7  mov     rcx, rsi; this
0x140010eda  call    ?UnregisterWaitHandle_ExceptionSafe@ProcessLifetimeMonitor@DiagHubCommon@@AEAAXPEAXI@Z
0x140010edf  cmp     byte ptr [rbx+28h], 0
0x140010ee3  jz      loc_140010F74
0x140010ee9  lea     r12, [rsi+0E0h]
0x140010ef0  mov     r9d, r14d
0x140010ef3  lea     r8, aTerminatingTar
0x140010efa  lea     rdx, aDAWork1SSource_1
0x140010f01  mov     rcx, r12; this
0x140010f04  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ
0x140010f09  mov     r8d, r14d; dwProcessId
0x140010f0c  xor     edx, edx; bInheritHandle
0x140010f0e  lea     ecx, [rdx+1]; dwDesiredAccess
0x140010f11  call    cs:__imp_OpenProcess
0x140010f17  mov     rdi, rax
0x140010f1a  mov     [rbp+57h+var_80], rax
0x140010f1e  test    rax, rax
0x140010f21  jnz     short loc_140010F32
0x140010f23  call    cs:__imp_GetLastError
0x140010f29  lea     r8, aFailedToOpenPr
0x140010f30  jmp     short loc_140010F4F
0x140010f32  or      edx, 0FFFFFFFFh; uExitCode
0x140010f35  mov     rcx, rdi; hProcess
0x140010f38  call    cs:__imp_TerminateProcess
0x140010f3e  test    eax, eax
0x140010f40  jnz     short loc_140010F66
0x140010f42  call    cs:__imp_GetLastError
0x140010f48  lea     r8, aFailedToTermin
0x140010f4f  mov     [rsp+0B0h+var_90], eax
0x140010f53  mov     r9d, r14d
0x140010f56  lea     rdx, aDAWork1SSource_1
0x140010f5d  mov     rcx, r12; this
0x140010f60  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ
0x140010f65  nop
0x140010f66  test    rdi, rdi
0x140010f69  jz      short loc_140010F74
0x140010f6b  mov     rcx, rdi; hObject
0x140010f6e  call    cs:__imp_CloseHandle
0x140010f74  mov     rbx, [rbx]
0x140010f77  cmp     rbx, r15
0x140010f7a  jnz     loc_140010ECC
0x140010f80  lea     rcx, [rbp+57h+var_58]
0x140010f84  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ
0x140010f89  lea     rcx, [rbp+57h+var_68]
0x140010f8d  call    ??1?$list@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@2@@std@@QEAA@XZ
0x140010f92  mov     rcx, [rbp+57h+var_30]
0x140010f96  xor     rcx, rsp; StackCookie
0x140010f99  call    __security_check_cookie
0x140010f9e  lea     r11, [rsp+0B0h+var_20]
0x140010fa6  mov     rbx, [r11+38h]
0x140010faa  mov     rsi, [r11+40h]
0x140010fae  mov     rsp, r11
0x140010fb1  pop     r15
0x140010fb3  pop     r14
0x140010fb5  pop     r12
0x140010fb7  pop     rdi
0x140010fb8  pop     rbp
0x140010fb9  retn
```
