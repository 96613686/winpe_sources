# CreateWmsNamedEvent(ulong,ushort const *,void * *)

- ea: `0x140006e24`
- end: `0x140007150`
- name: `?CreateWmsNamedEvent@@YAJKPEBGPEAPEAX@Z`
- size: `812`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400029e8`

## callees

- `0x1400011d4`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x140006a88`
- `0x140006e24`
- `0x14000a4f4`
- `0x14000ae60`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x1400070a0`
- `KERNEL32!OpenEventW` at `0x1400070a0`
- `KERNEL32!IsDebuggerPresent` at `0x140006f6a`
- `KERNEL32!IsDebuggerPresent` at `0x140007058`
- `KERNEL32!IsDebuggerPresent` at `0x140007106`
- `KERNEL32!IsDebuggerPresent` at `0x140006f6a`
- `KERNEL32!IsDebuggerPresent` at `0x140007058`
- `KERNEL32!IsDebuggerPresent` at `0x140007106`
- `KERNEL32!GetLastError` at `0x140006ffc`
- `KERNEL32!GetLastError` at `0x1400070ab`
- `KERNEL32!GetLastError` at `0x140006ffc`
- `KERNEL32!GetLastError` at `0x1400070ab`
- `KERNEL32!CreateEventW` at `0x140006fed`
- `KERNEL32!CreateEventW` at `0x140006fed`

## string_xrefs

- `0x140006f46`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140007040`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400070db`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140006f39`: `CreateWmsNamedEvent`
- `0x140007033`: `CreateWmsNamedEvent`
- `0x1400070ce`: `CreateWmsNamedEvent`
- `0x1400070e8`: `hWmsSvcReadyEvent != 0`
- `0x14000710e`: `hWmsSvcReadyEvent != 0`

## pseudocode

```c
__int64 __fastcall CreateWmsNamedEvent(const unsigned __int16 *a1, const unsigned __int16 *a2, void **a3)
{
  signed int DoesUserExist; // ebx
  unsigned __int64 v6; // rax
  int v7; // eax
  HANDLE v8; // rax
  signed int LastError; // eax
  unsigned int v10; // r13d
  bool v11; // zf
  const unsigned __int16 *v12; // rax
  signed int v13; // eax
  void **v15; // [rsp+30h] [rbp-A9h]
  int v16; // [rsp+40h] [rbp-99h] BYREF
  void *Block; // [rsp+48h] [rbp-91h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+50h] [rbp-89h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+68h] [rbp-71h] BYREF
  __int64 v20; // [rsp+88h] [rbp-51h]
  _DWORD v21[6]; // [rsp+90h] [rbp-49h] BYREF
  __int64 v22; // [rsp+A8h] [rbp-31h]
  int v23; // [rsp+B0h] [rbp-29h]
  int v24; // [rsp+B4h] [rbp-25h]
  int v25; // [rsp+B8h] [rbp-21h]
  int v26; // [rsp+C0h] [rbp-19h]
  int v27; // [rsp+C4h] [rbp-15h]
  __int64 v28; // [rsp+C8h] [rbp-11h]
  int v29; // [rsp+D0h] [rbp-9h]
  int v30; // [rsp+D4h] [rbp-5h]
  int v31; // [rsp+D8h] [rbp-1h]
  __int64 v32; // [rsp+E0h] [rbp+7h]
  const WCHAR *v33; // [rsp+E8h] [rbp+Fh]

  v21[5] = 26;
  Block = 0;
  v20 = 0;
  v16 = 0;
  v21[0] = 0;
  v21[1] = 2;
  v21[2] = 1048578;
  v33 = L"WmsShell";
  v21[4] = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v22 = 0;
  v23 = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v24 = 2;
  v25 = 1048578;
  v26 = 0;
  v27 = 22;
  v28 = 0;
  v29 = 0;
  v30 = 2;
  v31 = 1048578;
  v32 = 1;
  DoesUserExist = CUserManagement::s_DoesUserExist(a1, &v16);
  if ( DoesUserExist >= 0 )
  {
    v6 = 3;
    if ( !v16 )
      v6 = 2;
    v7 = CreateSecurityDescriptor(1u, 0, 0, (struct WmsAce *)v21, v6, pSecurityDescriptor, &Block);
    DoesUserExist = v7;
    if ( v7 < 0 )
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x4CAu,
        L"CreateWmsNamedEvent",
        L"CHRA",
        L"hr",
        v7);
      if ( IsDebuggerPresent() )
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          1226,
          L"CreateWmsNamedEvent",
          L"CHRA",
          L"hr",
          DoesUserExist);
      }
      else
      {
        LODWORD(v15) = DoesUserExist;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          1226,
          L"CreateWmsNamedEvent",
          L"CHRA",
          L"hr",
          v15);
      }
      goto LABEL_26;
    }
    EventAttributes.nLength = 24;
    EventAttributes.lpSecurityDescriptor = pSecurityDescriptor;
    EventAttributes.bInheritHandle = 0;
    v8 = CreateEventW(&EventAttributes, 1, 0, a2);
    if ( !v8 )
    {
      LastError = GetLastError();
      if ( LastError != 5 )
      {
        if ( LastError > 0 )
          DoesUserExist = (unsigned __int16)LastError | 0x80070000;
        else
          DoesUserExist = LastError;
        v10 = 1237;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          0x4D5u,
          L"CreateWmsNamedEvent",
          L"CBRAEx",
          L"dwLastError == 5L",
          DoesUserExist);
        v11 = !IsDebuggerPresent();
        v12 = L"dwLastError == 5L";
LABEL_16:
        if ( v11 )
        {
          LODWORD(v15) = DoesUserExist;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            v10,
            L"CreateWmsNamedEvent",
            L"CBRAEx",
            v12,
            v15);
        }
        else
        {
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            v10,
            L"CreateWmsNamedEvent",
            L"CBRAEx",
            v12,
            DoesUserExist);
        }
        goto LABEL_26;
      }
      v8 = OpenEventW(0x100002u, 0, a2);
      if ( !v8 )
      {
        v13 = GetLastError();
        DoesUserExist = v13;
        if ( v13 > 0 )
          DoesUserExist = (unsigned __int16)v13 | 0x80070000;
        v10 = 1241;
        if ( DoesUserExist >= 0 )
          DoesUserExist = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          0x4D9u,
          L"CreateWmsNamedEvent",
          L"CBRAEx",
          L"hWmsSvcReadyEvent != 0",
          DoesUserExist);
        v11 = !IsDebuggerPresent();
        v12 = L"hWmsSvcReadyEvent != 0";
        goto LABEL_16;
      }
    }
    *a3 = v8;
  }
LABEL_26:
  operator delete(Block);
  return (unsigned int)DoesUserExist;
}

```

