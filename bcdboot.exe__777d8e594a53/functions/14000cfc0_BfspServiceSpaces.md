# BfspServiceSpaces

- ea: `0x14000cfc0`
- end: `0x14000d2ab`
- name: `BfspServiceSpaces`
- size: `747`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x140009fd4`

## callees

- `0x140002b7c`
- `0x14000cfc0`
- `0x14000d494`
- `0x14000d918`
- `0x14000e628`
- `0x14000f50c`
- `0x14000f72c`
- `0x140012810`
- `0x14001d66c`
- `0x14002661e`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000d099`
- `KERNEL32!SetLastError` at `0x14000d0ef`
- `KERNEL32!SetLastError` at `0x14000d288`
- `KERNEL32!SetLastError` at `0x14000d099`
- `KERNEL32!SetLastError` at `0x14000d0ef`
- `KERNEL32!SetLastError` at `0x14000d288`
- `KERNEL32!GetLastError` at `0x14000cffd`
- `KERNEL32!GetLastError` at `0x14000d0d3`
- `KERNEL32!GetLastError` at `0x14000d16e`
- `KERNEL32!GetLastError` at `0x14000d1dc`
- `KERNEL32!GetLastError` at `0x14000d20f`
- `KERNEL32!GetLastError` at `0x14000d231`
- `KERNEL32!GetLastError` at `0x14000cffd`
- `KERNEL32!GetLastError` at `0x14000d0d3`
- `KERNEL32!GetLastError` at `0x14000d16e`
- `KERNEL32!GetLastError` at `0x14000d1dc`
- `KERNEL32!GetLastError` at `0x14000d20f`
- `KERNEL32!GetLastError` at `0x14000d231`
- `KERNEL32!HeapFree` at `0x14000d263`
- `KERNEL32!HeapFree` at `0x14000d27c`
- `KERNEL32!HeapFree` at `0x14000d263`
- `KERNEL32!HeapFree` at `0x14000d27c`
- `KERNEL32!GetProcessHeap` at `0x14000d255`
- `KERNEL32!GetProcessHeap` at `0x14000d26e`
- `KERNEL32!GetProcessHeap` at `0x14000d255`
- `KERNEL32!GetProcessHeap` at `0x14000d26e`
- `ntdll!RtlFreeHeap` at `0x14000d06e`
- `ntdll!RtlFreeHeap` at `0x14000d06e`
- `ntdll!RtlNtStatusToDosError` at `0x14000d07a`
- `ntdll!RtlNtStatusToDosError` at `0x14000d07a`

## string_xrefs

- `0x14000d157`: `|DEST|\bootspaces.dll`
- `0x14000d174`: `Failed to service spaces DLL. Last Error = %#x`
- `0x14000d15e`: `|SOURCE|\Misc\|FWTYPE|\bootspaces.dll`
- `0x14000d1ab`: `Failed to service spaces default bootmgr`
- `0x14000d1f8`: `|SYSPART|\|DEST|\bootspaces.dll`
- `0x14000d1e2`: `Failed to service spaces bootmgr. Last Error = %#x`
- `0x14000d23a`: `Error deleting stale spaces dll (%s)! Last Error = %#x`

## pseudocode

