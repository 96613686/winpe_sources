# EsdSipDelSignature(SIP_SUBJECTINFO_ *,ulong)

- ea: `0x180001dc0`
- end: `0x180001ec5`
- name: `?EsdSipDelSignature@@YAHPEAUSIP_SUBJECTINFO_@@K@Z`
- size: `261`
- prototype: `__int64 __fastcall(struct SIP_SUBJECTINFO_ *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180001dc0`
- `0x180002a4c`
- `0x180002cf0`
- `0x180002dfc`
- `0x180002f9c`
- `0x1800032ae`
- `0x1800032e0`

## import_xrefs

- `KERNEL32!SetEndOfFile` at `0x180001e6f`
- `KERNEL32!SetEndOfFile` at `0x180001e6f`
- `KERNEL32!SetLastError` at `0x180001e0d`
- `KERNEL32!SetLastError` at `0x180001e99`
- `KERNEL32!SetLastError` at `0x180001e0d`
- `KERNEL32!SetLastError` at `0x180001e99`
- `KERNEL32!SetFilePointerEx` at `0x180001e60`
- `KERNEL32!SetFilePointerEx` at `0x180001e60`

## pseudocode

```c
__int64 __fastcall EsdSipDelSignature(struct SIP_SUBJECTINFO_ *a1, int a2)
{
  unsigned int v4; // edi
  unsigned int v5; // ebx
  HANDLE hFile[2]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v8[180]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v9; // [rsp+E4h] [rbp-1Ch]
  LARGE_INTEGER liDistanceToMove; // [rsp+ECh] [rbp-14h]

  *(__m128i *)hFile = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v4 = 0;
  memset_0(v8, 0, 0xD0u);
  if ( a2 )
    SetLastError(0x57u);
  v5 = 1;
  if ( !CFile::Open((CFile *)hFile, a1, 1) || !CFile::Read(hFile, 0, 0xD0u, v8) )
    goto LABEL_10;
  if ( (_DWORD)v9 && liDistanceToMove.QuadPart )
  {
    if ( SetFilePointerEx(hFile[1], liDistanceToMove, 0, 0) )
      SetEndOfFile(hFile[1]);
    v9 = 0;
    liDistanceToMove.QuadPart = 0;
    v4 = (unsigned __int8)CFile::Write(hFile, 0, 0xD0u, v8);
LABEL_10:
    SetLastError(0);
    v5 = v4;
  }
  CFile::~CFile((CFile *)hFile);
  return v5;
}

```

## disassembly

```asm
0x180001dc0  push    rbp
0x180001dc2  push    rbx
0x180001dc3  push    rsi
0x180001dc4  push    rdi
0x180001dc5  lea     rbp, [rsp-18h]
0x180001dca  sub     rsp, 118h
0x180001dd1  mov     rax, cs:__security_cookie
0x180001dd8  xor     rax, rsp
0x180001ddb  mov     [rbp+30h+var_30], rax
0x180001ddf  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180001de7  mov     ebx, edx
0x180001de9  mov     rsi, rcx
0x180001dec  xor     edx, edx; Val
0x180001dee  lea     rcx, [rsp+130h+var_100]; void *
0x180001df3  mov     r8d, 0D0h; Size
0x180001df9  movdqu  xmmword ptr [rsp+130h+hFile], xmm0
0x180001dff  xor     edi, edi
0x180001e01  call    memset_0
0x180001e06  test    ebx, ebx
0x180001e08  jz      short loc_180001E13
0x180001e0a  lea     ecx, [rdi+57h]; dwErrCode
0x180001e0d  call    cs:__imp_SetLastError
0x180001e13  mov     ebx, 1
0x180001e18  lea     rcx, [rsp+130h+hFile]; this
0x180001e1d  mov     r8b, bl; bool
0x180001e20  mov     rdx, rsi; struct SIP_SUBJECTINFO_ *
0x180001e23  call    ?Open@CFile@@QEAA_NPEAUSIP_SUBJECTINFO_@@_N@Z; CFile::Open(SIP_SUBJECTINFO_ *,bool)
0x180001e28  test    al, al
0x180001e2a  jz      short loc_180001E97
0x180001e2c  lea     r9, [rsp+130h+var_100]; void *
0x180001e31  xor     edx, edx; unsigned __int64
0x180001e33  mov     r8d, 0D0h; unsigned int
0x180001e39  lea     rcx, [rsp+130h+hFile]; this
0x180001e3e  call    ?Read@CFile@@QEBA_N_KKPEAX@Z; CFile::Read(unsigned __int64,ulong,void *)
0x180001e43  test    al, al
0x180001e45  jz      short loc_180001E97
0x180001e47  cmp     dword ptr [rbp+30h+var_4C], edi
0x180001e4a  jz      short loc_180001EA1
0x180001e4c  mov     rdx, qword ptr [rbp+30h+liDistanceToMove]; liDistanceToMove
0x180001e50  test    rdx, rdx
0x180001e53  jz      short loc_180001EA1
0x180001e55  mov     rcx, [rsp+130h+hFile+8]; hFile
0x180001e5a  xor     r9d, r9d; dwMoveMethod
0x180001e5d  xor     r8d, r8d; lpNewFilePointer
0x180001e60  call    cs:__imp_SetFilePointerEx
0x180001e66  test    eax, eax
0x180001e68  jz      short loc_180001E75
0x180001e6a  mov     rcx, [rsp+130h+hFile+8]; hFile
0x180001e6f  call    cs:__imp_SetEndOfFile
0x180001e75  lea     r9, [rsp+130h+var_100]; void *
0x180001e7a  mov     [rbp+30h+var_4C], rdi
0x180001e7e  xor     edx, edx; unsigned __int64
0x180001e80  mov     qword ptr [rbp+30h+liDistanceToMove], rdi
0x180001e84  mov     r8d, 0D0h; unsigned int
0x180001e8a  lea     rcx, [rsp+130h+hFile]; this
0x180001e8f  call    ?Write@CFile@@QEBA_N_KKPEAX@Z; CFile::Write(unsigned __int64,ulong,void *)
0x180001e94  movzx   edi, al
0x180001e97  xor     ecx, ecx; dwErrCode
0x180001e99  call    cs:__imp_SetLastError
0x180001e9f  mov     ebx, edi
0x180001ea1  lea     rcx, [rsp+130h+hFile]; this
0x180001ea6  call    ??1CFile@@QEAA@XZ; CFile::~CFile(void)
0x180001eab  mov     eax, ebx
0x180001ead  mov     rcx, [rbp+30h+var_30]
0x180001eb1  xor     rcx, rsp; StackCookie
0x180001eb4  call    __security_check_cookie
0x180001eb9  add     rsp, 118h
0x180001ec0  pop     rdi
0x180001ec1  pop     rsi
0x180001ec2  pop     rbx
0x180001ec3  pop     rbp
0x180001ec4  retn
```
