# oCompareString

- ea: `0x180211abc`
- end: `0x180211dd2`
- name: `oCompareString`
- size: `790`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18010206c`
- `0x1801272b4`
- `0x18013362c`
- `0x180133b00`
- `0x1801a75ac`
- `0x1801dca38`
- `0x180254468`
- `0x18029df04`
- `0x18029e5c4`
- `0x1802cb098`
- `0x1802cb2e0`
- `0x1802cb4a0`
- `0x180302c0c`

## callees

- `0x180142894`
- `0x180142948`
- `0x180211abc`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180211cef`
- `KERNEL32!SetLastError` at `0x180211d8f`
- `KERNEL32!SetLastError` at `0x180211cef`
- `KERNEL32!SetLastError` at `0x180211d8f`
- `KERNEL32!RaiseException` at `0x180211b54`
- `KERNEL32!RaiseException` at `0x180211b9a`
- `KERNEL32!RaiseException` at `0x180211b54`
- `KERNEL32!RaiseException` at `0x180211b9a`
- `KERNEL32!CompareStringA` at `0x180211d6c`
- `KERNEL32!CompareStringA` at `0x180211d6c`
- `KERNEL32!WideCharToMultiByte` at `0x180211d1c`
- `KERNEL32!WideCharToMultiByte` at `0x180211d48`
- `KERNEL32!WideCharToMultiByte` at `0x180211d1c`
- `KERNEL32!WideCharToMultiByte` at `0x180211d48`
- `KERNEL32!VirtualQuery` at `0x180211bd3`
- `KERNEL32!VirtualQuery` at `0x180211c6b`
- `KERNEL32!VirtualQuery` at `0x180211bd3`
- `KERNEL32!VirtualQuery` at `0x180211c6b`
- `KERNEL32!CompareStringW` at `0x180211dab`
- `KERNEL32!CompareStringW` at `0x180211dab`

## pseudocode

