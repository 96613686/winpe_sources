# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x1800016b0`
- end: `0x180001889`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `473`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001644`
- `0x18011ae3c`
- `0x180139fd0`
- `0x180307b14`
- `0x180307c38`

## callees

- `0x1800016b0`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800017d6`
- `KERNEL32!GetLastError` at `0x1800017d6`
- `KERNEL32!SetLastError` at `0x18000177f`
- `KERNEL32!SetLastError` at `0x18000177f`
- `KERNEL32!LoadLibraryW` at `0x180001855`
- `KERNEL32!LoadLibraryW` at `0x180001855`
- `KERNEL32!GetModuleFileNameW` at `0x180001764`
- `KERNEL32!GetModuleFileNameW` at `0x180001764`
- `KERNEL32!GetModuleHandleExW` at `0x18000173c`
- `KERNEL32!GetModuleHandleExW` at `0x18000173c`
- `KERNEL32!CreateActCtxW` at `0x1800017c5`
- `KERNEL32!CreateActCtxW` at `0x1800017c5`
- `KERNEL32!ActivateActCtx` at `0x180001819`
- `KERNEL32!ActivateActCtx` at `0x180001819`
- `KERNEL32!DeactivateActCtx` at `0x180001863`
- `KERNEL32!DeactivateActCtx` at `0x180380923`
- `KERNEL32!DeactivateActCtx` at `0x180001863`
- `KERNEL32!DeactivateActCtx` at `0x180380923`
- `KERNEL32!FindActCtxSectionStringW` at `0x180001844`
- `KERNEL32!FindActCtxSectionStringW` at `0x180001844`
- `KERNEL32!QueryActCtxW` at `0x180001711`
- `KERNEL32!QueryActCtxW` at `0x180001711`

## string_xrefs

- `0x180001835`: `Comctl32.dll`
- `0x18000184e`: `Comctl32.dll`

## pseudocode

