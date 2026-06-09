# CFile::Open(SIP_SUBJECTINFO_ *,bool)

- ea: `0x180002cf0`
- end: `0x180002d39`
- name: `?Open@CFile@@QEAA_NPEAUSIP_SUBJECTINFO_@@_N@Z`
- size: `73`
- prototype: `bool __fastcall(CFile *__hidden this, struct SIP_SUBJECTINFO_ *, bool)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800019e0`
- `0x180001dc0`
- `0x180001f10`
- `0x180002210`
- `0x180002360`

## callees

- `0x180002cf0`
- `0x180002d40`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180002d2c`
- `KERNEL32!SetLastError` at `0x180002d2c`

## pseudocode

```c
bool __fastcall CFile::Open(CFile *this, struct SIP_SUBJECTINFO_ *a2, bool a3)
{
  HANDLE hFile; // rax
  const unsigned __int16 *pwsFileName; // rdx

  if ( !a2 )
  {
LABEL_8:
    SetLastError(0x57u);
    return 0;
  }
  hFile = a2->hFile;
  if ( hFile == (HANDLE)-1LL )
  {
    pwsFileName = a2->pwsFileName;
    if ( pwsFileName )
      return CFile::Open(this, pwsFileName, a3);
    goto LABEL_8;
  }
  if ( *((_QWORD *)this + 1) == -1 )
  {
    *(_QWORD *)this = hFile;
    *((_QWORD *)this + 1) = hFile;
  }
  return 1;
}

```

## disassembly

```asm
0x180002cf0  sub     rsp, 28h
0x180002cf4  test    rdx, rdx
0x180002cf7  jz      short loc_180002D27
0x180002cf9  mov     rax, [rdx+10h]
0x180002cfd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002d01  jnz     short loc_180002D15
0x180002d03  mov     rdx, [rdx+18h]; unsigned __int16 *
0x180002d07  test    rdx, rdx
0x180002d0a  jz      short loc_180002D27
0x180002d0c  add     rsp, 28h
0x180002d10  jmp     ?Open@CFile@@QEAA_NPEBG_N@Z; CFile::Open(ushort const *,bool)
0x180002d15  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x180002d1a  jnz     short loc_180002D23
0x180002d1c  mov     [rcx], rax
0x180002d1f  mov     [rcx+8], rax
0x180002d23  mov     al, 1
0x180002d25  jmp     short loc_180002D34
0x180002d27  mov     ecx, 57h ; 'W'; dwErrCode
0x180002d2c  call    cs:__imp_SetLastError
0x180002d32  xor     al, al
0x180002d34  add     rsp, 28h
0x180002d38  retn
```
