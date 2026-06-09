# Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180020d20`
- end: `0x1800211e0`
- name: `?GetOrSetAutopilotMarker@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1216`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a460`
- `0x18001b430`

## callees

- `0x1800045d0`
- `0x1800053c4`
- `0x1800098e7`
- `0x1800098f3`
- `0x180010744`
- `0x180010764`
- `0x180017a20`
- `0x1800192a4`
- `0x18001982c`
- `0x180020d20`
- `0x180021474`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180021023`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180021023`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180020f30`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180020f58`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180020f30`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180020f58`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002105d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002105d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020ea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020ef9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020fed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020ea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020ef9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020fed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020ebd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020f0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021001`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020ebd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020f0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020de7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020de7`
- `ntdll!RtlReleasePrivilege` at `0x180020d81`
- `ntdll!RtlReleasePrivilege` at `0x1800211b5`
- `ntdll!RtlReleasePrivilege` at `0x180020d81`
- `ntdll!RtlReleasePrivilege` at `0x1800211b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800210d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021186`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800210d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021186`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableW` at `0x1800210fb`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableW` at `0x1800210fb`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x180020dbb`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x180020dbb`
- `DMCmnUtils!MBToUnicode` at `0x180020e7f`
- `DMCmnUtils!MBToUnicode` at `0x180020e7f`
- `DMCmnUtils!UnicodeToMB` at `0x180021099`
- `DMCmnUtils!UnicodeToMB` at `0x180021099`

## string_xrefs

- `0x180020d65`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x180020e26`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x180020ed2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x1800210b2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18002110f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
      std::wstring::_Tidy_deallocate((char **)v29);
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
            (char **)v29,
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
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)v29,
      v23,
      v21,
      sz);
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
  std::wstring::operator=(a1, v29, v14);
  std::wstring::_Tidy_deallocate((char **)v29);
  if ( ReturnedState )
    RtlReleasePrivilege(ReturnedState);
  return 0;
}

```

## disassembly

