# OpenFileStream

- ea: `0x18000f500`
- end: `0x18000f5b5`
- name: `OpenFileStream`
- size: `181`
- prototype: `__int64 __fastcall(char *, unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800092d4`
- `0x180009378`
- `0x18000f500`
- `0x18000f6b0`
- `0x180011fec`
- `0x180012fc0`

## pseudocode

```c
__int64 __fastcall OpenFileStream(char *a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  unsigned int v8; // r9d
  __int64 v9; // r8
  int appended; // ebx
  const WCHAR *v11; // rcx
  int v13; // [rsp+30h] [rbp-268h] BYREF
  const WCHAR *v14; // [rsp+38h] [rbp-260h]
  unsigned __int16 v15[264]; // [rsp+50h] [rbp-248h] BYREF

  STRW::STRW((STRW *)&v13, v15, 0x104u);
  if ( !a1 )
    goto LABEL_5;
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  appended = STRW::AppendA_CCH_CP((STRW *)&v13, a1, v9, v8);
  if ( appended >= 0 )
  {
LABEL_5:
    v11 = &ExistingFileName;
    if ( v13 )
      v11 = v14;
    appended = OpenFileStreamWithFlagsW(v11, a2, a3, 128, a4);
  }
  STRW::~STRW((STRW *)&v13);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18000f500  push    rbx
0x18000f502  push    rbp
0x18000f503  push    rsi
0x18000f504  push    rdi
0x18000f505  sub     rsp, 278h
0x18000f50c  mov     rax, cs:__security_cookie
0x18000f513  xor     rax, rsp
0x18000f516  mov     [rsp+298h+var_38], rax
0x18000f51e  mov     esi, r8d
0x18000f521  mov     rbx, rcx
0x18000f524  mov     edi, edx
0x18000f526  lea     rcx, [rsp+298h+var_268]; this
0x18000f52b  mov     r8d, 104h; unsigned int
0x18000f531  lea     rdx, [rsp+298h+var_248]; unsigned __int16 *
0x18000f536  mov     rbp, r9
0x18000f539  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18000f53e  test    rbx, rbx
0x18000f541  jz      short loc_18000F564
0x18000f543  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f547  inc     r8; unsigned int
0x18000f54a  cmp     byte ptr [rbx+r8], 0
0x18000f54f  jnz     short loc_18000F547
0x18000f551  mov     rdx, rbx; char *
0x18000f554  lea     rcx, [rsp+298h+var_268]; this
0x18000f559  call    ?AppendA_CCH_CP@STRW@@QEAAJPEBDKI@Z; STRW::AppendA_CCH_CP(char const *,ulong,uint)
0x18000f55e  mov     ebx, eax
0x18000f560  test    eax, eax
0x18000f562  js      short loc_18000F58D
0x18000f564  cmp     [rsp+298h+var_268], 0
0x18000f569  lea     rcx, ExistingFileName
0x18000f570  mov     r9d, 80h
0x18000f576  mov     [rsp+298h+var_278], rbp
0x18000f57b  cmovnz  rcx, [rsp+298h+var_260]
0x18000f581  mov     r8d, esi
0x18000f584  mov     edx, edi
0x18000f586  call    OpenFileStreamWithFlagsW
0x18000f58b  mov     ebx, eax
0x18000f58d  lea     rcx, [rsp+298h+var_268]; this
0x18000f592  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x18000f597  mov     eax, ebx
0x18000f599  mov     rcx, [rsp+298h+var_38]
0x18000f5a1  xor     rcx, rsp; StackCookie
0x18000f5a4  call    __security_check_cookie
0x18000f5a9  add     rsp, 278h
0x18000f5b0  pop     rdi
0x18000f5b1  pop     rsi
0x18000f5b2  pop     rbp
0x18000f5b3  pop     rbx
0x18000f5b4  retn
```
