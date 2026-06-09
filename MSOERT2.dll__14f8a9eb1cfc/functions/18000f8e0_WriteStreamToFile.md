# WriteStreamToFile

- ea: `0x18000f8e0`
- end: `0x18000f98f`
- name: `WriteStreamToFile`
- size: `175`
- prototype: `__int64 __fastcall(IStream *pstm, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800092d4`
- `0x180009378`
- `0x18000f8e0`
- `0x18000f9a0`
- `0x180011fec`
- `0x180012fc0`

## pseudocode

```c
__int64 __fastcall WriteStreamToFile(IStream *pstm, char *a2)
{
  unsigned int v4; // r9d
  __int64 v5; // r8
  int appended; // ebx
  int v8; // [rsp+20h] [rbp-268h] BYREF
  unsigned __int16 v9[264]; // [rsp+40h] [rbp-248h] BYREF

  STRW::STRW((STRW *)&v8, v9, 0x104u);
  if ( !a2 )
    goto LABEL_5;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  appended = STRW::AppendA_CCH_CP((STRW *)&v8, a2, v5, v4);
  if ( appended >= 0 )
LABEL_5:
    appended = WriteStreamToFileW(pstm);
  STRW::~STRW((STRW *)&v8);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18000f8e0  push    rbx
0x18000f8e2  push    rbp
0x18000f8e3  push    rsi
0x18000f8e4  push    rdi
0x18000f8e5  sub     rsp, 268h
0x18000f8ec  mov     rax, cs:__security_cookie
0x18000f8f3  xor     rax, rsp
0x18000f8f6  mov     [rsp+288h+var_38], rax
0x18000f8fe  mov     esi, r8d
0x18000f901  mov     rdi, rcx
0x18000f904  mov     rbx, rdx
0x18000f907  lea     rcx, [rsp+288h+var_268]; this
0x18000f90c  mov     r8d, 104h; unsigned int
0x18000f912  lea     rdx, [rsp+288h+var_248]; unsigned __int16 *
0x18000f917  mov     ebp, r9d
0x18000f91a  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18000f91f  test    rbx, rbx
0x18000f922  jz      short loc_18000F945
0x18000f924  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f928  inc     r8; unsigned int
0x18000f92b  cmp     byte ptr [rbx+r8], 0
0x18000f930  jnz     short loc_18000F928
0x18000f932  mov     rdx, rbx; char *
0x18000f935  lea     rcx, [rsp+288h+var_268]; this
0x18000f93a  call    ?AppendA_CCH_CP@STRW@@QEAAJPEBDKI@Z; STRW::AppendA_CCH_CP(char const *,ulong,uint)
0x18000f93f  mov     ebx, eax
0x18000f941  test    eax, eax
0x18000f943  js      short loc_18000F967
0x18000f945  cmp     [rsp+288h+var_268], 0
0x18000f94a  lea     rdx, ExistingFileName
0x18000f951  mov     r9d, ebp
0x18000f954  mov     r8d, esi
0x18000f957  cmovnz  rdx, [rsp+288h+var_260]
0x18000f95d  mov     rcx, rdi; pstm
0x18000f960  call    WriteStreamToFileW
0x18000f965  mov     ebx, eax
0x18000f967  lea     rcx, [rsp+288h+var_268]; this
0x18000f96c  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x18000f971  mov     eax, ebx
0x18000f973  mov     rcx, [rsp+288h+var_38]
0x18000f97b  xor     rcx, rsp; StackCookie
0x18000f97e  call    __security_check_cookie
0x18000f983  add     rsp, 268h
0x18000f98a  pop     rdi
0x18000f98b  pop     rsi
0x18000f98c  pop     rbp
0x18000f98d  pop     rbx
0x18000f98e  retn
```
