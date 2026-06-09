# CExtensionList::IsStale(ExtensionListStalenessFlags,int *)

- ea: `0x180047670`
- end: `0x1800477e2`
- name: `?IsStale@CExtensionList@@UEAAJW4ExtensionListStalenessFlags@@PEAH@Z`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18003e3a8`
- `0x180047670`
- `0x180048730`
- `0x1800498dc`
- `0x180049b78`
- `0x180076c50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180047766`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180047766`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800476c5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004771d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800477a7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800476c5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004771d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800477a7`

## pseudocode

```c
__int64 __fastcall CExtensionList::IsStale(FILETIME *a1, char a2, _DWORD *a3)
{
  __int64 *v6; // rsi
  __int64 v7; // r8
  const unsigned __int16 *v8; // rcx
  FILETIME FileTime1; // [rsp+30h] [rbp-30h] BYREF
  FILETIME v11; // [rsp+38h] [rbp-28h] BYREF
  IID rclsid; // [rsp+40h] [rbp-20h] BYREF

  *a3 = 0;
  if ( (a2 & 1) == 0 )
    goto LABEL_5;
  FileTime1 = 0;
  if ( (int)CExtensionList::_GetLastExtensionCatalogWriteTime((CExtensionList *)a1, &FileTime1) >= 0 )
    *a3 = CompareFileTime(&FileTime1, a1 + 12) != 0;
  if ( !*a3 )
  {
LABEL_5:
    v6 = (__int64 *)&a1[9];
    if ( (a2 & 2) != 0 )
    {
      v7 = *v6;
      FileTime1 = 0;
      if ( (int)_GetRegKeyLastWriteTime(
                  HKEY_CURRENT_USER,
                  (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AppContract",
                  v7,
                  0,
                  &FileTime1) >= 0 )
        *a3 = CompareFileTime(&FileTime1, a1 + 13) != 0;
    }
    if ( !*a3 && (a2 & 4) != 0 )
    {
      v8 = (const unsigned __int16 *)*v6;
      rclsid = 0;
      if ( (int)UAGetLoggerIDByContractID(v8, &rclsid) >= 0 )
      {
        FileTime1 = 0;
        if ( StringFromCLSID(&rclsid, (LPOLESTR *)&FileTime1) >= 0 )
        {
          v11 = 0;
          if ( (int)_GetRegKeyLastWriteTime(
                      HKEY_CURRENT_USER,
                      (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\UserAssist",
                      *(_QWORD *)&FileTime1,
                      0,
                      &v11) >= 0 )
            *a3 = CompareFileTime(&v11, a1 + 14) != 0;
        }
        CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>((void **)&FileTime1);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180047670  mov     [rsp-18h+arg_8], rbx
0x180047675  mov     [rsp-18h+arg_18], rsi
0x18004767a  push    rbp
0x18004767b  push    rdi
0x18004767c  push    r14
0x18004767e  mov     rbp, rsp
0x180047681  sub     rsp, 60h
0x180047685  mov     rax, cs:__security_cookie
0x18004768c  xor     rax, rsp
0x18004768f  mov     [rbp+var_10], rax
0x180047693  mov     dword ptr [r8], 0
0x18004769a  mov     rbx, r8
0x18004769d  mov     r14d, edx
0x1800476a0  mov     rdi, rcx
0x1800476a3  test    dl, 1
0x1800476a6  jz      short loc_1800476DD
0x1800476a8  lea     rdx, [rbp+FileTime1]; struct _FILETIME *
0x1800476ac  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x1800476b4  call    ?_GetLastExtensionCatalogWriteTime@CExtensionList@@AEAAJPEAU_FILETIME@@@Z; CExtensionList::_GetLastExtensionCatalogWriteTime(_FILETIME *)
0x1800476b9  test    eax, eax
0x1800476bb  js      short loc_1800476D4
0x1800476bd  lea     rdx, [rdi+60h]; lpFileTime2
0x1800476c1  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800476c5  call    cs:__imp_CompareFileTime
0x1800476cb  xor     ecx, ecx
0x1800476cd  test    eax, eax
0x1800476cf  setnz   cl
0x1800476d2  mov     [rbx], ecx
0x1800476d4  cmp     dword ptr [rbx], 0
0x1800476d7  jnz     loc_1800477BF
0x1800476dd  lea     rsi, [rdi+48h]
0x1800476e1  test    r14b, 2
0x1800476e5  jz      short loc_18004772C
0x1800476e7  mov     r8, [rsi]
0x1800476ea  lea     rax, [rbp+FileTime1]
0x1800476ee  xor     r9d, r9d
0x1800476f1  mov     [rsp+60h+var_40], rax
0x1800476f6  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800476fd  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x180047705  mov     rcx, 0FFFFFFFF80000001h
0x18004770c  call    ?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z; _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)
0x180047711  test    eax, eax
0x180047713  js      short loc_18004772C
0x180047715  lea     rdx, [rdi+68h]; lpFileTime2
0x180047719  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18004771d  call    cs:__imp_CompareFileTime
0x180047723  xor     ecx, ecx
0x180047725  test    eax, eax
0x180047727  setnz   cl
0x18004772a  mov     [rbx], ecx
0x18004772c  cmp     dword ptr [rbx], 0
0x18004772f  jnz     loc_1800477BF
0x180047735  test    r14b, 4
0x180047739  jz      loc_1800477BF
0x18004773f  mov     rcx, [rsi]; unsigned __int16 *
0x180047742  lea     rdx, [rbp+rclsid]; struct _GUID *
0x180047746  xorps   xmm0, xmm0
0x180047749  movups  xmmword ptr [rbp+rclsid.Data1], xmm0
0x18004774d  call    ?UAGetLoggerIDByContractID@@YAJPEBGPEAU_GUID@@@Z; UAGetLoggerIDByContractID(ushort const *,_GUID *)
0x180047752  test    eax, eax
0x180047754  js      short loc_1800477BF
0x180047756  lea     rdx, [rbp+FileTime1]; lplpsz
0x18004775a  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x180047762  lea     rcx, [rbp+rclsid]; rclsid
0x180047766  call    cs:__imp_StringFromCLSID
0x18004776c  test    eax, eax
0x18004776e  js      short loc_1800477B6
0x180047770  mov     r8, qword ptr [rbp+FileTime1.dwLowDateTime]
0x180047774  lea     rax, [rbp+var_28]
0x180047778  xor     r9d, r9d
0x18004777b  mov     [rsp+60h+var_40], rax
0x180047780  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180047787  mov     qword ptr [rbp+var_28.dwLowDateTime], 0
0x18004778f  mov     rcx, 0FFFFFFFF80000001h
0x180047796  call    ?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z; _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)
0x18004779b  test    eax, eax
0x18004779d  js      short loc_1800477B6
0x18004779f  lea     rdx, [rdi+70h]; lpFileTime2
0x1800477a3  lea     rcx, [rbp+var_28]; lpFileTime1
0x1800477a7  call    cs:__imp_CompareFileTime
0x1800477ad  xor     ecx, ecx
0x1800477af  test    eax, eax
0x1800477b1  setnz   cl
0x1800477b4  mov     [rbx], ecx
0x1800477b6  lea     rcx, [rbp+FileTime1]
0x1800477ba  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800477bf  xor     eax, eax
0x1800477c1  mov     rcx, [rbp+var_10]
0x1800477c5  xor     rcx, rsp; StackCookie
0x1800477c8  call    __security_check_cookie
0x1800477cd  lea     r11, [rsp+60h+var_s0]
0x1800477d2  mov     rbx, [r11+28h]
0x1800477d6  mov     rsi, [r11+38h]
0x1800477da  mov     rsp, r11
0x1800477dd  pop     r14
0x1800477df  pop     rdi
0x1800477e0  pop     rbp
0x1800477e1  retn
```
