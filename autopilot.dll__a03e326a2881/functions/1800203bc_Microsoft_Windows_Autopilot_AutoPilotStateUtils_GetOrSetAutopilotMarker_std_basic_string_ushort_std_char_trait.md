# Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800203bc`
- end: `0x180020809`
- name: `?GetOrSetAutopilotMarker@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1101`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019e40`
- `0x18001ada0`

## callees

- `0x1800045b0`
- `0x180005374`
- `0x180009957`
- `0x180009963`
- `0x1800105d4`
- `0x1800105f4`
- `0x1800174f0`
- `0x180018cd0`
- `0x180019230`
- `0x1800203bc`
- `0x180020a84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180020677`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180020677`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18002059c`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800205be`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18002059c`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800205be`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800206ab`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800206ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002052d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020571`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002064d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002052d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020571`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002064d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002053b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002057f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002065b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002053b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002057f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002065b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020477`
- `ntdll!RtlReleasePrivilege` at `0x18002041d`
- `ntdll!RtlReleasePrivilege` at `0x1800207e5`
- `ntdll!RtlReleasePrivilege` at `0x18002041d`
- `ntdll!RtlReleasePrivilege` at `0x1800207e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020714`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800207bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020714`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800207bc`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableW` at `0x180020737`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableW` at `0x180020737`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x180020451`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x180020451`
- `DMCmnUtils!MBToUnicode` at `0x180020509`
- `DMCmnUtils!MBToUnicode` at `0x180020509`
- `DMCmnUtils!UnicodeToMB` at `0x1800206e1`
- `DMCmnUtils!UnicodeToMB` at `0x1800206e1`

## string_xrefs