```c
int __fastcall oCompareString(LCID a1, DWORD a2, const WCHAR *a3, int a4, const WCHAR *lpString2, int cchWideChar)
{
  LPCWCH v7; // rdx
  int v8; // ebx
  __int64 v11; // rdi
  __int64 v12; // rcx
  unsigned int v13; // esi
  __int64 AllocationBase; // rax
  unsigned int v15; // r12d
  unsigned __int64 v16; // rax
  void *v17; // rsp
  CHAR *lpMultiByteStr; // rsi
  __int64 v19; // rax
  unsigned __int64 v20; // rax
  void *v21; // rsp
  CHAR *v22; // rdi
  int v23; // r14d
  int v24; // eax
  CHAR MultiByteStr[4]; // [rsp+40h] [rbp+0h] BYREF
  _BYTE Address[4]; // [rsp+44h] [rbp+4h] BYREF
  int cbMultiByte; // [rsp+48h] [rbp+8h]
  DWORD dwCmpFlags; // [rsp+4Ch] [rbp+Ch]
  unsigned __int64 v30; // [rsp+50h] [rbp+10h] BYREF
  unsigned __int64 v31; // [rsp+58h] [rbp+18h] BYREF
  LPCWCH lpWideCharStr; // [rsp+60h] [rbp+20h]
  _BYTE v33[8]; // [rsp+68h] [rbp+28h] BYREF
  CHAR *v34; // [rsp+70h] [rbp+30h]
  _BYTE v35[8]; // [rsp+80h] [rbp+40h] BYREF
  CHAR *v36; // [rsp+88h] [rbp+48h]
  struct _MEMORY_BASIC_INFORMATION Buffer; // [rsp+98h] [rbp+58h] BYREF
  char v38[256]; // [rsp+D0h] [rbp+90h] BYREF
  char v39[256]; // [rsp+1D0h] [rbp+190h] BYREF

  dwCmpFlags = a2;
  v7 = lpString2;
  v8 = 0;
  lpWideCharStr = lpString2;
  *(_DWORD *)MultiByteStr = a1;
  if ( !g_fChicago )
    return CompareStringW(a1, a2, a3, a4, lpString2, cchWideChar);
  if ( a4 && cchWideChar )
  {
    v11 = -1;
    if ( a4 == -1 )
    {
      v12 = -1;
      do
        ++v12;
      while ( a3[v12] );
      if ( (unsigned int)v12 != v12 )
      {
        RaiseException(0xC0000095, 1u, 1u, (const ULONG_PTR *)v12);
        LODWORD(v12) = *(_DWORD *)MultiByteStr;
        v7 = lpWideCharStr;
      }
    }
    else
    {
      LODWORD(v12) = a4;
    }
    v13 = 2 * v12 + 1;
    cbMultiByte = v13;
    if ( cchWideChar == -1 )
    {
      do
        ++v11;
      while ( v7[v11] );
      if ( (unsigned int)v11 != v11 )
      {
        RaiseException(0xC0000095, 1u, 1u, (const ULONG_PTR *)v11);
        LODWORD(v11) = *(_DWORD *)MultiByteStr;
      }
    }
    else
    {
      LODWORD(v11) = cchWideChar;
    }
    AllocationBase = `StackAvailable'::`2'::pvStackBottom;
    v15 = 2 * v11 + 1;
    v31 = 0;
    if ( !`StackAvailable'::`2'::pvStackBottom )
    {
      VirtualQuery(Address, &Buffer, 0x30u);
      AllocationBase = (__int64)Buffer.AllocationBase;
      `StackAvailable'::`2'::pvStackBottom = (__int64)Buffer.AllocationBase;
    }
    TempBufferEx::TempBufferEx(
      (TempBufferEx *)v33,
      0x100u,
      (unsigned __int64)&Address[-AllocationBase - 128],
      v13,
      v38,
      &v31,
      1u);
    if ( v31 )
    {
      v16 = v31 + 15;
      if ( v31 + 15 < v31 )
        v16 = 0xFFFFFFFFFFFFFF0LL;
      v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
      lpMultiByteStr = MultiByteStr;
    }
    else
    {
      lpMultiByteStr = v34;
    }
    v19 = `StackAvailable'::`2'::pvStackBottom;
    v30 = 0;
    if ( !`StackAvailable'::`2'::pvStackBottom )
    {
      VirtualQuery(Address, &Buffer, 0x30u);
      v19 = (__int64)Buffer.AllocationBase;
      `StackAvailable'::`2'::pvStackBottom = (__int64)Buffer.AllocationBase;
    }
    TempBufferEx::TempBufferEx((TempBufferEx *)v35, 0x100u, (unsigned __int64)&Address[-v19 - 128], v15, v39, &v30, 1u);
    if ( v30 )
    {
      v20 = v30 + 15;
      if ( v30 + 15 < v30 )
        v20 = 0xFFFFFFFFFFFFFF0LL;
      v21 = alloca(v20 & 0xFFFFFFFFFFFFFFF0uLL);
      v22 = MultiByteStr;
    }
    else
    {
      v22 = v36;
    }
    if ( lpMultiByteStr && v22 )
    {
      v23 = WideCharToMultiByte(0, 0, a3, a4, lpMultiByteStr, cbMultiByte, 0, 0);
      v24 = WideCharToMultiByte(0, 0, lpWideCharStr, cchWideChar, v22, v15, 0, 0);
      if ( v23 )
      {
        if ( v24 )
          v8 = CompareStringA(*(LCID *)MultiByteStr, dwCmpFlags, lpMultiByteStr, v23, v22, v24);
      }
    }
    else
    {
      SetLastError(0xEu);
    }
    TempBufferEx::~TempBufferEx((TempBufferEx *)v35);
    TempBufferEx::~TempBufferEx((TempBufferEx *)v33);
    return v8;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x180211abc  push    rbp
0x180211abe  push    rbx
0x180211abf  push    rsi
0x180211ac0  push    rdi
0x180211ac1  push    r12
0x180211ac3  push    r13
0x180211ac5  push    r14
0x180211ac7  sub     rsp, 2E0h
0x180211ace  lea     rbp, [rsp+40h]
0x180211ad3  mov     rax, cs:__security_cookie
0x180211ada  xor     rax, rbp
0x180211add  mov     [rbp+2D0h+var_40], rax
0x180211ae4  mov     r10d, edx
0x180211ae7  mov     [rbp+2D0h+dwCmpFlags], edx
0x180211aea  mov     rdx, [rbp+2D0h+lpString2]
0x180211af1  xor     ebx, ebx
0x180211af3  mov     r14d, r9d
0x180211af6  mov     r13, r8
0x180211af9  cmp     cs:g_fChicago, ebx
0x180211aff  mov     [rbp+2D0h+lpWideCharStr], rdx
0x180211b03  mov     dword ptr [rbp+2D0h+MultiByteStr], ecx
0x180211b06  jz      loc_180211D99
0x180211b0c  test    r9d, r9d
0x180211b0f  jz      loc_180211D8A
0x180211b15  cmp     [rbp+2D0h+cchWideChar], ebx
0x180211b1b  jz      loc_180211D8A
0x180211b21  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180211b25  lea     r10d, [rbx+1]
0x180211b29  mov     r12d, 0C0000095h
0x180211b2f  cmp     r9d, edi
0x180211b32  jnz     short loc_180211B69
0x180211b34  mov     rcx, rdi
0x180211b37  inc     rcx
0x180211b3a  cmp     [r8+rcx*2], bx
0x180211b3f  jnz     short loc_180211B37
0x180211b41  mov     eax, ecx
0x180211b43  cmp     rax, rcx
0x180211b46  jz      short loc_180211B6C
0x180211b48  mov     r9, rcx; lpArguments
0x180211b4b  mov     r8d, r10d; nNumberOfArguments
0x180211b4e  mov     edx, r10d; dwExceptionFlags
0x180211b51  mov     ecx, r12d; dwExceptionCode
0x180211b54  call    cs:__imp_RaiseException
0x180211b5a  mov     ecx, dword ptr [rbp+2D0h+MultiByteStr]
0x180211b5d  mov     rdx, [rbp+2D0h+lpWideCharStr]
0x180211b61  mov     r10d, 1
0x180211b67  jmp     short loc_180211B6C
0x180211b69  mov     ecx, r9d
0x180211b6c  lea     esi, ds:1[rcx*2]
0x180211b73  mov     [rbp+2D0h+var_2C8], esi
0x180211b76  cmp     [rbp+2D0h+cchWideChar], edi
0x180211b7c  jnz     short loc_180211BA5
0x180211b7e  inc     rdi
0x180211b81  cmp     [rdx+rdi*2], bx
0x180211b85  jnz     short loc_180211B7E
0x180211b87  mov     eax, edi
0x180211b89  cmp     rax, rdi
0x180211b8c  jz      short loc_180211BAB
0x180211b8e  mov     r9, rdi; lpArguments
0x180211b91  mov     r8d, r10d; nNumberOfArguments
0x180211b94  mov     edx, r10d; dwExceptionFlags
0x180211b97  mov     ecx, r12d; dwExceptionCode
0x180211b9a  call    cs:__imp_RaiseException
0x180211ba0  mov     edi, dword ptr [rbp+2D0h+MultiByteStr]
0x180211ba3  jmp     short loc_180211BAB
0x180211ba5  mov     edi, [rbp+2D0h+cchWideChar]
0x180211bab  mov     rax, cs:?pvStackBottom@?1??StackAvailable@@YA_KXZ@4PEAXEA; void * `StackAvailable(void)'::`2'::pvStackBottom
0x180211bb2  lea     r12d, ds:1[rdi*2]
0x180211bba  mov     [rbp+2D0h+var_2B8], rbx
0x180211bbe  mov     edi, 30h ; '0'
0x180211bc3  test    rax, rax
0x180211bc6  jnz     short loc_180211BE4
0x180211bc8  lea     rdx, [rbp+2D0h+Buffer]; lpBuffer
0x180211bcc  lea     rcx, [rbp+2D0h+Address]; lpAddress
0x180211bd0  mov     r8d, edi; dwLength
0x180211bd3  call    cs:__imp_VirtualQuery
0x180211bd9  mov     rax, [rbp+2D0h+Buffer.AllocationBase]
0x180211bdd  mov     cs:?pvStackBottom@?1??StackAvailable@@YA_KXZ@4PEAXEA, rax; void * `StackAvailable(void)'::`2'::pvStackBottom
0x180211be4  mov     byte ptr [rsp+310h+lpDefaultChar], 1; unsigned __int8
0x180211be9  lea     r8, [rbp+2D0h+Address]
0x180211bed  lea     rcx, [rbp+2D0h+var_2A8]; this
0x180211bf1  sub     r8, rax
0x180211bf4  lea     rax, [rbp+2D0h+var_2B8]
0x180211bf8  mov     r9d, esi; unsigned __int64
0x180211bfb  mov     qword ptr [rsp+310h+cbMultiByte], rax; unsigned __int64 *
0x180211c00  lea     rax, [rbp+2D0h+var_240]
0x180211c07  add     r8, 0FFFFFFFFFFFFFF80h; unsigned __int64
0x180211c0b  mov     edx, 100h; unsigned __int64
0x180211c10  mov     [rsp+310h+lpMultiByteStr], rax; char *
0x180211c15  call    ??0TempBufferEx@@QEAA@_K00PEADPEA_KE@Z; TempBufferEx::TempBufferEx(unsigned __int64,unsigned __int64,unsigned __int64,char *,unsigned __int64 *,uchar)
0x180211c1a  mov     rcx, [rbp+2D0h+var_2B8]
0x180211c1e  mov     rdx, 0FFFFFFFFFFFFFF0h
0x180211c28  test    rcx, rcx
0x180211c2b  jz      short loc_180211C4C
0x180211c2d  lea     rax, [rcx+0Fh]
0x180211c31  cmp     rax, rcx
0x180211c34  ja      short loc_180211C39
0x180211c36  mov     rax, rdx
0x180211c39  and     rax, 0FFFFFFFFFFFFFFF0h
0x180211c3d  call    _alloca_probe
0x180211c42  sub     rsp, rax
0x180211c45  lea     rsi, [rsp+310h+MultiByteStr]
0x180211c4a  jmp     short loc_180211C50
0x180211c4c  mov     rsi, [rbp+2D0h+var_2A0]
0x180211c50  mov     rax, cs:?pvStackBottom@?1??StackAvailable@@YA_KXZ@4PEAXEA; void * `StackAvailable(void)'::`2'::pvStackBottom
0x180211c57  mov     [rbp+2D0h+var_2C0], rbx
0x180211c5b  test    rax, rax
0x180211c5e  jnz     short loc_180211C7C
0x180211c60  lea     rdx, [rbp+2D0h+Buffer]; lpBuffer
0x180211c64  lea     rcx, [rbp+2D0h+Address]; lpAddress
0x180211c68  mov     r8, rdi; dwLength
0x180211c6b  call    cs:__imp_VirtualQuery
0x180211c71  mov     rax, [rbp+2D0h+Buffer.AllocationBase]
0x180211c75  mov     cs:?pvStackBottom@?1??StackAvailable@@YA_KXZ@4PEAXEA, rax; void * `StackAvailable(void)'::`2'::pvStackBottom
0x180211c7c  mov     byte ptr [rsp+310h+lpDefaultChar], 1; unsigned __int8
0x180211c81  lea     r8, [rbp+2D0h+Address]
0x180211c85  lea     rcx, [rbp+2D0h+var_290]; this
0x180211c89  sub     r8, rax
0x180211c8c  lea     rax, [rbp+2D0h+var_2C0]
0x180211c90  mov     r9d, r12d; unsigned __int64
0x180211c93  mov     qword ptr [rsp+310h+cbMultiByte], rax; unsigned __int64 *
0x180211c98  lea     rax, [rbp+2D0h+var_140]
0x180211c9f  add     r8, 0FFFFFFFFFFFFFF80h; unsigned __int64
0x180211ca3  mov     edx, 100h; unsigned __int64
0x180211ca8  mov     [rsp+310h+lpMultiByteStr], rax; char *
0x180211cad  call    ??0TempBufferEx@@QEAA@_K00PEADPEA_KE@Z; TempBufferEx::TempBufferEx(unsigned __int64,unsigned __int64,unsigned __int64,char *,unsigned __int64 *,uchar)
0x180211cb2  mov     r11, [rbp+2D0h+var_2C0]
0x180211cb6  test    r11, r11
0x180211cb9  jz      short loc_180211CE1
0x180211cbb  lea     rax, [r11+0Fh]
0x180211cbf  cmp     rax, r11
0x180211cc2  ja      short loc_180211CCE
0x180211cc4  mov     rax, 0FFFFFFFFFFFFFF0h
0x180211cce  and     rax, 0FFFFFFFFFFFFFFF0h
0x180211cd2  call    _alloca_probe
0x180211cd7  sub     rsp, rax
0x180211cda  lea     rdi, [rsp+310h+MultiByteStr]
0x180211cdf  jmp     short loc_180211CE5
0x180211ce1  mov     rdi, [rbp+2D0h+var_288]
0x180211ce5  test    rsi, rsi
0x180211ce8  jnz     short loc_180211CF7
0x180211cea  mov     ecx, 0Eh; dwErrCode
0x180211cef  call    cs:__imp_SetLastError
0x180211cf5  jmp     short loc_180211D74
0x180211cf7  test    rdi, rdi
0x180211cfa  jz      short loc_180211CEA
0x180211cfc  mov     eax, [rbp+2D0h+var_2C8]
0x180211cff  mov     [rsp+310h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x180211d04  mov     [rsp+310h+lpDefaultChar], rbx; lpDefaultChar
0x180211d09  mov     [rsp+310h+cbMultiByte], eax; cbMultiByte
0x180211d0d  mov     r9d, r14d; cchWideChar
0x180211d10  mov     r8, r13; lpWideCharStr
0x180211d13  xor     edx, edx; dwFlags
0x180211d15  xor     ecx, ecx; CodePage
0x180211d17  mov     [rsp+310h+lpMultiByteStr], rsi; lpMultiByteStr
0x180211d1c  call    cs:__imp_WideCharToMultiByte
0x180211d22  mov     r9d, [rbp+2D0h+cchWideChar]; cchWideChar
0x180211d29  mov     r8, [rbp+2D0h+lpWideCharStr]; lpWideCharStr
0x180211d2d  mov     [rsp+310h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x180211d32  mov     [rsp+310h+lpDefaultChar], rbx; lpDefaultChar
0x180211d37  xor     edx, edx; dwFlags
0x180211d39  xor     ecx, ecx; CodePage
0x180211d3b  mov     [rsp+310h+cbMultiByte], r12d; cbMultiByte
0x180211d40  mov     r14d, eax
0x180211d43  mov     [rsp+310h+lpMultiByteStr], rdi; lpMultiByteStr
0x180211d48  call    cs:__imp_WideCharToMultiByte
0x180211d4e  test    r14d, r14d
0x180211d51  jz      short loc_180211D74
0x180211d53  test    eax, eax
0x180211d55  jz      short loc_180211D74
0x180211d57  mov     edx, [rbp+2D0h+dwCmpFlags]; dwCmpFlags
0x180211d5a  mov     ecx, dword ptr [rbp+2D0h+MultiByteStr]; Locale
0x180211d5d  mov     [rsp+310h+cbMultiByte], eax; cchCount2
0x180211d61  mov     r9d, r14d; cchCount1
0x180211d64  mov     r8, rsi; lpString1
0x180211d67  mov     [rsp+310h+lpMultiByteStr], rdi; lpString2
0x180211d6c  call    cs:__imp_CompareStringA
0x180211d72  mov     ebx, eax
0x180211d74  lea     rcx, [rbp+2D0h+var_290]; this
0x180211d78  call    ??1TempBufferEx@@QEAA@XZ; TempBufferEx::~TempBufferEx(void)
0x180211d7d  lea     rcx, [rbp+2D0h+var_2A8]; this
0x180211d81  call    ??1TempBufferEx@@QEAA@XZ; TempBufferEx::~TempBufferEx(void)
0x180211d86  mov     eax, ebx
0x180211d88  jmp     short loc_180211DB1
0x180211d8a  mov     ecx, 57h ; 'W'; dwErrCode
0x180211d8f  call    cs:__imp_SetLastError
0x180211d95  xor     eax, eax
0x180211d97  jmp     short loc_180211DB1
0x180211d99  mov     eax, [rbp+2D0h+cchWideChar]
0x180211d9f  mov     [rsp+310h+cbMultiByte], eax; cchCount2
0x180211da3  mov     [rsp+310h+lpMultiByteStr], rdx; lpString2
0x180211da8  mov     edx, r10d; dwCmpFlags
0x180211dab  call    cs:__imp_CompareStringW
0x180211db1  mov     rcx, [rbp+2D0h+var_40]
0x180211db8  xor     rcx, rbp; StackCookie
0x180211dbb  call    __security_check_cookie
0x180211dc0  lea     rsp, [rbp+2A0h]
0x180211dc7  pop     r14
0x180211dc9  pop     r13
0x180211dcb  pop     r12
0x180211dcd  pop     rdi
0x180211dce  pop     rsi
0x180211dcf  pop     rbx
0x180211dd0  pop     rbp
0x180211dd1  retn
```
