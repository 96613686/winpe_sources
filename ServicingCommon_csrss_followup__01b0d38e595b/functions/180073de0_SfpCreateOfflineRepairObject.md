# SfpCreateOfflineRepairObject

- ea: `0x180073de0`
- end: `0x18007407c`
- name: `SfpCreateOfflineRepairObject`
- size: `668`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180026e00`
- `0x18002d2b0`
- `0x180073ad4`
- `0x180073de0`
- `0x1800741a8`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180073eaf`
- `KERNEL32!GetLastError` at `0x180073eff`
- `KERNEL32!GetLastError` at `0x180073eaf`
- `KERNEL32!GetLastError` at `0x180073eff`
- `KERNEL32!LoadLibraryExW` at `0x180073e82`
- `KERNEL32!LoadLibraryExW` at `0x180073e82`
- `KERNEL32!GetProcAddress` at `0x180073ee7`
- `KERNEL32!GetProcAddress` at `0x180073f31`
- `KERNEL32!GetProcAddress` at `0x180073ee7`
- `KERNEL32!GetProcAddress` at `0x180073f31`
- `KERNEL32!FreeLibrary` at `0x180074037`
- `KERNEL32!FreeLibrary` at `0x180074037`
- `OLE32!CoGetMalloc` at `0x180073f5e`
- `OLE32!CoGetMalloc` at `0x180073f5e`

## pseudocode

```c
__int64 __fastcall SfpCreateOfflineRepairObject(wchar_t *a1, _QWORD *a2)
{
  int OfflineStackFromWindir; // ebx
  LPCWSTR v6; // rbx
  HMODULE Library; // rax
  const struct std::nothrow_t *v8; // rdx
  signed int LastError; // eax
  signed int v10; // eax
  __int64 v11; // rcx
  int v12; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpLibFileName; // [rsp+48h] [rbp-28h] BYREF
  __int64 v14; // [rsp+50h] [rbp-20h] BYREF
  LPMALLOC ppMalloc; // [rsp+58h] [rbp-18h] BYREF

  lpLibFileName = 0;
  ppMalloc = 0;
  v14 = 0;
  v12 = 0;
  if ( !a1 || !*a1 )
    return 2147942487LL;
  OfflineStackFromWindir = IsOnlineWindows(a1, &v12);
  if ( OfflineStackFromWindir >= 0 )
  {
    if ( v12 )
      return 2147753984LL;
    OfflineStackFromWindir = GetOfflineStackFromWindir(a1, (unsigned __int16 **)&lpLibFileName);
    if ( OfflineStackFromWindir >= 0 )
    {
      if ( !hLibModule )
      {
        v6 = lpLibFileName;
        Library = LoadLibraryExW(lpLibFileName, 0, 8u);
        hLibModule = Library;
        if ( v6 )
        {
          operator delete((void *)(v6 - 4), v8);
          Library = hLibModule;
        }
        if ( !Library )
        {
          LastError = GetLastError();
          OfflineStackFromWindir = LastError;
          if ( LastError > 0 )
            OfflineStackFromWindir = (unsigned __int16)LastError | 0x80070000;
          if ( OfflineStackFromWindir == -2147024770 )
            OfflineStackFromWindir = -2147467263;
          goto LABEL_26;
        }
        qword_1800D2D90 = (__int64)GetProcAddress(Library, "SfpInitialize");
        if ( !qword_1800D2D90 || (qword_1800D2D78 = (__int64)GetProcAddress(hLibModule, "SfpFinalize")) == 0 )
        {
          v10 = GetLastError();
          OfflineStackFromWindir = v10;
          if ( v10 > 0 )
            OfflineStackFromWindir = (unsigned __int16)v10 | 0x80070000;
          goto LABEL_26;
        }
      }
      v11 = qword_1800D2D80;
      if ( qword_1800D2D80 )
      {
LABEL_24:
        OfflineStackFromWindir = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v11 + 24LL))(
                                   v11,
                                   0,
                                   &GUID_90ed9faa_a6e5_4671_8e50_1c060f8b9c47,
                                   &v14);
        if ( OfflineStackFromWindir >= 0 )
        {
          *a2 = v14;
          v14 = 0;
        }
        goto LABEL_26;
      }
      OfflineStackFromWindir = CoGetMalloc(1u, &ppMalloc);
      if ( OfflineStackFromWindir >= 0 )
      {
        OfflineStackFromWindir = ((__int64 (__fastcall *)(LPMALLOC, void *, __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 *))qword_1800D2D90)(
                                   ppMalloc,
                                   &CCbsLogMonitorProvider::Init,
                                   RtlFinalizeSmartLBlobUcsWritingContext,
                                   WrpUtilInstanceCreated,
                                   WrpUtilInstanceDestroyed,
                                   RtlFinalizeSmartLBlobUcsWritingContext,
                                   &qword_1800D2D80);
        if ( OfflineStackFromWindir >= 0 )
        {
          v11 = qword_1800D2D80;
          goto LABEL_24;
        }
      }
    }
  }
LABEL_26:
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( ppMalloc )
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  if ( OfflineStackFromWindir < 0 && hLibModule && !qword_1800D2D80 )
  {
    FreeLibrary(hLibModule);
    hLibModule = 0;
    qword_1800D2D90 = 0;
  }
  return (unsigned int)OfflineStackFromWindir;
}

```

