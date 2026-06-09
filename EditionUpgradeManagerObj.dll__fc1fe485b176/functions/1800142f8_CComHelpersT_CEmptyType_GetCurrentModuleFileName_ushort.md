# CComHelpersT<CEmptyType>::GetCurrentModuleFileName(ushort * *)

- ea: `0x1800142f8`
- end: `0x18001443b`
- name: `?GetCurrentModuleFileName@?$CComHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z`
- size: `323`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016078`
- `0x1800161b0`
- `0x180016320`

## callees

- `0x180001ac0`
- `0x1800090dc`
- `0x180009480`
- `0x18000b448`
- `0x18000b68c`
- `0x1800142f8`
- `0x180014450`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001435a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001435a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014411`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014411`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014402`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001436d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001436d`

## pseudocode

```c
__int64 __fastcall CComHelpersT<CEmptyType>::GetCurrentModuleFileName(_QWORD *a1)
{
  __int64 v2; // rbx
  int CurrentModuleHandle; // eax
  signed int v4; // edi
  int v5; // ecx
  DWORD ModuleFileNameW; // eax
  signed int LastError; // eax
  int StringCch; // eax
  int v9; // eax
  __int64 v10; // rax
  HANDLE ProcessHeap; // rax
  HMODULE hModule; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Filename[264]; // [rsp+30h] [rbp-D0h] BYREF

  v2 = 0;
  v14 = 0;
  hModule = 0;
  CurrentModuleHandle = CMiscHelpersT<CEmptyType>::GetCurrentModuleHandle(&hModule);
  v4 = CurrentModuleHandle;
  if ( CurrentModuleHandle < 0 )
  {
    v5 = CurrentModuleHandle;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_20;
  }
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x105u);
  Filename[260] = 0;
  if ( ModuleFileNameW )
  {
    if ( ModuleFileNameW >= 0x105 )
    {
      v4 = -2147024774;
LABEL_14:
      v5 = v4;
      goto LABEL_3;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    if ( v4 < 0 )
      goto LABEL_14;
  }
  LODWORD(hModule) = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Filename, &hModule);
  v4 = StringCch;
  if ( StringCch >= 0 )
  {
    v9 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
           Filename,
           (unsigned int)hModule,
           &v14);
    v4 = v9;
    if ( v9 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
    v2 = v14;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  if ( v4 < 0 )
    goto LABEL_14;
  v10 = v2;
  v2 = 0;
  *a1 = v10;
LABEL_20:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v2 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800142f8  push    rbp
0x1800142fa  push    rbx
0x1800142fb  push    rsi
0x1800142fc  push    rdi
0x1800142fd  lea     rbp, [rsp-158h]
0x180014305  sub     rsp, 258h
0x18001430c  mov     rax, cs:__security_cookie
0x180014313  xor     rax, rsp
0x180014316  mov     [rbp+170h+var_30], rax
0x18001431d  mov     rsi, rcx
0x180014320  xor     ebx, ebx
0x180014322  lea     rcx, [rsp+270h+hModule]
0x180014327  mov     [rsp+270h+var_248], rbx
0x18001432c  mov     [rsp+270h+hModule], rbx
0x180014331  call    ?GetCurrentModuleHandle@?$CMiscHelpersT@VCEmptyType@@@@SAJPEAPEAUHINSTANCE__@@@Z; CMiscHelpersT<CEmptyType>::GetCurrentModuleHandle(HINSTANCE__ * *)
0x180014336  mov     edi, eax
0x180014338  test    eax, eax
0x18001433a  jns     short loc_180014348
0x18001433c  mov     ecx, eax
0x18001433e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180014343  jmp     loc_1800143F6
0x180014348  mov     rcx, [rsp+270h+hModule]; hModule
0x18001434d  lea     rdx, [rsp+270h+Filename]; lpFilename
0x180014352  mov     edi, 105h
0x180014357  mov     r8d, edi; nSize
0x18001435a  call    cs:__imp_GetModuleFileNameW
0x180014360  xor     ecx, ecx
0x180014362  mov     [rbp+170h+var_38], cx
0x180014369  test    eax, eax
0x18001436b  jnz     short loc_1800143B1
0x18001436d  call    cs:__imp_GetLastError
0x180014373  mov     edi, eax
0x180014375  test    eax, eax
0x180014377  jnz     short loc_180014380
0x180014379  mov     edi, 80004005h
0x18001437e  jmp     short loc_18001438B
0x180014380  jle     short loc_18001438B
0x180014382  movzx   edi, ax
0x180014385  or      edi, 80070000h
0x18001438b  test    edi, edi
0x18001438d  js      short loc_1800143BA
0x18001438f  lea     rdx, [rsp+270h+hModule]
0x180014394  mov     dword ptr [rsp+270h+hModule], ebx
0x180014398  lea     rcx, [rsp+270h+Filename]
0x18001439d  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x1800143a2  mov     edi, eax
0x1800143a4  test    eax, eax
0x1800143a6  jns     short loc_1800143BE
0x1800143a8  mov     ecx, eax
0x1800143aa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800143af  jmp     short loc_1800143E3
0x1800143b1  cmp     eax, edi
0x1800143b3  jb      short loc_18001438F
0x1800143b5  mov     edi, 8007007Ah
0x1800143ba  mov     ecx, edi
0x1800143bc  jmp     short loc_18001433E
0x1800143be  mov     edx, dword ptr [rsp+270h+hModule]
0x1800143c2  lea     r8, [rsp+270h+var_248]
0x1800143c7  lea     rcx, [rsp+270h+Filename]; Src
0x1800143cc  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x1800143d1  mov     edi, eax
0x1800143d3  test    eax, eax
0x1800143d5  jns     short loc_1800143DE
0x1800143d7  mov     ecx, eax
0x1800143d9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800143de  mov     rbx, [rsp+270h+var_248]
0x1800143e3  mov     ecx, edi
0x1800143e5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800143ea  test    edi, edi
0x1800143ec  js      short loc_1800143BA
0x1800143ee  mov     rax, rbx
0x1800143f1  xor     ebx, ebx
0x1800143f3  mov     [rsi], rax
0x1800143f6  mov     ecx, edi
0x1800143f8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800143fd  test    rbx, rbx
0x180014400  jz      short loc_18001441E
0x180014402  call    cs:__imp_GetProcessHeap
0x180014408  lea     r8, [rbx-4]; lpMem
0x18001440c  xor     edx, edx; dwFlags
0x18001440e  mov     rcx, rax; hHeap
0x180014411  call    cs:__imp_HeapFree
0x180014417  xor     ecx, ecx
0x180014419  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001441e  mov     eax, edi
0x180014420  mov     rcx, [rbp+170h+var_30]
0x180014427  xor     rcx, rsp; StackCookie
0x18001442a  call    __security_check_cookie
0x18001442f  add     rsp, 258h
0x180014436  pop     rdi
0x180014437  pop     rsi
0x180014438  pop     rbx
0x180014439  pop     rbp
0x18001443a  retn
```
