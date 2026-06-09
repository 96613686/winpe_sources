# VfpSettings::getTheAppDataDir(Vencoding)

- ea: `0x18004fab0`
- end: `0x18004fcfd`
- name: `?getTheAppDataDir@VfpSettings@@MEAA?AVVstring@@W4Vencoding@@@Z`
- size: `589`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180040c10`
- `0x18004e380`
- `0x18004fab0`
- `0x1800838f0`
- `0x180090610`
- `0x180095100`
- `0x180134070`
- `0x1801503e0`
- `0x1801519a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004fbb9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004fbe9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004fc3b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004fccd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004fbb9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004fbe9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004fc3b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004fccd`
- `SHELL32!SHGetMalloc` at `0x18004fc46`
- `SHELL32!SHGetMalloc` at `0x18004fc46`
- `SHELL32!SHGetPathFromIDListW` at `0x18004fb45`
- `SHELL32!SHGetPathFromIDListW` at `0x18004fb45`
- `SHELL32!SHGetSpecialFolderLocation` at `0x18004fb1f`
- `SHELL32!SHGetSpecialFolderLocation` at `0x18004fb1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
_QWORD *__fastcall VfpSettings::getTheAppDataDir(__int64 a1, _QWORD *a2, int a3)
{
  int *v5; // rcx
  int *v6; // rcx
  int *v7; // rcx
  IMalloc *v8; // rcx
  Vstring *FPTempDir; // rax
  int *v10; // rcx
  LPITEMIDLIST ppidl; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v13; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C8h] BYREF
  IMalloc *ppMalloc; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v17[6]; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+88h] [rbp-80h] BYREF

  v17[3] = -2;
  v17[4] = a2;
  *a2 = dword_1802AFD5C;
  _InterlockedIncrement(&dword_1802AFD50);
  ppidl = 0;
  if ( SHGetSpecialFolderLocation(0, 26, &ppidl) >= 0 )
  {
    pszPath[0] = 0;
    if ( SHGetPathFromIDListW(ppidl, pszPath) )
    {
      Vstring::Vstring((Vstring *)&v14, L"Microsoft");
      Vstring::Vstring((Vstring *)&v13, pszPath);
      Vpath::Vpath((Vpath *)v17, (const struct Vstring *)&v13, (const struct Vstring *)&v14, Class);
      v5 = (int *)(v13 - 12);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 - 12), 0xFFFFFFFF) == 1 && v5 != &dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v5);
        else
          free(v5);
      }
      v6 = (int *)(v14 - 12);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14 - 12), 0xFFFFFFFF) == 1 && v6 != &dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v6);
        else
          free(v6);
      }
      RWCString::operator=(a2, v17);
      Vpath::ClearStat((Vpath *)v17);
      v17[5] = v17;
      v7 = (int *)(v17[0] - 12LL);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17[0] - 12LL), 0xFFFFFFFF) == 1
        && v7 != &dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v7);
        else
          free(v7);
      }
    }
    if ( SHGetMalloc(&ppMalloc) >= 0 )
    {
      v8 = ppMalloc;
      if ( ppMalloc )
      {
        if ( ppidl )
        {
          ((void (__fastcall *)(IMalloc *))ppMalloc->lpVtbl->Free)(ppMalloc);
          v8 = ppMalloc;
        }
        ((void (__fastcall *)(IMalloc *))v8->lpVtbl->Release)(v8);
      }
    }
  }
  if ( !*(_DWORD *)(*a2 - 4LL) )
  {
    FPTempDir = VfpSettings::getFPTempDir((Vstring *)&v16, a3);
    RWCString::operator=(a2, FPTempDir);
    v10 = (int *)(v16 - 12);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v16 - 12), 0xFFFFFFFF) == 1 && v10 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v10);
      else
        free(v10);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18004fab0  mov     rax, rsp
