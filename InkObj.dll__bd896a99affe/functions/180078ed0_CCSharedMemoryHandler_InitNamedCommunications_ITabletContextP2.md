# CCSharedMemoryHandler::_InitNamedCommunications(ITabletContextP2 *)

- ea: `0x180078ed0`
- end: `0x1800791a0`
- name: `?_InitNamedCommunications@CCSharedMemoryHandler@@AEAAJPEAUITabletContextP2@@@Z`
- size: `720`
- prototype: `__int64 __fastcall(CCSharedMemoryHandler *__hidden this, struct ITabletContextP2 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180078a30`

## callees

- `0x18002b4f0`
- `0x180076e38`
- `0x180078ed0`
- `0x180079728`
- `0x180079754`
- `0x180079850`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800790b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800790e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800790b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800790e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079118`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18007906c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800790a7`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18007906c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800790a7`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800790d9`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800790d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180078f04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180078f04`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180079109`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180079109`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079165`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079171`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079165`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079171`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCSharedMemoryHandler::_InitNamedCommunications(
        CCSharedMemoryHandler *this,
        struct ITabletContextP2 *a2)
{
  DWORD CurrentProcessId; // esi
  signed int UserSid; // ebx
  HANDLE v6; // rax
  signed int LastError; // eax
  HANDLE v8; // rax
  signed int v9; // eax
  HANDLE v10; // rax
  signed int v11; // eax
  HANDLE v12; // rax
  struct ITabletContextP2 *v13; // rdx
  signed int v14; // eax
  __int64 v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+20h] [rbp-E0h]
  __int64 v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+54h] [rbp-ACh] BYREF
  int v21; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v22; // [rsp+5Ch] [rbp-A4h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v24; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v26[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR v27[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR v28[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  v19 = 0;
  v22 = 0;
  v20 = 0;
  v21 = 0;
  v24 = 0;
  hMem = 0;
  UserSid = GetUserSid((LPWSTR *)&v24);
  if ( UserSid < 0 )
    goto LABEL_25;
  UserSid = GetMandatoryLabel((LPWSTR *)&hMem);
  if ( UserSid < 0 )
    goto LABEL_25;
  UserSid = (*(__int64 (__fastcall **)(struct ITabletContextP2 *, _QWORD, HLOCAL, HLOCAL, int *, unsigned int *, int *, int *))(*(_QWORD *)a2 + 280LL))(
              a2,
              CurrentProcessId,
              v24,
              hMem,
              &v19,
              &v22,
              &v20,
              &v21);
  if ( UserSid < 0 )
    goto LABEL_25;
  LODWORD(v16) = v19;
  UserSid = StringCchPrintfW(v26, 0x105u, L"wisptis-1-%d-%u", CurrentProcessId, v16);
  if ( UserSid < 0 )
    goto LABEL_25;
  LODWORD(v17) = v20;
  UserSid = StringCchPrintfW(v27, 0x105u, L"wisptis-2-%d-%u", CurrentProcessId, v17);
  if ( UserSid < 0 )
    goto LABEL_25;
  LODWORD(v18) = v21;
  UserSid = StringCchPrintfW(v28, 0x105u, L"wisptis-3-%d-%u", CurrentProcessId, v18);
  if ( UserSid < 0 )
    goto LABEL_25;
  UserSid = StringCchPrintfW(Name, 0x105u, L"wisptis-4-%u", v22);
  if ( UserSid < 0 )
    goto LABEL_25;
  v6 = OpenEventW(0x1F0003u, 0, Name);
  *((_QWORD *)this + 3) = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    UserSid = LastError;
    if ( LastError > 0 )
      UserSid = (unsigned __int16)LastError | 0x80070000;
    if ( UserSid < 0 )
      goto LABEL_25;
  }
  v8 = OpenEventW(0x100000u, 0, v26);
  *((_QWORD *)this + 1) = v8;
  if ( !v8 )
  {
    v9 = GetLastError();
    UserSid = v9;
    if ( v9 > 0 )
      UserSid = (unsigned __int16)v9 | 0x80070000;
    if ( UserSid < 0 )
      goto LABEL_25;
  }
  v10 = OpenMutexW(0x1F0001u, 0, v27);
  *((_QWORD *)this + 2) = v10;
  if ( !v10 )
  {
    v11 = GetLastError();
    UserSid = v11;
    if ( v11 > 0 )
      UserSid = (unsigned __int16)v11 | 0x80070000;
    if ( UserSid < 0 )
      goto LABEL_25;
  }
  v12 = OpenFileMappingW(6u, 0, v28);
  *((_QWORD *)this + 4) = v12;
  if ( !v12 )
  {
    v14 = GetLastError();
    UserSid = v14;
    if ( v14 > 0 )
      UserSid = (unsigned __int16)v14 | 0x80070000;
    if ( UserSid < 0 )
      goto LABEL_25;
  }
  UserSid = CCSharedMemoryHandler::_InitCommunicationsCore(this, v13);
  if ( UserSid < 0 )
  {
LABEL_25:
    SafeCloseHandle((void **)this + 4);
    SafeCloseHandle((void **)this + 2);
    SafeCloseHandle((void **)this + 1);
    SafeCloseHandle((void **)this + 3);
  }
  LocalFree(hMem);
  LocalFree(v24);
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x180078ed0  mov     [rsp-8+arg_10], rbx
0x180078ed5  mov     [rsp-8+arg_18], rsi
0x180078eda  push    rbp
0x180078edb  push    rdi
0x180078edc  push    r14
0x180078ede  lea     rbp, [rsp-7C0h]
0x180078ee6  sub     rsp, 8C0h
0x180078eed  mov     rax, cs:__security_cookie
0x180078ef4  xor     rax, rsp
0x180078ef7  mov     [rbp+7D0h+var_20], rax
0x180078efe  mov     r14, rdx
0x180078f01  mov     rdi, rcx
0x180078f04  call    cs:__imp_GetCurrentProcessId
0x180078f0a  mov     esi, eax
0x180078f0c  mov     [rsp+8D0h+var_880], 0
0x180078f14  mov     [rsp+8D0h+var_874], 0
0x180078f1c  mov     [rsp+8D0h+var_87C], 0
0x180078f24  mov     [rsp+8D0h+var_878], 0
0x180078f2c  mov     [rsp+8D0h+var_868], 0
0x180078f35  mov     [rsp+8D0h+hMem], 0
0x180078f3e  lea     rcx, [rsp+8D0h+var_868]; StringSid
0x180078f43  call    ?GetUserSid@@YAJPEAPEAG@Z; GetUserSid(ushort * *)
0x180078f48  mov     ebx, eax
0x180078f4a  test    eax, eax
0x180078f4c  js      loc_18007913B
0x180078f52  lea     rcx, [rsp+8D0h+hMem]; StringSid
0x180078f57  call    ?GetMandatoryLabel@@YAJPEAPEAG@Z; GetMandatoryLabel(ushort * *)
0x180078f5c  mov     ebx, eax
0x180078f5e  test    eax, eax
0x180078f60  js      loc_18007913B
0x180078f66  mov     rax, [r14]
0x180078f69  lea     rcx, [rsp+8D0h+var_878]
0x180078f6e  mov     [rsp+8D0h+var_898], rcx
0x180078f73  lea     rcx, [rsp+8D0h+var_87C]
0x180078f78  mov     [rsp+8D0h+var_8A0], rcx
0x180078f7d  lea     rcx, [rsp+8D0h+var_874]
0x180078f82  mov     [rsp+8D0h+var_8A8], rcx
0x180078f87  lea     rcx, [rsp+8D0h+var_880]
0x180078f8c  mov     [rsp+8D0h+var_8B0], rcx
0x180078f91  mov     r9, [rsp+8D0h+hMem]
0x180078f96  mov     r8, [rsp+8D0h+var_868]
0x180078f9b  mov     edx, esi
0x180078f9d  mov     rcx, r14
0x180078fa0  mov     rax, [rax+118h]
0x180078fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078fac  mov     ebx, eax
0x180078fae  test    eax, eax
0x180078fb0  js      loc_18007913B
0x180078fb6  mov     eax, [rsp+8D0h+var_880]
0x180078fba  mov     dword ptr [rsp+8D0h+var_8B0], eax
0x180078fbe  mov     r9d, esi
0x180078fc1  lea     r8, aWisptis1DU; "wisptis-1-%d-%u"
0x180078fc8  mov     r14d, 105h
0x180078fce  mov     edx, r14d; unsigned __int64
0x180078fd1  lea     rcx, [rbp+7D0h+var_650]; unsigned __int16 *
0x180078fd8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078fdd  mov     ebx, eax
0x180078fdf  test    eax, eax
0x180078fe1  js      loc_18007913B
0x180078fe7  mov     eax, [rsp+8D0h+var_87C]
0x180078feb  mov     dword ptr [rsp+8D0h+var_8B0], eax
0x180078fef  mov     r9d, esi
0x180078ff2  lea     r8, aWisptis2DU; "wisptis-2-%d-%u"
0x180078ff9  mov     edx, r14d; unsigned __int64
0x180078ffc  lea     rcx, [rbp+7D0h+var_440]; unsigned __int16 *
0x180079003  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180079008  mov     ebx, eax
0x18007900a  test    eax, eax
0x18007900c  js      loc_18007913B
0x180079012  mov     eax, [rsp+8D0h+var_878]
0x180079016  mov     dword ptr [rsp+8D0h+var_8B0], eax
0x18007901a  mov     r9d, esi
0x18007901d  lea     r8, aWisptis3DU; "wisptis-3-%d-%u"
0x180079024  mov     edx, r14d; unsigned __int64
0x180079027  lea     rcx, [rbp+7D0h+var_230]; unsigned __int16 *
0x18007902e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180079033  mov     ebx, eax
0x180079035  test    eax, eax
0x180079037  js      loc_18007913B
0x18007903d  mov     r9d, [rsp+8D0h+var_874]
0x180079042  lea     r8, aWisptis4U; "wisptis-4-%u"
0x180079049  mov     edx, r14d; unsigned __int64
0x18007904c  lea     rcx, [rsp+8D0h+Name]; unsigned __int16 *
0x180079051  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180079056  mov     ebx, eax
0x180079058  test    eax, eax
0x18007905a  js      loc_18007913B
0x180079060  lea     r8, [rsp+8D0h+Name]; lpName
0x180079065  xor     edx, edx; bInheritHandle
0x180079067  mov     ecx, 1F0003h; dwDesiredAccess
0x18007906c  call    cs:__imp_OpenEventW
0x180079072  mov     [rdi+18h], rax
0x180079076  mov     esi, 80070000h
0x18007907b  test    rax, rax
0x18007907e  jnz     short loc_180079099
0x180079080  call    cs:__imp_GetLastError
0x180079086  mov     ebx, eax
0x180079088  test    eax, eax
0x18007908a  jle     short loc_180079091
0x18007908c  movzx   ebx, ax
0x18007908f  or      ebx, esi
0x180079091  test    ebx, ebx
0x180079093  js      loc_18007913B
0x180079099  lea     r8, [rbp+7D0h+var_650]; lpName
0x1800790a0  xor     edx, edx; bInheritHandle
0x1800790a2  mov     ecx, 100000h; dwDesiredAccess
0x1800790a7  call    cs:__imp_OpenEventW
0x1800790ad  mov     [rdi+8], rax
0x1800790b1  test    rax, rax
0x1800790b4  jnz     short loc_1800790CB
0x1800790b6  call    cs:__imp_GetLastError
0x1800790bc  mov     ebx, eax
0x1800790be  test    eax, eax
0x1800790c0  jle     short loc_1800790C7
0x1800790c2  movzx   ebx, ax
0x1800790c5  or      ebx, esi
0x1800790c7  test    ebx, ebx
0x1800790c9  js      short loc_18007913B
0x1800790cb  lea     r8, [rbp+7D0h+var_440]; lpName
0x1800790d2  xor     edx, edx; bInheritHandle
0x1800790d4  mov     ecx, 1F0001h; dwDesiredAccess
0x1800790d9  call    cs:__imp_OpenMutexW
0x1800790df  mov     [rdi+10h], rax
0x1800790e3  test    rax, rax
0x1800790e6  jnz     short loc_1800790FD
0x1800790e8  call    cs:__imp_GetLastError
0x1800790ee  mov     ebx, eax
0x1800790f0  test    eax, eax
0x1800790f2  jle     short loc_1800790F9
0x1800790f4  movzx   ebx, ax
0x1800790f7  or      ebx, esi
0x1800790f9  test    ebx, ebx
0x1800790fb  js      short loc_18007913B
0x1800790fd  lea     r8, [rbp+7D0h+var_230]; lpName
0x180079104  xor     edx, edx; bInheritHandle
0x180079106  lea     ecx, [rdx+6]; dwDesiredAccess
0x180079109  call    cs:__imp_OpenFileMappingW
0x18007910f  mov     [rdi+20h], rax
0x180079113  test    rax, rax
0x180079116  jnz     short loc_18007912D
0x180079118  call    cs:__imp_GetLastError
0x18007911e  mov     ebx, eax
0x180079120  test    eax, eax
0x180079122  jle     short loc_180079129
0x180079124  movzx   ebx, ax
0x180079127  or      ebx, esi
0x180079129  test    ebx, ebx
0x18007912b  js      short loc_18007913B
0x18007912d  mov     rcx, rdi; this
0x180079130  call    ?_InitCommunicationsCore@CCSharedMemoryHandler@@AEAAJPEAUITabletContextP2@@@Z; CCSharedMemoryHandler::_InitCommunicationsCore(ITabletContextP2 *)
0x180079135  mov     ebx, eax
0x180079137  test    eax, eax
0x180079139  jns     short loc_180079160
0x18007913b  lea     rcx, [rdi+20h]; void **
0x18007913f  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x180079144  lea     rcx, [rdi+10h]; void **
0x180079148  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18007914d  lea     rcx, [rdi+8]; void **
0x180079151  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x180079156  lea     rcx, [rdi+18h]; void **
0x18007915a  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18007915f  nop
0x180079160  mov     rcx, [rsp+8D0h+hMem]; hMem
0x180079165  call    cs:__imp_LocalFree
0x18007916b  nop
0x18007916c  mov     rcx, [rsp+8D0h+var_868]; hMem
0x180079171  call    cs:__imp_LocalFree
0x180079177  mov     eax, ebx
0x180079179  mov     rcx, [rbp+7D0h+var_20]
0x180079180  xor     rcx, rsp; StackCookie
0x180079183  call    __security_check_cookie
0x180079188  lea     r11, [rsp+8D0h+var_10]
0x180079190  mov     rbx, [r11+30h]
0x180079194  mov     rsi, [r11+38h]
0x180079198  mov     rsp, r11
0x18007919b  pop     r14
0x18007919d  pop     rdi
0x18007919e  pop     rbp
0x18007919f  retn
```
