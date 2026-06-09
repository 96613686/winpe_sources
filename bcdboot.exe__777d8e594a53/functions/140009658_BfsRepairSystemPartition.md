# BfsRepairSystemPartition

- ea: `0x140009658`
- end: `0x140009b75`
- name: `BfsRepairSystemPartition`
- size: `1309`
- prototype: `__int64 __fastcall(unsigned int, void *, int, const wchar_t *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140001bc8`

## callees

- `0x140001008`
- `0x140004080`
- `0x140006a14`
- `0x140009094`
- `0x140009658`
- `0x140009bdc`
- `0x140009fd4`
- `0x14000e578`
- `0x14000e5c8`
- `0x14000e628`
- `0x14000f2a0`
- `0x14000f2dc`
- `0x140013b48`
- `0x140013ee8`
- `0x140018890`
- `0x14001a8c4`
- `0x14001bb00`
- `0x140026650`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1400096d3`
- `msvcrt!wcscpy_s` at `0x1400096d3`
- `msvcrt!fclose` at `0x140009b1f`
- `msvcrt!fclose` at `0x140009b1f`
- `msvcrt!_wfopen_s` at `0x140009751`
- `msvcrt!_wfopen_s` at `0x140009751`
- `msvcrt!wcscat_s` at `0x1400096e6`
- `msvcrt!wcscat_s` at `0x1400096e6`
- `KERNEL32!SetLastError` at `0x14000993e`
- `KERNEL32!SetLastError` at `0x140009b40`
- `KERNEL32!SetLastError` at `0x14000993e`
- `KERNEL32!SetLastError` at `0x140009b40`
- `KERNEL32!GetLastError` at `0x140009982`
- `KERNEL32!GetLastError` at `0x1400099c5`
- `KERNEL32!GetLastError` at `0x140009982`
- `KERNEL32!GetLastError` at `0x1400099c5`
- `KERNEL32!HeapFree` at `0x1400098d9`
- `KERNEL32!HeapFree` at `0x1400098fe`
- `KERNEL32!HeapFree` at `0x1400098d9`
- `KERNEL32!HeapFree` at `0x1400098fe`
- `KERNEL32!GetProcessHeap` at `0x1400098c9`
- `KERNEL32!GetProcessHeap` at `0x1400098f0`
- `KERNEL32!GetProcessHeap` at `0x1400098c9`
- `KERNEL32!GetProcessHeap` at `0x1400098f0`
- `KERNEL32!CreateDirectoryW` at `0x14000972f`
- `KERNEL32!CreateDirectoryW` at `0x14000972f`
- `ntdll!RtlNtStatusToDosError` at `0x140009936`
- `ntdll!RtlNtStatusToDosError` at `0x140009936`

## string_xrefs

- `0x1400096d9`: `\Logs\bfsvc\repair.log`
- `0x1400097a2`: `BfsRepairSystemPartition flags(0x%08x), system root: %ws, online: %ws, boot files: %ws, caller: %d`
- `0x140009944`: `BfsRepair: BCD failed validation check after file system repair.`
- `0x140009988`: `BfsRepair: Failed to repair BCD store. Error: %08x`
- `0x1400099cb`: `BfsRepair: Failed to service boot files. Error: %08x`

## pseudocode

```c
__int64 __fastcall BfsRepairSystemPartition(unsigned int a1, void *a2, int a3, const wchar_t *a4)
{
  __int64 v8; // r13
  unsigned int v9; // ebx
  __int64 v10; // rdi
  __int64 v11; // rdi
  const wchar_t *v12; // rcx
  const wchar_t *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r8
  DWORD v16; // r14d
  DWORD v17; // eax
  void *v18; // rsi
  DWORD v19; // r15d
  int v20; // eax
  __int64 v21; // r12
  NTSTATUS ElementDataWithFlags; // edi
  int v23; // eax
  __int64 v24; // r8
  HANDLE v25; // r13
  DWORD v26; // r14d
  DWORD v27; // esi
  HANDLE ProcessHeap; // rax
  HANDLE v29; // rax
  ULONG v30; // eax
  int v31; // r15d
  __int64 LastError; // rdi
  int v33; // esi
  int v34; // r8d
  int v35; // r9d
  DWORD v37; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v38; // [rsp+44h] [rbp-BCh] BYREF
  int v39; // [rsp+48h] [rbp-B8h] BYREF
  int v40; // [rsp+4Ch] [rbp-B4h] BYREF
  int v41; // [rsp+50h] [rbp-B0h] BYREF
  int v42; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v43; // [rsp+58h] [rbp-A8h]
  int v44; // [rsp+5Ch] [rbp-A4h] BYREF
  int v45; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-88h] BYREF
  void *Src; // [rsp+80h] [rbp-80h]
  STRSAFE_LPCWSTR pszSrc; // [rsp+88h] [rbp-78h]
  __int128 v51; // [rsp+90h] [rbp-70h] BYREF
  __int64 v52[20]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Destination[264]; // [rsp+140h] [rbp+40h] BYREF

  pszSrc = a4;
  v40 = a3;
  Src = a2;
  v42 = 0;
  v39 = 0;
  LODWORD(v8) = 0;
  if ( (a1 & 0x10) != 0 )
    BfspLogInitialize((a1 & 0x40) == 0 ? 3 : 0);
  wcscpy_s(Destination, 0x104u, (const wchar_t *)a2);
  wcscat_s(Destination, 0x104u, L"\\Logs\\bfsvc\\repair.log");
  v9 = 1;
  if ( !FileLoggingEnabled )
  {
    v10 = -1;
    do
      ++v10;
    while ( Destination[v10] );
    v11 = v10 - 1;
    if ( v11 )
    {
      while ( Destination[v11] != 92 )
      {
        if ( !--v11 )
          goto LABEL_12;
      }
      Destination[v11] = 0;
      CreateDirectoryW(Destination, 0);
      Destination[v11] = 92;
      _wfopen_s(&LogFileStream, Destination, L"w");
      if ( LogFileStream )
        FileLoggingEnabled = 1;
    }
  }
