# UpdateReserveManager::GetReserveAndUserState(unsigned __int64,unsigned __int64,unsigned __int64,DiskStorageState *)

- ea: `0x180016d98`
- end: `0x180016fb1`
- name: `?GetReserveAndUserState@UpdateReserveManager@@AEAAJ_K00PEAUDiskStorageState@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(WCHAR *this, unsigned __int64, unsigned __int64, unsigned __int64, struct DiskStorageState *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180019634`

## callees

- `0x180003870`
- `0x180008140`
- `0x18000fafc`
- `0x180015ad0`
- `0x180016d98`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f69`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180016f03`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180016f03`

## string_xrefs

- `0x180016f24`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180016f3a`: `EnsureBOOL(::GetDiskFreeSpaceExW(m_WindowsDirPath, nullptr, nullptr, &FreeUserSpace))`
- `0x180016f2f`: `UpdateReserveManager::GetReserveAndUserState`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::GetReserveAndUserState(
        WCHAR *this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        struct DiskStorageState *a5)
{
  __int64 result; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rdx
  bool v12; // cc
  unsigned __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rax
  __int64 v17; // rax
  DWORD LastError; // ebx
  _QWORD v19[4]; // [rsp+30h] [rbp-61h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+50h] [rbp-41h] BYREF
  __int128 v21; // [rsp+58h] [rbp-39h] BYREF
  unsigned __int64 v22; // [rsp+68h] [rbp-29h]
  __int128 v23; // [rsp+70h] [rbp-21h] BYREF
  unsigned __int64 v24; // [rsp+80h] [rbp-11h]
  __int128 v25; // [rsp+88h] [rbp-9h] BYREF
  __int64 v26; // [rsp+98h] [rbp+7h]

  result = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)this);
  if ( (int)result >= 0 )
  {
    v22 = 0;
    v10 = *(_QWORD *)this;
    v21 = 0;
    result = (*(__int64 (__fastcall **)(WCHAR *, _QWORD, __int64, __int128 *))(v10 + 32))(this, 0, 1, &v21);
    if ( (int)result >= 0 )
    {
      v11 = v22;
      v12 = v22 <= a3;
      *(_OWORD *)a5 = v21;
      v13 = v11;
      if ( !v12 )
        v13 = a3;
      *((_QWORD *)a5 + 2) = v11;
      *((_QWORD *)a5 + 3) = v13;
      *((_QWORD *)a5 + 4) = (v11 - a3) & -(__int64)(a3 < v11);
      v24 = 0;
      v14 = *(_QWORD *)this;
      v23 = 0;
      result = (*(__int64 (__fastcall **)(WCHAR *, _QWORD, __int64, __int128 *))(v14 + 32))(this, 0, 2, &v23);
      if ( (int)result >= 0 )
      {
        v15 = v24;
        v12 = v24 <= a4;
        *(_OWORD *)((char *)a5 + 40) = v23;
        v16 = v15;
        if ( !v12 )
          v16 = a4;
        *((_QWORD *)a5 + 7) = v15;
        *((_QWORD *)a5 + 8) = v16;
        *((_QWORD *)a5 + 9) = (v15 - a4) & -(__int64)(a4 < v15);
        v26 = 0;
        v17 = *(_QWORD *)this;
        v25 = 0;
        result = (*(__int64 (__fastcall **)(WCHAR *, _QWORD, __int64, __int128 *))(v17 + 32))(this, 0, 6, &v25);
        if ( (int)result >= 0 )
        {
          *((_QWORD *)a5 + 11) = *((_QWORD *)&v25 + 1);
          *((_QWORD *)a5 + 12) = v26;
          *((_QWORD *)a5 + 10) = v25;
          TotalNumberOfFreeBytes.QuadPart = 0;
          if ( GetDiskFreeSpaceExW(this + 68, 0, 0, &TotalNumberOfFreeBytes) )
          {
            *((_QWORD *)a5 + 13) = a2 * (TotalNumberOfFreeBytes.QuadPart / a2);
            return 0;
          }
          else
          {
            if ( GetLastError() )
            {
              LastError = GetLastError();
              if ( !LastError )
                INTERNAL_ERROR_ACTION(-1073741595);
            }
            else
            {
              LastError = 14077;
            }
            v19[2] = 2419;
            v19[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v19[1] = "UpdateReserveManager::GetReserveAndUserState";
            v19[3] = "EnsureBOOL(::GetDiskFreeSpaceExW(m_WindowsDirPath, nullptr, nullptr, &FreeUserSpace))";
            if ( (int)LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            RtlReportErrorOrigination(v19, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, LastError);
            return LastError;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016d98  push    rbp
0x180016d9a  push    rbx
0x180016d9b  push    rsi
0x180016d9c  push    rdi
0x180016d9d  push    r14
0x180016d9f  push    r15
0x180016da1  lea     rbp, [rsp-27h]
0x180016da6  sub     rsp, 0B8h
0x180016dad  mov     rax, cs:__security_cookie
0x180016db4  xor     rax, rsp
0x180016db7  mov     [rbp+4Fh+var_40], rax
0x180016dbb  mov     rbx, [rbp+4Fh+arg_20]
0x180016dbf  mov     r14, r9
0x180016dc2  mov     r15, r8
0x180016dc5  mov     rsi, rdx
0x180016dc8  mov     rdi, rcx
0x180016dcb  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x180016dd0  test    eax, eax
0x180016dd2  js      loc_180016F8A
0x180016dd8  xor     eax, eax
0x180016dda  lea     r9, [rbp+4Fh+var_88]
0x180016dde  mov     [rbp+4Fh+var_78], rax
0x180016de2  xor     edx, edx
0x180016de4  mov     rax, [rdi]
0x180016de7  xorps   xmm0, xmm0
0x180016dea  mov     rcx, rdi
0x180016ded  movups  [rbp+4Fh+var_88], xmm0
0x180016df1  lea     r8d, [rdx+1]
0x180016df5  mov     rax, [rax+20h]
0x180016df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dfe  test    eax, eax
0x180016e00  js      loc_180016F8A
0x180016e06  mov     rdx, [rbp+4Fh+var_78]
0x180016e0a  lea     r9, [rbp+4Fh+var_70]
0x180016e0e  mov     rax, qword ptr [rbp+4Fh+var_88+8]
0x180016e12  cmp     rdx, r15
0x180016e15  mov     [rbx+8], rax
0x180016e19  mov     rcx, rdx
0x180016e1c  mov     rax, qword ptr [rbp+4Fh+var_88]
0x180016e20  xorps   xmm0, xmm0
0x180016e23  mov     [rbx], rax
0x180016e26  mov     rax, rdx
0x180016e29  cmova   rax, r15
0x180016e2d  mov     [rbx+10h], rdx
0x180016e31  mov     [rbx+18h], rax
0x180016e35  sub     rcx, r15
0x180016e38  cmp     r15, rdx
0x180016e3b  sbb     rax, rax
0x180016e3e  xor     edx, edx
0x180016e40  and     rax, rcx
0x180016e43  mov     rcx, rdi
0x180016e46  mov     [rbx+20h], rax
0x180016e4a  xor     eax, eax
0x180016e4c  mov     [rbp+4Fh+var_60], rax
0x180016e50  mov     rax, [rdi]
0x180016e53  lea     r8d, [rdx+2]
0x180016e57  movups  [rbp+4Fh+var_70], xmm0
0x180016e5b  mov     rax, [rax+20h]
0x180016e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e64  test    eax, eax
0x180016e66  js      loc_180016F8A
0x180016e6c  mov     rdx, [rbp+4Fh+var_60]
0x180016e70  lea     r9, [rbp+4Fh+var_58]
0x180016e74  mov     rax, qword ptr [rbp+4Fh+var_70+8]
0x180016e78  cmp     rdx, r14
0x180016e7b  mov     [rbx+30h], rax
0x180016e7f  mov     rcx, rdx
0x180016e82  mov     rax, qword ptr [rbp+4Fh+var_70]
0x180016e86  xorps   xmm0, xmm0
0x180016e89  mov     [rbx+28h], rax
0x180016e8d  mov     rax, rdx
0x180016e90  cmova   rax, r14
0x180016e94  mov     [rbx+38h], rdx
0x180016e98  mov     [rbx+40h], rax
0x180016e9c  sub     rcx, r14
0x180016e9f  cmp     r14, rdx
0x180016ea2  sbb     rax, rax
0x180016ea5  xor     edx, edx
0x180016ea7  and     rax, rcx
0x180016eaa  mov     rcx, rdi
0x180016ead  mov     [rbx+48h], rax
0x180016eb1  xor     eax, eax
0x180016eb3  mov     [rbp+4Fh+var_48], rax
0x180016eb7  mov     rax, [rdi]
0x180016eba  lea     r8d, [rdx+6]
0x180016ebe  movups  [rbp+4Fh+var_58], xmm0
0x180016ec2  mov     rax, [rax+20h]
0x180016ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ecb  test    eax, eax
0x180016ecd  js      loc_180016F8A
0x180016ed3  mov     rax, qword ptr [rbp+4Fh+var_58+8]
0x180016ed7  lea     rcx, [rdi+88h]; lpDirectoryName
0x180016ede  mov     [rbx+58h], rax
0x180016ee2  lea     r9, [rbp+4Fh+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x180016ee6  mov     rax, [rbp+4Fh+var_48]
0x180016eea  xor     r8d, r8d; lpTotalNumberOfBytes
0x180016eed  mov     [rbx+60h], rax
0x180016ef1  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180016ef3  mov     rax, qword ptr [rbp+4Fh+var_58]
0x180016ef7  mov     [rbx+50h], rax
0x180016efb  mov     qword ptr [rbp+4Fh+TotalNumberOfFreeBytes], 0
0x180016f03  call    cs:__imp_GetDiskFreeSpaceExW
0x180016f09  test    eax, eax
0x180016f0b  jnz     short loc_180016F77
0x180016f0d  call    cs:__imp_GetLastError
0x180016f13  test    eax, eax
0x180016f15  jnz     short loc_180016F69
0x180016f17  mov     ebx, 36FDh
0x180016f1c  mov     [rbp+4Fh+var_A0], 973h
0x180016f24  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180016f2b  mov     [rbp+4Fh+var_B0], rax
0x180016f2f  lea     rax, aUpdatereservem_3; "UpdateReserveManager::GetReserveAndUser"...
0x180016f36  mov     [rbp+4Fh+var_A8], rax
0x180016f3a  lea     rax, aEnsureboolGetd_1; "EnsureBOOL(::GetDiskFreeSpaceExW(m_Wind"...
0x180016f41  mov     [rbp+4Fh+var_98], rax
0x180016f45  test    ebx, ebx
0x180016f47  jle     short loc_180016F52
0x180016f49  movzx   ebx, bx
0x180016f4c  or      ebx, 80070000h
0x180016f52  mov     r8d, ebx
0x180016f55  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180016f5c  lea     rcx, [rbp+4Fh+var_B0]
0x180016f60  call    RtlReportErrorOrigination
0x180016f65  mov     eax, ebx
0x180016f67  jmp     short loc_180016F8A
0x180016f69  call    cs:__imp_GetLastError
0x180016f6f  mov     ebx, eax
0x180016f71  test    eax, eax
0x180016f73  jz      short loc_180016FA6
0x180016f75  jmp     short loc_180016F1C
0x180016f77  mov     rax, qword ptr [rbp+4Fh+TotalNumberOfFreeBytes]
0x180016f7b  xor     edx, edx
0x180016f7d  div     rsi
0x180016f80  imul    rax, rsi
0x180016f84  mov     [rbx+68h], rax
0x180016f88  xor     eax, eax
0x180016f8a  mov     rcx, [rbp+4Fh+var_40]
0x180016f8e  xor     rcx, rsp; StackCookie
0x180016f91  call    __security_check_cookie
0x180016f96  add     rsp, 0B8h
0x180016f9d  pop     r15
0x180016f9f  pop     r14
0x180016fa1  pop     rdi
0x180016fa2  pop     rsi
0x180016fa3  pop     rbx
0x180016fa4  pop     rbp
0x180016fa5  retn
0x180016fa6  mov     ecx, 0C00000E5h; int
0x180016fab  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
