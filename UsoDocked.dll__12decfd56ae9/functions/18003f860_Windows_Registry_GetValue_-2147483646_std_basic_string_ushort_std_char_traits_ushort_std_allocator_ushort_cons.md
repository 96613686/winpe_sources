# Windows::Registry::GetValue<-2147483646>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003f860`
- end: `0x18003fd36`
- name: `??$GetValue@$0?HPPPPPPO@@Registry@Windows@@QEAA?AU?$pair@JV?$optional@V?$variant@I_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@00@Z`
- size: `1238`
- prototype: `__int64 __fastcall(int, int, int, int, LPCWSTR lpValue)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180033130`
- `0x180037b40`

## callees

- `0x180007660`
- `0x1800085a8`
- `0x18001ee04`
- `0x18002778c`
- `0x18002ad38`
- `0x18003a740`
- `0x18003f438`
- `0x18003f4e0`
- `0x18003f860`
- `0x1800408f8`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f8f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f9a9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003fa64`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003fb65`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f8f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f9a9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003fa64`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003fb65`

## string_xrefs

- `0x18003f946`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`
- `0x18003fc59`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`
- `0x18003fd15`: `Registry type unsupported`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Registry::GetValue<-2147483646>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        LPCWSTR lpValue)
{
  LPCWSTR v6; // rbx
  const WCHAR *v7; // r8
  const WCHAR *v8; // rdx
  LSTATUS ValueW; // eax
  unsigned int v10; // edx
  LPCWSTR v11; // r8
  LPCWSTR *v12; // rax
  const WCHAR *v13; // r8
  const WCHAR *v14; // rdx
  unsigned int v15; // edi
  const WCHAR *v16; // r8
  const WCHAR *v17; // rdx
  PVOID *v18; // rax
  const WCHAR *v19; // r8
  const WCHAR *v20; // rdx
  PVOID *v21; // rax
  unsigned __int64 v22; // rdx
  PVOID *v23; // rcx
  PVOID *v24; // rdx
  LPCWSTR *v25; // rax
  bool v26; // zf
  __int64 pvData; // [rsp+40h] [rbp-81h] BYREF
  DWORD pdwType; // [rsp+48h] [rbp-79h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-75h] BYREF
  DWORD v31[2]; // [rsp+50h] [rbp-71h] BYREF
  __int128 v32; // [rsp+58h] [rbp-69h] BYREF
  __int64 v33; // [rsp+68h] [rbp-59h]
  __int64 v34; // [rsp+70h] [rbp-51h]
  char v35; // [rsp+78h] [rbp-49h]
  char v36; // [rsp+80h] [rbp-41h]
  PVOID pExceptionObject[2]; // [rsp+90h] [rbp-31h] BYREF
  unsigned __int64 v38; // [rsp+A0h] [rbp-21h]
  unsigned __int64 v39; // [rsp+A8h] [rbp-19h]
  LPCWSTR lpSubKey[3]; // [rsp+B0h] [rbp-11h] BYREF
  unsigned __int64 v41; // [rsp+C8h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  *(_QWORD *)v31 = a2;
  v6 = lpValue;
  v36 = 0;
  (*(void (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)a1 + 88LL))(a1, lpSubKey);
  pdwType = 0;
  pcbData = 0;
  v7 = lpValue;
  if ( *((_QWORD *)lpValue + 3) > 7u )
    v7 = *(const WCHAR **)lpValue;
  v8 = (const WCHAR *)lpSubKey;
  if ( v41 > 7 )
    v8 = lpSubKey[0];
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v8, v7, 0xFFFFu, &pdwType, 0, &pcbData);
  v10 = ValueW;
  if ( ValueW != 2 && ValueW != 1018 )
  {
    v11 = lpValue;
    if ( *((_QWORD *)lpValue + 3) > 7u )
      v11 = *(LPCWSTR *)lpValue;
    v12 = lpSubKey;
    if ( v41 > 7 )
      v12 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
      (const char *)v10,
      (unsigned int)"%ws[%ws]",
      (const char *)v12,
      v11);
    switch ( pdwType )
    {
      case 4u:
        LODWORD(pvData) = 0;
        v31[0] = 4;
        v13 = lpValue;
        if ( *((_QWORD *)lpValue + 3) > 7u )
          v13 = *(const WCHAR **)lpValue;
        v14 = (const WCHAR *)lpSubKey;
        if ( v41 > 7 )
          v14 = lpSubKey[0];
        v15 = RegGetValueW(HKEY_LOCAL_MACHINE, v14, v13, 0x10u, &pdwType, &pvData, v31);
        if ( !v15 )
        {
          if ( v36 )
          {
            if ( v35 )
            {
              if ( v35 != -1 && (unsigned __int64)v35 >= 2 )
                std::wstring::_Tidy_deallocate(&v32);
              LODWORD(v32) = pvData;
              v35 = 0;
            }
            else
            {
              LODWORD(v32) = pvData;
            }
            goto LABEL_71;
          }
          LODWORD(v32) = pvData;
          v35 = 0;
          goto LABEL_40;
        }
        break;
      case 0xBu:
        pvData = 0;
        v31[0] = 8;
        if ( *((_QWORD *)lpValue + 3) <= 7u )
          v16 = lpValue;
        else
          v16 = *(const WCHAR **)lpValue;
        v17 = (const WCHAR *)lpSubKey;
        if ( v41 > 7 )
          v17 = lpSubKey[0];
        v15 = RegGetValueW(HKEY_LOCAL_MACHINE, v17, v16, 0x40u, &pdwType, &pvData, v31);
        if ( !v15 )
        {
          if ( v36 )
          {
            if ( v35 == 1 )
            {
              *(_QWORD *)&v32 = pvData;
            }
            else
            {
              if ( v35 != -1 && (unsigned __int64)v35 >= 2 )
                std::wstring::_Tidy_deallocate(&v32);
              *(_QWORD *)&v32 = pvData;
              v35 = 1;
            }
            goto LABEL_71;
          }
          *(_QWORD *)&v32 = pvData;
          v35 = 1;
LABEL_40:
          v36 = 1;
          goto LABEL_71;
        }
        break;
      case 1u:
        *(_OWORD *)pExceptionObject = 0;
        v38 = 0;
        v39 = 7;
        LOWORD(pExceptionObject[0]) = 0;
        if ( (unsigned __int64)pcbData >> 1 )
        {
          std::wstring::append(pExceptionObject);
        }
        else
        {
          v38 = 0;
          LOWORD(pExceptionObject[0]) = 0;
        }
        v18 = pExceptionObject;
        if ( v39 > 7 )
          v18 = (PVOID *)pExceptionObject[0];
        if ( *((_QWORD *)lpValue + 3) <= 7u )
          v19 = lpValue;
        else
          v19 = *(const WCHAR **)lpValue;
        v20 = (const WCHAR *)lpSubKey;
        if ( v41 > 7 )
          v20 = lpSubKey[0];
        v15 = RegGetValueW(HKEY_LOCAL_MACHINE, v20, v19, 2u, &pdwType, v18, &pcbData);
        if ( !v15 )
        {
          while ( v38 )
          {
            v21 = pExceptionObject;
            if ( v39 > 7 )
              v21 = (PVOID *)pExceptionObject[0];
            v22 = v38 - 1;
            if ( *((_WORD *)v21 + v38 - 1) )
              break;
            if ( v22 > v38 )
            {
              std::wstring::append(pExceptionObject);
            }
            else
            {
              --v38;
              v23 = pExceptionObject;
              if ( v39 > 7 )
                v23 = (PVOID *)pExceptionObject[0];
              *((_WORD *)v23 + v22) = 0;
            }
          }
          v24 = pExceptionObject;
          if ( v36 )
          {
            std::variant<unsigned int,unsigned __int64,std::wstring>::operator=<std::wstring &,0,0>(
              &v32,
              pExceptionObject,
              v39,
              pExceptionObject[0]);
          }
          else
          {
            v32 = 0;
            v33 = 0;
            v34 = 0;
            if ( v39 > 7 )
              v24 = (PVOID *)pExceptionObject[0];
            std::wstring::_Construct<2,unsigned short const *>(&v32, v24, v38);
            v35 = 2;
            v36 = 1;
          }
        }
        std::wstring::_Tidy_deallocate(pExceptionObject);
        break;
      default:
        std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Registry type unsupported");
        throw (std::logic_error *)pExceptionObject;
    }
    if ( v15 == 2 || v15 == 1018 || v15 == 1168 )
    {
      *(_DWORD *)a2 = (unsigned __int16)v15 | 0x80070000;
      *(_BYTE *)(a2 + 48) = 0;
LABEL_76:
      std::wstring::_Tidy_deallocate(lpSubKey);
      if ( !v36 || v35 == -1 || !v35 )
        return a2;
      v26 = v35 == 1;
      goto LABEL_85;
    }