0x18004fab3  push    rbp
0x18004fab4  push    rsi
0x18004fab5  push    rdi
0x18004fab6  push    r14
0x18004fab8  push    r15
0x18004faba  lea     rbp, [rax-1C8h]
0x18004fac1  sub     rsp, 2A0h
0x18004fac8  mov     [rsp+2C0h+var_258], 0FFFFFFFFFFFFFFFEh
0x18004fad1  mov     [rax+8], rbx
0x18004fad5  mov     rax, cs:__security_cookie
0x18004fadc  xor     rax, rsp
0x18004fadf  mov     [rbp+1C0h+var_30], rax
0x18004fae6  mov     edi, r8d
0x18004fae9  mov     rbx, rdx
0x18004faec  mov     [rsp+2C0h+var_250], rdx
0x18004faf1  xor     esi, esi
0x18004faf3  mov     dword ptr [rsp+2C0h+var_2A0], esi
0x18004faf7  lea     rax, dword_1802AFD5C
0x18004fafe  mov     [rdx], rax
0x18004fb01  lock inc cs:dword_1802AFD50
0x18004fb08  mov     dword ptr [rsp+2C0h+var_2A0], 1
0x18004fb10  mov     [rsp+2C0h+ppidl], rsi
0x18004fb15  lea     r8, [rsp+2C0h+ppidl]; ppidl
0x18004fb1a  lea     edx, [rsi+1Ah]; csidl
0x18004fb1d  xor     ecx, ecx; hwnd
0x18004fb1f  call    cs:SHGetSpecialFolderLocation
0x18004fb25  or      r14d, 0FFFFFFFFh
0x18004fb29  lea     r15, dword_1802AFD50
0x18004fb30  test    eax, eax
0x18004fb32  js      loc_18004FC83
0x18004fb38  mov     [rbp+1C0h+pszPath], si
0x18004fb3c  lea     rdx, [rbp+1C0h+pszPath]; pszPath
0x18004fb40  mov     rcx, [rsp+2C0h+ppidl]; pidl
0x18004fb45  call    cs:SHGetPathFromIDListW
0x18004fb4b  test    eax, eax
0x18004fb4d  jz      loc_18004FC41
0x18004fb53  lea     rdx, aMicrosoft_0; "Microsoft"
0x18004fb5a  lea     rcx, [rsp+2C0h+var_288]; this
0x18004fb5f  call    ??0Vstring@@QEAA@PEB_W@Z; Vstring::Vstring(wchar_t const *)
0x18004fb64  nop
0x18004fb65  lea     rdx, [rbp+1C0h+pszPath]; wchar_t *
0x18004fb69  lea     rcx, [rsp+2C0h+var_290]; this
0x18004fb6e  call    ??0Vstring@@QEAA@PEB_W@Z; Vstring::Vstring(wchar_t const *)
0x18004fb73  nop
0x18004fb74  lea     r9, Class; char *
0x18004fb7b  lea     r8, [rsp+2C0h+var_288]; struct Vstring *
0x18004fb80  lea     rdx, [rsp+2C0h+var_290]; struct Vstring *
0x18004fb85  lea     rcx, [rsp+2C0h+var_270]; this
0x18004fb8a  call    ??0Vpath@@QEAA@AEBVVstring@@0PEBD@Z; Vpath::Vpath(Vstring const &,Vstring const &,char const *)
0x18004fb8f  nop
0x18004fb90  mov     rcx, [rsp+2C0h+var_290]
0x18004fb95  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18004fb99  mov     eax, r14d
0x18004fb9c  lock xadd [rcx], eax
0x18004fba0  add     eax, r14d
0x18004fba3  jnz     short loc_18004FBC0
0x18004fba5  cmp     rcx, r15
0x18004fba8  jz      short loc_18004FBC0
0x18004fbaa  cmp     cs:dword_1802B0018, esi
0x18004fbb0  jz      short loc_18004FBB9
0x18004fbb2  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18004fbb7  jmp     short loc_18004FBC0
0x18004fbb9  call    cs:free
0x18004fbbf  nop
0x18004fbc0  mov     rcx, [rsp+2C0h+var_288]
0x18004fbc5  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18004fbc9  mov     eax, r14d
0x18004fbcc  lock xadd [rcx], eax
0x18004fbd0  add     eax, r14d
0x18004fbd3  jnz     short loc_18004FBEF
0x18004fbd5  cmp     rcx, r15
0x18004fbd8  jz      short loc_18004FBEF
0x18004fbda  cmp     cs:dword_1802B0018, esi
0x18004fbe0  jz      short loc_18004FBE9
0x18004fbe2  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18004fbe7  jmp     short loc_18004FBEF
0x18004fbe9  call    cs:free
0x18004fbef  lea     rdx, [rsp+2C0h+var_270]
0x18004fbf4  mov     rcx, rbx
0x18004fbf7  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x18004fbfc  nop
0x18004fbfd  lea     rcx, [rsp+2C0h+var_270]; this
0x18004fc02  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x18004fc07  nop
0x18004fc08  lea     rax, [rsp+2C0h+var_270]
0x18004fc0d  mov     [rsp+78h], rax
0x18004fc12  mov     rcx, qword ptr [rsp+2C0h+var_270]
0x18004fc17  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18004fc1b  mov     eax, r14d
0x18004fc1e  lock xadd [rcx], eax
0x18004fc22  add     eax, r14d
0x18004fc25  jnz     short loc_18004FC41
0x18004fc27  cmp     rcx, r15
0x18004fc2a  jz      short loc_18004FC41
0x18004fc2c  cmp     cs:dword_1802B0018, esi
0x18004fc32  jz      short loc_18004FC3B
0x18004fc34  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18004fc39  jmp     short loc_18004FC41
0x18004fc3b  call    cs:free
0x18004fc41  lea     rcx, [rsp+2C0h+ppMalloc]; ppMalloc
0x18004fc46  call    cs:SHGetMalloc
0x18004fc4c  test    eax, eax
0x18004fc4e  js      short loc_18004FC83
0x18004fc50  mov     rcx, [rsp+2C0h+ppMalloc]
0x18004fc55  test    rcx, rcx
0x18004fc58  jz      short loc_18004FC83
0x18004fc5a  mov     rdx, [rsp+2C0h+ppidl]
0x18004fc5f  test    rdx, rdx
0x18004fc62  jz      short loc_18004FC76
0x18004fc64  mov     rax, [rcx]
0x18004fc67  mov     rax, [rax+28h]
0x18004fc6b  call    cs:__guard_dispatch_icall_fptr
0x18004fc71  mov     rcx, [rsp+2C0h+ppMalloc]
0x18004fc76  mov     rax, [rcx]
0x18004fc79  mov     rax, [rax+10h]
0x18004fc7d  call    cs:__guard_dispatch_icall_fptr
0x18004fc83  mov     rax, [rbx]
0x18004fc86  cmp     [rax-4], esi
0x18004fc89  jnz     short loc_18004FCD3
0x18004fc8b  mov     edx, edi
0x18004fc8d  lea     rcx, [rsp+2C0h+var_278]
0x18004fc92  call    ?getFPTempDir@VfpSettings@@SA?AVVstring@@W4Vencoding@@@Z; VfpSettings::getFPTempDir(Vencoding)
0x18004fc97  nop
0x18004fc98  mov     rdx, rax
0x18004fc9b  mov     rcx, rbx
0x18004fc9e  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x18004fca3  nop
0x18004fca4  mov     rcx, [rsp+2C0h+var_278]
0x18004fca9  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18004fcad  mov     eax, r14d
0x18004fcb0  lock xadd [rcx], eax
0x18004fcb4  add     eax, r14d
0x18004fcb7  jnz     short loc_18004FCD3
0x18004fcb9  cmp     rcx, r15
0x18004fcbc  jz      short loc_18004FCD3
0x18004fcbe  cmp     cs:dword_1802B0018, esi
0x18004fcc4  jz      short loc_18004FCCD
0x18004fcc6  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18004fccb  jmp     short loc_18004FCD3
0x18004fccd  call    cs:free
0x18004fcd3  mov     rax, rbx
0x18004fcd6  mov     rcx, [rbp+1C0h+var_30]
0x18004fcdd  xor     rcx, rsp
0x18004fce0  call    sub_1801503E0
0x18004fce5  mov     rbx, [rsp+2C0h+arg_0]
0x18004fced  add     rsp, 2A0h
0x18004fcf4  pop     r15
0x18004fcf6  pop     r14
0x18004fcf8  pop     rdi
0x18004fcf9  pop     rsi
0x18004fcfa  pop     rbp
0x18004fcfb  retn
```
