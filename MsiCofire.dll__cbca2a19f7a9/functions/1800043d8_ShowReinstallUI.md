# ShowReinstallUI

- ea: `0x1800043d8`
- end: `0x180004655`
- name: `ShowReinstallUI`
- size: `637`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int *pnButton)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180003ac8`

## callees

- `0x180002590`
- `0x180003ff8`
- `0x18000425c`
- `0x1800043d8`
- `0x180007013`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180004620`
- `KERNEL32!HeapFree` at `0x180004639`
- `KERNEL32!HeapFree` at `0x180004620`
- `KERNEL32!HeapFree` at `0x180004639`
- `KERNEL32!HeapAlloc` at `0x180004537`
- `KERNEL32!HeapAlloc` at `0x180004598`
- `KERNEL32!HeapAlloc` at `0x180004537`
- `KERNEL32!HeapAlloc` at `0x180004598`
- `KERNEL32!GetProcessHeap` at `0x180004526`
- `KERNEL32!GetProcessHeap` at `0x180004587`
- `KERNEL32!GetProcessHeap` at `0x180004612`
- `KERNEL32!GetProcessHeap` at `0x18000462b`
- `KERNEL32!GetProcessHeap` at `0x180004526`
- `KERNEL32!GetProcessHeap` at `0x180004587`
- `KERNEL32!GetProcessHeap` at `0x180004612`
- `KERNEL32!GetProcessHeap` at `0x18000462b`
- `USER32!GetSystemMetrics` at `0x180004468`
- `USER32!GetSystemMetrics` at `0x180004473`
- `USER32!GetSystemMetrics` at `0x1800044ce`
- `USER32!GetSystemMetrics` at `0x1800044db`
- `USER32!GetSystemMetrics` at `0x180004468`
- `USER32!GetSystemMetrics` at `0x180004473`
- `USER32!GetSystemMetrics` at `0x1800044ce`
- `USER32!GetSystemMetrics` at `0x1800044db`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x1800045e7`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x1800045e7`
- `COMCTL32!__imp_LoadIconWithScaleDown` at `0x180004490`
- `COMCTL32!__imp_LoadIconWithScaleDown` at `0x1800044f8`
- `COMCTL32!__imp_LoadIconWithScaleDown` at `0x180004490`
- `COMCTL32!__imp_LoadIconWithScaleDown` at `0x1800044f8`

## string_xrefs

- `0x1800044ad`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`
- `0x180004604`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`
- `0x1800044a2`: `ShowReinstallUI`
- `0x1800045f9`: `ShowReinstallUI`

## pseudocode

