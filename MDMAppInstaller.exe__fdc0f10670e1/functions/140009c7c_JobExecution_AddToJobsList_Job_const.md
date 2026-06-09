# JobExecution::AddToJobsList(_Job const &)

- ea: `0x140009c7c`
- end: `0x140009d78`
- name: `?AddToJobsList@JobExecution@@SAJAEBU_Job@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(const struct _Job *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140004128`

## callees

- `0x14000740c`
- `0x1400074d4`
- `0x14000775c`
- `0x1400095f8`
- `0x1400097ac`
- `0x140009c7c`
- `0x1400127f4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140009d65`
- `KERNEL32!LeaveCriticalSection` at `0x140009d65`
- `KERNEL32!EnterCriticalSection` at `0x140009c90`
- `KERNEL32!EnterCriticalSection` at `0x140009c90`

## string_xrefs

- `0x140009d52`: `Job %1 is already in job processing queue.`

## pseudocode

```c
__int64 __fastcall JobExecution::AddToJobsList(const struct _Job *a1)
{
  __int64 v2; // rcx
  unsigned int v3; // edi
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  EnterCriticalSection(&JobExecution::m_critSec);
  if ( !*((_QWORD *)a1 + 2) )
  {
    v3 = -2147024809;
LABEL_10:
    if ( *((_QWORD *)a1 + 3) >= 8u )
      a1 = *(const struct _Job **)a1;
    LogError(L"Unable to add job %1 to the processing queue", a1);
    goto LABEL_21;
  }
  v3 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,_Job,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_Job>>,0>>::find(
    v2,
    &v7,
    a1);
  if ( v7 == JobExecution::m_mapProcessingJobList )
  {
    v5 = std::map<std::wstring,_Job>::operator[](v4, a1);
    _Job::operator=(v5, a1);
    if ( *((_QWORD *)a1 + 3) >= 8u )
      a1 = *(const struct _Job **)a1;
    LogInfo(L"Added job %1 into job processing queue.", a1);
  }
  else
  {
    if ( v7 == -64 )
    {
      v3 = -2147024882;
      goto LABEL_10;
    }
    if ( *((_DWORD *)a1 + 37) != 10 || *(_DWORD *)(v7 + 212) == 10 )
    {
      if ( *((_QWORD *)a1 + 3) >= 8u )
        a1 = *(const struct _Job **)a1;
      LogWarn(L"Job %1 is already in job processing queue.", a1);
    }
    else
    {
      _Job::operator=(v7 + 64, a1);
      if ( *((_QWORD *)a1 + 3) >= 8u )
        a1 = *(const struct _Job **)a1;
      LogInfo(L"Updating job %1 in the processing queue. It has been reset to an Initialized state.", a1);
    }
  }
LABEL_21:
  LeaveCriticalSection(&JobExecution::m_critSec);
  return v3;
}

```

## disassembly

```asm
0x140009c7c  mov     [rsp+arg_0], rbx
0x140009c81  push    rdi
0x140009c82  sub     rsp, 20h
0x140009c86  mov     rbx, rcx
0x140009c89  lea     rcx, ?m_critSec@JobExecution@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x140009c90  call    cs:__imp_EnterCriticalSection
0x140009c96  cmp     qword ptr [rbx+10h], 0
0x140009c9b  jnz     short loc_140009CA4
0x140009c9d  mov     edi, 80070057h
0x140009ca2  jmp     short loc_140009CFD
0x140009ca4  mov     r8, rbx
0x140009ca7  lea     rdx, [rsp+28h+arg_8]
0x140009cac  xor     edi, edi
0x140009cae  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_Job,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_Job>>,0>>::find(std::wstring const &)
0x140009cb3  mov     rax, [rsp+28h+arg_8]
0x140009cb8  cmp     rax, cs:?m_mapProcessingJobList@JobExecution@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@2@@std@@A; std::map<std::wstring,_Job> JobExecution::m_mapProcessingJobList
0x140009cbf  jnz     short loc_140009CEF
0x140009cc1  mov     rdx, rbx
0x140009cc4  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@2@@std@@QEAAAEAU_Job@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_Job>::operator[](std::wstring const &)
0x140009cc9  mov     rcx, rax
0x140009ccc  mov     rdx, rbx
0x140009ccf  call    ??4_Job@@QEAAAEAU0@AEBU0@@Z; _Job::operator=(_Job const &)
0x140009cd4  cmp     qword ptr [rbx+18h], 8
0x140009cd9  jb      short loc_140009CDE
0x140009cdb  mov     rbx, [rbx]
0x140009cde  lea     rcx, aAddedJob1IntoJ; "Added job %1 into job processing queue."
0x140009ce5  mov     rdx, rbx
0x140009ce8  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140009ced  jmp     short loc_140009D5E
0x140009cef  lea     rcx, [rax+40h]
0x140009cf3  test    rcx, rcx
0x140009cf6  jnz     short loc_140009D18
0x140009cf8  mov     edi, 8007000Eh
0x140009cfd  cmp     qword ptr [rbx+18h], 8
0x140009d02  jb      short loc_140009D07
0x140009d04  mov     rbx, [rbx]
0x140009d07  mov     rdx, rbx
0x140009d0a  lea     rcx, aUnableToAddJob; "Unable to add job %1 to the processing "...
0x140009d11  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140009d16  jmp     short loc_140009D5E
0x140009d18  cmp     dword ptr [rbx+94h], 0Ah
0x140009d1f  jnz     short loc_140009D45
0x140009d21  cmp     dword ptr [rcx+94h], 0Ah
0x140009d28  jz      short loc_140009D45
0x140009d2a  mov     rdx, rbx
0x140009d2d  call    ??4_Job@@QEAAAEAU0@AEBU0@@Z; _Job::operator=(_Job const &)
0x140009d32  cmp     qword ptr [rbx+18h], 8
0x140009d37  jb      short loc_140009D3C
0x140009d39  mov     rbx, [rbx]
0x140009d3c  lea     rcx, aUpdatingJob1In; "Updating job %1 in the processing queue"...
0x140009d43  jmp     short loc_140009CE5
0x140009d45  cmp     qword ptr [rbx+18h], 8
0x140009d4a  jb      short loc_140009D4F
0x140009d4c  mov     rbx, [rbx]
0x140009d4f  mov     rdx, rbx
0x140009d52  lea     rcx, aJob1IsAlreadyI; "Job %1 is already in job processing que"...
0x140009d59  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x140009d5e  lea     rcx, ?m_critSec@JobExecution@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x140009d65  call    cs:__imp_LeaveCriticalSection
0x140009d6b  mov     rbx, [rsp+28h+arg_0]
0x140009d70  mov     eax, edi
0x140009d72  add     rsp, 20h
0x140009d76  pop     rdi
0x140009d77  retn
```
