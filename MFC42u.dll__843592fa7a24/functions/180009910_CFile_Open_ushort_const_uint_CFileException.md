# CFile::Open(ushort const *,uint,CFileException *)

- ea: `0x180009910`
- end: `0x180009ab2`
- name: `?Open@CFile@@UEAAHPEBGIPEAVCFileException@@@Z`
- size: `418`
- prototype: `int(CFile *__hidden this, const unsigned __int16 *, unsigned int, struct CFileException *)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180037ff0`
- `0x180039130`
- `0x180060880`
- `0x1800ce154`

## callees

- `0x180009740`
- `0x180009910`
- `0x18000a760`
- `0x18000b3a0`
- `0x180039db0`
- `0x1800d1fe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a66`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009a55`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009a55`
- `KERNEL32!lstrlenW` at `0x180009960`
- `KERNEL32!lstrlenW` at `0x180009960`

## pseudocode

```c
__int64 __fastcall CFile::Open(CFile *this, const unsigned __int16 *a2, __int16 a3, struct CFileException *a4)
{
  DWORD v8; // r10d
  DWORD dwCreationDisposition; // edx
  int v10; // eax
  DWORD v11; // r8d
  HANDLE v12; // rax
  DWORD LastError; // eax
  __int64 result; // rax
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-268h] BYREF
  wchar_t Source[264]; // [rsp+60h] [rbp-248h] BYREF

  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 1) = -1;
  CString::Empty((CFile *)((char *)this + 24));
  if ( !a2 || lstrlenW(a2) >= 260 || !(unsigned int)AfxFullPath(Source, a2) )
    return 0;
  CString::operator=((char *)this + 24, Source);
  v8 = 0;
  dwCreationDisposition = 3;
  if ( (a3 & 3) != 0 )
  {
    if ( (a3 & 3) == 1 )
    {
      v8 = 0x40000000;
    }
    else if ( (a3 & 3) == 2 )
    {
      v8 = -1073741824;
    }
  }
  else
  {
    v8 = 0x80000000;
  }
  v10 = a3 & 0x70;
  if ( (a3 & 0x70) != 0 && v10 != 16 )
  {
    switch ( v10 )
    {
      case ' ':
        v11 = 1;
        goto LABEL_19;
      case '0':
        v11 = 2;
        goto LABEL_19;
      case '@':
        v11 = 3;
        goto LABEL_19;
    }
  }
  v11 = 0;
LABEL_19:
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(&SecurityAttributes.bInheritHandle + 1) = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  SecurityAttributes.bInheritHandle = (unsigned __int8)~(_BYTE)a3 >> 7;
  if ( (a3 & 0x1000) != 0 )
    dwCreationDisposition = (a3 & 0x2000) != 0 ? 4 : 2;
  v12 = CreateFileW(a2, v8, v11, &SecurityAttributes, dwCreationDisposition, 0x80u, 0);
  if ( v12 == (HANDLE)-1LL )
  {
    if ( a4 )
    {
      LastError = GetLastError();
      *((_DWORD *)a4 + 5) = LastError;
      *((_DWORD *)a4 + 4) = CFileException::OsErrorToException(LastError);
      CString::operator=((char *)a4 + 24, a2);
    }
    return 0;
  }
  *((_QWORD *)this + 1) = v12;
  result = 1;
  *((_DWORD *)this + 4) = 1;
  return result;
}

```

## disassembly

