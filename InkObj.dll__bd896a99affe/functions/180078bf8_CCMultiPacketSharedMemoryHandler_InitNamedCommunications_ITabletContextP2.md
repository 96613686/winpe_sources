# CCMultiPacketSharedMemoryHandler::_InitNamedCommunications(ITabletContextP2 *)

- ea: `0x180078bf8`
- end: `0x180078eca`
- name: `?_InitNamedCommunications@CCMultiPacketSharedMemoryHandler@@AEAAJPEAUITabletContextP2@@@Z`
- size: `722`
- prototype: `__int64 __fastcall(CCMultiPacketSharedMemoryHandler *__hidden this, struct ITabletContextP2 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800789b0`

## callees

- `0x180076e38`
- `0x180078b68`
- `0x180078bf8`
- `0x180079728`
- `0x180079754`
- `0x180079850`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078dac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078e42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078dac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078e42`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180078d98`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180078dd3`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180078e03`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180078d98`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180078dd3`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180078e03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180078c2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180078c2c`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180078e33`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180078e33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078e8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078e9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078e8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078e9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCMultiPacketSharedMemoryHandler::_InitNamedCommunications(
        CCMultiPacketSharedMemoryHandler *this,
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
  UserSid = (*(__int64 (__fastcall **)(struct ITabletContextP2 *, _QWORD, HLOCAL, HLOCAL, int *, unsigned int *, int *, int *))(*(_QWORD *)a2 + 296LL))(
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
  v10 = OpenEventW(0x1F0003u, 0, v27);
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
  v12 = OpenFileMappingW(4u, 0, v28);
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
  UserSid = CCMultiPacketSharedMemoryHandler::_InitCommunicationsCore(this, v13);
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
0x180078bf8  mov     [rsp-8+arg_10], rbx
0x180078bfd  mov     [rsp-8+arg_18], rsi
0x180078c02  push    rbp
0x180078c03  push    rdi
0x180078c04  push    r14
0x180078c06  lea     rbp, [rsp-7C0h]
0x180078c0e  sub     rsp, 8C0h
0x180078c15  mov     rax, cs:__security_cookie
0x180078c1c  xor     rax, rsp
0x180078c1f  mov     [rbp+7D0h+var_20], rax
0x180078c26  mov     r14, rdx
0x180078c29  mov     rdi, rcx
0x180078c2c  call    cs:__imp_GetCurrentProcessId
0x180078c32  mov     esi, eax
0x180078c34  mov     [rsp+8D0h+var_880], 0
0x180078c3c  mov     [rsp+8D0h+var_874], 0
0x180078c44  mov     [rsp+8D0h+var_87C], 0
0x180078c4c  mov     [rsp+8D0h+var_878], 0
0x180078c54  mov     [rsp+8D0h+var_868], 0
0x180078c5d  mov     [rsp+8D0h+hMem], 0
0x180078c66  lea     rcx, [rsp+8D0h+var_868]; StringSid
0x180078c6b  call    ?GetUserSid@@YAJPEAPEAG@Z; GetUserSid(ushort * *)
0x180078c70  mov     ebx, eax
0x180078c72  test    eax, eax
0x180078c74  js      loc_180078E65
0x180078c7a  lea     rcx, [rsp+8D0h+hMem]; StringSid
0x180078c7f  call    ?GetMandatoryLabel@@YAJPEAPEAG@Z; GetMandatoryLabel(ushort * *)
0x180078c84  mov     ebx, eax
0x180078c86  test    eax, eax
0x180078c88  js      loc_180078E65
0x180078c8e  mov     rax, [r14]
0x180078c91  lea     rcx, [rsp+8D0h+var_878]
0x180078c96  mov     [rsp+8D0h+var_898], rcx
0x180078c9b  lea     rcx, [rsp+8D0h+var_87C]
0x180078ca0  mov     [rsp+8D0h+var_8A0], rcx
0x180078ca5  lea     rcx, [rsp+8D0h+var_874]
0x180078caa  mov     [rsp+8D0h+var_8A8], rcx
0x180078caf  lea     rcx, [rsp+8D0h+var_880]
0x180078cb4  mov     [rsp+8D0h+var_8B0], rcx
0x180078cb9  mov     r9, [rsp+8D0h+hMem]
0x180078cbe  mov     r8, [rsp+8D0h+var_868]
0x180078cc3  mov     edx, esi
0x180078cc5  mov     rcx, r14
0x180078cc8  mov     rax, [rax+128h]
0x180078ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078cd4  mov     ebx, eax
0x180078cd6  test    eax, eax
0x180078cd8  js      loc_180078E65
0x180078cde  mov     eax, [rsp+8D0h+var_880]
0x180078ce2  mov     dword ptr [rsp+8D0h+var_8B0], eax
0x180078ce6  mov     r9d, esi
0x180078ce9  lea     r8, aWisptis1DU; "wisptis-1-%d-%u"
0x180078cf0  mov     r14d, 105h
0x180078cf6  mov     edx, r14d; unsigned __int64
0x180078cf9  lea     rcx, [rbp+7D0h+var_650]; unsigned __int16 *
0x180078d00  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078d05  mov     ebx, eax
0x180078d07  test    eax, eax
0x180078d09  js      loc_180078E65
0x180078d0f  mov     eax, [rsp+8D0h+var_87C]
0x180078d13  mov     dword ptr [rsp+8D0h+var_8B0], eax
0x180078d17  mov     r9d, esi
0x180078d1a  lea     r8, aWisptis2DU; "wisptis-2-%d-%u"
0x180078d21  mov     edx, r14d; unsigned __int64
0x180078d24  lea     rcx, [rbp+7D0h+var_440]; unsigned __int16 *
0x180078d2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078d30  mov     ebx, eax
0x180078d32  test    eax, eax
0x180078d34  js      loc_180078E65
0x180078d3a  mov     eax, [rsp+8D0h+var_878]
0x180078d3e  mov     dword ptr [rsp+8D0h+var_8B0], eax
0x180078d42  mov     r9d, esi
0x180078d45  lea     r8, aWisptis3DU; "wisptis-3-%d-%u"
0x180078d4c  mov     edx, r14d; unsigned __int64
0x180078d4f  lea     rcx, [rbp+7D0h+var_230]; unsigned __int16 *
0x180078d56  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078d5b  mov     ebx, eax
0x180078d5d  test    eax, eax
0x180078d5f  js      loc_180078E65
0x180078d65  mov     r9d, [rsp+8D0h+var_874]
0x180078d6a  lea     r8, aWisptis4U; "wisptis-4-%u"
0x180078d71  mov     edx, r14d; unsigned __int64
0x180078d74  lea     rcx, [rsp+8D0h+Name]; unsigned __int16 *
0x180078d79  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078d7e  mov     ebx, eax
0x180078d80  test    eax, eax
0x180078d82  js      loc_180078E65
0x180078d88  lea     r8, [rsp+8D0h+Name]; lpName
0x180078d8d  xor     edx, edx; bInheritHandle
0x180078d8f  mov     r14d, 1F0003h
0x180078d95  mov     ecx, r14d; dwDesiredAccess
0x180078d98  call    cs:__imp_OpenEventW
0x180078d9e  mov     [rdi+18h], rax
0x180078da2  mov     esi, 80070000h
0x180078da7  test    rax, rax
0x180078daa  jnz     short loc_180078DC5
0x180078dac  call    cs:__imp_GetLastError
0x180078db2  mov     ebx, eax
0x180078db4  test    eax, eax
0x180078db6  jle     short loc_180078DBD
0x180078db8  movzx   ebx, ax
0x180078dbb  or      ebx, esi
0x180078dbd  test    ebx, ebx
0x180078dbf  js      loc_180078E65
0x180078dc5  lea     r8, [rbp+7D0h+var_650]; lpName
0x180078dcc  xor     edx, edx; bInheritHandle
0x180078dce  mov     ecx, 100000h; dwDesiredAccess
0x180078dd3  call    cs:__imp_OpenEventW
0x180078dd9  mov     [rdi+8], rax
0x180078ddd  test    rax, rax
0x180078de0  jnz     short loc_180078DF7
0x180078de2  call    cs:__imp_GetLastError
0x180078de8  mov     ebx, eax
0x180078dea  test    eax, eax
0x180078dec  jle     short loc_180078DF3
0x180078dee  movzx   ebx, ax
0x180078df1  or      ebx, esi
0x180078df3  test    ebx, ebx
0x180078df5  js      short loc_180078E65
0x180078df7  lea     r8, [rbp+7D0h+var_440]; lpName
0x180078dfe  xor     edx, edx; bInheritHandle
0x180078e00  mov     ecx, r14d; dwDesiredAccess
0x180078e03  call    cs:__imp_OpenEventW
0x180078e09  mov     [rdi+10h], rax
0x180078e0d  test    rax, rax
0x180078e10  jnz     short loc_180078E27
0x180078e12  call    cs:__imp_GetLastError
0x180078e18  mov     ebx, eax
0x180078e1a  test    eax, eax
0x180078e1c  jle     short loc_180078E23
0x180078e1e  movzx   ebx, ax
0x180078e21  or      ebx, esi
0x180078e23  test    ebx, ebx
0x180078e25  js      short loc_180078E65
0x180078e27  lea     r8, [rbp+7D0h+var_230]; lpName
0x180078e2e  xor     edx, edx; bInheritHandle
0x180078e30  lea     ecx, [rdx+4]; dwDesiredAccess
0x180078e33  call    cs:__imp_OpenFileMappingW
0x180078e39  mov     [rdi+20h], rax
0x180078e3d  test    rax, rax
0x180078e40  jnz     short loc_180078E57
0x180078e42  call    cs:__imp_GetLastError
0x180078e48  mov     ebx, eax
0x180078e4a  test    eax, eax
0x180078e4c  jle     short loc_180078E53
0x180078e4e  movzx   ebx, ax
0x180078e51  or      ebx, esi
0x180078e53  test    ebx, ebx
0x180078e55  js      short loc_180078E65
0x180078e57  mov     rcx, rdi; this
0x180078e5a  call    ?_InitCommunicationsCore@CCMultiPacketSharedMemoryHandler@@AEAAJPEAUITabletContextP2@@@Z; CCMultiPacketSharedMemoryHandler::_InitCommunicationsCore(ITabletContextP2 *)
0x180078e5f  mov     ebx, eax
0x180078e61  test    eax, eax
0x180078e63  jns     short loc_180078E8A
0x180078e65  lea     rcx, [rdi+20h]; void **
0x180078e69  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x180078e6e  lea     rcx, [rdi+10h]; void **
0x180078e72  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x180078e77  lea     rcx, [rdi+8]; void **
0x180078e7b  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x180078e80  lea     rcx, [rdi+18h]; void **
0x180078e84  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x180078e89  nop
0x180078e8a  mov     rcx, [rsp+8D0h+hMem]; hMem
0x180078e8f  call    cs:__imp_LocalFree
0x180078e95  nop
0x180078e96  mov     rcx, [rsp+8D0h+var_868]; hMem
0x180078e9b  call    cs:__imp_LocalFree
0x180078ea1  mov     eax, ebx
0x180078ea3  mov     rcx, [rbp+7D0h+var_20]
0x180078eaa  xor     rcx, rsp; StackCookie
0x180078ead  call    __security_check_cookie
0x180078eb2  lea     r11, [rsp+8D0h+var_10]
0x180078eba  mov     rbx, [r11+30h]
0x180078ebe  mov     rsi, [r11+38h]
0x180078ec2  mov     rsp, r11
0x180078ec5  pop     r14
0x180078ec7  pop     rdi
0x180078ec8  pop     rbp
0x180078ec9  retn
```
