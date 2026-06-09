# CheckDriverStatus(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,int *,_FileAttributesStrs const &)

- ea: `0x180012638`
- end: `0x180012b8a`
- name: `?CheckDriverStatus@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAHAEBU_FileAttributesStrs@@@Z`
- size: `1362`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x180014580`

## callees

- `0x180001cf0`
- `0x1800020c0`
- `0x180002120`
- `0x180002bb8`
- `0x18000b720`
- `0x18000e428`
- `0x1800119f0`
- `0x180011d40`
- `0x180012638`
- `0x180015938`
- `0x1800543c0`
- `0x18006a010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180012b00`
- `KERNEL32!FreeLibrary` at `0x180012b00`
- `KERNEL32!LoadLibraryExW` at `0x180012724`
- `KERNEL32!LoadLibraryExW` at `0x180012724`
- `KERNEL32!GetProcAddress` at `0x180012772`
- `KERNEL32!GetProcAddress` at `0x180012772`
- `KERNEL32!GetLastError` at `0x180012734`
- `KERNEL32!GetLastError` at `0x18001277d`
- `KERNEL32!GetLastError` at `0x18001293d`
- `KERNEL32!GetLastError` at `0x180012983`
- `KERNEL32!GetLastError` at `0x1800129f1`
- `KERNEL32!GetLastError` at `0x180012a60`
- `KERNEL32!GetLastError` at `0x180012a6e`
- `KERNEL32!GetLastError` at `0x180012ab4`
- `KERNEL32!GetLastError` at `0x180012734`
- `KERNEL32!GetLastError` at `0x18001277d`
- `KERNEL32!GetLastError` at `0x18001293d`
- `KERNEL32!GetLastError` at `0x180012983`
- `KERNEL32!GetLastError` at `0x1800129f1`
- `KERNEL32!GetLastError` at `0x180012a60`
- `KERNEL32!GetLastError` at `0x180012a6e`
- `KERNEL32!GetLastError` at `0x180012ab4`
- `ADVAPI32!OpenSCManagerW` at `0x18001292c`
- `ADVAPI32!OpenSCManagerW` at `0x18001292c`
- `ADVAPI32!OpenServiceW` at `0x180012972`
- `ADVAPI32!OpenServiceW` at `0x180012972`
- `ADVAPI32!QueryServiceStatusEx` at `0x1800129e4`
- `ADVAPI32!QueryServiceStatusEx` at `0x1800129e4`
- `ADVAPI32!QueryServiceConfigW` at `0x180012a56`
- `ADVAPI32!QueryServiceConfigW` at `0x180012aa7`
- `ADVAPI32!QueryServiceConfigW` at `0x180012a56`
- `ADVAPI32!QueryServiceConfigW` at `0x180012aa7`
- `ADVAPI32!CloseServiceHandle` at `0x180012b0e`
- `ADVAPI32!CloseServiceHandle` at `0x180012b1c`
- `ADVAPI32!CloseServiceHandle` at `0x180012b0e`
- `ADVAPI32!CloseServiceHandle` at `0x180012b1c`
- `SHLWAPI!StrToIntExW` at `0x18001283b`
- `SHLWAPI!StrToIntExW` at `0x18001283b`

## string_xrefs

- `0x18001271d`: `devinv.dll`
- `0x18001273e`: `devinv.dll could not be loaded, %d`
- `0x180012943`: `OpenSCManager failed, %d`
- `0x1800129a3`: `OpenService failed for %ws, %d`
- `0x1800129f7`: `QueryServiceStatusEx failed, %d`
- `0x180012a74`: `QueryServiceConfig failed, %d`
- `0x180012aba`: `QueryServiceConfig failed, %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall CheckDriverStatus(__int64 a1, _QWORD *a2, _DWORD *a3, __int64 a4)
{
  _QWORD *v5; // r14
  _QWORD *v7; // rax
  HMODULE Library; // rax
  SC_HANDLE v9; // rsi
  SC_HANDLE v10; // r12
  struct _QUERY_SERVICE_CONFIGW *v11; // r13
  FARPROC ProcAddress; // rax
  signed int v13; // eax
  const char *v14; // r9
  __int64 v15; // r8
  _QWORD *v16; // rbx
  const WCHAR **v17; // rsi
  const WCHAR *v18; // rcx
  __int64 **v19; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  __int64 v22; // rbx
  SC_HANDLE v23; // rax
  const WCHAR *v24; // rdx
  DWORD LastError; // eax
  LPCWSTR *v26; // rcx
  LPDWORD pcbBytesNeeded; // [rsp+28h] [rbp-E0h]
  DWORD pcbBytesNeededa; // [rsp+28h] [rbp-E0h]
  __int64 cbBufSize; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C8h]
  HMODULE v32; // [rsp+48h] [rbp-C0h]
  __int64 v33; // [rsp+58h] [rbp-B0h]
  __int64 lpServiceName; // [rsp+60h] [rbp-A8h]
  LPCWSTR lpServiceName_8[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+78h] [rbp-90h]
  unsigned __int64 v37; // [rsp+80h] [rbp-88h]
  void **v38; // [rsp+88h] [rbp-80h] BYREF
  int v39; // [rsp+90h] [rbp-78h]
  _BYTE v40[32]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v41; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v42; // [rsp+C8h] [rbp-40h]
  __int64 v43; // [rsp+D0h] [rbp-38h]
  _QWORD *v44; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v45; // [rsp+E0h] [rbp-28h]
  _QWORD v46[2]; // [rsp+E8h] [rbp-20h] BYREF
  int v47; // [rsp+F8h] [rbp-10h]
  __int64 v48; // [rsp+FCh] [rbp-Ch]
  int v49; // [rsp+104h] [rbp-4h]
  BYTE Buffer[16]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v51; // [rsp+118h] [rbp+10h]
  int v52; // [rsp+128h] [rbp+20h]

  lpServiceName = -2;
  v33 = a4;
  v5 = a2;
  *(_OWORD *)Buffer = 0;
  v51 = 0;
  v52 = 0;
  cbBufSize = 0;
  *(_OWORD *)lpServiceName_8 = 0;
  v36 = 0;
  v37 = 7;
  LOWORD(lpServiceName_8[0]) = 0;
  v38 = &DriverBinaryInventoryReader::`vftable';
  v39 = 0;
  std::wstring::wstring(v40, a2);
  v41 = 0;
  v42 = 0;
  v43 = 7;
  LOWORD(v41) = 0;
  v44 = 0;
  v45 = 0;
  v7 = operator new(0x60u);
  *v7 = v7;
  v7[1] = v7;
  v7[2] = v7;
  *((_WORD *)v7 + 12) = 257;
  v44 = v7;
  v46[1] = 0;
  v48 = 0;
  v49 = 0;
  v46[0] = 32;
  v47 = 3;
  *a3 = 0;
  Library = LoadLibraryExW(L"devinv.dll", 0, 0);
  v32 = Library;
  if ( !Library )
  {
    pcbBytesNeededa = GetLastError();
    AslLogCallPrintf(1, "CheckDriverStatus", 2233, "devinv.dll could not be loaded, %d", pcbBytesNeededa);
    goto LABEL_65;
  }
  v9 = 0;
  v10 = 0;
  v11 = 0;
  ProcAddress = GetProcAddress(Library, "GetDevInventory");
  if ( ProcAddress )
  {
    v13 = ((__int64 (__fastcall *)(void ***, _QWORD *, _QWORD))ProcAddress)(&v38, v46, 0);
    if ( v13 >= 0 )
    {
      if ( !v45 )
      {
        if ( v5[3] > 7u )
          v5 = (_QWORD *)*v5;
        AslLogCallPrintf(3, "CheckDriverStatus", 2258, "Have not found the driver name in the inventory, %ws", v5);
        goto LABEL_59;
      }
      LODWORD(v31) = GetPeChecksum(a1);
      v16 = (_QWORD *)*v44;
      while ( v16 != v44 )
      {
        v17 = (const WCHAR **)(v16 + 8);
        if ( v16[11] <= 7u )
          v18 = (const WCHAR *)(v16 + 8);
        else
          v18 = *v17;
        if ( StrToIntExW(v18, 0, (int *)&cbBufSize + 1) )
        {
          if ( (_DWORD)v31 == HIDWORD(cbBufSize) )
          {
            std::wstring::operator=(lpServiceName_8, v16 + 4);
            break;
          }
        }
        else
        {
          if ( v16[11] > 7u )
            v17 = (const WCHAR **)*v17;
          AslLogCallPrintf(3, "CheckDriverStatus", 2272, "StrToIntEx failed, %ws", v17);
        }
        v19 = (__int64 **)v16[2];
        if ( *((_BYTE *)v19 + 25) )
        {
          for ( i = v16[1]; !*(_BYTE *)(i + 25) && v16 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
            v16 = (_QWORD *)i;
          v16 = (_QWORD *)i;
        }
        else
        {
          v16 = (_QWORD *)v16[2];
          for ( j = *v19; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v16 = j;
        }
      }
      if ( !v36 )
      {
        if ( v5[3] > 7u )
          v5 = (_QWORD *)*v5;
        AslLogCallPrintf(
          3,
          "CheckDriverStatus",
          2285,
          "Have not found a driver matching both name and checksum in the inventory, %ws",
          v5);
        v9 = 0;
        goto LABEL_59;
      }
      v22 = v33;
      if ( *(_QWORD *)(v33 + 472) )
        *a3 = 1;
      v23 = OpenSCManagerW(0, 0, 1u);
      v9 = v23;
      if ( v23 )
      {
        v24 = (const WCHAR *)lpServiceName_8;
        if ( v37 > 7 )
          v24 = lpServiceName_8[0];
        v10 = OpenServiceW(v23, v24, 5u);
        if ( !v10 )
        {
          *a3 = 0;
          LastError = GetLastError();
          v26 = lpServiceName_8;
          if ( v37 > 7 )
            v26 = (LPCWSTR *)lpServiceName_8[0];
          AslLogCallPrintf(1, "CheckDriverStatus", 2308, "OpenService failed for %ws, %d", v26, LastError, cbBufSize);
          goto LABEL_59;
        }
        if ( *(_QWORD *)(v22 + 504) )
        {
          if ( !QueryServiceStatusEx(v10, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, (LPDWORD)&cbBufSize) )
          {
            *a3 = 0;
            v13 = GetLastError();
            v14 = "QueryServiceStatusEx failed, %d";
            v15 = 2321;
            goto LABEL_5;
          }
          AslLogCallPrintf(3, "CheckDriverStatus", 2325, "Driver current state: %d", *(_DWORD *)&Buffer[4]);
          if ( *(_DWORD *)&Buffer[4] == 1 )
          {
            *a3 = 0;
            goto LABEL_59;
          }
          *a3 = 1;
        }
        if ( !*(_QWORD *)(v22 + 536) )
          goto LABEL_59;
        LODWORD(cbBufSize) = 0;
        if ( QueryServiceConfigW(v10, 0, 0, (LPDWORD)&cbBufSize) || GetLastError() == 122 )
        {
          v11 = (struct _QUERY_SERVICE_CONFIGW *)operator new[]((unsigned int)cbBufSize);
          if ( QueryServiceConfigW(v10, v11, cbBufSize, (LPDWORD)&cbBufSize) )
          {
            AslLogCallPrintf(3, "CheckDriverStatus", 2364, "Driver start mode: %d", v11->dwStartType);
            *a3 = v11->dwStartType != 4;
            goto LABEL_59;
          }
          *a3 = 0;
          v13 = GetLastError();
          v14 = "QueryServiceConfig failed, %d";
          v15 = 2360;
        }
        else
        {
          *a3 = 0;
          v13 = GetLastError();
          v14 = "QueryServiceConfig failed, %d";
          v15 = 2345;
        }
      }
      else
      {
        *a3 = 0;
        v13 = GetLastError();
        v14 = "OpenSCManager failed, %d";
        v15 = 2298;
      }
    }
    else
    {
      v14 = "GetDevInventory failed, %x";
      v15 = 2250;
    }
  }
  else
  {
    v13 = GetLastError();
    v14 = "GetProcAddress GetDevInventory failed %d";
    v15 = 2242;
  }
LABEL_5:
  LODWORD(pcbBytesNeeded) = v13;
  AslLogCallPrintf(1, "CheckDriverStatus", v15, v14, pcbBytesNeeded);
LABEL_59:
  FreeLibrary(v32);
  if ( v9 )
    CloseServiceHandle(v9);
  if ( v10 )
    CloseServiceHandle(v10);
  if ( v11 )
    operator delete(v11);
LABEL_65:
  v38 = &DriverBinaryInventoryReader::`vftable';
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v44);
  std::wstring::~wstring(&v41);
  std::wstring::~wstring(v40);
  std::wstring::~wstring(lpServiceName_8);
  return 1;
}

