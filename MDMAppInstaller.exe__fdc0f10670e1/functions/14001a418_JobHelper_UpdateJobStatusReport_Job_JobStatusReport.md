# JobHelper::UpdateJobStatusReport(_Job &,JobStatusReport)

- ea: `0x14001a418`
- end: `0x14001a549`
- name: `?UpdateJobStatusReport@JobHelper@@SAJAEAU_Job@@W4JobStatusReport@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000cd78`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x14000740c`
- `0x1400074d4`
- `0x1400182dc`
- `0x140019750`
- `0x14001a418`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14001a4eb`
- `KERNEL32!LeaveCriticalSection` at `0x14001a4eb`
- `KERNEL32!EnterCriticalSection` at `0x14001a44d`
- `KERNEL32!EnterCriticalSection` at `0x14001a44d`

## string_xrefs

- `0x14001a4b0`: `Updated job %1 with %2 = '%3'.`
- `0x14001a513`: `UpdateJobStatusReport failed for job %1. Attempting to set %2 to value '%3!d!'. Error = 0x%4!x!.`

## pseudocode

```c
__int64 __fastcall JobHelper::UpdateJobStatusReport(__int64 *a1)
{
  HKEY v2; // rcx
  int JobRegPath; // edi
  const unsigned __int16 *v4; // rdx
  __int64 v5; // rdx
  unsigned __int64 v6; // rax
  __int64 v7; // rdx
  struct _SECURITY_ATTRIBUTES *v9; // [rsp+20h] [rbp-48h]
  unsigned __int16 *v10[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v10, (__int64)&word_14001E5B4);
  EnterCriticalSection(&JobHelper::m_critSec);
  JobRegPath = JobHelper::GetJobRegPath(a1, a1 + 4, v10);
  if ( JobRegPath >= 0 )
  {
    v4 = (const unsigned __int16 *)v10;
    if ( v10[3] >= (unsigned __int16 *)8 )
      v4 = v10[0];
    JobRegPath = WriteRegDWORDValue(v2, v4, L"JobStatusReport", 1u, v9);
    if ( JobRegPath >= 0 )
    {
      v5 = (unsigned __int64)a1[3] < 8 ? (__int64)a1 : *a1;
      LogInfo(L"Updated job %1 with %2 = '%3'.", v5, L"JobStatusReport", L"Sent(1)");
      v6 = (unsigned int)(*((_DWORD *)a1 + 37) - 30);
      if ( (unsigned int)v6 <= 0x28 )
      {
        v7 = 0x10040000001LL;
        if ( _bittest64(&v7, v6) )
          *((_DWORD *)a1 + 39) = 40;
      }
    }
  }
  LeaveCriticalSection(&JobHelper::m_critSec);
  if ( JobRegPath < 0 )
  {
    if ( (unsigned __int64)a1[3] >= 8 )
      a1 = (__int64 *)*a1;
    LODWORD(v9) = JobRegPath;
    LogError(
      L"UpdateJobStatusReport failed for job %1. Attempting to set %2 to value '%3!d!'. Error = 0x%4!x!.",
      a1,
      L"JobStatusReport",
      1,
      v9);
  }
  std::wstring::_Tidy(v10, 1, 0);
  return (unsigned int)JobRegPath;
}

```

## disassembly

```asm
0x14001a418  mov     [rsp+arg_8], rbx
0x14001a41d  push    rdi
0x14001a41e  sub     rsp, 60h
0x14001a422  mov     rax, cs:__security_cookie
0x14001a429  xor     rax, rsp
0x14001a42c  mov     [rsp+68h+var_18], rax
0x14001a431  mov     rbx, rcx
0x14001a434  lea     rdx, word_14001E5B4
0x14001a43b  lea     rcx, [rsp+68h+var_38]
0x14001a440  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14001a445  nop
0x14001a446  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14001a44d  call    cs:__imp_EnterCriticalSection
0x14001a453  lea     rdx, [rbx+20h]
0x14001a457  lea     r8, [rsp+68h+var_38]
0x14001a45c  mov     rcx, rbx
0x14001a45f  call    ?GetJobRegPath@JobHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring const &,std::wstring const &,std::wstring &)
0x14001a464  mov     edi, eax
0x14001a466  test    eax, eax
0x14001a468  js      short loc_14001A4E4
0x14001a46a  lea     rdx, [rsp+68h+var_38]
0x14001a46f  cmp     [rsp+68h+var_20], 8
0x14001a475  cmovnb  rdx, [rsp+68h+var_38]; unsigned __int16 *
0x14001a47b  mov     r9d, 1; unsigned int
0x14001a481  lea     r8, aJobstatusrepor; "JobStatusReport"
0x14001a488  call    ?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z; WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x14001a48d  mov     edi, eax
0x14001a48f  test    eax, eax
0x14001a491  js      short loc_14001A4E4
0x14001a493  cmp     qword ptr [rbx+18h], 8
0x14001a498  jb      short loc_14001A49F
0x14001a49a  mov     rdx, [rbx]
0x14001a49d  jmp     short loc_14001A4A2
0x14001a49f  mov     rdx, rbx
0x14001a4a2  lea     r9, aSent1; "Sent(1)"
0x14001a4a9  lea     r8, aJobstatusrepor; "JobStatusReport"
0x14001a4b0  lea     rcx, aUpdatedJob1Wit; "Updated job %1 with %2 = '%3'."
0x14001a4b7  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14001a4bc  mov     eax, [rbx+94h]
0x14001a4c2  add     eax, 0FFFFFFE2h
0x14001a4c5  cmp     eax, 28h ; '('
0x14001a4c8  ja      short loc_14001A4E4
0x14001a4ca  mov     rdx, 10040000001h
0x14001a4d4  bt      rdx, rax
0x14001a4d8  jnb     short loc_14001A4E4
0x14001a4da  mov     dword ptr [rbx+9Ch], 28h ; '('
0x14001a4e4  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14001a4eb  call    cs:__imp_LeaveCriticalSection
0x14001a4f1  test    edi, edi
0x14001a4f3  jns     short loc_14001A520
0x14001a4f5  cmp     qword ptr [rbx+18h], 8
0x14001a4fa  jb      short loc_14001A4FF
0x14001a4fc  mov     rbx, [rbx]
0x14001a4ff  mov     [rsp+68h+var_48], edi
0x14001a503  mov     r9d, 1
0x14001a509  lea     r8, aJobstatusrepor; "JobStatusReport"
0x14001a510  mov     rdx, rbx
0x14001a513  lea     rcx, aUpdatejobstatu; "UpdateJobStatusReport failed for job %1"...
0x14001a51a  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001a51f  nop
0x14001a520  xor     r8d, r8d
0x14001a523  mov     dl, 1
0x14001a525  lea     rcx, [rsp+68h+var_38]
0x14001a52a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14001a52f  mov     eax, edi
0x14001a531  mov     rcx, [rsp+68h+var_18]
0x14001a536  xor     rcx, rsp; StackCookie
0x14001a539  call    __security_check_cookie
0x14001a53e  mov     rbx, [rsp+68h+arg_8]
0x14001a543  add     rsp, 60h
0x14001a547  pop     rdi
0x14001a548  retn
```
