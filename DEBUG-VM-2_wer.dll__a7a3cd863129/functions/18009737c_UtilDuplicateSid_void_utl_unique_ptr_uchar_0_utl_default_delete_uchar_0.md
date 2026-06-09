# UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x18009737c`
- end: `0x180097448`
- name: `?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `204`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800982d0`
- `0x180098544`

## callees

- `0x18000716c`
- `0x18001c650`
- `0x18001daa8`
- `0x18002cdd0`
- `0x18009737c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097425`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097425`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800973fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800973fe`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800973b7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800973b7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800973a3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800973a3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800973f4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800973f4`

## pseudocode

```c
__int64 __fastcall UtilDuplicateSid(PSID pSourceSid, PSID *a2)
{
  unsigned int v4; // ebx
  DWORD LengthSid; // esi
  __int64 unique_oversize_for; // rax
  DWORD LastError; // eax
  unsigned int v8; // eax
  PSID v9; // r8
  char v11; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 || !pSourceSid )
    return 2147942487LL;
  if ( IsValidSid(pSourceSid) )
  {
    LengthSid = GetLengthSid(pSourceSid);
    unique_oversize_for = tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(&v11, LengthSid);
    utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
      a2,
      unique_oversize_for);
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v11);
    if ( *a2 )
    {
      if ( CopySid(LengthSid, *a2, pSourceSid) )
      {
        return 0;
      }
      else
      {
        LastError = GetLastError();
        v8 = ERROR_HR_FROM_WIN32(LastError);
        v9 = *a2;
        v4 = v8;
        *a2 = 0;
        if ( v9 )
          HeapFree(g_hWerheap, 0, v9);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18009737c  mov     [rsp+arg_0], rbx
0x180097381  mov     [rsp+arg_10], rsi
0x180097386  push    rdi
0x180097387  sub     rsp, 20h
0x18009738b  mov     rdi, rdx
0x18009738e  mov     rbx, rcx
0x180097391  test    rdx, rdx
0x180097394  jz      loc_180097433
0x18009739a  test    rcx, rcx
0x18009739d  jz      loc_180097433
0x1800973a3  call    cs:__imp_IsValidSid
0x1800973a9  test    eax, eax
0x1800973ab  jnz     short loc_1800973B4
0x1800973ad  mov     ebx, 80070057h
0x1800973b2  jmp     short loc_18009742F
0x1800973b4  mov     rcx, rbx; pSid
0x1800973b7  call    cs:__imp_GetLengthSid
0x1800973bd  mov     edx, eax
0x1800973bf  lea     rcx, [rsp+28h+arg_8]
0x1800973c4  mov     esi, eax
0x1800973c6  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x1800973cb  mov     rdx, rax
0x1800973ce  mov     rcx, rdi
0x1800973d1  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x1800973d6  lea     rcx, [rsp+28h+arg_8]; void *
0x1800973db  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800973e0  mov     rdx, [rdi]; pDestinationSid
0x1800973e3  test    rdx, rdx
0x1800973e6  jnz     short loc_1800973EF
0x1800973e8  mov     ebx, 8007000Eh
0x1800973ed  jmp     short loc_18009742F
0x1800973ef  mov     r8, rbx; pSourceSid
0x1800973f2  mov     ecx, esi; nDestinationSidLength
0x1800973f4  call    cs:__imp_CopySid
0x1800973fa  test    eax, eax
0x1800973fc  jnz     short loc_18009742D
0x1800973fe  call    cs:__imp_GetLastError
0x180097404  mov     ecx, eax; unsigned int
0x180097406  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009740b  mov     r8, [rdi]; lpMem
0x18009740e  mov     ebx, eax
0x180097410  mov     qword ptr [rdi], 0
0x180097417  test    r8, r8
0x18009741a  jz      short loc_18009742F
0x18009741c  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180097423  xor     edx, edx; dwFlags
0x180097425  call    cs:__imp_HeapFree
0x18009742b  jmp     short loc_18009742F
0x18009742d  xor     ebx, ebx
0x18009742f  mov     eax, ebx
0x180097431  jmp     short loc_180097438
0x180097433  mov     eax, 80070057h
0x180097438  mov     rbx, [rsp+28h+arg_0]
0x18009743d  mov     rsi, [rsp+28h+arg_10]
0x180097442  add     rsp, 20h
0x180097446  pop     rdi
0x180097447  retn
```