```asm
0x180009910  push    rbx
0x180009912  push    rbp
0x180009913  push    rsi
0x180009914  push    rdi
0x180009915  push    r14
0x180009917  sub     rsp, 280h
0x18000991e  mov     rax, cs:__security_cookie
0x180009925  xor     rax, rsp
0x180009928  mov     [rsp+2A8h+var_38], rax
0x180009930  mov     rsi, rcx
0x180009933  mov     dword ptr [rcx+10h], 0
0x18000993a  mov     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x180009942  mov     rdi, r9
0x180009945  add     rcx, 18h; this
0x180009949  mov     ebx, r8d
0x18000994c  mov     rbp, rdx
0x18000994f  call    ?Empty@CString@@QEAAXXZ; CString::Empty(void)
0x180009954  test    rbp, rbp
0x180009957  jz      loc_180009A85
0x18000995d  mov     rcx, rbp; lpString
0x180009960  call    cs:__imp_lstrlenW
0x180009966  cmp     eax, 104h
0x18000996b  jge     loc_180009A85
0x180009971  mov     rdx, rbp; lpFileName
0x180009974  lea     rcx, [rsp+2A8h+Source]; Source
0x180009979  call    ?AfxFullPath@@YAHPEAGPEBG@Z; AfxFullPath(ushort *,ushort const *)
0x18000997e  test    eax, eax
0x180009980  jz      loc_180009A85
0x180009986  lea     rdx, [rsp+2A8h+Source]
0x18000998b  lea     rcx, [rsi+18h]
0x18000998f  call    ??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180009994  xor     r10d, r10d
0x180009997  mov     eax, ebx
0x180009999  lea     edx, [r10+3]
0x18000999d  and     eax, edx
0x18000999f  jz      short loc_1800099BB
0x1800099a1  sub     eax, 1
0x1800099a4  jz      short loc_1800099B3
0x1800099a6  cmp     eax, 1
0x1800099a9  jnz     short loc_1800099C1
0x1800099ab  mov     r10d, 0C0000000h
0x1800099b1  jmp     short loc_1800099C1
0x1800099b3  mov     r10d, 40000000h
0x1800099b9  jmp     short loc_1800099C1
0x1800099bb  mov     r10d, 80000000h
0x1800099c1  mov     eax, ebx
0x1800099c3  mov     r14d, 1
0x1800099c9  and     eax, 70h
0x1800099cc  jz      short loc_1800099F4
0x1800099ce  cmp     eax, 10h
0x1800099d1  jz      short loc_1800099F4
0x1800099d3  cmp     eax, 20h ; ' '
0x1800099d6  jz      short loc_1800099EF
0x1800099d8  cmp     eax, 30h ; '0'
0x1800099db  jz      short loc_1800099E7
0x1800099dd  cmp     eax, 40h ; '@'
0x1800099e0  jnz     short loc_1800099F4
0x1800099e2  mov     r8d, edx
0x1800099e5  jmp     short loc_1800099F7
0x1800099e7  mov     r8d, 2
0x1800099ed  jmp     short loc_1800099F7
0x1800099ef  mov     r8d, r14d
0x1800099f2  jmp     short loc_1800099F7
0x1800099f4  xor     r8d, r8d; dwShareMode
0x1800099f7  mov     al, bl
0x1800099f9  mov     qword ptr [rsp+2A8h+SecurityAttributes.nLength], 18h
0x180009a02  not     al
0x180009a04  mov     dword ptr [rsp+2A8h+SecurityAttributes+14h], 0
0x180009a0c  movzx   ecx, al
0x180009a0f  shr     ecx, 7
0x180009a12  mov     [rsp+2A8h+SecurityAttributes.lpSecurityDescriptor], 0
0x180009a1b  mov     [rsp+2A8h+SecurityAttributes.bInheritHandle], ecx
0x180009a1f  bt      ebx, 0Ch
0x180009a23  jnb     short loc_180009A35
0x180009a25  and     ebx, 2000h
0x180009a2b  neg     ebx
0x180009a2d  sbb     edx, edx
0x180009a2f  and     edx, 2
0x180009a32  add     edx, 2
0x180009a35  mov     [rsp+2A8h+hTemplateFile], 0; hTemplateFile
0x180009a3e  lea     r9, [rsp+2A8h+SecurityAttributes]; lpSecurityAttributes
0x180009a43  mov     [rsp+2A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180009a4b  mov     rcx, rbp; lpFileName
0x180009a4e  mov     [rsp+2A8h+dwCreationDisposition], edx; dwCreationDisposition
0x180009a52  mov     edx, r10d; dwDesiredAccess
0x180009a55  call    cs:__imp_CreateFileW
0x180009a5b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009a5f  jnz     short loc_180009AA5
0x180009a61  test    rdi, rdi
0x180009a64  jz      short loc_180009A85
0x180009a66  call    cs:__imp_GetLastError
0x180009a6c  mov     ecx, eax; int
0x180009a6e  mov     [rdi+14h], eax
0x180009a71  call    ?OsErrorToException@CFileException@@SAHJ@Z; CFileException::OsErrorToException(long)
0x180009a76  lea     rcx, [rdi+18h]
0x180009a7a  mov     [rdi+10h], eax
0x180009a7d  mov     rdx, rbp
0x180009a80  call    ??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180009a85  xor     eax, eax
0x180009a87  mov     rcx, [rsp+2A8h+var_38]
0x180009a8f  xor     rcx, rsp; StackCookie
0x180009a92  call    __security_check_cookie
0x180009a97  add     rsp, 280h
0x180009a9e  pop     r14
0x180009aa0  pop     rdi
0x180009aa1  pop     rsi
0x180009aa2  pop     rbp
0x180009aa3  pop     rbx
0x180009aa4  retn
0x180009aa5  mov     [rsi+8], rax
0x180009aa9  mov     eax, r14d
0x180009aac  mov     [rsi+10h], r14d
0x180009ab0  jmp     short loc_180009A87
```
