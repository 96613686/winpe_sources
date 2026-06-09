# WindowsPerformanceRecorder::EnumerateManifestProviders(_LIST_ENTRY *,ulong *)

- ea: `0x180027480`
- end: `0x180027849`
- name: `?EnumerateManifestProviders@WindowsPerformanceRecorder@@YAKPEAU_LIST_ENTRY@@PEAK@Z`
- size: `969`
- prototype: `unsigned int __fastcall(WindowsPerformanceRecorder *__hidden this, struct _LIST_ENTRY *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800147fc`
- `0x18002711c`

## callees

- `0x180027480`
- `0x18004ece0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002768b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800276fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800277c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027830`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002768b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800276fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800277c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027830`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800277d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002783e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800277d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002783e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002769d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027711`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002769d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027711`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002750b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002762a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002750b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002762a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027668`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800276d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027668`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800276d0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800275fe`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800275fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800276f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027785`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027797`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800277ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800277db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027825`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800276f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027785`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027797`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800277ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800277db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027825`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180027551`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180027551`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180027739`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180027739`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::EnumerateManifestProviders(
        WindowsPerformanceRecorder *this,
        struct _LIST_ENTRY *a2,
        unsigned int *a3)
{
  BYTE *v5; // rdi
  unsigned int InfoKeyW; // ebx
  DWORD v8; // eax
  int v9; // r12d
  DWORD i; // r14d
  LSTATUS v11; // eax
  HKEY v12; // rsi
  __int64 v13; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v15; // rax
  GUID *v16; // rax
  GUID *v17; // rbx
  DWORD v18; // ecx
  WindowsPerformanceRecorder **v19; // rax
  HANDLE v20; // rax
  HANDLE v21; // rax
  HKEY phkResult; // [rsp+68h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-98h] BYREF
  DWORD Type; // [rsp+74h] [rbp-94h] BYREF
  DWORD cSubKeys[2]; // [rsp+78h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+88h] [rbp-80h] BYREF

  cSubKeys[1] = 260;
  hKey = 0;
  phkResult = 0;
  cSubKeys[0] = 0;
  if ( !this || !a2 )
    return 87;
  v5 = 0;
  InfoKeyW = RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT\\Publishers",
               0,
               0x20119u,
               &hKey);
  if ( !InfoKeyW )
  {
    InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( !InfoKeyW )
    {
      v8 = cSubKeys[0];
      v9 = 0;
      if ( cSubKeys[0] )
      {
        for ( i = 0; i < v8; ++i )
        {
          v11 = RegEnumKeyExW(hKey, i, Name, &cSubKeys[1], 0, 0, 0, 0);
          InfoKeyW = v11;
          if ( v11 )
          {
            if ( v11 != 259 )
              goto LABEL_5;
            InfoKeyW = 0;
            break;
          }
          InfoKeyW = RegOpenKeyExW(hKey, Name, 0, 0x20119u, &phkResult);
          if ( InfoKeyW )
            goto LABEL_5;
          v12 = phkResult;
          cbData = 0;
          Type = 0;
          InfoKeyW = RegQueryValueExW(phkResult, &LocaleName, 0, &Type, 0, &cbData);
          if ( InfoKeyW )
          {
            RegCloseKey(phkResult);
            phkResult = 0;
          }
          else if ( Type - 1 > 1 )
          {
            RegCloseKey(phkResult);
            phkResult = 0;
            InfoKeyW = 13;
          }
          else
          {
            v13 = cbData;
            ProcessHeap = GetProcessHeap();
            v5 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v13 + 2);
            if ( v5 )
            {
              InfoKeyW = RegQueryValueExW(v12, &LocaleName, 0, &Type, v5, &cbData);
              if ( InfoKeyW )
              {
                v20 = GetProcessHeap();
                HeapFree(v20, 0, v5);
                RegCloseKey(phkResult);
                v5 = 0;
                phkResult = 0;
              }
              else
              {
                *(_WORD *)&v5[2 * ((unsigned __int64)cbData >> 1)] = 0;
                RegCloseKey(phkResult);
                phkResult = 0;
                v15 = GetProcessHeap();
                v16 = (GUID *)HeapAlloc(v15, 8u, 0x30u);
                v17 = v16;
                if ( !v16 )
                {
                  InfoKeyW = 0;
                  goto LABEL_5;
                }
                v18 = cbData + 2;
                *(_QWORD *)&v16[2].Data1 = v5;
                *(_DWORD *)v16[2].Data4 = v18;
                if ( IIDFromString(Name, v16 + 1) < 0 )
                  v17[1] = (GUID)xmmword_18009C718;
                v5 = 0;
                *(_DWORD *)&v17[2].Data4[4] = 0;
                v19 = (WindowsPerformanceRecorder **)*((_QWORD *)this + 1);
                if ( *v19 != this )
                  __fastfail(3u);
                *(_QWORD *)&v17->Data1 = this;
                ++v9;
                *(_QWORD *)v17->Data4 = v19;
                *v19 = (WindowsPerformanceRecorder *)v17;
                *((_QWORD *)this + 1) = v17;
                InfoKeyW = 0;
              }
            }
            else
            {
              RegCloseKey(phkResult);
              v5 = 0;
              InfoKeyW = 8;
              phkResult = 0;
            }
          }
          v8 = cSubKeys[0];
          cSubKeys[1] = 260;
        }
      }
      else
      {
        InfoKeyW = 1168;
      }
      LODWORD(a2->Flink) = v9;
    }
  }
