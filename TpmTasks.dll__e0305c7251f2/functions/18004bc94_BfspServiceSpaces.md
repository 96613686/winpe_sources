# BfspServiceSpaces

- ea: `0x18004bc94`
- end: `0x18004bf40`
- name: `BfspServiceSpaces`
- size: `684`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x180049234`

## callees

- `0x1800466c0`
- `0x18004bc94`
- `0x18004c194`
- `0x18004c458`
- `0x18004cdd4`
- `0x1800513d4`
- `0x1800515f4`
- `0x180053994`
- `0x180059278`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18004bd13`
- `ntdll!RtlNtStatusToDosError` at `0x18004bd13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004befe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bf17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004befe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bf17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bef0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bf09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bef0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bf09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004bd32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004bd8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004bf23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004bd32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004bd8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004bf23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bcd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bd6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004beaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004becc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bcd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bd6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004beaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004becc`
- `bcd!SyspartIsSpace` at `0x18004bd07`
- `bcd!SyspartIsSpace` at `0x18004bd07`

## string_xrefs

- `0x18004bdf2`: `|DEST|\bootspaces.dll`
- `0x18004bdf9`: `|SOURCE|\Misc\|FWTYPE|\bootspaces.dll`
- `0x18004be46`: `Failed to service spaces default bootmgr`
- `0x18004be0f`: `Failed to service spaces DLL. Last Error = %#x`
- `0x18004be93`: `|SYSPART|\|DEST|\bootspaces.dll`
- `0x18004bed5`: `Error deleting stale spaces dll (%s)! Last Error = %#x`
- `0x18004be7d`: `Failed to service spaces bootmgr. Last Error = %#x`

## pseudocode

