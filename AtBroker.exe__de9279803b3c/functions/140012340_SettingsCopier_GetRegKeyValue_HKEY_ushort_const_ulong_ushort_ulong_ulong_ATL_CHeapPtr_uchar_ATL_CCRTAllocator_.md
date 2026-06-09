# SettingsCopier::GetRegKeyValue(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong *,ATL::CHeapPtr<uchar,ATL::CCRTAllocator> &,ulong *)

- ea: `0x140012340`
- end: `0x140012637`
- name: `?GetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBGKPEAGKPEAKAEAV?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@3@Z`
- size: `759`
- prototype: `signed int __fastcall(HKEY hKey, LPCWSTR lpSubKey, DWORD, WCHAR *, DWORD cchValueName, DWORD *, void **, DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config`

## callers

- `0x140011c60`

## callees

- `0x140012340`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140012581`
- `ADVAPI32!RegQueryValueExW` at `0x140012581`
- `ADVAPI32!RegOpenKeyExW` at `0x1400123f5`
- `ADVAPI32!RegOpenKeyExW` at `0x1400123f5`
- `ADVAPI32!RegCloseKey` at `0x14001244d`
- `ADVAPI32!RegCloseKey` at `0x140012523`
- `ADVAPI32!RegCloseKey` at `0x140012550`
- `ADVAPI32!RegCloseKey` at `0x14001258d`
- `ADVAPI32!RegCloseKey` at `0x14001244d`
- `ADVAPI32!RegCloseKey` at `0x140012523`
- `ADVAPI32!RegCloseKey` at `0x140012550`
- `ADVAPI32!RegCloseKey` at `0x14001258d`
- `KERNEL32!WaitForSingleObject` at `0x140012598`
- `KERNEL32!WaitForSingleObject` at `0x140012598`
- `KERNEL32!GetLastError` at `0x1400123bf`
- `KERNEL32!GetLastError` at `0x1400123bf`
- `KERNEL32!CloseHandle` at `0x140012404`
- `KERNEL32!CloseHandle` at `0x140012443`
- `KERNEL32!CloseHandle` at `0x140012519`
- `KERNEL32!CloseHandle` at `0x140012546`
- `KERNEL32!CloseHandle` at `0x1400125a3`
- `KERNEL32!CloseHandle` at `0x140012404`
- `KERNEL32!CloseHandle` at `0x140012443`
- `KERNEL32!CloseHandle` at `0x140012519`
- `KERNEL32!CloseHandle` at `0x140012546`
- `KERNEL32!CloseHandle` at `0x1400125a3`
- `KERNEL32!RegEnumValueW` at `0x14001248e`
- `KERNEL32!RegEnumValueW` at `0x14001250a`
- `KERNEL32!RegEnumValueW` at `0x14001248e`
- `KERNEL32!RegEnumValueW` at `0x14001250a`
- `KERNEL32!RegNotifyChangeKeyValue` at `0x140012434`
- `KERNEL32!RegNotifyChangeKeyValue` at `0x140012434`
- `KERNEL32!CreateEventW` at `0x1400123b1`
- `KERNEL32!CreateEventW` at `0x1400123b1`
- `msvcrt!malloc` at `0x1400124c7`
- `msvcrt!malloc` at `0x1400124c7`
- `msvcrt!free` at `0x14001239e`
- `msvcrt!free` at `0x14001252c`
- `msvcrt!free` at `0x1400125c0`
- `msvcrt!free` at `0x1400125f7`
- `msvcrt!free` at `0x14001239e`
- `msvcrt!free` at `0x14001252c`
- `msvcrt!free` at `0x1400125c0`
- `msvcrt!free` at `0x1400125f7`

## string_xrefs

- `0x14001257a`: `SymbolicLinkValue`

## pseudocode

```c
signed int __fastcall SettingsCopier::GetRegKeyValue(
        HKEY hKey,
        LPCWSTR lpSubKey,
        DWORD a3,
        WCHAR *a4,
        DWORD cchValueName,
        DWORD *a6,
        void **a7,
        DWORD *a8)
{
  DWORD *v8; // r12
  DWORD *v9; // r13
  void **v11; // rsi
  void *v14; // rcx
  HANDLE EventW; // r14
  signed int result; // eax
  LSTATUS v17; // ebx
  LSTATUS v18; // edi
  LSTATUS v19; // eax
  BYTE *lpData; // rax
  DWORD v21; // ebx
  DWORD Type; // [rsp+40h] [rbp-20h] BYREF
  DWORD v23; // [rsp+44h] [rbp-1Ch] BYREF
  DWORD v24; // [rsp+48h] [rbp-18h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+58h] BYREF

  v8 = a6;
  v9 = a8;
  v11 = a7;
  *a4 = 0;
  *v8 = 0;
  *v9 = 0;
  v14 = *v11;
  hKeya = 0;
  cchValueName = 260;
  Type = 0;
  cbData = 0;
  v23 = 0;
  v24 = 0;
  free(v14);
  *v11 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    v17 = RegOpenKeyExW(hKey, lpSubKey, 8u, 0x20019u, &hKeya);
    if ( v17 )
    {
      CloseHandle(EventW);
      goto LABEL_6;
    }
    v18 = 1;
    v17 = RegNotifyChangeKeyValue(hKeya, 0, 5u, EventW, 1);
    if ( v17 )
      goto LABEL_10;
    cchValueName = 260;
    v19 = RegEnumValueW(hKeya, a3, a4, &cchValueName, 0, &Type, 0, &cbData);
    v17 = v19;
    if ( v19 != 259 )
    {
      if ( v19 && v19 != 234 )
      {
LABEL_10:
        CloseHandle(EventW);
        RegCloseKey(hKeya);
        goto LABEL_6;
      }
      if ( !cbData )
      {
LABEL_22:
        v18 = RegQueryValueExW(hKeya, L"SymbolicLinkValue", 0, &v23, 0, &v24);
        RegCloseKey(hKeya);
        v21 = WaitForSingleObject(EventW, 0);
        CloseHandle(EventW);
        if ( !v21 )
        {
          v17 = -2147023590;
LABEL_30:
          free(*v11);
          *v11 = 0;
          *a4 = 0;
          return v17;
        }
        if ( v18 )
        {
          if ( v18 != 2 )
          {
            free(*v11);
            *v11 = 0;
            *a4 = 0;
            if ( v18 > 0 )
              return (unsigned __int16)v18 | 0x80070000;
            return v18;
          }
        }
        else if ( v23 == 6 )
        {
          v17 = -2147023432;
          goto LABEL_30;
        }
        *v8 = Type;
        *v9 = cbData;
        return 0;
      }
      if ( 0xFFFFFFFFFFFFFFFFuLL / cbData )
      {
        lpData = (BYTE *)malloc(cbData);
        *v11 = lpData;
        if ( lpData )
        {
          cchValueName = 260;
          v17 = RegEnumValueW(hKeya, a3, a4, &cchValueName, 0, &Type, lpData, &cbData);
          if ( v17 )
          {
            CloseHandle(EventW);
            RegCloseKey(hKeya);
            free(*v11);
            *v11 = 0;
LABEL_6:
            if ( v17 > 0 )
              return (unsigned __int16)v17 | 0x80070000;
            return v17;
          }
          goto LABEL_22;
        }
      }
      v18 = -2147024882;
    }
    CloseHandle(EventW);
    RegCloseKey(hKeya);
    return v18;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140012340  mov     [rsp-38h+arg_0], rbx
0x140012345  mov     [rsp-38h+dwIndex], r8d
0x14001234a  push    rbp
0x14001234b  push    rsi
0x14001234c  push    rdi
0x14001234d  push    r12
0x14001234f  push    r13
0x140012351  push    r14
0x140012353  push    r15
0x140012355  mov     rbp, rsp
0x140012358  sub     rsp, 60h
0x14001235c  mov     r12, [rbp+arg_28]
0x140012360  xor     r14d, r14d
0x140012363  mov     r13, [rbp+arg_38]
0x140012367  mov     rdi, rcx
0x14001236a  mov     rsi, [rbp+arg_30]
0x14001236e  mov     r15, r9
0x140012371  mov     [r9], r14w
0x140012375  mov     rbx, rdx
0x140012378  mov     [r12], r14d
0x14001237c  mov     [r13+0], r14d
0x140012380  mov     rcx, [rsi]; Block
0x140012383  mov     [rbp+hKey], r14
0x140012387  mov     [rbp+cchValueName], 104h
0x14001238e  mov     [rbp+Type], r14d
0x140012392  mov     [rbp+cbData], r14d
0x140012396  mov     [rbp+var_1C], r14d
0x14001239a  mov     [rbp+var_18], r14d
0x14001239e  call    cs:__imp_free
0x1400123a4  xor     r9d, r9d; lpName
0x1400123a7  mov     [rsi], r14
0x1400123aa  xor     r8d, r8d; bInitialState
0x1400123ad  xor     edx, edx; bManualReset
0x1400123af  xor     ecx, ecx; lpEventAttributes
0x1400123b1  call    cs:__imp_CreateEventW
0x1400123b7  mov     r14, rax
0x1400123ba  test    rax, rax
0x1400123bd  jnz     short loc_1400123DA
0x1400123bf  call    cs:__imp_GetLastError
0x1400123c5  test    eax, eax
0x1400123c7  jle     loc_14001261F
0x1400123cd  movzx   eax, ax
0x1400123d0  or      eax, 80070000h
0x1400123d5  jmp     loc_14001261F
0x1400123da  lea     rax, [rbp+hKey]
0x1400123de  mov     r9d, 20019h; samDesired
0x1400123e4  mov     r8d, 8; ulOptions
0x1400123ea  mov     [rsp+60h+phkResult], rax; phkResult
0x1400123ef  mov     rdx, rbx; lpSubKey
0x1400123f2  mov     rcx, rdi; hKey
0x1400123f5  call    cs:__imp_RegOpenKeyExW
0x1400123fb  mov     ebx, eax
0x1400123fd  test    eax, eax
0x1400123ff  jz      short loc_14001241E
0x140012401  mov     rcx, r14; hObject
0x140012404  call    cs:__imp_CloseHandle
0x14001240a  test    ebx, ebx
0x14001240c  jle     short loc_140012417
0x14001240e  movzx   ebx, bx
0x140012411  or      ebx, 80070000h
0x140012417  mov     eax, ebx
0x140012419  jmp     loc_14001261F
0x14001241e  mov     rcx, [rbp+hKey]; hKey
0x140012422  mov     edi, 1
0x140012427  mov     r9, r14; hEvent
0x14001242a  mov     dword ptr [rsp+60h+phkResult], edi; fAsynchronous
0x14001242e  xor     edx, edx; bWatchSubtree
0x140012430  lea     r8d, [rdi+4]; dwNotifyFilter
0x140012434  call    cs:__imp_RegNotifyChangeKeyValue
0x14001243a  mov     ebx, eax
0x14001243c  test    eax, eax
0x14001243e  jz      short loc_140012455
0x140012440  mov     rcx, r14; hObject
0x140012443  call    cs:__imp_CloseHandle
0x140012449  mov     rcx, [rbp+hKey]; hKey
0x14001244d  call    cs:__imp_RegCloseKey
0x140012453  jmp     short loc_14001240A
0x140012455  mov     edx, [rbp+dwIndex]; dwIndex
0x140012458  lea     rax, [rbp+cbData]
0x14001245c  mov     rcx, [rbp+hKey]; hKey
0x140012460  lea     r9, [rbp+cchValueName]; lpcchValueName
0x140012464  mov     [rsp+60h+lpcbData], rax; lpcbData
0x140012469  mov     r8, r15; lpValueName
0x14001246c  lea     rax, [rbp+Type]
0x140012470  mov     [rsp+60h+lpData], 0; lpData
0x140012479  mov     [rsp+60h+lpType], rax; lpType
0x14001247e  mov     [rsp+60h+phkResult], 0; lpReserved
0x140012487  mov     [rbp+cchValueName], 104h
0x14001248e  call    cs:__imp_RegEnumValueW
0x140012494  mov     ebx, eax
0x140012496  cmp     eax, 103h
0x14001249b  jz      loc_140012543
0x1400124a1  test    eax, eax
0x1400124a3  jz      short loc_1400124AC
0x1400124a5  cmp     eax, 0EAh
0x1400124aa  jnz     short loc_140012440
0x1400124ac  mov     eax, [rbp+cbData]
0x1400124af  test    eax, eax
0x1400124b1  jz      loc_14001255D
0x1400124b7  mov     ecx, eax; Size
0x1400124b9  xor     edx, edx
0x1400124bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400124bf  div     rcx
0x1400124c2  cmp     rax, rdi
0x1400124c5  jb      short loc_14001253E
0x1400124c7  call    cs:__imp_malloc
0x1400124cd  mov     [rsi], rax
0x1400124d0  test    rax, rax
0x1400124d3  jz      short loc_14001253E
0x1400124d5  mov     edx, [rbp+dwIndex]; dwIndex
0x1400124d8  lea     rcx, [rbp+cbData]
0x1400124dc  mov     [rsp+60h+lpcbData], rcx; lpcbData
0x1400124e1  lea     r9, [rbp+cchValueName]; lpcchValueName
0x1400124e5  mov     rcx, [rbp+hKey]; hKey
0x1400124e9  mov     r8, r15; lpValueName
0x1400124ec  mov     [rsp+60h+lpData], rax; lpData
0x1400124f1  lea     rax, [rbp+Type]
0x1400124f5  mov     [rsp+60h+lpType], rax; lpType
0x1400124fa  mov     [rsp+60h+phkResult], 0; lpReserved
0x140012503  mov     [rbp+cchValueName], 104h
0x14001250a  call    cs:__imp_RegEnumValueW
0x140012510  mov     ebx, eax
0x140012512  test    eax, eax
0x140012514  jz      short loc_14001255D
0x140012516  mov     rcx, r14; hObject
0x140012519  call    cs:__imp_CloseHandle
0x14001251f  mov     rcx, [rbp+hKey]; hKey
0x140012523  call    cs:__imp_RegCloseKey
0x140012529  mov     rcx, [rsi]; Block
0x14001252c  call    cs:__imp_free
0x140012532  mov     qword ptr [rsi], 0
0x140012539  jmp     loc_14001240A
0x14001253e  mov     edi, 8007000Eh
0x140012543  mov     rcx, r14; hObject
0x140012546  call    cs:__imp_CloseHandle
0x14001254c  mov     rcx, [rbp+hKey]; hKey
0x140012550  call    cs:__imp_RegCloseKey
0x140012556  mov     eax, edi
0x140012558  jmp     loc_14001261F
0x14001255d  mov     rcx, [rbp+hKey]; hKey
0x140012561  lea     rax, [rbp+var_18]
0x140012565  mov     [rsp+60h+lpType], rax; lpcbData
0x14001256a  lea     r9, [rbp+var_1C]; lpType
0x14001256e  xor     r8d, r8d; lpReserved
0x140012571  mov     [rsp+60h+phkResult], 0; lpData
0x14001257a  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x140012581  call    cs:__imp_RegQueryValueExW
0x140012587  mov     rcx, [rbp+hKey]; hKey
0x14001258b  mov     edi, eax
0x14001258d  call    cs:__imp_RegCloseKey
0x140012593  xor     edx, edx; dwMilliseconds
0x140012595  mov     rcx, r14; hHandle
0x140012598  call    cs:__imp_WaitForSingleObject
0x14001259e  mov     rcx, r14; hObject
0x1400125a1  mov     ebx, eax
0x1400125a3  call    cs:__imp_CloseHandle
0x1400125a9  test    ebx, ebx
0x1400125ab  jnz     short loc_1400125B4
0x1400125ad  mov     ebx, 8007051Ah
0x1400125b2  jmp     short loc_1400125F4
0x1400125b4  test    edi, edi
0x1400125b6  jz      short loc_1400125E9
0x1400125b8  cmp     edi, 2
0x1400125bb  jz      short loc_14001260F
0x1400125bd  mov     rcx, [rsi]; Block
0x1400125c0  call    cs:__imp_free
0x1400125c6  xor     eax, eax
0x1400125c8  mov     qword ptr [rsi], 0
0x1400125cf  mov     [r15], ax
0x1400125d3  test    edi, edi
0x1400125d5  jle     loc_140012556
0x1400125db  movzx   edi, di
0x1400125de  or      edi, 80070000h
0x1400125e4  jmp     loc_140012556
0x1400125e9  cmp     [rbp+var_1C], 6
0x1400125ed  jnz     short loc_14001260F
0x1400125ef  mov     ebx, 800705B8h
0x1400125f4  mov     rcx, [rsi]; Block
0x1400125f7  call    cs:__imp_free
0x1400125fd  xor     ecx, ecx
0x1400125ff  mov     qword ptr [rsi], 0
0x140012606  mov     [r15], cx
0x14001260a  jmp     loc_140012417
0x14001260f  mov     eax, [rbp+Type]
0x140012612  mov     [r12], eax
0x140012616  mov     eax, [rbp+cbData]
0x140012619  mov     [r13+0], eax
0x14001261d  xor     eax, eax
0x14001261f  mov     rbx, [rsp+60h+arg_0]
0x140012627  add     rsp, 60h
0x14001262b  pop     r15
0x14001262d  pop     r14
0x14001262f  pop     r13
0x140012631  pop     r12
0x140012633  pop     rdi
0x140012634  pop     rsi
0x140012635  pop     rbp
0x140012636  retn
```