```c
__int64 __fastcall ShowReinstallUI(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 *a3, int *pnButton)
{
  WCHAR *v8; // rdi
  int SystemMetrics; // ebx
  int v10; // eax
  HRESULT v11; // eax
  unsigned int v12; // ebx
  int v13; // r9d
  int v14; // ebx
  int v15; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v17; // rax
  unsigned int v18; // r8d
  WCHAR *v19; // rsi
  HRESULT MainText; // eax
  int v21; // r9d
  HANDLE v22; // rax
  unsigned __int16 *v23; // rax
  HANDLE v24; // rax
  HANDLE v25; // rax
  unsigned int phico; // [rsp+20h] [rbp-E0h]
  HICON v28; // [rsp+30h] [rbp-D0h] BYREF
  HICON v29; // [rsp+38h] [rbp-C8h] BYREF
  int v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+44h] [rbp-BCh]
  int v32; // [rsp+4Ch] [rbp-B4h]
  __int64 v33; // [rsp+50h] [rbp-B0h]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+60h] [rbp-A0h] BYREF
  BOOL pfVerificationFlagChecked; // [rsp+168h] [rbp+68h] BYREF

  memset_0(&pTaskConfig.dwCommonButtons, 0, 0x88u);
  v8 = 0;
  v30 = 6;
  pfVerificationFlagChecked = 0;
  *pnButton = 7;
  v32 = 7;
  pTaskConfig.hInstance = g_hInstance;
  v31 = 1014;
  v33 = 1015;
  pTaskConfig.cbSize = 160;
  pTaskConfig.hwndParent = 0;
  pTaskConfig.dwFlags = 78;
  v28 = 0;
  v29 = 0;
  SystemMetrics = GetSystemMetrics(12);
  v10 = GetSystemMetrics(11);
  v11 = LoadIconWithScaleDown(0, (PCWSTR)0x7F01, v10, SystemMetrics, &v28);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 170;
LABEL_3:
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "ShowReinstallUI", v13, v11);
    return v12;
  }
  pTaskConfig.hMainIcon = v28;
  v14 = GetSystemMetrics(50);
  v15 = GetSystemMetrics(49);
  v11 = LoadIconWithScaleDown(0, (PCWSTR)0x7F04, v15, v14, &v29);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 176;
    goto LABEL_3;
  }
  pTaskConfig.hFooterIcon = v29;
  pTaskConfig.pszWindowTitle = (PCWSTR)1010;
  pTaskConfig.pszMainInstruction = (PCWSTR)1012;
  ProcessHeap = GetProcessHeap();
  v17 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
  v19 = v17;
  if ( !v17 )
  {
    v11 = -2147024882;
    v13 = 185;
    v12 = -2147024882;
    goto LABEL_3;
  }
  MainText = LoadMainText(a2, v17, v18);
  v12 = MainText;
  if ( MainText >= 0 )
  {
    pTaskConfig.pszContent = v19;
    pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)&v30;
    pTaskConfig.cButtons = 2;
    v22 = GetProcessHeap();
    v23 = (unsigned __int16 *)HeapAlloc(v22, 0, 0x800u);
    v8 = v23;
    if ( v23 )
    {
      MainText = LoadExpandedText(a1, a2, a3, v23, phico);
      v12 = MainText;
      if ( MainText >= 0 )
      {
        pTaskConfig.pszExpandedInformation = v8;
        MainText = TaskDialogIndirect(&pTaskConfig, pnButton, 0, &pfVerificationFlagChecked);
        v12 = MainText;
        if ( MainText >= 0 )
          goto LABEL_17;
        v21 = 203;
      }
      else
      {
        v21 = 199;
      }
    }
    else
    {
      MainText = -2147024882;
      v21 = 197;
      v12 = -2147024882;
    }
  }
  else
  {
    v21 = 187;
  }
  DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "ShowReinstallUI", v21, MainText);
LABEL_17:
  v24 = GetProcessHeap();
  HeapFree(v24, 0, v19);
  if ( v8 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v8);
  }
  return v12;
}

```

## disassembly

