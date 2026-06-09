# CStdioFile::Open(ushort const *,uint,CFileException *)

- ea: `0x180039130`
- end: `0x180039257`
- name: `?Open@CStdioFile@@UEAAHPEBGIPEAVCFileException@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(CStdioFile *__hidden this, const unsigned __int16 *, unsigned int, struct CFileException *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180038ea0`

## callees

- `0x180009910`
- `0x180033ee0`
- `0x1800347b8`
- `0x180039130`
- `0x180039db0`

## import_xrefs

- `msvcrt!__doserrno` at `0x180039215`
- `msvcrt!__doserrno` at `0x180039220`
- `msvcrt!__doserrno` at `0x180039215`
- `msvcrt!__doserrno` at `0x180039220`
- `msvcrt!_fdopen` at `0x1800391ff`
- `msvcrt!_fdopen` at `0x1800391ff`
- `msvcrt!_open_osfhandle` at `0x1800391ed`
- `msvcrt!_open_osfhandle` at `0x1800391ed`

## pseudocode

```c
__int64 __fastcall CStdioFile::Open(CStdioFile *this, const unsigned __int16 *a2, int a3, struct CFileException *a4)
{
  __int16 v5; // bx
  unsigned int v7; // edx
  char v8; // cl
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned __int64 v12; // rcx
  int v13; // eax
  int *v14; // rax
  char Mode; // [rsp+38h] [rbp+10h] BYREF
  char v17; // [rsp+39h] [rbp+11h]

  v5 = a3;
  if ( !a2 )
    return 0;
  *((_QWORD *)this + 4) = 0;
  if ( !CFile::Open(this, a2, a3 & 0xFFFFBFFF, a4) )
    return 0;
  v7 = 1;
  if ( (v5 & 0x1000) != 0 )
  {
    v8 = (v5 & 0x2000) != 0 ? 97 : 119;
    v9 = v5 & 1;
  }
  else
  {
    v9 = v5 & 1;
    if ( (v5 & 1) != 0 )
    {
      Mode = 97;
      goto LABEL_13;
    }
    v8 = 114;
  }
  Mode = v8;
  if ( v8 != 114 )
  {
    if ( v9 )
      goto LABEL_13;
    goto LABEL_12;
  }
  if ( (v5 & 2) != 0 )
  {
LABEL_12:
    v17 = 43;
    v7 = 2;
  }
LABEL_13:
  v10 = v7;
  v11 = (v5 & 0x8000) == 0 ? 0x4000 : 0;
  *(&Mode + v10) = v5 < 0 ? 98 : 116;
  v12 = v10 + 1;
  if ( v12 >= 4 )
    _report_rangecheckfailure(v12, v11);
  *(&Mode + v12) = 0;
  v13 = _open_osfhandle(*((_QWORD *)this + 1), v11);
  if ( v13 != -1 )
    *((_QWORD *)this + 4) = _fdopen(v13, &Mode);
  if ( !*((_QWORD *)this + 4) )
  {
    if ( a4 )
    {
      *((_DWORD *)a4 + 5) = *__doserrno();
      v14 = (int *)__doserrno();
      *((_DWORD *)a4 + 4) = CFileException::OsErrorToException(*v14);
    }
    CFile::Abort(this);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180039130  mov     [rsp+arg_0], rbx
0x180039135  mov     [rsp+arg_10], rbp
0x18003913a  push    rsi
0x18003913b  sub     rsp, 20h
0x18003913f  mov     rbp, r9
0x180039142  mov     ebx, r8d
0x180039145  mov     rsi, rcx
0x180039148  test    rdx, rdx
0x18003914b  jz      loc_180039238
0x180039151  btr     r8d, 0Eh; unsigned int
0x180039156  mov     qword ptr [rcx+20h], 0
0x18003915e  call    ?Open@CFile@@UEAAHPEBGIPEAVCFileException@@@Z; CFile::Open(ushort const *,uint,CFileException *)
0x180039163  test    eax, eax
0x180039165  jz      loc_180039238
0x18003916b  mov     eax, ebx
0x18003916d  mov     edx, 1
0x180039172  bt      ebx, 0Ch
0x180039176  jnb     short loc_18003918D
0x180039178  and     eax, 2000h
0x18003917d  neg     eax
0x18003917f  mov     eax, ebx
0x180039181  sbb     cl, cl
0x180039183  and     cl, 0EAh
0x180039186  add     cl, 77h ; 'w'
0x180039189  and     eax, edx
0x18003918b  jmp     short loc_18003919B
0x18003918d  and     eax, 1
0x180039190  jz      short loc_180039199
0x180039192  mov     [rsp+28h+Mode], 61h ; 'a'
0x180039197  jmp     short loc_1800391B9
0x180039199  mov     cl, 72h ; 'r'
0x18003919b  mov     [rsp+28h+Mode], cl
0x18003919f  cmp     cl, 72h ; 'r'
0x1800391a2  jnz     short loc_1800391AB
0x1800391a4  test    bl, 2
0x1800391a7  jnz     short loc_1800391AF
0x1800391a9  jmp     short loc_1800391B9
0x1800391ab  test    eax, eax
0x1800391ad  jnz     short loc_1800391B9
0x1800391af  mov     [rsp+28h+arg_9], 2Bh ; '+'
0x1800391b4  mov     edx, 2
0x1800391b9  and     ebx, 8000h
0x1800391bf  mov     ecx, edx
0x1800391c1  mov     eax, ebx
0x1800391c3  neg     eax
0x1800391c5  sbb     edx, edx
0x1800391c7  not     edx
0x1800391c9  and     edx, 4000h; Flags
0x1800391cf  neg     ebx
0x1800391d1  sbb     al, al
0x1800391d3  and     al, 0EEh
0x1800391d5  add     al, 74h ; 't'
0x1800391d7  mov     [rsp+rcx+28h+Mode], al
0x1800391db  inc     rcx
0x1800391de  cmp     rcx, 4
0x1800391e2  jnb     short loc_180039251
0x1800391e4  mov     [rsp+rcx+28h+Mode], 0
0x1800391e9  mov     rcx, [rsi+8]; OSFileHandle
0x1800391ed  call    cs:__imp__open_osfhandle
0x1800391f3  cmp     eax, 0FFFFFFFFh
0x1800391f6  jz      short loc_180039209
0x1800391f8  lea     rdx, [rsp+28h+Mode]; Mode
0x1800391fd  mov     ecx, eax; FileHandle
0x1800391ff  call    cs:__imp__fdopen
0x180039205  mov     [rsi+20h], rax
0x180039209  cmp     qword ptr [rsi+20h], 0
0x18003920e  jnz     short loc_18003924A
0x180039210  test    rbp, rbp
0x180039213  jz      short loc_180039230
0x180039215  call    cs:__imp___doserrno
0x18003921b  mov     ecx, [rax]
0x18003921d  mov     [rbp+14h], ecx
0x180039220  call    cs:__imp___doserrno
0x180039226  mov     ecx, [rax]; int
0x180039228  call    ?OsErrorToException@CFileException@@SAHJ@Z; CFileException::OsErrorToException(long)
0x18003922d  mov     [rbp+10h], eax
0x180039230  mov     rcx, rsi; this
0x180039233  call    ?Abort@CFile@@UEAAXXZ; CFile::Abort(void)
0x180039238  xor     eax, eax
0x18003923a  mov     rbx, [rsp+28h+arg_0]
0x18003923f  mov     rbp, [rsp+28h+arg_10]
0x180039244  add     rsp, 20h
0x180039248  pop     rsi
0x180039249  retn
0x18003924a  mov     eax, 1
0x18003924f  jmp     short loc_18003923A
0x180039251  call    __report_rangecheckfailure
```
