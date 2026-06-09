# Throttler::ThrottleAnyIdInvocations(HKEY__ *)

- ea: `0x180006830`
- end: `0x180006d0e`
- name: `?ThrottleAnyIdInvocations@Throttler@@AEAA?AW4ThrottleResult@1@PEAUHKEY__@@@Z`
- size: `1246`
- prototype: `enum Throttler::ThrottleResult __high(HKEY)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180006530`

## callees

- `0x180002590`
- `0x180005ee4`
- `0x180006830`
- `0x180006de0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006ce2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006ce2`
- `KERNEL32!HeapFree` at `0x180006c62`
- `KERNEL32!HeapFree` at `0x180006cb8`
- `KERNEL32!HeapFree` at `0x180006c62`
- `KERNEL32!HeapFree` at `0x180006cb8`
- `KERNEL32!HeapAlloc` at `0x180006949`
- `KERNEL32!HeapAlloc` at `0x180006a8a`
- `KERNEL32!HeapAlloc` at `0x180006949`
- `KERNEL32!HeapAlloc` at `0x180006a8a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000690f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000690f`
- `KERNEL32!GetProcessHeap` at `0x180006938`
- `KERNEL32!GetProcessHeap` at `0x180006a7c`
- `KERNEL32!GetProcessHeap` at `0x180006c54`
- `KERNEL32!GetProcessHeap` at `0x180006caa`
- `KERNEL32!GetProcessHeap` at `0x180006938`
- `KERNEL32!GetProcessHeap` at `0x180006a7c`
- `KERNEL32!GetProcessHeap` at `0x180006c54`
- `KERNEL32!GetProcessHeap` at `0x180006caa`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800068b2`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800068b2`
- `ADVAPI32!RegDeleteKeyExW` at `0x180006c46`
- `ADVAPI32!RegDeleteKeyExW` at `0x180006c46`
- `ADVAPI32!RegEnumKeyExW` at `0x1800069e1`
- `ADVAPI32!RegEnumKeyExW` at `0x1800069e1`
- `ADVAPI32!RegOpenKeyExW` at `0x180006b91`
- `ADVAPI32!RegOpenKeyExW` at `0x180006b91`
- `ADVAPI32!RegCloseKey` at `0x180006bed`
- `ADVAPI32!RegCloseKey` at `0x180006c72`
- `ADVAPI32!RegCloseKey` at `0x180006bed`
- `ADVAPI32!RegCloseKey` at `0x180006c72`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Throttler::ThrottleAnyIdInvocations(Throttler *a1, HKEY a2)
{
  HKEY v2; // r15
  unsigned int v3; // r13d
  LSTATUS v4; // eax
  signed int v5; // ebx
  int v6; // r9d
  __int64 dwHighDateTime; // rsi
  DWORD v8; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v10; // r12
  unsigned int v11; // r14d
  DWORD i; // esi
  LSTATUS v13; // eax
  int v14; // r9d
  SIZE_T v15; // rbx
  HANDLE v16; // rax
  WCHAR *v17; // rdx
  unsigned __int64 v18; // rcx
  __int64 v19; // rax
  WCHAR *v20; // r8
  WCHAR v21; // r9
  WCHAR *v22; // rax
  LSTATUS v23; // eax
  int v24; // eax
  unsigned __int64 v25; // rsi
  unsigned __int64 j; // r14
  HANDLE v27; // rax
  unsigned __int64 v28; // rsi
  unsigned __int64 k; // r14
  __int64 v30; // r15
  void *v31; // r12
  HANDLE v32; // rax
  WCHAR *v34; // rbx
  HANDLE v35; // rax
  int lpcSubKeys; // [rsp+20h] [rbp-D8h]
  int lpcSubKeysa; // [rsp+20h] [rbp-D8h]
  unsigned int v38; // [rsp+60h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-90h] BYREF
  DWORD v40; // [rsp+70h] [rbp-88h]
  WCHAR *dwLowDateTime; // [rsp+78h] [rbp-80h] BYREF
  signed int v42; // [rsp+80h] [rbp-78h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-70h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+90h] [rbp-68h] BYREF
  __int128 v45; // [rsp+98h] [rbp-60h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-50h]
  __int64 v47; // [rsp+B0h] [rbp-48h]
  WCHAR *v48; // [rsp+B8h] [rbp-40h]
  DWORD cchName; // [rsp+110h] [rbp+18h] BYREF
  DWORD v52; // [rsp+118h] [rbp+20h] BYREF

  v2 = a2;
  v3 = 0;
  phkResult = 0;
  ftLastWriteTime = 0;
  SystemTimeAsFileTime = 0;
  v52 = 0;
  cchName = 0;
  v45 = 0;
  v46 = 0;
  v4 = RegQueryInfoKeyW(a2, 0, 0, 0, &v52, &cchName, 0, 0, 0, 0, 0, 0);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    lpcSubKeys = v5;
    v6 = 347;
    goto LABEL_5;
  }
  if ( !v52 || !cchName )
    return 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  dwHighDateTime = SystemTimeAsFileTime.dwHighDateTime;
  dwLowDateTime = (WCHAR *)SystemTimeAsFileTime.dwLowDateTime;
  v8 = ++cchName;
  ProcessHeap = GetProcessHeap();
  v10 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 2LL * v8);
  v48 = v10;
  if ( !v10 )
  {
    v5 = -2147024882;
    lpcSubKeys = -2147024882;
    v6 = 361;
LABEL_5:
    DebugPrint(0, "THROTTLE ERROR: %s:%d - hr = 0x%08X\n", "Throttler::ThrottleAnyIdInvocations", v6, lpcSubKeys);
    goto LABEL_49;
  }
  v11 = 0;
  v38 = 0;
  v5 = 0;
  v47 = (unsigned int)((unsigned __int64)&dwLowDateTime[0x80000000LL * dwHighDateTime] / 0x23C34600);
  for ( i = 0; ; ++i )
  {
    v40 = i;
    if ( i >= v52 )
      goto LABEL_46;
    v13 = RegEnumKeyExW(v2, i, v10, &cchName, 0, 0, 0, &ftLastWriteTime);
    if ( v13 == 259 )
      goto LABEL_46;
    if ( v13 )
    {
      if ( v13 > 0 )
        v5 = (unsigned __int16)v13 | 0x80070000;
      else
        v5 = v13;
      v14 = 375;
LABEL_18:
      lpcSubKeysa = v5;
LABEL_19:
      DebugPrint(0, "THROTTLE ERROR: %s:%d - hr = 0x%08X\n", "Throttler::ThrottleAnyIdInvocations", v14, lpcSubKeysa);
      goto LABEL_48;
    }
    if ( v47
       - (unsigned __int64)(unsigned int)((ftLastWriteTime.dwLowDateTime
                                         + ((unsigned __int64)ftLastWriteTime.dwHighDateTime << 32))
                                        / 0x23C34600) <= *((unsigned int *)a1 + 4) )
      break;
    v15 = 2LL * (cchName + 1);
    v16 = GetProcessHeap();
    v17 = (WCHAR *)HeapAlloc(v16, 0, v15);
    dwLowDateTime = v17;
    if ( !v17 )
    {
      v5 = -2147024882;
      lpcSubKeysa = -2147024882;
      v14 = 382;
      goto LABEL_19;
    }
    v18 = cchName + 1;
    if ( cchName == -1 )
    {
      v5 = -2147024809;
    }
    else
    {
      if ( v18 > 0x7FFFFFFF )
      {
        *v17 = 0;
        v5 = -2147024809;
        continue;
      }
      v19 = 2147483646;
      v20 = v10;
      do
      {
        if ( !v19 )
          break;
        v21 = *v20;
        if ( !*v20 )
          break;
        ++v20;
        *v17++ = v21;
        --v19;
        --v18;
      }
      while ( v18 );
      v22 = v17 - 1;
      if ( v18 )
        v22 = v17;
      *v22 = 0;
      v5 = v18 == 0 ? 0x8007007A : 0;
    }
    v42 = v5;
    if ( v5 >= 0 )
    {
      try
      {
        std::vector<unsigned short *>::push_back(&v45, &dwLowDateTime);
      }
      catch ( exception )
      {
        v34 = dwLowDateTime;
        if ( dwLowDateTime )
        {
          v35 = GetProcessHeap();
          HeapFree(v35, 0, v34);
        }
        v2 = a2;
        v11 = v38;
        v10 = v48;
        v5 = v42;
        v3 = 0;
        i = v40;
        continue;
      }
    }
LABEL_61:
    ;
  }
  v23 = RegOpenKeyExW(v2, v10, 0, 0x20019u, &phkResult);
  v5 = v23;
  if ( v23 )
  {
    if ( v23 > 0 )
      v5 = (unsigned __int16)v23 | 0x80070000;
    v14 = 404;
    goto LABEL_18;
  }
  v38 = 0;
  v24 = Throttler::CountRecentAndCleanOldOccurs(a1, phkResult, &v38);
  v5 = v24;
  if ( v24 < 0 )
  {
    lpcSubKeysa = v24;
    v14 = 408;
    goto LABEL_19;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  v11 += v38;
  if ( v11 < *((_DWORD *)a1 + 3) )
  {
    v38 = v11;
    goto LABEL_61;
  }
  v3 = 2;
LABEL_46:
  v25 = (__int64)(*((_QWORD *)&v45 + 1) - v45) >> 3;
  for ( j = 0; j < v25; ++j )
    RegDeleteKeyExW(v2, *(LPCWSTR *)(v45 + 8 * j), 0, 0);
LABEL_48:
  v27 = GetProcessHeap();
  HeapFree(v27, 0, v10);
LABEL_49:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  v28 = (__int64)(*((_QWORD *)&v45 + 1) - v45) >> 3;
  for ( k = 0; k < v28; ++k )
  {
    v30 = v45;
    v31 = *(void **)(v45 + 8 * k);
    if ( v31 )
    {
      v32 = GetProcessHeap();
      HeapFree(v32, 0, v31);
      *(_QWORD *)(v30 + 8 * k) = 0;
    }
  }
  if ( v5 < 0 )
    v3 = 4;
  if ( (_QWORD)v45 )
    operator delete((void *)v45);
  return v3;
}

