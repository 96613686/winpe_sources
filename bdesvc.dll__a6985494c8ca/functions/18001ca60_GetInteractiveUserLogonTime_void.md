# GetInteractiveUserLogonTime(void)

- ea: `0x18001ca60`
- end: `0x18001cde2`
- name: `?GetInteractiveUserLogonTime@@YA_JXZ`
- size: `898`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180007d90`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18001ca60`
- `0x1800266bc`
- `0x1800270f4`
- `0x180034070`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001cd26`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001cd26`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001cd42`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001cd42`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001cdca`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001cdca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001caf8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001caf8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001cab6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001cab6`

## pseudocode

```c
__int64 GetInteractiveUserLogonTime(void)
{
  __int64 v0; // rsi
  HRESULT v1; // edi
  HRESULT Instance; // eax
  int v3; // r14d
  PVOID *v4; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned __int64 UserLogonTime; // r13
  _FILETIME v9; // r12
  ULONGLONG TickCount64; // rax
  int v11; // [rsp+30h] [rbp-68h]
  _com_error *v12; // [rsp+40h] [rbp-58h] BYREF
  struct IUnknown *ppv; // [rsp+48h] [rbp-50h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  v0 = -1;
  SystemTimeAsFileTime = 0;
  ppv = 0;
  v1 = CoInitializeEx(0, 0);
  if ( (int)(v1 + 0x80000000) >= 0 && v1 != -2147417850 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        169,
        &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
        (unsigned int)v1);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    v3 = v1;
    if ( v4 == &WPP_GLOBAL_Control || (*((_BYTE *)v4 + 28) & 0x40) == 0 )
      goto LABEL_6;
    v6 = 170;
    v7 = (unsigned int)v1;
LABEL_23:
    WPP_SF_d(v4[2], v6, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v7);
LABEL_45:
    v4 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_6;
  }
  Instance = CoCreateInstance(&stru_180085DF0, 0, 4u, &GUID_8961f0a0_ff62_403b_91b4_7b9280241ceb, (LPVOID *)&ppv);
  v3 = Instance;
  if ( Instance >= 0 )
  {
    if ( ppv )
    {
      try
      {
        UserLogonTime = BdeUISrvLib::IBDEUILauncher::GetUserLogonTime(ppv);
      }
      catch ( _com_error *v12 )
      {
        v11 = *((_DWORD *)v12 + 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            174,
            &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
            *((unsigned int *)v12 + 2));
        v3 = v11;
        v0 = -1;
        goto LABEL_45;
      }
      catch ( ... )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
        v3 = -2147418113;
        v0 = -1;
        goto LABEL_45;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_i(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          176,
          &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
          UserLogonTime);
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v9 = SystemTimeAsFileTime;
      TickCount64 = GetTickCount64();
      if ( *(_QWORD *)&v9 > UserLogonTime && 10000 * TickCount64 > *(_QWORD *)&v9 - UserLogonTime )
        v0 = UserLogonTime + 10000 * TickCount64 - *(_QWORD *)&v9;
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_6;
      WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v0);
      goto LABEL_45;
    }
    v3 = -2147467259;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_8;
    v6 = 173;
    v7 = 2147500037LL;
    goto LABEL_23;
  }
  if ( Instance == -2147467238 )
  {
    v0 = 0;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    v3 = 1;
    goto LABEL_6;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      172,
      &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
      (unsigned int)Instance);
    goto LABEL_45;
  }
LABEL_6:
  if ( ppv )
  {
    ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
    ppv = 0;
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_8:
  if ( v1 >= 0 )
  {
    CoUninitialize();
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 < 0 )
    v0 = -1;
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_(v4[2], 178, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  return v0;
}

```

## disassembly

