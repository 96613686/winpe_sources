# CActiveXInstallBroker::RegisterExeFile(ushort *,ushort *,int,_PROCESS_INFORMATION *)

- ea: `0x404214`
- end: `0x404452`
- name: `?RegisterExeFile@CActiveXInstallBroker@@QAGJPAG0HPAU_PROCESS_INFORMATION@@@Z`
- size: `574`
- prototype: `int __userpurge@<eax>(const unsigned __int16 *@<edx>, int@<ecx>, CActiveXInstallBroker *this, unsigned __int16 *, unsigned __int16 *, int, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x405df0`

## callees

- `0x402625`
- `0x402dc4`
- `0x402eb9`
- `0x402ed3`
- `0x403094`
- `0x4030f5`
- `0x404214`
- `0x408301`
- `0x40838e`
- `0x408480`
- `0x408a2f`
- `0x409c72`
- `0x40cb60`
- `0x40eb27`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x40441b`
- `KERNEL32!CloseHandle` at `0x40442c`
- `KERNEL32!CloseHandle` at `0x40441b`
- `KERNEL32!CloseHandle` at `0x40442c`
- `KERNEL32!CreateProcessW` at `0x4043cf`
- `KERNEL32!CreateProcessW` at `0x4043cf`
- `KERNEL32!GetLastError` at `0x4043d9`
- `KERNEL32!GetLastError` at `0x4043d9`

## pseudocode

```c
int __userpurge CActiveXInstallBroker::RegisterExeFile@<eax>(
        const unsigned __int16 *a1@<edx>,
        int a2@<ecx>,
        CActiveXInstallBroker *this,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6,
        struct _PROCESS_INFORMATION *a7)
{
  int IsAuthorized; // esi
  int v10; // eax
  int v11; // ecx
  signed int LastError; // eax
  unsigned int v14; // [esp+0h] [ebp-490h]
  const unsigned __int16 *v15; // [esp+0h] [ebp-490h]
  unsigned int v16; // [esp+0h] [ebp-490h]
  unsigned int v17; // [esp+0h] [ebp-490h]
  const unsigned __int16 *v18; // [esp+4h] [ebp-48Ch]
  unsigned __int16 *v19; // [esp+4h] [ebp-48Ch]
  const unsigned __int16 *v20; // [esp+4h] [ebp-48Ch]
  _PROCESS_INFORMATION ProcessInformation; // [esp+18h] [ebp-478h] BYREF
  _STARTUPINFOW StartupInfo; // [esp+28h] [ebp-468h] BYREF
  unsigned __int16 v23[260]; // [esp+70h] [ebp-420h] BYREF
  WCHAR CommandLine[266]; // [esp+278h] [ebp-218h] BYREF

