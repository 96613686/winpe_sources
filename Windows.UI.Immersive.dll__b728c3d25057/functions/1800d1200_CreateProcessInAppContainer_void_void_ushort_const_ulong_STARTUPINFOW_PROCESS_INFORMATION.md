# _CreateProcessInAppContainer(void *,void *,ushort const *,ulong,_STARTUPINFOW *,_PROCESS_INFORMATION *)

- ea: `0x1800d1200`
- end: `0x1800d1389`
- name: `?_CreateProcessInAppContainer@@YAJPEAX0PEBGKPEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `393`
- prototype: `int(void *, void *, const unsigned __int16 *, unsigned int, struct _STARTUPINFOW *, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d1688`

## callees

- `0x180006538`
- `0x18003aa84`
- `0x180051524`
- `0x1800d1200`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800d1242`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800d128b`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800d1242`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800d128b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800d12da`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800d12da`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800d134e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800d134e`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800d1366`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800d1366`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d136f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d136f`

## pseudocode

```c
__int64 __fastcall _CreateProcessInAppContainer(
        void *a1,
        void *a2,
        WCHAR *a3,
        __int64 a4,
        struct _STARTUPINFOW *Size,
        LPPROCESS_INFORMATION a6)
{
  struct _PROCESS_INFORMATION *lpProcessInformation; // rsi
  void *v10; // rcx
  int Error; // ebx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v12; // rdi
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+60h] [rbp-79h] BYREF
  void *Value; // [rsp+68h] [rbp-71h] BYREF
  __int128 v16; // [rsp+70h] [rbp-69h]
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-59h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v18; // [rsp+E8h] [rbp+Fh]

  lpProcessInformation = a6;
  Size = 0;
  *(_OWORD *)&a6->hProcess = 0;
  *(_QWORD *)&lpProcessInformation->dwProcessId = 0;
  InitializeProcThreadAttributeList(0, 1u, 0, (PSIZE_T)&Size);
  Error = ResultFromKnownLastError();
  if ( Error == -2147024774 )
  {
    lpAttributeList = 0;
    Error = CTCoAllocPolicy::Alloc(v10, 1u, (unsigned int)Size, (void **)&lpAttributeList);
    if ( Error >= 0 )
    {
      v12 = lpAttributeList;
      if ( InitializeProcThreadAttributeList(lpAttributeList, 1u, 0, (PSIZE_T)&Size)
        || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        Value = a1;
        v16 = 0;
        if ( UpdateProcThreadAttribute(v12, 0, 0x20009u, &Value, 0x18u, 0, 0)
          || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          *(_QWORD *)&StartupInfo.cb = 112;
          memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
          v18 = v12;
          if ( CreateProcessAsUserW(a2, 0, a3, 0, 0, 0, 0x80004u, 0, 0, &StartupInfo, lpProcessInformation) )
            Error = 0;
          else
            Error = ResultFromKnownLastError();
        }
        DeleteProcThreadAttributeList(v12);
      }
      CoTaskMemFree(v12);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800d1200  push    rbp
0x1800d1202  push    rbx
0x1800d1203  push    rsi
0x1800d1204  push    rdi
0x1800d1205  push    r12
0x1800d1207  push    r14
0x1800d1209  push    r15
0x1800d120b  lea     rbp, [rsp-17h]
0x1800d1210  sub     rsp, 0F0h
0x1800d1217  mov     rsi, [rbp+47h+arg_28]
0x1800d121b  lea     r9, [rbp+47h+Size]; lpSize
0x1800d121f  xor     eax, eax
0x1800d1221  xorps   xmm0, xmm0
0x1800d1224  mov     r15, r8
0x1800d1227  mov     [rbp+47h+Size], rax
0x1800d122b  mov     r12, rdx
0x1800d122e  mov     r14, rcx
0x1800d1231  movups  xmmword ptr [rsi], xmm0
0x1800d1234  lea     edi, [rax+1]
0x1800d1237  mov     [rsi+10h], rax
0x1800d123b  mov     edx, edi; dwAttributeCount
0x1800d123d  xor     r8d, r8d; dwFlags
0x1800d1240  xor     ecx, ecx; lpAttributeList
0x1800d1242  call    cs:__imp_InitializeProcThreadAttributeList
0x1800d1248  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d124d  mov     ebx, eax
0x1800d124f  cmp     eax, 8007007Ah
0x1800d1254  jnz     loc_1800D1375
0x1800d125a  mov     r8d, dword ptr [rbp+47h+Size]; unsigned __int64
0x1800d125e  lea     r9, [rbp+47h+lpAttributeList]; void **
0x1800d1262  mov     edx, edi; unsigned int
0x1800d1264  mov     [rbp+47h+lpAttributeList], 0
0x1800d126c  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800d1271  mov     ebx, eax
0x1800d1273  test    eax, eax
0x1800d1275  js      loc_1800D1375
0x1800d127b  mov     edx, edi; dwAttributeCount
0x1800d127d  lea     r9, [rbp+47h+Size]; lpSize
0x1800d1281  mov     rdi, [rbp+47h+lpAttributeList]
0x1800d1285  xor     r8d, r8d; dwFlags
0x1800d1288  mov     rcx, rdi; lpAttributeList
0x1800d128b  call    cs:__imp_InitializeProcThreadAttributeList
0x1800d1291  test    eax, eax
0x1800d1293  jnz     short loc_1800D12A4
0x1800d1295  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d129a  mov     ebx, eax
0x1800d129c  test    eax, eax
0x1800d129e  js      loc_1800D136C
0x1800d12a4  xorps   xmm0, xmm0
0x1800d12a7  mov     [rsp+120h+lpReturnSize], 0; lpReturnSize
0x1800d12b0  mov     [rsp+120h+lpPreviousValue], 0; lpPreviousValue
0x1800d12b9  lea     r9, [rbp+47h+Value]; lpValue
0x1800d12bd  xor     edx, edx; dwFlags
0x1800d12bf  mov     [rsp+120h+cbSize], 18h; cbSize
0x1800d12c8  mov     r8d, 20009h; Attribute
0x1800d12ce  mov     [rbp+47h+Value], r14
0x1800d12d2  mov     rcx, rdi; lpAttributeList
0x1800d12d5  movdqu  [rbp+47h+var_B0], xmm0
0x1800d12da  call    cs:__imp_UpdateProcThreadAttribute
0x1800d12e0  test    eax, eax
0x1800d12e2  jnz     short loc_1800D12EF
0x1800d12e4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d12e9  mov     ebx, eax
0x1800d12eb  test    eax, eax
0x1800d12ed  js      short loc_1800D1363
0x1800d12ef  xor     edx, edx; Val
0x1800d12f1  mov     qword ptr [rbp+47h+StartupInfo.cb], 70h ; 'p'
0x1800d12f9  lea     rcx, [rbp+47h+StartupInfo.lpReserved]; void *
0x1800d12fd  lea     r8d, [rdx+68h]; Size
0x1800d1301  call    memset_0
0x1800d1306  mov     [rsp+120h+lpProcessInformation], rsi; lpProcessInformation
0x1800d130b  lea     rax, [rbp+47h+StartupInfo]
0x1800d130f  mov     [rsp+120h+lpStartupInfo], rax; lpStartupInfo
0x1800d1314  xor     r9d, r9d; lpProcessAttributes
0x1800d1317  mov     [rsp+120h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800d1320  mov     r8, r15; lpCommandLine
0x1800d1323  mov     [rsp+120h+lpEnvironment], 0; lpEnvironment
0x1800d132c  xor     edx, edx; lpApplicationName
0x1800d132e  mov     dword ptr [rsp+120h+lpReturnSize], 80004h; dwCreationFlags
0x1800d1336  mov     rcx, r12; hToken
0x1800d1339  mov     dword ptr [rsp+120h+lpPreviousValue], 0; bInheritHandles
0x1800d1341  mov     [rsp+120h+cbSize], 0; lpThreadAttributes
0x1800d134a  mov     [rbp+47h+var_38], rdi
0x1800d134e  call    cs:__imp_CreateProcessAsUserW
0x1800d1354  test    eax, eax
0x1800d1356  jz      short loc_1800D135C
0x1800d1358  xor     ebx, ebx
0x1800d135a  jmp     short loc_1800D1363
0x1800d135c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d1361  mov     ebx, eax
0x1800d1363  mov     rcx, rdi; lpAttributeList
0x1800d1366  call    cs:__imp_DeleteProcThreadAttributeList
0x1800d136c  mov     rcx, rdi; pv
0x1800d136f  call    cs:__imp_CoTaskMemFree
0x1800d1375  mov     eax, ebx
0x1800d1377  add     rsp, 0F0h
0x1800d137e  pop     r15
0x1800d1380  pop     r14
0x1800d1382  pop     r12
0x1800d1384  pop     rdi
0x1800d1385  pop     rsi
0x1800d1386  pop     rbx
0x1800d1387  pop     rbp
0x1800d1388  retn
```
