# UtilIsInteractiveDesktop(void)

- ea: `0x14005ae5c`
- end: `0x14005b18f`
- name: `?UtilIsInteractiveDesktop@@YAHXZ`
- size: `819`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14005acd0`

## callees

- `0x140002728`
- `0x14000433c`
- `0x14000e3c4`
- `0x14001444c`
- `0x140014474`
- `0x14005ae5c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005b14d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005b161`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005b14d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005b161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005aeed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005af1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005aff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b06b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b11c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005aeed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005af1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005aff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b06b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b11c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005aea8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005aea8`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005aee3`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005afc9`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005b036`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005b0fa`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005aee3`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005afc9`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005b036`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14005b0fa`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x14005aeb0`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x14005aeb0`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x14005ae9f`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x14005ae9f`

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
  DWORD v15; // eax
  DWORD nLengthNeeded; // [rsp+60h] [rbp+30h] BYREF
  void *v18; // [rsp+68h] [rbp+38h] BYREF

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
  unique_for = (void **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v18, nLengthNeeded + 1);
  v8 = *unique_for;
  *unique_for = 0;
  if ( v18 )
    operator delete(v18, v7);
  if ( v8 )
  {
    if ( GetUserObjectInformationW(ProcessWindowStation, 2, v8, nLengthNeeded, &nLengthNeeded) )
    {
      nLengthNeeded = 0;
      if ( GetUserObjectInformationW(v4, 2, 0, 0, &nLengthNeeded) || GetLastError() == 122 )
      {
        if ( nLengthNeeded )
        {
          v12 = (void **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v18, nLengthNeeded + 1);
          v13 = *v12;
          *v12 = 0;
          if ( v18 )
            operator delete(v18, v9);
          if ( v13 )
          {
            if ( GetUserObjectInformationW(v4, 2, v13, nLengthNeeded, &nLengthNeeded) )
            {
              if ( !(unsigned int)_o__wcsicmp(v8, L"WinSta0") && !(unsigned int)_o__wcsicmp(v13, L"default") )
                v0 = 1;
            }
            else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v15 = GetLastError();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids, v15);
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
0x14005ae5c  mov     [rsp-28h+arg_10], rbx
0x14005ae61  push    rbp
0x14005ae62  push    rsi
0x14005ae63  push    rdi
0x14005ae64  push    r14
0x14005ae66  push    r15
0x14005ae68  mov     rbp, rsp
0x14005ae6b  sub     rsp, 30h
0x14005ae6f  mov     [rbp+nLengthNeeded], 0
0x14005ae76  xor     esi, esi
0x14005ae78  call    IsGetThreadDesktopPresent
0x14005ae7d  test    al, al
0x14005ae7f  jz      loc_14005B17C
0x14005ae85  call    IsGetThreadDesktopPresent
0x14005ae8a  test    al, al
0x14005ae8c  jz      loc_14005B17C
0x14005ae92  call    IsGetThreadDesktopPresent
0x14005ae97  test    al, al
0x14005ae99  jz      loc_14005B17C
0x14005ae9f  call    cs:__imp_GetProcessWindowStation
0x14005aea5  mov     rdi, rax
0x14005aea8  call    cs:__imp_GetCurrentThreadId
0x14005aeae  mov     ecx, eax; dwThreadId
0x14005aeb0  call    cs:__imp_GetThreadDesktop
0x14005aeb6  mov     r15, rax
0x14005aeb9  test    rdi, rdi
0x14005aebc  jz      loc_14005B17C
0x14005aec2  test    rax, rax
0x14005aec5  jz      loc_14005B17C
0x14005aecb  lea     rax, [rbp+nLengthNeeded]
0x14005aecf  mov     [rbp+nLengthNeeded], esi
0x14005aed2  xor     r9d, r9d; nLength
0x14005aed5  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14005aeda  xor     r8d, r8d; pvInfo
0x14005aedd  lea     edx, [rsi+2]; nIndex
0x14005aee0  mov     rcx, rdi; hObj
0x14005aee3  call    cs:__imp_GetUserObjectInformationW
0x14005aee9  test    eax, eax
0x14005aeeb  jnz     short loc_14005AF43
0x14005aeed  call    cs:__imp_GetLastError
0x14005aef3  cmp     eax, 7Ah ; 'z'
0x14005aef6  jz      short loc_14005AF43
0x14005aef8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aeff  lea     rax, WPP_GLOBAL_Control
0x14005af06  cmp     rcx, rax
0x14005af09  jz      loc_14005B17C
0x14005af0f  lea     ebx, [rsi+1]
0x14005af12  test    [rcx+1Ch], bl
0x14005af15  jz      loc_14005B17C
0x14005af1b  call    cs:__imp_GetLastError
0x14005af21  mov     rcx, cs:WPP_GLOBAL_Control
0x14005af28  lea     edx, [rsi+0Ah]
0x14005af2b  mov     r9d, eax
0x14005af2e  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14005af35  mov     rcx, [rcx+10h]
0x14005af39  call    WPP_SF_d
0x14005af3e  jmp     loc_14005B17C
0x14005af43  mov     eax, [rbp+nLengthNeeded]
0x14005af46  mov     ebx, 1
0x14005af4b  inc     eax
0x14005af4d  cmp     eax, ebx
0x14005af4f  jnb     short loc_14005AF89
0x14005af51  mov     rcx, cs:WPP_GLOBAL_Control
0x14005af58  lea     rax, WPP_GLOBAL_Control
0x14005af5f  cmp     rcx, rax
0x14005af62  jz      loc_14005B17C
0x14005af68  test    [rcx+1Ch], bl
0x14005af6b  jz      loc_14005B17C
0x14005af71  mov     rcx, [rcx+10h]
0x14005af75  lea     edx, [rbx+0Ah]
0x14005af78  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14005af7f  call    WPP_SF_
0x14005af84  jmp     loc_14005B17C
0x14005af89  mov     edx, eax
0x14005af8b  lea     rcx, [rbp+arg_8]
0x14005af8f  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x14005af94  mov     r14, [rax]
0x14005af97  mov     [rax], rsi
0x14005af9a  mov     rcx, [rbp+arg_8]; void *
0x14005af9e  test    rcx, rcx
0x14005afa1  jz      short loc_14005AFA8
0x14005afa3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005afa8  test    r14, r14
0x14005afab  jz      loc_14005B17C
0x14005afb1  mov     r9d, [rbp+nLengthNeeded]; nLength
0x14005afb5  lea     rax, [rbp+nLengthNeeded]
0x14005afb9  mov     r8, r14; pvInfo
0x14005afbc  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14005afc1  mov     edx, 2; nIndex
0x14005afc6  mov     rcx, rdi; hObj
0x14005afc9  call    cs:__imp_GetUserObjectInformationW
0x14005afcf  test    eax, eax
0x14005afd1  jnz     short loc_14005B01D
0x14005afd3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005afda  lea     rax, WPP_GLOBAL_Control
0x14005afe1  cmp     rcx, rax
0x14005afe4  jz      loc_14005B174
0x14005afea  test    [rcx+1Ch], bl
0x14005afed  jz      loc_14005B174
0x14005aff3  call    cs:__imp_GetLastError
0x14005aff9  mov     edx, 0Ch
0x14005affe  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b005  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14005b00c  mov     r9d, eax
0x14005b00f  mov     rcx, [rcx+10h]
0x14005b013  call    WPP_SF_d
0x14005b018  jmp     loc_14005B174
0x14005b01d  xor     r9d, r9d; nLength
0x14005b020  mov     [rbp+nLengthNeeded], esi
0x14005b023  lea     rax, [rbp+nLengthNeeded]
0x14005b027  xor     r8d, r8d; pvInfo
0x14005b02a  mov     rcx, r15; hObj
0x14005b02d  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14005b032  lea     edx, [r9+2]; nIndex
0x14005b036  call    cs:__imp_GetUserObjectInformationW
0x14005b03c  test    eax, eax
0x14005b03e  jnz     short loc_14005B078
0x14005b040  call    cs:__imp_GetLastError
0x14005b046  cmp     eax, 7Ah ; 'z'
0x14005b049  jz      short loc_14005B078
0x14005b04b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b052  lea     rax, WPP_GLOBAL_Control
0x14005b059  cmp     rcx, rax
0x14005b05c  jz      loc_14005B174
0x14005b062  test    [rcx+1Ch], bl
0x14005b065  jz      loc_14005B174
0x14005b06b  call    cs:__imp_GetLastError
0x14005b071  mov     edx, 0Dh
0x14005b076  jmp     short loc_14005AFFE
0x14005b078  mov     eax, [rbp+nLengthNeeded]
0x14005b07b  cmp     eax, ebx
0x14005b07d  jnb     short loc_14005B0B9
0x14005b07f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b086  lea     rax, WPP_GLOBAL_Control
0x14005b08d  cmp     rcx, rax
0x14005b090  jz      loc_14005B174
0x14005b096  test    [rcx+1Ch], bl
0x14005b099  jz      loc_14005B174
0x14005b09f  mov     rcx, [rcx+10h]
0x14005b0a3  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14005b0aa  mov     edx, 0Eh
0x14005b0af  call    WPP_SF_
0x14005b0b4  jmp     loc_14005B174
0x14005b0b9  lea     edx, [rax+1]
0x14005b0bc  lea     rcx, [rbp+arg_8]
0x14005b0c0  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x14005b0c5  mov     rdi, [rax]
0x14005b0c8  mov     [rax], rsi
0x14005b0cb  mov     rcx, [rbp+arg_8]; void *
0x14005b0cf  test    rcx, rcx
0x14005b0d2  jz      short loc_14005B0D9
0x14005b0d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005b0d9  test    rdi, rdi
0x14005b0dc  jz      loc_14005B174
0x14005b0e2  mov     r9d, [rbp+nLengthNeeded]; nLength
0x14005b0e6  lea     rax, [rbp+nLengthNeeded]
0x14005b0ea  mov     r8, rdi; pvInfo
0x14005b0ed  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14005b0f2  mov     edx, 2; nIndex
0x14005b0f7  mov     rcx, r15; hObj
0x14005b0fa  call    cs:__imp_GetUserObjectInformationW
0x14005b100  test    eax, eax
0x14005b102  jnz     short loc_14005B143
0x14005b104  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b10b  lea     rax, WPP_GLOBAL_Control
0x14005b112  cmp     rcx, rax
0x14005b115  jz      short loc_14005B16C
0x14005b117  test    [rcx+1Ch], bl
0x14005b11a  jz      short loc_14005B16C
0x14005b11c  call    cs:__imp_GetLastError
0x14005b122  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b129  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14005b130  mov     edx, 0Fh
0x14005b135  mov     r9d, eax
0x14005b138  mov     rcx, [rcx+10h]
0x14005b13c  call    WPP_SF_d
0x14005b141  jmp     short loc_14005B16C
0x14005b143  lea     rdx, aWinsta0; "WinSta0"
0x14005b14a  mov     rcx, r14
0x14005b14d  call    cs:__imp__o__wcsicmp
0x14005b153  test    eax, eax
0x14005b155  jnz     short loc_14005B16C
0x14005b157  lea     rdx, aDefault; "default"
0x14005b15e  mov     rcx, rdi
0x14005b161  call    cs:__imp__o__wcsicmp
0x14005b167  test    eax, eax
0x14005b169  cmovz   esi, ebx
0x14005b16c  mov     rcx, rdi; void *
0x14005b16f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005b174  mov     rcx, r14; void *
0x14005b177  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005b17c  mov     rbx, [rsp+30h+arg_10]
0x14005b181  mov     eax, esi
0x14005b183  add     rsp, 30h
0x14005b187  pop     r15
0x14005b189  pop     r14
0x14005b18b  pop     rdi
0x14005b18c  pop     rsi
0x14005b18d  pop     rbp
0x14005b18e  retn
```