```

## disassembly

```asm
0x180012638  mov     rax, rsp
0x18001263b  push    rbp
0x18001263c  push    rsi
0x18001263d  push    rdi
0x18001263e  push    r12
0x180012640  push    r13
0x180012642  push    r14
0x180012644  push    r15
0x180012646  lea     rbp, [rax-68h]
0x18001264a  sub     rsp, 130h
0x180012651  mov     [rsp+160h+lpServiceName], 0FFFFFFFFFFFFFFFEh
0x18001265a  mov     [rax+20h], rbx
0x18001265e  mov     rax, cs:__security_cookie
0x180012665  xor     rax, rsp
0x180012668  mov     [rbp+60h+var_38], rax
0x18001266c  mov     [rsp+160h+var_110], r9
0x180012671  mov     r15, r8
0x180012674  mov     r14, rdx
0x180012677  mov     rbx, rcx
0x18001267a  xorps   xmm0, xmm0
0x18001267d  xor     eax, eax
0x18001267f  movups  xmmword ptr [rbp+60h+Buffer], xmm0
0x180012683  movups  [rbp+60h+var_50], xmm0
0x180012687  mov     [rbp+60h+var_40], eax
0x18001268a  xor     edi, edi
0x18001268c  mov     [rsp+160h+cbBufSize], edi
0x180012690  mov     [rsp+160h+piRet], edi
0x180012694  movups  xmmword ptr [rsp+160h+lpServiceName+8], xmm0
0x180012699  mov     [rsp+160h+var_F0], rdi
0x18001269e  lea     esi, [rax+7]
0x1800126a1  mov     [rsp+160h+var_E8], rsi
0x1800126a6  mov     word ptr [rsp+160h+lpServiceName+8], di
0x1800126ab  lea     rax, ??_7DriverBinaryInventoryReader@@6B@; const DriverBinaryInventoryReader::`vftable'
0x1800126b2  mov     [rbp+60h+var_E0], rax
0x1800126b6  mov     [rbp+60h+var_D8], edi
0x1800126b9  lea     rcx, [rbp+60h+var_D0]
0x1800126bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800126c2  nop
0x1800126c3  xorps   xmm0, xmm0
0x1800126c6  movups  [rbp+60h+var_B0], xmm0
0x1800126ca  mov     [rbp+60h+var_A0], rdi
0x1800126ce  mov     [rbp+60h+var_98], rsi
0x1800126d2  mov     word ptr [rbp+60h+var_B0], di
0x1800126d6  mov     [rbp+60h+var_90], rdi
0x1800126da  mov     [rbp+60h+var_88], rdi
0x1800126de  lea     ecx, [rdi+60h]; Size
0x1800126e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800126e6  mov     [rax], rax
0x1800126e9  mov     [rax+8], rax
0x1800126ed  mov     [rax+10h], rax
0x1800126f1  mov     word ptr [rax+18h], 101h
0x1800126f7  mov     [rbp+60h+var_90], rax
0x1800126fb  mov     [rbp+60h+var_78], rdi
0x1800126ff  mov     [rbp+60h+var_6C], rdi
0x180012703  mov     [rbp+60h+var_64], edi
0x180012706  mov     [rbp+60h+var_80], 20h ; ' '
0x18001270e  mov     [rbp+60h+var_70], 3
0x180012715  mov     [r15], edi
0x180012718  xor     r8d, r8d; dwFlags
0x18001271b  xor     edx, edx; hFile
0x18001271d  lea     rcx, Src; "devinv.dll"
0x180012724  call    cs:__imp_LoadLibraryExW
0x18001272a  mov     [rsp+160h+var_120], rax
0x18001272f  test    rax, rax
0x180012732  jnz     short loc_18001275F
0x180012734  call    cs:__imp_GetLastError
0x18001273a  mov     dword ptr [rsp+160h+pcbBytesNeeded], eax
0x18001273e  lea     r9, aDevinvDllCould; "devinv.dll could not be loaded, %d"
0x180012745  mov     r8d, 8B9h
0x18001274b  lea     rdx, aCheckdriversta; "CheckDriverStatus"
0x180012752  lea     ecx, [rdi+1]
0x180012755  call    AslLogCallPrintf
0x18001275a  jmp     loc_180012B30
0x18001275f  mov     rsi, rdi
0x180012762  mov     r12, rdi
0x180012765  mov     r13, rdi
0x180012768  lea     rdx, aGetdevinventor_0; "GetDevInventory"
0x18001276f  mov     rcx, rax; hModule
0x180012772  call    cs:__imp_GetProcAddress
0x180012778  test    rax, rax
0x18001277b  jnz     short loc_1800127AA
0x18001277d  call    cs:__imp_GetLastError
0x180012783  lea     r9, aGetprocaddress; "GetProcAddress GetDevInventory failed %"...
0x18001278a  mov     r8d, 8C2h
0x180012790  lea     rdx, aCheckdriversta; "CheckDriverStatus"
0x180012797  mov     dword ptr [rsp+160h+pcbBytesNeeded], eax
0x18001279b  mov     ecx, 1
0x1800127a0  call    AslLogCallPrintf
0x1800127a5  jmp     loc_180012AFB
0x1800127aa  xor     r8d, r8d
0x1800127ad  lea     rdx, [rbp+60h+var_80]
0x1800127b1  lea     rcx, [rbp+60h+var_E0]
0x1800127b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127ba  test    eax, eax
0x1800127bc  jns     short loc_1800127CD
0x1800127be  lea     r9, aGetdevinventor; "GetDevInventory failed, %x"
0x1800127c5  mov     r8d, 8CAh
0x1800127cb  jmp     short loc_180012790
0x1800127cd  cmp     [rbp+60h+var_88], rdi
0x1800127d1  jnz     short loc_1800127FD
0x1800127d3  cmp     qword ptr [r14+18h], 7
0x1800127d8  jbe     short loc_1800127DD
0x1800127da  mov     r14, [r14]
0x1800127dd  mov     [rsp+160h+pcbBytesNeeded], r14
0x1800127e2  lea     r9, aHaveNotFoundTh; "Have not found the driver name in the i"...
0x1800127e9  mov     r8d, 8D2h
0x1800127ef  lea     rdx, aCheckdriversta; "CheckDriverStatus"
0x1800127f6  mov     ecx, 3
0x1800127fb  jmp     short loc_1800127A0
0x1800127fd  mov     rcx, rbx
0x180012800  call    ?GetPeChecksum@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPeChecksum(std::wstring const &)
0x180012805  mov     dword ptr [rsp+160h+var_128], eax
0x180012809  mov     rbx, [rbp+60h+var_90]
0x18001280d  mov     rbx, [rbx]
0x180012810  lea     rdi, aCheckdriversta; "CheckDriverStatus"
0x180012817  cmp     rbx, [rbp+60h+var_90]
0x18001281b  jz      loc_1800128D7
0x180012821  lea     rsi, [rbx+40h]
0x180012825  cmp     qword ptr [rsi+18h], 7
0x18001282a  jbe     short loc_180012831
0x18001282c  mov     rcx, [rsi]
0x18001282f  jmp     short loc_180012834
0x180012831  mov     rcx, rsi; pszString
0x180012834  lea     r8, [rsp+160h+piRet]; piRet
0x180012839  xor     edx, edx; dwFlags
0x18001283b  call    cs:__imp_StrToIntExW
0x180012841  xor     edx, edx
0x180012843  test    eax, eax
0x180012845  jnz     short loc_180012874
0x180012847  cmp     qword ptr [rsi+18h], 7
0x18001284c  jbe     short loc_180012851
0x18001284e  mov     rsi, [rsi]
0x180012851  mov     [rsp+160h+pcbBytesNeeded], rsi
0x180012856  lea     r9, aStrtointexFail_1; "StrToIntEx failed, %ws"
0x18001285d  mov     r8d, 8E0h
0x180012863  mov     rdx, rdi
0x180012866  mov     ecx, 3
0x18001286b  call    AslLogCallPrintf
0x180012870  xor     edx, edx
0x180012872  jmp     short loc_18001287E
0x180012874  mov     eax, dword ptr [rsp+160h+var_128]
0x180012878  cmp     eax, [rsp+160h+piRet]
0x18001287c  jz      short loc_1800128C9
0x18001287e  mov     rcx, [rbx+10h]
0x180012882  cmp     [rcx+19h], dl
0x180012885  jz      short loc_1800128A7
0x180012887  mov     rax, [rbx+8]
0x18001288b  jmp     short loc_18001289A
0x18001288d  cmp     rbx, [rax+10h]
0x180012891  jnz     short loc_18001289F
0x180012893  mov     rbx, rax
0x180012896  mov     rax, [rax+8]
0x18001289a  cmp     [rax+19h], dl
0x18001289d  jz      short loc_18001288D
0x18001289f  mov     rbx, rax
0x1800128a2  jmp     loc_180012817
0x1800128a7  mov     rbx, rcx
0x1800128aa  mov     rcx, [rcx]
0x1800128ad  cmp     [rcx+19h], dl
0x1800128b0  jnz     loc_180012817
0x1800128b6  mov     rbx, rcx
0x1800128b9  mov     rax, [rcx]
0x1800128bc  mov     rcx, rax
0x1800128bf  cmp     [rax+19h], dl
0x1800128c2  jz      short loc_1800128B6
0x1800128c4  jmp     loc_180012817
0x1800128c9  lea     rdx, [rbx+20h]
0x1800128cd  lea     rcx, [rsp+160h+lpServiceName+8]
0x1800128d2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800128d7  cmp     [rsp+160h+var_F0], r12
0x1800128dc  jnz     short loc_18001290F
0x1800128de  cmp     qword ptr [r14+18h], 7
0x1800128e3  jbe     short loc_1800128E8
0x1800128e5  mov     r14, [r14]
0x1800128e8  mov     [rsp+160h+pcbBytesNeeded], r14
0x1800128ed  lea     r9, aHaveNotFoundAD; "Have not found a driver matching both n"...
0x1800128f4  mov     r8d, 8EDh
0x1800128fa  mov     rdx, rdi
0x1800128fd  mov     ecx, 3
0x180012902  call    AslLogCallPrintf
0x180012907  mov     rsi, r12
0x18001290a  jmp     loc_180012AFB
0x18001290f  mov     rbx, [rsp+160h+var_110]
0x180012914  cmp     [rbx+1D8h], r12
0x18001291b  jz      short loc_180012924
0x18001291d  mov     dword ptr [r15], 1
0x180012924  xor     edx, edx; lpDatabaseName
0x180012926  xor     ecx, ecx; lpMachineName
0x180012928  lea     r8d, [rdx+1]; dwDesiredAccess
0x18001292c  call    cs:__imp_OpenSCManagerW
0x180012932  mov     rsi, rax
0x180012935  test    rax, rax
0x180012938  jnz     short loc_180012958
0x18001293a  mov     [r15], r12d
0x18001293d  call    cs:__imp_GetLastError
0x180012943  lea     r9, aOpenscmanagerF; "OpenSCManager failed, %d"
0x18001294a  mov     r8d, 8FAh
0x180012950  mov     rdx, rdi
0x180012953  jmp     loc_180012797
0x180012958  lea     rdx, [rsp+160h+lpServiceName+8]
0x18001295d  cmp     [rsp+160h+var_E8], 7
0x180012963  cmova   rdx, [rsp+160h+lpServiceName+8]; lpServiceName
0x180012969  mov     r8d, 5; dwDesiredAccess
0x18001296f  mov     rcx, rax; hSCManager
0x180012972  call    cs:__imp_OpenServiceW
0x180012978  mov     r12, rax
0x18001297b  test    rax, rax
0x18001297e  jnz     short loc_1800129C2
0x180012980  mov     [r15], r13d
0x180012983  call    cs:__imp_GetLastError
0x180012989  lea     rcx, [rsp+160h+lpServiceName+8]
0x18001298e  cmp     [rsp+160h+var_E8], 7
0x180012994  cmova   rcx, [rsp+160h+lpServiceName+8]
0x18001299a  mov     [rsp+160h+var_138], eax
0x18001299e  mov     [rsp+160h+pcbBytesNeeded], rcx
0x1800129a3  lea     r9, aOpenserviceFai; "OpenService failed for %ws, %d"
0x1800129aa  mov     r8d, 904h
0x1800129b0  mov     rdx, rdi
0x1800129b3  lea     ecx, [r12+1]
0x1800129b8  call    AslLogCallPrintf
0x1800129bd  jmp     loc_180012AFB
0x1800129c2  cmp     [rbx+1F8h], r13
0x1800129c9  jz      short loc_180012A37
0x1800129cb  lea     rax, [rsp+160h+cbBufSize]
0x1800129d0  mov     [rsp+160h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800129d5  mov     r9d, 24h ; '$'; cbBufSize
0x1800129db  lea     r8, [rbp+60h+Buffer]; lpBuffer
0x1800129df  xor     edx, edx; InfoLevel
0x1800129e1  mov     rcx, r12; hService
0x1800129e4  call    cs:__imp_QueryServiceStatusEx
0x1800129ea  test    eax, eax
0x1800129ec  jnz     short loc_180012A09
0x1800129ee  mov     [r15], r13d
0x1800129f1  call    cs:__imp_GetLastError
0x1800129f7  lea     r9, aQueryservicest; "QueryServiceStatusEx failed, %d"
0x1800129fe  mov     r8d, 911h
0x180012a04  jmp     loc_180012950
0x180012a09  mov     eax, dword ptr [rbp+60h+Buffer+4]
0x180012a0c  mov     dword ptr [rsp+160h+pcbBytesNeeded], eax
0x180012a10  lea     r9, aDriverCurrentS; "Driver current state: %d"
0x180012a17  mov     r8d, 915h
0x180012a1d  mov     rdx, rdi
0x180012a20  mov     ecx, 3
0x180012a25  call    AslLogCallPrintf
0x180012a2a  cmp     dword ptr [rbp+60h+Buffer+4], 1
0x180012a2e  jz      short loc_180012A86
0x180012a30  mov     dword ptr [r15], 1
0x180012a37  cmp     [rbx+218h], r13
0x180012a3e  jz      loc_180012AFB
0x180012a44  mov     [rsp+160h+cbBufSize], r13d
0x180012a49  lea     r9, [rsp+160h+cbBufSize]; pcbBytesNeeded
0x180012a4e  xor     r8d, r8d; cbBufSize
0x180012a51  xor     edx, edx; lpServiceConfig
0x180012a53  mov     rcx, r12; hService
0x180012a56  call    cs:__imp_QueryServiceConfigW
0x180012a5c  test    eax, eax
0x180012a5e  jnz     short loc_180012A8B
0x180012a60  call    cs:__imp_GetLastError
0x180012a66  cmp     eax, 7Ah ; 'z'
0x180012a69  jz      short loc_180012A8B
0x180012a6b  mov     [r15], r13d
0x180012a6e  call    cs:__imp_GetLastError
0x180012a74  lea     r9, aQueryserviceco; "QueryServiceConfig failed, %d"
0x180012a7b  mov     r8d, 929h
0x180012a81  jmp     loc_180012950
0x180012a86  mov     [r15], r13d
0x180012a89  jmp     short loc_180012AFB
0x180012a8b  mov     ecx, [rsp+160h+cbBufSize]; unsigned __int64
0x180012a8f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180012a94  mov     r13, rax
0x180012a97  lea     r9, [rsp+160h+cbBufSize]; pcbBytesNeeded
0x180012a9c  mov     r8d, [rsp+160h+cbBufSize]; cbBufSize
0x180012aa1  mov     rdx, rax; lpServiceConfig
0x180012aa4  mov     rcx, r12; hService
0x180012aa7  call    cs:__imp_QueryServiceConfigW
0x180012aad  test    eax, eax
0x180012aaf  jnz     short loc_180012ACC
0x180012ab1  mov     [r15], eax
0x180012ab4  call    cs:__imp_GetLastError
0x180012aba  lea     r9, aQueryserviceco; "QueryServiceConfig failed, %d"
0x180012ac1  mov     r8d, 938h
0x180012ac7  jmp     loc_180012950
0x180012acc  mov     eax, [r13+4]
0x180012ad0  mov     dword ptr [rsp+160h+pcbBytesNeeded], eax
0x180012ad4  lea     r9, aDriverStartMod; "Driver start mode: %d"
0x180012adb  mov     r8d, 93Ch
0x180012ae1  mov     rdx, rdi
0x180012ae4  mov     ecx, 3
0x180012ae9  call    AslLogCallPrintf
0x180012aee  xor     eax, eax
0x180012af0  cmp     dword ptr [r13+4], 4
0x180012af5  setnz   al
0x180012af8  mov     [r15], eax
0x180012afb  mov     rcx, [rsp+160h+var_120]; hLibModule
0x180012b00  call    cs:__imp_FreeLibrary
0x180012b06  test    rsi, rsi
0x180012b09  jz      short loc_180012B14
0x180012b0b  mov     rcx, rsi; hSCObject
0x180012b0e  call    cs:__imp_CloseServiceHandle
0x180012b14  test    r12, r12
  ... truncated ...
```
