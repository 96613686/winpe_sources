# CWMIBinMof::OpenFileAndLookForItIfItDoesNotExist(std::unique_ptr<ushort [0],std::default_delete<ushort [0]>> &,void * &)

- ea: `0x180018fb4`
- end: `0x180019187`
- name: `?OpenFileAndLookForItIfItDoesNotExist@CWMIBinMof@@AEAAJAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@AEAPEAX@Z`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003b94`

## callees

- `0x180003b08`
- `0x180018fb4`
- `0x180019948`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001903b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800190a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001903b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800190a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019047`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800190fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019047`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800190fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001900f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001900f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180018ff6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001913a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180018ff6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001913a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001908c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800190c6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180019105`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001915f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001916a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001908c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800190c6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180019105`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001915f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001916a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001901c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001906d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800190b0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001901c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001906d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800190b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWMIBinMof::OpenFileAndLookForItIfItDoesNotExist(WCHAR *a1, LPCWSTR *a2, _QWORD *a3)
{
  HANDLE FileW; // rax
  DWORD LastError; // esi
  WCHAR *v8; // rax
  LPWSTR v9; // rbx
  UINT SystemDirectoryW; // eax
  UINT v11; // edi
  void *v12; // rax
  WCHAR *v13; // rdi
  unsigned int v14; // edi
  HANDLE v15; // rax
  LPWSTR lpBuffer; // [rsp+70h] [rbp+8h] BYREF
  WCHAR *v17; // [rsp+78h] [rbp+10h]

  lpBuffer = a1;
  FileW = CreateFileW(*a2, 0x80000000, 1u, 0, 3u, 0, 0);
  *a3 = FileW;
  if ( FileW != (HANDLE)-1LL )
    return 0;
  LastError = GetLastError();
  v8 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(0x20Au);
  v9 = v8;
  lpBuffer = v8;
  if ( v8 )
  {
    SystemDirectoryW = GetSystemDirectoryW(v8, 0x105u);
    if ( !SystemDirectoryW )
    {
      SetLastError(LastError);
LABEL_15:
      v14 = -2147217407;
      goto LABEL_18;
    }
    if ( SystemDirectoryW > 0x104 )
    {
      v11 = SystemDirectoryW + 1;
      v12 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(SystemDirectoryW + 1, 2u));
      std::unique_ptr<unsigned short [0]>::reset(&lpBuffer, v12);
      v9 = lpBuffer;
      if ( !lpBuffer )
      {
        CWin32DefaultArena::WbemMemFree(0);
        return 2147749894LL;
      }
      if ( !GetSystemDirectoryW(lpBuffer, v11) )
        goto LABEL_15;
    }
    v13 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(0x412u);
    v17 = v13;
    if ( v13 )
    {
      if ( (int)StringCchPrintfW(v13, 0x209u, L"%s\\%s", v9, *a2) >= 0 )
      {
        v15 = CreateFileW(v13, 0x80000000, 1u, 0, 3u, 0, 0);
        *a3 = v15;
        if ( v15 != (HANDLE)-1LL )
        {
          v17 = 0;
          std::unique_ptr<unsigned short [0]>::reset(a2, v13);
          CWin32DefaultArena::WbemMemFree(0);
          v14 = 0;
          goto LABEL_18;
        }
      }
      SetLastError(LastError);
      CWin32DefaultArena::WbemMemFree(v13);
      goto LABEL_15;
    }
    CWin32DefaultArena::WbemMemFree(0);
  }
  v14 = -2147217402;
LABEL_18:
  CWin32DefaultArena::WbemMemFree(v9);
  return v14;
}

```

## disassembly

