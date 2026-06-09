# GetLocalHostName(ushort * *)

- ea: `0x140064644`
- end: `0x140064910`
- name: `?GetLocalHostName@@YAJPEAPEAG@Z`
- size: `716`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `10`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002aa70`
- `0x14002b2ac`
- `0x14002ba9c`
- `0x14002c1b8`
- `0x140046d54`
- `0x14004823c`
- `0x140048fa8`
- `0x140055970`
- `0x140058260`
- `0x140059214`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140064644`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x14006466c`
- `KERNEL32!GetComputerNameExW` at `0x1400647db`
- `KERNEL32!GetComputerNameExW` at `0x14006466c`
- `KERNEL32!GetComputerNameExW` at `0x1400647db`
- `KERNEL32!GetLastError` at `0x14006467a`
- `KERNEL32!GetLastError` at `0x14006468d`
- `KERNEL32!GetLastError` at `0x1400647e5`
- `KERNEL32!GetLastError` at `0x14006467a`
- `KERNEL32!GetLastError` at `0x14006468d`
- `KERNEL32!GetLastError` at `0x1400647e5`
- `KERNEL32!IsDebuggerPresent` at `0x1400646de`
- `KERNEL32!IsDebuggerPresent` at `0x14006479f`
- `KERNEL32!IsDebuggerPresent` at `0x140064836`
- `KERNEL32!IsDebuggerPresent` at `0x1400648bd`
- `KERNEL32!IsDebuggerPresent` at `0x1400646de`
- `KERNEL32!IsDebuggerPresent` at `0x14006479f`
- `KERNEL32!IsDebuggerPresent` at `0x140064836`
- `KERNEL32!IsDebuggerPresent` at `0x1400648bd`
- `OLEAUT32!__imp_SysAllocString` at `0x140064869`
- `OLEAUT32!__imp_SysAllocString` at `0x140064869`

## string_xrefs

- `0x1400646ba`: `termsrv\wms\src\common\srcutils\wsutils.cpp`
- `0x140064784`: `termsrv\wms\src\common\srcutils\wsutils.cpp`
- `0x140064812`: `termsrv\wms\src\common\srcutils\wsutils.cpp`
- `0x1400648a2`: `termsrv\wms\src\common\srcutils\wsutils.cpp`

## pseudocode

```c
__int64 __fastcall GetLocalHostName(unsigned __int16 **a1)
{
  OLECHAR *v2; // rbp
  signed int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // r15d
  __int64 v6; // r9
  WCHAR *v7; // rax
  unsigned int v8; // r13d
  bool v9; // zf
  const unsigned __int16 *v10; // rax
  signed int LastError; // eax
  unsigned __int16 *v12; // rax
  const unsigned __int16 *v14; // [rsp+28h] [rbp-60h]
  const unsigned __int16 *v15; // [rsp+28h] [rbp-60h]
  const unsigned __int16 *v16; // [rsp+30h] [rbp-58h]
  unsigned int v17; // [rsp+30h] [rbp-58h]
  int v18; // [rsp+38h] [rbp-50h]
  DWORD nSize; // [rsp+98h] [rbp+10h] BYREF

  nSize = 0;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, 0, &nSize) || GetLastError() == 234 )
  {
    v7 = (WCHAR *)operator new(saturated_mul(nSize, 2u));
    v2 = v7;
    if ( v7 )
    {
      if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, v7, &nSize) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        v5 = 527;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\wsutils.cpp",
          0x20Fu,
          L"GetLocalHostName",
          L"CBRAEx",
          L"fSuccess",
          v4);
        if ( IsDebuggerPresent() )
        {
          v18 = v4;
          v6 = 527;
          v16 = L"fSuccess";
          v14 = L"CBRAEx";
          goto LABEL_7;
        }
        v17 = v4;
        v15 = L"fSuccess";
LABEL_9:
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\wsutils.cpp",
          v5,
          L"GetLocalHostName",
          L"CBRAEx",
          v15,
          v17);
        goto LABEL_23;
      }
      v4 = 0;
      v12 = SysAllocString(v2);
      *a1 = v12;
      if ( v12 )
        goto LABEL_23;
      v8 = 530;
      v4 = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\wsutils.cpp",
        0x212u,
        L"GetLocalHostName",
        L"CPR",
        L"*pbstrHostName",
        -2147024882);
      v9 = !IsDebuggerPresent();
      v10 = L"*pbstrHostName";
    }
    else
    {
      v8 = 524;
      v4 = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\wsutils.cpp",
        0x20Cu,
        L"GetLocalHostName",
        L"CPR",
        L"pszHostName",
        -2147024882);
      v9 = !IsDebuggerPresent();
      v10 = L"pszHostName";
    }
    if ( v9 )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\wsutils.cpp",
        v8,
        L"GetLocalHostName",
        L"CPR",
        v10,
        -2147024882);
      goto LABEL_23;
    }
    v18 = -2147024882;
    v6 = v8;
    v16 = v10;
    v14 = L"CPR";
    goto LABEL_7;
  }
  v2 = 0;
  v3 = GetLastError();
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  v5 = 521;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\wsutils.cpp",
    0x209u,
    L"GetLocalHostName",
    L"CBRAEx",
    L"fSuccess || GetLastError() == 234L",
    v4);
  if ( !IsDebuggerPresent() )
  {
    v17 = v4;
    v15 = L"fSuccess || GetLastError() == 234L";
    goto LABEL_9;
  }
  v18 = v4;
  v6 = 521;
  v16 = L"fSuccess || GetLastError() == 234L";
  v14 = L"CBRAEx";
