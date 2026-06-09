# JobHelper::DeleteJob(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140018d08`
- end: `0x140018e42`
- name: `?DeleteJob@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `314`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x14000cd78`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x14000740c`
- `0x1400074d4`
- `0x1400156e0`
- `0x140015a38`
- `0x140018b40`
- `0x140018d08`
- `0x140019750`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140018dcf`
- `KERNEL32!LeaveCriticalSection` at `0x140018dcf`
- `KERNEL32!EnterCriticalSection` at `0x140018d49`
- `KERNEL32!EnterCriticalSection` at `0x140018d49`

## string_xrefs

- `0x140018dad`: `DeleteRegKeyRecursive for subkey %1 failed`
- `0x140018de9`: `Failed to delete job %1 from registry.  Error = 0x%2!x!.`
- `0x140018e04`: `Deleted job %1 from registry.`

## pseudocode

```c
__int64 __fastcall JobHelper::DeleteJob(_QWORD *a1, __int64 a2)
{
  int JobRegPath; // edi
  _QWORD *v5; // rsi
  __int64 v6; // rdx
  const unsigned __int16 *v7; // rdx
  unsigned __int16 *v9[4]; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v10[4]; // [rsp+40h] [rbp-30h] BYREF

  std::wstring::wstring((__int64)v10, (__int64)&word_14001E5B4);
  EnterCriticalSection(&JobHelper::m_critSec);
  JobRegPath = JobHelper::GetJobRegPath(a1, a2, v10);
  if ( JobRegPath >= 0 )
  {
    v5 = v10;
    if ( v10[3] >= 8u )
      v5 = (_QWORD *)v10[0];
    JobHelper::DeleteContent((__int64)a1, a2);
    FindLastNoSiblingFromLeaf(v9, v6, v5);
    v7 = (const unsigned __int16 *)v9;
    if ( v9[3] >= (unsigned __int16 *)8 )
      v7 = v9[0];
    JobRegPath = DeleteRegKeyRecursive(HKEY_LOCAL_MACHINE, v7);
    if ( JobRegPath < 0 )
      LogError(L"DeleteRegKeyRecursive for subkey %1 failed", v5);
    std::wstring::_Tidy(v9, 1, 0);
  }
  LeaveCriticalSection(&JobHelper::m_critSec);
  if ( JobRegPath >= 0 )
  {
    if ( a1[3] >= 8u )
      a1 = (_QWORD *)*a1;
    LogInfo(L"Deleted job %1 from registry.", a1);
  }
  else
  {
    if ( a1[3] >= 8u )
      a1 = (_QWORD *)*a1;
    LogError(L"Failed to delete job %1 from registry.  Error = 0x%2!x!.", a1, (unsigned int)JobRegPath);
  }
  std::wstring::_Tidy(v10, 1, 0);
  return (unsigned int)JobRegPath;
}

```

## disassembly

```asm
0x140018d08  mov     [rsp-18h+arg_10], rbx
0x140018d0d  mov     [rsp-18h+arg_18], rsi
0x140018d12  push    rbp
0x140018d13  push    rdi
0x140018d14  push    r14
0x140018d16  mov     rbp, rsp
0x140018d19  sub     rsp, 70h
0x140018d1d  mov     rax, cs:__security_cookie
0x140018d24  xor     rax, rsp
0x140018d27  mov     [rbp+var_10], rax
0x140018d2b  mov     r14, rdx
0x140018d2e  mov     rbx, rcx
0x140018d31  lea     rdx, word_14001E5B4
0x140018d38  lea     rcx, [rbp+var_30]
0x140018d3c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140018d41  nop
0x140018d42  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x140018d49  call    cs:__imp_EnterCriticalSection
0x140018d4f  lea     r8, [rbp+var_30]
0x140018d53  mov     rdx, r14
0x140018d56  mov     rcx, rbx
0x140018d59  call    ?GetJobRegPath@JobHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring const &,std::wstring const &,std::wstring &)
0x140018d5e  mov     edi, eax
0x140018d60  test    eax, eax
0x140018d62  js      short loc_140018DC8
0x140018d64  lea     rsi, [rbp+var_30]
0x140018d68  cmp     [rbp+var_18], 8
0x140018d6d  cmovnb  rsi, [rbp+var_30]
0x140018d72  mov     rdx, r14
0x140018d75  mov     rcx, rbx
0x140018d78  call    ?DeleteContent@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; JobHelper::DeleteContent(std::wstring const &,std::wstring &)
0x140018d7d  mov     r8, rsi
0x140018d80  lea     rcx, [rbp+var_50]
0x140018d84  call    ?FindLastNoSiblingFromLeaf@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG@Z; FindLastNoSiblingFromLeaf(HKEY__ *,ushort const *)
0x140018d89  nop
0x140018d8a  lea     rdx, [rbp+var_50]
0x140018d8e  cmp     [rbp+var_38], 8
0x140018d93  cmovnb  rdx, [rbp+var_50]; unsigned __int16 *
0x140018d98  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x140018d9f  call    ?DeleteRegKeyRecursive@@YAJPEAUHKEY__@@PEBG@Z; DeleteRegKeyRecursive(HKEY__ *,ushort const *)
0x140018da4  mov     edi, eax
0x140018da6  test    eax, eax
0x140018da8  jns     short loc_140018DBA
0x140018daa  mov     rdx, rsi
0x140018dad  lea     rcx, aDeleteregkeyre; "DeleteRegKeyRecursive for subkey %1 fai"...
0x140018db4  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140018db9  nop
0x140018dba  xor     r8d, r8d
0x140018dbd  mov     dl, 1
0x140018dbf  lea     rcx, [rbp+var_50]
0x140018dc3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140018dc8  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x140018dcf  call    cs:__imp_LeaveCriticalSection
0x140018dd5  test    edi, edi
0x140018dd7  jns     short loc_140018DF7
0x140018dd9  cmp     qword ptr [rbx+18h], 8
0x140018dde  jb      short loc_140018DE3
0x140018de0  mov     rbx, [rbx]
0x140018de3  mov     r8d, edi
0x140018de6  mov     rdx, rbx
0x140018de9  lea     rcx, aFailedToDelete; "Failed to delete job %1 from registry. "...
0x140018df0  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140018df5  jmp     short loc_140018E11
0x140018df7  cmp     qword ptr [rbx+18h], 8
0x140018dfc  jb      short loc_140018E01
0x140018dfe  mov     rbx, [rbx]
0x140018e01  mov     rdx, rbx
0x140018e04  lea     rcx, aDeletedJob1Fro; "Deleted job %1 from registry."
0x140018e0b  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140018e10  nop
0x140018e11  xor     r8d, r8d
0x140018e14  mov     dl, 1
0x140018e16  lea     rcx, [rbp+var_30]
0x140018e1a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140018e1f  mov     eax, edi
0x140018e21  mov     rcx, [rbp+var_10]
0x140018e25  xor     rcx, rsp; StackCookie
0x140018e28  call    __security_check_cookie
0x140018e2d  lea     r11, [rsp+70h+var_s0]
0x140018e32  mov     rbx, [r11+30h]
0x140018e36  mov     rsi, [r11+38h]
0x140018e3a  mov     rsp, r11
0x140018e3d  pop     r14
0x140018e3f  pop     rdi
0x140018e40  pop     rbp
0x140018e41  retn
```