```

## disassembly

```asm
0x180006830  mov     r11, rsp
0x180006833  mov     [r11+10h], rdx
0x180006837  mov     [r11+8], rcx
0x18000683b  push    rbx
0x18000683c  push    rsi
0x18000683d  push    rdi
0x18000683e  push    r12
0x180006840  push    r13
0x180006842  push    r14
0x180006844  push    r15
0x180006846  sub     rsp, 0C0h
0x18000684d  mov     r15, rdx
0x180006850  xor     edi, edi
0x180006852  mov     r13d, edi
0x180006855  mov     [rsp+0F8h+phkResult], rdi
0x18000685a  mov     [r11-68h], rdi
0x18000685e  mov     [r11-70h], rdi
0x180006862  mov     [r11+20h], edi
0x180006866  mov     [r11+18h], edi
0x18000686a  xorps   xmm0, xmm0
0x18000686d  movdqu  xmmword ptr [r11-60h], xmm0
0x180006873  mov     [r11-50h], rdi
0x180006877  mov     [rsp+0F8h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18000687c  mov     [rsp+0F8h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180006881  mov     [rsp+0F8h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x180006886  mov     [rsp+0F8h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x18000688b  mov     [rsp+0F8h+lpcValues], rdi; lpcValues
0x180006890  mov     [rsp+0F8h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180006895  lea     rax, [r11+18h]
0x180006899  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000689e  lea     rax, [r11+20h]
0x1800068a2  mov     [rsp+0F8h+lpcSubKeys], rax; lpcSubKeys
0x1800068a7  xor     r9d, r9d; lpReserved
0x1800068aa  xor     r8d, r8d; lpcchClass
0x1800068ad  xor     edx, edx; lpClass
0x1800068af  mov     rcx, r15; hKey
0x1800068b2  call    cs:__imp_RegQueryInfoKeyW
0x1800068b8  mov     ebx, eax
0x1800068ba  test    eax, eax
0x1800068bc  jz      short loc_1800068ED
0x1800068be  jle     short loc_1800068C9
0x1800068c0  movzx   ebx, ax
0x1800068c3  or      ebx, 80070000h
0x1800068c9  mov     dword ptr [rsp+0F8h+lpcSubKeys], ebx
0x1800068cd  mov     r9d, 15Bh
0x1800068d3  lea     r8, aThrottlerThrot; "Throttler::ThrottleAnyIdInvocations"
0x1800068da  lea     rdx, aThrottleErrorS_0; "THROTTLE ERROR: %s:%d - hr = 0x%08X\n"
0x1800068e1  xor     ecx, ecx; Level
0x1800068e3  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x1800068e8  jmp     loc_180006C68
0x1800068ed  cmp     [rsp+0F8h+arg_18], edi
0x1800068f4  jz      loc_180006CF9
0x1800068fa  cmp     [rsp+0F8h+cchName], edi
0x180006901  jz      loc_180006CF9
0x180006907  lea     rcx, [rsp+0F8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000690f  call    cs:__imp_GetSystemTimeAsFileTime
0x180006915  mov     esi, [rsp+0F8h+SystemTimeAsFileTime.dwHighDateTime]
0x18000691c  mov     eax, [rsp+0F8h+SystemTimeAsFileTime.dwLowDateTime]
0x180006923  mov     [rsp+0F8h+var_80], rax
0x180006928  mov     ebx, [rsp+0F8h+cchName]
0x18000692f  inc     ebx
0x180006931  mov     [rsp+0F8h+cchName], ebx
0x180006938  call    cs:__imp_GetProcessHeap
0x18000693e  mov     r8d, ebx
0x180006941  add     r8, r8; dwBytes
0x180006944  xor     edx, edx; dwFlags
0x180006946  mov     rcx, rax; hHeap
0x180006949  call    cs:__imp_HeapAlloc
0x18000694f  mov     r12, rax
0x180006952  mov     [rsp+0F8h+var_40], rax
0x18000695a  test    rax, rax
0x18000695d  jnz     short loc_180006975
0x18000695f  mov     eax, 8007000Eh
0x180006964  mov     ebx, eax
0x180006966  mov     dword ptr [rsp+0F8h+lpcSubKeys], eax
0x18000696a  mov     r9d, 169h
0x180006970  jmp     loc_1800068D3
0x180006975  mov     r14d, edi
0x180006978  mov     [rsp+0F8h+var_98], edi
0x18000697c  mov     ebx, edi
0x18000697e  shl     rsi, 20h
0x180006982  add     rsi, [rsp+0F8h+var_80]
0x180006987  mov     rax, 0E5109EC205D7BEA7h
0x180006991  mul     rsi
0x180006994  shr     rdx, 1Dh
0x180006998  mov     eax, edx
0x18000699a  mov     [rsp+0F8h+var_48], rax
0x1800069a2  mov     esi, edi
0x1800069a4  mov     [rsp+0F8h+var_88], esi
0x1800069a8  cmp     esi, [rsp+0F8h+arg_18]
0x1800069af  jnb     loc_180006C15
0x1800069b5  lea     rax, [rsp+0F8h+ftLastWriteTime]
0x1800069bd  mov     [rsp+0F8h+lpcValues], rax; lpftLastWriteTime
0x1800069c2  mov     [rsp+0F8h+lpcbMaxClassLen], rdi; lpcchClass
0x1800069c7  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rdi; lpClass
0x1800069cc  mov     [rsp+0F8h+lpcSubKeys], rdi; lpReserved
0x1800069d1  lea     r9, [rsp+0F8h+cchName]; lpcchName
0x1800069d9  mov     r8, r12; lpName
0x1800069dc  mov     edx, esi; dwIndex
0x1800069de  mov     rcx, r15; hKey
0x1800069e1  call    cs:__imp_RegEnumKeyExW
0x1800069e7  cmp     eax, 103h
0x1800069ec  jz      loc_180006C15
0x1800069f2  test    eax, eax
0x1800069f4  jz      short loc_180006A29
0x1800069f6  jg      short loc_1800069FC
0x1800069f8  mov     ebx, eax
0x1800069fa  jmp     short loc_180006A05
0x1800069fc  movzx   ebx, ax
0x1800069ff  or      ebx, 80070000h
0x180006a05  mov     r9d, 177h
0x180006a0b  mov     dword ptr [rsp+0F8h+lpcSubKeys], ebx
0x180006a0f  lea     r8, aThrottlerThrot; "Throttler::ThrottleAnyIdInvocations"
0x180006a16  lea     rdx, aThrottleErrorS_0; "THROTTLE ERROR: %s:%d - hr = 0x%08X\n"
0x180006a1d  xor     ecx, ecx; Level
0x180006a1f  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180006a24  jmp     loc_180006C54
0x180006a29  mov     ecx, [rsp+0F8h+ftLastWriteTime.dwHighDateTime]
0x180006a30  shl     rcx, 20h
0x180006a34  mov     eax, [rsp+0F8h+ftLastWriteTime.dwLowDateTime]
0x180006a3b  add     rcx, rax
0x180006a3e  mov     rax, 0E5109EC205D7BEA7h
0x180006a48  mul     rcx
0x180006a4b  shr     rdx, 1Dh
0x180006a4f  mov     eax, edx
0x180006a51  mov     rcx, [rsp+0F8h+var_48]
0x180006a59  sub     rcx, rax
0x180006a5c  mov     rax, [rsp+0F8h+arg_0]
0x180006a64  mov     eax, [rax+10h]
0x180006a67  cmp     rcx, rax
0x180006a6a  jbe     loc_180006B78
0x180006a70  mov     ebx, [rsp+0F8h+cchName]
0x180006a77  inc     ebx
0x180006a79  add     rbx, rbx
0x180006a7c  call    cs:__imp_GetProcessHeap
0x180006a82  mov     r8, rbx; dwBytes
0x180006a85  xor     edx, edx; dwFlags
0x180006a87  mov     rcx, rax; hHeap
0x180006a8a  call    cs:__imp_HeapAlloc
0x180006a90  mov     rdx, rax
0x180006a93  mov     [rsp+0F8h+var_80], rax
0x180006a98  test    rax, rax
0x180006a9b  jnz     short loc_180006AB3
0x180006a9d  mov     eax, 8007000Eh
0x180006aa2  mov     ebx, eax
0x180006aa4  mov     dword ptr [rsp+0F8h+lpcSubKeys], eax
0x180006aa8  mov     r9d, 17Eh
0x180006aae  jmp     loc_180006A0F
0x180006ab3  mov     eax, [rsp+0F8h+cchName]
0x180006aba  add     eax, 1
0x180006abd  mov     ecx, eax
0x180006abf  jz      short loc_180006B38
0x180006ac1  cmp     rcx, 7FFFFFFFh
0x180006ac8  ja      short loc_180006B41
0x180006aca  mov     eax, 7FFFFFFEh
0x180006acf  mov     r8, r12
0x180006ad2  test    rax, rax
0x180006ad5  jz      short loc_180006AF6
0x180006ad7  movzx   r9d, word ptr [r8]
0x180006adb  test    r9w, r9w
0x180006adf  jz      short loc_180006AF6
0x180006ae1  add     r8, 2
0x180006ae5  mov     [rdx], r9w
0x180006ae9  add     rdx, 2
0x180006aed  dec     rax
0x180006af0  sub     rcx, 1
0x180006af4  jnz     short loc_180006AD2
0x180006af6  lea     rax, [rdx-2]
0x180006afa  test    rcx, rcx
0x180006afd  cmovnz  rax, rdx
0x180006b01  mov     [rax], di
0x180006b04  neg     rcx
0x180006b07  sbb     ebx, ebx
0x180006b09  not     ebx
0x180006b0b  and     ebx, 8007007Ah
0x180006b11  mov     [rsp+0F8h+var_78], ebx
0x180006b18  test    ebx, ebx
0x180006b1a  js      loc_180006CF2
0x180006b20  lea     rdx, [rsp+0F8h+var_80]
0x180006b25  lea     rcx, [rsp+0F8h+var_60]
0x180006b2d  call    ?push_back@?$vector@PEAGV?$allocator@PEAG@std@@@std@@QEAAXAEBQEAG@Z; std::vector<ushort *>::push_back(ushort * const &)
0x180006b32  nop
0x180006b33  jmp     loc_180006CF2
0x180006b38  mov     ebx, 80070057h
0x180006b3d  test    eax, eax
0x180006b3f  jz      short loc_180006B11
0x180006b41  mov     [rdx], di
0x180006b44  mov     ebx, 80070057h
0x180006b49  jmp     loc_180006CF2
0x180006b4e  xor     edi, edi
0x180006b50  mov     r15, [rsp+0F8h+arg_8]
0x180006b58  mov     r14d, [rsp+0F8h+var_98]
0x180006b5d  mov     r12, [rsp+0F8h+var_40]
0x180006b65  mov     ebx, [rsp+0F8h+var_78]
0x180006b6c  mov     r13d, edi
0x180006b6f  mov     esi, [rsp+0F8h+var_88]
0x180006b73  jmp     loc_180006CF2
0x180006b78  lea     rax, [rsp+0F8h+phkResult]
0x180006b7d  mov     [rsp+0F8h+lpcSubKeys], rax; phkResult
0x180006b82  mov     r9d, 20019h; samDesired
0x180006b88  xor     r8d, r8d; ulOptions
0x180006b8b  mov     rdx, r12; lpSubKey
0x180006b8e  mov     rcx, r15; hKey
0x180006b91  call    cs:__imp_RegOpenKeyExW
0x180006b97  mov     ebx, eax
0x180006b99  test    eax, eax
0x180006b9b  jz      short loc_180006BB3
0x180006b9d  jle     short loc_180006BA8
0x180006b9f  movzx   ebx, ax
0x180006ba2  or      ebx, 80070000h
0x180006ba8  mov     r9d, 194h
0x180006bae  jmp     loc_180006A0B
0x180006bb3  mov     [rsp+0F8h+var_98], edi
0x180006bb7  lea     r8, [rsp+0F8h+var_98]; unsigned int *
0x180006bbc  mov     rdx, [rsp+0F8h+phkResult]; HKEY
0x180006bc1  mov     rcx, [rsp+0F8h+arg_0]; this
0x180006bc9  call    ?CountRecentAndCleanOldOccurs@Throttler@@AEAAJPEAUHKEY__@@PEAK@Z; Throttler::CountRecentAndCleanOldOccurs(HKEY__ *,ulong *)
0x180006bce  mov     ebx, eax
0x180006bd0  test    eax, eax
0x180006bd2  jns     short loc_180006BE3
0x180006bd4  mov     dword ptr [rsp+0F8h+lpcSubKeys], eax
0x180006bd8  mov     r9d, 198h
0x180006bde  jmp     loc_180006A0F
0x180006be3  mov     rcx, [rsp+0F8h+phkResult]; hKey
0x180006be8  test    rcx, rcx
0x180006beb  jz      short loc_180006BF8
0x180006bed  call    cs:__imp_RegCloseKey
0x180006bf3  mov     [rsp+0F8h+phkResult], rdi
0x180006bf8  add     r14d, [rsp+0F8h+var_98]
0x180006bfd  mov     rax, [rsp+0F8h+arg_0]
0x180006c05  cmp     r14d, [rax+0Ch]
0x180006c09  jb      loc_180006CED
0x180006c0f  mov     r13d, 2
0x180006c15  mov     rsi, [rsp+0F8h+var_58]
0x180006c1d  sub     rsi, [rsp+0F8h+var_60]
0x180006c25  sar     rsi, 3
0x180006c29  mov     r14, rdi
0x180006c2c  test    rsi, rsi
0x180006c2f  jz      short loc_180006C54
0x180006c31  xor     r9d, r9d; Reserved
0x180006c34  xor     r8d, r8d; samDesired
0x180006c37  mov     rdx, [rsp+0F8h+var_60]
0x180006c3f  mov     rdx, [rdx+r14*8]; lpSubKey
0x180006c43  mov     rcx, r15; hKey
0x180006c46  call    cs:__imp_RegDeleteKeyExW
0x180006c4c  inc     r14
0x180006c4f  cmp     r14, rsi
0x180006c52  jb      short loc_180006C31
0x180006c54  call    cs:__imp_GetProcessHeap
0x180006c5a  mov     rcx, rax; hHeap
0x180006c5d  mov     r8, r12; lpMem
0x180006c60  xor     edx, edx; dwFlags
0x180006c62  call    cs:__imp_HeapFree
0x180006c68  mov     rcx, [rsp+0F8h+phkResult]; hKey
0x180006c6d  test    rcx, rcx
0x180006c70  jz      short loc_180006C7D
0x180006c72  call    cs:__imp_RegCloseKey
0x180006c78  mov     [rsp+0F8h+phkResult], rdi
0x180006c7d  mov     rsi, [rsp+0F8h+var_58]
0x180006c85  sub     rsi, [rsp+0F8h+var_60]
0x180006c8d  sar     rsi, 3
0x180006c91  mov     r14, rdi
0x180006c94  test    rsi, rsi
0x180006c97  jz      short loc_180006CCA
0x180006c99  mov     r15, [rsp+0F8h+var_60]
0x180006ca1  mov     r12, [r15+r14*8]
0x180006ca5  test    r12, r12
0x180006ca8  jz      short loc_180006CC2
0x180006caa  call    cs:__imp_GetProcessHeap
0x180006cb0  mov     r8, r12; lpMem
0x180006cb3  xor     edx, edx; dwFlags
0x180006cb5  mov     rcx, rax; hHeap
0x180006cb8  call    cs:__imp_HeapFree
0x180006cbe  mov     [r15+r14*8], rdi
0x180006cc2  inc     r14
0x180006cc5  cmp     r14, rsi
0x180006cc8  jb      short loc_180006C99
0x180006cca  mov     eax, 4
0x180006ccf  test    ebx, ebx
0x180006cd1  cmovs   r13d, eax
0x180006cd5  mov     rcx, [rsp+0F8h+var_60]
0x180006cdd  test    rcx, rcx
0x180006ce0  jz      short loc_180006CE8
0x180006ce2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006ce8  mov     eax, r13d
0x180006ceb  jmp     short loc_180006CFB
0x180006ced  mov     [rsp+0F8h+var_98], r14d
0x180006cf2  inc     esi
0x180006cf4  jmp     loc_1800069A4
0x180006cf9  xor     eax, eax
0x180006cfb  add     rsp, 0C0h
0x180006d02  pop     r15
0x180006d04  pop     r14
0x180006d06  pop     r13
0x180006d08  pop     r12
0x180006d0a  pop     rdi
0x180006d0b  pop     rsi
0x180006d0c  pop     rbx
0x180006d0d  retn
```