```asm
0x1800043d8  push    rbp
0x1800043da  push    rbx
0x1800043db  push    rsi
0x1800043dc  push    rdi
0x1800043dd  push    r12
0x1800043df  push    r13
0x1800043e1  push    r14
0x1800043e3  push    r15
0x1800043e5  lea     rbp, [rsp-8]
0x1800043ea  sub     rsp, 108h
0x1800043f1  mov     r12, r8
0x1800043f4  mov     r14, rdx
0x1800043f7  mov     r13, rcx
0x1800043fa  xor     edx, edx; Val
0x1800043fc  mov     r8d, 88h; Size
0x180004402  lea     rcx, [rsp+140h+pTaskConfig.dwCommonButtons]; void *
0x180004407  mov     r15, r9
0x18000440a  call    memset_0
0x18000440f  xor     edi, edi
0x180004411  mov     [rsp+140h+var_100], 6
0x180004419  mov     eax, 7
0x18000441e  mov     [rbp+40h+pfVerificationFlagChecked], edi
0x180004421  mov     [r15], eax
0x180004424  mov     [rsp+140h+var_F4], eax
0x180004428  mov     rax, cs:g_hInstance
0x18000442f  lea     ecx, [rdi+0Ch]; nIndex
0x180004432  mov     [rsp+140h+pTaskConfig.hInstance], rax
0x180004437  mov     [rsp+140h+var_FC], 3F6h
0x180004440  mov     [rsp+140h+var_F0], 3F7h
0x180004449  mov     [rsp+140h+pTaskConfig.cbSize], 0A0h
0x180004451  mov     [rsp+140h+pTaskConfig.hwndParent], rdi
0x180004456  mov     [rsp+140h+pTaskConfig.dwFlags], 4Eh ; 'N'
0x18000445e  mov     [rsp+140h+var_110], rdi
0x180004463  mov     [rsp+140h+var_108], rdi
0x180004468  call    cs:__imp_GetSystemMetrics
0x18000446e  lea     ecx, [rdi+0Bh]; nIndex
0x180004471  mov     ebx, eax
0x180004473  call    cs:__imp_GetSystemMetrics
0x180004479  lea     rcx, [rsp+140h+var_110]
0x18000447e  mov     r9d, ebx; cy
0x180004481  mov     qword ptr [rsp+140h+phico], rcx; phico
0x180004486  mov     r8d, eax; cx
0x180004489  xor     ecx, ecx; hinst
0x18000448b  mov     edx, 7F01h; pszName
0x180004490  call    cs:__imp_LoadIconWithScaleDown
0x180004496  mov     ebx, eax
0x180004498  test    eax, eax
0x18000449a  jns     short loc_1800044C0
0x18000449c  mov     r9d, 0AAh
0x1800044a2  lea     r8, aShowreinstallu; "ShowReinstallUI"
0x1800044a9  mov     [rsp+140h+phico], eax
0x1800044ad  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x1800044b4  xor     ecx, ecx; Level
0x1800044b6  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x1800044bb  jmp     loc_18000463F
0x1800044c0  mov     rax, [rsp+140h+var_110]
0x1800044c5  mov     ecx, 32h ; '2'; nIndex
0x1800044ca  mov     qword ptr [rbp+40h+pTaskConfig.24h], rax
0x1800044ce  call    cs:__imp_GetSystemMetrics
0x1800044d4  mov     ecx, 31h ; '1'; nIndex
0x1800044d9  mov     ebx, eax
0x1800044db  call    cs:__imp_GetSystemMetrics
0x1800044e1  lea     rcx, [rsp+140h+var_108]
0x1800044e6  mov     r9d, ebx; cy
0x1800044e9  mov     qword ptr [rsp+140h+phico], rcx; unsigned int
0x1800044ee  mov     r8d, eax; cx
0x1800044f1  xor     ecx, ecx; hinst
0x1800044f3  mov     edx, 7F04h; pszName
0x1800044f8  call    cs:__imp_LoadIconWithScaleDown
0x1800044fe  mov     ebx, eax
0x180004500  test    eax, eax
0x180004502  jns     short loc_18000450C
0x180004504  mov     r9d, 0B0h
0x18000450a  jmp     short loc_1800044A2
0x18000450c  mov     rax, [rsp+140h+var_108]
0x180004511  mov     qword ptr [rbp+40h+pTaskConfig.7Ch], rax
0x180004515  mov     [rsp+140h+pTaskConfig.pszWindowTitle], 3F2h
0x18000451e  mov     [rbp+40h+pTaskConfig.pszMainInstruction], 3F4h
0x180004526  call    cs:__imp_GetProcessHeap
0x18000452c  xor     edx, edx; dwFlags
0x18000452e  mov     r8d, 800h; dwBytes
0x180004534  mov     rcx, rax; hHeap
0x180004537  call    cs:__imp_HeapAlloc
0x18000453d  mov     rsi, rax
0x180004540  test    rax, rax
0x180004543  jnz     short loc_180004557
0x180004545  mov     eax, 8007000Eh
0x18000454a  mov     r9d, 0B9h
0x180004550  mov     ebx, eax
0x180004552  jmp     loc_1800044A2
0x180004557  mov     rdx, rsi; unsigned __int16 *
0x18000455a  mov     rcx, r14; unsigned __int16 *
0x18000455d  call    ?LoadMainText@@YAJPEBGPEAGK@Z; LoadMainText(ushort const *,ushort *,ulong)
0x180004562  mov     ebx, eax
0x180004564  test    eax, eax
0x180004566  jns     short loc_180004573
0x180004568  mov     r9d, 0BBh
0x18000456e  jmp     loc_1800045F9
0x180004573  lea     rax, [rsp+140h+var_100]
0x180004578  mov     [rbp+40h+pTaskConfig.pszContent], rsi
0x18000457c  mov     [rbp+40h+pTaskConfig.pButtons], rax
0x180004580  mov     [rbp+40h+pTaskConfig.cButtons], 2
0x180004587  call    cs:__imp_GetProcessHeap
0x18000458d  xor     edx, edx; dwFlags
0x18000458f  mov     r8d, 800h; dwBytes
0x180004595  mov     rcx, rax; hHeap
0x180004598  call    cs:__imp_HeapAlloc
0x18000459e  mov     rdi, rax
0x1800045a1  test    rax, rax
0x1800045a4  jnz     short loc_1800045B5
0x1800045a6  mov     eax, 8007000Eh
0x1800045ab  mov     r9d, 0C5h
0x1800045b1  mov     ebx, eax
0x1800045b3  jmp     short loc_1800045F9
0x1800045b5  mov     r9, rdi; unsigned __int16 *
0x1800045b8  mov     r8, r12; unsigned __int16 *
0x1800045bb  mov     rdx, r14; unsigned __int16 *
0x1800045be  mov     rcx, r13; unsigned __int16 *
0x1800045c1  call    ?LoadExpandedText@@YAJPEBG00PEAGK@Z; LoadExpandedText(ushort const *,ushort const *,ushort const *,ushort *,ulong)
0x1800045c6  mov     ebx, eax
0x1800045c8  test    eax, eax
0x1800045ca  jns     short loc_1800045D4
0x1800045cc  mov     r9d, 0C7h
0x1800045d2  jmp     short loc_1800045F9
0x1800045d4  lea     r9, [rbp+40h+pfVerificationFlagChecked]; pfVerificationFlagChecked
0x1800045d8  mov     [rbp+40h+pTaskConfig.pszExpandedInformation], rdi
0x1800045dc  xor     r8d, r8d; pnRadioButton
0x1800045df  lea     rcx, [rsp+140h+pTaskConfig]; pTaskConfig
0x1800045e4  mov     rdx, r15; pnButton
0x1800045e7  call    cs:__imp_TaskDialogIndirect
0x1800045ed  mov     ebx, eax
0x1800045ef  test    eax, eax
0x1800045f1  jns     short loc_180004612
0x1800045f3  mov     r9d, 0CBh
0x1800045f9  lea     r8, aShowreinstallu; "ShowReinstallUI"
0x180004600  mov     [rsp+140h+phico], eax
0x180004604  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x18000460b  xor     ecx, ecx; Level
0x18000460d  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180004612  call    cs:__imp_GetProcessHeap
0x180004618  mov     r8, rsi; lpMem
0x18000461b  xor     edx, edx; dwFlags
0x18000461d  mov     rcx, rax; hHeap
0x180004620  call    cs:__imp_HeapFree
0x180004626  test    rdi, rdi
0x180004629  jz      short loc_18000463F
0x18000462b  call    cs:__imp_GetProcessHeap
0x180004631  mov     r8, rdi; lpMem
0x180004634  xor     edx, edx; dwFlags
0x180004636  mov     rcx, rax; hHeap
0x180004639  call    cs:__imp_HeapFree
0x18000463f  mov     eax, ebx
0x180004641  add     rsp, 108h
0x180004648  pop     r15
0x18000464a  pop     r14
0x18000464c  pop     r13
0x18000464e  pop     r12
0x180004650  pop     rdi
0x180004651  pop     rsi
0x180004652  pop     rbx
0x180004653  pop     rbp
0x180004654  retn
```
