# RdVhd::Uvhd::CDirectoryHelper::CreateDirectoryW(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180018b00`
- end: `0x180018bcf`
- name: `?CreateDirectoryW@CDirectoryHelper@Uvhd@RdVhd@@AEBAHPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CDirectoryHelper *this, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004e2a0`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x180018b00`
- `0x180019b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b5f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180018b12`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180018bb0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180018b12`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180018bb0`

## string_xrefs

- `0x180018b89`: `CreateDirectoryW failed for path '%s'. Trying with long path`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CDirectoryHelper::CreateDirectoryW(
        RdVhd::Uvhd::CDirectoryHelper *this,
        const unsigned __int16 *a2,
        struct _SECURITY_ATTRIBUTES *a3)
{
  unsigned int DirectoryW; // ebx
  signed int LastError; // eax
  const WCHAR *v6; // rax
  void **v8; // [rsp+20h] [rbp-38h] BYREF
  int v9; // [rsp+28h] [rbp-30h]
  __int64 v10; // [rsp+2Ch] [rbp-2Ch]
  int v11; // [rsp+34h] [rbp-24h]
  __int64 v12; // [rsp+38h] [rbp-20h]
  int v13; // [rsp+40h] [rbp-18h]

  DirectoryW = CreateDirectoryW(a2, 0);
  if ( !DirectoryW && GetLastError() == 3 )
  {
    v10 = 128;
    v8 = &CPathString::`vftable';
    v12 = 0;
    v11 = 0;
    v13 = 0x8000000;
    v9 = 0;
    LastError = GetLastError();
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LastError = LastError & 0x8000FFFF | 0x50310000;
    }
    _TraceNrmRdvVmEx(L"UVHD", (unsigned int)LastError, L"CreateDirectoryW failed for path '%s'. Trying with long path");
    v6 = RdVhd::Uvhd::CLongPath::TryConvertToLongPath(a2, (struct CPathString *)&v8);
    DirectoryW = CreateDirectoryW(v6, 0);
    CPathString::~CPathString((CPathString *)&v8);
  }
  return DirectoryW;
}

```

## disassembly

```asm
0x180018b00  mov     [rsp+arg_0], rbx
0x180018b05  push    rdi
0x180018b06  sub     rsp, 50h
0x180018b0a  mov     rdi, rdx
0x180018b0d  xor     edx, edx; lpSecurityAttributes
0x180018b0f  mov     rcx, rdi; lpPathName
0x180018b12  call    cs:__imp_CreateDirectoryW
0x180018b18  mov     ebx, eax
0x180018b1a  test    eax, eax
0x180018b1c  jnz     loc_180018BC2
0x180018b22  call    cs:__imp_GetLastError
0x180018b28  cmp     eax, 3
0x180018b2b  jnz     loc_180018BC2
0x180018b31  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180018b38  mov     [rsp+58h+var_2C], 80h
0x180018b41  mov     [rsp+58h+var_38], rax
0x180018b46  mov     [rsp+58h+var_20], 0
0x180018b4f  mov     [rsp+58h+var_24], ebx
0x180018b53  mov     [rsp+58h+var_18], 8000000h
0x180018b5b  mov     [rsp+58h+var_30], ebx
0x180018b5f  call    cs:__imp_GetLastError
0x180018b65  test    eax, eax
0x180018b67  jz      short loc_180018B86
0x180018b69  test    eax, 0FFFF0000h
0x180018b6e  jnz     short loc_180018B86
0x180018b70  test    eax, eax
0x180018b72  jle     short loc_180018B7C
0x180018b74  movzx   eax, ax
0x180018b77  or      eax, 80070000h
0x180018b7c  and     eax, 0D031FFFFh
0x180018b81  or      eax, 50310000h
0x180018b86  mov     r9, rdi
0x180018b89  lea     r8, aCreatedirector_1; "CreateDirectoryW failed for path '%s'. "...
0x180018b90  mov     edx, eax; int
0x180018b92  lea     rcx, aUvhd; "UVHD"
0x180018b99  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180018b9e  lea     rdx, [rsp+58h+var_38]; struct CPathString *
0x180018ba3  mov     rcx, rdi; unsigned __int16 *
0x180018ba6  call    ?TryConvertToLongPath@CLongPath@Uvhd@RdVhd@@SAPEBGPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CLongPath::TryConvertToLongPath(ushort const *,CPathString &)
0x180018bab  mov     rcx, rax; lpPathName
0x180018bae  xor     edx, edx; lpSecurityAttributes
0x180018bb0  call    cs:__imp_CreateDirectoryW
0x180018bb6  lea     rcx, [rsp+58h+var_38]; this
0x180018bbb  mov     ebx, eax
0x180018bbd  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180018bc2  mov     eax, ebx
0x180018bc4  mov     rbx, [rsp+58h+arg_0]
0x180018bc9  add     rsp, 50h
0x180018bcd  pop     rdi
0x180018bce  retn
```