LABEL_71:
    if ( *((_QWORD *)lpValue + 3) > 7u )
      v6 = *(LPCWSTR *)lpValue;
    v25 = lpSubKey;
    if ( v41 > 7 )
      v25 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
      (const char *)v15,
      (unsigned int)"%ws[%ws]",
      (const char *)v25,
      v6);
    v31[0] = 0;
    std::pair<long,std::optional<std::variant<unsigned int,unsigned __int64,std::wstring>>>::pair<long,std::optional<std::variant<unsigned int,unsigned __int64,std::wstring>>>(
      a2,
      v31,
      &v32);
    goto LABEL_76;
  }
  *(_DWORD *)a2 = (unsigned __int16)ValueW | 0x80070000;
  *(_BYTE *)(a2 + 48) = 0;
  std::wstring::_Tidy_deallocate(lpSubKey);
  if ( !v36 || v35 == -1 || !v35 )
    return a2;
  v26 = v35 == 1;
LABEL_85:
  if ( !v26 )
    std::wstring::_Tidy_deallocate(&v32);
  return a2;
}

```

## disassembly

```asm
0x18003f860  push    rbp
0x18003f862  push    rbx
0x18003f863  push    rsi
0x18003f864  push    rdi
0x18003f865  push    r13
0x18003f867  push    r14
0x18003f869  push    r15
0x18003f86b  lea     rbp, [rsp-1Fh]
0x18003f870  sub     rsp, 0E0h
0x18003f877  mov     rax, cs:__security_cookie
0x18003f87e  xor     rax, rsp
0x18003f881  mov     [rbp+4Fh+var_40], rax
0x18003f885  mov     rsi, rdx
0x18003f888  mov     qword ptr [rbp+4Fh+var_C0], rdx
0x18003f88c  mov     rbx, [rbp+4Fh+lpValue]
0x18003f890  xor     r14d, r14d
0x18003f893  mov     [rbp+4Fh+var_90], r14b
0x18003f897  mov     rax, [rcx]
0x18003f89a  lea     rdx, [rbp+4Fh+lpSubKey]
0x18003f89e  mov     rax, [rax+58h]
0x18003f8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8a7  nop
0x18003f8a8  mov     [rbp+4Fh+var_C8], r14d
0x18003f8ac  mov     [rbp+4Fh+var_C4], r14d
0x18003f8b0  mov     r8, rbx
0x18003f8b3  lea     r15d, [r14+7]
0x18003f8b7  cmp     [rbx+18h], r15
0x18003f8bb  jbe     short loc_18003F8C0
0x18003f8bd  mov     r8, [rbx]; lpValue
0x18003f8c0  lea     rdx, [rbp+4Fh+lpSubKey]
0x18003f8c4  cmp     [rbp+4Fh+var_48], r15
0x18003f8c8  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x18003f8cd  lea     rax, [rbp+4Fh+var_C4]
0x18003f8d1  mov     [rsp+110h+pcbData], rax; pcbData
0x18003f8d6  mov     [rsp+110h+pvData], r14; pvData
0x18003f8db  lea     rax, [rbp+4Fh+var_C8]
0x18003f8df  mov     [rsp+110h+pdwType], rax; pdwType
0x18003f8e4  mov     rdi, 0FFFFFFFF80000002h
0x18003f8eb  mov     r9d, 0FFFFh; dwFlags
0x18003f8f1  mov     rcx, rdi; hkey
0x18003f8f4  call    cs:__imp_RegGetValueW
0x18003f8fa  mov     edx, eax
0x18003f8fc  cmp     eax, 2
0x18003f8ff  jz      loc_18003FCB6
0x18003f905  cmp     eax, 3FAh
0x18003f90a  jz      loc_18003FCB6
0x18003f910  mov     r8, rbx
0x18003f913  cmp     [rbx+18h], r15
0x18003f917  jbe     short loc_18003F91C
0x18003f919  mov     r8, [rbx]
0x18003f91c  lea     rax, [rbp+4Fh+lpSubKey]
0x18003f920  cmp     [rbp+4Fh+var_48], r15
0x18003f924  cmova   rax, [rbp+4Fh+lpSubKey]
0x18003f929  mov     rcx, [rbp+57h]; this
0x18003f92d  mov     [rsp+110h+pcbData], r8
0x18003f932  mov     [rsp+110h+pvData], rax; char *
0x18003f937  lea     r13, aWsWs; "%ws[%ws]"
0x18003f93e  mov     [rsp+110h+pdwType], r13; unsigned int
0x18003f943  mov     r9d, edx; char *
0x18003f946  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f94d  mov     edx, 3Ah ; ':'; void *
0x18003f952  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003f957  mov     eax, [rbp+4Fh+var_C8]
0x18003f95a  cmp     eax, 4
0x18003f95d  jnz     loc_18003FA0F
0x18003f963  mov     dword ptr [rsp+110h+var_D0], r14d
0x18003f968  mov     [rbp+4Fh+var_C0], eax
0x18003f96b  mov     r8, rbx
0x18003f96e  cmp     [rbx+18h], r15
0x18003f972  jbe     short loc_18003F977
0x18003f974  mov     r8, [rbx]; lpValue
0x18003f977  lea     rdx, [rbp+4Fh+lpSubKey]
0x18003f97b  cmp     [rbp+4Fh+var_48], r15
0x18003f97f  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x18003f984  lea     rax, [rbp+4Fh+var_C0]
0x18003f988  mov     [rsp+110h+pcbData], rax; pcbData
0x18003f98d  lea     rax, [rsp+110h+var_D0]
0x18003f992  mov     [rsp+110h+pvData], rax; pvData
0x18003f997  lea     rax, [rbp+4Fh+var_C8]
0x18003f99b  mov     [rsp+110h+pdwType], rax; pdwType
0x18003f9a0  mov     r9d, 10h; dwFlags
0x18003f9a6  mov     rcx, rdi; hkey
0x18003f9a9  call    cs:__imp_RegGetValueW
0x18003f9af  mov     edi, eax
0x18003f9b1  test    eax, eax
0x18003f9b3  jnz     loc_18003FC10
0x18003f9b9  cmp     [rbp+4Fh+var_90], r14b
0x18003f9bd  jz      short loc_18003F9FF
0x18003f9bf  movsx   rax, [rbp+4Fh+var_98]
0x18003f9c4  test    al, al
0x18003f9c6  jnz     short loc_18003F9D4
0x18003f9c8  mov     eax, dword ptr [rsp+110h+var_D0]
0x18003f9cc  mov     dword ptr [rbp+4Fh+var_B8], eax
0x18003f9cf  jmp     loc_18003FC2D
0x18003f9d4  add     rax, 1
0x18003f9d8  jz      short loc_18003F9EF
0x18003f9da  sub     rax, 1
0x18003f9de  jz      short loc_18003F9EF
0x18003f9e0  cmp     rax, 1
0x18003f9e4  jz      short loc_18003F9EF
0x18003f9e6  lea     rcx, [rbp+4Fh+var_B8]
0x18003f9ea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003f9ef  mov     eax, dword ptr [rsp+110h+var_D0]
0x18003f9f3  mov     dword ptr [rbp+4Fh+var_B8], eax
0x18003f9f6  mov     [rbp+4Fh+var_98], r14b
0x18003f9fa  jmp     loc_18003FC2D
0x18003f9ff  mov     eax, dword ptr [rsp+110h+var_D0]
0x18003fa03  mov     dword ptr [rbp+4Fh+var_B8], eax
0x18003fa06  mov     [rbp+4Fh+var_98], r14b
0x18003fa0a  jmp     loc_18003FAD7
0x18003fa0f  cmp     eax, 0Bh
0x18003fa12  jnz     loc_18003FAE0
0x18003fa18  mov     [rsp+110h+var_D0], r14
0x18003fa1d  mov     [rbp+4Fh+var_C0], 8
0x18003fa24  cmp     [rbx+18h], r15
0x18003fa28  jbe     short loc_18003FA2F
0x18003fa2a  mov     r8, [rbx]
0x18003fa2d  jmp     short loc_18003FA32
0x18003fa2f  mov     r8, rbx; lpValue
0x18003fa32  lea     rdx, [rbp+4Fh+lpSubKey]
0x18003fa36  cmp     [rbp+4Fh+var_48], r15
0x18003fa3a  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x18003fa3f  lea     rax, [rbp+4Fh+var_C0]
0x18003fa43  mov     [rsp+110h+pcbData], rax; pcbData
0x18003fa48  lea     rax, [rsp+110h+var_D0]
0x18003fa4d  mov     [rsp+110h+pvData], rax; pvData
0x18003fa52  lea     rax, [rbp+4Fh+var_C8]
0x18003fa56  mov     [rsp+110h+pdwType], rax; pdwType
0x18003fa5b  mov     r9d, 40h ; '@'; dwFlags
0x18003fa61  mov     rcx, rdi; hkey
0x18003fa64  call    cs:__imp_RegGetValueW
0x18003fa6a  mov     edi, eax
0x18003fa6c  test    eax, eax
0x18003fa6e  jnz     loc_18003FC10
0x18003fa74  cmp     [rbp+4Fh+var_90], r14b
0x18003fa78  jz      short loc_18003FAC6
0x18003fa7a  movsx   rax, [rbp+4Fh+var_98]
0x18003fa7f  cmp     al, 1
0x18003fa81  jnz     short loc_18003FA95
0x18003fa83  mov     eax, dword ptr [rsp+110h+var_D0]
0x18003fa87  mov     dword ptr [rbp+4Fh+var_B8], eax
0x18003fa8a  mov     eax, dword ptr [rbp+4Fh+var_D0+4]
0x18003fa8d  mov     dword ptr [rbp+4Fh+var_B8+4], eax
0x18003fa90  jmp     loc_18003FC2D
0x18003fa95  add     rax, 1
0x18003fa99  jz      short loc_18003FAB0
0x18003fa9b  sub     rax, 1
0x18003fa9f  jz      short loc_18003FAB0
0x18003faa1  cmp     rax, 1
0x18003faa5  jz      short loc_18003FAB0
0x18003faa7  lea     rcx, [rbp+4Fh+var_B8]
0x18003faab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003fab0  mov     eax, dword ptr [rsp+110h+var_D0]
0x18003fab4  mov     dword ptr [rbp+4Fh+var_B8], eax
0x18003fab7  mov     eax, dword ptr [rbp+4Fh+var_D0+4]
0x18003faba  mov     dword ptr [rbp+4Fh+var_B8+4], eax
0x18003fabd  mov     [rbp+4Fh+var_98], 1
0x18003fac1  jmp     loc_18003FC2D
0x18003fac6  mov     eax, dword ptr [rsp+110h+var_D0]
0x18003faca  mov     dword ptr [rbp+4Fh+var_B8], eax
0x18003facd  mov     eax, dword ptr [rbp+4Fh+var_D0+4]
0x18003fad0  mov     dword ptr [rbp+4Fh+var_B8+4], eax
0x18003fad3  mov     [rbp+4Fh+var_98], 1
0x18003fad7  mov     [rbp+4Fh+var_90], 1
0x18003fadb  jmp     loc_18003FC2D
0x18003fae0  cmp     eax, 1
0x18003fae3  jnz     loc_18003FD15
0x18003fae9  xorps   xmm0, xmm0
0x18003faec  movups  xmmword ptr [rbp+4Fh+pExceptionObject], xmm0
0x18003faf0  mov     [rbp+4Fh+var_70], r14
0x18003faf4  mov     [rbp+4Fh+var_68], r15
0x18003faf8  mov     word ptr [rbp+4Fh+pExceptionObject], r14w
0x18003fafd  mov     edx, [rbp+4Fh+var_C4]
0x18003fb00  shr     rdx, 1
0x18003fb03  jnz     short loc_18003FB11
0x18003fb05  mov     [rbp+4Fh+var_70], rdx
0x18003fb09  mov     word ptr [rbp+rdx*2+4Fh+pExceptionObject], r14w
0x18003fb0f  jmp     short loc_18003FB1D
0x18003fb11  xor     r8d, r8d
0x18003fb14  lea     rcx, [rbp+4Fh+pExceptionObject]; Src
0x18003fb18  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x18003fb1d  lea     rax, [rbp+4Fh+pExceptionObject]
0x18003fb21  cmp     [rbp+4Fh+var_68], r15
0x18003fb25  cmova   rax, [rbp+4Fh+pExceptionObject]
0x18003fb2a  cmp     [rbx+18h], r15
0x18003fb2e  jbe     short loc_18003FB35
0x18003fb30  mov     r8, [rbx]
0x18003fb33  jmp     short loc_18003FB38
0x18003fb35  mov     r8, rbx; lpValue
0x18003fb38  lea     rdx, [rbp+4Fh+lpSubKey]
0x18003fb3c  cmp     [rbp+4Fh+var_48], r15
0x18003fb40  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x18003fb45  lea     rcx, [rbp+4Fh+var_C4]
0x18003fb49  mov     [rsp+110h+pcbData], rcx; pcbData
0x18003fb4e  mov     [rsp+110h+pvData], rax; pvData
0x18003fb53  lea     rax, [rbp+4Fh+var_C8]
0x18003fb57  mov     [rsp+110h+pdwType], rax; pdwType
0x18003fb5c  mov     r9d, 2; dwFlags
0x18003fb62  mov     rcx, rdi; hkey
0x18003fb65  call    cs:__imp_RegGetValueW
0x18003fb6b  mov     edi, eax
0x18003fb6d  test    eax, eax
0x18003fb6f  jnz     loc_18003FC07
0x18003fb75  mov     r8, [rbp+4Fh+var_68]
0x18003fb79  mov     r9, [rbp+4Fh+pExceptionObject]
0x18003fb7d  mov     rcx, [rbp+4Fh+var_70]
0x18003fb81  test    rcx, rcx
0x18003fb84  jz      short loc_18003FBC8
0x18003fb86  lea     rax, [rbp+4Fh+pExceptionObject]
0x18003fb8a  cmp     r8, r15
0x18003fb8d  cmova   rax, r9
0x18003fb91  lea     rdx, [rcx-1]
0x18003fb95  cmp     [rax+rdx*2], r14w
0x18003fb9a  jnz     short loc_18003FBC8
0x18003fb9c  cmp     rdx, rcx
0x18003fb9f  ja      short loc_18003FBB7
0x18003fba1  mov     [rbp+4Fh+var_70], rdx
0x18003fba5  lea     rcx, [rbp+4Fh+pExceptionObject]
0x18003fba9  cmp     r8, r15
0x18003fbac  cmova   rcx, r9
0x18003fbb0  mov     [rcx+rdx*2], r14w
0x18003fbb5  jmp     short loc_18003FB75
0x18003fbb7  xor     r8d, r8d
0x18003fbba  sub     rdx, rcx
0x18003fbbd  lea     rcx, [rbp+4Fh+pExceptionObject]; Src
0x18003fbc1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x18003fbc6  jmp     short loc_18003FB75
0x18003fbc8  lea     rdx, [rbp+4Fh+pExceptionObject]
0x18003fbcc  cmp     [rbp+4Fh+var_90], r14b
0x18003fbd0  jz      short loc_18003FBDD
0x18003fbd2  lea     rcx, [rbp+4Fh+var_B8]
0x18003fbd6  call    ??$?4AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@$0A@@?$variant@I_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::variant<uint,unsigned __int64,std::wstring>::operator=<std::wstring &,0,0>(std::wstring &)
0x18003fbdb  jmp     short loc_18003FC07
0x18003fbdd  xorps   xmm0, xmm0
0x18003fbe0  movups  [rbp+4Fh+var_B8], xmm0
0x18003fbe4  mov     [rbp+4Fh+var_A8], r14
0x18003fbe8  mov     [rbp+4Fh+var_A0], r14
0x18003fbec  cmp     r8, r15
0x18003fbef  cmova   rdx, r9
0x18003fbf3  mov     r8, rcx
0x18003fbf6  lea     rcx, [rbp+4Fh+var_B8]
0x18003fbfa  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18003fbff  mov     [rbp+4Fh+var_98], 2
0x18003fc03  mov     [rbp+4Fh+var_90], 1
0x18003fc07  lea     rcx, [rbp+4Fh+pExceptionObject]
0x18003fc0b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003fc10  cmp     edi, 2
0x18003fc13  jz      loc_18003FCA6
0x18003fc19  cmp     edi, 3FAh
0x18003fc1f  jz      loc_18003FCA6
0x18003fc25  cmp     edi, 490h
0x18003fc2b  jz      short loc_18003FCA6
0x18003fc2d  cmp     [rbx+18h], r15
0x18003fc31  jbe     short loc_18003FC36
0x18003fc33  mov     rbx, [rbx]
0x18003fc36  lea     rax, [rbp+4Fh+lpSubKey]
0x18003fc3a  cmp     [rbp+4Fh+var_48], r15
0x18003fc3e  cmova   rax, [rbp+4Fh+lpSubKey]
0x18003fc43  mov     rcx, [rbp+57h]; this
0x18003fc47  mov     [rsp+110h+pcbData], rbx
0x18003fc4c  mov     [rsp+110h+pvData], rax; char *
0x18003fc51  mov     [rsp+110h+pdwType], r13; unsigned int
0x18003fc56  mov     r9d, edi; char *
0x18003fc59  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003fc60  mov     edx, 7Fh; void *
0x18003fc65  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003fc6a  mov     [rbp+4Fh+var_C0], r14d
0x18003fc6e  lea     r8, [rbp+4Fh+var_B8]
0x18003fc72  lea     rdx, [rbp+4Fh+var_C0]
0x18003fc76  mov     rcx, rsi
0x18003fc79  call    ??$?0JAEAV?$optional@V?$variant@I_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@$0A@@?$pair@JV?$optional@V?$variant@I_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAA@$$QEAJAEAV?$optional@V?$variant@I_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@1@@Z; std::pair<long,std::optional<std::variant<uint,unsigned __int64,std::wstring>>>::pair<long,std::optional<std::variant<uint,unsigned __int64,std::wstring>>>(long &&,std::optional<std::variant<uint,unsigned __int64,std::wstring>> &)
0x18003fc7e  nop
0x18003fc7f  lea     rcx, [rbp+4Fh+lpSubKey]
0x18003fc83  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003fc88  nop
0x18003fc89  cmp     [rbp+4Fh+var_90], r14b
0x18003fc8d  jz      short loc_18003FCF4
0x18003fc8f  movsx   rax, [rbp+4Fh+var_98]
0x18003fc94  add     rax, 1
0x18003fc98  jz      short loc_18003FCF4
0x18003fc9a  sub     rax, 1
0x18003fc9e  jz      short loc_18003FCF4
0x18003fca0  cmp     rax, 1
0x18003fca4  jmp     short loc_18003FCE9
0x18003fca6  movzx   eax, di
0x18003fca9  or      eax, 80070000h
0x18003fcae  mov     [rsi], eax
0x18003fcb0  mov     [rsi+30h], r14b
0x18003fcb4  jmp     short loc_18003FC7F
0x18003fcb6  movzx   eax, dx
0x18003fcb9  or      eax, 80070000h
0x18003fcbe  mov     [rsi], eax
0x18003fcc0  mov     [rsi+30h], r14b
0x18003fcc4  lea     rcx, [rbp+4Fh+lpSubKey]
0x18003fcc8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003fccd  nop
0x18003fcce  cmp     [rbp+4Fh+var_90], r14b
0x18003fcd2  jz      short loc_18003FCF4
0x18003fcd4  movsx   rcx, [rbp+4Fh+var_98]
0x18003fcd9  add     rcx, 1
  ... truncated ...
```
