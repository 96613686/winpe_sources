# JobHelper::UpdateEnforcementRetryIndex(_Job &,ulong)

- ea: `0x14001a0c4`
- end: `0x14001a23d`
- name: `?UpdateEnforcementRetryIndex@JobHelper@@SAJAEAU_Job@@K@Z`
- size: `377`
- prototype: `__int64 __fastcall(struct _Job *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000d470`
- `0x14000dab4`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x14000740c`
- `0x1400074d4`
- `0x1400182dc`
- `0x1400183f0`
- `0x140019750`
- `0x14001a0c4`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14001a1ba`
- `KERNEL32!LeaveCriticalSection` at `0x14001a1ba`
- `KERNEL32!EnterCriticalSection` at `0x14001a110`
- `KERNEL32!EnterCriticalSection` at `0x14001a110`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14001a103`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14001a103`

## string_xrefs

- `0x14001a1df`: `UpdateEnforcementRetryIndex for Job %1 to failed to set value %2 to %3!d!. Error = 0x%4!x!.`
- `0x14001a204`: `UpdateEnforcementRetryIndex for Job %1 successfully set value %2 to %3!d!.`

## pseudocode

```c
__int64 __fastcall JobHelper::UpdateEnforcementRetryIndex(struct _Job *a1, unsigned int a2)
{
  HKEY v4; // rcx
  int JobRegPath; // edi
  const unsigned __int16 *v6; // r8
  DWORD dwLowDateTime; // eax
  const unsigned __int16 *v8; // rdx
  int v9; // eax
  HKEY v10; // rcx
  const unsigned __int16 *v11; // rdx
  int v12; // eax
  struct _SECURITY_ATTRIBUTES *v14; // [rsp+20h] [rbp-40h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int16 *v16[3]; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v17; // [rsp+50h] [rbp-10h]

  std::wstring::wstring((__int64)v16, (__int64)&word_14001E5B4);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  EnterCriticalSection(&JobHelper::m_critSec);
  JobRegPath = JobHelper::GetJobRegPath(a1, (_QWORD *)a1 + 4, v16);
  if ( JobRegPath >= 0 )
  {
    dwLowDateTime = SystemTimeAsFileTime.dwLowDateTime;
    *(struct _FILETIME *)((char *)a1 + 364) = SystemTimeAsFileTime;
    v8 = (const unsigned __int16 *)v16;
    if ( v17 >= 8 )
      v8 = v16[0];
    v9 = WriteRegQWORDValue(v4, v8, v6, dwLowDateTime + ((unsigned __int64)*((unsigned int *)a1 + 92) << 32), v14);
    JobRegPath = v9;
    if ( v9 >= 0 )
    {
      *((_DWORD *)a1 + 94) = a2;
      v11 = (const unsigned __int16 *)v16;
      if ( v17 >= 8 )
        v11 = v16[0];
      v12 = WriteRegDWORDValue(v10, v11, L"EnforcementRetryIndex", a2, v14);
      JobRegPath = v12;
      if ( v12 < 0 )
        LogError(L"failed to set %1 0x%2!x!", L"EnforcementRetryIndex", (unsigned int)v12);
    }
    else
    {
      LogError(L"failed to set %1 ,0x%2!x!", L"EnforcementStartTime", (unsigned int)v9);
    }
  }
  LeaveCriticalSection(&JobHelper::m_critSec);
  if ( JobRegPath >= 0 )
  {
    if ( *((_QWORD *)a1 + 3) >= 8u )
      a1 = *(struct _Job **)a1;
    LogInfo(
      L"UpdateEnforcementRetryIndex for Job %1 successfully set value %2 to %3!d!.",
      a1,
      L"EnforcementRetryIndex",
      a2);
  }
  else
  {
    if ( *((_QWORD *)a1 + 3) >= 8u )
      a1 = *(struct _Job **)a1;
    LODWORD(v14) = JobRegPath;
    LogError(
      L"UpdateEnforcementRetryIndex for Job %1 to failed to set value %2 to %3!d!. Error = 0x%4!x!.",
      a1,
      L"EnforcementRetryIndex",
      a2,
      v14);
  }
  std::wstring::_Tidy(v16, 1, 0);
  return (unsigned int)JobRegPath;
}

```

## disassembly

