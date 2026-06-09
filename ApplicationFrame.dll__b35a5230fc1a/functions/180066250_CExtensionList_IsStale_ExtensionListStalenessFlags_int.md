# CExtensionList::IsStale(ExtensionListStalenessFlags,int *)

- ea: `0x180066250`
- end: `0x1800663c2`
- name: `?IsStale@CExtensionList@@UEAAJW4ExtensionListStalenessFlags@@PEAH@Z`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180043c30`
- `0x180061b4c`
- `0x180066250`
- `0x180067430`
- `0x180068988`
- `0x180068c24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180066346`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180066346`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800662a5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800662fd`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180066387`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800662a5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800662fd`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180066387`

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
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&FileTime1);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180066250  mov     [rsp-18h+arg_8], rbx
0x180066255  mov     [rsp-18h+arg_18], rsi
0x18006625a  push    rbp
0x18006625b  push    rdi
0x18006625c  push    r14
0x18006625e  mov     rbp, rsp
0x180066261  sub     rsp, 60h
0x180066265  mov     rax, cs:__security_cookie
0x18006626c  xor     rax, rsp
0x18006626f  mov     [rbp+var_10], rax
0x180066273  mov     dword ptr [r8], 0
0x18006627a  mov     rbx, r8
0x18006627d  mov     r14d, edx
0x180066280  mov     rdi, rcx
0x180066283  test    dl, 1
0x180066286  jz      short loc_1800662BD
0x180066288  lea     rdx, [rbp+FileTime1]; struct _FILETIME *
0x18006628c  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x180066294  call    ?_GetLastExtensionCatalogWriteTime@CExtensionList@@AEAAJPEAU_FILETIME@@@Z; CExtensionList::_GetLastExtensionCatalogWriteTime(_FILETIME *)
0x180066299  test    eax, eax
0x18006629b  js      short loc_1800662B4
0x18006629d  lea     rdx, [rdi+60h]; lpFileTime2
0x1800662a1  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800662a5  call    cs:__imp_CompareFileTime
0x1800662ab  xor     ecx, ecx
0x1800662ad  test    eax, eax
0x1800662af  setnz   cl
0x1800662b2  mov     [rbx], ecx
0x1800662b4  cmp     dword ptr [rbx], 0
0x1800662b7  jnz     loc_18006639F
0x1800662bd  lea     rsi, [rdi+48h]
0x1800662c1  test    r14b, 2
0x1800662c5  jz      short loc_18006630C
0x1800662c7  mov     r8, [rsi]
0x1800662ca  lea     rax, [rbp+FileTime1]
0x1800662ce  xor     r9d, r9d
0x1800662d1  mov     [rsp+60h+var_40], rax
0x1800662d6  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800662dd  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x1800662e5  mov     rcx, 0FFFFFFFF80000001h
0x1800662ec  call    ?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z; _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)
0x1800662f1  test    eax, eax
0x1800662f3  js      short loc_18006630C
0x1800662f5  lea     rdx, [rdi+68h]; lpFileTime2
0x1800662f9  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800662fd  call    cs:__imp_CompareFileTime
0x180066303  xor     ecx, ecx
0x180066305  test    eax, eax
0x180066307  setnz   cl
0x18006630a  mov     [rbx], ecx
0x18006630c  cmp     dword ptr [rbx], 0
0x18006630f  jnz     loc_18006639F
0x180066315  test    r14b, 4
0x180066319  jz      loc_18006639F
0x18006631f  mov     rcx, [rsi]; unsigned __int16 *
0x180066322  lea     rdx, [rbp+rclsid]; struct _GUID *
0x180066326  xorps   xmm0, xmm0
0x180066329  movups  xmmword ptr [rbp+rclsid.Data1], xmm0
0x18006632d  call    ?UAGetLoggerIDByContractID@@YAJPEBGPEAU_GUID@@@Z; UAGetLoggerIDByContractID(ushort const *,_GUID *)
0x180066332  test    eax, eax
0x180066334  js      short loc_18006639F
0x180066336  lea     rdx, [rbp+FileTime1]; lplpsz
0x18006633a  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x180066342  lea     rcx, [rbp+rclsid]; rclsid
0x180066346  call    cs:__imp_StringFromCLSID
0x18006634c  test    eax, eax
0x18006634e  js      short loc_180066396
0x180066350  mov     r8, qword ptr [rbp+FileTime1.dwLowDateTime]
0x180066354  lea     rax, [rbp+var_28]
0x180066358  xor     r9d, r9d
0x18006635b  mov     [rsp+60h+var_40], rax
0x180066360  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180066367  mov     qword ptr [rbp+var_28.dwLowDateTime], 0
0x18006636f  mov     rcx, 0FFFFFFFF80000001h
0x180066376  call    ?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z; _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)
0x18006637b  test    eax, eax
0x18006637d  js      short loc_180066396
0x18006637f  lea     rdx, [rdi+70h]; lpFileTime2
0x180066383  lea     rcx, [rbp+var_28]; lpFileTime1
0x180066387  call    cs:__imp_CompareFileTime
0x18006638d  xor     ecx, ecx
0x18006638f  test    eax, eax
0x180066391  setnz   cl
0x180066394  mov     [rbx], ecx
0x180066396  lea     rcx, [rbp+FileTime1]
0x18006639a  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18006639f  xor     eax, eax
0x1800663a1  mov     rcx, [rbp+var_10]
0x1800663a5  xor     rcx, rsp; StackCookie
0x1800663a8  call    __security_check_cookie
0x1800663ad  lea     r11, [rsp+60h+var_s0]
0x1800663b2  mov     rbx, [r11+28h]
0x1800663b6  mov     rsi, [r11+38h]
0x1800663ba  mov     rsp, r11
0x1800663bd  pop     r14
0x1800663bf  pop     rdi
0x1800663c0  pop     rbp
0x1800663c1  retn
```
