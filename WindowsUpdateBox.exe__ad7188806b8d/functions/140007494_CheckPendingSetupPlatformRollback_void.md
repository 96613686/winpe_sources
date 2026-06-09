# CheckPendingSetupPlatformRollback(void)

- ea: `0x140007494`
- end: `0x1400076c1`
- name: `?CheckPendingSetupPlatformRollback@@YAJXZ`
- size: `557`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140013894`

## callees

- `0x140002116`
- `0x140005e4c`
- `0x140007494`
- `0x1400076c8`
- `0x14000923c`
- `0x14000bbc4`
- `0x14000e2a0`
- `0x1400107c8`
- `0x140010a14`
- `0x140012f84`
- `0x1400135b8`
- `0x140016bb4`
- `0x1400276dc`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140007516`
- `KERNEL32!HeapFree` at `0x140007544`
- `KERNEL32!HeapFree` at `0x140007516`
- `KERNEL32!HeapFree` at `0x140007544`
- `KERNEL32!GetProcessHeap` at `0x140007501`
- `KERNEL32!GetProcessHeap` at `0x14000752f`
- `KERNEL32!GetProcessHeap` at `0x140007501`
- `KERNEL32!GetProcessHeap` at `0x14000752f`

## string_xrefs

- `0x1400074c5`: `RollbackOnline`
- `0x1400075af`: `RollbackOnline`
- `0x14000760c`: `Executing pending rollback command: [%s]...`
- `0x140007687`: `Rollback command returned: [0x%X]`
- `0x1400076a8`: `Error launching rollback command: hr = [0x%X]`

## pseudocode

```c
__int64 __fastcall CheckPendingSetupPlatformRollback(__int64 a1)
{
  __int64 v1; // rbx
  int v2; // edx
  int v3; // ecx
  int v4; // r8d
  const WCHAR *v5; // rsi
  unsigned int v6; // edi
  HANDLE ProcessHeap; // rax
  HANDLE v8; // rax
  int ExpandedString; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  HANDLE v14; // rcx
  HANDLE v15; // rcx
  char *v16; // rax
  DWORD v17; // [rsp+20h] [rbp-69h]
  __int64 v18; // [rsp+28h] [rbp-61h]
  struct _STARTUPINFOW v19; // [rsp+50h] [rbp-39h] BYREF
  DWORD v20; // [rsp+F0h] [rbp+67h] BYREF
  LPCWSTR lpSrc; // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v22; // [rsp+100h] [rbp+77h]

  lpSrc = 0;
  v1 = 0;
  v22 = 0;
  v20 = 0;
  if ( (int)CRegUtilT<unsigned short *,CRegType,0,1>::GetValue(
              a1,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\RunOnce",
              L"RollbackOnline",
              &lpSrc) < 0
    && (int)CRegUtilT<unsigned short *,CRegType2,0,1>::GetValue(v3, v2, v4, (unsigned int)&lpSrc) < 0 )
  {
    v5 = lpSrc;
LABEL_4:
    v6 = 0;
    goto LABEL_5;
  }
  v5 = lpSrc;
  if ( !StrStrIC(lpSrc) )
    goto LABEL_4;
  ExpandedString = CDlpHelpersT<CEmptyType>::CreateExpandedString(v5);
  v6 = ExpandedString;
  if ( ExpandedString >= 0 )
  {
    v1 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(&lpSrc, v22);
    v12 = CRegUtilT<unsigned short *,CRegType,0,1>::DeleteValueIfExists(
            v11,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\RunOnce",
            L"RollbackOnline");
    v6 = v12;
    if ( v12 < 0
      || (v12 = CDlpHelpersT<CEmptyType>::FlushRegistryKey(
                  v13,
                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\RunOnce"),
          v6 = v12,
          v12 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12);
      v5 = lpSrc;
    }
    else
    {
      v14 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v14 = g_shLogFile;
      v5 = lpSrc;
      OutputMsg(v14, g_shLogEvent, L"Executing pending rollback command: [%s]...", lpSrc);
      memset_0(&v19, 0, sizeof(v19));
      v19.cb = 104;
      v19.dwFlags |= 1u;
      v19.wShowWindow = 0;
      v6 = CMiscHelpersT<CEmptyType>::LaunchProcessInternal(0, (__int64)v5, &v19, 0x8000000u, v17, v18, &v20);
      v15 = 0;
      v16 = (char *)g_shLogFile - 1;
      if ( (v6 & 0x80000000) != 0 )
      {
        if ( (unsigned __int64)v16 <= 0xFFFFFFFFFFFFFFFDuLL )
          v15 = g_shLogFile;
        OutputMsg(v15, g_shLogEvent, L"Error launching rollback command: hr = [0x%X]", v6);
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
      }
      else
      {
        if ( (unsigned __int64)v16 <= 0xFFFFFFFFFFFFFFFDuLL )
          v15 = g_shLogFile;
        OutputMsg(v15, g_shLogEvent, L"Rollback command returned: [0x%X]", v20);
      }
    }
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)ExpandedString);
    v1 = v22;
  }
LABEL_5:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v1 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v5 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, (LPVOID)(v5 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v6;
}

```

