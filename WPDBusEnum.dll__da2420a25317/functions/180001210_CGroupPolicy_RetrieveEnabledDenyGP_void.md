# CGroupPolicy::RetrieveEnabledDenyGP(void)

- ea: `0x180001210`
- end: `0x18000172a`
- name: `?RetrieveEnabledDenyGP@CGroupPolicy@@IEAAXXZ`
- size: `1306`
- prototype: `void __fastcall(CGroupPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002c70`

## callees

- `0x180001210`
- `0x180001730`
- `0x180002fa0`
- `0x180005bb0`
- `0x180005d40`
- `0x180007f68`
- `0x1800097d0`
- `0x18000a192`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800014f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800014f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001709`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001709`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800012db`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800012db`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800013ab`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800016a3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800013ab`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800016a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001475`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800014cc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001556`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000159b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800015e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001619`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001475`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800014cc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001556`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000159b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800015e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001619`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800013d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000148c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800013d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000148c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001510`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001647`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800016d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800016e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001510`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001647`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800016d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800016e1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800014e6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800014e6`

## string_xrefs

- `0x1800012e8`: `Failed to open the EnabledDenyGP root key with (%d)\n`
- `0x18000141c`: `StringCchCopyW failed with (%d)hr\n`
- `0x180001459`: `SecurityDescriptor`
- `0x1800014ad`: `SecurityDescriptor`
- `0x1800014f9`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed with (%d)\n`
- `0x18000164f`: `Memory Allocation failed for stringSecurityDescriptor\n`
- `0x18000153a`: `AccessBitMask`
- `0x1800013e3`: `Memory Allocation failed for STORAGE_SECURITY_DESCRIPTOR\n`

## pseudocode

