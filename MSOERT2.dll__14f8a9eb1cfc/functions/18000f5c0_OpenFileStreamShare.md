# OpenFileStreamShare

- ea: `0x18000f5c0`
- end: `0x18000f686`
- name: `OpenFileStreamShare`
- size: `198`
- prototype: `__int64 __fastcall(char *, unsigned int, unsigned int, unsigned int, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180001980`
- `0x1800092d4`
- `0x180009378`
- `0x18000f5c0`
- `0x180011fec`
- `0x180012fc0`

## pseudocode

```c
__int64 __fastcall OpenFileStreamShare(char *a1, DWORD a2, DWORD a3, DWORD a4, struct IStream **a5)
{
  unsigned int v9; // r9d
  __int64 v10; // r8
  int appended; // ebx
  unsigned __int16 *v12; // rcx
  int v14; // [rsp+30h] [rbp-268h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-260h]
  unsigned __int16 v16[264]; // [rsp+50h] [rbp-248h] BYREF

  STRW::STRW((STRW *)&v14, v16, 0x104u);
  if ( !a1 )
    goto LABEL_5;
  v10 = -1;
  do
    ++v10;
  while ( a1[v10] );
  appended = STRW::AppendA_CCH_CP((STRW *)&v14, a1, v10, v9);
  if ( appended >= 0 )
  {
LABEL_5:
    v12 = (unsigned __int16 *)&ExistingFileName;
    if ( v14 )
      v12 = v15;
    appended = CreateFileStream(v12, a3, a4, a2, 0x80u, a5);
  }
  STRW::~STRW((STRW *)&v14);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18000f5c0  push    rbx
0x18000f5c2  push    rbp
0x18000f5c3  push    rsi
0x18000f5c4  push    rdi
0x18000f5c5  push    r14
0x18000f5c7  sub     rsp, 270h
0x18000f5ce  mov     rax, cs:__security_cookie
0x18000f5d5  xor     rax, rsp
0x18000f5d8  mov     [rsp+298h+var_38], rax
0x18000f5e0  mov     r14, [rsp+298h+arg_20]
0x18000f5e8  mov     esi, r8d
0x18000f5eb  mov     rbx, rcx
0x18000f5ee  mov     edi, edx
0x18000f5f0  mov     r8d, 104h; unsigned int
0x18000f5f6  lea     rdx, [rsp+298h+var_248]; unsigned __int16 *
0x18000f5fb  lea     rcx, [rsp+298h+var_268]; this
0x18000f600  mov     ebp, r9d
0x18000f603  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18000f608  test    rbx, rbx
0x18000f60b  jz      short loc_18000F62E
0x18000f60d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f611  inc     r8; unsigned int
0x18000f614  cmp     byte ptr [rbx+r8], 0
0x18000f619  jnz     short loc_18000F611
0x18000f61b  mov     rdx, rbx; char *
0x18000f61e  lea     rcx, [rsp+298h+var_268]; this
0x18000f623  call    ?AppendA_CCH_CP@STRW@@QEAAJPEBDKI@Z; STRW::AppendA_CCH_CP(char const *,ulong,uint)
0x18000f628  mov     ebx, eax
0x18000f62a  test    eax, eax
0x18000f62c  js      short loc_18000F65C
0x18000f62e  cmp     [rsp+298h+var_268], 0
0x18000f633  lea     rcx, ExistingFileName
0x18000f63a  mov     [rsp+298h+var_270], r14; struct IStream **
0x18000f63f  mov     r9d, edi; unsigned int
0x18000f642  cmovnz  rcx, [rsp+298h+var_260]; unsigned __int16 *
0x18000f648  mov     r8d, ebp; unsigned int
0x18000f64b  mov     edx, esi; unsigned int
0x18000f64d  mov     [rsp+298h+var_278], 80h; unsigned int
0x18000f655  call    ?CreateFileStream@@YAJPEBGKKKKPEAPEAUIStream@@@Z; CreateFileStream(ushort const *,ulong,ulong,ulong,ulong,IStream * *)
0x18000f65a  mov     ebx, eax
0x18000f65c  lea     rcx, [rsp+298h+var_268]; this
0x18000f661  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x18000f666  mov     eax, ebx
0x18000f668  mov     rcx, [rsp+298h+var_38]
0x18000f670  xor     rcx, rsp; StackCookie
0x18000f673  call    __security_check_cookie
0x18000f678  add     rsp, 270h
0x18000f67f  pop     r14
0x18000f681  pop     rdi
0x18000f682  pop     rsi
0x18000f683  pop     rbp
0x18000f684  pop     rbx
0x18000f685  retn
```
