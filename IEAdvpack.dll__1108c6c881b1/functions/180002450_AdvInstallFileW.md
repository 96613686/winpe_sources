# AdvInstallFileW

- ea: `0x180002450`
- end: `0x180002793`
- name: `AdvInstallFileW`
- size: `835`
- prototype: `HRESULT __stdcall(HWND hwnd, LPCWSTR lpszSourceDir, LPCWSTR lpszSourceFile, LPCWSTR lpszDestDir, LPCWSTR lpszDestFile, DWORD dwFlags, DWORD dwReserved)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002360`

## callees

- `0x180001dbc`
- `0x1800022bc`
- `0x180002450`
- `0x180003ce0`
- `0x180003e20`
- `0x1800045e8`
- `0x1800080c8`
- `0x1800080f0`
- `0x180008a6c`
- `0x180008f2c`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002585`
- `KERNEL32!GetLastError` at `0x1800026da`
- `KERNEL32!GetLastError` at `0x180002710`
- `KERNEL32!GetLastError` at `0x180002585`
- `KERNEL32!GetLastError` at `0x1800026da`
- `KERNEL32!GetLastError` at `0x180002710`
- `SETUPAPI!SetupCloseFileQueue` at `0x18000273e`
- `SETUPAPI!SetupCloseFileQueue` at `0x18000273e`
- `SETUPAPI!SetupCommitFileQueueW` at `0x1800026d0`
- `SETUPAPI!SetupCommitFileQueueW` at `0x1800026d0`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180002708`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180002708`
- `SETUPAPI!SetupQueueCopyW` at `0x180002688`
- `SETUPAPI!SetupQueueCopyW` at `0x180002688`
- `SETUPAPI!SetupOpenFileQueue` at `0x180002553`
- `SETUPAPI!SetupOpenFileQueue` at `0x180002553`
- `SETUPAPI!SetupInitDefaultQueueCallbackEx` at `0x1800026a4`
- `SETUPAPI!SetupInitDefaultQueueCallbackEx` at `0x1800026a4`

## string_xrefs

- `0x18000252b`: `SETUPAPI.DLL`
- `0x180002567`: `SetupOpenFileQueue`

## pseudocode

```c
HRESULT __stdcall AdvInstallFileW(
        HWND hwnd,
        LPCWSTR lpszSourceDir,
        LPCWSTR lpszSourceFile,
        LPCWSTR lpszDestDir,
        LPCWSTR lpszDestFile,
        DWORD dwFlags,
        DWORD dwReserved)
{
  unsigned __int64 v11; // rax
  int v13; // r12d
  const unsigned __int16 *v14; // rcx
  HRESULT LastError; // ebx
  HSPFILEQ v16; // rdi
  __int64 v17; // r8
  const WCHAR *v18; // r8
  DWORD v19; // ecx
  unsigned int v20; // edx
  int v21; // ecx
  int v22; // edx
  int v23; // ecx
  int v24; // edx
  DWORD CopyStyle; // ecx
  PVOID inited; // rax
  UINT (__stdcall *v27)(PVOID, UINT, UINT_PTR, UINT_PTR); // r8
  void *v28; // rbp
  WCHAR SourceRootPath[264]; // [rsp+50h] [rbp-268h] BYREF

  if ( !lpszSourceDir )
    return -2147024809;
  if ( !*lpszSourceDir )
    return -2147024809;
  if ( !lpszSourceFile )
    return -2147024809;
  if ( !*lpszSourceFile )
    return -2147024809;
  v11 = -1;
  do
    ++v11;
  while ( lpszSourceDir[v11] );
  if ( v11 < 3 || !lpszDestDir )
    return -2147024809;
  if ( !(unsigned int)SaveGlobalContext() )
    return -2147467259;
  hWnd = hwnd;
  if ( (unsigned int)CheckOSVersion() )
  {
    v13 = InternalNeedRebootInit((const unsigned __int16 *)ctx);
    hLibModule = MyLoadLibrary(v14);
    if ( hLibModule )
    {
      v16 = SetupOpenFileQueue();
      if ( v16 == (HSPFILEQ)-1LL )
      {
        MsgBox2Param(0, 0x455u, L"SetupOpenFileQueue", 0, 0x10u, 0);
        LastError = GetLastError();
        if ( (LastError & 0xE0000000) == 0xE0000000 )
        {
          LastError = (unsigned __int16)LastError | 0x800F0000;
        }
        else if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
        StringCchCopyW(SourceRootPath, 0x104u, (size_t *)lpszSourceDir);
        MakeRootDir(SourceRootPath);
        v17 = -1;
        do
          ++v17;
        while ( SourceRootPath[v17] );
        v18 = &lpszSourceDir[v17];
        v19 = ((dwFlags & 8) << 6) | 0x160;
        if ( (dwFlags & 4) == 0 )
          v19 = ((dwFlags & 8) << 6) | 0x164;
        v20 = v19 & 0xFFFFFFDF;
        if ( (dwFlags & 0x10000000) == 0 )
          v20 = v19;
        v21 = v20 | 0x2000;
        if ( (dwFlags & 0x20) == 0 )
          v21 = v20;
        v22 = v21 | 2;
        if ( (dwFlags & 0x400) == 0 )
          v22 = v21;
        v23 = v22 | 8;
        if ( (dwFlags & 0x10) == 0 )
          v23 = v22;
        v24 = v23 | 0x400;
        if ( (dwFlags & 2) == 0 )
          v24 = v23;
        CopyStyle = v24 | 0x4000;
        if ( (dwFlags & 1) == 0 )
          CopyStyle = v24;
        if ( SetupQueueCopyW(v16, SourceRootPath, v18, lpszSourceFile, 0, 0, lpszDestDir, lpszDestFile, CopyStyle) )
        {
          inited = SetupInitDefaultQueueCallbackEx(hwnd, HWND_MESSAGE|0x2LL, 0, 0, 0);
          v27 = (UINT (__stdcall *)(PVOID, UINT, UINT_PTR, UINT_PTR))AIFQuietSetupQueueCallback;
          v28 = inited;
          if ( (dwFlags & 0x20000000) == 0 )
            v27 = AIFSetupQueueCallback;
          LastError = 0;
          if ( !SetupCommitFileQueueW(hwnd, v16, v27, inited) )
          {
            LastError = GetLastError();
            if ( (LastError & 0xE0000000) == 0xE0000000 )
            {
              LastError = (unsigned __int16)LastError | 0x800F0000;
            }
            else if ( LastError > 0 )
            {
              LastError = (unsigned __int16)LastError | 0x80070000;
            }
          }
          SetupTermDefaultQueueCallback(v28);
        }
        else
        {
          LastError = GetLastError();
          if ( (LastError & 0xE0000000) == 0xE0000000 )
          {
            LastError = (unsigned __int16)LastError | 0x800F0000;
          }
          else if ( LastError > 0 )
          {
            LastError = (unsigned __int16)LastError | 0x80070000;
          }
        }
        SetupCloseFileQueue(v16);
        if ( LastError >= 0 && InternalNeedReboot(v13, ctx) )
          LastError = 3010;
      }
    }
    else
    {
      MsgBox2Param(0, 0x455u, L"SETUPAPI.DLL", 0, 0x10u, 0);
      LastError = -2147023739;
    }
    RestoreGlobalContext();
    return LastError;
  }
  else
  {
    RestoreGlobalContext();
    return -2147023746;
  }
}

