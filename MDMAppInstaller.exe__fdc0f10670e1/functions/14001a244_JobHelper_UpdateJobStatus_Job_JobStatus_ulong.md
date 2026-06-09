# JobHelper::UpdateJobStatus(_Job &,JobStatus,ulong)

- ea: `0x14001a244`
- end: `0x14001a411`
- name: `?UpdateJobStatus@JobHelper@@SAJAEAU_Job@@W4JobStatus@@K@Z`
- size: `461`
- prototype: `__int64 __fastcall(__int64 *, signed int, unsigned int)`
- caller_count: `8`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000a39c`
- `0x14000d134`
- `0x14000d470`
- `0x14000d898`
- `0x14000dab4`
- `0x14000e6cc`
- `0x14000eea4`
- `0x14001104c`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x14000740c`
- `0x1400074d4`
- `0x1400182dc`
- `0x140019750`
- `0x14001a244`
- `0x14001a550`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14001a3b5`
- `KERNEL32!LeaveCriticalSection` at `0x14001a3b5`
- `KERNEL32!EnterCriticalSection` at `0x14001a27f`
- `KERNEL32!EnterCriticalSection` at `0x14001a27f`

## string_xrefs

- `0x14001a3a2`: `Updated job %1 with JobStatus = %2!d!, LastError = 0x%3!x!, RetryStatus = %4!d!`
- `0x14001a3db`: `UpdateJobStatus failed for job %1. Error = 0x%2!x!. Attempting to set JobStatus to value %3!d! and JobLastError to 0x%4!x!.`

## pseudocode

```c
__int64 __fastcall JobHelper::UpdateJobStatus(__int64 *a1, signed int a2, unsigned int a3)
{
  HKEY v6; // rcx
  int JobRegPath; // esi
  const unsigned __int16 *v8; // rbp
  HKEY v9; // rcx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  __int64 *v15; // rdx
  __int64 v16; // r9
  struct _SECURITY_ATTRIBUTES *v18; // [rsp+20h] [rbp-68h]
  unsigned __int16 *v19[4]; // [rsp+30h] [rbp-58h] BYREF

  std::wstring::wstring((__int64)v19, (__int64)&word_14001E5B4);
  EnterCriticalSection(&JobHelper::m_critSec);
  JobRegPath = JobHelper::GetJobRegPath(a1, a1 + 4, v19);
  if ( JobRegPath >= 0 )
  {
    v8 = (const unsigned __int16 *)v19;
    if ( v19[3] >= (unsigned __int16 *)8 )
      v8 = v19[0];
    JobRegPath = WriteRegDWORDValue(v6, v8, L"Status", a2, v18);
    if ( JobRegPath >= 0 )
    {
      JobRegPath = WriteRegDWORDValue(v9, v8, L"LastError", a3, v18);
      if ( JobRegPath >= 0 )
      {
        *((_DWORD *)a1 + 37) = a2;
        *((_DWORD *)a1 + 40) = a3;
        if ( a2 > 48 )
        {
          v10 = a2 - 50;
          if ( v10 )
          {
            v11 = v10 - 5;
            if ( v11 )
            {
              v12 = v11 - 5;
              if ( !v12 )
                goto LABEL_25;
              v13 = v12 - 10;
              if ( !v13 )
                goto LABEL_25;
              v14 = v13 - 40;
              if ( v14 && v14 != 30 )
                goto LABEL_23;
            }
          }
        }
        else
        {
          if ( a2 == 48 )
          {
            *((_DWORD *)a1 + 39) = 30;
            goto LABEL_23;
          }
          if ( a2 == 10 )
            goto LABEL_14;
          if ( a2 != 20 && a2 != 25 )
          {
            if ( a2 != 30 )
            {
              if ( a2 == 40 || a2 == 45 )
LABEL_14:
                *((_DWORD *)a1 + 39) = 10;
LABEL_23:
              if ( (unsigned __int64)a1[3] < 8 )
                v15 = a1;
              else
                v15 = (__int64 *)*a1;
              LODWORD(v18) = *((_DWORD *)a1 + 39);
              LogInfo(
                L"Updated job %1 with JobStatus = %2!d!, LastError = 0x%3!x!, RetryStatus = %4!d!",
                v15,
                *((unsigned int *)a1 + 37),
                a3,
                v18);
              goto LABEL_29;
            }
LABEL_25:
            JobRegPath = JobHelper::UpdateProductVersion((struct _Job *)a1);
            if ( JobRegPath < 0 )
              goto LABEL_29;
            *((_DWORD *)a1 + 39) = *((_DWORD *)a1 + 38) != 0 ? 40 : 20;
            goto LABEL_23;
          }
        }
        *((_DWORD *)a1 + 39) = 20;
        goto LABEL_23;
      }
    }
  }
LABEL_29:
  LeaveCriticalSection(&JobHelper::m_critSec);
  if ( JobRegPath < 0 )
  {
    v16 = *((unsigned int *)a1 + 37);
    if ( (unsigned __int64)a1[3] >= 8 )
      a1 = (__int64 *)*a1;
    LODWORD(v18) = a3;
    LogError(
      L"UpdateJobStatus failed for job %1. Error = 0x%2!x!. Attempting to set JobStatus to value %3!d! and JobLastError to 0x%4!x!.",
      a1,
      (unsigned int)JobRegPath,
      v16,
      v18);
  }
  std::wstring::_Tidy(v19, 1, 0);
  return (unsigned int)JobRegPath;
}