## disassembly

```asm
0x140006e24  mov     [rsp-8+arg_0], rbx
0x140006e29  push    rbp
0x140006e2a  push    rsi
0x140006e2b  push    rdi
0x140006e2c  push    r12
0x140006e2e  push    r13
0x140006e30  push    r14
0x140006e32  push    r15
0x140006e34  lea     rbp, [rsp-27h]
0x140006e39  sub     rsp, 100h
0x140006e40  mov     rax, cs:__security_cookie
0x140006e47  xor     rax, rsp
0x140006e4a  mov     [rbp+57h+var_40], rax
0x140006e4e  xor     r15d, r15d
0x140006e51  mov     [rbp+57h+var_8C], 1Ah
0x140006e58  xor     eax, eax
0x140006e5a  mov     [rsp+130h+Block], r15
0x140006e5f  xorps   xmm0, xmm0
0x140006e62  mov     [rbp+57h+var_A8], rax
0x140006e66  mov     r14d, 100002h
0x140006e6c  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], rax
0x140006e70  mov     rdi, rdx
0x140006e73  mov     [rsp+130h+var_F0], r15d
0x140006e78  lea     r12d, [rax+2]
0x140006e7c  mov     [rbp+57h+var_A0], r15d
0x140006e80  lea     r13d, [rax+1]
0x140006e84  mov     [rbp+57h+var_9C], r12d
0x140006e88  lea     rax, username; "WmsShell"
0x140006e8f  mov     [rbp+57h+var_98], r14d
0x140006e93  lea     rdx, [rsp+130h+var_F0]; int *
0x140006e98  mov     [rbp+57h+var_48], rax
0x140006e9c  mov     rsi, r8
0x140006e9f  mov     [rbp+57h+var_90], r15d
0x140006ea3  movups  [rbp+57h+var_C8], xmm0
0x140006ea7  mov     [rbp+57h+var_88], r15
0x140006eab  movups  [rbp+57h+var_B8], xmm0
0x140006eaf  mov     [rbp+57h+var_80], r15d
0x140006eb3  movups  xmmword ptr [rsp+130h+EventAttributes.nLength], xmm0
0x140006eb8  mov     [rbp+57h+var_7C], r12d
0x140006ebc  mov     [rbp+57h+var_78], r14d
0x140006ec0  mov     [rbp+57h+var_70], r15d
0x140006ec4  mov     [rbp+57h+var_6C], 16h
0x140006ecb  mov     [rbp+57h+var_68], r15
0x140006ecf  mov     [rbp+57h+var_60], r15d
0x140006ed3  mov     [rbp+57h+var_5C], r12d
0x140006ed7  mov     [rbp+57h+var_58], r14d
0x140006edb  mov     [rbp+57h+var_50], r13
0x140006edf  call    ?s_DoesUserExist@CUserManagement@@SAJPEBGPEAH@Z; CUserManagement::s_DoesUserExist(ushort const *,int *)
0x140006ee4  mov     ebx, eax
0x140006ee6  test    eax, eax
0x140006ee8  js      loc_14000711D
0x140006eee  cmp     [rsp+130h+var_F0], r15d
0x140006ef3  lea     rcx, [rsp+130h+Block]
0x140006ef8  mov     [rsp+130h+var_100], rcx; void **
0x140006efd  lea     eax, [r15+3]
0x140006f01  cmovz   eax, r12d
0x140006f05  lea     rcx, [rbp+57h+var_C8]
0x140006f09  mov     [rsp+130h+pSecurityDescriptor], rcx; pSecurityDescriptor
0x140006f0e  lea     r9, [rbp+57h+var_A0]; struct WmsAce *
0x140006f12  mov     ecx, r13d; unsigned int
0x140006f15  mov     [rsp+130h+var_110], rax; unsigned __int64
0x140006f1a  xor     r8d, r8d; struct WmsSid *
0x140006f1d  xor     edx, edx; struct WmsSid *
0x140006f1f  call    ?CreateSecurityDescriptor@@YAJKPEAUWmsSid@@0PEAUWmsAce@@_KPEAU_SECURITY_DESCRIPTOR@@PEAPEAX@Z; CreateSecurityDescriptor(ulong,WmsSid *,WmsSid *,WmsAce *,unsigned __int64,_SECURITY_DESCRIPTOR *,void * *)
0x140006f24  mov     ebx, eax
0x140006f26  test    eax, eax
0x140006f28  jns     loc_140006FCA
0x140006f2e  mov     dword ptr [rsp+130h+pSecurityDescriptor], eax; int
0x140006f32  lea     r13, aChra; "CHRA"
0x140006f39  lea     rsi, aCreatewmsnamed; "CreateWmsNamedEvent"
0x140006f40  mov     r14d, 4CAh
0x140006f46  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140006f4d  mov     r9, r13; unsigned __int16 *
0x140006f50  lea     r12, aHr; "hr"
0x140006f57  mov     r8, rsi; unsigned __int16 *
0x140006f5a  mov     edx, r14d; unsigned int
0x140006f5d  mov     [rsp+130h+var_110], r12; unsigned __int16 *
0x140006f62  mov     rcx, rdi; unsigned __int16 *
0x140006f65  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140006f6a  call    cs:__imp_IsDebuggerPresent
0x140006f70  test    eax, eax
0x140006f72  jz      short loc_140006FA2
0x140006f74  mov     [rsp+130h+var_F8], ebx
0x140006f78  lea     ecx, [r15+2]; unsigned __int8
0x140006f7c  mov     [rsp+130h+var_100], r12
0x140006f81  mov     r9d, r14d
0x140006f84  mov     [rsp+130h+pSecurityDescriptor], r13
0x140006f89  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140006f90  mov     [rsp+130h+var_110], rsi
0x140006f95  mov     r8, rdi
0x140006f98  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140006f9d  jmp     loc_14000711D
0x140006fa2  mov     dword ptr [rsp+130h+var_100], ebx
0x140006fa6  mov     r8d, r14d
0x140006fa9  mov     [rsp+130h+pSecurityDescriptor], r12
0x140006fae  mov     [rsp+130h+var_110], r13
0x140006fb3  mov     r9, rsi
0x140006fb6  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140006fbd  mov     rdx, rdi
0x140006fc0  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140006fc5  jmp     loc_14000711D
0x140006fca  lea     rax, [rbp+57h+var_C8]
0x140006fce  mov     [rsp+130h+EventAttributes.nLength], 18h
0x140006fd6  mov     r9, rdi; lpName
0x140006fd9  mov     [rsp+130h+EventAttributes.lpSecurityDescriptor], rax
0x140006fde  xor     r8d, r8d; bInitialState
0x140006fe1  mov     [rbp+57h+EventAttributes.bInheritHandle], r15d
0x140006fe5  mov     edx, r13d; bManualReset
0x140006fe8  lea     rcx, [rsp+130h+EventAttributes]; lpEventAttributes
0x140006fed  call    cs:__imp_CreateEventW
0x140006ff3  test    rax, rax
0x140006ff6  jnz     loc_14000711A
0x140006ffc  call    cs:__imp_GetLastError
0x140007002  cmp     eax, 5
0x140007005  jz      loc_140007098
0x14000700b  test    eax, eax
0x14000700d  jg      short loc_140007013
0x14000700f  mov     ebx, eax
0x140007011  jmp     short loc_14000701C
0x140007013  movzx   ebx, ax
0x140007016  or      ebx, 80070000h
0x14000701c  lea     rax, aDwlasterror5l; "dwLastError == 5L"
0x140007023  mov     dword ptr [rsp+130h+pSecurityDescriptor], ebx; int
0x140007027  lea     r14, aCbraex; "CBRAEx"
0x14000702e  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x140007033  lea     rsi, aCreatewmsnamed; "CreateWmsNamedEvent"
0x14000703a  mov     r13d, 4D5h
0x140007040  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140007047  mov     r9, r14; unsigned __int16 *
0x14000704a  mov     r8, rsi; unsigned __int16 *
0x14000704d  mov     edx, r13d; unsigned int
0x140007050  mov     rcx, rdi; unsigned __int16 *
0x140007053  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007058  call    cs:__imp_IsDebuggerPresent
0x14000705e  test    eax, eax
0x140007060  lea     rax, aDwlasterror5l; "dwLastError == 5L"
0x140007067  jz      short loc_140007082
0x140007069  mov     [rsp+130h+var_F8], ebx
0x14000706d  mov     r9d, r13d
0x140007070  mov     [rsp+130h+var_100], rax
0x140007075  mov     ecx, r12d
0x140007078  mov     [rsp+130h+pSecurityDescriptor], r14
0x14000707d  jmp     loc_140006F89
0x140007082  mov     dword ptr [rsp+130h+var_100], ebx
0x140007086  mov     r8d, r13d
0x140007089  mov     [rsp+130h+pSecurityDescriptor], rax
0x14000708e  mov     [rsp+130h+var_110], r14
0x140007093  jmp     loc_140006FB3
0x140007098  mov     r8, rdi; lpName
0x14000709b  xor     edx, edx; bInheritHandle
0x14000709d  mov     ecx, r14d; dwDesiredAccess
0x1400070a0  call    cs:__imp_OpenEventW
0x1400070a6  test    rax, rax
0x1400070a9  jnz     short loc_14000711A
0x1400070ab  call    cs:__imp_GetLastError
0x1400070b1  mov     ebx, eax
0x1400070b3  test    eax, eax
0x1400070b5  jle     short loc_1400070C0
0x1400070b7  movzx   ebx, ax
0x1400070ba  or      ebx, 80070000h
0x1400070c0  mov     eax, 80004005h
0x1400070c5  lea     r14, aCbraex; "CBRAEx"
0x1400070cc  test    ebx, ebx
0x1400070ce  lea     rsi, aCreatewmsnamed; "CreateWmsNamedEvent"
0x1400070d5  mov     r13d, 4D9h
0x1400070db  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400070e2  cmovns  ebx, eax
0x1400070e5  mov     r9, r14; unsigned __int16 *
0x1400070e8  lea     rax, aHwmssvcreadyev; "hWmsSvcReadyEvent != 0"
0x1400070ef  mov     dword ptr [rsp+130h+pSecurityDescriptor], ebx; int
0x1400070f3  mov     r8, rsi; unsigned __int16 *
0x1400070f6  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x1400070fb  mov     edx, r13d; unsigned int
0x1400070fe  mov     rcx, rdi; unsigned __int16 *
0x140007101  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007106  call    cs:__imp_IsDebuggerPresent
0x14000710c  test    eax, eax
0x14000710e  lea     rax, aHwmssvcreadyev; "hWmsSvcReadyEvent != 0"
0x140007115  jmp     loc_140007067
0x14000711a  mov     [rsi], rax
0x14000711d  mov     rcx, [rsp+130h+Block]; Block
0x140007122  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140007127  mov     eax, ebx
0x140007129  mov     rcx, [rbp+57h+var_40]
0x14000712d  xor     rcx, rsp; StackCookie
0x140007130  call    __security_check_cookie
0x140007135  mov     rbx, [rsp+130h+arg_0]
0x14000713d  add     rsp, 100h
0x140007144  pop     r15
0x140007146  pop     r14
0x140007148  pop     r13
0x14000714a  pop     r12
0x14000714c  pop     rdi
0x14000714d  pop     rsi
0x14000714e  pop     rbp
0x14000714f  retn
```
