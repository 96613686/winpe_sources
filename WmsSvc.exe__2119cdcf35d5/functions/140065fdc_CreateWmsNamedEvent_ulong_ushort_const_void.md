# CreateWmsNamedEvent(ulong,ushort const *,void * *)

- ea: `0x140065fdc`
- end: `0x140066307`
- name: `?CreateWmsNamedEvent@@YAJKPEBGPEAPEAX@Z`
- size: `811`
- prototype: `__int64 __fastcall(DWORD dwDesiredAccess, LPCWSTR lpName, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140045b90`

## callees

- `0x1400016b8`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400657e8`
- `0x140065fdc`
- `0x14006aef0`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x140066257`
- `KERNEL32!OpenEventW` at `0x140066257`
- `KERNEL32!CreateEventW` at `0x1400661a4`
- `KERNEL32!CreateEventW` at `0x1400661a4`
- `KERNEL32!GetLastError` at `0x1400661b3`
- `KERNEL32!GetLastError` at `0x140066262`
- `KERNEL32!GetLastError` at `0x1400661b3`
- `KERNEL32!GetLastError` at `0x140066262`
- `KERNEL32!IsDebuggerPresent` at `0x140066121`
- `KERNEL32!IsDebuggerPresent` at `0x14006620f`
- `KERNEL32!IsDebuggerPresent` at `0x1400662bd`
- `KERNEL32!IsDebuggerPresent` at `0x140066121`
- `KERNEL32!IsDebuggerPresent` at `0x14006620f`
- `KERNEL32!IsDebuggerPresent` at `0x1400662bd`

## string_xrefs

- `0x1400660fd`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400661f7`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140066292`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400660f0`: `CreateWmsNamedEvent`
- `0x1400661ea`: `CreateWmsNamedEvent`
- `0x140066285`: `CreateWmsNamedEvent`
- `0x14006629f`: `hWmsSvcReadyEvent != 0`
- `0x1400662c5`: `hWmsSvcReadyEvent != 0`

## pseudocode

```c
__int64 __fastcall CreateWmsNamedEvent(DWORD dwDesiredAccess, LPCWSTR lpName, void **a3)
{
  signed int DoesUserExist; // ebx
  unsigned __int64 v7; // rax
  int v8; // eax
  HANDLE v9; // rax
  signed int LastError; // eax
  unsigned int v11; // r13d
  bool v12; // zf
  const unsigned __int16 *v13; // rax
  signed int v14; // eax
  void **v16; // [rsp+30h] [rbp-A9h]
  int v17; // [rsp+40h] [rbp-99h] BYREF
  void *Block; // [rsp+48h] [rbp-91h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+50h] [rbp-89h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+68h] [rbp-71h] BYREF
  __int64 v21; // [rsp+88h] [rbp-51h]
  _DWORD v22[6]; // [rsp+90h] [rbp-49h] BYREF
  __int64 v23; // [rsp+A8h] [rbp-31h]
  int v24; // [rsp+B0h] [rbp-29h]
  int v25; // [rsp+B4h] [rbp-25h]
  int v26; // [rsp+B8h] [rbp-21h]
  int v27; // [rsp+C0h] [rbp-19h]
  int v28; // [rsp+C4h] [rbp-15h]
  __int64 v29; // [rsp+C8h] [rbp-11h]
  int v30; // [rsp+D0h] [rbp-9h]
  int v31; // [rsp+D4h] [rbp-5h]
  int v32; // [rsp+D8h] [rbp-1h]
  __int64 v33; // [rsp+E0h] [rbp+7h]
  const WCHAR *v34; // [rsp+E8h] [rbp+Fh]

  v22[5] = 26;
  Block = 0;
  v21 = 0;
  v17 = 0;
  v22[0] = 0;
  v22[1] = 2;
  v22[2] = 1048578;
  v26 = 1048578;
  v32 = 1048578;
  v22[4] = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v23 = 0;
  v24 = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v25 = 2;
  v27 = 0;
  v28 = 22;
  v29 = 0;
  v30 = 0;
  v31 = 2;
  v33 = 1;
  v34 = L"WmsShell";
  DoesUserExist = CUserManagement::s_DoesUserExist(L"WmsShell", &v17);
  if ( DoesUserExist >= 0 )
  {
    v7 = 3;
    if ( !v17 )
      v7 = 2;
    v8 = CreateSecurityDescriptor(1u, 0, 0, (struct WmsAce *)v22, v7, pSecurityDescriptor, &Block);
    DoesUserExist = v8;
    if ( v8 < 0 )
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x4CAu,
        L"CreateWmsNamedEvent",
        L"CHRA",
        L"hr",
        v8);
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
        LODWORD(v16) = DoesUserExist;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          1226,
          L"CreateWmsNamedEvent",
          L"CHRA",
          L"hr",
          v16);
      }
      goto LABEL_26;
    }
    EventAttributes.nLength = 24;
    EventAttributes.lpSecurityDescriptor = pSecurityDescriptor;
    EventAttributes.bInheritHandle = 0;
    v9 = CreateEventW(&EventAttributes, 1, 0, lpName);
    if ( !v9 )
    {
      LastError = GetLastError();
      if ( LastError != 5 )
      {
        if ( LastError > 0 )
          DoesUserExist = (unsigned __int16)LastError | 0x80070000;
        else
          DoesUserExist = LastError;
        v11 = 1237;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          0x4D5u,
          L"CreateWmsNamedEvent",
          L"CBRAEx",
          L"dwLastError == 5L",
          DoesUserExist);
        v12 = !IsDebuggerPresent();
        v13 = L"dwLastError == 5L";
LABEL_16:
        if ( v12 )
        {
          LODWORD(v16) = DoesUserExist;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            v11,
            L"CreateWmsNamedEvent",
            L"CBRAEx",
            v13,
            v16);
        }
        else
        {
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            v11,
            L"CreateWmsNamedEvent",
            L"CBRAEx",
            v13,
            DoesUserExist);
        }
        goto LABEL_26;
      }
      v9 = OpenEventW(dwDesiredAccess, 0, lpName);
      if ( !v9 )
      {
        v14 = GetLastError();
        DoesUserExist = v14;
        if ( v14 > 0 )
          DoesUserExist = (unsigned __int16)v14 | 0x80070000;
        v11 = 1241;
        if ( DoesUserExist >= 0 )
          DoesUserExist = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          0x4D9u,
          L"CreateWmsNamedEvent",
          L"CBRAEx",
          L"hWmsSvcReadyEvent != 0",
          DoesUserExist);
        v12 = !IsDebuggerPresent();
        v13 = L"hWmsSvcReadyEvent != 0";
        goto LABEL_16;
      }
    }
    *a3 = v9;
  }
