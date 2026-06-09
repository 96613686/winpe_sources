# CILogCreateStorage2A::CreateStorage(char *,ulong,ulong,int,uint,uint,uint)

- ea: `0x180002150`
- end: `0x1800022dd`
- name: `?CreateStorage@CILogCreateStorage2A@@UEAAJPEADKKHIII@Z`
- size: `397`
- prototype: `__int64 __fastcall(CLogMgr **this, char *, unsigned int, unsigned int, int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180002150`
- `0x1800065c8`
- `0x180010a14`
- `0x180012830`
- `0x1800128f0`
- `0x180015010`

## import_xrefs

- `msvcrt!mbstowcs` at `0x180002251`
- `msvcrt!mbstowcs` at `0x180002251`

## pseudocode

```c
__int64 __fastcall CILogCreateStorage2A::CreateStorage(
        CLogMgr **this,
        char *a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  __int64 v11; // rsi
  unsigned __int64 v12; // rdi
  wchar_t *v13; // rbx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  _DWORD *v18; // rax
  unsigned int v20; // edi
  __int64 v21; // [rsp+0h] [rbp-60h] BYREF
  int v22; // [rsp+60h] [rbp+0h] BYREF
  _QWORD v23[5]; // [rsp+68h] [rbp+8h] BYREF
  unsigned int v24; // [rsp+B0h] [rbp+50h] BYREF

  v24 = a3;
  if ( !a3 || !a2 )
    return 2147942487LL;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  v12 = 2 * v11 + 2;
  v13 = 0;
  if ( 2 * v11 == -2
    || v12 > g_ulMaxStackAllocSize
    || v12 + g_ulAdditionalProbeSize + 8 < v12
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_13;
  }
  v14 = 2 * v11 + 25;
  if ( v14 <= 2 * v11 + 10 )
    v14 = 0xFFFFFFFFFFFFFF0LL;
  v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
  v16 = alloca(v15);
  v17 = alloca(v15);
  v13 = (wchar_t *)&v22;
  if ( &v21 == (__int64 *)-96LL || (v22 = 1801679955, (v13 = (wchar_t *)v23) == 0) )
  {
LABEL_13:
    if ( 2 * v11 + 10 >= (unsigned __int64)(2 * v11 + 2) )
    {
      v18 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      if ( !v18 )
        return 2147942414LL;
      *v18 = 1885431112;
      v13 = (wchar_t *)(v18 + 2);
    }
    if ( !v13 )
      return 2147942414LL;
  }
  mbstowcs(v13, a2, v11 + 1);
  v20 = CLogMgr::Init(this[1], 1, &v24, 0, v13, a4, a5, a6, a7, a8, 0xC8u);
  if ( *((_DWORD *)v13 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return v20;
}

```

## disassembly

