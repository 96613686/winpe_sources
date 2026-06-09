# sqlite3AuthReadCol

- ea: `0x180078798`
- end: `0x180078883`
- name: `sqlite3AuthReadCol`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800786ec`
- `0x180081db4`

## callees

- `0x180014464`
- `0x180078798`
- `0x180096550`
- `0x1800a8010`

## string_xrefs

- `0x18007883c`: `access to %z is prohibited`

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
0x180078798  push    rbx
0x18007879a  push    rbp
0x18007879b  push    rsi
0x18007879c  push    rdi
0x18007879d  push    r12
0x18007879f  push    r14
0x1800787a1  push    r15
0x1800787a3  sub     rsp, 40h
0x1800787a7  mov     rdi, [rcx]
0x1800787aa  mov     r14, r8
0x1800787ad  movsxd  rbp, r9d
0x1800787b0  mov     r15, rdx
0x1800787b3  mov     rbx, rcx
0x1800787b6  cmp     byte ptr [rdi+0C5h], 0
0x1800787bd  jz      short loc_1800787C6
0x1800787bf  xor     eax, eax
0x1800787c1  jmp     loc_180078874
0x1800787c6  mov     rax, [rdi+20h]
0x1800787ca  mov     rcx, rbp
0x1800787cd  shl     rcx, 5
0x1800787d1  mov     r9, r14
0x1800787d4  mov     r8, r15
0x1800787d7  mov     edx, 14h
0x1800787dc  mov     r12, [rcx+rax]
0x1800787e0  mov     rcx, [rbx+178h]
0x1800787e7  mov     rax, [rdi+200h]
0x1800787ee  mov     [rsp+78h+var_50], rcx
0x1800787f3  mov     rcx, [rdi+208h]
0x1800787fa  mov     [rsp+78h+var_58], r12
0x1800787ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078804  mov     esi, eax
0x180078806  cmp     eax, 1
0x180078809  jnz     short loc_180078854
0x18007880b  mov     r8, r14
0x18007880e  lea     rcx, aSS_5; "%s.%s"
0x180078815  mov     rdx, r15
0x180078818  call    sqlite3_mprintf
0x18007881d  cmp     dword ptr [rdi+28h], 2
0x180078821  jg      short loc_180078827
0x180078823  test    ebp, ebp
0x180078825  jz      short loc_180078839
0x180078827  mov     r8, rax
0x18007882a  lea     rcx, aSZ; "%s.%z"
0x180078831  mov     rdx, r12
0x180078834  call    sqlite3_mprintf
0x180078839  mov     r8, rax
0x18007883c  lea     rdx, aAccessToZIsPro; "access to %z is prohibited"
0x180078843  mov     rcx, rbx
0x180078846  call    sqlite3ErrorMsg
0x18007884b  mov     dword ptr [rbx+18h], 17h
0x180078852  jmp     short loc_180078872
0x180078854  test    esi, 0FFFFFFFDh
0x18007885a  jz      short loc_180078872
0x18007885c  lea     rdx, aAuthorizerMalf; "authorizer malfunction"
0x180078863  mov     rcx, rbx
0x180078866  call    sqlite3ErrorMsg
0x18007886b  mov     dword ptr [rbx+18h], 1
0x180078872  mov     eax, esi
0x180078874  add     rsp, 40h
0x180078878  pop     r15
0x18007887a  pop     r14
0x18007887c  pop     r12
0x18007887e  pop     rdi
0x18007887f  pop     rsi
0x180078880  pop     rbp
0x180078881  pop     rbx
0x180078882  retn
```
