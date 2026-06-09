# BdeCfgpCopyBootFiles(ushort const *,ushort const *)

- ea: `0x1800086f8`
- end: `0x180008962`
- name: `?BdeCfgpCopyBootFiles@@YAJPEBG0@Z`
- size: `618`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180007bd0`

## callees

- `0x180008020`
- `0x1800080f0`
- `0x1800086f8`
- `0x180008968`
- `0x180008e1c`
- `0x180009000`
- `0x1800135c0`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x18000890e`
- `ADVAPI32!FreeSid` at `0x18000890e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800087df`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800087df`
- `KERNEL32!GetLastError` at `0x1800087e9`
- `KERNEL32!GetLastError` at `0x1800087e9`

## string_xrefs

- `0x180008765`: `SeRestorePrivilege`
- `0x18000877b`: `SeTakeOwnershipPrivilege`
- `0x180008791`: `SeSecurityPrivilege`

## pseudocode

```c
__int64 __fastcall BdeCfgpCopyBootFiles(unsigned __int16 *a1, const unsigned __int16 *a2)
{
  void *v3; // rdi
  WCHAR *v4; // rsi
  unsigned __int16 *v5; // r14
  signed int v6; // ebx
  signed int LastError; // eax
  unsigned int i; // r15d
  int v9; // eax
  void *v10; // r8
  int v11; // eax
  int v12; // eax
  void *lpMem; // [rsp+60h] [rbp-19h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-11h] BYREF
  PSID pSid; // [rsp+70h] [rbp-9h] BYREF
  unsigned __int16 *v17; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int16 *v18; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int16 *v19; // [rsp+88h] [rbp+Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+17h] BYREF

  v19 = a1;
  lpMem = 0;
  lpFileName = 0;
  v3 = 0;
  v18 = 0;
  v4 = 0;
  v17 = 0;
  v5 = 0;
  pSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( a1 && a2 )
  {
    v6 = BdeCfgpAcquireNamedPrivilege(L"SeRestorePrivilege");
    if ( v6 >= 0 )
    {
      v6 = BdeCfgpAcquireNamedPrivilege(L"SeTakeOwnershipPrivilege");
      if ( v6 >= 0 )
      {
        v6 = BdeCfgpAcquireNamedPrivilege(L"SeSecurityPrivilege");
        if ( v6 >= 0 )
        {
          if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
          {
            for ( i = 0; i < 3; ++i )
            {
              v6 = BdeCfgpBuildVolumePath(v19, (&off_180016160)[2 * i], (unsigned __int16 **)&lpMem);
              if ( v6 < 0 )
              {
                v3 = lpMem;
                goto LABEL_22;
              }
              v9 = BdeCfgpBuildVolumePath(a2, (&off_180016160)[2 * i], (unsigned __int16 **)&lpFileName);
              v4 = (WCHAR *)lpFileName;
              v6 = v9;
              v3 = lpMem;
              if ( v9 < 0 )
                goto LABEL_22;
              v11 = BdeCfgpCopyFile((unsigned __int16 *)lpMem, lpFileName, v10);
              v6 = v11;
              if ( v11 < 0 && (v11 != -2147024894 || *((_BYTE *)&off_180016160 + 16 * i + 8)) )
                goto LABEL_22;
              BdeCfgpFree(v3);
              v3 = 0;
              lpMem = 0;
              BdeCfgpFree(v4);
              lpFileName = 0;
              v4 = 0;
            }
            v6 = BdeCfgpBuildVolumePath(v19, L"\\Boot", &v18);
            if ( v6 >= 0 )
            {
              v12 = BdeCfgpBuildVolumePath(a2, L"\\Boot", &v17);
              v5 = v17;
              v6 = v12;
              if ( v12 >= 0 )
                v6 = BdeCfgpRecursiveCopy(v18, v17, pSid);
            }
          }
          else
          {
            LastError = GetLastError();
            v6 = LastError;
            if ( LastError > 0 )
              v6 = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
  }
  else
  {
    v6 = -2147467261;
  }
LABEL_22:
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  BdeCfgpFree(v3);
  BdeCfgpFree(v4);
  BdeCfgpFree(v18);
  BdeCfgpFree(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800086f8  mov     [rsp-8+arg_10], rbx
0x1800086fd  push    rbp
0x1800086fe  push    rsi
0x1800086ff  push    rdi
0x180008700  push    r12
0x180008702  push    r13
0x180008704  push    r14
0x180008706  push    r15
0x180008708  lea     rbp, [rsp-27h]
0x18000870d  sub     rsp, 0A0h
0x180008714  mov     rax, cs:__security_cookie
0x18000871b  xor     rax, rsp
0x18000871e  mov     [rbp+57h+var_38], rax
0x180008722  xor     r12d, r12d
0x180008725  mov     [rbp+57h+var_48], rcx
0x180008729  mov     [rbp+57h+lpMem], r12
0x18000872d  mov     r13, rdx
0x180008730  mov     [rbp+57h+lpFileName], r12
0x180008734  mov     edi, r12d
0x180008737  mov     [rbp+57h+var_50], r12
0x18000873b  mov     esi, r12d
0x18000873e  mov     [rbp+57h+var_58], r12
0x180008742  mov     r14d, r12d
0x180008745  mov     [rbp+57h+var_60], r12
0x180008749  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x18000874d  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180008753  test    rcx, rcx
0x180008756  jz      loc_180008900
0x18000875c  test    rdx, rdx
0x18000875f  jz      loc_180008900
0x180008765  lea     rcx, Name; "SeRestorePrivilege"
0x18000876c  call    ?BdeCfgpAcquireNamedPrivilege@@YAJPEAG@Z; BdeCfgpAcquireNamedPrivilege(ushort *)
0x180008771  mov     ebx, eax
0x180008773  test    eax, eax
0x180008775  js      loc_180008905
0x18000877b  lea     rcx, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x180008782  call    ?BdeCfgpAcquireNamedPrivilege@@YAJPEAG@Z; BdeCfgpAcquireNamedPrivilege(ushort *)
0x180008787  mov     ebx, eax
0x180008789  test    eax, eax
0x18000878b  js      loc_180008905
0x180008791  lea     rcx, aSesecuritypriv; "SeSecurityPrivilege"
0x180008798  call    ?BdeCfgpAcquireNamedPrivilege@@YAJPEAG@Z; BdeCfgpAcquireNamedPrivilege(ushort *)
0x18000879d  mov     ebx, eax
0x18000879f  test    eax, eax
0x1800087a1  js      loc_180008905
0x1800087a7  lea     rax, [rbp+57h+var_60]
0x1800087ab  mov     r9d, 220h; nSubAuthority1
0x1800087b1  mov     [rsp+0D0h+pSid], rax; pSid
0x1800087b6  lea     r8d, [r12+20h]; nSubAuthority0
0x1800087bb  mov     [rsp+0D0h+nSubAuthority7], r12d; nSubAuthority7
0x1800087c0  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800087c4  mov     [rsp+0D0h+nSubAuthority6], r12d; nSubAuthority6
0x1800087c9  mov     dl, 2; nSubAuthorityCount
0x1800087cb  mov     [rsp+0D0h+nSubAuthority5], r12d; nSubAuthority5
0x1800087d0  mov     [rsp+0D0h+nSubAuthority4], r12d; nSubAuthority4
0x1800087d5  mov     [rsp+0D0h+nSubAuthority3], r12d; nSubAuthority3
0x1800087da  mov     [rsp+0D0h+nSubAuthority2], r12d; nSubAuthority2
0x1800087df  call    cs:__imp_AllocateAndInitializeSid
0x1800087e5  test    eax, eax
0x1800087e7  jnz     short loc_180008807
0x1800087e9  call    cs:__imp_GetLastError
0x1800087ef  mov     ebx, eax
0x1800087f1  test    eax, eax
0x1800087f3  jle     loc_180008905
0x1800087f9  movzx   ebx, ax
0x1800087fc  or      ebx, 80070000h
0x180008802  jmp     loc_180008905
0x180008807  mov     r15d, r12d
0x18000880a  mov     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x18000880e  lea     rdi, off_180016160; "\\bootmgr"
0x180008815  mov     r12d, r15d
0x180008818  lea     r8, [rbp+57h+lpMem]; unsigned __int16 **
0x18000881c  add     r12, r12
0x18000881f  mov     rdx, [rdi+r12*8]; unsigned __int16 *
0x180008823  call    ?BdeCfgpBuildVolumePath@@YAJPEBG0PEAPEAG@Z; BdeCfgpBuildVolumePath(ushort const *,ushort const *,ushort * *)
0x180008828  mov     ebx, eax
0x18000882a  test    eax, eax
0x18000882c  js      loc_1800088F7
0x180008832  mov     rdx, [rdi+r12*8]; unsigned __int16 *
0x180008836  lea     r8, [rbp+57h+lpFileName]; unsigned __int16 **
0x18000883a  mov     rcx, r13; unsigned __int16 *
0x18000883d  call    ?BdeCfgpBuildVolumePath@@YAJPEBG0PEAPEAG@Z; BdeCfgpBuildVolumePath(ushort const *,ushort const *,ushort * *)
0x180008842  mov     rsi, [rbp+57h+lpFileName]
0x180008846  mov     ebx, eax
0x180008848  mov     rdi, [rbp+57h+lpMem]
0x18000884c  test    eax, eax
0x18000884e  js      loc_1800088FB
0x180008854  mov     rdx, rsi; lpFileName
0x180008857  mov     rcx, rdi; unsigned __int16 *
0x18000885a  call    ?BdeCfgpCopyFile@@YAJPEAG0PEAX@Z; BdeCfgpCopyFile(ushort *,ushort *,void *)
0x18000885f  mov     ebx, eax
0x180008861  test    eax, eax
0x180008863  jns     short loc_18000887E
0x180008865  cmp     eax, 80070002h
0x18000886a  jnz     loc_1800088FB
0x180008870  lea     rax, off_180016160; "\\bootmgr"
0x180008877  cmp     [rax+r12*8+8], r14b
0x18000887c  jnz     short loc_1800088FB
0x18000887e  mov     rcx, rdi; lpMem
0x180008881  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x180008886  xor     r12d, r12d
0x180008889  mov     rcx, rsi; lpMem
0x18000888c  mov     edi, r12d
0x18000888f  mov     [rbp+57h+lpMem], r12
0x180008893  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x180008898  inc     r15d
0x18000889b  mov     [rbp+57h+lpFileName], r12
0x18000889f  mov     esi, r12d
0x1800088a2  cmp     r15d, 3
0x1800088a6  jb      loc_18000880A
0x1800088ac  mov     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x1800088b0  lea     r8, [rbp+57h+var_50]; unsigned __int16 **
0x1800088b4  lea     rdx, aBoot; "\\Boot"
0x1800088bb  call    ?BdeCfgpBuildVolumePath@@YAJPEBG0PEAPEAG@Z; BdeCfgpBuildVolumePath(ushort const *,ushort const *,ushort * *)
0x1800088c0  mov     ebx, eax
0x1800088c2  test    eax, eax
0x1800088c4  js      short loc_180008905
0x1800088c6  lea     r8, [rbp+57h+var_58]; unsigned __int16 **
0x1800088ca  mov     rcx, r13; unsigned __int16 *
0x1800088cd  lea     rdx, aBoot; "\\Boot"
0x1800088d4  call    ?BdeCfgpBuildVolumePath@@YAJPEBG0PEAPEAG@Z; BdeCfgpBuildVolumePath(ushort const *,ushort const *,ushort * *)
0x1800088d9  mov     r14, [rbp+57h+var_58]
0x1800088dd  mov     ebx, eax
0x1800088df  test    eax, eax
0x1800088e1  js      short loc_180008905
0x1800088e3  mov     r8, [rbp+57h+var_60]; void *
0x1800088e7  mov     rdx, r14; unsigned __int16 *
0x1800088ea  mov     rcx, [rbp+57h+var_50]; unsigned __int16 *
0x1800088ee  call    ?BdeCfgpRecursiveCopy@@YAJPEAG0PEAX@Z; BdeCfgpRecursiveCopy(ushort *,ushort *,void *)
0x1800088f3  mov     ebx, eax
0x1800088f5  jmp     short loc_180008905
0x1800088f7  mov     rdi, [rbp+57h+lpMem]
0x1800088fb  xor     r12d, r12d
0x1800088fe  jmp     short loc_180008905
0x180008900  mov     ebx, 80004003h
0x180008905  mov     rcx, [rbp+57h+var_60]; pSid
0x180008909  test    rcx, rcx
0x18000890c  jz      short loc_180008918
0x18000890e  call    cs:__imp_FreeSid
0x180008914  mov     [rbp+57h+var_60], r12
0x180008918  mov     rcx, rdi; lpMem
0x18000891b  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x180008920  mov     rcx, rsi; lpMem
0x180008923  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x180008928  mov     rcx, [rbp+57h+var_50]; lpMem
0x18000892c  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x180008931  mov     rcx, r14; lpMem
0x180008934  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x180008939  mov     eax, ebx
0x18000893b  mov     rcx, [rbp+57h+var_38]
0x18000893f  xor     rcx, rsp; StackCookie
0x180008942  call    __security_check_cookie
0x180008947  mov     rbx, [rsp+0D0h+arg_10]
0x18000894f  add     rsp, 0A0h
0x180008956  pop     r15
0x180008958  pop     r14
0x18000895a  pop     r13
0x18000895c  pop     r12
0x18000895e  pop     rdi
0x18000895f  pop     rsi
0x180008960  pop     rbp
0x180008961  retn
```
