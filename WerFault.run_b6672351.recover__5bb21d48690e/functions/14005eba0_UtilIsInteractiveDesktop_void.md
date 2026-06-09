# UtilIsInteractiveDesktop(void)

- ea: `0x14005eba0`
- end: `0x14005ef31`
- name: `?UtilIsInteractiveDesktop@@YAHXZ`
- size: `913`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14005e9f8`

## callees

- `0x140002748`
- `0x14000438c`
- `0x14000e658`
- `0x140014ee4`
- `0x140014f14`
- `0x14005eba0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005eee2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005eefc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005eee2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005eefc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ec49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ec7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ed61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005edba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005edeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005eeab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ec49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ec7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ed61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005edba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005edeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005eeab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005ebf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005ebf2`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005ec39`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005ed31`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005edaa`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005ee83`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005ec39`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005ed31`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005edaa`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005ee83`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x14005ec00`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x14005ec00`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x14005ebe3`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x14005ebe3`

## pseudocode

```c
__int64 UtilIsInteractiveDesktop(void)
{
  unsigned int v0; // esi
  HWINSTA ProcessWindowStation; // rdi
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  HDESK v4; // r15
  DWORD LastError; // eax
  void **unique_for; // rax
  const struct std::nothrow_t *v7; // rdx
  void *v8; // r14
  const struct std::nothrow_t *v9; // rdx
  DWORD v10; // eax
  __int64 v11; // rdx
  void **v12; // rax
  void *v13; // rdi
  const struct std::nothrow_t *v14; // rdx
  __int64 v15; // r8
  DWORD v16; // eax
  __int64 v17; // r8
  DWORD nLengthNeeded; // [rsp+60h] [rbp+30h] BYREF
  void *v20; // [rsp+68h] [rbp+38h] BYREF

  nLengthNeeded = 0;
  v0 = 0;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    return v0;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    return v0;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    return v0;
  ProcessWindowStation = GetProcessWindowStation();
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  v4 = ThreadDesktop;
  if ( !ProcessWindowStation || !ThreadDesktop )
    return v0;
  nLengthNeeded = 0;
  if ( !GetUserObjectInformationW(ProcessWindowStation, 2, 0, 0, &nLengthNeeded) && GetLastError() != 122 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids, LastError);
    }
    return v0;
  }
  if ( nLengthNeeded == -1 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids);
    }
    return v0;
  }
  unique_for = (void **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v20, nLengthNeeded + 1);
  v8 = *unique_for;
  *unique_for = 0;
  if ( v20 )
    operator delete(v20, v7);
  if ( v8 )
  {
    if ( GetUserObjectInformationW(ProcessWindowStation, 2, v8, nLengthNeeded, &nLengthNeeded) )
    {
      nLengthNeeded = 0;
      if ( GetUserObjectInformationW(v4, 2, 0, 0, &nLengthNeeded) || GetLastError() == 122 )
      {
        if ( nLengthNeeded )
        {
          v12 = (void **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v20, nLengthNeeded + 1);
          v13 = *v12;
          *v12 = 0;
          if ( v20 )
            operator delete(v20, v9);
          if ( v13 )
          {
            if ( GetUserObjectInformationW(v4, 2, v13, nLengthNeeded, &nLengthNeeded) )
            {
              if ( !(unsigned int)_o__wcsicmp(v8, L"WinSta0", v15) && !(unsigned int)_o__wcsicmp(v13, L"default", v17) )
                v0 = 1;
            }
            else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v16 = GetLastError();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids, v16);
            }
            operator delete(v13, v14);
          }
        }
        else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids);
        }
        goto LABEL_43;
      }
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_43:
        operator delete(v8, v9);
        return v0;
      }
      v10 = GetLastError();
      v11 = 13;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_43;
      }
      v10 = GetLastError();
      v11 = 12;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids, v10);
    goto LABEL_43;
  }
  return v0;
}

