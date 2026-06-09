# TEMPFILEINFO::CreateInstance(ushort const *,int,TEMPFILEINFO * *)

- ea: `0x180009834`
- end: `0x180009913`
- name: `?CreateInstance@TEMPFILEINFO@@SAJPEBGHPEAPEAV1@@Z`
- size: `223`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, struct TEMPFILEINFO **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000a420`

## callees

- `0x180001c80`
- `0x180001f7c`
- `0x180009240`
- `0x1800092d4`
- `0x180009578`
- `0x180009834`
- `0x18000a374`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180009857`
- `KERNEL32!GetFileAttributesW` at `0x180009857`

## pseudocode

```c
__int64 __fastcall TEMPFILEINFO::CreateInstance(const unsigned __int16 *a1, int a2, struct TEMPFILEINFO **a3)
{
  DWORD FileAttributesW; // ebx
  int LastError; // ebx
  int v8; // ebx
  unsigned __int16 *v9; // rdi
  unsigned __int16 *v11; // [rsp+58h] [rbp+20h] BYREF

  v11 = 0;
  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 )
  {
    LastError = HrGetLastError();
  }
  else
  {
    v8 = (FileAttributesW >> 4) & 1;
    v9 = (unsigned __int16 *)operator new(0x240u);
    if ( v9 )
    {
      *(_QWORD *)v9 = &TEMPFILEINFO::`vftable';
      STRW::STRW((STRW *)(v9 + 264), v9 + 4, 0x104u);
      *((_DWORD *)v9 + 140) = v8;
      *((_QWORD *)v9 + 71) = -1;
      v11 = v9;
      LastError = STRW::Append((STRW *)(v9 + 264), a1);
      if ( LastError >= 0 )
      {
        if ( a2 )
          TEMPFILEINFO::_OpenDeleteHandle((TEMPFILEINFO *)v9);
        *a3 = (struct TEMPFILEINFO *)v9;
        LastError = 0;
        v11 = 0;
      }
    }
    else
    {
      LastError = -2147024882;
    }
  }
  OE_SafeReleaseAndNullPtr<TEMPFILEINFO>(&v11);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180009834  mov     [rsp+arg_0], rbx
0x180009839  mov     [rsp+arg_8], rbp
0x18000983e  push    rsi
0x18000983f  push    rdi
0x180009840  push    r14
0x180009842  sub     rsp, 20h
0x180009846  mov     r14, r8
0x180009849  mov     [rsp+38h+arg_18], 0
0x180009852  mov     esi, edx
0x180009854  mov     rbp, rcx
0x180009857  call    cs:__imp_GetFileAttributesW
0x18000985d  mov     ebx, eax
0x18000985f  cmp     eax, 0FFFFFFFFh
0x180009862  jnz     short loc_180009870
0x180009864  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180009869  mov     ebx, eax
0x18000986b  jmp     loc_1800098F4
0x180009870  shr     ebx, 4
0x180009873  mov     ecx, 240h; Size
0x180009878  and     ebx, 1
0x18000987b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009880  mov     rdi, rax
0x180009883  test    rax, rax
0x180009886  jz      short loc_1800098EF
0x180009888  lea     rax, ??_7TEMPFILEINFO@@6B@; const TEMPFILEINFO::`vftable'
0x18000988f  mov     r8d, 104h; unsigned int
0x180009895  lea     rdx, [rdi+8]; unsigned __int16 *
0x180009899  mov     [rdi], rax
0x18000989c  lea     rcx, [rdi+210h]; this
0x1800098a3  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x1800098a8  lea     rcx, [rdi+210h]; this
0x1800098af  mov     [rdi+230h], ebx
0x1800098b5  mov     rdx, rbp; unsigned __int16 *
0x1800098b8  mov     qword ptr [rdi+238h], 0FFFFFFFFFFFFFFFFh
0x1800098c3  mov     [rsp+38h+arg_18], rdi
0x1800098c8  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x1800098cd  mov     ebx, eax
0x1800098cf  test    eax, eax
0x1800098d1  js      short loc_1800098F4
0x1800098d3  test    esi, esi
0x1800098d5  jz      short loc_1800098DF
0x1800098d7  mov     rcx, rdi; this
0x1800098da  call    ?_OpenDeleteHandle@TEMPFILEINFO@@AEAAJXZ; TEMPFILEINFO::_OpenDeleteHandle(void)
0x1800098df  mov     [r14], rdi
0x1800098e2  xor     ebx, ebx
0x1800098e4  mov     [rsp+38h+arg_18], 0
0x1800098ed  jmp     short loc_1800098F4
0x1800098ef  mov     ebx, 8007000Eh
0x1800098f4  lea     rcx, [rsp+38h+arg_18]
0x1800098f9  call    ??$OE_SafeReleaseAndNullPtr@VTEMPFILEINFO@@@@YAXAEAPEAVTEMPFILEINFO@@@Z; OE_SafeReleaseAndNullPtr<TEMPFILEINFO>(TEMPFILEINFO * &)
0x1800098fe  mov     rbp, [rsp+38h+arg_8]
0x180009903  mov     eax, ebx
0x180009905  mov     rbx, [rsp+38h+arg_0]
0x18000990a  add     rsp, 20h
0x18000990e  pop     r14
0x180009910  pop     rdi
0x180009911  pop     rsi
0x180009912  retn
```
