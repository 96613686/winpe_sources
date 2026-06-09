# GetValueFromRegistry(ushort *,ulong,ushort const *,ushort const *,ushort const *)

- ea: `0x1800076a8`
- end: `0x1800078d1`
- name: `?GetValueFromRegistry@@YAHPEAGKPEBG11@Z`
- size: `553`
- prototype: `__int64 __fastcall(BYTE *, unsigned int, PCNZWCH lpString1, LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002c74`
- `0x1800063c4`

## callees

- `0x1800022bc`
- `0x1800076a8`
- `0x180008a6c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180007876`
- `KERNEL32!LocalFree` at `0x180007876`
- `KERNEL32!LocalAlloc` at `0x180007845`
- `KERNEL32!LocalAlloc` at `0x180007845`
- `KERNEL32!CompareStringW` at `0x1800076f9`
- `KERNEL32!CompareStringW` at `0x18000772f`
- `KERNEL32!CompareStringW` at `0x180007762`
- `KERNEL32!CompareStringW` at `0x180007795`
- `KERNEL32!CompareStringW` at `0x1800076f9`
- `KERNEL32!CompareStringW` at `0x18000772f`
- `KERNEL32!CompareStringW` at `0x180007762`
- `KERNEL32!CompareStringW` at `0x180007795`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000786a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000786a`
- `ADVAPI32!RegQueryValueExW` at `0x180007800`
- `ADVAPI32!RegQueryValueExW` at `0x180007800`
- `ADVAPI32!RegCloseKey` at `0x18000780e`
- `ADVAPI32!RegCloseKey` at `0x180007819`
- `ADVAPI32!RegCloseKey` at `0x18000780e`
- `ADVAPI32!RegCloseKey` at `0x180007819`
- `ADVAPI32!RegOpenKeyExW` at `0x1800077c0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800077c0`

## pseudocode

```c
__int64 __fastcall GetValueFromRegistry(
        BYTE *a1,
        unsigned int a2,
        PCNZWCH lpString1,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName)
{
  unsigned __int64 v5; // rsi
  unsigned __int64 v9; // rcx
  HKEY v10; // rcx
  LSTATUS v11; // eax
  unsigned __int16 *v12; // rax
  WCHAR *v13; // rbx
  DWORD cbData; // [rsp+30h] [rbp-18h] BYREF
  DWORD Type; // [rsp+34h] [rbp-14h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-10h] BYREF

  v5 = a2;
  phkResult = 0;
  Type = 0;
  cbData = 0;
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"HKCR", -1) == 2 )
  {
    v9 = 0xFFFFFFFF80000000uLL;
  }
  else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"HKCU", -1) == 2 )
  {
    v9 = -2147483647;
  }
  else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"HKLM", -1) == 2 )
  {
    v9 = -2147483646;
  }
  else
  {
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"HKU", -1) != 2 )
    {
      if ( *lpString1 )
        MsgBox2Param(hWnd, 0x465u, 0, 0, 0x10u, 0);
      return 0;
    }
    v9 = -2147483645;
  }
  if ( !RegOpenKeyExW((HKEY)v9, lpSubKey, 0, 0x20019u, &phkResult) )
  {
    v10 = phkResult;
    if ( 2 * v5 > 0xFFFFFFFF )
    {
      cbData = -1;
      goto LABEL_12;
    }
    cbData = 2 * v5;
    v11 = RegQueryValueExW(phkResult, lpValueName, 0, &Type, a1, &cbData);
    v10 = phkResult;
    if ( v11 )
    {
LABEL_12:
      RegCloseKey(v10);
      return 0;
    }
    RegCloseKey(phkResult);
    if ( cbData )
    {
      if ( Type - 1 <= 1 )
      {
        if ( Type != 2 )
          return 1;
        v12 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v5);
        v13 = v12;
        if ( v12 )
        {
          StringCchCopyW(v12, v5, (const unsigned __int16 *)a1);
          cbData = ExpandEnvironmentStringsW(v13, (LPWSTR)a1, v5);
          LocalFree(v13);
          if ( cbData )
          {
            if ( cbData <= (unsigned int)v5 )
              return 1;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800076a8  push    rbp
0x1800076aa  push    rbx
0x1800076ab  push    rsi
0x1800076ac  push    rdi
0x1800076ad  push    r12
0x1800076af  push    r13
0x1800076b1  push    r14
0x1800076b3  push    r15
0x1800076b5  mov     rbp, rsp
0x1800076b8  sub     rsp, 48h
0x1800076bc  xor     r15d, r15d
0x1800076bf  mov     esi, edx
0x1800076c1  or      r12d, 0FFFFFFFFh
0x1800076c5  mov     [rbp+phkResult], r15
0x1800076c9  mov     rdi, r9
0x1800076cc  mov     [rsp+48h+cchCount2], r12d; cchCount2
0x1800076d1  mov     r14, rcx
0x1800076d4  mov     [rbp+Type], r15d
0x1800076d8  lea     rax, aHkcr; "HKCR"
0x1800076df  mov     [rbp+cbData], r15d
0x1800076e3  lea     r13d, [r15+1]
0x1800076e7  mov     [rsp+48h+lpString2], rax; lpString2
0x1800076ec  mov     edx, r13d; dwCmpFlags
0x1800076ef  lea     ecx, [r15+7Fh]; Locale
0x1800076f3  mov     r9d, r12d; cchCount1
0x1800076f6  mov     rbx, r8
0x1800076f9  call    cs:__imp_CompareStringW
0x1800076ff  cmp     eax, 2
0x180007702  jnz     short loc_180007710
0x180007704  mov     rcx, 0FFFFFFFF80000000h
0x18000770b  jmp     loc_1800077AB
0x180007710  lea     rax, aHkcu; "HKCU"
0x180007717  mov     [rsp+48h+cchCount2], r12d; cchCount2
0x18000771c  mov     r9d, r12d; cchCount1
0x18000771f  mov     [rsp+48h+lpString2], rax; lpString2
0x180007724  mov     r8, rbx; lpString1
0x180007727  mov     edx, r13d; dwCmpFlags
0x18000772a  mov     ecx, 7Fh; Locale
0x18000772f  call    cs:__imp_CompareStringW
0x180007735  cmp     eax, 2
0x180007738  jnz     short loc_180007743
0x18000773a  mov     rcx, 0FFFFFFFF80000001h
0x180007741  jmp     short loc_1800077AB
0x180007743  lea     rax, String1; "HKLM"
0x18000774a  mov     [rsp+48h+cchCount2], r12d; cchCount2
0x18000774f  mov     r9d, r12d; cchCount1
0x180007752  mov     [rsp+48h+lpString2], rax; lpString2
0x180007757  mov     r8, rbx; lpString1
0x18000775a  mov     edx, r13d; dwCmpFlags
0x18000775d  mov     ecx, 7Fh; Locale
0x180007762  call    cs:__imp_CompareStringW
0x180007768  cmp     eax, 2
0x18000776b  jnz     short loc_180007776
0x18000776d  mov     rcx, 0FFFFFFFF80000002h
0x180007774  jmp     short loc_1800077AB
0x180007776  lea     rax, aHku; "HKU"
0x18000777d  mov     [rsp+48h+cchCount2], r12d; cchCount2
0x180007782  mov     r9d, r12d; cchCount1
0x180007785  mov     [rsp+48h+lpString2], rax; lpString2
0x18000778a  mov     r8, rbx; lpString1
0x18000778d  mov     edx, r13d; dwCmpFlags
0x180007790  mov     ecx, 7Fh; Locale
0x180007795  call    cs:__imp_CompareStringW
0x18000779b  cmp     eax, 2
0x18000779e  jnz     loc_180007894
0x1800077a4  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800077ab  lea     rax, [rbp+phkResult]
0x1800077af  mov     r9d, 20019h; samDesired
0x1800077b5  xor     r8d, r8d; ulOptions
0x1800077b8  mov     [rsp+48h+lpString2], rax; phkResult
0x1800077bd  mov     rdx, rdi; lpSubKey
0x1800077c0  call    cs:__imp_RegOpenKeyExW
0x1800077c6  test    eax, eax
0x1800077c8  jnz     loc_1800078BE
0x1800077ce  mov     rcx, [rbp+phkResult]; hKey
0x1800077d2  lea     rbx, [rsi+rsi]
0x1800077d6  mov     eax, 0FFFFFFFFh
0x1800077db  cmp     rbx, rax
0x1800077de  ja      loc_18000788C
0x1800077e4  mov     rdx, [rbp+lpValueName]; lpValueName
0x1800077e8  lea     rax, [rbp+cbData]
0x1800077ec  mov     qword ptr [rsp+48h+cchCount2], rax; lpcbData
0x1800077f1  lea     r9, [rbp+Type]; lpType
0x1800077f5  xor     r8d, r8d; lpReserved
0x1800077f8  mov     [rsp+48h+lpString2], r14; lpData
0x1800077fd  mov     [rbp+cbData], ebx
0x180007800  call    cs:__imp_RegQueryValueExW
0x180007806  mov     rcx, [rbp+phkResult]; hKey
0x18000780a  test    eax, eax
0x18000780c  jz      short loc_180007819
0x18000780e  call    cs:__imp_RegCloseKey
0x180007814  jmp     loc_1800078BE
0x180007819  call    cs:__imp_RegCloseKey
0x18000781f  cmp     [rbp+cbData], r15d
0x180007823  jz      loc_1800078BE
0x180007829  mov     ecx, [rbp+Type]
0x18000782c  lea     eax, [rcx-1]
0x18000782f  cmp     eax, r13d
0x180007832  ja      loc_1800078BE
0x180007838  cmp     ecx, 2
0x18000783b  jnz     short loc_180007887
0x18000783d  mov     rdx, rbx; uBytes
0x180007840  mov     ecx, 40h ; '@'; uFlags
0x180007845  call    cs:__imp_LocalAlloc
0x18000784b  mov     rbx, rax
0x18000784e  test    rax, rax
0x180007851  jz      short loc_1800078BE
0x180007853  mov     r8, r14; unsigned __int16 *
0x180007856  mov     rdx, rsi; unsigned __int64
0x180007859  mov     rcx, rax; unsigned __int16 *
0x18000785c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007861  mov     r8d, esi; nSize
0x180007864  mov     rdx, r14; lpDst
0x180007867  mov     rcx, rbx; lpSrc
0x18000786a  call    cs:__imp_ExpandEnvironmentStringsW
0x180007870  mov     rcx, rbx; hMem
0x180007873  mov     [rbp+cbData], eax
0x180007876  call    cs:__imp_LocalFree
0x18000787c  mov     ecx, [rbp+cbData]
0x18000787f  test    ecx, ecx
0x180007881  jz      short loc_1800078BE
0x180007883  cmp     ecx, esi
0x180007885  ja      short loc_1800078BE
0x180007887  mov     eax, r13d
0x18000788a  jmp     short loc_1800078C0
0x18000788c  mov     [rbp+cbData], eax
0x18000788f  jmp     loc_18000780E
0x180007894  cmp     [rbx], r15w
0x180007898  jz      short loc_1800078BE
0x18000789a  mov     rcx, cs:hWnd; hWnd
0x1800078a1  xor     r9d, r9d; unsigned __int16 *
0x1800078a4  mov     [rsp+48h+cchCount2], r15d; unsigned int
0x1800078a9  xor     r8d, r8d; unsigned __int16 *
0x1800078ac  mov     edx, 465h; uID
0x1800078b1  mov     dword ptr [rsp+48h+lpString2], 10h; unsigned int
0x1800078b9  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x1800078be  xor     eax, eax
0x1800078c0  add     rsp, 48h
0x1800078c4  pop     r15
0x1800078c6  pop     r14
0x1800078c8  pop     r13
0x1800078ca  pop     r12
0x1800078cc  pop     rdi
0x1800078cd  pop     rsi
0x1800078ce  pop     rbx
0x1800078cf  pop     rbp
0x1800078d0  retn
```