```c
__int64 __fastcall BfspServiceSpaces(_QWORD *a1)
{
  void *v1; // rdi
  unsigned int v3; // r15d
  wchar_t *v4; // rsi
  __int64 v5; // rbx
  unsigned __int64 v6; // rax
  bool v7; // bp
  int v8; // eax
  PVOID v9; // r8
  NTSTATUS v10; // ebx
  ULONG v11; // eax
  __int64 v12; // r8
  DWORD LastError; // eax
  const wchar_t *Value; // rax
  DWORD v15; // eax
  const wchar_t *v16; // rdx
  const wchar_t *v17; // r8
  const wchar_t *v18; // rdx
  wchar_t *v19; // rax
  __int64 v20; // rbp
  HANDLE ProcessHeap; // rax
  HANDLE v22; // rax
  _DWORD *v24; // [rsp+70h] [rbp+18h] BYREF
  PVOID P; // [rsp+78h] [rbp+20h] BYREF

  v1 = 0;
  v24 = 0;
  v3 = 1;
  v4 = BfspEnvExpandString((__int64)a1, L"|SYSPART|");
  if ( !v4 )
  {
    LODWORD(v5) = GetLastError();
    goto LABEL_30;
  }
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  if ( v6 > 1 && v4[1] == 92 )
    v4[1] = 63;
  P = 0;
  v7 = 0;
  v8 = SiQueryProperty(v4, 0, 8, &P);
  v9 = P;
  v10 = v8;
  if ( v8 >= 0 )
    v7 = *((_DWORD *)P + 7) == 16;
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v10 < 0 )
  {
    v11 = RtlNtStatusToDosError(v10);
    BfspLogMessage(3, L"Failed to determine whether the system partition is in a space. Last Error = %#x", v11);
    LODWORD(v5) = 0;
    SetLastError(0);
    goto LABEL_30;
  }
  LODWORD(v5) = 0;
  if ( !v7 )
  {
    BfspLogMessage(2, L"System partition is not in a space", v9);
    goto LABEL_30;
  }
  if ( !(unsigned int)BfspSpacesGetPhysicalPartitions(v4, &v24, v9) )
  {
    LastError = GetLastError();
    BfspLogMessage(3, L"Failed to retrieve physical partitions. Last Error = %#x", LastError);
    SetLastError(0);
    v1 = v24;
    goto LABEL_30;
  }
  v1 = v24;
  if ( !v24[2] )
  {
    BfspLogMessage(2, L"No physical partitions found", v12);
    goto LABEL_30;
  }
  BfspLogMessage(2, L"Servicing spaces files");
  Value = (const wchar_t *)BfspEnvGetValue(a1, L"FWTYPE");
  if ( !wcsncmp_0(Value, L"EFI", 4u) )
  {
    if ( !(unsigned int)BfspSpacesCopyToPhysicalPartitions(
                          (_DWORD)a1,
                          (unsigned int)L"|SYSPART|\\|DEST|\\|BOOTMGBIN|",
                          (unsigned int)L"|EFIDEFAULTDIR|\\|DEFAULTAPP|",
                          (unsigned int)L"bootmgr.exe",
                          (__int64)v1) )
      BfspLogMessage(3, L"Failed to service spaces default bootmgr");
    v17 = L"|DEST|\\|BOOTMGBIN|";
    v18 = L"|SYSPART|\\|DEST|\\|BOOTMGBIN|";
  }
  else
  {
    if ( !(unsigned int)BfspSpacesCopyToPhysicalPartitions(
                          (_DWORD)a1,
                          (unsigned int)L"|SOURCE|\\Misc\\|FWTYPE|\\bootspaces.dll",
                          (unsigned int)L"|DEST|\\bootspaces.dll",
                          0,
                          (__int64)v1) )
    {
      v15 = GetLastError();
      v16 = L"Failed to service spaces DLL. Last Error = %#x";
      goto LABEL_29;
    }
    v17 = L"|BOOTMGBIN|";
    v18 = L"|SYSPART|\\|BOOTMGBIN|";
  }
  if ( (unsigned int)BfspSpacesCopyToPhysicalPartitions((_DWORD)a1, (_DWORD)v18, (_DWORD)v17, 0, (__int64)v1) )
    goto LABEL_30;
  v15 = GetLastError();
  v16 = L"Failed to service spaces bootmgr. Last Error = %#x";
LABEL_29:
  LODWORD(v5) = v15;
  BfspLogMessage(4, v16, v15);
LABEL_30:
  v19 = BfspEnvExpandString((__int64)a1, L"|SYSPART|\\|DEST|\\bootspaces.dll");
  v20 = (__int64)v19;
  if ( v19 )
  {
    if ( (unsigned int)BfspFileExists(v19) && !DeleteFileEx2(v20) )
    {
      v5 = GetLastError();
      BfspLogMessage(4, L"Error deleting stale spaces dll (%s)! Last Error = %#x", v20, v5);
    }
  }
  else
  {
    LODWORD(v5) = GetLastError();
  }
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
  if ( v4 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v4);
  }
  if ( (_DWORD)v5 )
  {
    SetLastError(v5);
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x14000cfc0  mov     [rsp+arg_0], rbx
0x14000cfc5  mov     [rsp+arg_8], rbp
0x14000cfca  push    rsi
0x14000cfcb  push    rdi
0x14000cfcc  push    r12
0x14000cfce  push    r14
0x14000cfd0  push    r15
0x14000cfd2  sub     rsp, 30h
0x14000cfd6  xor     r12d, r12d
0x14000cfd9  lea     rdx, aSyspart; "|SYSPART|"
0x14000cfe0  mov     edi, r12d
0x14000cfe3  mov     [rsp+58h+arg_10], r12
0x14000cfe8  mov     r14, rcx
0x14000cfeb  call    BfspEnvExpandString
0x14000cff0  lea     r15d, [r12+1]
0x14000cff5  mov     rsi, rax
0x14000cff8  test    rax, rax
0x14000cffb  jnz     short loc_14000D00A
0x14000cffd  call    cs:__imp_GetLastError
0x14000d003  mov     ebx, eax
0x14000d005  jmp     loc_14000D1F8
0x14000d00a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d00e  inc     rax
0x14000d011  cmp     [rsi+rax*2], r12w
0x14000d016  jnz     short loc_14000D00E
0x14000d018  cmp     rax, r15
0x14000d01b  jbe     short loc_14000D02A
0x14000d01d  cmp     word ptr [rsi+2], 5Ch ; '\'
0x14000d022  jnz     short loc_14000D02A
0x14000d024  mov     word ptr [rsi+2], 3Fh ; '?'
0x14000d02a  xor     edx, edx
0x14000d02c  mov     [rsp+58h+P], r12
0x14000d031  lea     r9, [rsp+58h+P]
0x14000d036  movzx   ebp, r12b
0x14000d03a  mov     rcx, rsi
0x14000d03d  lea     r8d, [rdx+8]
0x14000d041  call    SiQueryProperty
0x14000d046  mov     r8, [rsp+58h+P]; P
0x14000d04b  mov     ebx, eax
0x14000d04d  test    eax, eax
0x14000d04f  js      short loc_14000D05A
0x14000d051  cmp     dword ptr [r8+1Ch], 10h
0x14000d056  cmovz   ebp, r15d
0x14000d05a  test    r8, r8
0x14000d05d  jz      short loc_14000D074
0x14000d05f  mov     rcx, gs:60h
0x14000d068  xor     edx, edx; Flags
0x14000d06a  mov     rcx, [rcx+30h]; HeapHandle
0x14000d06e  call    cs:__imp_RtlFreeHeap
0x14000d074  test    ebx, ebx
0x14000d076  jns     short loc_14000D0A4
0x14000d078  mov     ecx, ebx; Status
0x14000d07a  call    cs:__imp_RtlNtStatusToDosError
0x14000d080  lea     rdx, aFailedToDeterm_0; "Failed to determine whether the system "...
0x14000d087  mov     ecx, 3
0x14000d08c  mov     r8d, eax
0x14000d08f  call    BfspLogMessage
0x14000d094  xor     ecx, ecx; dwErrCode
0x14000d096  mov     ebx, r12d
0x14000d099  call    cs:__imp_SetLastError
0x14000d09f  jmp     loc_14000D1F8
0x14000d0a4  mov     ebx, r12d
0x14000d0a7  test    bpl, bpl
0x14000d0aa  jnz     short loc_14000D0C2
0x14000d0ac  lea     rdx, aSystemPartitio; "System partition is not in a space"
0x14000d0b3  mov     ecx, 2
0x14000d0b8  call    BfspLogMessage
0x14000d0bd  jmp     loc_14000D1F8
0x14000d0c2  lea     rdx, [rsp+58h+arg_10]
0x14000d0c7  mov     rcx, rsi
0x14000d0ca  call    BfspSpacesGetPhysicalPartitions
0x14000d0cf  test    eax, eax
0x14000d0d1  jnz     short loc_14000D0FF
0x14000d0d3  call    cs:__imp_GetLastError
0x14000d0d9  lea     rdx, aFailedToRetrie; "Failed to retrieve physical partitions."...
0x14000d0e0  mov     ecx, 3
0x14000d0e5  mov     r8d, eax
0x14000d0e8  call    BfspLogMessage
0x14000d0ed  xor     ecx, ecx; dwErrCode
0x14000d0ef  call    cs:__imp_SetLastError
0x14000d0f5  mov     rdi, [rsp+58h+arg_10]
0x14000d0fa  jmp     loc_14000D1F8
0x14000d0ff  mov     rdi, [rsp+58h+arg_10]
0x14000d104  mov     ecx, 2
0x14000d109  cmp     [rdi+8], r12d
0x14000d10d  jnz     short loc_14000D118
0x14000d10f  lea     rdx, aNoPhysicalPart; "No physical partitions found"
0x14000d116  jmp     short loc_14000D0B8
0x14000d118  lea     rdx, aServicingSpace; "Servicing spaces files"
0x14000d11f  call    BfspLogMessage
0x14000d124  lea     rdx, aFwtype; "FWTYPE"
0x14000d12b  mov     rcx, r14
0x14000d12e  call    BfspEnvGetValue
0x14000d133  mov     rcx, rax; String1
0x14000d136  lea     rdx, aEfi; "EFI"
0x14000d13d  mov     r8d, 4; MaxCount
0x14000d143  call    wcsncmp_0
0x14000d148  mov     [rsp+58h+var_38], rdi
0x14000d14d  mov     rcx, r14
0x14000d150  test    eax, eax
0x14000d152  jz      short loc_14000D18D
0x14000d154  xor     r9d, r9d
0x14000d157  lea     r8, aDestBootspaces; "|DEST|\\bootspaces.dll"
0x14000d15e  lea     rdx, aSourceMiscFwty; "|SOURCE|\\Misc\\|FWTYPE|\\bootspaces.dl"...
0x14000d165  call    BfspSpacesCopyToPhysicalPartitions
0x14000d16a  test    eax, eax
0x14000d16c  jnz     short loc_14000D17D
0x14000d16e  call    cs:__imp_GetLastError
0x14000d174  lea     rdx, aFailedToServic_0; "Failed to service spaces DLL. Last Erro"...
0x14000d17b  jmp     short loc_14000D1E9
0x14000d17d  lea     r8, aBootmgbin_0; "|BOOTMGBIN|"
0x14000d184  lea     rdx, aSyspartBootmgb; "|SYSPART|\\|BOOTMGBIN|"
0x14000d18b  jmp     short loc_14000D1C8
0x14000d18d  lea     r9, aBootmgrExe; "bootmgr.exe"
0x14000d194  lea     r8, aEfidefaultdirD; "|EFIDEFAULTDIR|\\|DEFAULTAPP|"
0x14000d19b  lea     rdx, aSyspartDestBoo_2; "|SYSPART|\\|DEST|\\|BOOTMGBIN|"
0x14000d1a2  call    BfspSpacesCopyToPhysicalPartitions
0x14000d1a7  test    eax, eax
0x14000d1a9  jnz     short loc_14000D1BA
0x14000d1ab  lea     rdx, aFailedToServic_1; "Failed to service spaces default bootmg"...
0x14000d1b2  lea     ecx, [rax+3]
0x14000d1b5  call    BfspLogMessage
0x14000d1ba  lea     r8, aDestBootmgbin; "|DEST|\\|BOOTMGBIN|"
0x14000d1c1  lea     rdx, aSyspartDestBoo_2; "|SYSPART|\\|DEST|\\|BOOTMGBIN|"
0x14000d1c8  xor     r9d, r9d
0x14000d1cb  mov     [rsp+58h+var_38], rdi
0x14000d1d0  mov     rcx, r14
0x14000d1d3  call    BfspSpacesCopyToPhysicalPartitions
0x14000d1d8  test    eax, eax
0x14000d1da  jnz     short loc_14000D1F8
0x14000d1dc  call    cs:__imp_GetLastError
0x14000d1e2  lea     rdx, aFailedToServic; "Failed to service spaces bootmgr. Last "...
0x14000d1e9  mov     r8d, eax
0x14000d1ec  mov     ecx, 4
0x14000d1f1  mov     ebx, eax
0x14000d1f3  call    BfspLogMessage
0x14000d1f8  lea     rdx, aSyspartDestBoo_0; "|SYSPART|\\|DEST|\\bootspaces.dll"
0x14000d1ff  mov     rcx, r14
0x14000d202  call    BfspEnvExpandString
0x14000d207  mov     rbp, rax
0x14000d20a  test    rax, rax
0x14000d20d  jnz     short loc_14000D219
0x14000d20f  call    cs:__imp_GetLastError
0x14000d215  mov     ebx, eax
0x14000d217  jmp     short loc_14000D250
0x14000d219  mov     rcx, rbp
0x14000d21c  call    BfspFileExists
0x14000d221  test    eax, eax
0x14000d223  jz      short loc_14000D250
0x14000d225  mov     rcx, rbp
0x14000d228  call    DeleteFileEx2
0x14000d22d  test    eax, eax
0x14000d22f  jnz     short loc_14000D250
0x14000d231  call    cs:__imp_GetLastError
0x14000d237  mov     r8, rbp
0x14000d23a  lea     rdx, aErrorDeletingS; "Error deleting stale spaces dll (%s)! L"...
0x14000d241  mov     r9d, eax
0x14000d244  mov     ecx, 4
0x14000d249  mov     ebx, eax
0x14000d24b  call    BfspLogMessage
0x14000d250  test    rdi, rdi
0x14000d253  jz      short loc_14000D269
0x14000d255  call    cs:__imp_GetProcessHeap
0x14000d25b  mov     r8, rdi; lpMem
0x14000d25e  xor     edx, edx; dwFlags
0x14000d260  mov     rcx, rax; hHeap
0x14000d263  call    cs:__imp_HeapFree
0x14000d269  test    rsi, rsi
0x14000d26c  jz      short loc_14000D282
0x14000d26e  call    cs:__imp_GetProcessHeap
0x14000d274  mov     r8, rsi; lpMem
0x14000d277  xor     edx, edx; dwFlags
0x14000d279  mov     rcx, rax; hHeap
0x14000d27c  call    cs:__imp_HeapFree
0x14000d282  test    ebx, ebx
0x14000d284  jz      short loc_14000D291
0x14000d286  mov     ecx, ebx; dwErrCode
0x14000d288  call    cs:__imp_SetLastError
0x14000d28e  mov     r15d, r12d
0x14000d291  mov     rbx, [rsp+58h+arg_0]
0x14000d296  mov     eax, r15d
0x14000d299  mov     rbp, [rsp+58h+arg_8]
0x14000d29e  add     rsp, 30h
0x14000d2a2  pop     r15
0x14000d2a4  pop     r14
0x14000d2a6  pop     r12
0x14000d2a8  pop     rdi
0x14000d2a9  pop     rsi
0x14000d2aa  retn
```
