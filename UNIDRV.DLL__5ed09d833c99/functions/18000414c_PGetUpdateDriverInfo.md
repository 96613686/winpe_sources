# PGetUpdateDriverInfo

- ea: `0x18000414c`
- end: `0x180004319`
- name: `PGetUpdateDriverInfo`
- size: `461`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025dc0`

## callees

- `0x180003da8`
- `0x18000414c`
- `0x180004320`
- `0x180004810`
- `0x180005020`
- `0x180005b20`
- `0x180007150`
- `0x180007320`
- `0x180045334`
- `0x180049d00`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180004218`
- `KERNEL32!LocalFree` at `0x180004218`
- `KERNEL32!LocalAlloc` at `0x1800041c2`
- `KERNEL32!LocalAlloc` at `0x1800041c2`

## pseudocode

```c
__int64 __fastcall PGetUpdateDriverInfo(
        __int64 a1,
        __int64 a2,
        void *a3,
        void *a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  _BYTE *v11; // rsi
  HLOCAL v12; // rax
  void *v13; // rbx
  int v14; // ebp
  _BYTE *v15; // rbx
  __int64 v16; // r9
  __int64 v17; // rax
  _BYTE v19[512]; // [rsp+30h] [rbp-448h] BYREF
  _BYTE v20[512]; // [rsp+230h] [rbp-248h] BYREF

  v11 = (_BYTE *)(a8 + 48);
  if ( *(_DWORD *)(a8 + 40) != *(_DWORD *)(a5 + 12) )
    v11 = 0;
  if ( !a7 || (v15 = (_BYTE *)(a7 + *(unsigned __int16 *)(a7 + 68) + 48LL)) == 0 )
  {
    if ( *(_DWORD *)(a5 + 20) > 0x100u )
      return 0;
    v12 = LocalAlloc(0, 0x400u);
    v13 = v12;
    if ( !v12
      || !(unsigned int)BinitDefaultOptionArray((__int64)v12, a5)
      || (v14 = 1, !(unsigned int)GPDSeparateOptionArray(a5, (__int64)v13, (__int64)v19, 0x100u, 0)) )
    {
      WriteDbgTraceErrorGpd((__int64)"GPDInitDefaultOptions", "InitDefaultOptions: internal failure.");
      v14 = 0;
      if ( !v13 )
        return 0;
    }
    LocalFree(v13);
    if ( !v14 )
      return 0;
    v15 = v19;
  }
  if ( !v11 )
  {
    if ( !(unsigned int)GPDInitDefaultOptions(a5, (__int64)v20, 0x100u, 1) )
      return 0;
    v11 = v20;
  }
  GPDCombineOptionArray(a5, (__int64)a4, 0x100u, (__int64)v15, (__int64)v11);
  BMergeFormToTrayAssignments(a1);
  GPDResolveUIConflicts(a5, (__int64)a4, 0x100u, 2);
  v17 = GPDInitBinaryDataWithSize(a5, a3, a4, v16);
  if ( !v17 || !*(_DWORD *)(v17 + 60) )
    return 0;
  return v17 + *(unsigned int *)(v17 + 60);
}

```

## disassembly