LABEL_12:
  v12 = a4;
  if ( !a4 )
    v12 = L"None";
  v13 = L"True";
  if ( !a3 )
    v13 = L"False";
  BfspLogMessage(
    2,
    L"BfsRepairSystemPartition flags(0x%08x), system root: %ws, online: %ws, boot files: %ws, caller: %d",
    a1,
    a2,
    v13,
    v12,
    1);
  v38 = BfspChkDiskHelper(v14, &v42);
  v16 = v38;
  v37 = 0;
  v17 = 0;
  v46 = 0;
  if ( v42 )
    v17 = v38;
  Handle = 0;
  v43 = v17;
  lpMem = 0;
  v51 = 0;
  v18 = 0;
  v19 = 0;
  v20 = BiOpenStoreWithHash(0, 2, v15, &v46);
  v21 = v46;
  ElementDataWithFlags = v20;
  if ( v20 >= 0 )
  {
    v23 = BcdOpenObject(v46, &GUID_WINDOWS_BOOTMGR, &Handle);
    v25 = Handle;
    ElementDataWithFlags = v23;
    if ( v23 < 0 )
    {
LABEL_35:
      if ( v25 )
        BcdCloseObject(v25);
      LODWORD(v8) = v39;
      goto LABEL_38;
    }
    LODWORD(v46) = 16;
    v26 = 0;
    ElementDataWithFlags = BcdGetElementDataWithFlags(Handle, 587202563, v24, &v51, &v46);
    if ( ElementDataWithFlags < 0 || (v26 = BfspValidateBcdEntry(v21, &v51)) == 0 )
    {
      ElementDataWithFlags = BfspGetBcdElementData(v25, 603979777, &lpMem, &v37);
      if ( ElementDataWithFlags < 0 || (v37 & 0xF) != 0 )
      {
        v18 = lpMem;
        goto LABEL_32;
      }
      v27 = v37 >> 4;
      if ( v37 >> 4 )
      {
        do
        {
          v26 = BfspValidateBcdEntry(v21, (char *)lpMem + 16 * v19);
          if ( v26 )
            break;
          ++v19;
        }
        while ( v19 < v27 );
      }
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, lpMem);
      }
      v18 = 0;
    }
    v19 = v26;
