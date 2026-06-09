# Throttler::CountRecentAndCleanOldOccurs(HKEY__ *,ulong *)

- ea: `0x180005ee4`
- end: `0x18000636a`
- name: `?CountRecentAndCleanOldOccurs@Throttler@@AEAAJPEAUHKEY__@@PEAK@Z`
- size: `1158`
- prototype: `int(Throttler *__hidden this, HKEY, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180006530`
- `0x180006830`

## callees

- `0x180002590`
- `0x180005ee4`
- `0x180006370`
- `0x180006de0`
- `0x180007040`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000614e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006312`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000614e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006312`
- `KERNEL32!HeapFree` at `0x180006207`
- `KERNEL32!HeapFree` at `0x1800062f8`
- `KERNEL32!HeapFree` at `0x180006207`
- `KERNEL32!HeapFree` at `0x1800062f8`
- `KERNEL32!HeapAlloc` at `0x180006196`
- `KERNEL32!HeapAlloc` at `0x180006196`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180006030`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180006030`
- `KERNEL32!GetProcessHeap` at `0x180006188`
- `KERNEL32!GetProcessHeap` at `0x1800061f9`
- `KERNEL32!GetProcessHeap` at `0x1800062ea`
- `KERNEL32!GetProcessHeap` at `0x180006188`
- `KERNEL32!GetProcessHeap` at `0x1800061f9`
- `KERNEL32!GetProcessHeap` at `0x1800062ea`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005f9e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005f9e`
- `ADVAPI32!RegEnumValueW` at `0x1800060fa`
- `ADVAPI32!RegEnumValueW` at `0x1800060fa`
- `ADVAPI32!RegDeleteValueW` at `0x1800062c4`
- `ADVAPI32!RegDeleteValueW` at `0x1800062c4`

## string_xrefs

- `0x180006329`: `THROTTLE CONFIGURATION ERROR - unexpected registry value  %s:%d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Throttler::CountRecentAndCleanOldOccurs(Throttler *this, HKEY a2, unsigned int *a3)
{
  unsigned int *v3; // r14
  HKEY v4; // r12
  LSTATUS v6; // eax
  signed int v7; // ebx
  __int64 v8; // rbx
  __int64 v9; // r13
  unsigned int *v10; // r15
  DWORD i; // esi
  LSTATUS v13; // eax
  SIZE_T v14; // rbx
  HANDLE ProcessHeap; // rax
  _WORD *v16; // rax
  void *v17; // rbx
  __int64 v18; // rsi
  LPCWSTR *v19; // rbx
  unsigned __int64 v20; // rcx
  HANDLE v21; // rax
  __int64 v22; // rax
  WCHAR *v23; // r8
  WCHAR *v24; // rdx
  WCHAR v25; // r9
  WCHAR *v26; // rax
  unsigned __int64 v27; // r14
  unsigned __int64 j; // r15
  unsigned __int64 v29; // rsi
  unsigned __int64 k; // r14
  WCHAR *v31; // r15
  HANDLE v32; // rax
  void *v33; // rbx
  HANDLE v34; // rax
  DWORD cchValueName; // [rsp+60h] [rbp-108h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+64h] [rbp-104h] BYREF
  DWORD cbMaxValueLen; // [rsp+68h] [rbp-100h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-FCh] BYREF
  DWORD cbData; // [rsp+70h] [rbp-F8h] BYREF
  DWORD Type; // [rsp+74h] [rbp-F4h] BYREF
  DWORD v41; // [rsp+78h] [rbp-F0h]
  struct _FILETIME lpftLastWriteTime; // [rsp+80h] [rbp-E8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-E0h] BYREF
  BYTE Data[8]; // [rsp+90h] [rbp-D8h] BYREF
  _WORD *v45; // [rsp+98h] [rbp-D0h] BYREF
  __int128 v46; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v47; // [rsp+B0h] [rbp-B8h]
  __int64 v48; // [rsp+B8h] [rbp-B0h]
  HKEY v49; // [rsp+C0h] [rbp-A8h]
  unsigned int *v50; // [rsp+C8h] [rbp-A0h]
  unsigned int *v51; // [rsp+D0h] [rbp-98h]
  WCHAR ValueName[40]; // [rsp+E0h] [rbp-88h] BYREF

  v3 = a3;
  v4 = a2;
  v49 = a2;
  v50 = a3;
  *a3 = 0;
  v46 = 0;
  v47 = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  lpftLastWriteTime = 0;
  v6 = RegQueryInfoKeyW(a2, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, &lpftLastWriteTime);
  v7 = v6;
  if ( v6 )
  {
    DebugPrint(0, "THROTTLE ERROR: %s:%d - ret = %d\n", "Throttler::CountRecentAndCleanOldOccurs", 472, v6);
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
    return (unsigned int)v7;
  }
  if ( cbMaxValueNameLen > 0x28 || cbMaxValueLen > 8 )
  {
    DebugPrint(
      0,
      "THROTTLE CONFIGURATION ERROR - unexpected registry value  %s:%d\n",
      "Throttler::CountRecentAndCleanOldOccurs",
      478);
    return 2147549183LL;
  }
  v8 = (unsigned int)((lpftLastWriteTime.dwLowDateTime + ((unsigned __int64)lpftLastWriteTime.dwHighDateTime << 32))
                    / 0x23C34600);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v9 = (unsigned int)((SystemTimeAsFileTime.dwLowDateTime + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32))
                    / 0x23C34600);
  v48 = v9;
  v10 = (unsigned int *)((char *)this + 16);
  if ( v9 - v8 > (unsigned __int64)*v10 )
  {
    Throttler::DeleteAllOccursForThrottleId((Throttler *)(v9 - v8), v4);
    *v3 = 0;
    return 0;
  }
  v51 = v10;
  cchValueName = 0;
  cbData = 0;
  Type = 0;
  *(_QWORD *)Data = 0;
  for ( i = 0; ; ++i )
  {
    v41 = i;
    if ( i >= cValues )
      break;
    cchValueName = 40;
    cbData = 8;
    v13 = RegEnumValueW(v4, i, ValueName, &cchValueName, 0, &Type, Data, &cbData);
    v7 = v13;
    if ( v13 == 259 )
      break;
    if ( v13 )
    {
      DebugPrint(0, "THROTTLE ERROR: %s:%d - ret = %d\n", "Throttler::CountRecentAndCleanOldOccurs", 521, v13);
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      if ( (_QWORD)v46 )
        operator delete((void *)v46);
      return (unsigned int)v7;
    }
    if ( Type == 11 )
    {
      if ( v9 - *(_QWORD *)Data <= (unsigned __int64)*v10 )
      {
        ++*v3;
        continue;
      }
      v14 = 2LL * (cchValueName + 1);
      ProcessHeap = GetProcessHeap();
      v16 = HeapAlloc(ProcessHeap, 0, v14);
      v17 = v16;
      v45 = v16;
      if ( !v16 )
      {
        DebugPrint(
          0,
          "THROTTLE ERROR: %s:%d - hr = 0x%08X\n",
          "Throttler::CountRecentAndCleanOldOccurs",
          535,
          -2147024882);
        v18 = *((_QWORD *)&v46 + 1);
        v19 = (LPCWSTR *)v46;
        goto LABEL_37;
      }
      v20 = cchValueName + 1;
      if ( cchValueName == -1 )
        goto LABEL_25;
      if ( v20 > 0x7FFFFFFF )
      {
        *v16 = 0;
LABEL_25:
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v17);
        continue;
      }
      v22 = 2147483646;
      v23 = ValueName;
      v24 = (WCHAR *)v17;
      do
      {
        if ( !v22 )
          break;
        v25 = *v23;
        if ( !*v23 )
          break;
        ++v23;
        *v24++ = v25;
        --v22;
        --v20;
      }
      while ( v20 );
      v26 = v24 - 1;
      if ( v20 )
        v26 = v24;
      *v26 = 0;
      if ( !v20 )
        goto LABEL_25;
      try
      {
        std::vector<unsigned short *>::push_back(&v46, &v45);
      }
      catch ( exception )
      {
        v33 = v45;
        if ( v45 )
        {
          v34 = GetProcessHeap();
          HeapFree(v34, 0, v33);
        }
        v9 = v48;
        i = v41;
        v4 = v49;
        v3 = v50;
        v10 = v51;
        continue;
      }
    }
  }
  v18 = *((_QWORD *)&v46 + 1);
  v19 = (LPCWSTR *)v46;
  v27 = (__int64)(*((_QWORD *)&v46 + 1) - v46) >> 3;
  for ( j = 0; j < v27; ++j )
    RegDeleteValueW(v4, v19[j]);