```c
void __fastcall CGroupPolicy::RetrieveEnabledDenyGP(CGroupPolicy *this)
{
  int v2; // eax
  LSTATUS v3; // eax
  __int64 v4; // rdx
  _QWORD *v5; // rdi
  _DWORD *v6; // r14
  int v7; // eax
  int v8; // r12d
  LSTATUS i; // eax
  int v10; // eax
  WCHAR *v11; // rsi
  BOOL v12; // r15d
  DWORD LastError; // eax
  LSTATUS ValueW; // eax
  DWORD v15; // edx
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(SubKey, 0, 0x208u);
  hKey = 0;
  pcbData = 0;
  *(_QWORD *)cchName = 0;
  v2 = StringCchPrintfW(SubKey, 0x104u, L"%ws\\%ws", L"SYSTEM\\CurrentControlSet\\Control\\Storage", L"EnabledDenyGP");
  if ( v2 >= 0 )
  {
    v3 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20019u, 0, &hKey, 0);
    if ( v3 )
    {
      GPDebugPrintX(2, "Failed to open the EnabledDenyGP root key with (%d)\n", v3);
    }
    else
    {
      v5 = 0;
      pcbData = 4;
      WPDLibGetRegistryValue(hKey, v4, 0, L"DenyAllGPState", 4, cchName, &pcbData);
      v6 = *(_DWORD **)cchName;
      if ( *(_QWORD *)cchName )
        v7 = **(_DWORD **)cchName;
      else
        v7 = 0;
      *((_DWORD *)this + 6) = v7;
      memset_0(Name, 0, 0x208u);
      v8 = 1;
      cchName[0] = 260;
      for ( i = RegEnumKeyExW(hKey, 0, Name, cchName, 0, 0, 0, 0);
            !i;
            i = RegEnumKeyExW(hKey, v15, Name, cchName, 0, 0, 0, 0) )
      {
        if ( v5 || (v5 = LocalAlloc(0x40u, 0x40u)) != 0 )
        {
          memset_0(v5, 0, 0x40u);
          v10 = StringCchCopyW(SubKey, 0x104u, Name);
          if ( v10 >= 0 )
          {
            if ( (unsigned int)WPDLibConvertStringGUIDToGUID(SubKey, (char *)v5 + 28)
              && !RegGetValueW(hKey, Name, L"SecurityDescriptor", 2u, 0, 0, &pcbData) )
            {
              v11 = (WCHAR *)LocalAlloc(0x40u, pcbData);
              if ( v11 )
              {
                v12 = 0;
                if ( !RegGetValueW(hKey, Name, L"SecurityDescriptor", 2u, 0, v11, &pcbData) )
                {
                  v12 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
                          v11,
                          1u,
                          (PSECURITY_DESCRIPTOR *)v5 + 2,
                          (PULONG)v5 + 6);
                  if ( !v12 )
                  {
                    LastError = GetLastError();
                    GPDebugPrintX(
                      2,
                      "ConvertStringSecurityDescriptorToSecurityDescriptor failed with (%d)\n",
                      LastError);
                  }
                }
                LocalFree(v11);
                if ( v12 )
                {
                  pcbData = 4;
                  ValueW = RegGetValueW(hKey, Name, L"AccessBitMask", 0x18u, 0, (char *)v5 + 44, &pcbData);
                  if ( ValueW
                    || (pcbData = 4,
                        (ValueW = RegGetValueW(hKey, Name, L"EnumerateDevices", 0x18u, 0, v5 + 6, &pcbData)) != 0)
                    || (pcbData = 4,
                        (ValueW = RegGetValueW(hKey, Name, L"UserPolicy", 0x18u, 0, (char *)v5 + 52, &pcbData)) != 0) )
                  {
                    GPDebugPrintX(2, "RegGetValue status (%d)\n", ValueW);
                    LocalFree((HLOCAL)v5[2]);
                  }
                  else
                  {
                    RegGetValueW(hKey, Name, L"AuditPolicyOnly", 0x18u, 0, v5 + 7, &pcbData);
                    *v5 = *((_QWORD *)this + 1);
                    *((_QWORD *)this + 1) = v5;
                    v5 = 0;
                  }
                }
              }
              else
              {
                GPDebugPrintX(2, "Memory Allocation failed for stringSecurityDescriptor\n");
              }
            }
          }
          else
          {
            GPDebugPrintX(2, "StringCchCopyW failed with (%d)hr\n", v10);
          }
        }
        else
        {
          GPDebugPrintX(2, "Memory Allocation failed for STORAGE_SECURITY_DESCRIPTOR\n");
        }
        memset_0(Name, 0, 0x208u);
        v15 = v8++;
        cchName[0] = 260;
      }
      GPDebugPrintX(8, "RegEnumKeyExW failed with (%d)\n", i);
      LocalFree(v5);
      LocalFree(v6);
      if ( hKey )
        RegCloseKey(hKey);
    }
  }
  else
  {
    GPDebugPrintX(2, "StringCchPrintfW failed with (%d)hr\n", v2);
  }
}

```

## disassembly

