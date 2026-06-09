# InsertSecureBootEntry(ushort const *,ushort const *,ulong,int *,ushort *,int *,SBServicingFailureReason *,uint *,int *)

- ea: `0x180037338`
- end: `0x180037725`
- name: `?InsertSecureBootEntry@@YAJPEBG0KPEAHPEAG1PEAW4SBServicingFailureReason@@PEAI1@Z`
- size: `1005`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, int *, unsigned __int16 *, int *, enum SBServicingFailureReason *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x180034634`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x1800341b0`
- `0x180035cbc`
- `0x180036230`
- `0x1800367d4`
- `0x180037338`
- `0x180037b10`
- `0x180038b9c`
- `0x1800394b0`
- `0x18003a220`
- `0x18003a308`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800374db`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003754c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800374db`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003754c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800376a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800376c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800376a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800376c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037469`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003769b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800376b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037469`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003769b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800376b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003747c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003747c`

## string_xrefs

- `0x1800373ee`: `Power check failed with hr=0x%x, aborting SecureBoot update for safety`
- `0x18003741a`: `Insufficient power for SecureBoot update, aborting update (error=0x%x)`
- `0x180037458`: `Ignoring empty Update.bin`
- `0x1800375d6`: `InsertSecureBootEntry: TryCustomKEKPathFromRegistry failed with %x `
- `0x1800375ea`: `TryCustomKEKPathFromRegistry`
- `0x1800375fe`: `Custom KEK update requested but CustomKekDirectory registry value is not configured`
- `0x18003760a`: `CustomKEKNotConfigured`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall InsertSecureBootEntry(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        int *a4,
        unsigned __int16 *a5,
        int *a6,
        enum SBServicingFailureReason *a7,
        unsigned int *a8,
        int *a9)
{
  const unsigned __int16 *v10; // r15
  unsigned int v12; // edi
  int v13; // eax
  int FileContent; // ebx
  const unsigned __int16 *v15; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int8 *v17; // rax
  unsigned __int8 *v18; // r14
  int v19; // eax
  unsigned int v20; // r15d
  const WCHAR *v21; // r12
  int PairedContent; // eax
  unsigned int v23; // eax
  void *v24; // r8
  const wchar_t *v25; // rax
  HANDLE v26; // rax
  void *v27; // r14
  HANDLE v28; // rax
  unsigned __int16 *v29; // r9
  SIZE_T dwBytes; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v32; // [rsp+38h] [rbp-C8h]
  int v33; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR SourceString; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v37; // [rsp+58h] [rbp-A8h]
  unsigned int *v38; // [rsp+60h] [rbp-A0h]
  int *v39; // [rsp+68h] [rbp-98h]
  unsigned __int16 v40[264]; // [rsp+70h] [rbp-90h] BYREF

  v10 = a1;
  v37 = a5;
  v39 = a6;
  v12 = 0;
  SourceString = a2;
  v32 = a1;
  v38 = a8;
  dwBytes = 0;
  v34 = 0;
  lpMem = 0;
  memset_0(v40, 0, 0x208u);
  v33 = 0;
  v13 = CheckSufficientPowerForSecureBootUpdate(&v33);
  FileContent = v13;
  if ( v13 < 0 )
  {
    *(_DWORD *)a7 = 10;
    SBServicingLogMessage(
      (wchar_t *)L"Power check failed with hr=0x%x, aborting SecureBoot update for safety",
      (unsigned int)v13);
    v15 = L"PowerCheckFailed";
LABEL_49:
    v29 = v40;
    if ( a3 != 0x10000 )
      v29 = (unsigned __int16 *)v10;
    SBServicingLogMessage(
      (wchar_t *)L"InsertSecureBootEntry failed with %x action:%ls FileName:%ls",
      (unsigned int)FileContent,
      v15,
      v29);
    SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(L"InsertSecureBootEntry", v15);
    return (unsigned int)FileContent;
  }
  if ( !v33 )
  {
    FileContent = -2147467260;
    *(_DWORD *)a7 = 11;
    SBServicingLogMessage(
      (wchar_t *)L"Insufficient power for SecureBoot update, aborting update (error=0x%x)",
      2147500036LL);
    v15 = L"InsufficientPower";
    goto LABEL_49;
  }
  FileContent = GetFileContent(v10, 0, (unsigned int *)&dwBytes);
  if ( FileContent < 0 )
  {
    v15 = v10;
    goto LABEL_49;
  }
  if ( (unsigned int)dwBytes <= 0x14 )
  {
    FileContent = 0;
    SBServicingLogMessage((wchar_t *)L"Ignoring empty Update.bin");
    return (unsigned int)FileContent;
  }
  ProcessHeap = GetProcessHeap();
  v17 = (unsigned __int8 *)HeapAlloc(ProcessHeap, 8u, (unsigned int)dwBytes);
  v18 = v17;
  if ( !v17 )
  {
    FileContent = -2147024882;
    v15 = L"E_OUTOFMEMORY_content";
    goto LABEL_49;
  }
  FileContent = GetFileContent(v10, v17, (unsigned int *)&dwBytes);
  if ( FileContent < 0 )
  {
    v15 = L"GetFileContent2";
    goto LABEL_46;
  }
  StripAuthVariableFileWrapper(v18, &dwBytes, SourceString);
  v19 = _o__wcsicmp(SourceString, L"dbx");
  v20 = dwBytes;
  if ( v19
    || (unsigned int)IsRevocationOverrideEnabled()
    || (FileContent = IsBootmgrInDBXRevocationList(v18, v20, &v34, v37), FileContent >= 0) )
  {
    if ( v34 )
    {
      v15 = L"Passed";
      if ( a4 )
        *a4 = 1;
      goto LABEL_45;
    }
    v21 = SourceString;
    if ( !(unsigned int)_o__wcsicmp(SourceString, L"KEK") && (a3 == 4 || a3 == 0x10000) )
    {
      if ( !v38 )
      {
        v15 = L"GetPairedContentVersionNull";
        goto LABEL_45;
      }
      if ( a3 != 0x10000 )
      {
        PairedContent = GetPairedContent((unsigned __int8 **)&lpMem, (unsigned int *)&dwBytes + 1, v38, v18, v20);
        v12 = HIDWORD(dwBytes);
        FileContent = PairedContent;
      }
      if ( FileContent < 0 || a3 == 0x10000 )
      {
        v23 = TryCustomKEKPathFromRegistry((unsigned __int8 **)&lpMem, (unsigned int *)&dwBytes + 1, v40);
        FileContent = v23;
        if ( v23 )
        {
          if ( v23 == 1 )
          {
            if ( a3 == 0x10000 )
            {
              SBServicingLogMessage((wchar_t *)L"Custom KEK update requested but CustomKekDirectory registry value is not configured");
              v15 = L"CustomKEKNotConfigured";
              FileContent = -2147024894;
              goto LABEL_45;
            }
          }
          else
          {
            SBServicingLogMessage(
              (wchar_t *)L"InsertSecureBootEntry: TryCustomKEKPathFromRegistry failed with %x ",
              v23);
            if ( a3 == 0x10000 )
            {
              v15 = L"TryCustomKEKPathFromRegistry";
              goto LABEL_45;
            }
          }
        }
        v12 = HIDWORD(dwBytes);
      }
      if ( !a9 )
      {
        v15 = L"pIsMatchFoundNULL";
        FileContent = -2147467261;
        goto LABEL_45;
      }
      if ( !v12 )
      {
        SBServicingLogMessage((wchar_t *)L"Paired Content Size 0");
        *a9 = 0;
        FileContent = -2147024894;
        v15 = L"NoPairedContent";
        goto LABEL_45;
      }
      v24 = lpMem;
      *a9 = 1;
    }
    else
    {
      v24 = v18;
      v12 = v20;
    }
    FileContent = AppendContentToVariable(v21, a3, v24, (PULONG)v12, v39);
    v25 = L"AppendContentToVariable";
    if ( FileContent >= 0 )
      v25 = L"Passed";
    v15 = v25;
    goto LABEL_45;
  }
  v15 = L"IsBootmgrInDBXRevocationList";
LABEL_45:
  v10 = v32;
LABEL_46:
  v26 = GetProcessHeap();
  HeapFree(v26, 0, v18);
  v27 = lpMem;
  if ( lpMem )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v27);
  }
  if ( FileContent < 0 )
    goto LABEL_49;
  return (unsigned int)FileContent;
}

```