- `0x180020401`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x1800204b0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18002054a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x1800206f4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x180020745`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker(__int64 a1)
{
  int v2; // eax
  int v3; // ebx
  DWORD FirmwareEnvironmentVariableW; // eax
  signed int LastError; // eax
  __int64 v7; // rdx
  char v8; // si
  void *v9; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v11; // rdx
  void *v12; // rdi
  HANDLE v13; // rax
  __int64 v14; // r8
  unsigned __int64 v15; // rax
  void **v16; // rdi
  __int64 v17; // rbx
  void *v18; // rbx
  HANDLE v19; // rax
  int v20; // eax
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rdx
  void **v24; // rdi
  __int64 v25; // rbx
  LPVOID lpMem; // [rsp+20h] [rbp-E0h] BYREF
  DWORD nSize; // [rsp+28h] [rbp-D8h] BYREF
  PVOID ReturnedState; // [rsp+30h] [rbp-D0h] BYREF
  void *v29[2]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v30; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v31; // [rsp+50h] [rbp-B0h]
  GUID Buf1; // [rsp+58h] [rbp-A8h] BYREF
  char v33; // [rsp+68h] [rbp-98h]
  GUID iid; // [rsp+70h] [rbp-90h] BYREF
  _OWORD pBuffer[3]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[40]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  ReturnedState = 0;
  v2 = ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(&ReturnedState);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F2,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
      (const char *)(unsigned int)v2,
      (int)lpMem);
LABEL_3:
    if ( ReturnedState )
      RtlReleasePrivilege(ReturnedState);
    return (unsigned int)v3;
  }
  memset(pBuffer, 0, 39);
  FirmwareEnvironmentVariableW = GetFirmwareEnvironmentVariableW(
                                   L"AUTOPILOT_MARKER",
                                   L"{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}",
                                   pBuffer,
                                   0x27u);
  *(_OWORD *)v29 = 0;
  v30 = 0;
  v31 = 7;
  LOWORD(v29[0]) = 0;
  if ( !FirmwareEnvironmentVariableW )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError != 203 && LastError != 122 )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 >= 0 )
        goto LABEL_14;
      v7 = 514;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
        (const char *)(unsigned int)v3,
        (int)lpMem);
LABEL_14:
      std::wstring::_Tidy_deallocate(v29);
      goto LABEL_3;
    }
    goto LABEL_35;
  }
  if ( FirmwareEnvironmentVariableW == 39 )
  {
    lpMem = 0;
    nSize = 0;
    *(_QWORD *)&Buf1.Data1 = &lpMem;
    *(_QWORD *)Buf1.Data4 = 0;
    v8 = 1;
    v33 = 1;
    v3 = MBToUnicode((const char *)pBuffer, 0xFDE9u, (unsigned __int16 **)Buf1.Data4, &nSize);
    if ( v33 )
    {
      v9 = **(void ***)&Buf1.Data1;
      **(_QWORD **)&Buf1.Data1 = *(_QWORD *)Buf1.Data4;
      if ( v9 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v9);
      }
    }
    if ( v3 < 0 )
    {
      v11 = 528;
      goto LABEL_21;
    }
    iid = 0;
    if ( IIDFromString((LPCOLESTR)lpMem, &iid) >= 0 )
    {
      Buf1 = 0;
      v3 = IIDFromString(L"{00000000-0000-0000-0000-000000000000}", &Buf1);
      if ( v3 < 0 )
      {
        v11 = 538;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
          (const char *)(unsigned int)v3,
          (int)lpMem);
        v12 = lpMem;
        lpMem = 0;
        if ( v12 )
        {
          v13 = GetProcessHeap();
          HeapFree(v13, 0, v12);
        }
        goto LABEL_14;
      }
      if ( memcmp_0(&Buf1, &iid, 0x10u) )
      {
        v8 = 0;
        v15 = nSize - 1;
        if ( v15 > v31 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            v29,
            v15,
            v14,
            lpMem);
        }
        else
        {
          v16 = v29;
          if ( v31 > 7 )
            v16 = (void **)v29[0];
          v30 = nSize - 1;
          v17 = 2 * v15;
          memmove_0(v16, lpMem, 2 * v15);
          *(_WORD *)((char *)v16 + v17) = 0;
        }
      }
    }
    v18 = lpMem;
    lpMem = 0;
    if ( v18 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v18);
    }
    if ( !v8 )
      goto LABEL_54;
  }
LABEL_35:
  Buf1 = 0;
  v3 = CoCreateGuid(&Buf1);
  if ( v3 < 0 )
  {
    v7 = 553;
    goto LABEL_13;
  }
  memset_0(sz, 0, 0x4Eu);
  if ( !StringFromGUID2(&Buf1, sz, 39) )
  {
    v3 = -2147418113;
    v7 = 555;
    goto LABEL_13;
  }
  nSize = 0;
  lpMem = 0;
  v20 = UnicodeToMB(sz, 0xFDE9u, (char **)&lpMem, &nSize);
  v3 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
      (const char *)(unsigned int)v20,
      (int)lpMem);
    goto LABEL_41;
  }
  if ( !SetFirmwareEnvironmentVariableW(L"AUTOPILOT_MARKER", L"{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}", lpMem, nSize) )
  {
    v3 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x236,
           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
           v22);
LABEL_41:
    if ( lpMem )
      LocalFree(lpMem);
    goto LABEL_14;
  }
  v23 = -1;
  do
    ++v23;
  while ( sz[v23] );
  if ( v23 > v31 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v29, v23, v21, sz);
  }
  else
  {
    v24 = v29;
    if ( v31 > 7 )
      v24 = (void **)v29[0];
    v30 = v23;
    v25 = 2 * v23;
    memmove_0(v24, sz, 2 * v23);
    *(_WORD *)((char *)v24 + v25) = 0;
  }
  if ( lpMem )
    LocalFree(lpMem);
LABEL_54:
  std::wstring::operator=(a1, v29);
  std::wstring::_Tidy_deallocate(v29);
  if ( ReturnedState )
    RtlReleasePrivilege(ReturnedState);
  return 0;
}

```

## disassembly