```

## disassembly

```asm
0x14005eba0  mov     [rsp-28h+arg_10], rbx
0x14005eba5  push    rbp
0x14005eba6  push    rsi
0x14005eba7  push    rdi
0x14005eba8  push    r14
0x14005ebaa  push    r15
0x14005ebac  mov     rbp, rsp
0x14005ebaf  sub     rsp, 30h
0x14005ebb3  mov     [rbp+nLengthNeeded], 0
0x14005ebba  xor     esi, esi
0x14005ebbc  call    IsGetThreadDesktopPresent
0x14005ebc1  test    al, al
0x14005ebc3  jz      loc_14005EF1D
0x14005ebc9  call    IsGetThreadDesktopPresent
0x14005ebce  test    al, al
0x14005ebd0  jz      loc_14005EF1D
0x14005ebd6  call    IsGetThreadDesktopPresent
0x14005ebdb  test    al, al
0x14005ebdd  jz      loc_14005EF1D
0x14005ebe3  call    cs:__imp_GetProcessWindowStation
0x14005ebea  nop     dword ptr [rax+rax+00h]
0x14005ebef  mov     rdi, rax
0x14005ebf2  call    cs:__imp_GetCurrentThreadId
0x14005ebf9  nop     dword ptr [rax+rax+00h]
0x14005ebfe  mov     ecx, eax; dwThreadId
0x14005ec00  call    cs:__imp_GetThreadDesktop
0x14005ec07  nop     dword ptr [rax+rax+00h]
0x14005ec0c  mov     r15, rax
0x14005ec0f  test    rdi, rdi
0x14005ec12  jz      loc_14005EF1D
0x14005ec18  test    rax, rax
0x14005ec1b  jz      loc_14005EF1D
0x14005ec21  lea     rax, [rbp+nLengthNeeded]
0x14005ec25  mov     [rbp+nLengthNeeded], esi
0x14005ec28  xor     r9d, r9d; nLength
0x14005ec2b  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14005ec30  xor     r8d, r8d; pvInfo
0x14005ec33  lea     edx, [rsi+2]; nIndex
0x14005ec36  mov     rcx, rdi; hObj
0x14005ec39  call    cs:__imp_GetUserObjectInformationW
0x14005ec40  nop     dword ptr [rax+rax+00h]
0x14005ec45  test    eax, eax
0x14005ec47  jnz     short loc_14005ECAB
0x14005ec49  call    cs:__imp_GetLastError
0x14005ec50  nop     dword ptr [rax+rax+00h]
0x14005ec55  cmp     eax, 7Ah ; 'z'
0x14005ec58  jz      short loc_14005ECAB
0x14005ec5a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ec61  lea     rax, WPP_GLOBAL_Control
0x14005ec68  cmp     rcx, rax
0x14005ec6b  jz      loc_14005EF1D
0x14005ec71  lea     ebx, [rsi+1]
0x14005ec74  test    [rcx+1Ch], bl
0x14005ec77  jz      loc_14005EF1D
0x14005ec7d  call    cs:__imp_GetLastError
0x14005ec84  nop     dword ptr [rax+rax+00h]
0x14005ec89  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ec90  lea     edx, [rsi+0Ah]
0x14005ec93  mov     r9d, eax
0x14005ec96  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14005ec9d  mov     rcx, [rcx+10h]
0x14005eca1  call    WPP_SF_d
0x14005eca6  jmp     loc_14005EF1D
0x14005ecab  mov     eax, [rbp+nLengthNeeded]
0x14005ecae  mov     ebx, 1
0x14005ecb3  inc     eax
0x14005ecb5  cmp     eax, ebx
0x14005ecb7  jnb     short loc_14005ECF1
0x14005ecb9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ecc0  lea     rax, WPP_GLOBAL_Control
0x14005ecc7  cmp     rcx, rax
0x14005ecca  jz      loc_14005EF1D
0x14005ecd0  test    [rcx+1Ch], bl
0x14005ecd3  jz      loc_14005EF1D
0x14005ecd9  mov     rcx, [rcx+10h]
0x14005ecdd  lea     edx, [rbx+0Ah]
0x14005ece0  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14005ece7  call    WPP_SF_
0x14005ecec  jmp     loc_14005EF1D
0x14005ecf1  mov     edx, eax
0x14005ecf3  lea     rcx, [rbp+arg_8]
0x14005ecf7  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x14005ecfc  mov     r14, [rax]
0x14005ecff  mov     [rax], rsi
0x14005ed02  mov     rcx, [rbp+arg_8]; void *
0x14005ed06  test    rcx, rcx
0x14005ed09  jz      short loc_14005ED10
0x14005ed0b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005ed10  test    r14, r14
0x14005ed13  jz      loc_14005EF1D
0x14005ed19  mov     r9d, [rbp+nLengthNeeded]; nLength
0x14005ed1d  lea     rax, [rbp+nLengthNeeded]
0x14005ed21  mov     r8, r14; pvInfo
0x14005ed24  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14005ed29  mov     edx, 2; nIndex
0x14005ed2e  mov     rcx, rdi; hObj
0x14005ed31  call    cs:__imp_GetUserObjectInformationW
0x14005ed38  nop     dword ptr [rax+rax+00h]
0x14005ed3d  test    eax, eax
0x14005ed3f  jnz     short loc_14005ED91
0x14005ed41  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ed48  lea     rax, WPP_GLOBAL_Control
0x14005ed4f  cmp     rcx, rax
0x14005ed52  jz      loc_14005EF15
0x14005ed58  test    [rcx+1Ch], bl
0x14005ed5b  jz      loc_14005EF15
0x14005ed61  call    cs:__imp_GetLastError
0x14005ed68  nop     dword ptr [rax+rax+00h]
0x14005ed6d  mov     edx, 0Ch
0x14005ed72  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ed79  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14005ed80  mov     r9d, eax
0x14005ed83  mov     rcx, [rcx+10h]
0x14005ed87  call    WPP_SF_d
0x14005ed8c  jmp     loc_14005EF15
0x14005ed91  xor     r9d, r9d; nLength
0x14005ed94  mov     [rbp+nLengthNeeded], esi
0x14005ed97  lea     rax, [rbp+nLengthNeeded]
0x14005ed9b  xor     r8d, r8d; pvInfo
0x14005ed9e  mov     rcx, r15; hObj
0x14005eda1  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14005eda6  lea     edx, [r9+2]; nIndex
0x14005edaa  call    cs:__imp_GetUserObjectInformationW
0x14005edb1  nop     dword ptr [rax+rax+00h]
0x14005edb6  test    eax, eax
0x14005edb8  jnz     short loc_14005EE01
0x14005edba  call    cs:__imp_GetLastError
0x14005edc1  nop     dword ptr [rax+rax+00h]
0x14005edc6  cmp     eax, 7Ah ; 'z'
0x14005edc9  jz      short loc_14005EE01
0x14005edcb  mov     rcx, cs:WPP_GLOBAL_Control
0x14005edd2  lea     rax, WPP_GLOBAL_Control
0x14005edd9  cmp     rcx, rax
0x14005eddc  jz      loc_14005EF15
0x14005ede2  test    [rcx+1Ch], bl
0x14005ede5  jz      loc_14005EF15
0x14005edeb  call    cs:__imp_GetLastError
0x14005edf2  nop     dword ptr [rax+rax+00h]
0x14005edf7  mov     edx, 0Dh
0x14005edfc  jmp     loc_14005ED72
0x14005ee01  mov     eax, [rbp+nLengthNeeded]
0x14005ee04  cmp     eax, ebx
0x14005ee06  jnb     short loc_14005EE42
0x14005ee08  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ee0f  lea     rax, WPP_GLOBAL_Control
0x14005ee16  cmp     rcx, rax
0x14005ee19  jz      loc_14005EF15
0x14005ee1f  test    [rcx+1Ch], bl
0x14005ee22  jz      loc_14005EF15
0x14005ee28  mov     rcx, [rcx+10h]
0x14005ee2c  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14005ee33  mov     edx, 0Eh
0x14005ee38  call    WPP_SF_
0x14005ee3d  jmp     loc_14005EF15
0x14005ee42  lea     edx, [rax+1]
0x14005ee45  lea     rcx, [rbp+arg_8]
0x14005ee49  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x14005ee4e  mov     rdi, [rax]
0x14005ee51  mov     [rax], rsi
0x14005ee54  mov     rcx, [rbp+arg_8]; void *
0x14005ee58  test    rcx, rcx
0x14005ee5b  jz      short loc_14005EE62
0x14005ee5d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005ee62  test    rdi, rdi
0x14005ee65  jz      loc_14005EF15
0x14005ee6b  mov     r9d, [rbp+nLengthNeeded]; nLength
0x14005ee6f  lea     rax, [rbp+nLengthNeeded]
0x14005ee73  mov     r8, rdi; pvInfo
0x14005ee76  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14005ee7b  mov     edx, 2; nIndex
0x14005ee80  mov     rcx, r15; hObj
0x14005ee83  call    cs:__imp_GetUserObjectInformationW
0x14005ee8a  nop     dword ptr [rax+rax+00h]
0x14005ee8f  test    eax, eax
0x14005ee91  jnz     short loc_14005EED8
0x14005ee93  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ee9a  lea     rax, WPP_GLOBAL_Control
0x14005eea1  cmp     rcx, rax
0x14005eea4  jz      short loc_14005EF0D
0x14005eea6  test    [rcx+1Ch], bl
0x14005eea9  jz      short loc_14005EF0D
0x14005eeab  call    cs:__imp_GetLastError
0x14005eeb2  nop     dword ptr [rax+rax+00h]
0x14005eeb7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005eebe  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14005eec5  mov     edx, 0Fh
0x14005eeca  mov     r9d, eax
0x14005eecd  mov     rcx, [rcx+10h]
0x14005eed1  call    WPP_SF_d
0x14005eed6  jmp     short loc_14005EF0D
0x14005eed8  lea     rdx, aWinsta0; "WinSta0"
0x14005eedf  mov     rcx, r14
0x14005eee2  call    cs:__imp__o__wcsicmp
0x14005eee9  nop     dword ptr [rax+rax+00h]
0x14005eeee  test    eax, eax
0x14005eef0  jnz     short loc_14005EF0D
0x14005eef2  lea     rdx, aDefault; "default"
0x14005eef9  mov     rcx, rdi
0x14005eefc  call    cs:__imp__o__wcsicmp
0x14005ef03  nop     dword ptr [rax+rax+00h]
0x14005ef08  test    eax, eax
0x14005ef0a  cmovz   esi, ebx
0x14005ef0d  mov     rcx, rdi; void *
0x14005ef10  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005ef15  mov     rcx, r14; void *
0x14005ef18  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005ef1d  mov     rbx, [rsp+30h+arg_10]
0x14005ef22  mov     eax, esi
0x14005ef24  add     rsp, 30h
0x14005ef28  pop     r15
0x14005ef2a  pop     r14
0x14005ef2c  pop     rdi
0x14005ef2d  pop     rsi
0x14005ef2e  pop     rbp
0x14005ef2f  retn
```
