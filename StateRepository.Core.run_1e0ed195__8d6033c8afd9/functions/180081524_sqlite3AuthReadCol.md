# sqlite3AuthReadCol

- ea: `0x180081524`
- end: `0x18008160f`
- name: `sqlite3AuthReadCol`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001c6f8`
- `0x180081470`

## callees

- `0x180001110`
- `0x180060ce8`
- `0x180081524`
- `0x18009a010`

## string_xrefs

- `0x1800815c8`: `access to %z is prohibited`

## pseudocode

```c
__int64 __fastcall sqlite3AuthReadCol(__int64 *a1, const char *a2, const char *a3, int a4)
{
  __int64 v4; // rdi
  __int64 v10; // r12
  unsigned int v11; // esi
  __int64 v12; // rax

  v4 = *a1;
  if ( *(_BYTE *)(*a1 + 197) )
    return 0;
  v10 = *(_QWORD *)(32LL * a4 + *(_QWORD *)(v4 + 32));
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, const char *, const char *, __int64, __int64))(v4 + 512))(
          *(_QWORD *)(v4 + 520),
          20,
          a2,
          a3,
          v10,
          a1[47]);
  if ( v11 == 1 )
  {
    v12 = sqlite3_mprintf("%s.%s", a2, a3);
    if ( *(int *)(v4 + 40) > 2 || a4 )
      v12 = sqlite3_mprintf("%s.%z", v10, v12);
    sqlite3ErrorMsg(a1, "access to %z is prohibited", v12);
    *((_DWORD *)a1 + 6) = 23;
  }
  else if ( (v11 & 0xFFFFFFFD) != 0 )
  {
    sqlite3ErrorMsg(a1, "authorizer malfunction");
    *((_DWORD *)a1 + 6) = 1;
  }
  return v11;
}

```

## disassembly

```asm
0x180081524  push    rbx
0x180081526  push    rbp
0x180081527  push    rsi
0x180081528  push    rdi
0x180081529  push    r12
0x18008152b  push    r14
0x18008152d  push    r15
0x18008152f  sub     rsp, 40h
0x180081533  mov     rdi, [rcx]
0x180081536  mov     r14, r8
0x180081539  movsxd  rbp, r9d
0x18008153c  mov     r15, rdx
0x18008153f  mov     rbx, rcx
0x180081542  cmp     byte ptr [rdi+0C5h], 0
0x180081549  jz      short loc_180081552
0x18008154b  xor     eax, eax
0x18008154d  jmp     loc_180081600
0x180081552  mov     rax, [rdi+20h]
0x180081556  mov     rcx, rbp
0x180081559  shl     rcx, 5
0x18008155d  mov     r9, r14
0x180081560  mov     r8, r15
0x180081563  mov     edx, 14h
0x180081568  mov     r12, [rcx+rax]
0x18008156c  mov     rcx, [rbx+178h]
0x180081573  mov     rax, [rdi+200h]
0x18008157a  mov     [rsp+78h+var_50], rcx
0x18008157f  mov     rcx, [rdi+208h]
0x180081586  mov     [rsp+78h+var_58], r12
0x18008158b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081590  mov     esi, eax
0x180081592  cmp     eax, 1
0x180081595  jnz     short loc_1800815E0
0x180081597  mov     r8, r14
0x18008159a  lea     rcx, aSS_2; "%s.%s"
0x1800815a1  mov     rdx, r15
0x1800815a4  call    sqlite3_mprintf
0x1800815a9  cmp     dword ptr [rdi+28h], 2
0x1800815ad  jg      short loc_1800815B3
0x1800815af  test    ebp, ebp
0x1800815b1  jz      short loc_1800815C5
0x1800815b3  mov     r8, rax
0x1800815b6  lea     rcx, aSZ; "%s.%z"
0x1800815bd  mov     rdx, r12
0x1800815c0  call    sqlite3_mprintf
0x1800815c5  mov     r8, rax
0x1800815c8  lea     rdx, aAccessToZIsPro; "access to %z is prohibited"
0x1800815cf  mov     rcx, rbx
0x1800815d2  call    sqlite3ErrorMsg
0x1800815d7  mov     dword ptr [rbx+18h], 17h
0x1800815de  jmp     short loc_1800815FE
0x1800815e0  test    esi, 0FFFFFFFDh
0x1800815e6  jz      short loc_1800815FE
0x1800815e8  lea     rdx, aAuthorizerMalf; "authorizer malfunction"
0x1800815ef  mov     rcx, rbx
0x1800815f2  call    sqlite3ErrorMsg
0x1800815f7  mov     dword ptr [rbx+18h], 1
0x1800815fe  mov     eax, esi
0x180081600  add     rsp, 40h
0x180081604  pop     r15
0x180081606  pop     r14
0x180081608  pop     r12
0x18008160a  pop     rdi
0x18008160b  pop     rsi
0x18008160c  pop     rbp
0x18008160d  pop     rbx
0x18008160e  retn
```