LABEL_32:
    if ( v18 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v18);
    }
    v16 = v38;
    goto LABEL_35;
  }
LABEL_38:
  if ( v21 )
    BcdCloseStore(v21);
  if ( v19 )
  {
    v31 = 0;
  }
  else
  {
    if ( ElementDataWithFlags < 0 )
    {
      v30 = RtlNtStatusToDosError(ElementDataWithFlags);
      SetLastError(v30);
    }
    v31 = 1;
    BfspLogMessage(3, L"BfsRepair: BCD failed validation check after file system repair.");
    v40 = -v40;
    if ( !(unsigned int)BfsInitializeBcdStoreEx(Src, 0) )
    {
      LastError = GetLastError();
      BfspLogMessage(4, L"BfsRepair: Failed to repair BCD store. Error: %08x", LastError);
      goto LABEL_47;
    }
  }
  LODWORD(LastError) = 0;
LABEL_47:
  if ( pszSrc )
  {
    v33 = 1;
    if ( !(unsigned int)BfsServiceBootFilesEx2(pszSrc) )
    {
      v8 = GetLastError();
      BfspLogMessage(4, L"BfsRepair: Failed to service boot files. Error: %08x", v8);
    }
  }
  else
  {
    v33 = 0;
  }
  if ( (int)RegisterBfsTelemetryProvider() >= 0 )
  {
    if ( (unsigned int)dword_14003F020 > 5
      && (qword_14003F030 & 0x800000000000LL) != 0
      && (qword_14003F038 & 0x800000000000LL) == qword_14003F038 )
    {
      v45 = 1;
      v52[4] = (__int64)&v45;
      v44 = v42;
      v52[6] = (__int64)&v44;
      LODWORD(v46) = v43;
      v52[8] = (__int64)&v46;
      v52[10] = (__int64)&v41;
      v52[12] = (__int64)&v40;
      v52[14] = (__int64)&v39;
      v52[16] = (__int64)&v38;
      v52[18] = (__int64)&v37;
      v52[5] = 4;
      v52[7] = 4;
      v52[9] = 4;
      v41 = v31;
      v52[11] = 4;
      v40 = LastError;
      v52[13] = 4;
      v39 = v33;
      v52[15] = 4;
      v38 = v8;
      v52[17] = 4;
      v37 = v16;
      v52[19] = 4;
      tlgWriteTransfer_EventWriteTransfer((int)&dword_14003F020, (int)&byte_14003AAD1, v34, v35, 0xAu, (__int64)v52);
    }
    UnregisterBfsTelemetryProvider();
  }
  if ( FileLoggingEnabled )
  {
    fclose(LogFileStream);
    LogFileStream = 0;
    FileLoggingEnabled = 0;
  }
  BfspLogDestroy();
  if ( v16 )
  {
    SetLastError(v16);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x140009658  mov     [rsp-8+arg_10], rbx
0x14000965d  push    rbp
0x14000965e  push    rsi
0x14000965f  push    rdi
0x140009660  push    r12
0x140009662  push    r13
0x140009664  push    r14
0x140009666  push    r15
0x140009668  lea     rbp, [rsp-260h]
0x140009670  sub     rsp, 360h
0x140009677  mov     rax, cs:__security_cookie
0x14000967e  xor     rax, rsp
0x140009681  mov     [rbp+290h+var_40], rax
0x140009688  mov     esi, ecx
0x14000968a  mov     [rbp+290h+pszSrc], r9
0x14000968e  xor     ecx, ecx
0x140009690  mov     [rsp+390h+var_344], r8d
0x140009695  mov     [rbp+290h+Src], rdx
0x140009699  mov     r14, r9
0x14000969c  mov     [rsp+390h+var_33C], ecx
0x1400096a0  mov     r12d, r8d
0x1400096a3  mov     [rsp+390h+var_348], ecx
0x1400096a7  mov     r15, rdx
0x1400096aa  mov     r13d, ecx
0x1400096ad  test    sil, 10h
0x1400096b1  jz      short loc_1400096C5
0x1400096b3  mov     eax, esi
0x1400096b5  and     al, 40h
0x1400096b7  neg     al
0x1400096b9  sbb     ecx, ecx
0x1400096bb  not     ecx
0x1400096bd  and     ecx, 3
0x1400096c0  call    BfspLogInitialize
0x1400096c5  mov     ebx, 104h
0x1400096ca  lea     rcx, [rbp+290h+Destination]; Destination
0x1400096ce  mov     edx, ebx; SizeInWords
0x1400096d0  mov     r8, r15; Source
0x1400096d3  call    cs:__imp_wcscpy_s
0x1400096d9  lea     r8, aLogsBfsvcRepai; "\\Logs\\bfsvc\\repair.log"
0x1400096e0  mov     edx, ebx; SizeInWords
0x1400096e2  lea     rcx, [rbp+290h+Destination]; Destination
0x1400096e6  call    cs:__imp_wcscat_s
0x1400096ec  xor     eax, eax
0x1400096ee  mov     ebx, 1
0x1400096f3  cmp     cs:FileLoggingEnabled, eax
0x1400096f9  jnz     short loc_140009766
0x1400096fb  lea     rcx, [rbp+290h+Destination]
0x1400096ff  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140009703  inc     rdi
0x140009706  cmp     [rcx+rdi*2], ax
0x14000970a  jnz     short loc_140009703
0x14000970c  sub     rdi, rbx
0x14000970f  jz      short loc_140009766
0x140009711  mov     ecx, 5Ch ; '\'
0x140009716  cmp     [rbp+rdi*2+290h+Destination], cx
0x14000971b  jz      short loc_140009724
0x14000971d  sub     rdi, rbx
0x140009720  jnz     short loc_140009716
0x140009722  jmp     short loc_140009766
0x140009724  xor     edx, edx; lpSecurityAttributes
0x140009726  mov     [rbp+rdi*2+290h+Destination], ax
0x14000972b  lea     rcx, [rbp+290h+Destination]; lpPathName
0x14000972f  call    cs:__imp_CreateDirectoryW
0x140009735  mov     eax, 5Ch ; '\'
0x14000973a  lea     r8, aW; "w"
0x140009741  lea     rdx, [rbp+290h+Destination]; FileName
0x140009745  mov     [rbp+rdi*2+290h+Destination], ax
0x14000974a  lea     rcx, LogFileStream; Stream
0x140009751  call    cs:__imp__wfopen_s
0x140009757  cmp     cs:LogFileStream, r13
0x14000975e  jz      short loc_140009766
0x140009760  mov     cs:FileLoggingEnabled, ebx
0x140009766  test    r14, r14
0x140009769  mov     [rsp+390h+var_360], ebx
0x14000976d  lea     rax, aNone_0; "None"
0x140009774  mov     rcx, r14
0x140009777  cmovz   rcx, rax
0x14000977b  lea     rdx, aFalse; "False"
0x140009782  mov     [rsp+390h+var_368], rcx
0x140009787  lea     rax, aTrue; "True"
0x14000978e  test    r12d, r12d
0x140009791  mov     edi, 2
0x140009796  mov     r9, r15
0x140009799  mov     r8d, esi
0x14000979c  cmovz   rax, rdx
0x1400097a0  mov     ecx, edi
0x1400097a2  lea     rdx, aBfsrepairsyste; "BfsRepairSystemPartition flags(0x%08x),"...
0x1400097a9  mov     qword ptr [rsp+390h+var_370], rax
0x1400097ae  call    BfspLogMessage
0x1400097b3  lea     rdx, [rsp+390h+var_33C]
0x1400097b8  call    BfspChkDiskHelper
0x1400097bd  xor     ecx, ecx
0x1400097bf  mov     [rsp+390h+var_34C], eax
0x1400097c3  cmp     [rsp+390h+var_33C], ecx
0x1400097c7  lea     r9, [rsp+390h+var_328]
0x1400097cc  mov     r14d, eax
0x1400097cf  mov     [rsp+390h+var_350], ecx
0x1400097d3  mov     eax, ecx
0x1400097d5  mov     [rsp+390h+var_328], rcx
0x1400097da  cmovnz  eax, r14d
0x1400097de  mov     [rsp+390h+Handle], rcx
0x1400097e3  xorps   xmm0, xmm0
0x1400097e6  mov     [rsp+390h+var_338], eax
0x1400097ea  mov     edx, edi
0x1400097ec  mov     [rsp+390h+lpMem], rcx
0x1400097f1  movups  [rbp+290h+var_300], xmm0
0x1400097f5  mov     esi, ecx
0x1400097f7  mov     r15d, ecx
0x1400097fa  call    BiOpenStoreWithHash
0x1400097ff  mov     r12, [rsp+390h+var_328]
0x140009804  mov     edi, eax
0x140009806  test    eax, eax
0x140009808  js      loc_14000991B
0x14000980e  lea     r8, [rsp+390h+Handle]
0x140009813  mov     rcx, r12
0x140009816  lea     rdx, GUID_WINDOWS_BOOTMGR
0x14000981d  call    BcdOpenObject
0x140009822  mov     r13, [rsp+390h+Handle]
0x140009827  mov     edi, eax
0x140009829  test    eax, eax
0x14000982b  js      loc_140009909
0x140009831  lea     rax, [rsp+390h+var_328]
0x140009836  mov     dword ptr [rsp+390h+var_328], 10h
0x14000983e  lea     r9, [rbp+290h+var_300]
0x140009842  mov     qword ptr [rsp+390h+var_370], rax
0x140009847  mov     edx, 23000003h
0x14000984c  mov     rcx, r13
0x14000984f  xor     r14d, r14d
0x140009852  call    BcdGetElementDataWithFlags
0x140009857  mov     edi, eax
0x140009859  test    eax, eax
0x14000985b  js      short loc_140009870
0x14000985d  lea     rdx, [rbp+290h+var_300]
0x140009861  mov     rcx, r12
0x140009864  call    BfspValidateBcdEntry
0x140009869  mov     r14d, eax
0x14000986c  test    eax, eax
0x14000986e  jnz     short loc_1400098E1
0x140009870  lea     r9, [rsp+390h+var_350]
0x140009875  mov     edx, 24000001h
0x14000987a  lea     r8, [rsp+390h+lpMem]
0x14000987f  mov     rcx, r13
0x140009882  call    BfspGetBcdElementData
0x140009887  mov     edi, eax
0x140009889  test    eax, eax
0x14000988b  js      short loc_1400098E6
0x14000988d  mov     esi, [rsp+390h+var_350]
0x140009891  test    sil, 0Fh
0x140009895  jnz     short loc_1400098E6
0x140009897  shr     esi, 4
0x14000989a  test    esi, esi
0x14000989c  jz      short loc_1400098C1
0x14000989e  mov     edx, r15d
0x1400098a1  mov     rcx, r12
0x1400098a4  shl     rdx, 4
0x1400098a8  add     rdx, [rsp+390h+lpMem]
0x1400098ad  call    BfspValidateBcdEntry
0x1400098b2  mov     r14d, eax
0x1400098b5  test    eax, eax
0x1400098b7  jnz     short loc_1400098C1
0x1400098b9  add     r15d, ebx
0x1400098bc  cmp     r15d, esi
0x1400098bf  jb      short loc_14000989E
0x1400098c1  cmp     [rsp+390h+lpMem], 0
0x1400098c7  jz      short loc_1400098DF
0x1400098c9  call    cs:__imp_GetProcessHeap
0x1400098cf  mov     r8, [rsp+390h+lpMem]; lpMem
0x1400098d4  xor     edx, edx; dwFlags
0x1400098d6  mov     rcx, rax; hHeap
0x1400098d9  call    cs:__imp_HeapFree
0x1400098df  xor     esi, esi
0x1400098e1  mov     r15d, r14d
0x1400098e4  jmp     short loc_1400098EB
0x1400098e6  mov     rsi, [rsp+390h+lpMem]
0x1400098eb  test    rsi, rsi
0x1400098ee  jz      short loc_140009904
0x1400098f0  call    cs:__imp_GetProcessHeap
0x1400098f6  mov     r8, rsi; lpMem
0x1400098f9  xor     edx, edx; dwFlags
0x1400098fb  mov     rcx, rax; hHeap
0x1400098fe  call    cs:__imp_HeapFree
0x140009904  mov     r14d, [rsp+390h+var_34C]
0x140009909  test    r13, r13
0x14000990c  jz      short loc_140009916
0x14000990e  mov     rcx, r13; Handle
0x140009911  call    BcdCloseObject
0x140009916  mov     r13d, [rsp+390h+var_348]
0x14000991b  test    r12, r12
0x14000991e  jz      short loc_140009928
0x140009920  mov     rcx, r12
0x140009923  call    BcdCloseStore
0x140009928  xor     r12d, r12d
0x14000992b  test    r15d, r15d
0x14000992e  jnz     short loc_1400099A0
0x140009930  test    edi, edi
0x140009932  jns     short loc_140009944
0x140009934  mov     ecx, edi; Status
0x140009936  call    cs:__imp_RtlNtStatusToDosError
0x14000993c  mov     ecx, eax; dwErrCode
0x14000993e  call    cs:__imp_SetLastError
0x140009944  lea     rdx, aBfsrepairBcdFa; "BfsRepair: BCD failed validation check "...
0x14000994b  mov     ecx, 3
0x140009950  mov     r15d, ebx
0x140009953  call    BfspLogMessage
0x140009958  neg     [rsp+390h+var_344]
0x14000995c  mov     rcx, [rbp+290h+Src]; Src
0x140009960  sbb     edx, edx
0x140009962  mov     qword ptr [rsp+390h+var_370], r12; __int64
0x140009967  and     edx, 8000h
0x14000996d  xor     r9d, r9d
0x140009970  add     edx, 5144h
0x140009976  xor     r8d, r8d
0x140009979  call    BfsInitializeBcdStoreEx
0x14000997e  test    eax, eax
0x140009980  jnz     short loc_1400099A3
0x140009982  call    cs:__imp_GetLastError
0x140009988  lea     rdx, aBfsrepairFaile_6; "BfsRepair: Failed to repair BCD store. "...
0x14000998f  mov     ecx, 4
0x140009994  mov     r8d, eax
0x140009997  mov     edi, eax
0x140009999  call    BfspLogMessage
0x14000999e  jmp     short loc_1400099A6
0x1400099a0  mov     r15d, r12d
0x1400099a3  mov     edi, r12d
0x1400099a6  mov     rcx, [rbp+290h+pszSrc]; pszSrc
0x1400099aa  test    rcx, rcx
0x1400099ad  jz      short loc_1400099E4
0x1400099af  xor     r9d, r9d
0x1400099b2  xor     r8d, r8d
0x1400099b5  mov     edx, 10Ch
0x1400099ba  mov     esi, ebx
0x1400099bc  call    BfsServiceBootFilesEx2
0x1400099c1  test    eax, eax
0x1400099c3  jnz     short loc_1400099E7
0x1400099c5  call    cs:__imp_GetLastError
0x1400099cb  lea     rdx, aBfsrepairFaile_4; "BfsRepair: Failed to service boot files"...
0x1400099d2  mov     ecx, 4
0x1400099d7  mov     r8d, eax
0x1400099da  mov     r13d, eax
0x1400099dd  call    BfspLogMessage
0x1400099e2  jmp     short loc_1400099E7
0x1400099e4  mov     esi, r12d
0x1400099e7  call    RegisterBfsTelemetryProvider
0x1400099ec  test    eax, eax
0x1400099ee  js      loc_140009B0F
0x1400099f4  mov     ecx, cs:dword_14003F020
0x1400099fa  cmp     ecx, 5
0x1400099fd  jbe     loc_140009B0A
0x140009a03  mov     rcx, cs:qword_14003F038
0x140009a0a  mov     rdx, 800000000000h
0x140009a14  mov     rax, cs:qword_14003F030
0x140009a1b  test    rdx, rax
0x140009a1e  jz      loc_140009B0A
0x140009a24  mov     rax, rcx
0x140009a27  and     rax, rdx
0x140009a2a  cmp     rax, rcx
0x140009a2d  jnz     loc_140009B0A
0x140009a33  lea     rax, [rsp+390h+var_330]
0x140009a38  mov     [rsp+390h+var_330], ebx
0x140009a3c  mov     [rbp+290h+var_2D0], rax
0x140009a40  lea     rdx, byte_14003AAD1; int
0x140009a47  mov     eax, [rsp+390h+var_33C]
0x140009a4b  lea     rcx, dword_14003F020; int
0x140009a52  mov     [rsp+390h+var_334], eax
0x140009a56  lea     rax, [rsp+390h+var_334]
0x140009a5b  mov     [rbp+290h+var_2C0], rax
0x140009a5f  mov     eax, [rsp+390h+var_338]
0x140009a63  mov     dword ptr [rsp+390h+var_328], eax
0x140009a67  lea     rax, [rsp+390h+var_328]
0x140009a6c  mov     [rbp+290h+var_2B0], rax
0x140009a70  lea     rax, [rsp+390h+var_340]
0x140009a75  mov     [rbp+290h+var_2A0], rax
0x140009a79  lea     rax, [rsp+390h+var_344]
0x140009a7e  mov     [rbp+290h+var_290], rax
0x140009a82  lea     rax, [rsp+390h+var_348]
0x140009a87  mov     [rbp+290h+var_280], rax
0x140009a8b  lea     rax, [rsp+390h+var_34C]
0x140009a90  mov     [rbp+290h+var_270], rax
0x140009a94  lea     rax, [rsp+390h+var_350]
0x140009a99  mov     [rbp+290h+var_260], rax
0x140009a9d  lea     rax, [rbp+290h+var_2F0]
0x140009aa1  mov     [rsp+390h+var_368], rax; __int64
0x140009aa6  mov     [rsp+390h+var_370], 0Ah; ULONG
0x140009aae  mov     [rbp+290h+var_2C8], 4
0x140009ab6  mov     [rbp+290h+var_2B8], 4
0x140009abe  mov     [rbp+290h+var_2A8], 4
0x140009ac6  mov     [rsp+390h+var_340], r15d
0x140009acb  mov     [rbp+290h+var_298], 4
0x140009ad3  mov     [rsp+390h+var_344], edi
0x140009ad7  mov     [rbp+290h+var_288], 4
0x140009adf  mov     [rsp+390h+var_348], esi
0x140009ae3  mov     [rbp+290h+var_278], 4
0x140009aeb  mov     [rsp+390h+var_34C], r13d
0x140009af0  mov     [rbp+290h+var_268], 4
0x140009af8  mov     [rsp+390h+var_350], r14d
0x140009afd  mov     [rbp+290h+var_258], 4
0x140009b05  call    _tlgWriteTransfer_EventWriteTransfer
0x140009b0a  call    UnregisterBfsTelemetryProvider
0x140009b0f  cmp     cs:FileLoggingEnabled, r12d
0x140009b16  jz      short loc_140009B33
  ... truncated ...
```
