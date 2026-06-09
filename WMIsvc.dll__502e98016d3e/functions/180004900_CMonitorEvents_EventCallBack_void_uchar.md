# CMonitorEvents::EventCallBack(void *,uchar)

- ea: `0x180004900`
- end: `0x180004ac1`
- name: `?EventCallBack@CMonitorEvents@@SAXPEAXE@Z`
- size: `449`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004120`
- `0x180004900`
- `0x180004bf0`
- `0x180004c30`
- `0x180004ccc`
- `0x18000618c`
- `0x18000a18c`
- `0x180012c34`
- `0x18001d3a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800049ed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800049ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049af`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000495b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000495b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180004a8e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180004a8e`
- `wbemcomn!?Enter@CStaticCritSec@@QEAAXXZ` at `0x180004a71`
- `wbemcomn!?Enter@CStaticCritSec@@QEAAXXZ` at `0x180004a71`
- `wbemcomn!?Leave@CStaticCritSec@@QEAAXXZ` at `0x180004a82`
- `wbemcomn!?Leave@CStaticCritSec@@QEAAXXZ` at `0x180004a82`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000496d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000496d`
- `wbemcomn!GetMemLogObject` at `0x180004961`
- `wbemcomn!GetMemLogObject` at `0x180004961`

## pseudocode

```c
void __fastcall CMonitorEvents::EventCallBack(unsigned int *a1, char a2)
{
  __int64 v4; // rbx
  CMemoryLog *MemLogObject; // rax
  HKEY v6; // rcx
  struct ResyncPerfTask *Available; // rsi
  unsigned int v8; // r10d
  WCHAR CommandLine[64]; // [rsp+30h] [rbp-98h] BYREF

  if ( (unsigned int)GLOB_Monitor_IsRegistred() && a1 && *a1 == 1498629458 )
  {
    v4 = *((_QWORD *)a1 + 4);
    if ( a2 )
    {
      TerminateProcess(*((HANDLE *)a1 + 5), 0);
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -1);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids, a1[2]);
      }
    }
    CloseHandle(*((HANDLE *)a1 + 5));
    if ( a1[2] == 3 )
    {
      *(_DWORD *)(v4 + 4) = 0;
      RegSetDWORD(v6, L"Software\\Microsoft\\WBEM\\CIMOM", L"ThrottleDrege", 1);
      if ( dword_180032A90 )
        SetEvent(hEvent);
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4, 0xFFFFFFFF) == 1 )
    {
      if ( *(_DWORD *)(v4 + 4) )
      {
        Available = CMonitorEvents::GetAvailable((CMonitorEvents *)&dword_180032A88, 3u);
        if ( Available )
        {
          StringCchCopyW(CommandLine, 0x40u, L"wmiadap.exe ");
          StringCchCatW(CommandLine, v8, (const unsigned __int16 *)(&g_Strings)[*((unsigned int *)Available + 3)]);
          CMonitorEvents::CreateProcess_(CommandLine, (struct CMonitorEvents *)&dword_180032A88, Available);
        }
      }
    }
    *((_QWORD *)a1 + 5) = 0;
    CStaticCritSec::Enter((CStaticCritSec *)(v4 + 24));
    a1[1] = 1;
    CStaticCritSec::Leave((CStaticCritSec *)(v4 + 24));
    UnregisterWaitEx(*((HANDLE *)a1 + 6), 0);
    *((_QWORD *)a1 + 6) = 0;
  }
}

