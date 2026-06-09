# TEMPFILEINFO::~TEMPFILEINFO(void)

- ea: `0x1800093f0`
- end: `0x180009483`
- name: `??1TEMPFILEINFO@@EEAA@XZ`
- size: `147`
- prototype: `void __fastcall(TEMPFILEINFO *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009500`

## callees

- `0x180009378`
- `0x1800093f0`
- `0x18000a0fc`
- `0x18000a420`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180009410`
- `KERNEL32!CloseHandle` at `0x180009410`

## pseudocode

```c
void __fastcall TEMPFILEINFO::~TEMPFILEINFO(TEMPFILEINFO *this)
{
  void *v2; // rcx
  bool v3; // zf
  const unsigned __int16 *v4; // rdx

  *(_QWORD *)this = &TEMPFILEINFO::`vftable';
  v2 = (void *)*((_QWORD *)this + 71);
  if ( v2 == (void *)-1LL )
  {
    if ( (int)TEMPFILEINFO::_DeletePathLate(this) < 0 && !dword_1800209F8 )
    {
      v3 = *((_DWORD *)this + 132) == 0;
      v4 = &ExistingFileName;
      dword_1800209F8 = 1;
      if ( !v3 )
        v4 = (const unsigned __int16 *)*((_QWORD *)this + 67);
      AppendTempFileList((void **)&g_pTempFileHead, v4, 1);
      dword_1800209F8 = 0;
    }
  }
  else
  {
    CloseHandle(v2);
    *((_QWORD *)this + 71) = -1;
  }
  STRW::~STRW((TEMPFILEINFO *)((char *)this + 528));
}

```

## disassembly

```asm
0x1800093f0  push    rbx
0x1800093f2  sub     rsp, 20h
0x1800093f6  lea     rax, ??_7TEMPFILEINFO@@6B@; const TEMPFILEINFO::`vftable'
0x1800093fd  mov     rbx, rcx
0x180009400  mov     [rcx], rax
0x180009403  mov     rcx, [rcx+238h]; hObject
0x18000940a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000940e  jz      short loc_180009423
0x180009410  call    cs:__imp_CloseHandle
0x180009416  mov     qword ptr [rbx+238h], 0FFFFFFFFFFFFFFFFh
0x180009421  jmp     short loc_180009472
0x180009423  mov     rcx, rbx; this
0x180009426  call    ?_DeletePathLate@TEMPFILEINFO@@AEAAJXZ; TEMPFILEINFO::_DeletePathLate(void)
0x18000942b  test    eax, eax
0x18000942d  jns     short loc_180009472
0x18000942f  cmp     cs:dword_1800209F8, 0
0x180009436  jnz     short loc_180009472
0x180009438  cmp     dword ptr [rbx+210h], 0
0x18000943f  lea     rdx, ExistingFileName
0x180009446  mov     r8d, 1
0x18000944c  mov     cs:dword_1800209F8, r8d
0x180009453  jz      short loc_18000945C
0x180009455  mov     rdx, [rbx+218h]
0x18000945c  lea     rcx, ?g_pTempFileHead@@3PEAVTEMPFILELIST@@EA; TEMPFILELIST * g_pTempFileHead
0x180009463  call    AppendTempFileList
0x180009468  mov     cs:dword_1800209F8, 0
0x180009472  lea     rcx, [rbx+210h]; this
0x180009479  add     rsp, 20h
0x18000947d  pop     rbx
0x18000947e  jmp     ??1STRW@@QEAA@XZ; STRW::~STRW(void)
```
