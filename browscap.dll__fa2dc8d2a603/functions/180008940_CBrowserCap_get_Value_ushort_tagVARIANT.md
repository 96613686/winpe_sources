# CBrowserCap::get_Value(ushort *,tagVARIANT *)

- ea: `0x180008940`
- end: `0x180008abd`
- name: `?get_Value@CBrowserCap@@UEAAJPEAGPEAUtagVARIANT@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(CBrowserCap *this, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002498`
- `0x18000888c`
- `0x180008940`
- `0x180009ab4`
- `0x18000b640`
- `0x18000b700`

## import_xrefs

- `msvcrt!_strlwr` at `0x180008a30`
- `msvcrt!_strlwr` at `0x180008a30`
- `KERNEL32!WideCharToMultiByte` at `0x180008a1d`
- `KERNEL32!WideCharToMultiByte` at `0x180008a1d`
- `KERNEL32!LeaveCriticalSection` at `0x180008a98`
- `KERNEL32!LeaveCriticalSection` at `0x180008a98`
- `KERNEL32!EnterCriticalSection` at `0x1800089a4`
- `KERNEL32!EnterCriticalSection` at `0x1800089a4`
- `OLEAUT32!__imp_SysAllocString` at `0x180008982`
- `OLEAUT32!__imp_SysAllocString` at `0x180008a6d`
- `OLEAUT32!__imp_SysAllocString` at `0x180008982`
- `OLEAUT32!__imp_SysAllocString` at `0x180008a6d`
- `OLEAUT32!__imp_VariantCopy` at `0x180008a8d`
- `OLEAUT32!__imp_VariantCopy` at `0x180008a8d`

## pseudocode

```c
__int64 __fastcall CBrowserCap::get_Value(CBrowserCap *this, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  BSTR v6; // rax
  struct _RTL_CRITICAL_SECTION *v8; // r14
  __int64 v9; // rax
  int v10; // edx
  unsigned __int64 v11; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  void *v14; // rsp
  void *v15; // rsp
  char *v16; // rcx
  char *v17; // rax
  bool v18; // r8
  __int64 v19; // rdi
  BSTR v20; // rax
  unsigned int v21; // ebx
  __int64 v22; // [rsp+0h] [rbp-40h] BYREF
  CHAR MultiByteStr[16]; // [rsp+40h] [rbp+0h] BYREF

  if ( a2 )
  {
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    v10 = v9 + 1;
    if ( (int)v9 + 1 > 0x3FFFFFFF )
      goto LABEL_10;
    v11 = 2LL * (int)v9 + 2;
    v12 = v11 + 15;
    if ( v11 + 15 < v11 )
      v12 = 0xFFFFFFFFFFFFFF0LL;
    v13 = v12 & 0xFFFFFFFFFFFFFFF0uLL;
    v14 = alloca(v13);
    v15 = alloca(v13);
    if ( &v22 == (__int64 *)-64LL )
    {
LABEL_10:
      v16 = 0;
    }
    else
    {
      MultiByteStr[0] = 0;
      v16 = (char *)((unsigned __int64)MultiByteStr
                   & -(__int64)(WideCharToMultiByte(3u, 0, a2, -1, MultiByteStr, 2 * v10, 0, 0) != 0));
    }
    v17 = _strlwr(v16);
    String::String((String *)MultiByteStr, v17, v18);
    v19 = TStringMap<ATL::CComVariant>::find((char *)this + 72, MultiByteStr);
    TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(MultiByteStr);
    if ( v19 == *((_QWORD *)this + 11) )
    {
      a3->vt = 8;
      v20 = SysAllocString(L"unknown");
      a3->llVal = (LONGLONG)v20;
      v21 = v20 == 0 ? 0x8007000E : 0;
    }
    else
    {
      v21 = VariantCopy(a3, (const VARIANTARG *)(v19 + 16));
    }
    LeaveCriticalSection(v8);
    return v21;
  }
  else
  {
    a3->vt = 8;
    v6 = SysAllocString(L"unknown");
    a3->llVal = (LONGLONG)v6;
    return v6 == 0 ? 0x8007000E : 0;
  }
}

```

## disassembly

