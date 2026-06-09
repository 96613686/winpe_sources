# SfpCreateOfflineRepairObject

- ea: `0x180074040`
- end: `0x1800742dc`
- name: `SfpCreateOfflineRepairObject`
- size: `668`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180022ef0`
- `0x1800293a0`
- `0x180073d34`
- `0x180074040`
- `0x180074408`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007410f`
- `KERNEL32!GetLastError` at `0x18007415f`
- `KERNEL32!GetLastError` at `0x18007410f`
- `KERNEL32!GetLastError` at `0x18007415f`
- `KERNEL32!GetProcAddress` at `0x180074147`
- `KERNEL32!GetProcAddress` at `0x180074191`
- `KERNEL32!GetProcAddress` at `0x180074147`
- `KERNEL32!GetProcAddress` at `0x180074191`
- `KERNEL32!LoadLibraryExW` at `0x1800740e2`
- `KERNEL32!LoadLibraryExW` at `0x1800740e2`
- `KERNEL32!FreeLibrary` at `0x180074297`
- `KERNEL32!FreeLibrary` at `0x180074297`
- `OLE32!CoGetMalloc` at `0x1800741be`
- `OLE32!CoGetMalloc` at `0x1800741be`

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
        qword_1800D4D80 = (__int64)GetProcAddress(Library, "SfpInitialize");
        if ( !qword_1800D4D80 || (qword_1800D4D68 = (__int64)GetProcAddress(hLibModule, "SfpFinalize")) == 0 )
        {
          v10 = GetLastError();
          OfflineStackFromWindir = v10;
          if ( v10 > 0 )
            OfflineStackFromWindir = (unsigned __int16)v10 | 0x80070000;
          goto LABEL_26;
        }
      }
      v11 = qword_1800D4D70;
      if ( qword_1800D4D70 )
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
        OfflineStackFromWindir = ((__int64 (__fastcall *)(LPMALLOC, void *, __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 *))qword_1800D4D80)(
                                   ppMalloc,
                                   &CCbsLogMonitorProvider::Init,
                                   RtlFinalizeSmartLBlobUcsWritingContext,
                                   WrpUtilInstanceCreated,
                                   WrpUtilInstanceDestroyed,
                                   RtlFinalizeSmartLBlobUcsWritingContext,
                                   &qword_1800D4D70);
        if ( OfflineStackFromWindir >= 0 )
        {
          v11 = qword_1800D4D70;
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
  if ( OfflineStackFromWindir < 0 && hLibModule && !qword_1800D4D70 )
  {
    FreeLibrary(hLibModule);
    hLibModule = 0;
    qword_1800D4D80 = 0;
  }
  return (unsigned int)OfflineStackFromWindir;
}