```asm
0x180020d20  push    rbp
0x180020d22  push    rbx
0x180020d23  push    rsi
0x180020d24  push    rdi
0x180020d25  push    r14
0x180020d27  push    r15
0x180020d29  lea     rbp, [rsp-18h]
0x180020d2e  sub     rsp, 118h
0x180020d35  mov     rax, cs:__security_cookie
0x180020d3c  xor     rax, rsp
0x180020d3f  mov     [rbp+40h+var_40], rax
0x180020d43  mov     r14, rcx
0x180020d46  xor     r15d, r15d
0x180020d49  mov     [rsp+140h+ReturnedState], r15
0x180020d4e  lea     rcx, [rsp+140h+ReturnedState]; ReturnedState
0x180020d53  call    ?Init@AcquireEnvironmentPrivilege@Core@Autopilot@ModernDeployment@@QEAAJXZ; ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(void)
0x180020d58  mov     ebx, eax
0x180020d5a  test    eax, eax
0x180020d5c  jns     short loc_180020D94
0x180020d5e  mov     rcx, [rbp+48h]; this
0x180020d62  mov     r9d, eax; char *
0x180020d65  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180020d6c  mov     edx, 1F2h; void *
0x180020d71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020d76  nop
0x180020d77  mov     rcx, [rsp+140h+ReturnedState]; ReturnedState
0x180020d7c  test    rcx, rcx
0x180020d7f  jz      short loc_180020D8D
0x180020d81  call    cs:__imp_RtlReleasePrivilege
0x180020d88  nop     dword ptr [rax+rax+00h]
0x180020d8d  mov     eax, ebx
0x180020d8f  jmp     loc_1800211C3
0x180020d94  xorps   xmm0, xmm0
0x180020d97  xor     eax, eax
0x180020d99  movups  [rbp+40h+pBuffer], xmm0
0x180020d9d  movups  xmmword ptr [rbp+40h+var_B0], xmm0
0x180020da1  mov     qword ptr [rbp+40h+var_B0+0Fh], rax
0x180020da5  lea     r9d, [rax+27h]; nSize
0x180020da9  lea     r8, [rbp+40h+pBuffer]; pBuffer
0x180020dad  lea     rdx, Guid; "{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}"
0x180020db4  lea     rcx, Name; "AUTOPILOT_MARKER"
0x180020dbb  call    cs:__imp_GetFirmwareEnvironmentVariableW
0x180020dc2  nop     dword ptr [rax+rax+00h]
0x180020dc7  xorps   xmm0, xmm0
0x180020dca  movups  xmmword ptr [rsp+140h+var_108], xmm0
0x180020dcf  mov     [rsp+140h+var_F8], r15
0x180020dd4  mov     [rsp+140h+var_F0], 7
0x180020ddd  mov     word ptr [rsp+140h+var_108], r15w
0x180020de3  test    eax, eax
0x180020de5  jnz     short loc_180020E42
0x180020de7  call    cs:__imp_GetLastError
0x180020dee  nop     dword ptr [rax+rax+00h]
0x180020df3  mov     ebx, eax
0x180020df5  cmp     eax, 0CBh
0x180020dfa  jz      loc_180021016
0x180020e00  cmp     eax, 7Ah ; 'z'
0x180020e03  jz      loc_180021016
0x180020e09  test    eax, eax
0x180020e0b  jle     short loc_180020E16
0x180020e0d  movzx   ebx, ax
0x180020e10  or      ebx, 80070000h
0x180020e16  test    ebx, ebx
0x180020e18  jns     short loc_180020E33
0x180020e1a  mov     edx, 202h; void *
0x180020e1f  mov     rcx, [rbp+48h]; this
0x180020e23  mov     r9d, ebx; char *
0x180020e26  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180020e2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020e32  nop
0x180020e33  lea     rcx, [rsp+140h+var_108]
0x180020e38  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020e3d  jmp     loc_180020D77
0x180020e42  cmp     eax, 27h ; '''
0x180020e45  jnz     loc_180021016
0x180020e4b  mov     [rsp+140h+lpMem], r15; int
0x180020e50  mov     [rsp+140h+nSize], r15d
0x180020e55  lea     rax, [rsp+140h+lpMem]
0x180020e5a  mov     qword ptr [rsp+140h+Buf1.Data1], rax
0x180020e5f  mov     qword ptr [rsp+140h+Buf1.Data4], r15
0x180020e64  mov     sil, 1
0x180020e67  mov     [rsp+140h+var_D8], sil
0x180020e6c  lea     r9, [rsp+140h+nSize]
0x180020e71  lea     r8, [rsp+140h+Buf1.Data4]
0x180020e76  mov     edx, 0FDE9h
0x180020e7b  lea     rcx, [rbp+40h+pBuffer]
0x180020e7f  call    cs:__imp_?MBToUnicode@@YAJPEBDIPEAPEAGPEAK@Z; MBToUnicode(char const *,uint,ushort * *,ulong *)
0x180020e86  nop     dword ptr [rax+rax+00h]
0x180020e8b  mov     ebx, eax
0x180020e8d  cmp     [rsp+140h+var_D8], r15b
0x180020e92  jz      short loc_180020EC9
0x180020e94  mov     rdx, qword ptr [rsp+140h+Buf1.Data1]
0x180020e99  mov     rdi, [rdx]
0x180020e9c  mov     rcx, qword ptr [rsp+140h+Buf1.Data4]
0x180020ea1  mov     [rdx], rcx
0x180020ea4  test    rdi, rdi
0x180020ea7  jz      short loc_180020EC9
0x180020ea9  call    cs:__imp_GetProcessHeap
0x180020eb0  nop     dword ptr [rax+rax+00h]
0x180020eb5  mov     rcx, rax; hHeap
0x180020eb8  mov     r8, rdi; lpMem
0x180020ebb  xor     edx, edx; dwFlags
0x180020ebd  call    cs:__imp_HeapFree
0x180020ec4  nop     dword ptr [rax+rax+00h]
0x180020ec9  test    ebx, ebx
0x180020ecb  jns     short loc_180020F1E
0x180020ecd  mov     edx, 210h; void *
0x180020ed2  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180020ed9  mov     r9d, ebx; char *
0x180020edc  mov     rcx, [rbp+48h]; this
0x180020ee0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ee5  nop
0x180020ee6  mov     rdi, [rsp+140h+lpMem]
0x180020eeb  mov     [rsp+140h+lpMem], r15
0x180020ef0  test    rdi, rdi
0x180020ef3  jz      loc_180020E33
0x180020ef9  call    cs:__imp_GetProcessHeap
0x180020f00  nop     dword ptr [rax+rax+00h]
0x180020f05  mov     rcx, rax; hHeap
0x180020f08  mov     r8, rdi; lpMem
0x180020f0b  xor     edx, edx; dwFlags
0x180020f0d  call    cs:__imp_HeapFree
0x180020f14  nop     dword ptr [rax+rax+00h]
0x180020f19  jmp     loc_180020E33
0x180020f1e  xorps   xmm0, xmm0
0x180020f21  movups  xmmword ptr [rsp+140h+iid.Data1], xmm0
0x180020f26  lea     rdx, [rsp+140h+iid]; lpiid
0x180020f2b  mov     rcx, [rsp+140h+lpMem]; lpsz
0x180020f30  call    cs:__imp_IIDFromString
0x180020f37  nop     dword ptr [rax+rax+00h]
0x180020f3c  test    eax, eax
0x180020f3e  js      loc_180020FDE
0x180020f44  xorps   xmm0, xmm0
0x180020f47  movups  xmmword ptr [rsp+140h+Buf1.Data1], xmm0
0x180020f4c  lea     rdx, [rsp+140h+Buf1]; lpiid
0x180020f51  lea     rcx, sz; "{00000000-0000-0000-0000-000000000000}"
0x180020f58  call    cs:__imp_IIDFromString
0x180020f5f  nop     dword ptr [rax+rax+00h]
0x180020f64  mov     ebx, eax
0x180020f66  test    eax, eax
0x180020f68  jns     short loc_180020F74
0x180020f6a  mov     edx, 21Ah
0x180020f6f  jmp     loc_180020ED2
0x180020f74  mov     r8d, 10h; Size
0x180020f7a  lea     rdx, [rsp+140h+iid]; Buf2
0x180020f7f  lea     rcx, [rsp+140h+Buf1]; Buf1
0x180020f84  call    memcmp_0
0x180020f89  test    eax, eax
0x180020f8b  jz      short loc_180020FDE
0x180020f8d  mov     sil, r15b
0x180020f90  mov     eax, [rsp+140h+nSize]
0x180020f94  dec     eax
0x180020f96  mov     edx, eax
0x180020f98  mov     r9, [rsp+140h+lpMem]
0x180020f9d  cmp     rdx, [rsp+140h+var_F0]
0x180020fa2  ja      short loc_180020FD3
0x180020fa4  lea     rdi, [rsp+140h+var_108]
0x180020fa9  cmp     [rsp+140h+var_F0], 7
0x180020faf  cmova   rdi, [rsp+140h+var_108]
0x180020fb5  mov     [rsp+140h+var_F8], rdx
0x180020fba  lea     rbx, [rax+rax]
0x180020fbe  mov     r8, rbx; Size
0x180020fc1  mov     rdx, r9; Src
0x180020fc4  mov     rcx, rdi; void *
0x180020fc7  call    memmove_0
0x180020fcc  mov     [rbx+rdi], r15w
0x180020fd1  jmp     short loc_180020FDE
0x180020fd3  lea     rcx, [rsp+140h+var_108]
0x180020fd8  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180020fdd  nop
0x180020fde  mov     rbx, [rsp+140h+lpMem]
0x180020fe3  mov     [rsp+140h+lpMem], r15
0x180020fe8  test    rbx, rbx
0x180020feb  jz      short loc_18002100D
0x180020fed  call    cs:__imp_GetProcessHeap
0x180020ff4  nop     dword ptr [rax+rax+00h]
0x180020ff9  mov     rcx, rax; hHeap
0x180020ffc  mov     r8, rbx; lpMem
0x180020fff  xor     edx, edx; dwFlags
0x180021001  call    cs:__imp_HeapFree
0x180021008  nop     dword ptr [rax+rax+00h]
0x18002100d  test    sil, sil
0x180021010  jz      loc_180021192
0x180021016  xorps   xmm0, xmm0
0x180021019  movups  xmmword ptr [rsp+140h+Buf1.Data1], xmm0
0x18002101e  lea     rcx, [rsp+140h+Buf1]; pguid
0x180021023  call    cs:__imp_CoCreateGuid
0x18002102a  nop     dword ptr [rax+rax+00h]
0x18002102f  mov     ebx, eax
0x180021031  test    eax, eax
0x180021033  jns     short loc_18002103F
0x180021035  mov     edx, 229h
0x18002103a  jmp     loc_180020E1F
0x18002103f  xor     edx, edx; Val
0x180021041  lea     r8d, [rdx+4Eh]; Size
0x180021045  lea     rcx, [rbp+40h+sz]; void *
0x180021049  call    memset_0
0x18002104e  mov     r8d, 27h ; '''; cchMax
0x180021054  lea     rdx, [rbp+40h+sz]; lpsz
0x180021058  lea     rcx, [rsp+140h+Buf1]; rguid
0x18002105d  call    cs:__imp_StringFromGUID2
0x180021064  nop     dword ptr [rax+rax+00h]
0x180021069  test    eax, eax
0x18002106b  jnz     short loc_18002107C
0x18002106d  mov     ebx, 8000FFFFh
0x180021072  mov     edx, 22Bh
0x180021077  jmp     loc_180020E1F
0x18002107c  mov     [rsp+140h+nSize], r15d
0x180021081  mov     [rsp+140h+lpMem], r15; int
0x180021086  lea     r9, [rsp+140h+nSize]
0x18002108b  lea     r8, [rsp+140h+lpMem]
0x180021090  mov     edx, 0FDE9h
0x180021095  lea     rcx, [rbp+40h+sz]
0x180021099  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x1800210a0  nop     dword ptr [rax+rax+00h]
0x1800210a5  mov     ebx, eax
0x1800210a7  test    eax, eax
0x1800210a9  jns     short loc_1800210E3
0x1800210ab  mov     rcx, [rbp+48h]; this
0x1800210af  mov     r9d, eax; char *
0x1800210b2  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800210b9  mov     edx, 22Fh; void *
0x1800210be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800210c3  nop
0x1800210c4  mov     rcx, [rsp+140h+lpMem]; hMem
0x1800210c9  test    rcx, rcx
0x1800210cc  jz      loc_180020E33
0x1800210d2  call    cs:__imp_LocalFree
0x1800210d9  nop     dword ptr [rax+rax+00h]
0x1800210de  jmp     loc_180020E33
0x1800210e3  mov     r9d, [rsp+140h+nSize]; nSize
0x1800210e8  mov     r8, [rsp+140h+lpMem]; pValue
0x1800210ed  lea     rdx, Guid; "{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}"
0x1800210f4  lea     rcx, Name; "AUTOPILOT_MARKER"
0x1800210fb  call    cs:__imp_SetFirmwareEnvironmentVariableW
0x180021102  nop     dword ptr [rax+rax+00h]
0x180021107  test    eax, eax
0x180021109  jnz     short loc_180021124
0x18002110b  mov     rcx, [rbp+48h]; this
0x18002110f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180021116  mov     edx, 236h; void *
0x18002111b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021120  mov     ebx, eax
0x180021122  jmp     short loc_1800210C4
0x180021124  lea     rax, [rbp+40h+sz]
0x180021128  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002112c  inc     rdx
0x18002112f  cmp     [rax+rdx*2], r15w
0x180021134  jnz     short loc_18002112C
0x180021136  cmp     rdx, [rsp+140h+var_F0]
0x18002113b  ja      short loc_18002116D
0x18002113d  lea     rdi, [rsp+140h+var_108]
0x180021142  cmp     [rsp+140h+var_F0], 7
0x180021148  cmova   rdi, [rsp+140h+var_108]
0x18002114e  mov     [rsp+140h+var_F8], rdx
0x180021153  lea     rbx, [rdx+rdx]
0x180021157  mov     r8, rbx; Size
0x18002115a  lea     rdx, [rbp+40h+sz]; Src
0x18002115e  mov     rcx, rdi; void *
0x180021161  call    memmove_0
0x180021166  mov     [rbx+rdi], r15w
0x18002116b  jmp     short loc_18002117C
0x18002116d  lea     r9, [rbp+40h+sz]
0x180021171  lea     rcx, [rsp+140h+var_108]
0x180021176  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002117b  nop
0x18002117c  mov     rcx, [rsp+140h+lpMem]; hMem
0x180021181  test    rcx, rcx
0x180021184  jz      short loc_180021192
0x180021186  call    cs:__imp_LocalFree
0x18002118d  nop     dword ptr [rax+rax+00h]
0x180021192  lea     rdx, [rsp+140h+var_108]
0x180021197  mov     rcx, r14
0x18002119a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002119f  nop
0x1800211a0  lea     rcx, [rsp+140h+var_108]
0x1800211a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800211aa  nop
0x1800211ab  mov     rcx, [rsp+140h+ReturnedState]; ReturnedState
0x1800211b0  test    rcx, rcx
0x1800211b3  jz      short loc_1800211C1
0x1800211b5  call    cs:__imp_RtlReleasePrivilege
0x1800211bc  nop     dword ptr [rax+rax+00h]
0x1800211c1  xor     eax, eax
0x1800211c3  mov     rcx, [rbp+40h+var_40]
0x1800211c7  xor     rcx, rsp; StackCookie
0x1800211ca  call    __security_check_cookie
0x1800211cf  add     rsp, 118h
0x1800211d6  pop     r15
0x1800211d8  pop     r14
0x1800211da  pop     rdi
0x1800211db  pop     rsi
0x1800211dc  pop     rbx
0x1800211dd  pop     rbp
0x1800211de  retn
```