```asm
0x180001210  push    rbp
0x180001212  push    rbx
0x180001213  push    r13
0x180001215  lea     rbp, [rsp-3B0h]
0x18000121d  sub     rsp, 4B0h
0x180001224  mov     rax, cs:__security_cookie
0x18000122b  xor     rax, rsp
0x18000122e  mov     [rbp+3C0h+var_30], rax
0x180001235  mov     rbx, rcx
0x180001238  xor     edx, edx; Val
0x18000123a  lea     rcx, [rbp+3C0h+SubKey]; void *
0x180001241  mov     r8d, 208h; Size
0x180001247  call    memset_0
0x18000124c  xor     r13d, r13d
0x18000124f  lea     rax, aEnableddenygp; "EnabledDenyGP"
0x180001256  lea     r9, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Sto"...
0x18000125d  mov     qword ptr [rsp+4C0h+dwOptions], rax
0x180001262  lea     r8, aWsWs; "%ws\\%ws"
0x180001269  mov     [rsp+4C0h+hKey], r13
0x18000126e  mov     edx, 104h; unsigned __int64
0x180001273  mov     [rsp+4C0h+pcbData], r13d
0x180001278  lea     rcx, [rbp+3C0h+SubKey]; unsigned __int16 *
0x18000127f  mov     qword ptr [rsp+4C0h+cchName], r13
0x180001284  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001289  test    eax, eax
0x18000128b  jns     short loc_1800012A6
0x18000128d  mov     r8d, eax
0x180001290  lea     rdx, aStringcchprint; "StringCchPrintfW failed with (%d)hr\n"
0x180001297  mov     ecx, 2; unsigned int
0x18000129c  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x1800012a1  jmp     loc_18000170F
0x1800012a6  mov     [rsp+4C0h+lpdwDisposition], r13; lpdwDisposition
0x1800012ab  lea     rax, [rsp+4C0h+hKey]
0x1800012b0  mov     [rsp+4C0h+phkResult], rax; phkResult
0x1800012b5  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x1800012bc  mov     [rsp+4C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800012c1  xor     r9d, r9d; lpClass
0x1800012c4  mov     [rsp+4C0h+samDesired], 20019h; samDesired
0x1800012cc  xor     r8d, r8d; Reserved
0x1800012cf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800012d6  mov     [rsp+4C0h+dwOptions], r13d; dwOptions
0x1800012db  call    cs:__imp_RegCreateKeyExW
0x1800012e1  test    eax, eax
0x1800012e3  jz      short loc_1800012FE
0x1800012e5  mov     r8d, eax
0x1800012e8  lea     rdx, aFailedToOpenTh; "Failed to open the EnabledDenyGP root k"...
0x1800012ef  mov     ecx, 2; unsigned int
0x1800012f4  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x1800012f9  jmp     loc_18000170F
0x1800012fe  mov     rcx, [rsp+4C0h+hKey]
0x180001303  lea     rax, [rsp+4C0h+pcbData]
0x180001308  mov     [rsp+4C0h+lpSecurityAttributes], rax
0x18000130d  lea     r9, aDenyallgpstate; "DenyAllGPState"
0x180001314  mov     [rsp+4C0h+arg_10], rdi
0x18000131c  lea     rax, [rsp+4C0h+cchName]
0x180001321  mov     qword ptr [rsp+4C0h+samDesired], rax
0x180001326  xor     r8d, r8d
0x180001329  mov     [rsp+4C0h+arg_18], r12
0x180001331  mov     rdi, r13
0x180001334  mov     [rsp+4C0h+dwOptions], 4
0x18000133c  mov     [rsp+4C0h+var_18], r14
0x180001344  mov     [rsp+4C0h+pcbData], 4
0x18000134c  call    WPDLibGetRegistryValue
0x180001351  mov     r14, qword ptr [rsp+4C0h+cchName]
0x180001356  test    r14, r14
0x180001359  jz      short loc_180001360
0x18000135b  mov     eax, [r14]
0x18000135e  jmp     short loc_180001363
0x180001360  mov     eax, r13d
0x180001363  xor     edx, edx; Val
0x180001365  mov     [rbx+18h], eax
0x180001368  mov     r8d, 208h; Size
0x18000136e  lea     rcx, [rsp+4C0h+Name]; void *
0x180001373  call    memset_0
0x180001378  mov     rcx, [rsp+4C0h+hKey]; hKey
0x18000137d  lea     r9, [rsp+4C0h+cchName]; lpcchName
0x180001382  mov     [rsp+4C0h+phkResult], r13; lpftLastWriteTime
0x180001387  lea     r8, [rsp+4C0h+Name]; lpName
0x18000138c  mov     [rsp+4C0h+lpSecurityAttributes], r13; lpcchClass
0x180001391  xor     edx, edx; dwIndex
0x180001393  mov     qword ptr [rsp+4C0h+samDesired], r13; lpClass
0x180001398  mov     r12d, 1
0x18000139e  mov     qword ptr [rsp+4C0h+dwOptions], r13; lpReserved
0x1800013a3  mov     [rsp+4C0h+cchName], 104h
0x1800013ab  call    cs:__imp_RegEnumKeyExW
0x1800013b1  test    eax, eax
0x1800013b3  jnz     loc_1800016C1
0x1800013b9  mov     [rsp+4C0h+arg_8], rsi
0x1800013c1  mov     [rsp+4C0h+var_20], r15
0x1800013c9  test    rdi, rdi
0x1800013cc  jnz     short loc_1800013EF
0x1800013ce  mov     edx, 40h ; '@'; uBytes
0x1800013d3  mov     ecx, edx; uFlags
0x1800013d5  call    cs:__imp_LocalAlloc
0x1800013db  mov     rdi, rax
0x1800013de  test    rax, rax
0x1800013e1  jnz     short loc_1800013EF
0x1800013e3  lea     rdx, aMemoryAllocati_0; "Memory Allocation failed for STORAGE_SE"...
0x1800013ea  jmp     loc_180001656
0x1800013ef  xor     edx, edx; Val
0x1800013f1  mov     r8d, 40h ; '@'; Size
0x1800013f7  mov     rcx, rdi; void *
0x1800013fa  call    memset_0
0x1800013ff  lea     r8, [rsp+4C0h+Name]; unsigned __int16 *
0x180001404  mov     edx, 104h; unsigned __int64
0x180001409  lea     rcx, [rbp+3C0h+SubKey]; unsigned __int16 *
0x180001410  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001415  test    eax, eax
0x180001417  jns     short loc_180001432
0x180001419  mov     r8d, eax
0x18000141c  lea     rdx, aStringcchcopyw; "StringCchCopyW failed with (%d)hr\n"
0x180001423  mov     ecx, 2; unsigned int
0x180001428  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000142d  jmp     loc_180001660
0x180001432  lea     rdx, [rdi+1Ch]
0x180001436  lea     rcx, [rbp+3C0h+SubKey]
0x18000143d  call    WPDLibConvertStringGUIDToGUID
0x180001442  test    eax, eax
0x180001444  jz      loc_180001660
0x18000144a  mov     rcx, [rsp+4C0h+hKey]; hkey
0x18000144f  lea     rax, [rsp+4C0h+pcbData]
0x180001454  mov     [rsp+4C0h+lpSecurityAttributes], rax; pcbData
0x180001459  lea     r8, Value; "SecurityDescriptor"
0x180001460  mov     qword ptr [rsp+4C0h+samDesired], r13; pvData
0x180001465  lea     rdx, [rsp+4C0h+Name]; lpSubKey
0x18000146a  mov     r9d, 2; dwFlags
0x180001470  mov     qword ptr [rsp+4C0h+dwOptions], r13; pdwType
0x180001475  call    cs:__imp_RegGetValueW
0x18000147b  test    eax, eax
0x18000147d  jnz     loc_180001660
0x180001483  mov     edx, [rsp+4C0h+pcbData]; uBytes
0x180001487  mov     ecx, 40h ; '@'; uFlags
0x18000148c  call    cs:__imp_LocalAlloc
0x180001492  mov     rsi, rax
0x180001495  test    rax, rax
0x180001498  jz      loc_18000164F
0x18000149e  mov     rcx, [rsp+4C0h+hKey]; hkey
0x1800014a3  lea     rax, [rsp+4C0h+pcbData]
0x1800014a8  mov     [rsp+4C0h+lpSecurityAttributes], rax; pcbData
0x1800014ad  lea     r8, Value; "SecurityDescriptor"
0x1800014b4  mov     qword ptr [rsp+4C0h+samDesired], rsi; pvData
0x1800014b9  lea     rdx, [rsp+4C0h+Name]; lpSubKey
0x1800014be  mov     r9d, 2; dwFlags
0x1800014c4  mov     qword ptr [rsp+4C0h+dwOptions], r13; pdwType
0x1800014c9  mov     r15d, r13d
0x1800014cc  call    cs:__imp_RegGetValueW
0x1800014d2  test    eax, eax
0x1800014d4  jnz     short loc_18000150D
0x1800014d6  lea     r9, [rdi+18h]; SecurityDescriptorSize
0x1800014da  mov     edx, 1; StringSDRevision
0x1800014df  lea     r8, [rdi+10h]; SecurityDescriptor
0x1800014e3  mov     rcx, rsi; StringSecurityDescriptor
0x1800014e6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800014ec  mov     r15d, eax
0x1800014ef  test    eax, eax
0x1800014f1  jnz     short loc_18000150D
0x1800014f3  call    cs:__imp_GetLastError
0x1800014f9  lea     rdx, aConvertstrings_0; "ConvertStringSecurityDescriptorToSecuri"...
0x180001500  mov     ecx, 2; unsigned int
0x180001505  mov     r8d, eax
0x180001508  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000150d  mov     rcx, rsi; hMem
0x180001510  call    cs:__imp_LocalFree
0x180001516  test    r15d, r15d
0x180001519  jz      loc_180001660
0x18000151f  lea     rcx, [rsp+4C0h+pcbData]
0x180001524  mov     [rsp+4C0h+pcbData], 4
0x18000152c  mov     [rsp+4C0h+lpSecurityAttributes], rcx; pcbData
0x180001531  lea     rax, [rdi+2Ch]
0x180001535  mov     rcx, [rsp+4C0h+hKey]; hkey
0x18000153a  lea     r8, aAccessbitmask; "AccessBitMask"
0x180001541  mov     qword ptr [rsp+4C0h+samDesired], rax; pvData
0x180001546  lea     rdx, [rsp+4C0h+Name]; lpSubKey
0x18000154b  mov     r9d, 18h; dwFlags
0x180001551  mov     qword ptr [rsp+4C0h+dwOptions], r13; pdwType
0x180001556  call    cs:__imp_RegGetValueW
0x18000155c  test    eax, eax
0x18000155e  jnz     loc_18000162F
0x180001564  lea     rcx, [rsp+4C0h+pcbData]
0x180001569  mov     [rsp+4C0h+pcbData], 4
0x180001571  mov     [rsp+4C0h+lpSecurityAttributes], rcx; pcbData
0x180001576  lea     rax, [rdi+30h]
0x18000157a  mov     rcx, [rsp+4C0h+hKey]; hkey
0x18000157f  lea     r8, aEnumeratedevic; "EnumerateDevices"
0x180001586  mov     qword ptr [rsp+4C0h+samDesired], rax; pvData
0x18000158b  lea     rdx, [rsp+4C0h+Name]; lpSubKey
0x180001590  mov     r9d, 18h; dwFlags
0x180001596  mov     qword ptr [rsp+4C0h+dwOptions], r13; pdwType
0x18000159b  call    cs:__imp_RegGetValueW
0x1800015a1  test    eax, eax
0x1800015a3  jnz     loc_18000162F
0x1800015a9  lea     rcx, [rsp+4C0h+pcbData]
0x1800015ae  mov     [rsp+4C0h+pcbData], 4
0x1800015b6  mov     [rsp+4C0h+lpSecurityAttributes], rcx; pcbData
0x1800015bb  lea     rax, [rdi+34h]
0x1800015bf  mov     rcx, [rsp+4C0h+hKey]; hkey
0x1800015c4  lea     r8, aUserpolicy; "UserPolicy"
0x1800015cb  mov     qword ptr [rsp+4C0h+samDesired], rax; pvData
0x1800015d0  lea     rdx, [rsp+4C0h+Name]; lpSubKey
0x1800015d5  mov     r9d, 18h; dwFlags
0x1800015db  mov     qword ptr [rsp+4C0h+dwOptions], r13; pdwType
0x1800015e0  call    cs:__imp_RegGetValueW
0x1800015e6  test    eax, eax
0x1800015e8  jnz     short loc_18000162F
0x1800015ea  lea     rcx, [rsp+4C0h+pcbData]
0x1800015ef  mov     r9d, 18h; dwFlags
0x1800015f5  mov     [rsp+4C0h+lpSecurityAttributes], rcx; pcbData
0x1800015fa  lea     rax, [rdi+38h]
0x1800015fe  mov     rcx, [rsp+4C0h+hKey]; hkey
0x180001603  lea     r8, aAuditpolicyonl; "AuditPolicyOnly"
0x18000160a  mov     qword ptr [rsp+4C0h+samDesired], rax; pvData
0x18000160f  lea     rdx, [rsp+4C0h+Name]; lpSubKey
0x180001614  mov     qword ptr [rsp+4C0h+dwOptions], r13; pdwType
0x180001619  call    cs:__imp_RegGetValueW
0x18000161f  mov     rax, [rbx+8]
0x180001623  mov     [rdi], rax
0x180001626  mov     [rbx+8], rdi
0x18000162a  mov     rdi, r13
0x18000162d  jmp     short loc_180001660
0x18000162f  mov     r8d, eax
0x180001632  lea     rdx, aReggetvalueSta; "RegGetValue status (%d)\n"
0x180001639  mov     ecx, 2; unsigned int
0x18000163e  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180001643  mov     rcx, [rdi+10h]; hMem
0x180001647  call    cs:__imp_LocalFree
0x18000164d  jmp     short loc_180001660
0x18000164f  lea     rdx, aMemoryAllocati; "Memory Allocation failed for stringSecu"...
0x180001656  mov     ecx, 2; unsigned int
0x18000165b  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180001660  xor     edx, edx; Val
0x180001662  lea     rcx, [rsp+4C0h+Name]; void *
0x180001667  mov     r8d, 208h; Size
0x18000166d  call    memset_0
0x180001672  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180001677  lea     r9, [rsp+4C0h+cchName]; lpcchName
0x18000167c  mov     [rsp+4C0h+phkResult], r13; lpftLastWriteTime
0x180001681  lea     r8, [rsp+4C0h+Name]; lpName
0x180001686  mov     [rsp+4C0h+lpSecurityAttributes], r13; lpcchClass
0x18000168b  mov     edx, r12d; dwIndex
0x18000168e  mov     qword ptr [rsp+4C0h+samDesired], r13; lpClass
0x180001693  inc     r12d
0x180001696  mov     qword ptr [rsp+4C0h+dwOptions], r13; lpReserved
0x18000169b  mov     [rsp+4C0h+cchName], 104h
0x1800016a3  call    cs:__imp_RegEnumKeyExW
0x1800016a9  test    eax, eax
0x1800016ab  jz      loc_1800013C9
0x1800016b1  mov     r15, [rsp+4C0h+var_20]
0x1800016b9  mov     rsi, [rsp+4C0h+arg_8]
0x1800016c1  mov     r8d, eax
0x1800016c4  lea     rdx, aRegenumkeyexwF; "RegEnumKeyExW failed with (%d)\n"
0x1800016cb  mov     ecx, 8; unsigned int
0x1800016d0  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x1800016d5  mov     rcx, rdi; hMem
0x1800016d8  call    cs:__imp_LocalFree
0x1800016de  mov     rcx, r14; hMem
0x1800016e1  call    cs:__imp_LocalFree
0x1800016e7  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800016ec  mov     r14, [rsp+4C0h+var_18]
0x1800016f4  mov     r12, [rsp+4C0h+arg_18]
0x1800016fc  mov     rdi, [rsp+4C0h+arg_10]
0x180001704  test    rcx, rcx
0x180001707  jz      short loc_18000170F
0x180001709  call    cs:__imp_RegCloseKey
0x18000170f  mov     rcx, [rbp+3C0h+var_30]
0x180001716  xor     rcx, rsp; StackCookie
0x180001719  call    __security_check_cookie
0x18000171e  add     rsp, 4B0h
0x180001725  pop     r13
0x180001727  pop     rbx
0x180001728  pop     rbp
0x180001729  retn
```
