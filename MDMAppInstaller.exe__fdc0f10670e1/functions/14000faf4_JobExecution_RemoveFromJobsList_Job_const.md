# JobExecution::RemoveFromJobsList(_Job const &)

- ea: `0x14000faf4`
- end: `0x14000fbe8`
- name: `?RemoveFromJobsList@JobExecution@@CAJAEBU_Job@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(const struct _Job *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14000cd78`
- `0x14000e6cc`

## callees

- `0x140006480`
- `0x1400074d4`
- `0x14000775c`
- `0x140009598`
- `0x14000faf4`
- `0x140012468`
- `0x1400127f4`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000fbb5`
- `KERNEL32!LeaveCriticalSection` at `0x14000fbb5`
- `KERNEL32!EnterCriticalSection` at `0x14000fb30`
- `KERNEL32!EnterCriticalSection` at `0x14000fb30`

## string_xrefs

- `0x14000fb86`: `Removed job %1 from the job processing queue.`
- `0x14000fba2`: `Job %1 was not found in the processing queue when attempting to remove it.`

## pseudocode

```c
__int64 __fastcall JobExecution::RemoveFromJobsList(const struct _Job *a1)
{
  unsigned int v2; // edi
  __int64 v3; // rcx
  _QWORD *v4; // rdx
  _QWORD *v5; // rdx
  __int64 v7; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v8[3]; // [rsp+28h] [rbp-28h] BYREF
  unsigned __int64 v9; // [rsp+40h] [rbp-10h]

  v9 = 7;
  v2 = 0;
  v8[2] = 0;
  LOWORD(v8[0]) = 0;
  EnterCriticalSection(&JobExecution::m_critSec);
  if ( *((_QWORD *)a1 + 2) )
  {
    std::wstring::operator=((__int64)v8, (__int64)a1);
    std::_Tree<std::_Tmap_traits<std::wstring,_Job,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_Job>>,0>>::find(
      v3,
      &v7,
      a1);
    if ( v7 == JobExecution::m_mapProcessingJobList )
    {
      v5 = v8;
      if ( v9 >= 8 )
        v5 = (_QWORD *)v8[0];
      LogWarn(L"Job %1 was not found in the processing queue when attempting to remove it.", v5);
    }
    else
    {
      std::_Tree<std::_Tmap_traits<std::wstring,_Job,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_Job>>,0>>::erase(
        &JobExecution::m_mapProcessingJobList,
        &v7);
      v4 = v8;
      if ( v9 >= 8 )
        v4 = (_QWORD *)v8[0];
      LogInfo(L"Removed job %1 from the job processing queue.", v4);
    }
  }
  else
  {
    v2 = -2147024809;
  }
  LeaveCriticalSection(&JobExecution::m_critSec);
  std::wstring::_Tidy(v8, 1, 0);
  return v2;
}

```

## disassembly

```asm
0x14000faf4  mov     [rsp-8+arg_8], rbx
0x14000faf9  mov     [rsp-8+arg_10], rdi
0x14000fafe  push    rbp
0x14000faff  mov     rbp, rsp
0x14000fb02  sub     rsp, 50h
0x14000fb06  mov     rax, cs:__security_cookie
0x14000fb0d  xor     rax, rsp
0x14000fb10  mov     [rbp+var_8], rax
0x14000fb14  mov     rbx, rcx
0x14000fb17  mov     [rbp+var_10], 7
0x14000fb1f  xor     edi, edi
0x14000fb21  mov     [rbp+var_18], rdi
0x14000fb25  mov     word ptr [rbp+var_28], di
0x14000fb29  lea     rcx, ?m_critSec@JobExecution@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14000fb30  call    cs:__imp_EnterCriticalSection
0x14000fb36  cmp     [rbx+10h], rdi
0x14000fb3a  jnz     short loc_14000FB43
0x14000fb3c  mov     edi, 80070057h
0x14000fb41  jmp     short loc_14000FBAE
0x14000fb43  mov     rdx, rbx
0x14000fb46  lea     rcx, [rbp+var_28]
0x14000fb4a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14000fb4f  mov     r8, rbx
0x14000fb52  lea     rdx, [rbp+var_30]
0x14000fb56  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_Job,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_Job>>,0>>::find(std::wstring const &)
0x14000fb5b  mov     r8, [rbp+var_30]
0x14000fb5f  cmp     r8, cs:?m_mapProcessingJobList@JobExecution@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@2@@std@@A; std::map<std::wstring,_Job> JobExecution::m_mapProcessingJobList
0x14000fb66  jz      short loc_14000FB94
0x14000fb68  lea     rdx, [rbp+var_30]
0x14000fb6c  lea     rcx, ?m_mapProcessingJobList@JobExecution@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@2@@std@@A; std::map<std::wstring,_Job> JobExecution::m_mapProcessingJobList
0x14000fb73  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_Job,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_Job>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_Job>>>>)
0x14000fb78  lea     rdx, [rbp+var_28]
0x14000fb7c  cmp     [rbp+var_10], 8
0x14000fb81  cmovnb  rdx, [rbp+var_28]
0x14000fb86  lea     rcx, aRemovedJob1Fro; "Removed job %1 from the job processing "...
0x14000fb8d  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000fb92  jmp     short loc_14000FBAE
0x14000fb94  lea     rdx, [rbp+var_28]
0x14000fb98  cmp     [rbp+var_10], 8
0x14000fb9d  cmovnb  rdx, [rbp+var_28]
0x14000fba2  lea     rcx, aJob1WasNotFoun; "Job %1 was not found in the processing "...
0x14000fba9  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x14000fbae  lea     rcx, ?m_critSec@JobExecution@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14000fbb5  call    cs:__imp_LeaveCriticalSection
0x14000fbbb  nop
0x14000fbbc  xor     r8d, r8d
0x14000fbbf  mov     dl, 1
0x14000fbc1  lea     rcx, [rbp+var_28]
0x14000fbc5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000fbca  mov     eax, edi
0x14000fbcc  mov     rcx, [rbp+var_8]
0x14000fbd0  xor     rcx, rsp; StackCookie
0x14000fbd3  call    __security_check_cookie
0x14000fbd8  mov     rbx, [rsp+50h+arg_8]
0x14000fbdd  mov     rdi, [rsp+50h+arg_10]
0x14000fbe2  add     rsp, 50h
0x14000fbe6  pop     rbp
0x14000fbe7  retn
```