```

## disassembly

```asm
0x180002450  push    rbx
0x180002452  push    rbp
0x180002453  push    rsi
0x180002454  push    rdi
0x180002455  push    r12
0x180002457  push    r13
0x180002459  push    r14
0x18000245b  push    r15
0x18000245d  sub     rsp, 278h
0x180002464  mov     rax, cs:__security_cookie
0x18000246b  xor     rax, rsp
0x18000246e  mov     [rsp+2B8h+var_58], rax
0x180002476  mov     r13, [rsp+2B8h+lpszDestFile]
0x18000247e  xor     r15d, r15d
0x180002481  mov     r14, r9
0x180002484  mov     rbp, r8
0x180002487  mov     rbx, rdx
0x18000248a  mov     rsi, rcx
0x18000248d  test    rdx, rdx
0x180002490  jz      loc_18000276A
0x180002496  cmp     [rdx], r15w
0x18000249a  jz      loc_18000276A
0x1800024a0  test    r8, r8
0x1800024a3  jz      loc_18000276A
0x1800024a9  cmp     [r8], r15w
0x1800024ad  jz      loc_18000276A
0x1800024b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800024b7  inc     rax
0x1800024ba  cmp     [rdx+rax*2], r15w
0x1800024bf  jnz     short loc_1800024B7
0x1800024c1  cmp     rax, 3
0x1800024c5  jb      loc_18000276A
0x1800024cb  test    r14, r14
0x1800024ce  jz      loc_18000276A
0x1800024d4  call    ?SaveGlobalContext@@YAHXZ; SaveGlobalContext(void)
0x1800024d9  test    eax, eax
0x1800024db  jnz     short loc_1800024E7
0x1800024dd  mov     eax, 80004005h
0x1800024e2  jmp     loc_18000276F
0x1800024e7  mov     cs:hWnd, rsi
0x1800024ee  call    ?CheckOSVersion@@YAHXZ; CheckOSVersion(void)
0x1800024f3  test    eax, eax
0x1800024f5  jnz     short loc_180002506
0x1800024f7  call    ?RestoreGlobalContext@@YAHXZ; RestoreGlobalContext(void)
0x1800024fc  mov     eax, 8007047Eh
0x180002501  jmp     loc_18000276F
0x180002506  movzx   ecx, cs:?ctx@@3UADVCONTEXTW@@A; unsigned __int16
0x18000250d  call    ?InternalNeedRebootInit@@YAKG@Z; InternalNeedRebootInit(ushort)
0x180002512  mov     r12d, eax
0x180002515  call    ?MyLoadLibrary@@YAPEAUHINSTANCE__@@PEBG@Z; MyLoadLibrary(ushort const *)
0x18000251a  mov     cs:hLibModule, rax
0x180002521  test    rax, rax
0x180002524  jnz     short loc_180002553
0x180002526  mov     dword ptr [rsp+2B8h+SourceTagfile], r15d; unsigned int
0x18000252b  lea     r8, FileName; "SETUPAPI.DLL"
0x180002532  xor     r9d, r9d; unsigned __int16 *
0x180002535  mov     dword ptr [rsp+2B8h+SourceDescription], 10h; unsigned int
0x18000253d  mov     edx, 455h; uID
0x180002542  xor     ecx, ecx; hWnd
0x180002544  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180002549  mov     ebx, 80070485h
0x18000254e  jmp     loc_180002761
0x180002553  call    cs:__imp_SetupOpenFileQueue
0x180002559  mov     rdi, rax
0x18000255c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002560  jnz     short loc_1800025BC
0x180002562  mov     dword ptr [rsp+2B8h+SourceTagfile], r15d; unsigned int
0x180002567  lea     r8, aSetupopenfileq; "SetupOpenFileQueue"
0x18000256e  xor     r9d, r9d; unsigned __int16 *
0x180002571  mov     dword ptr [rsp+2B8h+SourceDescription], 10h; unsigned int
0x180002579  mov     edx, 455h; uID
0x18000257e  xor     ecx, ecx; hWnd
0x180002580  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180002585  call    cs:__imp_GetLastError
0x18000258b  mov     ecx, 0E0000000h
0x180002590  mov     ebx, eax
0x180002592  and     eax, ecx
0x180002594  cmp     eax, ecx
0x180002596  jnz     short loc_1800025A6
0x180002598  movzx   ebx, bx
0x18000259b  or      ebx, 800F0000h
0x1800025a1  jmp     loc_180002761
0x1800025a6  test    ebx, ebx
0x1800025a8  jle     loc_180002761
0x1800025ae  movzx   ebx, bx
0x1800025b1  or      ebx, 80070000h
0x1800025b7  jmp     loc_180002761
0x1800025bc  mov     r8, rbx; unsigned __int16 *
0x1800025bf  lea     rcx, [rsp+2B8h+SourceRootPath]; unsigned __int16 *
0x1800025c4  mov     edx, 104h; unsigned __int64
0x1800025c9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800025ce  lea     rcx, [rsp+2B8h+SourceRootPath]; unsigned __int16 *
0x1800025d3  call    ?MakeRootDir@@YAXPEAG@Z; MakeRootDir(ushort *)
0x1800025d8  lea     rax, [rsp+2B8h+SourceRootPath]
0x1800025dd  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800025e1  inc     r8
0x1800025e4  cmp     [rax+r8*2], r15w
0x1800025e9  jnz     short loc_1800025E1
0x1800025eb  mov     r15d, [rsp+2B8h+dwFlags]
0x1800025f3  lea     r8, [rbx+r8*2]; SourcePath
0x1800025f7  mov     edx, r15d
0x1800025fa  mov     r9d, 400h
0x180002600  and     edx, 8
0x180002603  shl     edx, 6
0x180002606  or      edx, 164h
0x18000260c  mov     ecx, edx
0x18000260e  and     ecx, 0FFFFFFFBh
0x180002611  test    r15b, 4
0x180002615  cmovz   ecx, edx
0x180002618  mov     edx, ecx
0x18000261a  and     edx, 0FFFFFFDFh
0x18000261d  bt      r15d, 1Ch
0x180002622  cmovnb  edx, ecx
0x180002625  mov     ecx, edx
0x180002627  bts     ecx, 0Dh
0x18000262b  test    r15b, 20h
0x18000262f  cmovz   ecx, edx
0x180002632  mov     edx, ecx
0x180002634  or      edx, 2
0x180002637  test    r9d, r15d
0x18000263a  cmovz   edx, ecx
0x18000263d  mov     ecx, edx
0x18000263f  or      ecx, 8
0x180002642  test    r15b, 10h
0x180002646  cmovz   ecx, edx
0x180002649  mov     edx, ecx
0x18000264b  or      edx, r9d
0x18000264e  mov     r9, rbp; SourceFilename
0x180002651  test    r15b, 2
0x180002655  cmovz   edx, ecx
0x180002658  mov     ecx, edx
0x18000265a  bts     ecx, 0Eh
0x18000265e  test    r15b, 1
0x180002662  cmovz   ecx, edx
0x180002665  lea     rdx, [rsp+2B8h+SourceRootPath]; SourceRootPath
0x18000266a  mov     [rsp+2B8h+CopyStyle], ecx; CopyStyle
0x18000266e  mov     rcx, rdi; QueueHandle
0x180002671  mov     [rsp+2B8h+TargetFilename], r13; TargetFilename
0x180002676  mov     [rsp+2B8h+TargetDirectory], r14; TargetDirectory
0x18000267b  xor     r14d, r14d
0x18000267e  mov     [rsp+2B8h+SourceTagfile], r14; SourceTagfile
0x180002683  mov     [rsp+2B8h+SourceDescription], r14; SourceDescription
0x180002688  call    cs:__imp_SetupQueueCopyW
0x18000268e  test    eax, eax
0x180002690  jz      short loc_180002710
0x180002692  xor     r9d, r9d; Reserved1
0x180002695  mov     [rsp+2B8h+SourceDescription], r14; Reserved2
0x18000269a  xor     r8d, r8d; ProgressMessage
0x18000269d  or      rdx, 0FFFFFFFFFFFFFFFFh; AlternateProgressWindow
0x1800026a1  mov     rcx, rsi; OwnerWindow
0x1800026a4  call    cs:__imp_SetupInitDefaultQueueCallbackEx
0x1800026aa  bt      r15d, 1Dh
0x1800026af  lea     r8, ?AIFQuietSetupQueueCallback@@YAIPEAXI_K1@Z; AIFQuietSetupQueueCallback(void *,uint,unsigned __int64,unsigned __int64)
0x1800026b6  mov     rbp, rax
0x1800026b9  mov     rdx, rdi; QueueHandle
0x1800026bc  lea     rax, ?AIFSetupQueueCallback@@YAIPEAXI_K1@Z; AIFSetupQueueCallback(void *,uint,unsigned __int64,unsigned __int64)
0x1800026c3  mov     r9, rbp; Context
0x1800026c6  cmovnb  r8, rax; MsgHandler
0x1800026ca  mov     rcx, rsi; Owner
0x1800026cd  mov     ebx, r14d
0x1800026d0  call    cs:__imp_SetupCommitFileQueueW
0x1800026d6  test    eax, eax
0x1800026d8  jnz     short loc_180002705
0x1800026da  call    cs:__imp_GetLastError
0x1800026e0  mov     ecx, 0E0000000h
0x1800026e5  mov     ebx, eax
0x1800026e7  and     eax, ecx
0x1800026e9  cmp     eax, ecx
0x1800026eb  jnz     short loc_1800026F8
0x1800026ed  movzx   ebx, bx
0x1800026f0  or      ebx, 800F0000h
0x1800026f6  jmp     short loc_180002705
0x1800026f8  test    ebx, ebx
0x1800026fa  jle     short loc_180002705
0x1800026fc  movzx   ebx, bx
0x1800026ff  or      ebx, 80070000h
0x180002705  mov     rcx, rbp; Context
0x180002708  call    cs:__imp_SetupTermDefaultQueueCallback
0x18000270e  jmp     short loc_18000273B
0x180002710  call    cs:__imp_GetLastError
0x180002716  mov     ecx, 0E0000000h
0x18000271b  mov     ebx, eax
0x18000271d  and     eax, ecx
0x18000271f  cmp     eax, ecx
0x180002721  jnz     short loc_18000272E
0x180002723  movzx   ebx, bx
0x180002726  or      ebx, 800F0000h
0x18000272c  jmp     short loc_18000273B
0x18000272e  test    ebx, ebx
0x180002730  jle     short loc_18000273B
0x180002732  movzx   ebx, bx
0x180002735  or      ebx, 80070000h
0x18000273b  mov     rcx, rdi; QueueHandle
0x18000273e  call    cs:__imp_SetupCloseFileQueue
0x180002744  test    ebx, ebx
0x180002746  js      short loc_180002761
0x180002748  movzx   edx, cs:?ctx@@3UADVCONTEXTW@@A; unsigned __int16
0x18000274f  mov     ecx, r12d; unsigned int
0x180002752  call    ?InternalNeedReboot@@YAHKG@Z; InternalNeedReboot(ulong,ushort)
0x180002757  test    eax, eax
0x180002759  mov     ecx, 0BC2h
0x18000275e  cmovnz  ebx, ecx
0x180002761  call    ?RestoreGlobalContext@@YAHXZ; RestoreGlobalContext(void)
0x180002766  mov     eax, ebx
0x180002768  jmp     short loc_18000276F
0x18000276a  mov     eax, 80070057h
0x18000276f  mov     rcx, [rsp+2B8h+var_58]
0x180002777  xor     rcx, rsp; StackCookie
0x18000277a  call    __security_check_cookie
0x18000277f  add     rsp, 278h
0x180002786  pop     r15
0x180002788  pop     r14
0x18000278a  pop     r13
0x18000278c  pop     r12
0x18000278e  pop     rdi
0x18000278f  pop     rsi
0x180002790  pop     rbp
0x180002791  pop     rbx
0x180002792  retn
```