## disassembly

```asm
0x180037338  push    rbp
0x18003733a  push    rbx
0x18003733b  push    rsi
0x18003733c  push    rdi
0x18003733d  push    r12
0x18003733f  push    r13
0x180037341  push    r14
0x180037343  push    r15
0x180037345  lea     rbp, [rsp-198h]
0x18003734d  sub     rsp, 298h
0x180037354  mov     rax, cs:__security_cookie
0x18003735b  xor     rax, rsp
0x18003735e  mov     [rbp+1D0h+var_50], rax
0x180037365  mov     rax, [rbp+1D0h+arg_20]
0x18003736c  xor     ebx, ebx
0x18003736e  mov     r14, [rbp+1D0h+arg_30]
0x180037375  mov     esi, r8d
0x180037378  mov     r13, [rbp+1D0h+arg_40]
0x18003737f  mov     r15, rcx
0x180037382  mov     [rsp+2D0h+var_278], rax
0x180037387  mov     r8d, 208h; Size
0x18003738d  mov     rax, [rbp+1D0h+arg_28]
0x180037394  mov     r12, r9
0x180037397  mov     [rsp+2D0h+var_268], rax
0x18003739c  mov     edi, ebx
0x18003739e  mov     rax, [rbp+1D0h+arg_38]
0x1800373a5  mov     [rsp+2D0h+SourceString], rdx
0x1800373aa  xor     edx, edx; Val
0x1800373ac  mov     [rsp+2D0h+var_298], rcx
0x1800373b1  lea     rcx, [rsp+2D0h+var_260]; void *
0x1800373b6  mov     [rsp+2D0h+var_270], rax
0x1800373bb  mov     dword ptr [rsp+2D0h+dwBytes], ebx
0x1800373bf  mov     [rsp+2D0h+var_28C], ebx
0x1800373c3  mov     [rsp+2D0h+lpMem], rbx
0x1800373c8  mov     dword ptr [rsp+2D0h+dwBytes+4], ebx
0x1800373cc  call    memset_0
0x1800373d1  lea     rcx, [rsp+2D0h+var_290]; int *
0x1800373d6  mov     [rsp+2D0h+var_290], ebx
0x1800373da  call    ?CheckSufficientPowerForSecureBootUpdate@@YAJPEAH@Z; CheckSufficientPowerForSecureBootUpdate(int *)
0x1800373df  mov     ebx, eax
0x1800373e1  test    eax, eax
0x1800373e3  jns     short loc_180037406
0x1800373e5  mov     edx, eax
0x1800373e7  mov     dword ptr [r14], 0Ah
0x1800373ee  lea     rcx, aPowerCheckFail; "Power check failed with hr=0x%x, aborti"...
0x1800373f5  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800373fa  lea     rdi, aPowercheckfail; "PowerCheckFailed"
0x180037401  jmp     loc_1800376D1
0x180037406  cmp     [rsp+2D0h+var_290], edi
0x18003740a  jnz     short loc_180037432
0x18003740c  mov     ebx, 80004004h
0x180037411  mov     dword ptr [r14], 0Bh
0x180037418  mov     edx, ebx
0x18003741a  lea     rcx, aInsufficientPo; "Insufficient power for SecureBoot updat"...
0x180037421  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180037426  lea     rdi, aInsufficientpo; "InsufficientPower"
0x18003742d  jmp     loc_1800376D1
0x180037432  lea     r8, [rsp+2D0h+dwBytes]; unsigned int *
0x180037437  xor     edx, edx; unsigned __int8 *
0x180037439  mov     rcx, r15; unsigned __int16 *
0x18003743c  call    ?GetFileContent@@YAJPEBGQEAEPEAK@Z; GetFileContent(ushort const *,uchar * const,ulong *)
0x180037441  mov     ebx, eax
0x180037443  test    eax, eax
0x180037445  jns     short loc_18003744F
0x180037447  mov     rdi, r15
0x18003744a  jmp     loc_1800376D1
0x18003744f  cmp     dword ptr [rsp+2D0h+dwBytes], 14h
0x180037454  ja      short loc_180037469
0x180037456  xor     ebx, ebx
0x180037458  lea     rcx, aIgnoringEmptyU; "Ignoring empty Update.bin"
0x18003745f  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180037464  jmp     loc_180037700
0x180037469  call    cs:__imp_GetProcessHeap
0x18003746f  mov     r8d, dword ptr [rsp+2D0h+dwBytes]; dwBytes
0x180037474  mov     edx, 8; dwFlags
0x180037479  mov     rcx, rax; hHeap
0x18003747c  call    cs:__imp_HeapAlloc
0x180037482  mov     r14, rax
0x180037485  test    rax, rax
0x180037488  jnz     short loc_18003749B
0x18003748a  mov     ebx, 8007000Eh
0x18003748f  lea     rdi, aEOutofmemoryCo; "E_OUTOFMEMORY_content"
0x180037496  jmp     loc_1800376D1
0x18003749b  lea     r8, [rsp+2D0h+dwBytes]; unsigned int *
0x1800374a0  mov     rdx, r14; unsigned __int8 *
0x1800374a3  mov     rcx, r15; unsigned __int16 *
0x1800374a6  call    ?GetFileContent@@YAJPEBGQEAEPEAK@Z; GetFileContent(ushort const *,uchar * const,ulong *)
0x1800374ab  mov     ebx, eax
0x1800374ad  test    eax, eax
0x1800374af  jns     short loc_1800374BD
0x1800374b1  lea     rdi, aGetfilecontent; "GetFileContent2"
0x1800374b8  jmp     loc_18003769B
0x1800374bd  mov     r8, [rsp+2D0h+SourceString]
0x1800374c2  lea     rdx, [rsp+2D0h+dwBytes]
0x1800374c7  mov     rcx, r14
0x1800374ca  call    StripAuthVariableFileWrapper
0x1800374cf  mov     rcx, [rsp+2D0h+SourceString]
0x1800374d4  lea     rdx, aDbx; "dbx"
0x1800374db  call    cs:__imp__o__wcsicmp
0x1800374e1  mov     r15d, dword ptr [rsp+2D0h+dwBytes]
0x1800374e6  test    eax, eax
0x1800374e8  jnz     short loc_18003751A
0x1800374ea  call    ?IsRevocationOverrideEnabled@@YAHXZ; IsRevocationOverrideEnabled(void)
0x1800374ef  test    eax, eax
0x1800374f1  jnz     short loc_18003751A
0x1800374f3  mov     r9, [rsp+2D0h+var_278]; unsigned __int16 *
0x1800374f8  lea     r8, [rsp+2D0h+var_28C]; int *
0x1800374fd  mov     edx, r15d; unsigned int
0x180037500  mov     rcx, r14; unsigned __int8 *
0x180037503  call    ?IsBootmgrInDBXRevocationList@@YAJPEAEKPEAHPEAG@Z; IsBootmgrInDBXRevocationList(uchar *,ulong,int *,ushort *)
0x180037508  mov     ebx, eax
0x18003750a  test    eax, eax
0x18003750c  jns     short loc_18003751A
0x18003750e  lea     rdi, aIsbootmgrindbx_0; "IsBootmgrInDBXRevocationList"
0x180037515  jmp     loc_180037696
0x18003751a  cmp     [rsp+2D0h+var_28C], edi
0x18003751e  jz      short loc_18003753D
0x180037520  lea     rdi, aPassed; "Passed"
0x180037527  test    r12, r12
0x18003752a  jz      loc_180037696
0x180037530  mov     dword ptr [r12], 1
0x180037538  jmp     loc_180037696
0x18003753d  mov     r12, [rsp+2D0h+SourceString]
0x180037542  lea     rdx, aKek; "KEK"
0x180037549  mov     rcx, r12
0x18003754c  call    cs:__imp__o__wcsicmp
0x180037552  test    eax, eax
0x180037554  jnz     loc_180037660
0x18003755a  cmp     esi, 4
0x18003755d  jz      short loc_18003756B
0x18003755f  cmp     esi, 10000h
0x180037565  jnz     loc_180037660
0x18003756b  mov     rax, [rsp+2D0h+var_270]
0x180037570  test    rax, rax
0x180037573  jnz     short loc_180037581
0x180037575  lea     rdi, aGetpairedconte_1; "GetPairedContentVersionNull"
0x18003757c  jmp     loc_180037696
0x180037581  cmp     esi, 10000h
0x180037587  jz      short loc_1800375A9
0x180037589  mov     r9, r14; unsigned __int8 *
0x18003758c  mov     dword ptr [rsp+2D0h+var_2B0], r15d; unsigned int
0x180037591  mov     r8, rax; unsigned int *
0x180037594  lea     rdx, [rsp+2D0h+dwBytes+4]; unsigned int *
0x180037599  lea     rcx, [rsp+2D0h+lpMem]; unsigned __int8 **
0x18003759e  call    ?GetPairedContent@@YAJPEAPEAEPEAI1PEAEK@Z; GetPairedContent(uchar * *,uint *,uint *,uchar *,ulong)
0x1800375a3  mov     edi, dword ptr [rsp+2D0h+dwBytes+4]
0x1800375a7  mov     ebx, eax
0x1800375a9  test    ebx, ebx
0x1800375ab  js      short loc_1800375B5
0x1800375ad  cmp     esi, 10000h
0x1800375b3  jnz     short loc_18003761C
0x1800375b5  lea     r8, [rsp+2D0h+var_260]; unsigned __int16 *
0x1800375ba  lea     rdx, [rsp+2D0h+dwBytes+4]; unsigned int *
0x1800375bf  lea     rcx, [rsp+2D0h+lpMem]; unsigned __int8 **
0x1800375c4  call    ?TryCustomKEKPathFromRegistry@@YAJPEAPEAEPEAIPEAG@Z; TryCustomKEKPathFromRegistry(uchar * *,uint *,ushort *)
0x1800375c9  mov     ebx, eax
0x1800375cb  test    eax, eax
0x1800375cd  jz      short loc_180037618
0x1800375cf  cmp     eax, 1
0x1800375d2  jz      short loc_1800375F6
0x1800375d4  mov     edx, eax
0x1800375d6  lea     rcx, aInsertsecurebo_7; "InsertSecureBootEntry: TryCustomKEKPath"...
0x1800375dd  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800375e2  cmp     esi, 10000h
0x1800375e8  jnz     short loc_180037618
0x1800375ea  lea     rdi, aTrycustomkekpa; "TryCustomKEKPathFromRegistry"
0x1800375f1  jmp     loc_180037696
0x1800375f6  cmp     esi, 10000h
0x1800375fc  jnz     short loc_180037618
0x1800375fe  lea     rcx, aCustomKekUpdat; "Custom KEK update requested but CustomK"...
0x180037605  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003760a  lea     rdi, aCustomkeknotco; "CustomKEKNotConfigured"
0x180037611  mov     ebx, 80070002h
0x180037616  jmp     short loc_180037696
0x180037618  mov     edi, dword ptr [rsp+2D0h+dwBytes+4]
0x18003761c  test    r13, r13
0x18003761f  jnz     short loc_18003762F
0x180037621  lea     rdi, aPismatchfoundn; "pIsMatchFoundNULL"
0x180037628  mov     ebx, 80004003h
0x18003762d  jmp     short loc_180037696
0x18003762f  test    edi, edi
0x180037631  jnz     short loc_180037651
0x180037633  lea     rcx, aPairedContentS; "Paired Content Size 0"
0x18003763a  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003763f  mov     [r13+0], edi
0x180037643  mov     ebx, 80070002h
0x180037648  lea     rdi, aNopairedconten; "NoPairedContent"
0x18003764f  jmp     short loc_180037696
0x180037651  mov     r8, [rsp+2D0h+lpMem]
0x180037656  mov     dword ptr [r13+0], 1
0x18003765e  jmp     short loc_180037666
0x180037660  mov     r8, r14; Value
0x180037663  mov     edi, r15d
0x180037666  mov     rax, [rsp+2D0h+var_268]
0x18003766b  mov     r9d, edi; ReturnLength
0x18003766e  mov     edx, esi; unsigned int
0x180037670  mov     [rsp+2D0h+var_2B0], rax; int *
0x180037675  mov     rcx, r12; SourceString
0x180037678  call    ?AppendContentToVariable@@YAJPEBGKQEAEKPEAH@Z; AppendContentToVariable(ushort const *,ulong,uchar * const,ulong,int *)
0x18003767d  mov     ebx, eax
0x18003767f  lea     rdi, aPassed; "Passed"
0x180037686  test    ebx, ebx
0x180037688  lea     rax, aAppendcontentt; "AppendContentToVariable"
0x18003768f  cmovns  rax, rdi
0x180037693  mov     rdi, rax
0x180037696  mov     r15, [rsp+2D0h+var_298]
0x18003769b  call    cs:__imp_GetProcessHeap
0x1800376a1  mov     r8, r14; lpMem
0x1800376a4  xor     edx, edx; dwFlags
0x1800376a6  mov     rcx, rax; hHeap
0x1800376a9  call    cs:__imp_HeapFree
0x1800376af  mov     r14, [rsp+2D0h+lpMem]
0x1800376b4  test    r14, r14
0x1800376b7  jz      short loc_1800376CD
0x1800376b9  call    cs:__imp_GetProcessHeap
0x1800376bf  mov     r8, r14; lpMem
0x1800376c2  xor     edx, edx; dwFlags
0x1800376c4  mov     rcx, rax; hHeap
0x1800376c7  call    cs:__imp_HeapFree
0x1800376cd  test    ebx, ebx
0x1800376cf  jns     short loc_180037700
0x1800376d1  cmp     esi, 10000h
0x1800376d7  lea     r9, [rsp+2D0h+var_260]
0x1800376dc  mov     r8, rdi
0x1800376df  lea     rcx, aInsertsecurebo_0; "InsertSecureBootEntry failed with %x ac"...
0x1800376e6  cmovnz  r9, r15
0x1800376ea  mov     edx, ebx
0x1800376ec  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800376f1  mov     rdx, rdi; unsigned __int16 *
0x1800376f4  lea     rcx, aInsertsecurebo; "InsertSecureBootEntry"
0x1800376fb  call    ?SBServicingCoreFunctionFailed@SBServicingCoreTelemetryProvider@@SAXPEBG0@Z; SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(ushort const *,ushort const *)
0x180037700  mov     eax, ebx
0x180037702  mov     rcx, [rbp+1D0h+var_50]
0x180037709  xor     rcx, rsp; StackCookie
0x18003770c  call    __security_check_cookie
0x180037711  add     rsp, 298h
0x180037718  pop     r15
0x18003771a  pop     r14
0x18003771c  pop     r13
0x18003771e  pop     r12
0x180037720  pop     rdi
0x180037721  pop     rsi
0x180037722  pop     rbx
0x180037723  pop     rbp
0x180037724  retn
```
