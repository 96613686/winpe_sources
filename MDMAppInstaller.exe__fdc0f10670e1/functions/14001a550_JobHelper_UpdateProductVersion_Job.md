# JobHelper::UpdateProductVersion(_Job &)

- ea: `0x14001a550`
- end: `0x14001a680`
- name: `?UpdateProductVersion@JobHelper@@SAJAEAU_Job@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(struct _Job *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001a244`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x14000740c`
- `0x1400074d4`
- `0x140018520`
- `0x140019750`
- `0x14001a550`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14001a613`
- `KERNEL32!LeaveCriticalSection` at `0x14001a613`
- `KERNEL32!EnterCriticalSection` at `0x14001a58a`
- `KERNEL32!EnterCriticalSection` at `0x14001a58a`

## string_xrefs

- `0x14001a600`: `Updated job %1 with %2 = '%3'.`
- `0x14001a643`: `UpdateProductVersion failed for job %1. Attempting to set %2 to value '%3'. Error = 0x%4!x!.`

## pseudocode

```c
__int64 __fastcall JobHelper::UpdateProductVersion(struct _Job *a1)
{
  HKEY v2; // rcx
  int JobRegPath; // esi
  const unsigned __int16 *v4; // rdx
  const unsigned __int16 **v5; // rdi
  const unsigned __int16 *v6; // r9
  struct _Job *v7; // rdx
  struct _SECURITY_ATTRIBUTES *v9; // [rsp+20h] [rbp-48h]
  int v10; // [rsp+28h] [rbp-40h]
  unsigned __int16 *v11[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v11, (__int64)&word_14001E5B4);
  EnterCriticalSection(&JobHelper::m_critSec);
  JobRegPath = JobHelper::GetJobRegPath(a1, (_QWORD *)a1 + 4, v11);
  if ( JobRegPath >= 0 )
  {
    v4 = (const unsigned __int16 *)v11;
    if ( v11[3] >= (unsigned __int16 *)8 )
      v4 = v11[0];
    v5 = (const unsigned __int16 **)((char *)a1 + 104);
    if ( *((_QWORD *)a1 + 16) < 8u )
      v6 = (const unsigned __int16 *)((char *)a1 + 104);
    else
      v6 = *v5;
    JobRegPath = WriteRegSZValue(v2, v4, L"ProductVersion", v6, v9, v10);
    if ( JobRegPath >= 0 )
    {
      if ( *((_QWORD *)a1 + 16) >= 8u )
        v5 = (const unsigned __int16 **)*v5;
      if ( *((_QWORD *)a1 + 3) < 8u )
        v7 = a1;
      else
        v7 = *(struct _Job **)a1;
      LogInfo(L"Updated job %1 with %2 = '%3'.", v7, L"ProductVersion", v5);
    }
  }
  LeaveCriticalSection(&JobHelper::m_critSec);
  if ( JobRegPath < 0 )
  {
    if ( *((_QWORD *)a1 + 3) >= 8u )
      a1 = *(struct _Job **)a1;
    LogError(
      L"UpdateProductVersion failed for job %1. Attempting to set %2 to value '%3'. Error = 0x%4!x!.",
      a1,
      L"ProductVersion");
  }
  std::wstring::_Tidy(v11, 1, 0);
  return (unsigned int)JobRegPath;
}

```

## disassembly

```asm
0x14001a550  mov     [rsp+arg_8], rbx
0x14001a555  mov     [rsp+arg_10], rsi
0x14001a55a  push    rdi
0x14001a55b  sub     rsp, 60h
0x14001a55f  mov     rax, cs:__security_cookie
0x14001a566  xor     rax, rsp
0x14001a569  mov     [rsp+68h+var_18], rax
0x14001a56e  mov     rbx, rcx
0x14001a571  lea     rdx, word_14001E5B4
0x14001a578  lea     rcx, [rsp+68h+var_38]
0x14001a57d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14001a582  nop
0x14001a583  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14001a58a  call    cs:__imp_EnterCriticalSection
0x14001a590  lea     rdx, [rbx+20h]
0x14001a594  lea     r8, [rsp+68h+var_38]
0x14001a599  mov     rcx, rbx
0x14001a59c  call    ?GetJobRegPath@JobHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring const &,std::wstring const &,std::wstring &)
0x14001a5a1  mov     esi, eax
0x14001a5a3  test    eax, eax
0x14001a5a5  js      short loc_14001A60C
0x14001a5a7  lea     rdx, [rsp+68h+var_38]
0x14001a5ac  cmp     [rsp+68h+var_20], 8
0x14001a5b2  cmovnb  rdx, [rsp+68h+var_38]; unsigned __int16 *
0x14001a5b8  lea     rdi, [rbx+68h]
0x14001a5bc  cmp     qword ptr [rdi+18h], 8
0x14001a5c1  jb      short loc_14001A5C8
0x14001a5c3  mov     r9, [rdi]
0x14001a5c6  jmp     short loc_14001A5CB
0x14001a5c8  mov     r9, rdi; unsigned __int16 *
0x14001a5cb  lea     r8, aProductversion; "ProductVersion"
0x14001a5d2  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x14001a5d7  mov     esi, eax
0x14001a5d9  test    eax, eax
0x14001a5db  js      short loc_14001A60C
0x14001a5dd  cmp     qword ptr [rdi+18h], 8
0x14001a5e2  jb      short loc_14001A5E7
0x14001a5e4  mov     rdi, [rdi]
0x14001a5e7  cmp     qword ptr [rbx+18h], 8
0x14001a5ec  jb      short loc_14001A5F3
0x14001a5ee  mov     rdx, [rbx]
0x14001a5f1  jmp     short loc_14001A5F6
0x14001a5f3  mov     rdx, rbx
0x14001a5f6  mov     r9, rdi
0x14001a5f9  lea     r8, aProductversion; "ProductVersion"
0x14001a600  lea     rcx, aUpdatedJob1Wit; "Updated job %1 with %2 = '%3'."
0x14001a607  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14001a60c  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14001a613  call    cs:__imp_LeaveCriticalSection
0x14001a619  test    esi, esi
0x14001a61b  jns     short loc_14001A650
0x14001a61d  lea     r9, [rbx+68h]
0x14001a621  cmp     qword ptr [r9+18h], 8
0x14001a626  jb      short loc_14001A62B
0x14001a628  mov     r9, [r9]
0x14001a62b  cmp     qword ptr [rbx+18h], 8
0x14001a630  jb      short loc_14001A635
0x14001a632  mov     rbx, [rbx]
0x14001a635  mov     dword ptr [rsp+68h+var_48], esi
0x14001a639  lea     r8, aProductversion; "ProductVersion"
0x14001a640  mov     rdx, rbx
0x14001a643  lea     rcx, aUpdateproductv; "UpdateProductVersion failed for job %1."...
0x14001a64a  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001a64f  nop
0x14001a650  xor     r8d, r8d
0x14001a653  mov     dl, 1
0x14001a655  lea     rcx, [rsp+68h+var_38]
0x14001a65a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14001a65f  mov     eax, esi
0x14001a661  mov     rcx, [rsp+68h+var_18]
0x14001a666  xor     rcx, rsp; StackCookie
0x14001a669  call    __security_check_cookie
0x14001a66e  lea     r11, [rsp+68h+var_8]
0x14001a673  mov     rbx, [r11+18h]
0x14001a677  mov     rsi, [r11+20h]
0x14001a67b  mov     rsp, r11
0x14001a67e  pop     rdi
0x14001a67f  retn
```