```asm
0x180002150  mov     [rsp-8+arg_10], r8d
0x180002155  push    rbp
0x180002156  push    rdi
0x180002157  push    r13
0x180002159  push    r14
0x18000215b  push    r15
0x18000215d  sub     rsp, 70h
0x180002161  lea     rbp, [rsp+60h]
0x180002166  mov     [rbp+30h+arg_0], rbx
0x18000216a  mov     [rbp+30h+arg_8], rsi
0x18000216e  mov     rax, cs:__security_cookie
0x180002175  xor     rax, rbp
0x180002178  mov     [rbp+30h+var_28], rax
0x18000217c  mov     r15d, r9d
0x18000217f  mov     r14, rdx
0x180002182  mov     r13, rcx
0x180002185  test    r8d, r8d
0x180002188  jz      loc_1800022B7
0x18000218e  test    rdx, rdx
0x180002191  jz      loc_1800022B7
0x180002197  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000219b  inc     rsi
0x18000219e  cmp     byte ptr [rdx+rsi], 0
0x1800021a2  jnz     short loc_18000219B
0x1800021a4  lea     rdi, ds:2[rsi*2]
0x1800021ac  xor     ebx, ebx
0x1800021ae  test    rdi, rdi
0x1800021b1  jz      short loc_180002214
0x1800021b3  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800021ba  ja      short loc_180002214
0x1800021bc  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800021c3  add     rcx, 8
0x1800021c7  add     rcx, rdi
0x1800021ca  cmp     rcx, rdi
0x1800021cd  jb      short loc_180002214
0x1800021cf  call    VerifyStackAvailable
0x1800021d4  test    eax, eax
0x1800021d6  jz      short loc_180002214
0x1800021d8  lea     rax, [rdi+8]
0x1800021dc  lea     rcx, [rax+0Fh]
0x1800021e0  cmp     rcx, rax
0x1800021e3  ja      short loc_1800021EF
0x1800021e5  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800021ef  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800021f3  mov     rax, rcx
0x1800021f6  call    _alloca_probe
0x1800021fb  sub     rsp, rcx
0x1800021fe  lea     rbx, [rsp+90h+var_30]
0x180002203  test    rbx, rbx
0x180002206  jz      short loc_180002214
0x180002208  mov     dword ptr [rbx], 6B637453h
0x18000220e  add     rbx, 8
0x180002212  jnz     short loc_180002247
0x180002214  lea     rcx, [rdi+8]
0x180002218  cmp     rcx, rdi
0x18000221b  jb      short loc_18000223B
0x18000221d  mov     rax, cs:g_pfnAllocate
0x180002224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002229  mov     rbx, rax
0x18000222c  test    rax, rax
0x18000222f  jz      short loc_180002240
0x180002231  mov     dword ptr [rax], 70616548h
0x180002237  add     rbx, 8
0x18000223b  test    rbx, rbx
0x18000223e  jnz     short loc_180002247
0x180002240  mov     eax, 8007000Eh
0x180002245  jmp     short loc_1800022BC
0x180002247  lea     r8, [rsi+1]; MaxCount
0x18000224b  mov     rdx, r14; Source
0x18000224e  mov     rcx, rbx; Dest
0x180002251  call    cs:__imp_mbstowcs
0x180002257  mov     eax, [rbp+30h+arg_38]
0x18000225a  lea     r8, [rbp+30h+arg_10]; unsigned int *
0x18000225e  mov     rcx, [r13+8]; this
0x180002262  xor     r9d, r9d; unsigned int *
0x180002265  mov     [rsp+90h+var_40], 0C8h; unsigned int
0x18000226d  mov     [rsp+90h+var_48], eax; unsigned int
0x180002271  mov     eax, [rbp+30h+arg_30]
0x180002274  mov     [rsp+90h+var_50], eax; unsigned int
0x180002278  lea     edx, [r9+1]; int
0x18000227c  mov     eax, [rbp+30h+arg_28]
0x18000227f  mov     [rsp+90h+var_58], eax; unsigned int
0x180002283  mov     eax, [rbp+30h+arg_20]
0x180002286  mov     [rsp+90h+var_60], eax; int
0x18000228a  mov     [rsp+90h+var_68], r15d; unsigned int
0x18000228f  mov     [rsp+90h+var_70], rbx; unsigned __int16 *
0x180002294  call    ?Init@CLogMgr@@IEAAJHPEAK0PEAGKHIIII@Z; CLogMgr::Init(int,ulong *,ulong *,ushort *,ulong,int,uint,uint,uint,uint)
0x180002299  lea     rcx, [rbx-8]
0x18000229d  mov     edi, eax
0x18000229f  cmp     dword ptr [rcx], 70616548h
0x1800022a5  jnz     short loc_1800022B3
0x1800022a7  mov     rax, cs:g_pfnFree
0x1800022ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022b3  mov     eax, edi
0x1800022b5  jmp     short loc_1800022BC
0x1800022b7  mov     eax, 80070057h
0x1800022bc  mov     rcx, [rbp+30h+var_28]
0x1800022c0  xor     rcx, rbp; StackCookie
0x1800022c3  call    __security_check_cookie
0x1800022c8  mov     rbx, [rbp+30h+arg_0]
0x1800022cc  mov     rsi, [rbp+30h+arg_8]
0x1800022d0  lea     rsp, [rbp+10h]
0x1800022d4  pop     r15
0x1800022d6  pop     r14
0x1800022d8  pop     r13
0x1800022da  pop     rdi
0x1800022db  pop     rbp
0x1800022dc  retn
```
