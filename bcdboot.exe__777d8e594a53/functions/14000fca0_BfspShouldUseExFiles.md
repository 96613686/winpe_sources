# BfspShouldUseExFiles

- ea: `0x14000fca0`
- end: `0x14000ff26`
- name: `BfspShouldUseExFiles`
- size: `646`
- prototype: `__int64 __fastcall(__int16, const WCHAR *, const wchar_t **, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009fd4`

## callees

- `0x140002b7c`
- `0x14000e628`
- `0x14000f838`
- `0x14000fa8c`
- `0x14000fca0`
- `0x140026612`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000fe9c`
- `KERNEL32!HeapFree` at `0x14000fe9c`
- `KERNEL32!GetProcessHeap` at `0x14000fe8e`
- `KERNEL32!GetProcessHeap` at `0x14000fe8e`
- `ntdll!NtQuerySystemInformation` at `0x14000fd38`
- `ntdll!NtQuerySystemInformation` at `0x14000fd38`

## string_xrefs

- `0x14000fd93`: `Using EX bins because bootmgfw on ESP is 2023 already.`

## pseudocode

```c
__int64 __fastcall BfspShouldUseExFiles(__int16 a1, const WCHAR *a2, const wchar_t **a3, _DWORD *a4)
{
  unsigned int IsHashInSecurityDatabase; // edi
  int v5; // ebx
  int v9; // ebx
  const wchar_t *v10; // r8
  NTSTATUS v11; // eax
  char v12; // r13
  const WCHAR *v13; // rdi
  unsigned int v14; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  wchar_t *v18; // rbx
  HANDLE ProcessHeap; // rax
  int v20; // [rsp+30h] [rbp-18h] BYREF
  int v21; // [rsp+34h] [rbp-14h]
  ULONG ReturnLength[4]; // [rsp+38h] [rbp-10h] BYREF
  __int16 SystemInformation; // [rsp+90h] [rbp+48h] BYREF
  const WCHAR *v24; // [rsp+98h] [rbp+50h]
  int v25; // [rsp+A0h] [rbp+58h] BYREF
  int v26; // [rsp+A8h] [rbp+60h] BYREF

  v24 = a2;
  IsHashInSecurityDatabase = 0;
  v5 = a1 & 0x800;
  v25 = 0;
  v21 = v5;
  v20 = 0;
  v26 = 0;
  *a3 = 0;
  *a4 = 0;
  if ( (a1 & 0x800) != 0 )
  {
    v9 = 0;
    if ( (a1 & 0x400) != 0 )
    {
      v9 = 1;
      *a4 = 1;
    }
    v10 = L"2023";
    if ( !v9 )
      v10 = L"2011";
    BfspLogMessage(2, L"Offline mode, using %ws cert binaries", v10);
    goto LABEL_7;
  }
  ReturnLength[0] = 0;
  SystemInformation = 0;
  v11 = NtQuerySystemInformation(SystemObjectInformation|0x80, &SystemInformation, 2u, ReturnLength);
  if ( v11 >= 0 )
  {
    v12 = SystemInformation;
    if ( (_BYTE)SystemInformation )
    {
      IsHashInSecurityDatabase = BfspIsHashInSecurityDatabase(2, (__int64)&qword_140028020, &v25);
      if ( !IsHashInSecurityDatabase )
      {
        if ( v25 )
        {
          BfspLogMessage(2, L"Using files signed with 2023 cert, because 2011 PCA is revoked");
          goto LABEL_18;
        }
      }
    }
  }
  else
  {
    BfspLogMessage(
      3,
      L"Failed to determine Secure Boot enablement state. Assuming disabled. NtStatus = %#x",
      (unsigned int)v11);
    v12 = 0;
  }
  v13 = v24;
  if ( (unsigned int)BfspFileExists(v24) )
  {
    v14 = BfspCheckFileCertAuthority(v13, a3);
    IsHashInSecurityDatabase = v14;
    if ( v14 )
    {
      BfspLogMessage(3, L"Failed to get cert auth of bootmgfw on ESP with SB enabled. Error code = %#x", v14);
LABEL_20:
      IsHashInSecurityDatabase = 0;
      goto LABEL_21;
    }
    if ( !wcscmp_0(*a3, L"Windows UEFI CA 2023") )
    {
      BfspLogMessage(2, L"Using EX bins because bootmgfw on ESP is 2023 already.");
LABEL_18:
      *a4 = 1;
      return IsHashInSecurityDatabase;
    }
  }
  if ( (a1 & 0x400) == 0 )
    goto LABEL_20;
  v16 = BfspIsHashInSecurityDatabase(1, (__int64)&qword_140028010, &v26);
  if ( v16 )
    BfspLogMessage(2, L"Failed to check UEFI DbDefault variable. Error code = %#x", v16);
  v17 = BfspIsHashInSecurityDatabase(0, (__int64)&qword_140028010, &v20);
  IsHashInSecurityDatabase = v17;
  if ( v17 )
  {
    BfspLogMessage(4, L"Failed to check UEFI DB variable. Error code = %#x", v17);
    v18 = (wchar_t *)*a3;
    if ( *a3 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *a3 = 0;
    }
  }
  else
  {
    if ( !v20 )
    {
      BfspLogMessage(4, L"USE_EX_BINS flag is specified, but 2023 cert is not in db");
LABEL_7:
      v5 = v21;
LABEL_21:
      if ( !*a4 && !v5 )
        BfspLogMessage(2, L"Not using Ex bins.");
      return IsHashInSecurityDatabase;
    }
    BfspLogMessage(
      2,
      L"BfspShouldUseExFiles - IsSbOn:%c Has2023PCAinDb:%c Has2023PCAinDbDefault:%c BFSVC_USE_EX_BINS:%c",
      v12 != 0 ? 121 : 110);
    if ( v12 )
      BfspLogMessage(2, L"Using Ex bins because SB is on, BFSVC_USE_EX_BINS is set, and 2023 PCA is in DB.");
    else
      BfspLogMessage(2, L"Using Ex bins because SB is off and BFSVC_USE_EX_BINS is set. ");
    *a4 = 1;
  }
  return IsHashInSecurityDatabase;
}

