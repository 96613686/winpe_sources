# AspCreateFile(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x180013f04`
- end: `0x180013fc9`
- name: `?AspCreateFile@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `197`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, __int64, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013d7c`
- `0x180016b50`
- `0x180048848`
- `0x180052cb0`

## callees

- `0x180013f04`
- `0x180023d86`
- `0x180023dd0`
- `0x180062344`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180013f99`
- `KERNEL32!CreateFileW` at `0x180013f99`
- `KERNEL32!SetLastError` at `0x18002c00b`
- `KERNEL32!SetLastError` at `0x18002c00b`
- `iisutil!MakePathCanonicalizationProof` at `0x180013f58`
- `iisutil!MakePathCanonicalizationProof` at `0x180013f58`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013fa7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013fa7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180013f6b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180013f6b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180013f4a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180013f4a`

## pseudocode

```c
__int64 __fastcall AspCreateFile(const unsigned __int16 *a1, __int64 a2, __int64 a3, struct _SECURITY_ATTRIBUTES *a4)
{
  int PathCanonicalizationProof; // eax
  const WCHAR *Str; // rax
  __int64 FileW; // rbx
  DWORD v9; // eax
  _BYTE v10[64]; // [rsp+40h] [rbp-268h] BYREF
  unsigned __int16 v11[264]; // [rsp+80h] [rbp-228h] BYREF

  memset_0(v11, 0, 0x208u);
  STRU::STRU((STRU *)v10, v11, 0x104u);
  PathCanonicalizationProof = MakePathCanonicalizationProof(a1, (struct STRU *)v10);
  if ( PathCanonicalizationProof < 0 )
  {
    v9 = WIN32_FROM_HRESULT(PathCanonicalizationProof);
    SetLastError(v9);
    FileW = -1;
  }
  else
  {
    Str = STRU::QueryStr((STRU *)v10);
    FileW = (__int64)CreateFileW(Str, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  }
  STRU::~STRU((STRU *)v10);
  return FileW;
}

```

## disassembly

```asm
0x180013f04  push    rbx
0x180013f06  sub     rsp, 2A0h
0x180013f0d  mov     rax, cs:__security_cookie
0x180013f14  xor     rax, rsp
0x180013f17  mov     [rsp+2A8h+var_18], rax
0x180013f1f  mov     rbx, rcx
0x180013f22  xor     edx, edx; Val
0x180013f24  lea     rcx, [rsp+2A8h+var_228]; void *
0x180013f2c  mov     r8d, 208h; Size
0x180013f32  call    memset_0
0x180013f37  mov     r8d, 104h
0x180013f3d  lea     rdx, [rsp+2A8h+var_228]
0x180013f45  lea     rcx, [rsp+2A8h+var_268]
0x180013f4a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180013f50  lea     rdx, [rsp+2A8h+var_268]
0x180013f55  mov     rcx, rbx
0x180013f58  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180013f5e  test    eax, eax
0x180013f60  js      loc_18002C002
0x180013f66  lea     rcx, [rsp+2A8h+var_268]
0x180013f6b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180013f71  xor     r9d, r9d; lpSecurityAttributes
0x180013f74  mov     [rsp+2A8h+hTemplateFile], 0; hTemplateFile
0x180013f7d  mov     rcx, rax; lpFileName
0x180013f80  mov     [rsp+2A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180013f88  mov     edx, 80000000h; dwDesiredAccess
0x180013f8d  mov     [rsp+2A8h+dwCreationDisposition], 3; dwCreationDisposition
0x180013f95  lea     r8d, [r9+1]; dwShareMode
0x180013f99  call    cs:__imp_CreateFileW
0x180013f9f  mov     rbx, rax
0x180013fa2  lea     rcx, [rsp+2A8h+var_268]
0x180013fa7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180013fad  mov     rax, rbx
0x180013fb0  mov     rcx, [rsp+2A8h+var_18]
0x180013fb8  xor     rcx, rsp; StackCookie
0x180013fbb  call    __security_check_cookie
0x180013fc0  add     rsp, 2A0h
0x180013fc7  pop     rbx
0x180013fc8  retn
0x18002c002  mov     ecx, eax; int
0x18002c004  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18002c009  mov     ecx, eax; dwErrCode
0x18002c00b  call    cs:__imp_SetLastError
0x18002c011  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002c015  jmp     loc_180013FA2
```