## disassembly

```asm
0x140007494  push    rbp
0x140007496  push    rbx
0x140007497  push    rsi
0x140007498  push    rdi
0x140007499  push    r14
0x14000749b  lea     rbp, [rsp-37h]
0x1400074a0  sub     rsp, 0C0h
0x1400074a7  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x1400074af  xor     r14d, r14d
0x1400074b2  mov     [rbp+57h+lpSrc], r14
0x1400074b6  mov     ebx, r14d
0x1400074b9  mov     [rbp+57h+arg_10], rbx
0x1400074bd  mov     [rbp+57h+arg_0], r14d
0x1400074c1  lea     r9, [rbp+57h+lpSrc]
0x1400074c5  lea     r8, ValueName; "RollbackOnline"
0x1400074cc  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400074d3  call    ?GetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAGPEAK@Z; CRegUtilT<ushort *,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,ushort * *,ulong *)
0x1400074d8  test    eax, eax
0x1400074da  jns     loc_140007568
0x1400074e0  lea     r9, [rbp+57h+lpSrc]
0x1400074e4  call    ?GetValue@?$CRegUtilT@PEAGUCRegType2@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAGPEAK@Z; CRegUtilT<ushort *,CRegType2,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,ushort * *,ulong *)
0x1400074e9  test    eax, eax
0x1400074eb  jns     short loc_140007568
0x1400074ed  mov     rsi, [rbp+57h+lpSrc]
0x1400074f1  mov     edi, r14d
0x1400074f4  mov     ecx, edi
0x1400074f6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400074fb  nop
0x1400074fc  test    rbx, rbx
0x1400074ff  jz      short loc_14000752A
0x140007501  call    cs:__imp_GetProcessHeap
0x140007508  nop     dword ptr [rax+rax+00h]
0x14000750d  mov     rcx, rax; hHeap
0x140007510  lea     r8, [rbx-4]; lpMem
0x140007514  xor     edx, edx; dwFlags
0x140007516  call    cs:__imp_HeapFree
0x14000751d  nop     dword ptr [rax+rax+00h]
0x140007522  xor     ecx, ecx
0x140007524  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140007529  nop
0x14000752a  test    rsi, rsi
0x14000752d  jz      short loc_140007557
0x14000752f  call    cs:__imp_GetProcessHeap
0x140007536  nop     dword ptr [rax+rax+00h]
0x14000753b  mov     rcx, rax; hHeap
0x14000753e  lea     r8, [rsi-4]; lpMem
0x140007542  xor     edx, edx; dwFlags
0x140007544  call    cs:__imp_HeapFree
0x14000754b  nop     dword ptr [rax+rax+00h]
0x140007550  xor     ecx, ecx
0x140007552  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140007557  mov     eax, edi
0x140007559  add     rsp, 0C0h
0x140007560  pop     r14
0x140007562  pop     rdi
0x140007563  pop     rsi
0x140007564  pop     rbx
0x140007565  pop     rbp
0x140007566  retn
0x140007568  mov     rsi, [rbp+57h+lpSrc]
0x14000756c  mov     rcx, rsi
0x14000756f  call    StrStrIC
0x140007574  test    rax, rax
0x140007577  jz      loc_1400074F1
0x14000757d  lea     rdx, [rbp+57h+arg_10]
0x140007581  mov     rcx, rsi; lpSrc
0x140007584  call    ?CreateExpandedString@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CDlpHelpersT<CEmptyType>::CreateExpandedString(ushort const *,ushort * *)
0x140007589  mov     edi, eax
0x14000758b  test    eax, eax
0x14000758d  jns     short loc_14000759F
0x14000758f  mov     ecx, eax
0x140007591  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140007596  mov     rbx, [rbp+57h+arg_10]
0x14000759a  jmp     loc_1400074F4
0x14000759f  mov     rbx, r14
0x1400075a2  mov     rdx, [rbp+57h+arg_10]
0x1400075a6  lea     rcx, [rbp+57h+lpSrc]
0x1400075aa  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x1400075af  lea     r8, ValueName; "RollbackOnline"
0x1400075b6  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400075bd  call    ?DeleteValueIfExists@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1@Z; CRegUtilT<ushort *,CRegType,0,1>::DeleteValueIfExists(HKEY__ *,ushort const *,ushort const *)
0x1400075c2  mov     edi, eax
0x1400075c4  test    eax, eax
0x1400075c6  jns     short loc_1400075D8
0x1400075c8  mov     ecx, eax
0x1400075ca  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400075cf  mov     rsi, [rbp+57h+lpSrc]
0x1400075d3  jmp     loc_1400074F4
0x1400075d8  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400075df  call    ?FlushRegistryKey@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAUHKEY__@@PEBG@Z; CDlpHelpersT<CEmptyType>::FlushRegistryKey(HKEY__ *,ushort const *)
0x1400075e4  mov     edi, eax
0x1400075e6  test    eax, eax
0x1400075e8  js      short loc_1400075C8
0x1400075ea  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x1400075f1  lea     rax, [r8-1]
0x1400075f5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400075f9  setnbe  al
0x1400075fc  mov     rcx, r14
0x1400075ff  test    al, al
0x140007601  cmovz   rcx, r8; hFile
0x140007605  mov     rsi, [rbp+57h+lpSrc]
0x140007609  mov     r9, rsi
0x14000760c  lea     r8, aExecutingPendi; "Executing pending rollback command: [%s"...
0x140007613  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14000761a  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14000761f  mov     edi, 68h ; 'h'
0x140007624  mov     r8d, edi; Size
0x140007627  xor     edx, edx; Val
0x140007629  lea     rcx, [rbp+57h+var_90]; void *
0x14000762d  call    memset_0
0x140007632  mov     [rbp+57h+var_90], edi
0x140007635  or      [rbp+57h+var_54], 1
0x140007639  mov     [rbp+57h+var_50], r14w
0x14000763e  lea     rax, [rbp+57h+arg_0]
0x140007642  mov     [rsp+0E0h+var_B0], rax
0x140007647  mov     r9d, 8000000h
0x14000764d  lea     r8, [rbp+57h+var_90]
0x140007651  mov     rdx, rsi
0x140007654  xor     ecx, ecx
0x140007656  call    ?LaunchProcessInternal@?$CMiscHelpersT@VCEmptyType@@@@CAJPEBG0PEAU_STARTUPINFOW@@KHIPEAK@Z; CMiscHelpersT<CEmptyType>::LaunchProcessInternal(ushort const *,ushort const *,_STARTUPINFOW *,ulong,int,uint,ulong *)
0x14000765b  mov     edi, eax
0x14000765d  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140007664  mov     rcx, r14
0x140007667  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14000766e  test    eax, eax
0x140007670  lea     rax, [r8-1]
0x140007674  js      short loc_140007698
0x140007676  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000767a  setnbe  al
0x14000767d  test    al, al
0x14000767f  cmovz   rcx, r8; hFile
0x140007683  mov     r9d, [rbp+57h+arg_0]
0x140007687  lea     r8, aRollbackComman; "Rollback command returned: [0x%X]"
0x14000768e  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140007693  jmp     loc_1400074F4
0x140007698  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000769c  setnbe  al
0x14000769f  test    al, al
0x1400076a1  cmovz   rcx, r8; hFile
0x1400076a5  mov     r9d, edi
0x1400076a8  lea     r8, aErrorLaunching; "Error launching rollback command: hr = "...
0x1400076af  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x1400076b4  mov     ecx, edi
0x1400076b6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400076bb  jmp     loc_1400074F4
```