```asm
0x18000414c  mov     [rsp+arg_8], rbx
0x180004151  push    rbp
0x180004152  push    rsi
0x180004153  push    rdi
0x180004154  push    r12
0x180004156  push    r13
0x180004158  push    r14
0x18000415a  push    r15
0x18000415c  sub     rsp, 440h
0x180004163  mov     rax, cs:__security_cookie
0x18000416a  xor     rax, rsp
0x18000416d  mov     [rsp+478h+var_48], rax
0x180004175  mov     rax, [rsp+478h+arg_38]
0x18000417d  mov     r15, rcx
0x180004180  mov     rdi, [rsp+478h+arg_20]
0x180004188  mov     r14, r9
0x18000418b  mov     rdx, [rsp+478h+arg_30]
0x180004193  mov     r12, r8
0x180004196  mov     r13d, 100h
0x18000419c  mov     ecx, [rax+28h]
0x18000419f  lea     rsi, [rax+30h]
0x1800041a3  xor     eax, eax
0x1800041a5  cmp     ecx, [rdi+0Ch]
0x1800041a8  cmovnz  rsi, rax
0x1800041ac  test    rdx, rdx
0x1800041af  jnz     short loc_18000422F
0x1800041b1  cmp     [rdi+14h], r13d
0x1800041b5  ja      loc_180004291
0x1800041bb  mov     edx, 400h; uBytes
0x1800041c0  xor     ecx, ecx; uFlags
0x1800041c2  call    cs:__imp_LocalAlloc
0x1800041c9  nop     dword ptr [rax+rax+00h]
0x1800041ce  mov     rbx, rax
0x1800041d1  test    rax, rax
0x1800041d4  jz      loc_1800042BF
0x1800041da  mov     rdx, rdi
0x1800041dd  mov     rcx, rax
0x1800041e0  call    BinitDefaultOptionArray
0x1800041e5  test    eax, eax
0x1800041e7  jz      loc_1800042BF
0x1800041ed  mov     r9d, r13d
0x1800041f0  mov     dword ptr [rsp+478h+var_458], 0
0x1800041f8  lea     r8, [rsp+478h+var_448]
0x1800041fd  mov     rdx, rbx
0x180004200  mov     rcx, rdi
0x180004203  mov     ebp, 1
0x180004208  call    GPDSeparateOptionArray
0x18000420d  test    eax, eax
0x18000420f  jz      loc_1800042BF
0x180004215  mov     rcx, rbx; hMem
0x180004218  call    cs:__imp_LocalFree
0x18000421f  nop     dword ptr [rax+rax+00h]
0x180004224  test    ebp, ebp
0x180004226  jz      short loc_180004291
0x180004228  lea     rbx, [rsp+478h+var_448]
0x18000422d  jmp     short loc_180004240
0x18000422f  movzx   ebx, word ptr [rdx+44h]
0x180004233  add     rbx, 30h ; '0'
0x180004237  add     rbx, rdx
0x18000423a  jz      loc_1800041B1
0x180004240  test    rsi, rsi
0x180004243  jz      loc_1800042DE
0x180004249  mov     r9, rbx
0x18000424c  mov     [rsp+478h+var_458], rsi
0x180004251  mov     r8d, r13d
0x180004254  mov     rdx, r14
0x180004257  mov     rcx, rdi
0x18000425a  call    GPDCombineOptionArray
0x18000425f  mov     rcx, r15
0x180004262  call    BMergeFormToTrayAssignments
0x180004267  mov     r9d, 2
0x18000426d  mov     r8d, r13d
0x180004270  mov     rdx, r14
0x180004273  mov     rcx, rdi; int
0x180004276  call    GPDResolveUIConflicts
0x18000427b  mov     r8, r14
0x18000427e  mov     rdx, r12
0x180004281  mov     rcx, rdi
0x180004284  call    GPDInitBinaryDataWithSize
0x180004289  mov     rcx, rax
0x18000428c  test    rax, rax
0x18000428f  jnz     short loc_180004308
0x180004291  xor     eax, eax
0x180004293  mov     rcx, [rsp+478h+var_48]
0x18000429b  xor     rcx, rsp; StackCookie
0x18000429e  call    __security_check_cookie
0x1800042a3  mov     rbx, [rsp+478h+arg_8]
0x1800042ab  add     rsp, 440h
0x1800042b2  pop     r15
0x1800042b4  pop     r14
0x1800042b6  pop     r13
0x1800042b8  pop     r12
0x1800042ba  pop     rdi
0x1800042bb  pop     rsi
0x1800042bc  pop     rbp
0x1800042bd  retn
0x1800042bf  lea     rdx, aInitdefaultopt; "InitDefaultOptions: internal failure."
0x1800042c6  lea     rcx, aGpdinitdefault; "GPDInitDefaultOptions"
0x1800042cd  call    WriteDbgTraceErrorGpd
0x1800042d2  xor     ebp, ebp
0x1800042d4  test    rbx, rbx
0x1800042d7  jz      short loc_180004291
0x1800042d9  jmp     loc_180004215
0x1800042de  mov     r9d, 1
0x1800042e4  lea     rdx, [rsp+478h+var_248]
0x1800042ec  mov     r8d, r13d
0x1800042ef  mov     rcx, rdi
0x1800042f2  call    GPDInitDefaultOptions
0x1800042f7  test    eax, eax
0x1800042f9  jz      short loc_180004291
0x1800042fb  lea     rsi, [rsp+478h+var_248]
0x180004303  jmp     loc_180004249
0x180004308  cmp     dword ptr [rax+3Ch], 0
0x18000430c  jz      short loc_180004291
0x18000430e  mov     eax, [rax+3Ch]
0x180004311  add     rax, rcx
0x180004314  jmp     loc_180004293
```
