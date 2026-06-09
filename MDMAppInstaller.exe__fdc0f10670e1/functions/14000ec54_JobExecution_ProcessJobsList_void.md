# JobExecution::ProcessJobsList(void)

- ea: `0x14000ec54`
- end: `0x14000ede3`
- name: `?ProcessJobsList@JobExecution@@SAJXZ`
- size: `399`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140006dc8`

## callees

- `0x14000740c`
- `0x1400074d4`
- `0x1400089c8`
- `0x140008a0c`
- `0x140008a80`
- `0x1400091dc`
- `0x14000ec54`
- `0x140011ac4`
- `0x140012a8c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000edc4`
- `KERNEL32!LeaveCriticalSection` at `0x14000edc4`
- `KERNEL32!EnterCriticalSection` at `0x14000ec7b`
- `KERNEL32!EnterCriticalSection` at `0x14000ec7b`

## string_xrefs

- `0x14000ed2c`: `Skipping completed job %1.`

## pseudocode

```c
__int64 JobExecution::ProcessJobsList(void)
{
  __int64 v0; // r9
  __int64 v1; // rbx
  int v2; // eax
  int v3; // eax
  _QWORD *v4; // rcx
  __int64 i; // rax
  unsigned int v6; // ebx
  __int64 v7; // r9
  _QWORD v9[2]; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v10[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v11; // [rsp+50h] [rbp+10h] BYREF

  LogInfo(L"++ Starting to process %1!d! jobs in list ++", qword_14002BD68);
  EnterCriticalSection(&JobExecution::m_critSec);
  std::list<_Job *>::list<_Job *>(v10);
  std::list<_Job *>::list<_Job *>(v9);
  v1 = *(_QWORD *)JobExecution::m_mapProcessingJobList;
  while ( v1 != JobExecution::m_mapProcessingJobList )
  {
    v11 = v1 + 64;
    if ( v1 == -64 )
    {
      v6 = -2147024882;
      goto LABEL_24;
    }
    v2 = *(_DWORD *)(v1 + 220);
    if ( v2 == 40 )
    {
      LogInfo(L"Skipping completed job %1.");
      goto LABEL_14;
    }
    if ( v2 == 30 )
    {
      LogInfo(L"Skipping blocked job %1.");
      goto LABEL_14;
    }
    v3 = *(_DWORD *)(v1 + 208);
    if ( v3 == 1 )
    {
      v4 = v10;
    }
    else
    {
      if ( v3 != 2 )
      {
        LogError(L"Skipping unknown job type for job %1.");
        goto LABEL_14;
      }
      v4 = v9;
    }
    std::list<_Job *>::push_back(v4, &v11);
LABEL_14:
    if ( !*(_BYTE *)(v1 + 25) )
    {
      if ( *(_BYTE *)(*(_QWORD *)(v1 + 16) + 25LL) )
      {
        for ( i = *(_QWORD *)(v1 + 8); !*(_BYTE *)(i + 25) && v1 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v1 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>::_Min();
      }
      v1 = i;
    }
  }
  v6 = 0;
  LOBYTE(v0) = 0;
  std::for_each_std::_List_iterator_std::_List_val_std::_List_simple_types__Job_________lambda_b95765a8bf9c1cd66ddb5a7621850a5b___(
    &v11,
    *(_QWORD *)v10[0],
    v10[0],
    v0);
  LOBYTE(v7) = 0;
  std::for_each_std::_List_iterator_std::_List_val_std::_List_simple_types__Job_________lambda_c6672250848d4967b274276ac94b90f1___(
    &v11,
    *(_QWORD *)v9[0],
    v9[0],
    v7);
LABEL_24:
  std::list<_Job *>::~list<_Job *>(v9);
  std::list<_Job *>::~list<_Job *>(v10);
  LeaveCriticalSection(&JobExecution::m_critSec);
  LogInfo(L"++ Finished processing the job list ++");
  return v6;
}

```

## disassembly

```asm
0x14000ec54  mov     [rsp-8+arg_8], rbx
0x14000ec59  push    rbp
0x14000ec5a  mov     rbp, rsp
0x14000ec5d  sub     rsp, 40h
0x14000ec61  mov     rdx, cs:qword_14002BD68
0x14000ec68  lea     rcx, aStartingToProc; "++ Starting to process %1!d! jobs in li"...
0x14000ec6f  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000ec74  lea     rcx, ?m_critSec@JobExecution@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14000ec7b  call    cs:__imp_EnterCriticalSection
0x14000ec81  lea     rcx, [rbp+var_10]
0x14000ec85  call    ??0?$list@PEAU_Job@@V?$allocator@PEAU_Job@@@std@@@std@@QEAA@XZ; std::list<_Job *>::list<_Job *>(void)
0x14000ec8a  nop
0x14000ec8b  lea     rcx, [rbp+var_20]
0x14000ec8f  call    ??0?$list@PEAU_Job@@V?$allocator@PEAU_Job@@@std@@@std@@QEAA@XZ; std::list<_Job *>::list<_Job *>(void)
0x14000ec94  nop
0x14000ec95  mov     rbx, cs:?m_mapProcessingJobList@JobExecution@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@2@@std@@A; std::map<std::wstring,_Job> JobExecution::m_mapProcessingJobList
0x14000ec9c  mov     rbx, [rbx]
0x14000ec9f  cmp     rbx, cs:?m_mapProcessingJobList@JobExecution@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@2@@std@@A; std::map<std::wstring,_Job> JobExecution::m_mapProcessingJobList
0x14000eca6  jz      loc_14000ED7B
0x14000ecac  lea     rdx, [rbx+40h]
0x14000ecb0  mov     [rbp+arg_0], rdx
0x14000ecb4  test    rdx, rdx
0x14000ecb7  jz      loc_14000ED74
0x14000ecbd  mov     eax, [rdx+9Ch]
0x14000ecc3  cmp     eax, 28h ; '('
0x14000ecc6  jz      short loc_14000ED0A
0x14000ecc8  cmp     eax, 1Eh
0x14000eccb  jz      short loc_14000ED0F
0x14000eccd  mov     eax, [rdx+90h]
0x14000ecd3  cmp     eax, 1
0x14000ecd6  jnz     short loc_14000ECDE
0x14000ecd8  lea     rcx, [rbp+var_10]
0x14000ecdc  jmp     short loc_14000ECE7
0x14000ecde  cmp     eax, 2
0x14000ece1  jnz     short loc_14000ECF2
0x14000ece3  lea     rcx, [rbp+var_20]
0x14000ece7  lea     rdx, [rbp+arg_0]
0x14000eceb  call    ?push_back@?$list@PEAU_Job@@V?$allocator@PEAU_Job@@@std@@@std@@QEAAXAEBQEAU_Job@@@Z; std::list<_Job *>::push_back(_Job * const &)
0x14000ecf0  jmp     short loc_14000ED38
0x14000ecf2  cmp     qword ptr [rbx+58h], 8
0x14000ecf7  jb      short loc_14000ECFC
0x14000ecf9  mov     rdx, [rdx]
0x14000ecfc  lea     rcx, aSkippingUnknow; "Skipping unknown job type for job %1."
0x14000ed03  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000ed08  jmp     short loc_14000ED38
0x14000ed0a  cmp     eax, 1Eh
0x14000ed0d  jnz     short loc_14000ED22
0x14000ed0f  cmp     qword ptr [rbx+58h], 8
0x14000ed14  jb      short loc_14000ED19
0x14000ed16  mov     rdx, [rdx]
0x14000ed19  lea     rcx, aSkippingBlocke; "Skipping blocked job %1."
0x14000ed20  jmp     short loc_14000ED33
0x14000ed22  cmp     qword ptr [rbx+58h], 8
0x14000ed27  jb      short loc_14000ED2C
0x14000ed29  mov     rdx, [rdx]
0x14000ed2c  lea     rcx, aSkippingComple; "Skipping completed job %1."
0x14000ed33  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000ed38  cmp     byte ptr [rbx+19h], 0
0x14000ed3c  jnz     loc_14000EC9F
0x14000ed42  mov     rcx, [rbx+10h]
0x14000ed46  cmp     byte ptr [rcx+19h], 0
0x14000ed4a  jnz     short loc_14000ED53
0x14000ed4c  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>::_Min(std::_Tree_node<std::pair<std::wstring const,ulong>,void *> *)
0x14000ed51  jmp     short loc_14000ED6C
0x14000ed53  mov     rax, [rbx+8]
0x14000ed57  jmp     short loc_14000ED66
0x14000ed59  cmp     rbx, [rax+10h]
0x14000ed5d  jnz     short loc_14000ED6C
0x14000ed5f  mov     rbx, rax
0x14000ed62  mov     rax, [rax+8]
0x14000ed66  cmp     byte ptr [rax+19h], 0
0x14000ed6a  jz      short loc_14000ED59
0x14000ed6c  mov     rbx, rax
0x14000ed6f  jmp     loc_14000EC9F
0x14000ed74  mov     ebx, 8007000Eh
0x14000ed79  jmp     short loc_14000EDAA
0x14000ed7b  xor     ebx, ebx
0x14000ed7d  xor     r9b, r9b
0x14000ed80  mov     rdx, [rbp+var_10]
0x14000ed84  mov     r8, rdx
0x14000ed87  mov     rdx, [rdx]
0x14000ed8a  lea     rcx, [rbp+arg_0]
0x14000ed8e  call    std__for_each_std___List_iterator_std___List_val_std___List_simple_types__Job_________lambda_b95765a8bf9c1cd66ddb5a7621850a5b___
0x14000ed93  xor     r9b, r9b
0x14000ed96  mov     rdx, [rbp+var_20]
0x14000ed9a  mov     r8, rdx
0x14000ed9d  mov     rdx, [rdx]
0x14000eda0  lea     rcx, [rbp+arg_0]
0x14000eda4  call    std__for_each_std___List_iterator_std___List_val_std___List_simple_types__Job_________lambda_c6672250848d4967b274276ac94b90f1___
0x14000eda9  nop
0x14000edaa  lea     rcx, [rbp+var_20]
0x14000edae  call    ??1?$list@PEAU_Job@@V?$allocator@PEAU_Job@@@std@@@std@@QEAA@XZ; std::list<_Job *>::~list<_Job *>(void)
0x14000edb3  nop
0x14000edb4  lea     rcx, [rbp+var_10]
0x14000edb8  call    ??1?$list@PEAU_Job@@V?$allocator@PEAU_Job@@@std@@@std@@QEAA@XZ; std::list<_Job *>::~list<_Job *>(void)
0x14000edbd  lea     rcx, ?m_critSec@JobExecution@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14000edc4  call    cs:__imp_LeaveCriticalSection
0x14000edca  lea     rcx, aFinishedProces; "++ Finished processing the job list ++"
0x14000edd1  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000edd6  mov     eax, ebx
0x14000edd8  mov     rbx, [rsp+40h+arg_8]
0x14000eddd  add     rsp, 40h
0x14000ede1  pop     rbp
0x14000ede2  retn
```
