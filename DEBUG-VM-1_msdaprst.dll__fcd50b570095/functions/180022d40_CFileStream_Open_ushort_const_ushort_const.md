# CFileStream::Open(ushort const *,ushort const *)

- ea: `0x180022d40`
- end: `0x180022e1a`
- name: `?Open@CFileStream@@QEAAJPEBG0@Z`
- size: `218`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, OLECHAR *psz, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180021680`

## callees

- `0x180015370`
- `0x180015f14`
- `0x180020d68`
- `0x180022d40`

## import_xrefs

- `msvcrt!_wfsopen` at `0x180022d7e`
- `msvcrt!_wfsopen` at `0x180022d7e`
- `msvcrt!_get_osfhandle` at `0x180022dc2`
- `msvcrt!_get_osfhandle` at `0x180022dc2`
- `msvcrt!_fileno` at `0x180022dba`
- `msvcrt!_fileno` at `0x180022dba`
- `KERNEL32!GetFileType` at `0x180022dd1`
- `KERNEL32!GetFileType` at `0x180022dd1`
- `KERNEL32!GetLastError` at `0x180022d8d`
- `KERNEL32!GetLastError` at `0x180022d8d`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180022d57`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180022d57`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileStream::Open(CFileStream *this, OLECHAR *psz, const unsigned __int16 *a3)
{
  FILE *v5; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx
  int v8; // eax
  void *osfhandle; // rax
  _BYTE v11[8]; // [rsp+20h] [rbp-28h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-20h] BYREF
  int v13; // [rsp+30h] [rbp-18h]
  __int64 v14; // [rsp+38h] [rbp-10h]

  GetErrorInfo(0, &pperrinfo);
  v13 = 0;
  v14 = 0;
  v5 = _wfsopen(psz, L"rb", 32);
  *((_QWORD *)this + 3) = v5;
  if ( v5 )
  {
    v8 = _fileno(v5);
    osfhandle = (void *)_get_osfhandle(v8);
    if ( osfhandle != (void *)-1LL && GetFileType(osfhandle) == 1 )
    {
      v7 = 0;
      goto LABEL_13;
    }
    CFileStream::Close(this);
LABEL_12:
    v7 = -2147287038;
    CPersistErrorCache::AddInternalError((CPersistErrorCache *)v11, -2147287038, psz, 0x82u);
    goto LABEL_13;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 )
  {
    if ( v7 != -2147024894 )
      goto LABEL_13;
    goto LABEL_12;
  }
  v7 = -2147467259;
LABEL_13:
  CPersistErrorCache::~CPersistErrorCache((CPersistErrorCache *)v11);
  return v7;
}

```

## disassembly

```asm
0x180022d40  mov     [rsp+arg_0], rbx
0x180022d45  push    rdi
0x180022d46  sub     rsp, 40h
0x180022d4a  mov     rdi, rdx
0x180022d4d  mov     rbx, rcx
0x180022d50  lea     rdx, [rsp+48h+pperrinfo]; pperrinfo
0x180022d55  xor     ecx, ecx; dwReserved
0x180022d57  call    cs:__imp_GetErrorInfo
0x180022d5d  mov     [rsp+48h+var_18], 0
0x180022d65  mov     [rsp+48h+var_10], 0
0x180022d6e  mov     r8d, 20h ; ' '; ShFlag
0x180022d74  lea     rdx, aRb; "rb"
0x180022d7b  mov     rcx, rdi; FileName
0x180022d7e  call    cs:__imp__wfsopen
0x180022d84  mov     [rbx+18h], rax
0x180022d88  test    rax, rax
0x180022d8b  jnz     short loc_180022DB7
0x180022d8d  call    cs:__imp_GetLastError
0x180022d93  mov     ebx, eax
0x180022d95  test    eax, eax
0x180022d97  jle     short loc_180022DA2
0x180022d99  movzx   ebx, ax
0x180022d9c  or      ebx, 80070000h
0x180022da2  test    ebx, ebx
0x180022da4  jnz     short loc_180022DAD
0x180022da6  mov     ebx, 80004005h
0x180022dab  jmp     short loc_180022E03
0x180022dad  cmp     ebx, 80070002h
0x180022db3  jz      short loc_180022DE8
0x180022db5  jmp     short loc_180022E03
0x180022db7  mov     rcx, rax; Stream
0x180022dba  call    cs:__imp__fileno
0x180022dc0  mov     ecx, eax; FileHandle
0x180022dc2  call    cs:__imp__get_osfhandle
0x180022dc8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022dcc  jz      short loc_180022DE0
0x180022dce  mov     rcx, rax; hFile
0x180022dd1  call    cs:__imp_GetFileType
0x180022dd7  cmp     eax, 1
0x180022dda  jnz     short loc_180022DE0
0x180022ddc  xor     ebx, ebx
0x180022dde  jmp     short loc_180022E03
0x180022de0  mov     rcx, rbx; this
0x180022de3  call    ?Close@CFileStream@@QEAAXXZ; CFileStream::Close(void)
0x180022de8  mov     ebx, 80030002h
0x180022ded  mov     r9d, 82h; unsigned int
0x180022df3  mov     r8, rdi; psz
0x180022df6  mov     edx, ebx; int
0x180022df8  lea     rcx, [rsp+48h+var_28]; this
0x180022dfd  call    ?AddInternalError@CPersistErrorCache@@QEAAXJPEBGK@Z; CPersistErrorCache::AddInternalError(long,ushort const *,ulong)
0x180022e02  nop
0x180022e03  lea     rcx, [rsp+48h+var_28]; this
0x180022e08  call    ??1CPersistErrorCache@@QEAA@XZ; CPersistErrorCache::~CPersistErrorCache(void)
0x180022e0d  mov     eax, ebx
0x180022e0f  mov     rbx, [rsp+48h+arg_0]
0x180022e14  add     rsp, 40h
0x180022e18  pop     rdi
0x180022e19  retn
```