LABEL_26:
  operator delete(Block);
  return (unsigned int)DoesUserExist;
}

```

## disassembly

```asm
0x140065fdc  mov     [rsp-8+arg_18], rbx
0x140065fe1  push    rbp
0x140065fe2  push    rsi
0x140065fe3  push    rdi
0x140065fe4  push    r12
0x140065fe6  push    r13
0x140065fe8  push    r14
0x140065fea  push    r15
0x140065fec  lea     rbp, [rsp-27h]
0x140065ff1  sub     rsp, 100h
0x140065ff8  mov     rax, cs:__security_cookie
0x140065fff  xor     rax, rsp
0x140066002  mov     [rbp+57h+var_40], rax
0x140066006  xor     r15d, r15d
0x140066009  mov     [rbp+57h+var_8C], 1Ah
0x140066010  xor     eax, eax
0x140066012  mov     [rsp+130h+Block], r15
0x140066017  xorps   xmm0, xmm0
0x14006601a  mov     [rbp+57h+var_A8], rax
0x14006601e  mov     r14d, ecx
0x140066021  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], rax
0x140066025  mov     rdi, rdx
0x140066028  mov     [rsp+130h+var_F0], r15d
0x14006602d  lea     r12d, [rax+2]
0x140066031  mov     [rbp+57h+var_A0], r15d
0x140066035  mov     eax, 100002h
0x14006603a  mov     [rbp+57h+var_9C], r12d
0x14006603e  lea     rcx, username; "WmsShell"
0x140066045  mov     [rbp+57h+var_98], eax
0x140066048  lea     r13d, [r15+1]
0x14006604c  mov     [rbp+57h+var_78], eax
0x14006604f  lea     rdx, [rsp+130h+var_F0]; int *
0x140066054  mov     [rbp+57h+var_58], eax
0x140066057  mov     rsi, r8
0x14006605a  mov     [rbp+57h+var_90], r15d
0x14006605e  movups  [rbp+57h+var_C8], xmm0
0x140066062  mov     [rbp+57h+var_88], r15
0x140066066  movups  [rbp+57h+var_B8], xmm0
0x14006606a  mov     [rbp+57h+var_80], r15d
0x14006606e  movups  xmmword ptr [rsp+130h+EventAttributes.nLength], xmm0
0x140066073  mov     [rbp+57h+var_7C], r12d
0x140066077  mov     [rbp+57h+var_70], r15d
0x14006607b  mov     [rbp+57h+var_6C], 16h
0x140066082  mov     [rbp+57h+var_68], r15
0x140066086  mov     [rbp+57h+var_60], r15d
0x14006608a  mov     [rbp+57h+var_5C], r12d
0x14006608e  mov     [rbp+57h+var_50], r13
0x140066092  mov     [rbp+57h+var_48], rcx
0x140066096  call    ?s_DoesUserExist@CUserManagement@@SAJPEBGPEAH@Z; CUserManagement::s_DoesUserExist(ushort const *,int *)
0x14006609b  mov     ebx, eax
0x14006609d  test    eax, eax
0x14006609f  js      loc_1400662D4
0x1400660a5  cmp     [rsp+130h+var_F0], r15d
0x1400660aa  lea     rcx, [rsp+130h+Block]
0x1400660af  mov     [rsp+130h+var_100], rcx; void **
0x1400660b4  lea     eax, [r15+3]
0x1400660b8  cmovz   eax, r12d
0x1400660bc  lea     rcx, [rbp+57h+var_C8]
0x1400660c0  mov     [rsp+130h+pSecurityDescriptor], rcx; pSecurityDescriptor
0x1400660c5  lea     r9, [rbp+57h+var_A0]; struct WmsAce *
0x1400660c9  mov     ecx, r13d; unsigned int
0x1400660cc  mov     [rsp+130h+var_110], rax; unsigned __int64
0x1400660d1  xor     r8d, r8d; struct WmsSid *
0x1400660d4  xor     edx, edx; struct WmsSid *
0x1400660d6  call    ?CreateSecurityDescriptor@@YAJKPEAUWmsSid@@0PEAUWmsAce@@_KPEAU_SECURITY_DESCRIPTOR@@PEAPEAX@Z; CreateSecurityDescriptor(ulong,WmsSid *,WmsSid *,WmsAce *,unsigned __int64,_SECURITY_DESCRIPTOR *,void * *)
0x1400660db  mov     ebx, eax
0x1400660dd  test    eax, eax
0x1400660df  jns     loc_140066181
0x1400660e5  mov     dword ptr [rsp+130h+pSecurityDescriptor], eax; int
0x1400660e9  lea     r13, aChra; "CHRA"
0x1400660f0  lea     rsi, aCreatewmsnamed; "CreateWmsNamedEvent"
0x1400660f7  mov     r14d, 4CAh
0x1400660fd  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140066104  mov     r9, r13; unsigned __int16 *
0x140066107  lea     r12, aHr; "hr"
0x14006610e  mov     r8, rsi; unsigned __int16 *
0x140066111  mov     edx, r14d; unsigned int
0x140066114  mov     [rsp+130h+var_110], r12; unsigned __int16 *
0x140066119  mov     rcx, rdi; unsigned __int16 *
0x14006611c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140066121  call    cs:__imp_IsDebuggerPresent
0x140066127  test    eax, eax
0x140066129  jz      short loc_140066159
0x14006612b  mov     [rsp+130h+var_F8], ebx
0x14006612f  lea     ecx, [r15+2]; unsigned __int8
0x140066133  mov     [rsp+130h+var_100], r12
0x140066138  mov     r9d, r14d
0x14006613b  mov     [rsp+130h+pSecurityDescriptor], r13
0x140066140  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140066147  mov     [rsp+130h+var_110], rsi
0x14006614c  mov     r8, rdi
0x14006614f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140066154  jmp     loc_1400662D4
0x140066159  mov     dword ptr [rsp+130h+var_100], ebx
0x14006615d  mov     r8d, r14d
0x140066160  mov     [rsp+130h+pSecurityDescriptor], r12
0x140066165  mov     [rsp+130h+var_110], r13
0x14006616a  mov     r9, rsi
0x14006616d  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140066174  mov     rdx, rdi
0x140066177  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006617c  jmp     loc_1400662D4
0x140066181  lea     rax, [rbp+57h+var_C8]
0x140066185  mov     [rsp+130h+EventAttributes.nLength], 18h
0x14006618d  mov     r9, rdi; lpName
0x140066190  mov     [rsp+130h+EventAttributes.lpSecurityDescriptor], rax
0x140066195  xor     r8d, r8d; bInitialState
0x140066198  mov     [rbp+57h+EventAttributes.bInheritHandle], r15d
0x14006619c  mov     edx, r13d; bManualReset
0x14006619f  lea     rcx, [rsp+130h+EventAttributes]; lpEventAttributes
0x1400661a4  call    cs:__imp_CreateEventW
0x1400661aa  test    rax, rax
0x1400661ad  jnz     loc_1400662D1
0x1400661b3  call    cs:__imp_GetLastError
0x1400661b9  cmp     eax, 5
0x1400661bc  jz      loc_14006624F
0x1400661c2  test    eax, eax
0x1400661c4  jg      short loc_1400661CA
0x1400661c6  mov     ebx, eax
0x1400661c8  jmp     short loc_1400661D3
0x1400661ca  movzx   ebx, ax
0x1400661cd  or      ebx, 80070000h
0x1400661d3  lea     rax, aDwlasterror5l; "dwLastError == 5L"
0x1400661da  mov     dword ptr [rsp+130h+pSecurityDescriptor], ebx; int
0x1400661de  lea     r14, aCbraex; "CBRAEx"
0x1400661e5  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x1400661ea  lea     rsi, aCreatewmsnamed; "CreateWmsNamedEvent"
0x1400661f1  mov     r13d, 4D5h
0x1400661f7  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400661fe  mov     r9, r14; unsigned __int16 *
0x140066201  mov     r8, rsi; unsigned __int16 *
0x140066204  mov     edx, r13d; unsigned int
0x140066207  mov     rcx, rdi; unsigned __int16 *
0x14006620a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006620f  call    cs:__imp_IsDebuggerPresent
0x140066215  test    eax, eax
0x140066217  lea     rax, aDwlasterror5l; "dwLastError == 5L"
0x14006621e  jz      short loc_140066239
0x140066220  mov     [rsp+130h+var_F8], ebx
0x140066224  mov     r9d, r13d
0x140066227  mov     [rsp+130h+var_100], rax
0x14006622c  mov     ecx, r12d
0x14006622f  mov     [rsp+130h+pSecurityDescriptor], r14
0x140066234  jmp     loc_140066140
0x140066239  mov     dword ptr [rsp+130h+var_100], ebx
0x14006623d  mov     r8d, r13d
0x140066240  mov     [rsp+130h+pSecurityDescriptor], rax
0x140066245  mov     [rsp+130h+var_110], r14
0x14006624a  jmp     loc_14006616A
0x14006624f  mov     r8, rdi; lpName
0x140066252  xor     edx, edx; bInheritHandle
0x140066254  mov     ecx, r14d; dwDesiredAccess
0x140066257  call    cs:__imp_OpenEventW
0x14006625d  test    rax, rax
0x140066260  jnz     short loc_1400662D1
0x140066262  call    cs:__imp_GetLastError
0x140066268  mov     ebx, eax
0x14006626a  test    eax, eax
0x14006626c  jle     short loc_140066277
0x14006626e  movzx   ebx, ax
0x140066271  or      ebx, 80070000h
0x140066277  mov     eax, 80004005h
0x14006627c  lea     r14, aCbraex; "CBRAEx"
0x140066283  test    ebx, ebx
0x140066285  lea     rsi, aCreatewmsnamed; "CreateWmsNamedEvent"
0x14006628c  mov     r13d, 4D9h
0x140066292  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140066299  cmovns  ebx, eax
0x14006629c  mov     r9, r14; unsigned __int16 *
0x14006629f  lea     rax, aHwmssvcreadyev; "hWmsSvcReadyEvent != 0"
0x1400662a6  mov     dword ptr [rsp+130h+pSecurityDescriptor], ebx; int
0x1400662aa  mov     r8, rsi; unsigned __int16 *
0x1400662ad  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x1400662b2  mov     edx, r13d; unsigned int
0x1400662b5  mov     rcx, rdi; unsigned __int16 *
0x1400662b8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400662bd  call    cs:__imp_IsDebuggerPresent
0x1400662c3  test    eax, eax
0x1400662c5  lea     rax, aHwmssvcreadyev; "hWmsSvcReadyEvent != 0"
0x1400662cc  jmp     loc_14006621E
0x1400662d1  mov     [rsi], rax
0x1400662d4  mov     rcx, [rsp+130h+Block]; Block
0x1400662d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400662de  mov     eax, ebx
0x1400662e0  mov     rcx, [rbp+57h+var_40]
0x1400662e4  xor     rcx, rsp; StackCookie
0x1400662e7  call    __security_check_cookie
0x1400662ec  mov     rbx, [rsp+130h+arg_18]
0x1400662f4  add     rsp, 100h
0x1400662fb  pop     r15
0x1400662fd  pop     r14
0x1400662ff  pop     r13
0x140066301  pop     r12
0x140066303  pop     rdi
0x140066304  pop     rsi
0x140066305  pop     rbp
0x140066306  retn
```