```

## disassembly

```asm
0x180074040  mov     [rsp-18h+arg_10], rbx
0x180074045  mov     [rsp-18h+arg_18], rsi
0x18007404a  push    rbp
0x18007404b  push    rdi
0x18007404c  push    r14
0x18007404e  mov     rbp, rsp
0x180074051  sub     rsp, 70h
0x180074055  mov     rax, cs:__security_cookie
0x18007405c  xor     rax, rsp
0x18007405f  mov     [rbp+var_10], rax
0x180074063  xor     r14d, r14d
0x180074066  mov     rsi, rdx
0x180074069  mov     [rbp+lpLibFileName], r14
0x18007406d  mov     rdi, rcx
0x180074070  mov     [rbp+ppMalloc], r14
0x180074074  mov     [rbp+var_20], r14
0x180074078  mov     [rbp+var_30], r14d
0x18007407c  test    rcx, rcx
0x18007407f  jz      loc_1800742B5
0x180074085  cmp     [rcx], r14w
0x180074089  jz      loc_1800742B5
0x18007408f  lea     rdx, [rbp+var_30]
0x180074093  call    IsOnlineWindows
0x180074098  mov     ebx, eax
0x18007409a  test    eax, eax
0x18007409c  js      loc_180074254
0x1800740a2  cmp     [rbp+var_30], r14d
0x1800740a6  jz      short loc_1800740B2
0x1800740a8  mov     eax, 80042000h
0x1800740ad  jmp     loc_1800742BA
0x1800740b2  lea     rdx, [rbp+lpLibFileName]; unsigned __int16 **
0x1800740b6  mov     rcx, rdi; wchar_t *
0x1800740b9  call    ?GetOfflineStackFromWindir@@YAJPEBGPEAPEAG@Z; GetOfflineStackFromWindir(ushort const *,ushort * *)
0x1800740be  mov     ebx, eax
0x1800740c0  test    eax, eax
0x1800740c2  js      loc_180074254
0x1800740c8  cmp     cs:hLibModule, r14
0x1800740cf  jnz     loc_1800741A9
0x1800740d5  mov     rbx, [rbp+lpLibFileName]
0x1800740d9  xor     edx, edx; hFile
0x1800740db  mov     rcx, rbx; lpLibFileName
0x1800740de  lea     r8d, [rdx+8]; dwFlags
0x1800740e2  call    cs:__imp_LoadLibraryExW
0x1800740e9  nop     dword ptr [rax+rax+00h]
0x1800740ee  mov     cs:hLibModule, rax
0x1800740f5  test    rbx, rbx
0x1800740f8  jz      short loc_18007410A
0x1800740fa  lea     rcx, [rbx-8]; void *
0x1800740fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180074103  mov     rax, cs:hLibModule
0x18007410a  test    rax, rax
0x18007410d  jnz     short loc_18007413D
0x18007410f  call    cs:__imp_GetLastError
0x180074116  nop     dword ptr [rax+rax+00h]
0x18007411b  mov     ebx, eax
0x18007411d  test    eax, eax
0x18007411f  jle     short loc_18007412A
0x180074121  movzx   ebx, ax
0x180074124  or      ebx, 80070000h
0x18007412a  cmp     ebx, 8007007Eh
0x180074130  mov     eax, 80004001h
0x180074135  cmovz   ebx, eax
0x180074138  jmp     loc_180074254
0x18007413d  lea     rdx, aSfpinitialize; "SfpInitialize"
0x180074144  mov     rcx, rax; hModule
0x180074147  call    cs:__imp_GetProcAddress
0x18007414e  nop     dword ptr [rax+rax+00h]
0x180074153  mov     cs:qword_1800D4D80, rax
0x18007415a  test    rax, rax
0x18007415d  jnz     short loc_180074183
0x18007415f  call    cs:__imp_GetLastError
0x180074166  nop     dword ptr [rax+rax+00h]
0x18007416b  mov     ebx, eax
0x18007416d  test    eax, eax
0x18007416f  jle     loc_180074254
0x180074175  movzx   ebx, ax
0x180074178  or      ebx, 80070000h
0x18007417e  jmp     loc_180074254
0x180074183  mov     rcx, cs:hLibModule; hModule
0x18007418a  lea     rdx, aSfpfinalize; "SfpFinalize"
0x180074191  call    cs:__imp_GetProcAddress
0x180074198  nop     dword ptr [rax+rax+00h]
0x18007419d  mov     cs:qword_1800D4D68, rax
0x1800741a4  test    rax, rax
0x1800741a7  jz      short loc_18007415F
0x1800741a9  mov     rcx, cs:qword_1800D4D70
0x1800741b0  test    rcx, rcx
0x1800741b3  jnz     short loc_18007422A
0x1800741b5  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x1800741b9  mov     ecx, 1; dwMemContext
0x1800741be  call    cs:__imp_CoGetMalloc
0x1800741c5  nop     dword ptr [rax+rax+00h]
0x1800741ca  mov     ebx, eax
0x1800741cc  test    eax, eax
0x1800741ce  js      loc_180074254
0x1800741d4  mov     rcx, [rbp+ppMalloc]
0x1800741d8  lea     rax, qword_1800D4D70
0x1800741df  mov     [rsp+70h+var_40], rax
0x1800741e4  lea     r9, WrpUtilInstanceCreated
0x1800741eb  lea     rax, RtlFinalizeSmartLBlobUcsWritingContext
0x1800741f2  mov     [rsp+70h+var_48], rax
0x1800741f7  lea     r8, RtlFinalizeSmartLBlobUcsWritingContext
0x1800741fe  lea     rax, WrpUtilInstanceDestroyed
0x180074205  mov     [rsp+70h+var_50], rax
0x18007420a  lea     rdx, ?Init@CCbsLogMonitorProvider@@UEAA?AW4tagLOGRESULT@@PEAXPEAVILogContext@@@Z; CCbsLogMonitorProvider::Init(void *,ILogContext *)
0x180074211  mov     rax, cs:qword_1800D4D80
0x180074218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007421d  mov     ebx, eax
0x18007421f  test    eax, eax
0x180074221  js      short loc_180074254
0x180074223  mov     rcx, cs:qword_1800D4D70
0x18007422a  mov     rax, [rcx]
0x18007422d  lea     r9, [rbp+var_20]
0x180074231  lea     r8, _GUID_90ed9faa_a6e5_4671_8e50_1c060f8b9c47
0x180074238  xor     edx, edx
0x18007423a  mov     rax, [rax+18h]
0x18007423e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074243  mov     ebx, eax
0x180074245  test    eax, eax
0x180074247  js      short loc_180074254
0x180074249  mov     rax, [rbp+var_20]
0x18007424d  mov     [rsi], rax
0x180074250  mov     [rbp+var_20], r14
0x180074254  mov     rcx, [rbp+var_20]
0x180074258  test    rcx, rcx
0x18007425b  jz      short loc_180074269
0x18007425d  mov     rax, [rcx]
0x180074260  mov     rax, [rax+10h]
0x180074264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074269  mov     rcx, [rbp+ppMalloc]
0x18007426d  test    rcx, rcx
0x180074270  jz      short loc_18007427E
0x180074272  mov     rax, [rcx]
0x180074275  mov     rax, [rax+10h]
0x180074279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007427e  test    ebx, ebx
0x180074280  jns     short loc_1800742B1
0x180074282  mov     rcx, cs:hLibModule; hLibModule
0x180074289  test    rcx, rcx
0x18007428c  jz      short loc_1800742B1
0x18007428e  cmp     cs:qword_1800D4D70, r14
0x180074295  jnz     short loc_1800742B1
0x180074297  call    cs:__imp_FreeLibrary
0x18007429e  nop     dword ptr [rax+rax+00h]
0x1800742a3  mov     cs:hLibModule, r14
0x1800742aa  mov     cs:qword_1800D4D80, r14
0x1800742b1  mov     eax, ebx
0x1800742b3  jmp     short loc_1800742BA
0x1800742b5  mov     eax, 80070057h
0x1800742ba  mov     rcx, [rbp+var_10]
0x1800742be  xor     rcx, rsp; StackCookie
0x1800742c1  call    __security_check_cookie
0x1800742c6  lea     r11, [rsp+70h+var_s0]
0x1800742cb  mov     rbx, [r11+30h]
0x1800742cf  mov     rsi, [r11+38h]
0x1800742d3  mov     rsp, r11
0x1800742d6  pop     r14
0x1800742d8  pop     rdi
0x1800742d9  pop     rbp
0x1800742da  retn
```
