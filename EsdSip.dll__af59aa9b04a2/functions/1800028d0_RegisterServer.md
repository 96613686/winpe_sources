# RegisterServer

- ea: `0x1800028d0`
- end: `0x180002a02`
- name: `RegisterServer`
- size: `306`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800027f0`
- `0x180002810`

## callees

- `0x1800028d0`
- `0x1800030c8`
- `0x1800032ae`

## import_xrefs

- `CRYPT32!CryptSIPAddProvider` at `0x1800029b7`
- `CRYPT32!CryptSIPAddProvider` at `0x1800029b7`
- `KERNEL32!HeapFree` at `0x1800029e5`
- `KERNEL32!HeapFree` at `0x1800029e5`
- `KERNEL32!GetProcessHeap` at `0x1800029d7`
- `KERNEL32!GetProcessHeap` at `0x1800029d7`
- `KERNEL32!GetLastError` at `0x180002929`
- `KERNEL32!GetLastError` at `0x180002929`

## string_xrefs

- `0x180002974`: `EsdSipCreateHash`

## pseudocode

```c
__int64 __fastcall RegisterServer(GUID *a1)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  WCHAR *v4; // rax
  signed int LastError; // eax
  void *v6; // rdi
  HANDLE ProcessHeap; // rax
  SIP_ADD_NEWPROVIDER psNewProv; // [rsp+20h] [rbp-60h] BYREF
  const wchar_t *v10; // [rsp+78h] [rbp-8h]
  LPVOID lpMem; // [rsp+98h] [rbp+18h] BYREF

  lpMem = 0;
  memset_0(&psNewProv, 0, 0x60u);
  if ( *(_QWORD *)&g_pgSubject.Data1 )
  {
    return (unsigned int)-2147023649;
  }
  else
  {
    v4 = FormModuleFullPathName(v2, (LPWSTR *)&lpMem);
    lpMem = v4;
    if ( !v4 )
      goto LABEL_4;
    psNewProv.pwszDLLFileName = v4;
    *(_QWORD *)&psNewProv.cbStruct = 96;
    psNewProv.pwszIsFunctionName = L"EsdSipIsFileSupported";
    psNewProv.pwszGetFuncName = L"EsdSipGetSignature";
    psNewProv.pwszPutFuncName = L"EsdSipPutSignature";
    psNewProv.pwszCreateFuncName = L"EsdSipCreateHash";
    psNewProv.pwszVerifyFuncName = L"EsdSipVerifyHash";
    psNewProv.pwszRemoveFuncName = L"EsdSipDelSignature";
    psNewProv.pwszIsFunctionNameFmt2 = L"EsdSipIsFileSupportedName";
    v10 = L"EsdSipGetCaps";
    psNewProv.pgSubject = a1;
    psNewProv.pwszMagicNumber = 0;
    if ( CryptSIPAddProvider(&psNewProv) )
    {
      v3 = 0;
      *(_QWORD *)&g_pgSubject.Data1 = a1;
    }
    else
    {
LABEL_4:
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    v6 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800028d0  mov     [rsp-8+arg_0], rbx
0x1800028d5  mov     [rsp-8+arg_10], rdi
0x1800028da  push    rbp
0x1800028db  mov     rbp, rsp
0x1800028de  sub     rsp, 80h
0x1800028e5  mov     rdi, rcx
0x1800028e8  mov     [rbp+lpMem], 0
0x1800028f0  mov     ebx, 60h ; '`'
0x1800028f5  lea     rcx, [rbp+psNewProv]; void *
0x1800028f9  mov     r8d, ebx; Size
0x1800028fc  xor     edx, edx; Val
0x1800028fe  call    memset_0
0x180002903  cmp     qword ptr cs:?g_pgSubject@@3PEAU_GUID@@EA.Data1, 0; _GUID * g_pgSubject ...
0x18000290b  jz      short loc_180002917
0x18000290d  mov     ebx, 800704DFh
0x180002912  jmp     loc_1800029EB
0x180002917  lea     rdx, [rbp+lpMem]
0x18000291b  call    FormModuleFullPathName
0x180002920  mov     [rbp+lpMem], rax
0x180002924  test    rax, rax
0x180002927  jnz     short loc_180002947
0x180002929  call    cs:__imp_GetLastError
0x18000292f  mov     ebx, eax
0x180002931  test    eax, eax
0x180002933  jle     loc_1800029CE
0x180002939  movzx   ebx, ax
0x18000293c  or      ebx, 80070000h
0x180002942  jmp     loc_1800029CE
0x180002947  mov     [rbp+psNewProv.pwszDLLFileName], rax
0x18000294b  lea     rcx, [rbp+psNewProv]; psNewProv
0x18000294f  lea     rax, aEsdsipisfilesu_1; "EsdSipIsFileSupported"
0x180002956  mov     qword ptr [rbp+psNewProv.cbStruct], rbx
0x18000295a  mov     [rbp+psNewProv.pwszIsFunctionName], rax
0x18000295e  lea     rax, aEsdsipgetsigna_0; "EsdSipGetSignature"
0x180002965  mov     [rbp+psNewProv.pwszGetFuncName], rax
0x180002969  lea     rax, aEsdsipputsigna_0; "EsdSipPutSignature"
0x180002970  mov     [rbp+psNewProv.pwszPutFuncName], rax
0x180002974  lea     rax, aEsdsipcreateha_0; "EsdSipCreateHash"
0x18000297b  mov     [rbp+psNewProv.pwszCreateFuncName], rax
0x18000297f  lea     rax, aEsdsipverifyha_0; "EsdSipVerifyHash"
0x180002986  mov     [rbp+psNewProv.pwszVerifyFuncName], rax
0x18000298a  lea     rax, aEsdsipdelsigna_0; "EsdSipDelSignature"
0x180002991  mov     [rbp+psNewProv.pwszRemoveFuncName], rax
0x180002995  lea     rax, aEsdsipisfilesu_2; "EsdSipIsFileSupportedName"
0x18000299c  mov     [rbp+psNewProv.pwszIsFunctionNameFmt2], rax
0x1800029a0  lea     rax, aEsdsipgetcaps_0; "EsdSipGetCaps"
0x1800029a7  mov     [rbp+var_8], rax
0x1800029ab  mov     [rbp+psNewProv.pgSubject], rdi
0x1800029af  mov     [rbp+psNewProv.pwszMagicNumber], 0
0x1800029b7  call    cs:__imp_CryptSIPAddProvider
0x1800029bd  test    eax, eax
0x1800029bf  jz      loc_180002929
0x1800029c5  xor     ebx, ebx
0x1800029c7  mov     qword ptr cs:?g_pgSubject@@3PEAU_GUID@@EA.Data1, rdi; _GUID * g_pgSubject ...
0x1800029ce  mov     rdi, [rbp+lpMem]
0x1800029d2  test    rdi, rdi
0x1800029d5  jz      short loc_1800029EB
0x1800029d7  call    cs:__imp_GetProcessHeap
0x1800029dd  mov     r8, rdi; lpMem
0x1800029e0  xor     edx, edx; dwFlags
0x1800029e2  mov     rcx, rax; hHeap
0x1800029e5  call    cs:__imp_HeapFree
0x1800029eb  lea     r11, [rsp+80h+var_s0]
0x1800029f3  mov     eax, ebx
0x1800029f5  mov     rbx, [r11+10h]
0x1800029f9  mov     rdi, [r11+20h]
0x1800029fd  mov     rsp, r11
0x180002a00  pop     rbp
0x180002a01  retn
```