```asm
0x180018fb4  mov     rax, rsp
0x180018fb7  mov     [rax+18h], rbx
0x180018fbb  mov     [rax+8], rcx
0x180018fbf  push    rsi
0x180018fc0  push    rdi
0x180018fc1  push    r12
0x180018fc3  push    r14
0x180018fc5  push    r15
0x180018fc7  sub     rsp, 40h
0x180018fcb  mov     r15, r8
0x180018fce  mov     r14, rdx
0x180018fd1  mov     qword ptr [rax-38h], 0
0x180018fd9  mov     dword ptr [rax-40h], 0
0x180018fe0  mov     dword ptr [rax-48h], 3
0x180018fe7  xor     r9d, r9d; lpSecurityAttributes
0x180018fea  mov     edx, 80000000h; dwDesiredAccess
0x180018fef  lea     r8d, [r9+1]; dwShareMode
0x180018ff3  mov     rcx, [r14]; lpFileName
0x180018ff6  call    cs:__imp_CreateFileW
0x180018ffc  mov     [r15], rax
0x180018fff  or      r12, 0FFFFFFFFFFFFFFFFh
0x180019003  cmp     rax, r12
0x180019006  jz      short loc_18001900F
0x180019008  xor     eax, eax
0x18001900a  jmp     loc_180019172
0x18001900f  call    cs:__imp_GetLastError
0x180019015  mov     esi, eax
0x180019017  mov     ecx, 20Ah
0x18001901c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180019022  mov     rbx, rax
0x180019025  mov     [rsp+68h+lpBuffer], rax
0x18001902a  test    rax, rax
0x18001902d  jz      loc_1800190CC
0x180019033  mov     edx, 105h; uSize
0x180019038  mov     rcx, rax; lpBuffer
0x18001903b  call    cs:__imp_GetSystemDirectoryW
0x180019041  test    eax, eax
0x180019043  jnz     short loc_180019052
0x180019045  mov     ecx, esi; dwErrCode
0x180019047  call    cs:__imp_SetLastError
0x18001904d  jmp     loc_18001910B
0x180019052  cmp     eax, 104h
0x180019057  jbe     short loc_1800190AB
0x180019059  lea     edi, [rax+1]
0x18001905c  mov     ecx, edi
0x18001905e  mov     eax, 2
0x180019063  mul     rcx
0x180019066  cmovb   rax, r12
0x18001906a  mov     rcx, rax
0x18001906d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180019073  mov     rdx, rax
0x180019076  lea     rcx, [rsp+68h+lpBuffer]
0x18001907b  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort [0]>::reset(ushort *)
0x180019080  mov     rbx, [rsp+68h+lpBuffer]
0x180019085  test    rbx, rbx
0x180019088  jnz     short loc_18001909C
0x18001908a  xor     ecx, ecx
0x18001908c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180019092  mov     eax, 80041006h
0x180019097  jmp     loc_180019172
0x18001909c  mov     edx, edi; uSize
0x18001909e  mov     rcx, rbx; lpBuffer
0x1800190a1  call    cs:__imp_GetSystemDirectoryW
0x1800190a7  test    eax, eax
0x1800190a9  jz      short loc_18001910B
0x1800190ab  mov     ecx, 412h
0x1800190b0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800190b6  mov     rdi, rax
0x1800190b9  mov     [rsp+68h+arg_8], rax
0x1800190be  test    rax, rax
0x1800190c1  jnz     short loc_1800190D6
0x1800190c3  mov     rcx, rax
0x1800190c6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800190cc  mov     edi, 80041006h
0x1800190d1  jmp     loc_180019167
0x1800190d6  mov     rax, [r14]
0x1800190d9  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x1800190de  mov     r9, rbx
0x1800190e1  lea     r8, aSS_0; "%s\\%s"
0x1800190e8  mov     edx, 209h; unsigned __int64
0x1800190ed  mov     rcx, rdi; unsigned __int16 *
0x1800190f0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800190f5  test    eax, eax
0x1800190f7  jns     short loc_180019112
0x1800190f9  mov     ecx, esi; dwErrCode
0x1800190fb  call    cs:__imp_SetLastError
0x180019101  nop
0x180019102  mov     rcx, rdi
0x180019105  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001910b  mov     edi, 80041001h
0x180019110  jmp     short loc_180019167
0x180019112  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18001911b  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180019123  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18001912b  xor     r9d, r9d; lpSecurityAttributes
0x18001912e  mov     edx, 80000000h; dwDesiredAccess
0x180019133  lea     r8d, [r9+1]; dwShareMode
0x180019137  mov     rcx, rdi; lpFileName
0x18001913a  call    cs:__imp_CreateFileW
0x180019140  mov     [r15], rax
0x180019143  cmp     rax, r12
0x180019146  jz      short loc_1800190F9
0x180019148  mov     [rsp+68h+arg_8], 0
0x180019151  mov     rdx, rdi
0x180019154  mov     rcx, r14
0x180019157  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort [0]>::reset(ushort *)
0x18001915c  nop
0x18001915d  xor     ecx, ecx
0x18001915f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180019165  xor     edi, edi
0x180019167  mov     rcx, rbx
0x18001916a  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180019170  mov     eax, edi
0x180019172  mov     rbx, [rsp+68h+arg_10]
0x18001917a  add     rsp, 40h
0x18001917e  pop     r15
0x180019180  pop     r14
0x180019182  pop     r12
0x180019184  pop     rdi
0x180019185  pop     rsi
0x180019186  retn
```