LABEL_5:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v5);
  }
  return InfoKeyW;
}

```

## disassembly

```asm
0x180027480  mov     r11, rsp
0x180027483  push    rbp
0x180027484  push    rsi
0x180027485  push    r13
0x180027487  push    r15
0x180027489  lea     rbp, [r11-1D8h]
0x180027490  sub     rsp, 2B8h
0x180027497  mov     rax, cs:__security_cookie
0x18002749e  xor     rax, rsp
0x1800274a1  mov     [rbp+1D0h+var_40], rax
0x1800274a8  xor     esi, esi
0x1800274aa  mov     [rsp+2D0h+cSubKeys+4], 104h
0x1800274b2  mov     [rsp+2D0h+hKey], rsi
0x1800274b7  mov     r13, rdx
0x1800274ba  mov     [rsp+2D0h+var_270], rsi
0x1800274bf  mov     r15, rcx
0x1800274c2  mov     [rsp+2D0h+cSubKeys], esi
0x1800274c6  test    rcx, rcx
0x1800274c9  jz      loc_1800275B3
0x1800274cf  test    rdx, rdx
0x1800274d2  jz      loc_1800275B3
0x1800274d8  mov     [r11+18h], rbx
0x1800274dc  lea     rax, [rsp+2D0h+hKey]
0x1800274e1  mov     [r11-28h], rdi
0x1800274e5  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800274ec  mov     [r11-30h], r12
0x1800274f0  mov     r9d, 20119h; samDesired
0x1800274f6  xor     r8d, r8d; ulOptions
0x1800274f9  mov     [r11-38h], r14
0x1800274fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027504  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180027509  mov     edi, esi
0x18002750b  call    cs:__imp_RegOpenKeyExW
0x180027511  mov     ebx, eax
0x180027513  test    eax, eax
0x180027515  jnz     short loc_18002755D
0x180027517  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18002751c  lea     rax, [rsp+2D0h+cSubKeys]
0x180027521  mov     [rsp+2D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180027526  xor     r9d, r9d; lpReserved
0x180027529  mov     [rsp+2D0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18002752e  xor     r8d, r8d; lpcchClass
0x180027531  mov     [rsp+2D0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180027536  xor     edx, edx; lpClass
0x180027538  mov     [rsp+2D0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18002753d  mov     [rsp+2D0h+lpcValues], rsi; lpcValues
0x180027542  mov     [rsp+2D0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180027547  mov     [rsp+2D0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x18002754c  mov     [rsp+2D0h+phkResult], rax; lpcSubKeys
0x180027551  call    cs:__imp_RegQueryInfoKeyW
0x180027557  mov     ebx, eax
0x180027559  test    eax, eax
0x18002755b  jz      short loc_1800275BA
0x18002755d  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180027562  test    rcx, rcx
0x180027565  jnz     loc_180027825
0x18002756b  test    rdi, rdi
0x18002756e  jnz     loc_180027830
0x180027574  mov     r12, [rsp+2D0h+var_28]
0x18002757c  mov     eax, ebx
0x18002757e  mov     rbx, [rsp+2D0h+arg_10]
0x180027586  mov     r14, [rsp+2D0h+var_30]
0x18002758e  mov     rdi, [rsp+2B0h]
0x180027596  mov     rcx, [rbp+1D0h+var_40]
0x18002759d  xor     rcx, rsp; StackCookie
0x1800275a0  call    __security_check_cookie
0x1800275a5  add     rsp, 2B8h
0x1800275ac  pop     r15
0x1800275ae  pop     r13
0x1800275b0  pop     rsi
0x1800275b1  pop     rbp
0x1800275b2  retn
0x1800275b3  mov     eax, 57h ; 'W'
0x1800275b8  jmp     short loc_180027596
0x1800275ba  mov     eax, [rsp+2D0h+cSubKeys]
0x1800275be  mov     r12d, edi
0x1800275c1  test    eax, eax
0x1800275c3  jz      loc_18002781E
0x1800275c9  mov     r14d, edi
0x1800275cc  nop     dword ptr [rax+00h]
0x1800275d0  cmp     r14d, eax
0x1800275d3  jnb     loc_180027815
0x1800275d9  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800275de  lea     r9, [rsp+2D0h+cSubKeys+4]; lpcchName
0x1800275e3  mov     [rsp+2D0h+lpcValues], rdi; lpftLastWriteTime
0x1800275e8  lea     r8, [rbp+1D0h+Name]; lpName
0x1800275ec  mov     [rsp+2D0h+lpcbMaxClassLen], rdi; lpcchClass
0x1800275f1  mov     edx, r14d; dwIndex
0x1800275f4  mov     [rsp+2D0h+lpcbMaxSubKeyLen], rdi; lpClass
0x1800275f9  mov     [rsp+2D0h+phkResult], rdi; lpReserved
0x1800275fe  call    cs:__imp_RegEnumKeyExW
0x180027604  mov     ebx, eax
0x180027606  test    eax, eax
0x180027608  jnz     loc_180027808
0x18002760e  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180027613  lea     rax, [rsp+2D0h+var_270]
0x180027618  mov     r9d, 20119h; samDesired
0x18002761e  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180027623  xor     r8d, r8d; ulOptions
0x180027626  lea     rdx, [rbp+1D0h+Name]; lpSubKey
0x18002762a  call    cs:__imp_RegOpenKeyExW
0x180027630  mov     ebx, eax
0x180027632  test    eax, eax
0x180027634  jnz     loc_18002755D
0x18002763a  mov     rsi, [rsp+2D0h+var_270]
0x18002763f  lea     rax, [rsp+2D0h+cbData]
0x180027644  mov     [rsp+2D0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180027649  lea     r9, [rsp+2D0h+Type]; lpType
0x18002764e  mov     rcx, rsi; hKey
0x180027651  mov     [rsp+2D0h+phkResult], rdi; lpData
0x180027656  xor     r8d, r8d; lpReserved
0x180027659  mov     [rsp+2D0h+cbData], edi
0x18002765d  lea     rdx, LocaleName; lpValueName
0x180027664  mov     [rsp+2D0h+Type], edi
0x180027668  call    cs:__imp_RegQueryValueExW
0x18002766e  mov     ebx, eax
0x180027670  test    eax, eax
0x180027672  jnz     loc_180027780
0x180027678  mov     eax, [rsp+2D0h+Type]
0x18002767c  dec     eax
0x18002767e  cmp     eax, 1
0x180027681  ja      loc_180027792
0x180027687  mov     ebx, [rsp+2D0h+cbData]
0x18002768b  call    cs:__imp_GetProcessHeap
0x180027691  lea     r8, [rbx+2]; dwBytes
0x180027695  mov     edx, 8; dwFlags
0x18002769a  mov     rcx, rax; hHeap
0x18002769d  call    cs:__imp_HeapAlloc
0x1800276a3  mov     rdi, rax
0x1800276a6  test    rax, rax
0x1800276a9  jz      loc_1800277A9
0x1800276af  lea     rax, [rsp+2D0h+cbData]
0x1800276b4  xor     r8d, r8d; lpReserved
0x1800276b7  mov     [rsp+2D0h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800276bc  lea     r9, [rsp+2D0h+Type]; lpType
0x1800276c1  lea     rdx, LocaleName; lpValueName
0x1800276c8  mov     [rsp+2D0h+phkResult], rdi; lpData
0x1800276cd  mov     rcx, rsi; hKey
0x1800276d0  call    cs:__imp_RegQueryValueExW
0x1800276d6  mov     ebx, eax
0x1800276d8  test    eax, eax
0x1800276da  jnz     loc_1800277C2
0x1800276e0  mov     ecx, [rsp+2D0h+cbData]
0x1800276e4  xor     esi, esi
0x1800276e6  shr     rcx, 1
0x1800276e9  mov     [rdi+rcx*2], si
0x1800276ed  mov     rcx, [rsp+2D0h+var_270]; hKey
0x1800276f2  call    cs:__imp_RegCloseKey
0x1800276f8  mov     [rsp+2D0h+var_270], rsi
0x1800276fd  call    cs:__imp_GetProcessHeap
0x180027703  mov     edx, 8; dwFlags
0x180027708  mov     r8d, 30h ; '0'; dwBytes
0x18002770e  mov     rcx, rax; hHeap
0x180027711  call    cs:__imp_HeapAlloc
0x180027717  mov     rbx, rax
0x18002771a  test    rax, rax
0x18002771d  jz      loc_180027801
0x180027723  mov     ecx, [rsp+2D0h+cbData]
0x180027727  lea     rdx, [rax+10h]; lpiid
0x18002772b  add     ecx, 2
0x18002772e  mov     [rax+20h], rdi
0x180027732  mov     [rax+28h], ecx
0x180027735  lea     rcx, [rbp+1D0h+Name]; lpsz
0x180027739  call    cs:__imp_IIDFromString
0x18002773f  test    eax, eax
0x180027741  js      loc_1800277EA
0x180027747  xor     edi, edi
0x180027749  mov     [rbx+2Ch], edi
0x18002774c  mov     rax, [r15+8]
0x180027750  cmp     [rax], r15
0x180027753  jnz     loc_1800277FA
0x180027759  mov     [rbx], r15
0x18002775c  inc     r12d
0x18002775f  mov     [rbx+8], rax
0x180027763  mov     [rax], rbx
0x180027766  mov     [r15+8], rbx
0x18002776a  mov     ebx, edi
0x18002776c  mov     eax, [rsp+2D0h+cSubKeys]
0x180027770  inc     r14d
0x180027773  mov     [rsp+2D0h+cSubKeys+4], 104h
0x18002777b  jmp     loc_1800275D0
0x180027780  mov     rcx, [rsp+2D0h+var_270]; hKey
0x180027785  call    cs:__imp_RegCloseKey
0x18002778b  mov     [rsp+2D0h+var_270], rdi
0x180027790  jmp     short loc_18002776C
0x180027792  mov     rcx, [rsp+2D0h+var_270]; hKey
0x180027797  call    cs:__imp_RegCloseKey
0x18002779d  mov     [rsp+2D0h+var_270], rdi
0x1800277a2  mov     ebx, 0Dh
0x1800277a7  jmp     short loc_18002776C
0x1800277a9  mov     rcx, [rsp+2D0h+var_270]; hKey
0x1800277ae  call    cs:__imp_RegCloseKey
0x1800277b4  xor     edi, edi
0x1800277b6  mov     ebx, 8
0x1800277bb  mov     [rsp+2D0h+var_270], rdi
0x1800277c0  jmp     short loc_18002776C
0x1800277c2  call    cs:__imp_GetProcessHeap
0x1800277c8  mov     r8, rdi; lpMem
0x1800277cb  xor     edx, edx; dwFlags
0x1800277cd  mov     rcx, rax; hHeap
0x1800277d0  call    cs:__imp_HeapFree
0x1800277d6  mov     rcx, [rsp+2D0h+var_270]; hKey
0x1800277db  call    cs:__imp_RegCloseKey
0x1800277e1  xor     edi, edi
0x1800277e3  mov     [rsp+2D0h+var_270], rdi
0x1800277e8  jmp     short loc_18002776C
0x1800277ea  movups  xmm0, cs:xmmword_18009C718
0x1800277f1  movups  xmmword ptr [rbx+10h], xmm0
0x1800277f5  jmp     loc_180027747
0x1800277fa  mov     ecx, 3
0x1800277ff  int     29h; Win8: RtlFailFast(ecx)
0x180027801  mov     ebx, esi
0x180027803  jmp     loc_18002755D
0x180027808  cmp     eax, 103h
0x18002780d  jnz     loc_18002755D
0x180027813  mov     ebx, edi
0x180027815  mov     [r13+0], r12d
0x180027819  jmp     loc_18002755D
0x18002781e  mov     ebx, 490h
0x180027823  jmp     short loc_180027815
0x180027825  call    cs:__imp_RegCloseKey
0x18002782b  jmp     loc_18002756B
0x180027830  call    cs:__imp_GetProcessHeap
0x180027836  mov     r8, rdi; lpMem
0x180027839  xor     edx, edx; dwFlags
0x18002783b  mov     rcx, rax; hHeap
0x18002783e  call    cs:__imp_HeapFree
0x180027844  jmp     loc_180027574
```