  memset(CommandLine, 0, 528);
  memset(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CLock::Lock((CLock *)a2) )
  {
    IsAuthorized = -2147024882;
    goto LABEL_28;
  }
  if ( *(int *)(a2 + 28) < 6 )
  {
    IsAuthorized = -2147019873;
    goto LABEL_28;
  }
  if ( !a1 || !this || !a5 )
    goto LABEL_27;
  v10 = wcscmp(a1, *(const unsigned __int16 **)(a2 + 36));
  if ( v10 )
    v10 = v10 < 0 ? -1 : 1;
  if ( v10 )
    goto LABEL_11;
  if ( StringCchCopyW((size_t)this, v14, v18) >= 0
    && (AxiAdjustSlashToBackslashW((__int16 *)v23), AxiPreScanPathW(v23) >= 0)
    && VerifyFileHasExtensionW(v15) >= 0 )
  {
    IsAuthorized = CActiveXInstallBroker::FileIsAuthorized((CActiveXInstallBroker *)a2, v23, v11);
    if ( IsAuthorized >= 0 )
    {
      if ( !*(_DWORD *)(a2 + 84) && !ContainingPathIsTamperProof(v23) )
      {
LABEL_11:
        IsAuthorized = -2147024891;
        goto LABEL_28;
      }
      IsAuthorized = QuotePath(264, v23, CommandLine, v16, v19);
      if ( IsAuthorized >= 0 )
      {
        if ( !a4 || (IsAuthorized = StringCchCatW(L" /RegServer", v17, v20), IsAuthorized >= 0) )
        {
          StartupInfo.cb = 68;
          if ( CreateProcessW(0, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
          {
            IsAuthorized = CActiveXInstallBroker::DuplicateProcessInformation(
                             (CActiveXInstallBroker *)a2,
                             &ProcessInformation,
                             (struct _PROCESS_INFORMATION *)a5);
            if ( IsAuthorized >= 0 )
              *(_DWORD *)(a2 + 28) = 8;
          }
          else
          {
            LastError = GetLastError();
            IsAuthorized = (unsigned __int16)LastError | 0x80070000;
            if ( LastError <= 0 )
              IsAuthorized = LastError;
          }
        }
      }
    }
  }
  else
  {
LABEL_27:
    IsAuthorized = -2147024809;
  }
LABEL_28:
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  CLock::Unlock((CLock *)a2);
  return IsAuthorized;
}

```

## disassembly

```asm
0x404214  mov     edi, edi
0x404216  push    ebp
0x404217  mov     ebp, esp
0x404219  and     esp, 0FFFFFFF8h
0x40421c  sub     esp, 484h
0x404222  mov     eax, ___security_cookie
0x404227  xor     eax, esp
0x404229  mov     [esp+484h+var_4], eax
0x404230  mov     eax, [ebp+this]
0x404233  push    ebx
0x404234  push    esi; unsigned __int16 *
0x404235  mov     [esp+48Ch+cchDest], eax
0x404239  mov     esi, edx
0x40423b  mov     eax, [ebp+arg_8]
0x40423e  mov     ebx, ecx
0x404240  push    edi; unsigned int
0x404241  mov     [esp+490h+var_47C], eax
0x404245  xor     eax, eax
0x404247  push    20Eh; Size
0x40424c  push    eax; Val
0x40424d  mov     [esp+498h+CommandLine], ax
0x404255  lea     eax, [esp+498h+var_216]
0x40425c  push    eax; void *
0x40425d  call    _memset
0x404262  push    44h ; 'D'; Size
0x404264  lea     eax, [esp+4A0h+StartupInfo]
0x404268  push    0; Val
0x40426a  push    eax; void *
0x40426b  call    _memset
0x404270  xor     eax, eax
0x404272  lea     edi, [esp+4A8h+ProcessInformation]
0x404276  stosd
0x404277  add     esp, 18h
0x40427a  mov     ecx, ebx; this
0x40427c  stosd
0x40427d  stosd
0x40427e  stosd
0x40427f  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x404284  test    eax, eax
0x404286  jnz     short loc_404292
0x404288  mov     esi, 8007000Eh
0x40428d  jmp     loc_404410
0x404292  cmp     dword ptr [ebx+1Ch], 6
0x404296  jge     short loc_4042A2
0x404298  mov     esi, 8007139Fh
0x40429d  jmp     loc_404410
0x4042a2  test    esi, esi
0x4042a4  jz      loc_40440B
0x4042aa  mov     edx, [esp+490h+cchDest]
0x4042ae  test    edx, edx
0x4042b0  jz      loc_40440B
0x4042b6  mov     edi, [esp+490h+var_47C]
0x4042ba  test    edi, edi
0x4042bc  jz      loc_40440B
0x4042c2  mov     eax, [ebx+24h]
0x4042c5  mov     cx, [esi]
0x4042c8  cmp     cx, [eax]
0x4042cb  jnz     short loc_4042EB
0x4042cd  test    cx, cx
0x4042d0  jz      short loc_4042E7
0x4042d2  mov     cx, [esi+2]
0x4042d6  cmp     cx, [eax+2]
0x4042da  jnz     short loc_4042EB
0x4042dc  add     esi, 4
0x4042df  add     eax, 4
0x4042e2  test    cx, cx
0x4042e5  jnz     short loc_4042C5
0x4042e7  xor     eax, eax
0x4042e9  jmp     short loc_4042F0
0x4042eb  sbb     eax, eax
0x4042ed  or      eax, 1
0x4042f0  test    eax, eax
0x4042f2  jz      short loc_4042FE
0x4042f4  mov     esi, 80070005h
0x4042f9  jmp     loc_404410
0x4042fe  push    edx; cchDest
0x4042ff  mov     edx, 104h
0x404304  lea     ecx, [esp+494h+var_420]
0x404308  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x40430d  test    eax, eax
0x40430f  js      loc_40440B
0x404315  lea     ecx, [esp+490h+var_420]
0x404319  call    ?AxiAdjustSlashToBackslashW@@YGXPAG@Z; AxiAdjustSlashToBackslashW(ushort *)
0x40431e  lea     ecx, [esp+490h+var_420]
0x404322  call    ?AxiPreScanPathW@@YGJPBG@Z; AxiPreScanPathW(ushort const *)
0x404327  test    eax, eax
0x404329  js      loc_40440B
0x40432f  lea     ecx, [esp+490h+var_420]
0x404333  call    ?VerifyFileHasExtensionW@@YGJPBG@Z; VerifyFileHasExtensionW(ushort const *)
0x404338  test    eax, eax
0x40433a  js      loc_40440B
0x404340  push    ecx; int
0x404341  lea     eax, [esp+494h+var_420]
0x404345  mov     ecx, ebx; this
0x404347  push    eax; unsigned __int16 *
0x404348  call    ?FileIsAuthorized@CActiveXInstallBroker@@AAEJPBGH@Z; CActiveXInstallBroker::FileIsAuthorized(ushort const *,int)
0x40434d  mov     esi, eax
0x40434f  test    esi, esi
0x404351  js      loc_404410
0x404357  cmp     dword ptr [ebx+54h], 0
0x40435b  jnz     short loc_40436A
0x40435d  lea     ecx, [esp+490h+var_420]
0x404361  call    ?ContainingPathIsTamperProof@@YGHPBG@Z; ContainingPathIsTamperProof(ushort const *)
0x404366  test    eax, eax
0x404368  jz      short loc_4042F4
0x40436a  lea     eax, [esp+490h+CommandLine]
0x404371  mov     edx, 108h
0x404376  push    eax; unsigned __int16 *
0x404377  lea     ecx, [esp+494h+var_420]
0x40437b  call    ?QuotePath@@YGJPBGKPAG@Z; QuotePath(ushort const *,ulong,ushort *)
0x404380  mov     esi, eax
0x404382  test    esi, esi
0x404384  js      loc_404410
0x40438a  cmp     [ebp+arg_4], 0
0x40438e  jz      short loc_4043AC
0x404390  push    offset aRegserver_0; " /RegServer"
0x404395  mov     edx, 108h
0x40439a  lea     ecx, [esp+494h+CommandLine]
0x4043a1  call    ?StringCchCatW@@YGJPAGIPBG@Z; StringCchCatW(ushort *,uint,ushort const *)
0x4043a6  mov     esi, eax
0x4043a8  test    esi, esi
0x4043aa  js      short loc_404410
0x4043ac  xor     ecx, ecx
0x4043ae  mov     [esp+490h+StartupInfo.cb], 44h ; 'D'
0x4043b6  lea     eax, [esp+490h+ProcessInformation]
0x4043ba  push    eax; lpProcessInformation
0x4043bb  lea     eax, [esp+494h+StartupInfo]
0x4043bf  push    eax; lpStartupInfo
0x4043c0  push    ecx; lpCurrentDirectory
0x4043c1  push    ecx; lpEnvironment
0x4043c2  push    ecx; dwCreationFlags
0x4043c3  push    ecx; bInheritHandles
0x4043c4  push    ecx; lpThreadAttributes
0x4043c5  push    ecx; lpProcessAttributes
0x4043c6  lea     eax, [esp+4B0h+CommandLine]
0x4043cd  push    eax; lpCommandLine
0x4043ce  push    ecx; lpApplicationName
0x4043cf  call    ds:__imp__CreateProcessW@40; CreateProcessW(x,x,x,x,x,x,x,x,x,x)
0x4043d5  test    eax, eax
0x4043d7  jnz     short loc_4043EF
0x4043d9  call    ds:__imp__GetLastError@0; GetLastError()
0x4043df  movzx   esi, ax
0x4043e2  or      esi, 80070000h
0x4043e8  test    eax, eax
0x4043ea  cmovle  esi, eax
0x4043ed  jmp     short loc_404410
0x4043ef  push    edi; struct _PROCESS_INFORMATION *
0x4043f0  lea     eax, [esp+494h+ProcessInformation]
0x4043f4  mov     ecx, ebx; this
0x4043f6  push    eax; struct _PROCESS_INFORMATION *
0x4043f7  call    ?DuplicateProcessInformation@CActiveXInstallBroker@@AAEJPAU_PROCESS_INFORMATION@@0@Z; CActiveXInstallBroker::DuplicateProcessInformation(_PROCESS_INFORMATION *,_PROCESS_INFORMATION *)
0x4043fc  mov     esi, eax
0x4043fe  test    esi, esi
0x404400  js      short loc_404410
0x404402  mov     dword ptr [ebx+1Ch], 8
0x404409  jmp     short loc_404410
0x40440b  mov     esi, 80070057h
0x404410  cmp     [esp+490h+ProcessInformation.hThread], 0
0x404415  jz      short loc_404421
0x404417  push    [esp+490h+ProcessInformation.hThread]; hObject
0x40441b  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x404421  cmp     [esp+490h+ProcessInformation.hProcess], 0
0x404426  jz      short loc_404432
0x404428  push    [esp+490h+ProcessInformation.hProcess]; hObject
0x40442c  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x404432  mov     ecx, ebx; this
0x404434  call    ?Unlock@CLock@@QAEHXZ; CLock::Unlock(void)
0x404439  mov     ecx, [esp+490h+var_4]
0x404440  mov     eax, esi
0x404442  pop     edi
0x404443  pop     esi
0x404444  pop     ebx
0x404445  xor     ecx, esp; StackCookie
0x404447  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40444c  mov     esp, ebp
0x40444e  pop     ebp
0x40444f  retn    0Ch
```