```

## disassembly

```asm
0x14001a244  push    rbx
0x14001a246  push    rbp
0x14001a247  push    rsi
0x14001a248  push    rdi
0x14001a249  push    r14
0x14001a24b  sub     rsp, 60h
0x14001a24f  mov     rax, cs:__security_cookie
0x14001a256  xor     rax, rsp
0x14001a259  mov     [rsp+88h+var_38], rax
0x14001a25e  mov     r14d, r8d
0x14001a261  mov     ebx, edx
0x14001a263  mov     rdi, rcx
0x14001a266  lea     rdx, word_14001E5B4
0x14001a26d  lea     rcx, [rsp+88h+var_58]
0x14001a272  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14001a277  nop
0x14001a278  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14001a27f  call    cs:__imp_EnterCriticalSection
0x14001a285  lea     rdx, [rdi+20h]
0x14001a289  lea     r8, [rsp+88h+var_58]
0x14001a28e  mov     rcx, rdi
0x14001a291  call    ?GetJobRegPath@JobHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring const &,std::wstring const &,std::wstring &)
0x14001a296  mov     esi, eax
0x14001a298  test    eax, eax
0x14001a29a  js      loc_14001A3AE
0x14001a2a0  lea     rbp, [rsp+88h+var_58]
0x14001a2a5  cmp     [rsp+88h+var_40], 8
0x14001a2ab  cmovnb  rbp, [rsp+88h+var_58]
0x14001a2b1  mov     r9d, ebx; unsigned int
0x14001a2b4  lea     r8, aStatus; "Status"
0x14001a2bb  mov     rdx, rbp; unsigned __int16 *
0x14001a2be  call    ?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z; WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x14001a2c3  mov     esi, eax
0x14001a2c5  test    eax, eax
0x14001a2c7  js      loc_14001A3AE
0x14001a2cd  mov     r9d, r14d; unsigned int
0x14001a2d0  lea     r8, aLasterror; "LastError"
0x14001a2d7  mov     rdx, rbp; unsigned __int16 *
0x14001a2da  call    ?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z; WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x14001a2df  mov     esi, eax
0x14001a2e1  test    eax, eax
0x14001a2e3  js      loc_14001A3AE
0x14001a2e9  mov     [rdi+94h], ebx
0x14001a2ef  mov     [rdi+0A0h], r14d
0x14001a2f6  mov     ebp, 14h
0x14001a2fb  cmp     ebx, 30h ; '0'
0x14001a2fe  jg      short loc_14001A337
0x14001a300  jz      short loc_14001A32B
0x14001a302  cmp     ebx, 0Ah
0x14001a305  jz      short loc_14001A31F
0x14001a307  cmp     ebx, ebp
0x14001a309  jz      short loc_14001A355
0x14001a30b  cmp     ebx, 19h
0x14001a30e  jz      short loc_14001A355
0x14001a310  cmp     ebx, 1Eh
0x14001a313  jz      short loc_14001A36D
0x14001a315  cmp     ebx, 28h ; '('
0x14001a318  jz      short loc_14001A31F
0x14001a31a  cmp     ebx, 2Dh ; '-'
0x14001a31d  jnz     short loc_14001A35B
0x14001a31f  mov     dword ptr [rdi+9Ch], 0Ah
0x14001a329  jmp     short loc_14001A35B
0x14001a32b  mov     dword ptr [rdi+9Ch], 1Eh
0x14001a335  jmp     short loc_14001A35B
0x14001a337  sub     ebx, 32h ; '2'
0x14001a33a  jz      short loc_14001A355
0x14001a33c  sub     ebx, 5
0x14001a33f  jz      short loc_14001A355
0x14001a341  sub     ebx, 5
0x14001a344  jz      short loc_14001A36D
0x14001a346  sub     ebx, 0Ah
0x14001a349  jz      short loc_14001A36D
0x14001a34b  sub     ebx, 28h ; '('
0x14001a34e  jz      short loc_14001A355
0x14001a350  cmp     ebx, 1Eh
0x14001a353  jnz     short loc_14001A35B
0x14001a355  mov     [rdi+9Ch], ebp
0x14001a35b  mov     eax, [rdi+9Ch]
0x14001a361  cmp     qword ptr [rdi+18h], 8
0x14001a366  jb      short loc_14001A391
0x14001a368  mov     rdx, [rdi]
0x14001a36b  jmp     short loc_14001A394
0x14001a36d  mov     rcx, rdi; struct _Job *
0x14001a370  call    ?UpdateProductVersion@JobHelper@@SAJAEAU_Job@@@Z; JobHelper::UpdateProductVersion(_Job &)
0x14001a375  mov     esi, eax
0x14001a377  test    eax, eax
0x14001a379  js      short loc_14001A3AE
0x14001a37b  mov     eax, [rdi+98h]
0x14001a381  neg     eax
0x14001a383  sbb     ecx, ecx
0x14001a385  and     ecx, ebp
0x14001a387  add     ecx, ebp
0x14001a389  mov     [rdi+9Ch], ecx
0x14001a38f  jmp     short loc_14001A35B
0x14001a391  mov     rdx, rdi
0x14001a394  mov     [rsp+88h+var_68], eax
0x14001a398  mov     r9d, r14d
0x14001a39b  mov     r8d, [rdi+94h]
0x14001a3a2  lea     rcx, aUpdatedJob1Wit_0; "Updated job %1 with JobStatus = %2!d!, "...
0x14001a3a9  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14001a3ae  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14001a3b5  call    cs:__imp_LeaveCriticalSection
0x14001a3bb  test    esi, esi
0x14001a3bd  jns     short loc_14001A3E8
0x14001a3bf  mov     r9d, [rdi+94h]
0x14001a3c6  cmp     qword ptr [rdi+18h], 8
0x14001a3cb  jb      short loc_14001A3D0
0x14001a3cd  mov     rdi, [rdi]
0x14001a3d0  mov     [rsp+88h+var_68], r14d
0x14001a3d5  mov     r8d, esi
0x14001a3d8  mov     rdx, rdi
0x14001a3db  lea     rcx, aUpdatejobstatu_0; "UpdateJobStatus failed for job %1. Erro"...
0x14001a3e2  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001a3e7  nop
0x14001a3e8  xor     r8d, r8d
0x14001a3eb  mov     dl, 1
0x14001a3ed  lea     rcx, [rsp+88h+var_58]
0x14001a3f2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14001a3f7  mov     eax, esi
0x14001a3f9  mov     rcx, [rsp+88h+var_38]
0x14001a3fe  xor     rcx, rsp; StackCookie
0x14001a401  call    __security_check_cookie
0x14001a406  add     rsp, 60h
0x14001a40a  pop     r14
0x14001a40c  pop     rdi
0x14001a40d  pop     rsi
0x14001a40e  pop     rbp
0x14001a40f  pop     rbx
0x14001a410  retn
```