## disassembly

```asm
0x180073de0  mov     [rsp-18h+arg_10], rbx
0x180073de5  mov     [rsp-18h+arg_18], rsi
0x180073dea  push    rbp
0x180073deb  push    rdi
0x180073dec  push    r14
0x180073dee  mov     rbp, rsp
0x180073df1  sub     rsp, 70h
0x180073df5  mov     rax, cs:__security_cookie
0x180073dfc  xor     rax, rsp
0x180073dff  mov     [rbp+var_10], rax
0x180073e03  xor     r14d, r14d
0x180073e06  mov     rsi, rdx
0x180073e09  mov     [rbp+lpLibFileName], r14
0x180073e0d  mov     rdi, rcx
0x180073e10  mov     [rbp+ppMalloc], r14
0x180073e14  mov     [rbp+var_20], r14
0x180073e18  mov     [rbp+var_30], r14d
0x180073e1c  test    rcx, rcx
0x180073e1f  jz      loc_180074055
0x180073e25  cmp     [rcx], r14w
0x180073e29  jz      loc_180074055
0x180073e2f  lea     rdx, [rbp+var_30]
0x180073e33  call    IsOnlineWindows
0x180073e38  mov     ebx, eax
0x180073e3a  test    eax, eax
0x180073e3c  js      loc_180073FF4
0x180073e42  cmp     [rbp+var_30], r14d
0x180073e46  jz      short loc_180073E52
0x180073e48  mov     eax, 80042000h
0x180073e4d  jmp     loc_18007405A
0x180073e52  lea     rdx, [rbp+lpLibFileName]; unsigned __int16 **
0x180073e56  mov     rcx, rdi; wchar_t *
0x180073e59  call    ?GetOfflineStackFromWindir@@YAJPEBGPEAPEAG@Z; GetOfflineStackFromWindir(ushort const *,ushort * *)
0x180073e5e  mov     ebx, eax
0x180073e60  test    eax, eax
0x180073e62  js      loc_180073FF4
0x180073e68  cmp     cs:hLibModule, r14
0x180073e6f  jnz     loc_180073F49
0x180073e75  mov     rbx, [rbp+lpLibFileName]
0x180073e79  xor     edx, edx; hFile
0x180073e7b  mov     rcx, rbx; lpLibFileName
0x180073e7e  lea     r8d, [rdx+8]; dwFlags
0x180073e82  call    cs:__imp_LoadLibraryExW
0x180073e89  nop     dword ptr [rax+rax+00h]
0x180073e8e  mov     cs:hLibModule, rax
0x180073e95  test    rbx, rbx
0x180073e98  jz      short loc_180073EAA
0x180073e9a  lea     rcx, [rbx-8]; void *
0x180073e9e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180073ea3  mov     rax, cs:hLibModule
0x180073eaa  test    rax, rax
0x180073ead  jnz     short loc_180073EDD
0x180073eaf  call    cs:__imp_GetLastError
0x180073eb6  nop     dword ptr [rax+rax+00h]
0x180073ebb  mov     ebx, eax
0x180073ebd  test    eax, eax
0x180073ebf  jle     short loc_180073ECA
0x180073ec1  movzx   ebx, ax
0x180073ec4  or      ebx, 80070000h
0x180073eca  cmp     ebx, 8007007Eh
0x180073ed0  mov     eax, 80004001h
0x180073ed5  cmovz   ebx, eax
0x180073ed8  jmp     loc_180073FF4
0x180073edd  lea     rdx, aSfpinitialize; "SfpInitialize"
0x180073ee4  mov     rcx, rax; hModule
0x180073ee7  call    cs:__imp_GetProcAddress
0x180073eee  nop     dword ptr [rax+rax+00h]
0x180073ef3  mov     cs:qword_1800D2D90, rax
0x180073efa  test    rax, rax
0x180073efd  jnz     short loc_180073F23
0x180073eff  call    cs:__imp_GetLastError
0x180073f06  nop     dword ptr [rax+rax+00h]
0x180073f0b  mov     ebx, eax
0x180073f0d  test    eax, eax
0x180073f0f  jle     loc_180073FF4
0x180073f15  movzx   ebx, ax
0x180073f18  or      ebx, 80070000h
0x180073f1e  jmp     loc_180073FF4
0x180073f23  mov     rcx, cs:hLibModule; hModule
0x180073f2a  lea     rdx, aSfpfinalize; "SfpFinalize"
0x180073f31  call    cs:__imp_GetProcAddress
0x180073f38  nop     dword ptr [rax+rax+00h]
0x180073f3d  mov     cs:qword_1800D2D78, rax
0x180073f44  test    rax, rax
0x180073f47  jz      short loc_180073EFF
0x180073f49  mov     rcx, cs:qword_1800D2D80
0x180073f50  test    rcx, rcx
0x180073f53  jnz     short loc_180073FCA
0x180073f55  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x180073f59  mov     ecx, 1; dwMemContext
0x180073f5e  call    cs:__imp_CoGetMalloc
0x180073f65  nop     dword ptr [rax+rax+00h]
0x180073f6a  mov     ebx, eax
0x180073f6c  test    eax, eax
0x180073f6e  js      loc_180073FF4
0x180073f74  mov     rcx, [rbp+ppMalloc]
0x180073f78  lea     rax, qword_1800D2D80
0x180073f7f  mov     [rsp+70h+var_40], rax
0x180073f84  lea     r9, WrpUtilInstanceCreated
0x180073f8b  lea     rax, RtlFinalizeSmartLBlobUcsWritingContext
0x180073f92  mov     [rsp+70h+var_48], rax
0x180073f97  lea     r8, RtlFinalizeSmartLBlobUcsWritingContext
0x180073f9e  lea     rax, WrpUtilInstanceDestroyed
0x180073fa5  mov     [rsp+70h+var_50], rax
0x180073faa  lea     rdx, ?Init@CCbsLogMonitorProvider@@UEAA?AW4tagLOGRESULT@@PEAXPEAVILogContext@@@Z; CCbsLogMonitorProvider::Init(void *,ILogContext *)
0x180073fb1  mov     rax, cs:qword_1800D2D90
0x180073fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073fbd  mov     ebx, eax
0x180073fbf  test    eax, eax
0x180073fc1  js      short loc_180073FF4
0x180073fc3  mov     rcx, cs:qword_1800D2D80
0x180073fca  mov     rax, [rcx]
0x180073fcd  lea     r9, [rbp+var_20]
0x180073fd1  lea     r8, _GUID_90ed9faa_a6e5_4671_8e50_1c060f8b9c47
0x180073fd8  xor     edx, edx
0x180073fda  mov     rax, [rax+18h]
0x180073fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073fe3  mov     ebx, eax
0x180073fe5  test    eax, eax
0x180073fe7  js      short loc_180073FF4
0x180073fe9  mov     rax, [rbp+var_20]
0x180073fed  mov     [rsi], rax
0x180073ff0  mov     [rbp+var_20], r14
0x180073ff4  mov     rcx, [rbp+var_20]
0x180073ff8  test    rcx, rcx
0x180073ffb  jz      short loc_180074009
0x180073ffd  mov     rax, [rcx]
0x180074000  mov     rax, [rax+10h]
0x180074004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074009  mov     rcx, [rbp+ppMalloc]
0x18007400d  test    rcx, rcx
0x180074010  jz      short loc_18007401E
0x180074012  mov     rax, [rcx]
0x180074015  mov     rax, [rax+10h]
0x180074019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007401e  test    ebx, ebx
0x180074020  jns     short loc_180074051
0x180074022  mov     rcx, cs:hLibModule; hLibModule
0x180074029  test    rcx, rcx
0x18007402c  jz      short loc_180074051
0x18007402e  cmp     cs:qword_1800D2D80, r14
0x180074035  jnz     short loc_180074051
0x180074037  call    cs:__imp_FreeLibrary
0x18007403e  nop     dword ptr [rax+rax+00h]
0x180074043  mov     cs:hLibModule, r14
0x18007404a  mov     cs:qword_1800D2D90, r14
0x180074051  mov     eax, ebx
0x180074053  jmp     short loc_18007405A
0x180074055  mov     eax, 80070057h
0x18007405a  mov     rcx, [rbp+var_10]
0x18007405e  xor     rcx, rsp; StackCookie
0x180074061  call    __security_check_cookie
0x180074066  lea     r11, [rsp+70h+var_s0]
0x18007406b  mov     rbx, [r11+30h]
0x18007406f  mov     rsi, [r11+38h]
0x180074073  mov     rsp, r11
0x180074076  pop     r14
0x180074078  pop     rdi
0x180074079  pop     rbp
0x18007407a  retn
```