```asm
0x18001ca60  push    rbx
0x18001ca62  push    rsi
0x18001ca63  push    rdi
0x18001ca64  push    r12
0x18001ca66  push    r13
0x18001ca68  push    r14
0x18001ca6a  push    r15
0x18001ca6c  sub     rsp, 60h
0x18001ca70  mov     rax, cs:__security_cookie
0x18001ca77  xor     rax, rsp
0x18001ca7a  mov     [rsp+98h+var_40], rax
0x18001ca7f  lea     rbx, WPP_GLOBAL_Control
0x18001ca86  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca8d  cmp     rcx, rbx
0x18001ca90  jnz     loc_18001CC36
0x18001ca96  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18001ca9d  mov     rsi, r15
0x18001caa0  mov     qword ptr [rsp+98h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001caa9  mov     [rsp+98h+var_50], 0
0x18001cab2  xor     edx, edx; dwCoInit
0x18001cab4  xor     ecx, ecx; pvReserved
0x18001cab6  call    cs:__imp_CoInitializeEx
0x18001cabd  nop     dword ptr [rax+rax+00h]
0x18001cac2  mov     edi, eax
0x18001cac4  mov     [rsp+98h+var_64], eax
0x18001cac8  mov     eax, 80000000h
0x18001cacd  lea     ecx, [rdi+rax]
0x18001cad0  test    eax, ecx
0x18001cad2  jz      loc_18001CB71
0x18001cad8  lea     rax, [rsp+98h+var_50]
0x18001cadd  mov     [rsp+98h+ppv], rax; ppv
0x18001cae2  lea     r9, _GUID_8961f0a0_ff62_403b_91b4_7b9280241ceb; riid
0x18001cae9  xor     edx, edx; pUnkOuter
0x18001caeb  mov     r8d, 4; dwClsContext
0x18001caf1  lea     rcx, stru_180085DF0; rclsid
0x18001caf8  call    cs:__imp_CoCreateInstance
0x18001caff  nop     dword ptr [rax+rax+00h]
0x18001cb04  mov     r14d, eax
0x18001cb07  test    eax, eax
0x18001cb09  jns     loc_18001CBA5
0x18001cb0f  cmp     eax, 8000401Ah
0x18001cb14  jz      loc_18001CC88
0x18001cb1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb21  cmp     rcx, rbx
0x18001cb24  jnz     loc_18001CCC3
0x18001cb2a  mov     rdx, [rsp+98h+var_50]
0x18001cb2f  test    rdx, rdx
0x18001cb32  jnz     loc_18001CC12
0x18001cb38  test    edi, edi
0x18001cb3a  jns     loc_18001CDCA
0x18001cb40  test    r14d, r14d
0x18001cb43  cmovs   rsi, r15
0x18001cb47  cmp     rcx, rbx
0x18001cb4a  jnz     loc_18001CBEE
0x18001cb50  mov     rax, rsi
0x18001cb53  mov     rcx, [rsp+98h+var_40]
0x18001cb58  xor     rcx, rsp; StackCookie
0x18001cb5b  call    __security_check_cookie
0x18001cb60  add     rsp, 60h
0x18001cb64  pop     r15
0x18001cb66  pop     r14
0x18001cb68  pop     r13
0x18001cb6a  pop     r12
0x18001cb6c  pop     rdi
0x18001cb6d  pop     rsi
0x18001cb6e  pop     rbx
0x18001cb6f  retn
0x18001cb71  cmp     edi, 80010106h
0x18001cb77  jz      loc_18001CAD8
0x18001cb7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb84  cmp     rcx, rbx
0x18001cb87  jnz     loc_18001CC5A
0x18001cb8d  mov     r14d, edi
0x18001cb90  cmp     rcx, rbx
0x18001cb93  jz      short loc_18001CB2A
0x18001cb95  test    byte ptr [rcx+1Ch], 40h
0x18001cb99  jz      short loc_18001CB2A
0x18001cb9b  mov     edx, 0AAh
0x18001cba0  mov     r9d, edi
0x18001cba3  jmp     short loc_18001CBD9
0x18001cba5  cmp     [rsp+98h+var_50], 0
0x18001cbab  jnz     loc_18001CCEA
0x18001cbb1  mov     r14d, 80004005h
0x18001cbb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbbe  cmp     rcx, rbx
0x18001cbc1  jz      loc_18001CB38
0x18001cbc7  test    byte ptr [rcx+1Ch], 40h
0x18001cbcb  jz      loc_18001CB38
0x18001cbd1  mov     edx, 0ADh
0x18001cbd6  mov     r9d, r14d
0x18001cbd9  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001cbe0  mov     rcx, [rcx+10h]
0x18001cbe4  call    WPP_SF_d
0x18001cbe9  jmp     loc_18001CDBE
0x18001cbee  test    byte ptr [rcx+1Ch], 20h
0x18001cbf2  jz      loc_18001CB50
0x18001cbf8  mov     edx, 0B2h
0x18001cbfd  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001cc04  mov     rcx, [rcx+10h]
0x18001cc08  call    WPP_SF_
0x18001cc0d  jmp     loc_18001CB50
0x18001cc12  mov     rax, [rdx]
0x18001cc15  mov     rcx, rdx
0x18001cc18  mov     rax, [rax+10h]
0x18001cc1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc21  mov     [rsp+98h+var_50], 0
0x18001cc2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc31  jmp     loc_18001CB38
0x18001cc36  test    byte ptr [rcx+1Ch], 20h
0x18001cc3a  jz      loc_18001CA96
0x18001cc40  mov     edx, 0A8h
0x18001cc45  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001cc4c  mov     rcx, [rcx+10h]
0x18001cc50  call    WPP_SF_
0x18001cc55  jmp     loc_18001CA96
0x18001cc5a  test    byte ptr [rcx+1Ch], 2
0x18001cc5e  jz      loc_18001CB8D
0x18001cc64  mov     edx, 0A9h
0x18001cc69  mov     r9d, edi
0x18001cc6c  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001cc73  mov     rcx, [rcx+10h]
0x18001cc77  call    WPP_SF_d
0x18001cc7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc83  jmp     loc_18001CB8D
0x18001cc88  xor     esi, esi
0x18001cc8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc91  cmp     rcx, rbx
0x18001cc94  jz      short loc_18001CCB8
0x18001cc96  test    byte ptr [rcx+1Ch], 8
0x18001cc9a  jz      short loc_18001CCB8
0x18001cc9c  mov     edx, 0ABh
0x18001cca1  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001cca8  mov     rcx, [rcx+10h]
0x18001ccac  call    WPP_SF_
0x18001ccb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccb8  mov     r14d, 1
0x18001ccbe  jmp     loc_18001CB2A
0x18001ccc3  test    byte ptr [rcx+1Ch], 2
0x18001ccc7  jz      loc_18001CB2A
0x18001cccd  mov     edx, 0ACh
0x18001ccd2  mov     r9d, eax
0x18001ccd5  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001ccdc  mov     rcx, [rcx+10h]
0x18001cce0  call    WPP_SF_d
0x18001cce5  jmp     loc_18001CDBE
0x18001ccea  mov     rcx, [rsp+98h+var_50]; this
0x18001ccef  call    ?GetUserLogonTime@IBDEUILauncher@BdeUISrvLib@@QEAA_JXZ; BdeUISrvLib::IBDEUILauncher::GetUserLogonTime(void)
0x18001ccf4  mov     r13, rax
0x18001ccf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccfe  cmp     rcx, rbx
0x18001cd01  jz      short loc_18001CD21
0x18001cd03  test    byte ptr [rcx+1Ch], 8
0x18001cd07  jz      short loc_18001CD21
0x18001cd09  mov     edx, 0B0h
0x18001cd0e  mov     r9, r13
0x18001cd11  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001cd18  mov     rcx, [rcx+10h]
0x18001cd1c  call    WPP_SF_i
0x18001cd21  lea     rcx, [rsp+98h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001cd26  call    cs:__imp_GetSystemTimeAsFileTime
0x18001cd2d  nop     dword ptr [rax+rax+00h]
0x18001cd32  mov     r12d, [rsp+98h+SystemTimeAsFileTime.dwHighDateTime]
0x18001cd37  shl     r12, 20h
0x18001cd3b  mov     eax, [rsp+98h+SystemTimeAsFileTime.dwLowDateTime]
0x18001cd3f  or      r12, rax
0x18001cd42  call    cs:__imp_GetTickCount64
0x18001cd49  nop     dword ptr [rax+rax+00h]
0x18001cd4e  cmp     r12, r13
0x18001cd51  jbe     short loc_18001CD6E
0x18001cd53  imul    rcx, rax, 2710h
0x18001cd5a  mov     rax, r12
0x18001cd5d  sub     rax, r13
0x18001cd60  cmp     rcx, rax
0x18001cd63  jbe     short loc_18001CD6E
0x18001cd65  mov     rsi, rcx
0x18001cd68  sub     rsi, r12
0x18001cd6b  add     rsi, r13
0x18001cd6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd75  cmp     rcx, rbx
0x18001cd78  jz      loc_18001CB2A
0x18001cd7e  test    byte ptr [rcx+1Ch], 8
0x18001cd82  jz      loc_18001CB2A
0x18001cd88  mov     edx, 0B1h
0x18001cd8d  mov     r9, rsi
0x18001cd90  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001cd97  mov     rcx, [rcx+10h]
0x18001cd9b  call    WPP_SF_i
0x18001cda0  jmp     short loc_18001CDBE
0x18001cda2  jmp     short $+2
0x18001cda4  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18001cdab  mov     edi, [rsp+98h+var_64]
0x18001cdaf  mov     r14d, [rsp+98h+var_68]
0x18001cdb4  mov     rsi, r15
0x18001cdb7  lea     rbx, WPP_GLOBAL_Control
0x18001cdbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdc5  jmp     loc_18001CB2A
0x18001cdca  call    cs:__imp_CoUninitialize
0x18001cdd1  nop     dword ptr [rax+rax+00h]
0x18001cdd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cddd  jmp     loc_18001CB40
```
