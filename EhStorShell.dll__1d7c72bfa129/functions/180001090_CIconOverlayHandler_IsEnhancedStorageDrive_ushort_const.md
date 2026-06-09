# CIconOverlayHandler::_IsEnhancedStorageDrive(ushort const *)

- ea: `0x180001090`
- end: `0x18000130c`
- name: `?_IsEnhancedStorageDrive@CIconOverlayHandler@@AEAAHPEBG@Z`
- size: `636`
- prototype: `__int64 __fastcall(CIconOverlayHandler *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001050`

## callees

- `0x180001090`
- `0x180001320`
- `0x1800013e0`
- `0x18000453c`
- `0x18000684c`
- `0x180009ac0`
- `0x18000b630`
- `0x18000c010`

## import_xrefs

- `msvcrt!toupper` at `0x1800010f2`
- `msvcrt!toupper` at `0x1800010f2`
- `KERNEL32!EnterCriticalSection` at `0x1800010c5`
- `KERNEL32!EnterCriticalSection` at `0x18000113f`
- `KERNEL32!EnterCriticalSection` at `0x1800010c5`
- `KERNEL32!EnterCriticalSection` at `0x18000113f`
- `KERNEL32!LeaveCriticalSection` at `0x1800010d5`
- `KERNEL32!LeaveCriticalSection` at `0x18000114f`
- `KERNEL32!LeaveCriticalSection` at `0x1800010d5`
- `KERNEL32!LeaveCriticalSection` at `0x18000114f`
- `KERNEL32!GetLogicalDrives` at `0x1800010db`
- `KERNEL32!GetLogicalDrives` at `0x1800010db`
- `KERNEL32!GetDriveTypeW` at `0x1800011e1`
- `KERNEL32!GetDriveTypeW` at `0x1800011e1`
- `ole32!CoCreateInstance` at `0x18000118e`
- `ole32!CoCreateInstance` at `0x18000118e`

## pseudocode

```c
__int64 __fastcall CIconOverlayHandler::_IsEnhancedStorageDrive(CIconOverlayHandler *this, const unsigned __int16 *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  int v5; // edi
  int v6; // r15d
  DWORD LogicalDrives; // eax
  DWORD v8; // r13d
  DWORD v10; // edi
  __int64 v11; // r9
  DWORD v12; // r13d
  unsigned __int16 v13; // r14
  UINT DriveTypeW; // eax
  int v15; // edx
  int v16; // r8d
  UINT v17; // [rsp+30h] [rbp-50h] BYREF
  __int64 v18; // [rsp+38h] [rbp-48h] BYREF
  int (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-40h] BYREF
  unsigned int v20; // [rsp+48h] [rbp-38h]
  DWORD v21; // [rsp+4Ch] [rbp-34h]
  LPVOID ppv; // [rsp+50h] [rbp-30h] BYREF
  WCHAR RootPathName[8]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v24; // [rsp+68h] [rbp-18h]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v5 = *((_DWORD *)this + 14);
  v6 = *((_DWORD *)this + 15);
  LeaveCriticalSection(v4);
  LogicalDrives = GetLogicalDrives();
  v8 = LogicalDrives;
  if ( v5 != LogicalDrives )
  {
    v10 = LogicalDrives;
    v21 = LogicalDrives;
    v6 = 0;
    if ( (unsigned int)IsAnyEhStorDevicePresent() )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_c8fefde2d03f30a89c7cae0a6090c140_Traceguids, v11);
      ppv = 0;
      if ( CoCreateInstance(&CLSID_EnumEnhancedStorageACT, 0, 1u, &GUID_09b224bd_1335_4631_a7ff_cfd3a92646d7, &ppv) >= 0 )
      {
        v12 = v8 >> 2;
        if ( v12 )
        {
          v13 = 2;
          do
          {
            *(_OWORD *)RootPathName = 0;
            v24 = 0;
            v20 = v13 + 65;
            StringCchPrintfW(RootPathName, 0x10u, L"\\\\.\\%c:\\", v20);
            DriveTypeW = GetDriveTypeW(RootPathName);
            v17 = DriveTypeW;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
            {
              WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, (unsigned int)RootPathName, DriveTypeW);
              DriveTypeW = v17;
            }
            if ( DriveTypeW - 2 <= 1 )
            {
              StringCchPrintfW(RootPathName, 0x10u, L"\\\\.\\%c:", v20);
              v19 = 0;
              v18 = 0;
              if ( (*(int (__fastcall **)(LPVOID, WCHAR *, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, RootPathName, &v19) >= 0 )
              {
                if ( (**v19)(v19, &GUID_022150a1_113d_11df_bb61_001aa01bbc58, &v18) < 0
                  || (v17 = 0, (*(int (__fastcall **)(__int64, UINT *))(*(_QWORD *)v18 + 104LL))(v18, &v17) < 0)
                  || v17 )
                {
                  v6 |= 1 << v13;
                }
              }
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
            }
            ++v13;
            v12 >>= 1;
          }
          while ( v12 );
          v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
          v10 = v21;
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    EnterCriticalSection(v4);
    *((_DWORD *)this + 14) = v10;
    *((_DWORD *)this + 15) = v6;
    LeaveCriticalSection(v4);
  }
  return v6 & (unsigned int)(1 << (toupper(*a2) - 65));
}

```