LABEL_7:
  DEBUGMSGLEVEL(
    2u,
    L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
    L"termsrv\\wms\\src\\common\\srcutils\\wsutils.cpp",
    v6,
    L"GetLocalHostName",
    v14,
    v16,
    v18);
LABEL_23:
  operator delete(v2);
  return v4;
}

```

## disassembly

```asm
0x140064644  mov     rax, rsp
0x140064647  push    rbx
0x140064648  push    rbp
0x140064649  push    rsi
0x14006464a  push    rdi
0x14006464b  push    r12
0x14006464d  push    r13
0x14006464f  push    r14
0x140064651  push    r15
0x140064653  sub     rsp, 48h
0x140064657  xor     edx, edx; lpBuffer
0x140064659  mov     dword ptr [rax+10h], 0
0x140064660  mov     rdi, rcx
0x140064663  lea     r8, [rax+10h]; nSize
0x140064667  lea     ebx, [rdx+3]
0x14006466a  mov     ecx, ebx; NameType
0x14006466c  call    cs:__imp_GetComputerNameExW
0x140064672  test    eax, eax
0x140064674  jnz     loc_14006472D
0x14006467a  call    cs:__imp_GetLastError
0x140064680  cmp     eax, 0EAh
0x140064685  jz      loc_14006472D
0x14006468b  xor     ebp, ebp
0x14006468d  call    cs:__imp_GetLastError
0x140064693  mov     ebx, eax
0x140064695  test    eax, eax
0x140064697  jle     short loc_1400646A2
0x140064699  movzx   ebx, ax
0x14006469c  or      ebx, 80070000h
0x1400646a2  lea     r14, aCbraex; "CBRAEx"
0x1400646a9  mov     [rsp+88h+var_60], ebx; int
0x1400646ad  lea     rsi, aGetlocalhostna; "GetLocalHostName"
0x1400646b4  mov     r15d, 209h
0x1400646ba  lea     rdi, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\ws"...
0x1400646c1  mov     r9, r14; unsigned __int16 *
0x1400646c4  lea     r12, aFsuccessGetlas_0; "fSuccess || GetLastError() == 234L"
0x1400646cb  mov     r8, rsi; unsigned __int16 *
0x1400646ce  mov     edx, r15d; unsigned int
0x1400646d1  mov     [rsp+88h+var_68], r12; unsigned __int16 *
0x1400646d6  mov     rcx, rdi; unsigned __int16 *
0x1400646d9  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400646de  call    cs:__imp_IsDebuggerPresent
0x1400646e4  test    eax, eax
0x1400646e6  jz      short loc_140064717
0x1400646e8  mov     [rsp+88h+var_50], ebx
0x1400646ec  mov     r9d, r15d
0x1400646ef  mov     [rsp+88h+var_58], r12
0x1400646f4  mov     ecx, 2; unsigned __int8
0x1400646f9  mov     qword ptr [rsp+88h+var_60], r14
0x1400646fe  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140064705  mov     [rsp+88h+var_68], rsi
0x14006470a  mov     r8, rdi
0x14006470d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140064712  jmp     loc_1400648F5
0x140064717  mov     dword ptr [rsp+88h+var_58], ebx
0x14006471b  mov     qword ptr [rsp+88h+var_60], r12
0x140064720  mov     [rsp+88h+var_68], r14
0x140064725  mov     r8d, r15d
0x140064728  jmp     loc_1400648E3
0x14006472d  mov     ecx, [rsp+88h+nSize]
0x140064734  mov     r12d, 2
0x14006473a  mov     eax, r12d
0x14006473d  mul     rcx
0x140064740  lea     rcx, [r12-3]
0x140064745  cmovb   rax, rcx
0x140064749  mov     rcx, rax; Size
0x14006474c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140064751  mov     rbp, rax
0x140064754  test    rax, rax
0x140064757  jnz     short loc_1400647CE
0x140064759  mov     r14d, 8007000Eh
0x14006475f  lea     rax, aPszhostname; "pszHostName"
0x140064766  lea     r15, aCpr; "CPR"
0x14006476d  mov     [rsp+88h+var_60], r14d; int
0x140064772  lea     rsi, aGetlocalhostna; "GetLocalHostName"
0x140064779  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x14006477e  mov     r13d, 20Ch
0x140064784  lea     rdi, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\ws"...
0x14006478b  mov     r9, r15; unsigned __int16 *
0x14006478e  mov     r8, rsi; unsigned __int16 *
0x140064791  mov     edx, r13d; unsigned int
0x140064794  mov     rcx, rdi; unsigned __int16 *
0x140064797  mov     ebx, r14d
0x14006479a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006479f  call    cs:__imp_IsDebuggerPresent
0x1400647a5  test    eax, eax
0x1400647a7  lea     rax, aPszhostname; "pszHostName"
0x1400647ae  jz      loc_1400648D1
0x1400647b4  mov     [rsp+88h+var_50], r14d
0x1400647b9  mov     r9d, r13d
0x1400647bc  mov     [rsp+88h+var_58], rax
0x1400647c1  mov     qword ptr [rsp+88h+var_60], r15
0x1400647c6  mov     ecx, r12d
0x1400647c9  jmp     loc_1400646FE
0x1400647ce  lea     r8, [rsp+88h+nSize]; nSize
0x1400647d6  mov     rdx, rbp; lpBuffer
0x1400647d9  mov     ecx, ebx; NameType
0x1400647db  call    cs:__imp_GetComputerNameExW
0x1400647e1  test    eax, eax
0x1400647e3  jnz     short loc_140064864
0x1400647e5  call    cs:__imp_GetLastError
0x1400647eb  mov     ebx, eax
0x1400647ed  test    eax, eax
0x1400647ef  jle     short loc_1400647FA
0x1400647f1  movzx   ebx, ax
0x1400647f4  or      ebx, 80070000h
0x1400647fa  lea     r14, aCbraex; "CBRAEx"
0x140064801  mov     [rsp+88h+var_60], ebx; int
0x140064805  lea     rsi, aGetlocalhostna; "GetLocalHostName"
0x14006480c  mov     r15d, 20Fh
0x140064812  lea     rdi, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\ws"...
0x140064819  mov     r9, r14; unsigned __int16 *
0x14006481c  lea     r13, aFsuccess; "fSuccess"
0x140064823  mov     r8, rsi; unsigned __int16 *
0x140064826  mov     edx, r15d; unsigned int
0x140064829  mov     [rsp+88h+var_68], r13; unsigned __int16 *
0x14006482e  mov     rcx, rdi; unsigned __int16 *
0x140064831  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140064836  call    cs:__imp_IsDebuggerPresent
0x14006483c  test    eax, eax
0x14006483e  jz      short loc_140064856
0x140064840  mov     [rsp+88h+var_50], ebx
0x140064844  mov     r9d, r15d
0x140064847  mov     [rsp+88h+var_58], r13
0x14006484c  mov     qword ptr [rsp+88h+var_60], r14
0x140064851  jmp     loc_1400647C6
0x140064856  mov     dword ptr [rsp+88h+var_58], ebx
0x14006485a  mov     qword ptr [rsp+88h+var_60], r13
0x14006485f  jmp     loc_140064720
0x140064864  mov     rcx, rbp; psz
0x140064867  xor     ebx, ebx
0x140064869  call    cs:__imp_SysAllocString
0x14006486f  mov     [rdi], rax
0x140064872  test    rax, rax
0x140064875  jnz     short loc_1400648F5
0x140064877  mov     r14d, 8007000Eh
0x14006487d  lea     rax, aPbstrhostname; "*pbstrHostName"
0x140064884  lea     r15, aCpr; "CPR"
0x14006488b  mov     [rsp+88h+var_60], r14d; int
0x140064890  lea     rsi, aGetlocalhostna; "GetLocalHostName"
0x140064897  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x14006489c  mov     r13d, 212h
0x1400648a2  lea     rdi, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\ws"...
0x1400648a9  mov     r9, r15; unsigned __int16 *
0x1400648ac  mov     r8, rsi; unsigned __int16 *
0x1400648af  mov     edx, r13d; unsigned int
0x1400648b2  mov     rcx, rdi; unsigned __int16 *
0x1400648b5  mov     ebx, r14d
0x1400648b8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400648bd  call    cs:__imp_IsDebuggerPresent
0x1400648c3  test    eax, eax
0x1400648c5  lea     rax, aPbstrhostname; "*pbstrHostName"
0x1400648cc  jmp     loc_1400647AE
0x1400648d1  mov     dword ptr [rsp+88h+var_58], r14d
0x1400648d6  mov     r8d, r13d
0x1400648d9  mov     qword ptr [rsp+88h+var_60], rax
0x1400648de  mov     [rsp+88h+var_68], r15
0x1400648e3  mov     r9, rsi
0x1400648e6  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400648ed  mov     rdx, rdi
0x1400648f0  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400648f5  mov     rcx, rbp; Block
0x1400648f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400648fd  mov     eax, ebx
0x1400648ff  add     rsp, 48h
0x140064903  pop     r15
0x140064905  pop     r14
0x140064907  pop     r13
0x140064909  pop     r12
0x14006490b  pop     rdi
0x14006490c  pop     rsi
0x14006490d  pop     rbp
0x14006490e  pop     rbx
0x14006490f  retn
```