```asm
0x180008940  push    rbp
0x180008942  push    rbx
0x180008943  push    rsi
0x180008944  push    rdi
0x180008945  push    r12
0x180008947  push    r13
0x180008949  push    r14
0x18000894b  push    r15
0x18000894d  sub     rsp, 68h
0x180008951  lea     rbp, [rsp+40h]
0x180008956  mov     rax, cs:__security_cookie
0x18000895d  xor     rax, rbp
0x180008960  mov     [rbp+60h+var_50], rax
0x180008964  xor     r13d, r13d
0x180008967  mov     rbx, r8
0x18000896a  mov     rdi, rdx
0x18000896d  mov     r15, rcx
0x180008970  test    rdx, rdx
0x180008973  jnz     short loc_18000899D
0x180008975  lea     rcx, aUnknown; "unknown"
0x18000897c  mov     word ptr [r8], 8
0x180008982  call    cs:__imp_SysAllocString
0x180008988  mov     [rbx+8], rax
0x18000898c  neg     rax
0x18000898f  sbb     eax, eax
0x180008991  not     eax
0x180008993  and     eax, 8007000Eh
0x180008998  jmp     loc_180008AA0
0x18000899d  lea     r14, [rcx+60h]
0x1800089a1  mov     rcx, r14; lpCriticalSection
0x1800089a4  call    cs:__imp_EnterCriticalSection
0x1800089aa  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800089ae  mov     rax, r9
0x1800089b1  inc     rax
0x1800089b4  cmp     [rdi+rax*2], r13w
0x1800089b9  jnz     short loc_1800089B1
0x1800089bb  lea     edx, [rax+1]
0x1800089be  cmp     edx, 3FFFFFFFh
0x1800089c4  jg      short loc_180008A2D
0x1800089c6  cdqe
0x1800089c8  lea     rax, ds:2[rax*2]
0x1800089d0  lea     rcx, [rax+0Fh]
0x1800089d4  cmp     rcx, rax
0x1800089d7  ja      short loc_1800089E3
0x1800089d9  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800089e3  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800089e7  mov     rax, rcx
0x1800089ea  call    _alloca_probe
0x1800089ef  sub     rsp, rcx
0x1800089f2  lea     rsi, [rsp+0A0h+MultiByteStr]
0x1800089f7  test    rsi, rsi
0x1800089fa  jz      short loc_180008A2D
0x1800089fc  lea     eax, [rdx+rdx]
0x1800089ff  mov     [rsp+0A0h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180008a04  xor     edx, edx; dwFlags
0x180008a06  mov     [rsp+0A0h+lpDefaultChar], r13; lpDefaultChar
0x180008a0b  mov     [rsp+0A0h+cbMultiByte], eax; cbMultiByte
0x180008a0f  mov     r8, rdi; lpWideCharStr
0x180008a12  mov     [rsi], r13b
0x180008a15  mov     [rsp+0A0h+lpMultiByteStr], rsi; lpMultiByteStr
0x180008a1a  lea     ecx, [rdx+3]; CodePage
0x180008a1d  call    cs:__imp_WideCharToMultiByte
0x180008a23  neg     eax
0x180008a25  sbb     rcx, rcx
0x180008a28  and     rcx, rsi
0x180008a2b  jmp     short loc_180008A30
0x180008a2d  mov     rcx, r13; String
0x180008a30  call    cs:__imp__strlwr
0x180008a36  mov     rdx, rax; char *
0x180008a39  lea     rcx, [rbp+60h+MultiByteStr]; this
0x180008a3d  call    ??0String@@QEAA@PEBD_N@Z; String::String(char const *,bool)
0x180008a42  lea     rdx, [rbp+60h+MultiByteStr]
0x180008a46  lea     rcx, [r15+48h]
0x180008a4a  call    ?find@?$TStringMap@VCComVariant@ATL@@@@QEAAPEAU?$pair@VString@@VCComVariant@ATL@@@std@@AEBVString@@@Z; TStringMap<ATL::CComVariant>::find(String const &)
0x180008a4f  lea     rcx, [rbp+60h+MultiByteStr]
0x180008a53  mov     rdi, rax
0x180008a56  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x180008a5b  cmp     rdi, [r15+58h]
0x180008a5f  jnz     short loc_180008A86
0x180008a61  lea     rcx, aUnknown; "unknown"
0x180008a68  mov     word ptr [rbx], 8
0x180008a6d  call    cs:__imp_SysAllocString
0x180008a73  mov     [rbx+8], rax
0x180008a77  neg     rax
0x180008a7a  sbb     ebx, ebx
0x180008a7c  not     ebx
0x180008a7e  and     ebx, 8007000Eh
0x180008a84  jmp     short loc_180008A95
0x180008a86  lea     rdx, [rdi+10h]; pvargSrc
0x180008a8a  mov     rcx, rbx; pvargDest
0x180008a8d  call    cs:__imp_VariantCopy
0x180008a93  mov     ebx, eax
0x180008a95  mov     rcx, r14; lpCriticalSection
0x180008a98  call    cs:__imp_LeaveCriticalSection
0x180008a9e  mov     eax, ebx
0x180008aa0  mov     rcx, [rbp+60h+var_50]
0x180008aa4  xor     rcx, rbp; StackCookie
0x180008aa7  call    __security_check_cookie
0x180008aac  lea     rsp, [rbp+28h]
0x180008ab0  pop     r15
0x180008ab2  pop     r14
0x180008ab4  pop     r13
0x180008ab6  pop     r12
0x180008ab8  pop     rdi
0x180008ab9  pop     rsi
0x180008aba  pop     rbx
0x180008abb  pop     rbp
0x180008abc  retn
```