LABEL_37:
  v29 = (v18 - (__int64)v19) >> 3;
  for ( k = 0; k < v29; ++k )
  {
    v31 = (WCHAR *)v19[k];
    if ( v31 )
    {
      v32 = GetProcessHeap();
      HeapFree(v32, 0, v31);
      v19[k] = 0;
    }
  }
  if ( v19 )
    operator delete(v19);
  return 0;
}

```

## disassembly

```asm
0x180005ee4  mov     r11, rsp
0x180005ee7  mov     [r11+8], rbx
0x180005eeb  mov     [r11+20h], rsi
0x180005eef  push    rdi
0x180005ef0  push    r12
0x180005ef2  push    r13
0x180005ef4  push    r14
0x180005ef6  push    r15
0x180005ef8  sub     rsp, 140h
0x180005eff  mov     rax, cs:__security_cookie
0x180005f06  xor     rax, rsp
0x180005f09  mov     [rsp+168h+var_38], rax
0x180005f11  mov     r14, r8
0x180005f14  mov     r12, rdx
0x180005f17  mov     r15, rcx
0x180005f1a  mov     [rsp+168h+var_A8], rdx
0x180005f22  mov     [rsp+168h+var_A0], r8
0x180005f2a  xor     edi, edi
0x180005f2c  mov     [r8], edi
0x180005f2f  xorps   xmm0, xmm0
0x180005f32  movdqu  [rsp+168h+var_C8], xmm0
0x180005f3b  mov     [r11-0B8h], rdi
0x180005f42  mov     [rsp+168h+cValues], edi
0x180005f46  mov     [rsp+168h+cbMaxValueNameLen], edi
0x180005f4a  mov     [rsp+168h+cbMaxValueLen], edi
0x180005f4e  mov     [r11-0E8h], rdi
0x180005f55  lea     rax, [r11-0E8h]
0x180005f5c  mov     [rsp+168h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180005f61  mov     [rsp+168h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180005f66  lea     rax, [rsp+168h+cbMaxValueLen]
0x180005f6b  mov     [rsp+168h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180005f70  lea     rax, [rsp+168h+cbMaxValueNameLen]
0x180005f75  mov     [rsp+168h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180005f7a  lea     rax, [rsp+168h+cValues]
0x180005f7f  mov     [rsp+168h+lpcValues], rax; lpcValues
0x180005f84  mov     [rsp+168h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180005f89  mov     [rsp+168h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x180005f8e  mov     [rsp+168h+lpcSubKeys], rdi; lpcSubKeys
0x180005f93  xor     r9d, r9d; lpReserved
0x180005f96  xor     r8d, r8d; lpcchClass
0x180005f99  xor     edx, edx; lpClass
0x180005f9b  mov     rcx, r12; hKey
0x180005f9e  call    cs:__imp_RegQueryInfoKeyW
0x180005fa4  mov     ebx, eax
0x180005fa6  test    eax, eax
0x180005fa8  jz      short loc_180005FDF
0x180005faa  mov     dword ptr [rsp+168h+lpcSubKeys], eax
0x180005fae  mov     r9d, 1D8h
0x180005fb4  lea     r8, aThrottlerCount; "Throttler::CountRecentAndCleanOldOccurs"
0x180005fbb  lea     rdx, aThrottleErrorS; "THROTTLE ERROR: %s:%d - ret = %d\n"
0x180005fc2  xor     ecx, ecx; Level
0x180005fc4  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180005fc9  test    ebx, ebx
0x180005fcb  jle     loc_18000607F
0x180005fd1  movzx   ebx, bx
0x180005fd4  or      ebx, 80070000h
0x180005fda  jmp     loc_18000607F
0x180005fdf  cmp     [rsp+168h+cbMaxValueNameLen], 28h ; '('
0x180005fe4  ja      loc_18000631C
0x180005fea  cmp     [rsp+168h+cbMaxValueLen], 8
0x180005fef  ja      loc_18000631C
0x180005ff5  mov     ecx, [rsp+168h+var_E4]
0x180005ffc  shl     rcx, 20h
0x180006000  mov     eax, [rsp+168h+var_E8]
0x180006007  add     rcx, rax
0x18000600a  mov     rsi, 0E5109EC205D7BEA7h
0x180006014  mov     rax, rsi
0x180006017  mul     rcx
0x18000601a  shr     rdx, 1Dh
0x18000601e  mov     ebx, edx
0x180006020  mov     qword ptr [rsp+168h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x180006028  lea     rcx, [rsp+168h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006030  call    cs:__imp_GetSystemTimeAsFileTime
0x180006036  mov     r8d, [rsp+168h+SystemTimeAsFileTime.dwHighDateTime]
0x18000603e  shl     r8, 20h
0x180006042  mov     ecx, [rsp+168h+SystemTimeAsFileTime.dwLowDateTime]
0x180006049  add     r8, rcx
0x18000604c  mov     rax, rsi
0x18000604f  mul     r8
0x180006052  shr     rdx, 1Dh
0x180006056  mov     r13d, edx
0x180006059  mov     [rsp+168h+var_B0], r13
0x180006061  add     r15, 10h
0x180006065  mov     ecx, edx
0x180006067  sub     rcx, rbx; this
0x18000606a  mov     eax, [r15]
0x18000606d  cmp     rcx, rax
0x180006070  jbe     short loc_180006086
0x180006072  mov     rdx, r12; HKEY
0x180006075  call    ?DeleteAllOccursForThrottleId@Throttler@@AEAAXPEAUHKEY__@@@Z; Throttler::DeleteAllOccursForThrottleId(HKEY__ *)
0x18000607a  mov     [r14], edi
0x18000607d  mov     ebx, edi
0x18000607f  mov     eax, ebx
0x180006081  jmp     loc_18000633D
0x180006086  mov     [rsp+168h+var_98], r15
0x18000608e  mov     [rsp+168h+cchValueName], edi
0x180006092  mov     [rsp+168h+cbData], edi
0x180006096  mov     [rsp+168h+Type], edi
0x18000609a  mov     qword ptr [rsp+168h+Data], rdi
0x1800060a2  mov     esi, edi
0x1800060a4  mov     [rsp+168h+var_F0], esi
0x1800060a8  cmp     esi, [rsp+168h+cValues]
0x1800060ac  jnb     loc_18000629B
0x1800060b2  mov     [rsp+168h+cchValueName], 28h ; '('
0x1800060ba  mov     [rsp+168h+cbData], 8
0x1800060c2  lea     rax, [rsp+168h+cbData]
0x1800060c7  mov     [rsp+168h+lpcValues], rax; lpcbData
0x1800060cc  lea     rax, [rsp+168h+Data]
0x1800060d4  mov     [rsp+168h+lpcbMaxClassLen], rax; lpData
0x1800060d9  lea     rax, [rsp+168h+Type]
0x1800060de  mov     [rsp+168h+lpcbMaxSubKeyLen], rax; lpType
0x1800060e3  mov     [rsp+168h+lpcSubKeys], rdi; lpReserved
0x1800060e8  lea     r9, [rsp+168h+cchValueName]; lpcchValueName
0x1800060ed  lea     r8, [rsp+168h+ValueName]; lpValueName
0x1800060f5  mov     edx, esi; dwIndex
0x1800060f7  mov     rcx, r12; hKey
0x1800060fa  call    cs:__imp_RegEnumValueW
0x180006100  mov     ebx, eax
0x180006102  cmp     eax, 103h
0x180006107  jz      loc_18000629B
0x18000610d  test    eax, eax
0x18000610f  jz      short loc_180006159
0x180006111  mov     dword ptr [rsp+168h+lpcSubKeys], eax
0x180006115  mov     r9d, 209h
0x18000611b  lea     r8, aThrottlerCount; "Throttler::CountRecentAndCleanOldOccurs"
0x180006122  lea     rdx, aThrottleErrorS; "THROTTLE ERROR: %s:%d - ret = %d\n"
0x180006129  xor     ecx, ecx; Level
0x18000612b  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180006130  test    ebx, ebx
0x180006132  jle     short loc_18000613D
0x180006134  movzx   ebx, bx
0x180006137  or      ebx, 80070000h
0x18000613d  mov     rcx, qword ptr [rsp+168h+var_C8]
0x180006145  test    rcx, rcx
0x180006148  jz      loc_18000607F
0x18000614e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006154  jmp     loc_18000607F
0x180006159  cmp     [rsp+168h+Type], 0Bh
0x18000615e  jnz     loc_18000620D
0x180006164  mov     rcx, r13
0x180006167  sub     rcx, qword ptr [rsp+168h+Data]
0x18000616f  mov     eax, [r15]
0x180006172  cmp     rcx, rax
0x180006175  ja      short loc_18000617F
0x180006177  inc     dword ptr [r14]
0x18000617a  jmp     loc_18000620D
0x18000617f  mov     ebx, [rsp+168h+cchValueName]
0x180006183  inc     ebx
0x180006185  add     rbx, rbx
0x180006188  call    cs:__imp_GetProcessHeap
0x18000618e  mov     r8, rbx; dwBytes
0x180006191  xor     edx, edx; dwFlags
0x180006193  mov     rcx, rax; hHeap
0x180006196  call    cs:__imp_HeapAlloc
0x18000619c  mov     rbx, rax
0x18000619f  mov     [rsp+168h+var_D0], rax
0x1800061a7  test    rax, rax
0x1800061aa  jnz     short loc_1800061E4
0x1800061ac  mov     dword ptr [rsp+168h+lpcSubKeys], 8007000Eh
0x1800061b4  mov     r9d, 217h
0x1800061ba  lea     r8, aThrottlerCount; "Throttler::CountRecentAndCleanOldOccurs"
0x1800061c1  lea     rdx, aThrottleErrorS_0; "THROTTLE ERROR: %s:%d - hr = 0x%08X\n"
0x1800061c8  xor     ecx, ecx; Level
0x1800061ca  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x1800061cf  mov     rsi, qword ptr [rsp+168h+var_C8+8]
0x1800061d7  mov     rbx, qword ptr [rsp+168h+var_C8]
0x1800061df  jmp     loc_1800062D2
0x1800061e4  mov     ecx, [rsp+168h+cchValueName]
0x1800061e8  add     ecx, 1
0x1800061eb  jz      short loc_1800061F9
0x1800061ed  cmp     rcx, 7FFFFFFFh
0x1800061f4  jbe     short loc_180006214
0x1800061f6  mov     [rax], di
0x1800061f9  call    cs:__imp_GetProcessHeap
0x1800061ff  mov     r8, rbx; lpMem
0x180006202  xor     edx, edx; dwFlags
0x180006204  mov     rcx, rax; hHeap
0x180006207  call    cs:__imp_HeapFree
0x18000620d  inc     esi
0x18000620f  jmp     loc_1800060A4
0x180006214  mov     eax, 7FFFFFFEh
0x180006219  lea     r8, [rsp+168h+ValueName]
0x180006221  mov     rdx, rbx
0x180006224  test    rax, rax
0x180006227  jz      short loc_180006248
0x180006229  movzx   r9d, word ptr [r8]
0x18000622d  test    r9w, r9w
0x180006231  jz      short loc_180006248
0x180006233  add     r8, 2
0x180006237  mov     [rdx], r9w
0x18000623b  add     rdx, 2
0x18000623f  dec     rax
0x180006242  sub     rcx, 1
0x180006246  jnz     short loc_180006224
0x180006248  lea     rax, [rdx-2]
0x18000624c  test    rcx, rcx
0x18000624f  cmovnz  rax, rdx
0x180006253  mov     [rax], di
0x180006256  jz      short loc_1800061F9
0x180006258  lea     rdx, [rsp+168h+var_D0]
0x180006260  lea     rcx, [rsp+168h+var_C8]
0x180006268  call    ?push_back@?$vector@PEAGV?$allocator@PEAG@std@@@std@@QEAAXAEBQEAG@Z; std::vector<ushort *>::push_back(ushort * const &)
0x18000626d  nop
0x18000626e  jmp     short loc_18000620D
0x180006270  xor     edi, edi
0x180006272  mov     r13, [rsp+168h+var_B0]
0x18000627a  mov     esi, [rsp+168h+var_F0]
0x18000627e  mov     r12, [rsp+168h+var_A8]
0x180006286  mov     r14, [rsp+168h+var_A0]
0x18000628e  mov     r15, [rsp+168h+var_98]
0x180006296  jmp     loc_18000620D
0x18000629b  mov     rsi, qword ptr [rsp+168h+var_C8+8]
0x1800062a3  mov     r14, rsi
0x1800062a6  mov     rbx, qword ptr [rsp+168h+var_C8]
0x1800062ae  sub     r14, rbx
0x1800062b1  sar     r14, 3
0x1800062b5  mov     r15, rdi
0x1800062b8  test    r14, r14
0x1800062bb  jz      short loc_1800062D2
0x1800062bd  mov     rdx, [rbx+r15*8]; lpValueName
0x1800062c1  mov     rcx, r12; hKey
0x1800062c4  call    cs:__imp_RegDeleteValueW
0x1800062ca  inc     r15
0x1800062cd  cmp     r15, r14
0x1800062d0  jb      short loc_1800062BD
0x1800062d2  sub     rsi, rbx
0x1800062d5  sar     rsi, 3
0x1800062d9  mov     r14, rdi
0x1800062dc  test    rsi, rsi
0x1800062df  jz      short loc_18000630A
0x1800062e1  mov     r15, [rbx+r14*8]
0x1800062e5  test    r15, r15
0x1800062e8  jz      short loc_180006302
0x1800062ea  call    cs:__imp_GetProcessHeap
0x1800062f0  mov     r8, r15; lpMem
0x1800062f3  xor     edx, edx; dwFlags
0x1800062f5  mov     rcx, rax; hHeap
0x1800062f8  call    cs:__imp_HeapFree
0x1800062fe  mov     [rbx+r14*8], rdi
0x180006302  inc     r14
0x180006305  cmp     r14, rsi
0x180006308  jb      short loc_1800062E1
0x18000630a  test    rbx, rbx
0x18000630d  jz      short loc_180006318
0x18000630f  mov     rcx, rbx
0x180006312  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006318  xor     eax, eax
0x18000631a  jmp     short loc_18000633D
0x18000631c  mov     r9d, 1DEh
0x180006322  lea     r8, aThrottlerCount; "Throttler::CountRecentAndCleanOldOccurs"
0x180006329  lea     rdx, aThrottleConfig; "THROTTLE CONFIGURATION ERROR - unexpect"...
0x180006330  xor     ecx, ecx; Level
0x180006332  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180006337  nop
0x180006338  mov     eax, 8000FFFFh
0x18000633d  mov     rcx, [rsp+168h+var_38]
0x180006345  xor     rcx, rsp; StackCookie
0x180006348  call    __security_check_cookie
0x18000634d  lea     r11, [rsp+168h+var_28]
0x180006355  mov     rbx, [r11+30h]
0x180006359  mov     rsi, [r11+48h]
0x18000635d  mov     rsp, r11
0x180006360  pop     r15
0x180006362  pop     r14
0x180006364  pop     r13
0x180006366  pop     r12
0x180006368  pop     rdi
0x180006369  retn
```
