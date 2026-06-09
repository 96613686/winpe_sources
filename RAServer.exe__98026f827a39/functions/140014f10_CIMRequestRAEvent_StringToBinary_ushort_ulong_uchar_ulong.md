# CIMRequestRAEvent::StringToBinary(ushort *,ulong,uchar * *,ulong *)

- ea: `0x140014f10`
- end: `0x140015019`
- name: `?StringToBinary@CIMRequestRAEvent@@QEAAJPEAGKPEAPEAEPEAK@Z`
- size: `265`
- prototype: `__int64 __fastcall(CIMRequestRAEvent *this, unsigned __int16 *, DWORD, unsigned __int8 **, unsigned int *pcbBinary)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140013c10`
- `0x140013ef8`

## callees

- `0x140014f10`
- `0x140015240`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140014f72`
- `KERNEL32!GetLastError` at `0x140014fcb`
- `KERNEL32!GetLastError` at `0x140014f72`
- `KERNEL32!GetLastError` at `0x140014fcb`
- `msvcrt!malloc` at `0x140014f93`
- `msvcrt!malloc` at `0x140014f93`
- `CRYPT32!CryptStringToBinaryW` at `0x140014f68`
- `CRYPT32!CryptStringToBinaryW` at `0x140014fc1`
- `CRYPT32!CryptStringToBinaryW` at `0x140014f68`
- `CRYPT32!CryptStringToBinaryW` at `0x140014fc1`

## string_xrefs

- `0x140014ff1`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRAEvent::StringToBinary(
        CIMRequestRAEvent *this,
        unsigned __int16 *a2,
        DWORD a3,
        unsigned __int8 **a4,
        unsigned int *pcbBinary)
{
  DWORD *v5; // rdi
  signed int LastError; // eax
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  CEventLogger *v11; // rcx
  unsigned int v12; // ebx
  unsigned int v13; // r9d
  unsigned __int8 *v14; // rax
  signed int v15; // eax
  DWORD pdwSkip[4]; // [rsp+40h] [rbp-28h] BYREF
  DWORD pdwFlags; // [rsp+70h] [rbp+8h] BYREF
  int v19; // [rsp+74h] [rbp+Ch]

  v19 = HIDWORD(this);
  v5 = pcbBinary;
  pdwSkip[0] = 0;
  pdwFlags = 0;
  if ( !CryptStringToBinaryW(a2, a3, 1u, 0, pcbBinary, pdwSkip, &pdwFlags) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    v13 = 457;
LABEL_9:
    CEventLogger::LogError(
      v11,
      v10,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      v13,
      L"CIMRequestRAEvent::StringToBinary",
      v12);
    return v12;
  }
  v12 = 0;
  v14 = (unsigned __int8 *)malloc(*v5);
  *a4 = v14;
  if ( !CryptStringToBinaryW(a2, a3, 1u, v14, v5, pdwSkip, &pdwFlags) )
  {
    v15 = GetLastError();
    v12 = v15;
    if ( v15 > 0 )
      v12 = (unsigned __int16)v15 | 0x80070000;
    v13 = 474;
    goto LABEL_9;
  }
  return v12;
}

```

## disassembly

```asm
0x140014f10  mov     r11, rsp
0x140014f13  mov     [r11+10h], rbx
0x140014f17  mov     [r11+18h], rbp
0x140014f1b  mov     [r11+8], rcx
0x140014f1f  push    rsi
0x140014f20  push    rdi
0x140014f21  push    r14
0x140014f23  sub     rsp, 50h
0x140014f27  mov     rdi, [rsp+68h+arg_20]
0x140014f2f  lea     rax, [r11+8]
0x140014f33  mov     [r11-38h], rax
0x140014f37  mov     esi, r8d
0x140014f3a  mov     rbp, rdx
0x140014f3d  mov     [rsp+68h+var_28], 0
0x140014f45  mov     r14, r9
0x140014f48  mov     [rsp+68h+arg_0], 0
0x140014f50  xor     r9d, r9d; pbBinary
0x140014f53  lea     rax, [r11-28h]
0x140014f57  mov     [r11-40h], rax
0x140014f5b  mov     edx, esi; cchString
0x140014f5d  mov     rcx, rbp; pszString
0x140014f60  mov     [r11-48h], rdi
0x140014f64  lea     r8d, [r9+1]; dwFlags
0x140014f68  call    cs:__imp_CryptStringToBinaryW
0x140014f6e  test    eax, eax
0x140014f70  jnz     short loc_140014F8F
0x140014f72  call    cs:__imp_GetLastError
0x140014f78  mov     ebx, eax
0x140014f7a  test    eax, eax
0x140014f7c  jle     short loc_140014F87
0x140014f7e  movzx   ebx, ax
0x140014f81  or      ebx, 80070000h
0x140014f87  mov     r9d, 1C9h
0x140014f8d  jmp     short loc_140014FE6
0x140014f8f  mov     ecx, [rdi]; Size
0x140014f91  xor     ebx, ebx
0x140014f93  call    cs:__imp_malloc
0x140014f99  lea     rcx, [rsp+68h+arg_0]
0x140014f9e  mov     edx, esi; cchString
0x140014fa0  lea     r8d, [rbx+1]; dwFlags
0x140014fa4  mov     [r14], rax
0x140014fa7  mov     [rsp+68h+pdwFlags], rcx; pdwFlags
0x140014fac  mov     r9, rax; pbBinary
0x140014faf  lea     rcx, [rsp+68h+var_28]
0x140014fb4  mov     [rsp+68h+pdwSkip], rcx; pdwSkip
0x140014fb9  mov     rcx, rbp; pszString
0x140014fbc  mov     [rsp+68h+pcbBinary], rdi; pcbBinary
0x140014fc1  call    cs:__imp_CryptStringToBinaryW
0x140014fc7  test    eax, eax
0x140014fc9  jnz     short loc_140015002
0x140014fcb  call    cs:__imp_GetLastError
0x140014fd1  mov     ebx, eax
0x140014fd3  test    eax, eax
0x140014fd5  jle     short loc_140014FE0
0x140014fd7  movzx   ebx, ax
0x140014fda  or      ebx, 80070000h
0x140014fe0  mov     r9d, 1DAh; unsigned int
0x140014fe6  lea     rax, aCimrequestraev_9; "CIMRequestRAEvent::StringToBinary"
0x140014fed  mov     dword ptr [rsp+68h+pdwSkip], ebx; unsigned int
0x140014ff1  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x140014ff8  mov     [rsp+68h+pcbBinary], rax; unsigned __int16 *
0x140014ffd  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140015002  lea     r11, [rsp+68h+var_18]
0x140015007  mov     eax, ebx
0x140015009  mov     rbx, [r11+28h]
0x14001500d  mov     rbp, [r11+30h]
0x140015011  mov     rsp, r11
0x140015014  pop     r14
0x140015016  pop     rdi
0x140015017  pop     rsi
0x140015018  retn
```
