# JobHelper::CheckJobIntentChanged(_Job &,bool &)

- ea: `0x140018970`
- end: `0x140018a61`
- name: `?CheckJobIntentChanged@JobHelper@@SAJAEAU_Job@@AEA_N@Z`
- size: `241`
- prototype: `__int64 __fastcall(struct _Job *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14000e6cc`

## callees

- `0x140003d00`
- `0x1400074d4`
- `0x14000775c`
- `0x140008e80`
- `0x140018970`
- `0x140019054`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140018a17`
- `KERNEL32!LeaveCriticalSection` at `0x140018a17`
- `KERNEL32!EnterCriticalSection` at `0x1400189af`
- `KERNEL32!EnterCriticalSection` at `0x1400189af`

## string_xrefs

- `0x1400189de`: `Install`
- `0x1400189e5`: `Uninstall`

## pseudocode

```c
__int64 __fastcall JobHelper::CheckJobIntentChanged(struct _Job *a1, bool *a2)
{
  int Job; // ebx
  int v5; // eax
  const wchar_t *v6; // r8
  _QWORD *v7; // rdx
  __int64 v8; // rdx
  _QWORD v10[18]; // [rsp+20h] [rbp-1E8h] BYREF
  int v11; // [rsp+B0h] [rbp-158h]

  _Job::_Job((_Job *)v10);
  *a2 = 0;
  EnterCriticalSection(&JobHelper::m_critSec);
  Job = JobHelper::GetJob(a1, (__int64)a1 + 32, (__int64)v10);
  if ( Job >= 0 )
  {
    v5 = v11;
    if ( v11 != *((_DWORD *)a1 + 36) )
    {
      *a2 = 1;
      v6 = L"Install";
      if ( v5 != 1 )
        v6 = L"Uninstall";
      v7 = v10;
      if ( v10[3] >= 8u )
        v7 = (_QWORD *)v10[0];
      LogInfo(L" Job intent changed for job %1. The new intent = '%2'.", v7, v6);
    }
  }
  LeaveCriticalSection(&JobHelper::m_critSec);
  if ( Job < 0 )
    LogWarn(L"Unable to determine if the job intent changed. Error = 0x%1!x!.", (unsigned int)Job);
  _Job::~_Job((_Job *)v10, v8);
  return (unsigned int)Job;
}

```

## disassembly

```asm
0x140018970  mov     [rsp+arg_10], rbx
0x140018975  mov     [rsp+arg_18], rsi
0x14001897a  push    rdi
0x14001897b  sub     rsp, 200h
0x140018982  mov     rax, cs:__security_cookie
0x140018989  xor     rax, rsp
0x14001898c  mov     [rsp+208h+var_18], rax
0x140018994  mov     rsi, rdx
0x140018997  mov     rdi, rcx
0x14001899a  lea     rcx, [rsp+208h+var_1E8]; this
0x14001899f  call    ??0_Job@@QEAA@XZ; _Job::_Job(void)
0x1400189a4  nop
0x1400189a5  mov     byte ptr [rsi], 0
0x1400189a8  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x1400189af  call    cs:__imp_EnterCriticalSection
0x1400189b5  lea     rdx, [rdi+20h]
0x1400189b9  lea     r8, [rsp+208h+var_1E8]
0x1400189be  mov     rcx, rdi
0x1400189c1  call    ?GetJob@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@AEAU_Job@@@Z; JobHelper::GetJob(std::wstring const &,std::wstring &,_Job &)
0x1400189c6  mov     ebx, eax
0x1400189c8  test    eax, eax
0x1400189ca  js      short loc_140018A10
0x1400189cc  mov     eax, [rsp+208h+var_158]
0x1400189d3  cmp     eax, [rdi+90h]
0x1400189d9  jz      short loc_140018A10
0x1400189db  mov     byte ptr [rsi], 1
0x1400189de  lea     r8, aInstall; "Install"
0x1400189e5  lea     rdx, aUninstall; "Uninstall"
0x1400189ec  cmp     eax, 1
0x1400189ef  cmovnz  r8, rdx
0x1400189f3  lea     rdx, [rsp+208h+var_1E8]
0x1400189f8  cmp     [rsp+208h+var_1D0], 8
0x1400189fe  cmovnb  rdx, [rsp+208h+var_1E8]
0x140018a04  lea     rcx, aJobIntentChang; " Job intent changed for job %1. The new"...
0x140018a0b  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140018a10  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x140018a17  call    cs:__imp_LeaveCriticalSection
0x140018a1d  test    ebx, ebx
0x140018a1f  jns     short loc_140018A30
0x140018a21  mov     edx, ebx
0x140018a23  lea     rcx, aUnableToDeterm; "Unable to determine if the job intent c"...
0x140018a2a  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x140018a2f  nop
0x140018a30  lea     rcx, [rsp+208h+var_1E8]; this
0x140018a35  call    ??1_Job@@QEAA@XZ; _Job::~_Job(void)
0x140018a3a  mov     eax, ebx
0x140018a3c  mov     rcx, [rsp+208h+var_18]
0x140018a44  xor     rcx, rsp; StackCookie
0x140018a47  call    __security_check_cookie
0x140018a4c  lea     r11, [rsp+208h+var_8]
0x140018a54  mov     rbx, [r11+20h]
0x140018a58  mov     rsi, [r11+28h]
0x140018a5c  mov     rsp, r11
0x140018a5f  pop     rdi
0x140018a60  retn
```