```

## disassembly

```asm
0x14000fca0  mov     [rsp-40h+arg_8], rdx
0x14000fca5  push    rbp
0x14000fca6  push    rbx
0x14000fca7  push    rsi
0x14000fca8  push    rdi
0x14000fca9  push    r12
0x14000fcab  push    r13
0x14000fcad  push    r14
0x14000fcaf  push    r15
0x14000fcb1  mov     rbp, rsp
0x14000fcb4  sub     rsp, 48h
0x14000fcb8  xor     edi, edi
0x14000fcba  mov     ebx, ecx
0x14000fcbc  and     ebx, 800h
0x14000fcc2  mov     [rbp+arg_10], edi
0x14000fcc5  mov     [rbp+var_14], ebx
0x14000fcc8  mov     r14, r9
0x14000fccb  mov     r15, r8
0x14000fcce  mov     [rbp+var_18], edi
0x14000fcd1  mov     r12d, ecx
0x14000fcd4  mov     [rbp+arg_18], edi
0x14000fcd7  mov     [r8], rdi
0x14000fcda  mov     [r9], edi
0x14000fcdd  jz      short loc_14000FD1C
0x14000fcdf  xor     ebx, ebx
0x14000fce1  bt      ecx, 0Ah
0x14000fce5  jnb     short loc_14000FCED
0x14000fce7  lea     ebx, [rdi+1]
0x14000fcea  mov     [r9], ebx
0x14000fced  test    ebx, ebx
0x14000fcef  lea     rax, a2011; "2011"
0x14000fcf6  lea     r8, a2023; "2023"
0x14000fcfd  mov     esi, 2
0x14000fd02  cmovz   r8, rax
0x14000fd06  lea     rdx, aOfflineModeUsi; "Offline mode, using %ws cert binaries"
0x14000fd0d  mov     ecx, esi
0x14000fd0f  call    BfspLogMessage
0x14000fd14  mov     ebx, [rbp+var_14]
0x14000fd17  jmp     loc_14000FDEF
0x14000fd1c  mov     esi, 2
0x14000fd21  mov     [rbp+ReturnLength], edi
0x14000fd24  mov     r8d, esi; SystemInformationLength
0x14000fd27  mov     [rbp+SystemInformation], di
0x14000fd2b  lea     r9, [rbp+ReturnLength]; ReturnLength
0x14000fd2f  mov     ecx, 91h; SystemInformationClass
0x14000fd34  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x14000fd38  call    cs:__imp_NtQuerySystemInformation
0x14000fd3e  test    eax, eax
0x14000fd40  jns     short loc_14000FD9C
0x14000fd42  mov     r8d, eax
0x14000fd45  lea     rdx, aFailedToDeterm; "Failed to determine Secure Boot enablem"...
0x14000fd4c  lea     ecx, [rsi+1]
0x14000fd4f  call    BfspLogMessage
0x14000fd54  mov     r13b, dil
0x14000fd57  mov     rdi, [rbp+arg_8]
0x14000fd5b  mov     rcx, rdi
0x14000fd5e  call    BfspFileExists
0x14000fd63  test    eax, eax
0x14000fd65  jz      loc_14000FE1A
0x14000fd6b  mov     rdx, r15
0x14000fd6e  mov     rcx, rdi
0x14000fd71  call    BfspCheckFileCertAuthority
0x14000fd76  mov     edi, eax
0x14000fd78  test    eax, eax
0x14000fd7a  jnz     short loc_14000FDD9
0x14000fd7c  mov     rcx, [r15]; String1
0x14000fd7f  lea     rdx, aWindowsUefiCa2; "Windows UEFI CA 2023"
0x14000fd86  call    wcscmp_0
0x14000fd8b  test    eax, eax
0x14000fd8d  jnz     loc_14000FE1A
0x14000fd93  lea     rdx, aUsingExBinsBec_0; "Using EX bins because bootmgfw on ESP i"...
0x14000fd9a  jmp     short loc_14000FDC9
0x14000fd9c  mov     r13b, byte ptr [rbp+SystemInformation]
0x14000fda0  test    r13b, r13b
0x14000fda3  jz      short loc_14000FD57
0x14000fda5  lea     r8, [rbp+arg_10]
0x14000fda9  mov     ecx, esi
0x14000fdab  lea     rdx, qword_140028020
0x14000fdb2  call    BfspIsHashInSecurityDatabase
0x14000fdb7  mov     edi, eax
0x14000fdb9  test    eax, eax
0x14000fdbb  jnz     short loc_14000FD57
0x14000fdbd  cmp     [rbp+arg_10], eax
0x14000fdc0  jz      short loc_14000FD57
0x14000fdc2  lea     rdx, aUsingFilesSign; "Using files signed with 2023 cert, beca"...
0x14000fdc9  mov     ecx, esi
0x14000fdcb  call    BfspLogMessage
0x14000fdd0  mov     dword ptr [r14], 1
0x14000fdd7  jmp     short loc_14000FE07
0x14000fdd9  mov     r8d, eax
0x14000fddc  lea     rdx, aFailedToGetCer; "Failed to get cert auth of bootmgfw on "...
0x14000fde3  mov     ecx, 3
0x14000fde8  call    BfspLogMessage
0x14000fded  xor     edi, edi
0x14000fdef  cmp     dword ptr [r14], 0
0x14000fdf3  jnz     short loc_14000FE07
0x14000fdf5  test    ebx, ebx
0x14000fdf7  jnz     short loc_14000FE07
0x14000fdf9  lea     rdx, aNotUsingExBins; "Not using Ex bins."
0x14000fe00  mov     ecx, esi
0x14000fe02  call    BfspLogMessage
0x14000fe07  mov     eax, edi
0x14000fe09  add     rsp, 48h
0x14000fe0d  pop     r15
0x14000fe0f  pop     r14
0x14000fe11  pop     r13
0x14000fe13  pop     r12
0x14000fe15  pop     rdi
0x14000fe16  pop     rsi
0x14000fe17  pop     rbx
0x14000fe18  pop     rbp
0x14000fe19  retn
0x14000fe1a  bt      r12d, 0Ah
0x14000fe1f  jnb     short loc_14000FDED
0x14000fe21  mov     ebx, 1
0x14000fe26  lea     r8, [rbp+arg_18]
0x14000fe2a  mov     ecx, ebx
0x14000fe2c  lea     rdx, qword_140028010
0x14000fe33  call    BfspIsHashInSecurityDatabase
0x14000fe38  test    eax, eax
0x14000fe3a  jz      short loc_14000FE52
0x14000fe3c  mov     r8d, eax
0x14000fe3f  lea     rdx, aFailedToCheckU; "Failed to check UEFI DbDefault variable"...
0x14000fe46  mov     ecx, esi
0x14000fe48  call    BfspLogMessage
0x14000fe4d  xor     r12d, r12d
0x14000fe50  jmp     short loc_14000FE56
0x14000fe52  mov     r12d, [rbp+arg_18]
0x14000fe56  lea     r8, [rbp+var_18]
0x14000fe5a  xor     ecx, ecx
0x14000fe5c  lea     rdx, qword_140028010
0x14000fe63  call    BfspIsHashInSecurityDatabase
0x14000fe68  mov     edi, eax
0x14000fe6a  test    eax, eax
0x14000fe6c  jz      short loc_14000FEAE
0x14000fe6e  mov     r8d, eax
0x14000fe71  lea     rdx, aFailedToCheckU_0; "Failed to check UEFI DB variable. Error"...
0x14000fe78  mov     ecx, 4
0x14000fe7d  call    BfspLogMessage
0x14000fe82  mov     rbx, [r15]
0x14000fe85  test    rbx, rbx
0x14000fe88  jz      loc_14000FE07
0x14000fe8e  call    cs:__imp_GetProcessHeap
0x14000fe94  mov     r8, rbx; lpMem
0x14000fe97  xor     edx, edx; dwFlags
0x14000fe99  mov     rcx, rax; hHeap
0x14000fe9c  call    cs:__imp_HeapFree
0x14000fea2  mov     qword ptr [r15], 0
0x14000fea9  jmp     loc_14000FE07
0x14000feae  cmp     [rbp+var_18], 0
0x14000feb2  jnz     short loc_14000FECA
0x14000feb4  lea     rdx, aUseExBinsFlagI; "USE_EX_BINS flag is specified, but 2023"...
0x14000febb  mov     ecx, 4
0x14000fec0  call    BfspLogMessage
0x14000fec5  jmp     loc_14000FD14
0x14000feca  neg     r12d
0x14000fecd  lea     rdx, aBfspshouldusee; "BfspShouldUseExFiles - IsSbOn:%c Has202"...
0x14000fed4  mov     al, r13b
0x14000fed7  mov     r9d, 79h ; 'y'
0x14000fedd  sbb     ecx, ecx
0x14000fedf  mov     [rsp+48h+var_20], r9d
0x14000fee4  and     ecx, 0Bh
0x14000fee7  add     ecx, 6Eh ; 'n'
0x14000feea  neg     al
0x14000feec  mov     [rsp+48h+var_28], ecx
0x14000fef0  mov     ecx, esi
0x14000fef2  sbb     r8d, r8d
0x14000fef5  and     r8d, 0Bh
0x14000fef9  add     r8d, 6Eh ; 'n'
0x14000fefd  call    BfspLogMessage
0x14000ff02  mov     ecx, esi
0x14000ff04  test    r13b, r13b
0x14000ff07  jnz     short loc_14000FF1D
0x14000ff09  lea     rdx, aUsingExBinsBec_1; "Using Ex bins because SB is off and BFS"...
0x14000ff10  call    BfspLogMessage
0x14000ff15  mov     [r14], ebx
0x14000ff18  jmp     loc_14000FE07
0x14000ff1d  lea     rdx, aUsingExBinsBec; "Using Ex bins because SB is on, BFSVC_U"...
0x14000ff24  jmp     short loc_14000FF10
```