```c
__int64 __fastcall BfspServiceSpaces(__int64 a1, int a2)
{
  void *v2; // rdi
  unsigned int v4; // r14d
  _WORD *v5; // rsi
  __int64 v6; // rbx
  unsigned __int64 v7; // rax
  NTSTATUS IsSpace; // eax
  ULONG v9; // eax
  DWORD LastError; // eax
  const wchar_t *Value; // rax
  DWORD v12; // eax
  const wchar_t *v13; // rdx
  const wchar_t *v14; // r8
  const wchar_t *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rbp
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax
  int v21; // [rsp+68h] [rbp+10h] BYREF
  _DWORD *v22; // [rsp+70h] [rbp+18h] BYREF

  v21 = a2;
  LOBYTE(v21) = 0;
  v2 = 0;
  v22 = 0;
  v4 = 1;
  v5 = (_WORD *)BfspEnvExpandString(a1, L"|SYSPART|");
  if ( !v5 )
  {
    LODWORD(v6) = GetLastError();
    goto LABEL_27;
  }
  v7 = -1;
  do
    ++v7;
  while ( v5[v7] );
  if ( v7 > 1 && v5[1] == 92 )
    v5[1] = 63;
  IsSpace = SyspartIsSpace(v5, &v21);
  if ( IsSpace < 0 )
  {
    v9 = RtlNtStatusToDosError(IsSpace);
    BfspLogMessage(3, L"Failed to determine whether the system partition is in a space. Last Error = %#x", v9);
    LODWORD(v6) = 0;
    SetLastError(0);
    goto LABEL_27;
  }
  LODWORD(v6) = 0;
  if ( (_BYTE)v21 )
  {
    if ( !(unsigned int)BfspSpacesGetPhysicalPartitions(v5, &v22) )
    {
      LastError = GetLastError();
      BfspLogMessage(3, L"Failed to retrieve physical partitions. Last Error = %#x", LastError);
      SetLastError(0);
      v2 = v22;
      goto LABEL_27;
    }
    v2 = v22;
    if ( !v22[2] )
    {
      BfspLogMessage(2, L"No physical partitions found");
      goto LABEL_27;
    }
    BfspLogMessage(2, L"Servicing spaces files");
    Value = (const wchar_t *)BfspEnvGetValue(a1, L"FWTYPE");
    if ( !wcsncmp_0(Value, L"EFI", 4u) )
    {
      if ( !(unsigned int)BfspSpacesCopyToPhysicalPartitions(
                            a1,
                            (unsigned int)L"|SYSPART|\\|DEST|\\|BOOTMGBIN|",
                            (unsigned int)L"|EFIDEFAULTDIR|\\|DEFAULTAPP|",
                            (unsigned int)L"bootmgr.exe",
                            (__int64)v2) )
        BfspLogMessage(3, L"Failed to service spaces default bootmgr");
      v14 = L"|DEST|\\|BOOTMGBIN|";
      v15 = L"|SYSPART|\\|DEST|\\|BOOTMGBIN|";
    }
    else
    {
      if ( !(unsigned int)BfspSpacesCopyToPhysicalPartitions(
                            a1,
                            (unsigned int)L"|SOURCE|\\Misc\\|FWTYPE|\\bootspaces.dll",
                            (unsigned int)L"|DEST|\\bootspaces.dll",
                            0,
                            (__int64)v2) )
      {
        v12 = GetLastError();
        v13 = L"Failed to service spaces DLL. Last Error = %#x";
LABEL_26:
        LODWORD(v6) = v12;
        BfspLogMessage(4, v13, v12);
        goto LABEL_27;
      }
      v14 = L"|BOOTMGBIN|";
      v15 = L"|SYSPART|\\|BOOTMGBIN|";
    }
    if ( (unsigned int)BfspSpacesCopyToPhysicalPartitions(a1, (_DWORD)v15, (_DWORD)v14, 0, (__int64)v2) )
      goto LABEL_27;
    v12 = GetLastError();
    v13 = L"Failed to service spaces bootmgr. Last Error = %#x";
    goto LABEL_26;
  }
  BfspLogMessage(2, L"System partition is not in a space");
LABEL_27:
  v16 = BfspEnvExpandString(a1, L"|SYSPART|\\|DEST|\\bootspaces.dll");
  v17 = v16;
  if ( v16 )
  {
    if ( (unsigned int)BfspFileExists(v16) && !DeleteFileEx2(v17) )
    {
      v6 = GetLastError();
      BfspLogMessage(4, L"Error deleting stale spaces dll (%s)! Last Error = %#x", v17, v6);
    }
  }
  else
  {
    LODWORD(v6) = GetLastError();
  }
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  if ( v5 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
  if ( (_DWORD)v6 )
  {
    SetLastError(v6);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18004bc94  mov     rax, rsp
0x18004bc97  mov     [rax+8], rbx
0x18004bc9b  mov     [rax+10h], edx
0x18004bc9e  push    rbp
0x18004bc9f  push    rsi
0x18004bca0  push    rdi
0x18004bca1  push    r14
0x18004bca3  push    r15
0x18004bca5  sub     rsp, 30h
0x18004bca9  xor     r15d, r15d
0x18004bcac  lea     rdx, aSyspart; "|SYSPART|"
0x18004bcb3  mov     [rax+10h], r15b
0x18004bcb7  mov     edi, r15d
0x18004bcba  mov     [rax+18h], r15
0x18004bcbe  mov     rbp, rcx
0x18004bcc1  call    BfspEnvExpandString
0x18004bcc6  lea     r14d, [r15+1]
0x18004bcca  mov     rsi, rax
0x18004bccd  test    rax, rax
0x18004bcd0  jnz     short loc_18004BCDF
0x18004bcd2  call    cs:__imp_GetLastError
0x18004bcd8  mov     ebx, eax
0x18004bcda  jmp     loc_18004BE93
0x18004bcdf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004bce3  inc     rax
0x18004bce6  cmp     [rsi+rax*2], r15w
0x18004bceb  jnz     short loc_18004BCE3
0x18004bced  cmp     rax, r14
0x18004bcf0  jbe     short loc_18004BCFF
0x18004bcf2  cmp     word ptr [rsi+2], 5Ch ; '\'
0x18004bcf7  jnz     short loc_18004BCFF
0x18004bcf9  mov     word ptr [rsi+2], 3Fh ; '?'
0x18004bcff  lea     rdx, [rsp+58h+arg_8]
0x18004bd04  mov     rcx, rsi
0x18004bd07  call    cs:__imp_SyspartIsSpace
0x18004bd0d  test    eax, eax
0x18004bd0f  jns     short loc_18004BD3D
0x18004bd11  mov     ecx, eax; Status
0x18004bd13  call    cs:__imp_RtlNtStatusToDosError
0x18004bd19  lea     rdx, aFailedToDeterm_0; "Failed to determine whether the system "...
0x18004bd20  mov     ecx, 3
0x18004bd25  mov     r8d, eax
0x18004bd28  call    BfspLogMessage
0x18004bd2d  xor     ecx, ecx; dwErrCode
0x18004bd2f  mov     ebx, r15d
0x18004bd32  call    cs:__imp_SetLastError
0x18004bd38  jmp     loc_18004BE93
0x18004bd3d  mov     ebx, r15d
0x18004bd40  cmp     byte ptr [rsp+58h+arg_8], r15b
0x18004bd45  jnz     short loc_18004BD5D
0x18004bd47  lea     rdx, aSystemPartitio; "System partition is not in a space"
0x18004bd4e  mov     ecx, 2
0x18004bd53  call    BfspLogMessage
0x18004bd58  jmp     loc_18004BE93
0x18004bd5d  lea     rdx, [rsp+58h+arg_10]
0x18004bd62  mov     rcx, rsi
0x18004bd65  call    BfspSpacesGetPhysicalPartitions
0x18004bd6a  test    eax, eax
0x18004bd6c  jnz     short loc_18004BD9A
0x18004bd6e  call    cs:__imp_GetLastError
0x18004bd74  lea     rdx, aFailedToRetrie; "Failed to retrieve physical partitions."...
0x18004bd7b  mov     ecx, 3
0x18004bd80  mov     r8d, eax
0x18004bd83  call    BfspLogMessage
0x18004bd88  xor     ecx, ecx; dwErrCode
0x18004bd8a  call    cs:__imp_SetLastError
0x18004bd90  mov     rdi, [rsp+58h+arg_10]
0x18004bd95  jmp     loc_18004BE93
0x18004bd9a  mov     rdi, [rsp+58h+arg_10]
0x18004bd9f  mov     ecx, 2
0x18004bda4  cmp     [rdi+8], r15d
0x18004bda8  jnz     short loc_18004BDB3
0x18004bdaa  lea     rdx, aNoPhysicalPart; "No physical partitions found"
0x18004bdb1  jmp     short loc_18004BD53
0x18004bdb3  lea     rdx, aServicingSpace; "Servicing spaces files"
0x18004bdba  call    BfspLogMessage
0x18004bdbf  lea     rdx, aFwtype; "FWTYPE"
0x18004bdc6  mov     rcx, rbp
0x18004bdc9  call    BfspEnvGetValue
0x18004bdce  mov     rcx, rax; String1
0x18004bdd1  lea     rdx, aEfi; "EFI"
0x18004bdd8  mov     r8d, 4; MaxCount
0x18004bdde  call    wcsncmp_0
0x18004bde3  mov     [rsp+58h+var_38], rdi
0x18004bde8  mov     rcx, rbp
0x18004bdeb  test    eax, eax
0x18004bded  jz      short loc_18004BE28
0x18004bdef  xor     r9d, r9d
0x18004bdf2  lea     r8, aDestBootspaces; "|DEST|\\bootspaces.dll"
0x18004bdf9  lea     rdx, aSourceMiscFwty; "|SOURCE|\\Misc\\|FWTYPE|\\bootspaces.dl"...
0x18004be00  call    BfspSpacesCopyToPhysicalPartitions
0x18004be05  test    eax, eax
0x18004be07  jnz     short loc_18004BE18
0x18004be09  call    cs:__imp_GetLastError
0x18004be0f  lea     rdx, aFailedToServic_0; "Failed to service spaces DLL. Last Erro"...
0x18004be16  jmp     short loc_18004BE84
0x18004be18  lea     r8, aBootmgbin_0; "|BOOTMGBIN|"
0x18004be1f  lea     rdx, aSyspartBootmgb; "|SYSPART|\\|BOOTMGBIN|"
0x18004be26  jmp     short loc_18004BE63
0x18004be28  lea     r9, aBootmgrExe; "bootmgr.exe"
0x18004be2f  lea     r8, aEfidefaultdirD; "|EFIDEFAULTDIR|\\|DEFAULTAPP|"
0x18004be36  lea     rdx, aSyspartDestBoo_2; "|SYSPART|\\|DEST|\\|BOOTMGBIN|"
0x18004be3d  call    BfspSpacesCopyToPhysicalPartitions
0x18004be42  test    eax, eax
0x18004be44  jnz     short loc_18004BE55
0x18004be46  lea     rdx, aFailedToServic_1; "Failed to service spaces default bootmg"...
0x18004be4d  lea     ecx, [rax+3]
0x18004be50  call    BfspLogMessage
0x18004be55  lea     r8, aDestBootmgbin; "|DEST|\\|BOOTMGBIN|"
0x18004be5c  lea     rdx, aSyspartDestBoo_2; "|SYSPART|\\|DEST|\\|BOOTMGBIN|"
0x18004be63  xor     r9d, r9d
0x18004be66  mov     [rsp+58h+var_38], rdi
0x18004be6b  mov     rcx, rbp
0x18004be6e  call    BfspSpacesCopyToPhysicalPartitions
0x18004be73  test    eax, eax
0x18004be75  jnz     short loc_18004BE93
0x18004be77  call    cs:__imp_GetLastError
0x18004be7d  lea     rdx, aFailedToServic; "Failed to service spaces bootmgr. Last "...
0x18004be84  mov     r8d, eax
0x18004be87  mov     ecx, 4
0x18004be8c  mov     ebx, eax
0x18004be8e  call    BfspLogMessage
0x18004be93  lea     rdx, aSyspartDestBoo_0; "|SYSPART|\\|DEST|\\bootspaces.dll"
0x18004be9a  mov     rcx, rbp
0x18004be9d  call    BfspEnvExpandString
0x18004bea2  mov     rbp, rax
0x18004bea5  test    rax, rax
0x18004bea8  jnz     short loc_18004BEB4
0x18004beaa  call    cs:__imp_GetLastError
0x18004beb0  mov     ebx, eax
0x18004beb2  jmp     short loc_18004BEEB
0x18004beb4  mov     rcx, rbp
0x18004beb7  call    BfspFileExists
0x18004bebc  test    eax, eax
0x18004bebe  jz      short loc_18004BEEB
0x18004bec0  mov     rcx, rbp
0x18004bec3  call    DeleteFileEx2
0x18004bec8  test    eax, eax
0x18004beca  jnz     short loc_18004BEEB
0x18004becc  call    cs:__imp_GetLastError
0x18004bed2  mov     r8, rbp
0x18004bed5  lea     rdx, aErrorDeletingS; "Error deleting stale spaces dll (%s)! L"...
0x18004bedc  mov     r9d, eax
0x18004bedf  mov     ecx, 4
0x18004bee4  mov     ebx, eax
0x18004bee6  call    BfspLogMessage
0x18004beeb  test    rdi, rdi
0x18004beee  jz      short loc_18004BF04
0x18004bef0  call    cs:__imp_GetProcessHeap
0x18004bef6  mov     r8, rdi; lpMem
0x18004bef9  xor     edx, edx; dwFlags
0x18004befb  mov     rcx, rax; hHeap
0x18004befe  call    cs:__imp_HeapFree
0x18004bf04  test    rsi, rsi
0x18004bf07  jz      short loc_18004BF1D
0x18004bf09  call    cs:__imp_GetProcessHeap
0x18004bf0f  mov     r8, rsi; lpMem
0x18004bf12  xor     edx, edx; dwFlags
0x18004bf14  mov     rcx, rax; hHeap
0x18004bf17  call    cs:__imp_HeapFree
0x18004bf1d  test    ebx, ebx
0x18004bf1f  jz      short loc_18004BF2C
0x18004bf21  mov     ecx, ebx; dwErrCode
0x18004bf23  call    cs:__imp_SetLastError
0x18004bf29  mov     r14d, r15d
0x18004bf2c  mov     rbx, [rsp+58h+arg_0]
0x18004bf31  mov     eax, r14d
0x18004bf34  add     rsp, 30h
0x18004bf38  pop     r15
0x18004bf3a  pop     r14
0x18004bf3c  pop     rdi
0x18004bf3d  pop     rsi
0x18004bf3e  pop     rbp
0x18004bf3f  retn
```