## disassembly

```asm
0x180001090  mov     [rsp-38h+arg_10], rbx
0x180001095  push    rbp
0x180001096  push    rsi
0x180001097  push    rdi
0x180001098  push    r12
0x18000109a  push    r13
0x18000109c  push    r14
0x18000109e  push    r15
0x1800010a0  mov     rbp, rsp
0x1800010a3  sub     rsp, 80h
0x1800010aa  mov     rax, cs:__security_cookie
0x1800010b1  xor     rax, rsp
0x1800010b4  mov     [rbp+var_8], rax
0x1800010b8  mov     r12, rdx
0x1800010bb  mov     rsi, rcx
0x1800010be  lea     r14, [rcx+10h]
0x1800010c2  mov     rcx, r14; lpCriticalSection
0x1800010c5  call    cs:__imp_EnterCriticalSection
0x1800010cb  mov     edi, [rsi+38h]
0x1800010ce  mov     r15d, [rsi+3Ch]
0x1800010d2  mov     rcx, r14; lpCriticalSection
0x1800010d5  call    cs:__imp_LeaveCriticalSection
0x1800010db  call    cs:__imp_GetLogicalDrives
0x1800010e1  mov     r13d, eax
0x1800010e4  mov     ebx, 1
0x1800010e9  cmp     edi, eax
0x1800010eb  jnz     short loc_180001129
0x1800010ed  movzx   ecx, word ptr [r12]; C
0x1800010f2  call    cs:__imp_toupper
0x1800010f8  lea     ecx, [rax-41h]
0x1800010fb  shl     ebx, cl
0x1800010fd  and     ebx, r15d
0x180001100  mov     eax, ebx
0x180001102  mov     rcx, [rbp+var_8]
0x180001106  xor     rcx, rsp; StackCookie
0x180001109  call    __security_check_cookie
0x18000110e  mov     rbx, [rsp+80h+arg_10]
0x180001116  add     rsp, 80h
0x18000111d  pop     r15
0x18000111f  pop     r14
0x180001121  pop     r13
0x180001123  pop     r12
0x180001125  pop     rdi
0x180001126  pop     rsi
0x180001127  pop     rbp
0x180001128  retn
0x180001129  mov     edi, r13d
0x18000112c  mov     [rbp+var_34], r13d
0x180001130  xor     r15d, r15d
0x180001133  call    IsAnyEhStorDevicePresent
0x180001138  test    eax, eax
0x18000113a  jnz     short loc_180001157
0x18000113c  mov     rcx, r14; lpCriticalSection
0x18000113f  call    cs:__imp_EnterCriticalSection
0x180001145  mov     [rsi+38h], edi
0x180001148  mov     [rsi+3Ch], r15d
0x18000114c  mov     rcx, r14; lpCriticalSection
0x18000114f  call    cs:__imp_LeaveCriticalSection
0x180001155  jmp     short loc_1800010ED
0x180001157  lea     rax, WPP_GLOBAL_Control
0x18000115e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001165  cmp     rcx, rax
0x180001168  jnz     loc_180001222
0x18000116e  mov     [rbp+var_30], r15
0x180001172  lea     rax, [rbp+var_30]
0x180001176  mov     [rsp+80h+ppv], rax; ppv
0x18000117b  lea     r9, _GUID_09b224bd_1335_4631_a7ff_cfd3a92646d7; riid
0x180001182  mov     r8d, ebx; dwClsContext
0x180001185  xor     edx, edx; pUnkOuter
0x180001187  lea     rcx, CLSID_EnumEnhancedStorageACT; rclsid
0x18000118e  call    cs:__imp_CoCreateInstance
0x180001194  test    eax, eax
0x180001196  js      short loc_18000113C
0x180001198  shr     r13d, 2
0x18000119c  test    r13d, r13d
0x18000119f  jz      short loc_18000120D
0x1800011a1  mov     r14d, 2
0x1800011a7  lea     rdi, WPP_GLOBAL_Control
0x1800011ae  xchg    ax, ax
0x1800011b0  xorps   xmm0, xmm0
0x1800011b3  movups  xmmword ptr [rbp+RootPathName], xmm0
0x1800011b7  movups  [rbp+var_18], xmm0
0x1800011bb  movzx   eax, r14w
0x1800011bf  add     eax, 41h ; 'A'
0x1800011c2  mov     [rbp+var_38], eax
0x1800011c5  mov     r9d, eax
0x1800011c8  lea     r8, aC_0; "\\\\.\\%c:\\"
0x1800011cf  mov     edx, 10h; unsigned __int64
0x1800011d4  lea     rcx, [rbp+RootPathName]; unsigned __int16 *
0x1800011d8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800011dd  lea     rcx, [rbp+RootPathName]; lpRootPathName
0x1800011e1  call    cs:__imp_GetDriveTypeW
0x1800011e7  mov     [rbp+var_50], eax
0x1800011ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800011f1  cmp     rcx, rdi
0x1800011f4  jnz     short loc_180001246
0x1800011f6  add     eax, 0FFFFFFFEh
0x1800011f9  cmp     eax, 1
0x1800011fc  jbe     short loc_180001262
0x1800011fe  inc     r14d
0x180001201  shr     r13d, 1
0x180001204  jnz     short loc_1800011B0
0x180001206  lea     r14, [rsi+10h]
0x18000120a  mov     edi, [rbp+var_34]
0x18000120d  mov     rcx, [rbp+var_30]
0x180001211  mov     rax, [rcx]
0x180001214  mov     rax, [rax+10h]
0x180001218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000121d  jmp     loc_18000113C
0x180001222  test    byte ptr [rcx+1Ch], 20h
0x180001226  jz      loc_18000116E
0x18000122c  mov     edx, 0Eh
0x180001231  lea     r8, WPP_c8fefde2d03f30a89c7cae0a6090c140_Traceguids
0x180001238  mov     rcx, [rcx+10h]
0x18000123c  call    WPP_SF_
0x180001241  jmp     loc_18000116E
0x180001246  test    byte ptr [rcx+1Ch], 20h
0x18000124a  jz      short loc_1800011F6
0x18000124c  mov     dword ptr [rsp+80h+ppv], eax
0x180001250  lea     r9, [rbp+RootPathName]
0x180001254  mov     rcx, [rcx+10h]
0x180001258  call    WPP_SF_Sd
0x18000125d  mov     eax, [rbp+var_50]
0x180001260  jmp     short loc_1800011F6
0x180001262  mov     r9d, [rbp+var_38]
0x180001266  lea     r8, aC; "\\\\.\\%c:"
0x18000126d  mov     edx, 10h; unsigned __int64
0x180001272  lea     rcx, [rbp+RootPathName]; unsigned __int16 *
0x180001276  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000127b  mov     [rbp+var_40], 0
0x180001283  mov     [rbp+var_48], 0
0x18000128b  mov     rcx, [rbp+var_30]
0x18000128f  mov     rax, [rcx]
0x180001292  lea     r8, [rbp+var_40]
0x180001296  lea     rdx, [rbp+RootPathName]
0x18000129a  mov     rax, [rax+20h]
0x18000129e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012a3  test    eax, eax
0x1800012a5  js      short loc_1800012F4
0x1800012a7  mov     rcx, [rbp+var_40]
0x1800012ab  mov     rax, [rcx]
0x1800012ae  lea     r8, [rbp+var_48]
0x1800012b2  lea     rdx, _GUID_022150a1_113d_11df_bb61_001aa01bbc58
0x1800012b9  mov     rax, [rax]
0x1800012bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012c1  test    eax, eax
0x1800012c3  js      short loc_1800012EA
0x1800012c5  mov     [rbp+var_50], 0
0x1800012cc  mov     rcx, [rbp+var_48]
0x1800012d0  mov     rax, [rcx]
0x1800012d3  lea     rdx, [rbp+var_50]
0x1800012d7  mov     rax, [rax+68h]
0x1800012db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012e0  test    eax, eax
0x1800012e2  js      short loc_1800012EA
0x1800012e4  cmp     [rbp+var_50], 0
0x1800012e8  jz      short loc_1800012F4
0x1800012ea  mov     ecx, r14d
0x1800012ed  mov     eax, ebx
0x1800012ef  shl     eax, cl
0x1800012f1  or      r15d, eax
0x1800012f4  lea     rcx, [rbp+var_48]
0x1800012f8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800012fd  nop
0x1800012fe  lea     rcx, [rbp+var_40]
0x180001302  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001307  jmp     loc_1800011FE
```