```asm
0x1800203bc  push    rbp
0x1800203be  push    rbx
0x1800203bf  push    rsi
0x1800203c0  push    rdi
0x1800203c1  push    r14
0x1800203c3  push    r15
0x1800203c5  lea     rbp, [rsp-18h]
0x1800203ca  sub     rsp, 118h
0x1800203d1  mov     rax, cs:__security_cookie
0x1800203d8  xor     rax, rsp
0x1800203db  mov     [rbp+40h+var_40], rax
0x1800203df  mov     r14, rcx
0x1800203e2  xor     r15d, r15d
0x1800203e5  mov     [rsp+140h+ReturnedState], r15
0x1800203ea  lea     rcx, [rsp+140h+ReturnedState]; ReturnedState
0x1800203ef  call    ?Init@AcquireEnvironmentPrivilege@Core@Autopilot@ModernDeployment@@QEAAJXZ; ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(void)
0x1800203f4  mov     ebx, eax
0x1800203f6  test    eax, eax
0x1800203f8  jns     short loc_18002042A
0x1800203fa  mov     rcx, [rbp+48h]; this
0x1800203fe  mov     r9d, eax; char *
0x180020401  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180020408  mov     edx, 1F2h; void *
0x18002040d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020412  nop
0x180020413  mov     rcx, [rsp+140h+ReturnedState]; ReturnedState
0x180020418  test    rcx, rcx
0x18002041b  jz      short loc_180020423
0x18002041d  call    cs:__imp_RtlReleasePrivilege
0x180020423  mov     eax, ebx
0x180020425  jmp     loc_1800207ED
0x18002042a  xorps   xmm0, xmm0
0x18002042d  xor     eax, eax
0x18002042f  movups  [rbp+40h+pBuffer], xmm0
0x180020433  movups  xmmword ptr [rbp+40h+var_B0], xmm0
0x180020437  mov     qword ptr [rbp+40h+var_B0+0Fh], rax
0x18002043b  lea     r9d, [rax+27h]; nSize
0x18002043f  lea     r8, [rbp+40h+pBuffer]; pBuffer
0x180020443  lea     rdx, Guid; "{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}"
0x18002044a  lea     rcx, Name; "AUTOPILOT_MARKER"
0x180020451  call    cs:__imp_GetFirmwareEnvironmentVariableW
0x180020457  xorps   xmm0, xmm0
0x18002045a  movups  xmmword ptr [rsp+140h+var_108], xmm0
0x18002045f  mov     [rsp+140h+var_F8], r15
0x180020464  mov     [rsp+140h+var_F0], 7
0x18002046d  mov     word ptr [rsp+140h+var_108], r15w
0x180020473  test    eax, eax
0x180020475  jnz     short loc_1800204CC
0x180020477  call    cs:__imp_GetLastError
0x18002047d  mov     ebx, eax
0x18002047f  cmp     eax, 0CBh
0x180020484  jz      loc_18002066A
0x18002048a  cmp     eax, 7Ah ; 'z'
0x18002048d  jz      loc_18002066A
0x180020493  test    eax, eax
0x180020495  jle     short loc_1800204A0
0x180020497  movzx   ebx, ax
0x18002049a  or      ebx, 80070000h
0x1800204a0  test    ebx, ebx
0x1800204a2  jns     short loc_1800204BD
0x1800204a4  mov     edx, 202h; void *
0x1800204a9  mov     rcx, [rbp+48h]; this
0x1800204ad  mov     r9d, ebx; char *
0x1800204b0  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800204b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800204bc  nop
0x1800204bd  lea     rcx, [rsp+140h+var_108]
0x1800204c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800204c7  jmp     loc_180020413
0x1800204cc  cmp     eax, 27h ; '''
0x1800204cf  jnz     loc_18002066A
0x1800204d5  mov     [rsp+140h+lpMem], r15; int
0x1800204da  mov     [rsp+140h+nSize], r15d
0x1800204df  lea     rax, [rsp+140h+lpMem]
0x1800204e4  mov     qword ptr [rsp+140h+Buf1.Data1], rax
0x1800204e9  mov     qword ptr [rsp+140h+Buf1.Data4], r15
0x1800204ee  mov     sil, 1
0x1800204f1  mov     [rsp+140h+var_D8], sil
0x1800204f6  lea     r9, [rsp+140h+nSize]
0x1800204fb  lea     r8, [rsp+140h+Buf1.Data4]
0x180020500  mov     edx, 0FDE9h
0x180020505  lea     rcx, [rbp+40h+pBuffer]
0x180020509  call    cs:__imp_?MBToUnicode@@YAJPEBDIPEAPEAGPEAK@Z; MBToUnicode(char const *,uint,ushort * *,ulong *)
0x18002050f  mov     ebx, eax
0x180020511  cmp     [rsp+140h+var_D8], r15b
0x180020516  jz      short loc_180020541
0x180020518  mov     rdx, qword ptr [rsp+140h+Buf1.Data1]
0x18002051d  mov     rdi, [rdx]
0x180020520  mov     rcx, qword ptr [rsp+140h+Buf1.Data4]
0x180020525  mov     [rdx], rcx
0x180020528  test    rdi, rdi
0x18002052b  jz      short loc_180020541
0x18002052d  call    cs:__imp_GetProcessHeap
0x180020533  mov     rcx, rax; hHeap
0x180020536  mov     r8, rdi; lpMem
0x180020539  xor     edx, edx; dwFlags
0x18002053b  call    cs:__imp_HeapFree
0x180020541  test    ebx, ebx
0x180020543  jns     short loc_18002058A
0x180020545  mov     edx, 210h; void *
0x18002054a  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180020551  mov     r9d, ebx; char *
0x180020554  mov     rcx, [rbp+48h]; this
0x180020558  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002055d  nop
0x18002055e  mov     rdi, [rsp+140h+lpMem]
0x180020563  mov     [rsp+140h+lpMem], r15
0x180020568  test    rdi, rdi
0x18002056b  jz      loc_1800204BD
0x180020571  call    cs:__imp_GetProcessHeap
0x180020577  mov     rcx, rax; hHeap
0x18002057a  mov     r8, rdi; lpMem
0x18002057d  xor     edx, edx; dwFlags
0x18002057f  call    cs:__imp_HeapFree
0x180020585  jmp     loc_1800204BD
0x18002058a  xorps   xmm0, xmm0
0x18002058d  movups  xmmword ptr [rsp+140h+iid.Data1], xmm0
0x180020592  lea     rdx, [rsp+140h+iid]; lpiid
0x180020597  mov     rcx, [rsp+140h+lpMem]; lpsz
0x18002059c  call    cs:__imp_IIDFromString
0x1800205a2  test    eax, eax
0x1800205a4  js      loc_18002063E
0x1800205aa  xorps   xmm0, xmm0
0x1800205ad  movups  xmmword ptr [rsp+140h+Buf1.Data1], xmm0
0x1800205b2  lea     rdx, [rsp+140h+Buf1]; lpiid
0x1800205b7  lea     rcx, sz; "{00000000-0000-0000-0000-000000000000}"
0x1800205be  call    cs:__imp_IIDFromString
0x1800205c4  mov     ebx, eax
0x1800205c6  test    eax, eax
0x1800205c8  jns     short loc_1800205D4
0x1800205ca  mov     edx, 21Ah
0x1800205cf  jmp     loc_18002054A
0x1800205d4  mov     r8d, 10h; Size
0x1800205da  lea     rdx, [rsp+140h+iid]; Buf2
0x1800205df  lea     rcx, [rsp+140h+Buf1]; Buf1
0x1800205e4  call    memcmp_0
0x1800205e9  test    eax, eax
0x1800205eb  jz      short loc_18002063E
0x1800205ed  mov     sil, r15b
0x1800205f0  mov     eax, [rsp+140h+nSize]
0x1800205f4  dec     eax
0x1800205f6  mov     edx, eax
0x1800205f8  mov     r9, [rsp+140h+lpMem]
0x1800205fd  cmp     rdx, [rsp+140h+var_F0]
0x180020602  ja      short loc_180020633
0x180020604  lea     rdi, [rsp+140h+var_108]
0x180020609  cmp     [rsp+140h+var_F0], 7
0x18002060f  cmova   rdi, [rsp+140h+var_108]
0x180020615  mov     [rsp+140h+var_F8], rdx
0x18002061a  lea     rbx, [rax+rax]
0x18002061e  mov     r8, rbx; Size
0x180020621  mov     rdx, r9; Src
0x180020624  mov     rcx, rdi; void *
0x180020627  call    memmove_0
0x18002062c  mov     [rbx+rdi], r15w
0x180020631  jmp     short loc_18002063E
0x180020633  lea     rcx, [rsp+140h+var_108]
0x180020638  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002063d  nop
0x18002063e  mov     rbx, [rsp+140h+lpMem]
0x180020643  mov     [rsp+140h+lpMem], r15
0x180020648  test    rbx, rbx
0x18002064b  jz      short loc_180020661
0x18002064d  call    cs:__imp_GetProcessHeap
0x180020653  mov     rcx, rax; hHeap
0x180020656  mov     r8, rbx; lpMem
0x180020659  xor     edx, edx; dwFlags
0x18002065b  call    cs:__imp_HeapFree
0x180020661  test    sil, sil
0x180020664  jz      loc_1800207C2
0x18002066a  xorps   xmm0, xmm0
0x18002066d  movups  xmmword ptr [rsp+140h+Buf1.Data1], xmm0
0x180020672  lea     rcx, [rsp+140h+Buf1]; pguid
0x180020677  call    cs:__imp_CoCreateGuid
0x18002067d  mov     ebx, eax
0x18002067f  test    eax, eax
0x180020681  jns     short loc_18002068D
0x180020683  mov     edx, 229h
0x180020688  jmp     loc_1800204A9
0x18002068d  xor     edx, edx; Val
0x18002068f  lea     r8d, [rdx+4Eh]; Size
0x180020693  lea     rcx, [rbp+40h+sz]; void *
0x180020697  call    memset_0
0x18002069c  mov     r8d, 27h ; '''; cchMax
0x1800206a2  lea     rdx, [rbp+40h+sz]; lpsz
0x1800206a6  lea     rcx, [rsp+140h+Buf1]; rguid
0x1800206ab  call    cs:__imp_StringFromGUID2
0x1800206b1  test    eax, eax
0x1800206b3  jnz     short loc_1800206C4
0x1800206b5  mov     ebx, 8000FFFFh
0x1800206ba  mov     edx, 22Bh
0x1800206bf  jmp     loc_1800204A9
0x1800206c4  mov     [rsp+140h+nSize], r15d
0x1800206c9  mov     [rsp+140h+lpMem], r15; int
0x1800206ce  lea     r9, [rsp+140h+nSize]
0x1800206d3  lea     r8, [rsp+140h+lpMem]
0x1800206d8  mov     edx, 0FDE9h
0x1800206dd  lea     rcx, [rbp+40h+sz]
0x1800206e1  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x1800206e7  mov     ebx, eax
0x1800206e9  test    eax, eax
0x1800206eb  jns     short loc_18002071F
0x1800206ed  mov     rcx, [rbp+48h]; this
0x1800206f1  mov     r9d, eax; char *
0x1800206f4  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800206fb  mov     edx, 22Fh; void *
0x180020700  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020705  nop
0x180020706  mov     rcx, [rsp+140h+lpMem]; hMem
0x18002070b  test    rcx, rcx
0x18002070e  jz      loc_1800204BD
0x180020714  call    cs:__imp_LocalFree
0x18002071a  jmp     loc_1800204BD
0x18002071f  mov     r9d, [rsp+140h+nSize]; nSize
0x180020724  mov     r8, [rsp+140h+lpMem]; pValue
0x180020729  lea     rdx, Guid; "{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}"
0x180020730  lea     rcx, Name; "AUTOPILOT_MARKER"
0x180020737  call    cs:__imp_SetFirmwareEnvironmentVariableW
0x18002073d  test    eax, eax
0x18002073f  jnz     short loc_18002075A
0x180020741  mov     rcx, [rbp+48h]; this
0x180020745  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002074c  mov     edx, 236h; void *
0x180020751  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020756  mov     ebx, eax
0x180020758  jmp     short loc_180020706
0x18002075a  lea     rax, [rbp+40h+sz]
0x18002075e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180020762  inc     rdx
0x180020765  cmp     [rax+rdx*2], r15w
0x18002076a  jnz     short loc_180020762
0x18002076c  cmp     rdx, [rsp+140h+var_F0]
0x180020771  ja      short loc_1800207A3
0x180020773  lea     rdi, [rsp+140h+var_108]
0x180020778  cmp     [rsp+140h+var_F0], 7
0x18002077e  cmova   rdi, [rsp+140h+var_108]
0x180020784  mov     [rsp+140h+var_F8], rdx
0x180020789  lea     rbx, [rdx+rdx]
0x18002078d  mov     r8, rbx; Size
0x180020790  lea     rdx, [rbp+40h+sz]; Src
0x180020794  mov     rcx, rdi; void *
0x180020797  call    memmove_0
0x18002079c  mov     [rbx+rdi], r15w
0x1800207a1  jmp     short loc_1800207B2
0x1800207a3  lea     r9, [rbp+40h+sz]
0x1800207a7  lea     rcx, [rsp+140h+var_108]
0x1800207ac  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800207b1  nop
0x1800207b2  mov     rcx, [rsp+140h+lpMem]; hMem
0x1800207b7  test    rcx, rcx
0x1800207ba  jz      short loc_1800207C2
0x1800207bc  call    cs:__imp_LocalFree
0x1800207c2  lea     rdx, [rsp+140h+var_108]
0x1800207c7  mov     rcx, r14
0x1800207ca  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800207cf  nop
0x1800207d0  lea     rcx, [rsp+140h+var_108]
0x1800207d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800207da  nop
0x1800207db  mov     rcx, [rsp+140h+ReturnedState]; ReturnedState
0x1800207e0  test    rcx, rcx
0x1800207e3  jz      short loc_1800207EB
0x1800207e5  call    cs:__imp_RtlReleasePrivilege
0x1800207eb  xor     eax, eax
0x1800207ed  mov     rcx, [rbp+40h+var_40]
0x1800207f1  xor     rcx, rsp; StackCookie
0x1800207f4  call    __security_check_cookie
0x1800207f9  add     rsp, 118h
0x180020800  pop     r15
0x180020802  pop     r14
0x180020804  pop     rdi
0x180020805  pop     rsi
0x180020806  pop     rbx
0x180020807  pop     rbp
0x180020808  retn
```