```c
__int64 WinbaseIsolationAwarePrivatetRgzlnPgpgk()
{
  unsigned int v0; // ebx
  HANDLE ActCtxW; // rax
  DWORD LastError; // eax
  ULONG_PTR Cookie; // [rsp+40h] [rbp-2B8h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp-2B0h] BYREF
  HANDLE hActCtx[2]; // [rsp+50h] [rbp-2A8h] BYREF
  struct tagACTCTX_SECTION_KEYED_DATA pActCtx; // [rsp+60h] [rbp-298h] BYREF
  WCHAR Filename[260]; // [rsp+D0h] [rbp-228h] BYREF
  int v9; // [rsp+2D8h] [rbp-20h]

  v0 = 0;
  Cookie = 0;
  if ( WinbaseIsolationAwarePrivateT_UnPgpgk != (HANDLE)-1LL )
    return 1;
  if ( QueryActCtxW(0x80000010, &WinbaseIsolationAwarePrivateT_UnPgpgk, 0, 1u, hActCtx, 0x10u, 0) )
  {
    ActCtxW = hActCtx[0];
    if ( hActCtx[0] )
      goto LABEL_15;
    if ( GetModuleHandleExW(6u, (LPCWSTR)&WinbaseIsolationAwarePrivateT_UnPgpgk, &phModule) )
    {
      v9 = 0;
      if ( GetModuleFileNameW(phModule, Filename, 0x105u) )
      {
        if ( (_WORD)v9 )
        {
          SetLastError(0x6Fu);
          return v0;
        }
        pActCtx.cbSize = 56;
        pActCtx.ulDataFormatVersion = 136;
        pActCtx.lpData = Filename;
        *(_QWORD *)&pActCtx.ulSectionGlobalDataLength = 3;
        *(_QWORD *)&pActCtx.ulSectionTotalLength = phModule;
        ActCtxW = CreateActCtxW((PCACTCTXW)&pActCtx);
        hActCtx[0] = ActCtxW;
        if ( ActCtxW != (HANDLE)-1LL )
          goto LABEL_14;
        LastError = GetLastError();
        if ( LastError == 1812 || LastError == 1813 || LastError == 1815 || LastError == 1814 )
        {
          ActCtxW = 0;
          hActCtx[0] = 0;
LABEL_14:
          WinbaseIsolationAwarePrivateT_SpeRNgRQnPgpgk = 1;
LABEL_15:
          WinbaseIsolationAwarePrivateT_UnPgpgk = ActCtxW;
          if ( ActivateActCtx(ActCtxW, &Cookie) )
          {
            pActCtx.cbSize = 112;
            if ( FindActCtxSectionStringW(0, 0, 2u, L"Comctl32.dll", &pActCtx) )
              LoadLibraryW(L"Comctl32.dll");
            DeactivateActCtx(0, Cookie);
          }
          return 1;
        }
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800016b0  push    rbx
0x1800016b2  mov     eax, 2F0h
0x1800016b7  call    _alloca_probe
0x1800016bc  sub     rsp, rax
0x1800016bf  mov     rax, cs:__security_cookie
0x1800016c6  xor     rax, rsp
0x1800016c9  mov     [rsp+2F8h+var_18], rax
0x1800016d1  xor     ebx, ebx
0x1800016d3  mov     [rsp+2F8h+Cookie], rbx
0x1800016d8  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x1800016e0  jnz     loc_180001869
0x1800016e6  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x1800016eb  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x1800016f4  lea     rax, [rsp+2F8h+hActCtx]
0x1800016f9  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x1800016fe  lea     r9d, [rbx+1]; ulInfoClass
0x180001702  xor     r8d, r8d; pvSubInstance
0x180001705  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18000170c  mov     ecx, 80000010h; dwFlags
0x180001711  call    cs:__imp_QueryActCtxW
0x180001717  test    eax, eax
0x180001719  jz      loc_18000186E
0x18000171f  mov     rax, [rsp+2F8h+hActCtx]
0x180001724  test    rax, rax
0x180001727  jnz     loc_18000180A
0x18000172d  lea     r8, [rsp+2F8h+phModule]; phModule
0x180001732  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x180001739  lea     ecx, [rbx+6]; dwFlags
0x18000173c  call    cs:__imp_GetModuleHandleExW
0x180001742  test    eax, eax
0x180001744  jz      loc_18000186E
0x18000174a  mov     [rsp+2F8h+var_20], ebx
0x180001751  mov     r8d, 105h; nSize
0x180001757  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18000175f  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180001764  call    cs:__imp_GetModuleFileNameW
0x18000176a  test    eax, eax
0x18000176c  jz      loc_18000186E
0x180001772  cmp     word ptr [rsp+2F8h+var_20], bx
0x18000177a  jz      short loc_18000178A
0x18000177c  lea     ecx, [rbx+6Fh]; dwErrCode
0x18000177f  call    cs:__imp_SetLastError
0x180001785  jmp     loc_18000186E
0x18000178a  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x180001792  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x18000179a  lea     rax, [rsp+2F8h+Filename]
0x1800017a2  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x1800017a7  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x1800017b3  mov     rax, [rsp+2F8h+phModule]
0x1800017b8  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x1800017c0  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x1800017c5  call    cs:__imp_CreateActCtxW
0x1800017cb  mov     [rsp+2F8h+hActCtx], rax
0x1800017d0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800017d4  jnz     short loc_180001800
0x1800017d6  call    cs:__imp_GetLastError
0x1800017dc  cmp     eax, 714h
0x1800017e1  jz      short loc_1800017F8
0x1800017e3  cmp     eax, 715h
0x1800017e8  jz      short loc_1800017F8
0x1800017ea  cmp     eax, 717h
0x1800017ef  jz      short loc_1800017F8
0x1800017f1  cmp     eax, 716h
0x1800017f6  jnz     short loc_18000186E
0x1800017f8  mov     rax, rbx
0x1800017fb  mov     [rsp+2F8h+hActCtx], rbx
0x180001800  mov     cs:WinbaseIsolationAwarePrivateT_SpeRNgRQnPgpgk, 1
0x18000180a  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180001811  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x180001816  mov     rcx, rax; hActCtx
0x180001819  call    cs:__imp_ActivateActCtx
0x18000181f  test    eax, eax
0x180001821  jz      short loc_180001869
0x180001823  mov     dword ptr [rsp+2F8h+pActCtx], 70h ; 'p'
0x18000182b  lea     rax, [rsp+2F8h+pActCtx]
0x180001830  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180001835  lea     r9, LibFileName; "Comctl32.dll"
0x18000183c  xor     edx, edx; lpExtensionGuid
0x18000183e  xor     ecx, ecx; dwFlags
0x180001840  lea     r8d, [rdx+2]; ulSectionId
0x180001844  call    cs:__imp_FindActCtxSectionStringW
0x18000184a  test    eax, eax
0x18000184c  jz      short loc_18000185C
0x18000184e  lea     rcx, LibFileName; "Comctl32.dll"
0x180001855  call    cs:__imp_LoadLibraryW
0x18000185b  nop
0x18000185c  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180001861  xor     ecx, ecx; dwFlags
0x180001863  call    cs:__imp_DeactivateActCtx
0x180001869  mov     ebx, 1
0x18000186e  mov     eax, ebx
0x180001870  mov     rcx, [rsp+2F8h+var_18]
0x180001878  xor     rcx, rsp; StackCookie
0x18000187b  call    __security_check_cookie
0x180001880  add     rsp, 2F0h
0x180001887  pop     rbx
0x180001888  retn
0x18038090b  push    rbp
0x18038090d  mov     eax, 40h ; '@'
0x180380912  call    _alloca_probe
0x180380917  sub     rsp, rax
0x18038091a  mov     rbp, rdx
0x18038091d  mov     rdx, [rbp+40h]; ulCookie
0x180380921  xor     ecx, ecx; dwFlags
0x180380923  call    cs:__imp_DeactivateActCtx
0x180380929  nop
0x18038092a  add     rsp, 40h
0x18038092e  pop     rbp
0x18038092f  retn
```