```asm
0x14001a0c4  mov     [rsp-18h+arg_10], rbx
0x14001a0c9  push    rbp
0x14001a0ca  push    rsi
0x14001a0cb  push    rdi
0x14001a0cc  mov     rbp, rsp
0x14001a0cf  sub     rsp, 60h
0x14001a0d3  mov     rax, cs:__security_cookie
0x14001a0da  xor     rax, rsp
0x14001a0dd  mov     [rbp+var_8], rax
0x14001a0e1  mov     esi, edx
0x14001a0e3  mov     rbx, rcx
0x14001a0e6  lea     rdx, word_14001E5B4
0x14001a0ed  lea     rcx, [rbp+var_28]
0x14001a0f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14001a0f6  nop
0x14001a0f7  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x14001a0ff  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14001a103  call    cs:__imp_GetSystemTimeAsFileTime
0x14001a109  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14001a110  call    cs:__imp_EnterCriticalSection
0x14001a116  lea     rdx, [rbx+20h]
0x14001a11a  lea     r8, [rbp+var_28]
0x14001a11e  mov     rcx, rbx
0x14001a121  call    ?GetJobRegPath@JobHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring const &,std::wstring const &,std::wstring &)
0x14001a126  mov     edi, eax
0x14001a128  test    eax, eax
0x14001a12a  js      loc_14001A1B3
0x14001a130  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14001a134  mov     [rbx+16Ch], rax
0x14001a13b  mov     r9d, [rbx+170h]
0x14001a142  shl     r9, 20h
0x14001a146  mov     eax, eax
0x14001a148  add     r9, rax; __int64
0x14001a14b  lea     rdx, [rbp+var_28]
0x14001a14f  cmp     [rbp+var_10], 8
0x14001a154  cmovnb  rdx, [rbp+var_28]; unsigned __int16 *
0x14001a159  call    ?WriteRegQWORDValue@@YAJPEAUHKEY__@@PEBG1_JPEAU_SECURITY_ATTRIBUTES@@@Z; WriteRegQWORDValue(HKEY__ *,ushort const *,ushort const *,__int64,_SECURITY_ATTRIBUTES *)
0x14001a15e  mov     edi, eax
0x14001a160  test    eax, eax
0x14001a162  jns     short loc_14001A174
0x14001a164  lea     rdx, aEnforcementsta; "EnforcementStartTime"
0x14001a16b  lea     rcx, aFailedToSet10x; "failed to set %1 ,0x%2!x!"
0x14001a172  jmp     short loc_14001A1AB
0x14001a174  mov     [rbx+178h], esi
0x14001a17a  lea     rdx, [rbp+var_28]
0x14001a17e  cmp     [rbp+var_10], 8
0x14001a183  cmovnb  rdx, [rbp+var_28]; unsigned __int16 *
0x14001a188  mov     r9d, esi; unsigned int
0x14001a18b  lea     r8, aEnforcementret; "EnforcementRetryIndex"
0x14001a192  call    ?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z; WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x14001a197  mov     edi, eax
0x14001a199  test    eax, eax
0x14001a19b  jns     short loc_14001A1B3
0x14001a19d  lea     rdx, aEnforcementret; "EnforcementRetryIndex"
0x14001a1a4  lea     rcx, aFailedToSet10x_0; "failed to set %1 0x%2!x!"
0x14001a1ab  mov     r8d, eax
0x14001a1ae  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001a1b3  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14001a1ba  call    cs:__imp_LeaveCriticalSection
0x14001a1c0  test    edi, edi
0x14001a1c2  jns     short loc_14001A1ED
0x14001a1c4  cmp     qword ptr [rbx+18h], 8
0x14001a1c9  jb      short loc_14001A1CE
0x14001a1cb  mov     rbx, [rbx]
0x14001a1ce  mov     [rsp+60h+var_40], edi
0x14001a1d2  mov     r9d, esi
0x14001a1d5  lea     r8, aEnforcementret; "EnforcementRetryIndex"
0x14001a1dc  mov     rdx, rbx
0x14001a1df  lea     rcx, aUpdateenforcem_0; "UpdateEnforcementRetryIndex for Job %1 "...
0x14001a1e6  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001a1eb  jmp     short loc_14001A211
0x14001a1ed  cmp     qword ptr [rbx+18h], 8
0x14001a1f2  jb      short loc_14001A1F7
0x14001a1f4  mov     rbx, [rbx]
0x14001a1f7  mov     r9d, esi
0x14001a1fa  lea     r8, aEnforcementret; "EnforcementRetryIndex"
0x14001a201  mov     rdx, rbx
0x14001a204  lea     rcx, aUpdateenforcem; "UpdateEnforcementRetryIndex for Job %1 "...
0x14001a20b  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14001a210  nop
0x14001a211  xor     r8d, r8d
0x14001a214  mov     dl, 1
0x14001a216  lea     rcx, [rbp+var_28]
0x14001a21a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14001a21f  mov     eax, edi
0x14001a221  mov     rcx, [rbp+var_8]
0x14001a225  xor     rcx, rsp; StackCookie
0x14001a228  call    __security_check_cookie
0x14001a22d  mov     rbx, [rsp+60h+arg_10]
0x14001a235  add     rsp, 60h
0x14001a239  pop     rdi
0x14001a23a  pop     rsi
0x14001a23b  pop     rbp
0x14001a23c  retn
```