```

## disassembly

```asm
0x180004900  mov     [rsp+arg_8], rbx
0x180004905  mov     [rsp+arg_10], rsi
0x18000490a  push    rdi
0x18000490b  sub     rsp, 0C0h
0x180004912  mov     rax, cs:__security_cookie
0x180004919  xor     rax, rsp
0x18000491c  mov     [rsp+0C8h+var_18], rax
0x180004924  mov     sil, dl
0x180004927  mov     rdi, rcx
0x18000492a  call    ?GLOB_Monitor_IsRegistred@@YAHXZ; GLOB_Monitor_IsRegistred(void)
0x18000492f  test    eax, eax
0x180004931  jz      loc_180004A9C
0x180004937  test    rdi, rdi
0x18000493a  jz      loc_180004A9C
0x180004940  cmp     dword ptr [rdi], 59534552h
0x180004946  jnz     loc_180004A9C
0x18000494c  mov     rbx, [rdi+20h]
0x180004950  test    sil, sil
0x180004953  jz      short loc_1800049AB
0x180004955  mov     rcx, [rdi+28h]; hProcess
0x180004959  xor     edx, edx; uExitCode
0x18000495b  call    cs:__imp_TerminateProcess
0x180004961  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180004967  mov     rcx, rax
0x18000496a  or      edx, 0FFFFFFFFh
0x18000496d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180004973  mov     rcx, cs:WPP_GLOBAL_Control
0x18000497a  lea     rax, WPP_GLOBAL_Control
0x180004981  cmp     rcx, rax
0x180004984  jz      short loc_1800049AB
0x180004986  test    byte ptr [rcx+1Ch], 1
0x18000498a  jz      short loc_1800049AB
0x18000498c  cmp     byte ptr [rcx+19h], 2
0x180004990  jb      short loc_1800049AB
0x180004992  mov     r9d, [rdi+8]
0x180004996  lea     r8, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids
0x18000499d  mov     rcx, [rcx+10h]
0x1800049a1  mov     edx, 14h
0x1800049a6  call    WPP_SF_d
0x1800049ab  mov     rcx, [rdi+28h]; hObject
0x1800049af  call    cs:__imp_CloseHandle
0x1800049b5  mov     edx, 3; unsigned int
0x1800049ba  cmp     [rdi+8], edx
0x1800049bd  jnz     short loc_1800049F5
0x1800049bf  lea     r9d, [rdx-2]; unsigned int
0x1800049c3  mov     dword ptr [rbx+4], 0
0x1800049ca  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x1800049d1  lea     r8, aThrottledrege; "ThrottleDrege"
0x1800049d8  call    ?RegSetDWORD@@YAKPEAUHKEY__@@PEBG1K@Z; RegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800049dd  cmp     cs:dword_180032A90, 0
0x1800049e4  jz      short loc_180004A65
0x1800049e6  mov     rcx, cs:hEvent; hEvent
0x1800049ed  call    cs:__imp_SetEvent
0x1800049f3  jmp     short loc_180004A65
0x1800049f5  or      eax, 0FFFFFFFFh
0x1800049f8  lock xadd [rbx], eax
0x1800049fc  cmp     eax, 1
0x1800049ff  jnz     short loc_180004A65
0x180004a01  cmp     dword ptr [rbx+4], 0
0x180004a05  jz      short loc_180004A65
0x180004a07  lea     rcx, dword_180032A88; this
0x180004a0e  call    ?GetAvailable@CMonitorEvents@@QEAAPEAVResyncPerfTask@@K@Z; CMonitorEvents::GetAvailable(ulong)
0x180004a13  mov     rsi, rax
0x180004a16  test    rax, rax
0x180004a19  jz      short loc_180004A65
0x180004a1b  mov     r10d, 40h ; '@'
0x180004a21  lea     r8, aWmiadapExe; "wmiadap.exe "
0x180004a28  mov     edx, r10d; unsigned __int64
0x180004a2b  lea     rcx, [rsp+0C8h+CommandLine]; unsigned __int16 *
0x180004a30  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004a35  mov     r8d, [rsi+0Ch]
0x180004a39  lea     rax, ?g_Strings@@3PAPEAGA; ushort * near * g_Strings
0x180004a40  mov     edx, r10d; unsigned __int64
0x180004a43  lea     rcx, [rsp+0C8h+CommandLine]; unsigned __int16 *
0x180004a48  mov     r8, [rax+r8*8]; unsigned __int16 *
0x180004a4c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004a51  mov     r8, rsi; struct ResyncPerfTask *
0x180004a54  lea     rdx, dword_180032A88; struct CMonitorEvents *
0x180004a5b  lea     rcx, [rsp+0C8h+CommandLine]; lpCommandLine
0x180004a60  call    ?CreateProcess_@CMonitorEvents@@SAHPEAGPEAV1@PEAVResyncPerfTask@@@Z; CMonitorEvents::CreateProcess_(ushort *,CMonitorEvents *,ResyncPerfTask *)
0x180004a65  lea     rcx, [rbx+18h]
0x180004a69  mov     qword ptr [rdi+28h], 0
0x180004a71  call    cs:__imp_?Enter@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Enter(void)
0x180004a77  lea     rcx, [rbx+18h]
0x180004a7b  mov     dword ptr [rdi+4], 1
0x180004a82  call    cs:__imp_?Leave@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Leave(void)
0x180004a88  mov     rcx, [rdi+30h]; WaitHandle
0x180004a8c  xor     edx, edx; CompletionEvent
0x180004a8e  call    cs:__imp_UnregisterWaitEx
0x180004a94  mov     qword ptr [rdi+30h], 0
0x180004a9c  mov     rcx, [rsp+0C8h+var_18]
0x180004aa4  xor     rcx, rsp; StackCookie
0x180004aa7  call    __security_check_cookie
0x180004aac  lea     r11, [rsp+0C8h+var_8]
0x180004ab4  mov     rbx, [r11+18h]
0x180004ab8  mov     rsi, [r11+20h]
0x180004abc  mov     rsp, r11
0x180004abf  pop     rdi
0x180004ac0  retn
```
