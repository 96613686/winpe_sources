# sqlite3AuthReadCol

- ea: `0x14004be68`
- end: `0x14004bf53`
- name: `sqlite3AuthReadCol`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140037ce0`
- `0x14005b9d0`

## callees

- `0x14004be68`
- `0x1400560c4`
- `0x14008b8d0`
- `0x1400a8010`

## string_xrefs

- `0x14004bf0c`: `access to %z is prohibited`

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
          a1[46]);
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
0x14004be68  push    rbx
0x14004be6a  push    rbp
0x14004be6b  push    rsi
0x14004be6c  push    rdi
0x14004be6d  push    r12
0x14004be6f  push    r14
0x14004be71  push    r15
0x14004be73  sub     rsp, 40h
0x14004be77  mov     rdi, [rcx]
0x14004be7a  mov     r14, r8
0x14004be7d  movsxd  rbp, r9d
0x14004be80  mov     r15, rdx
0x14004be83  mov     rbx, rcx
0x14004be86  cmp     byte ptr [rdi+0C5h], 0
0x14004be8d  jz      short loc_14004BE96
0x14004be8f  xor     eax, eax
0x14004be91  jmp     loc_14004BF44
0x14004be96  mov     rax, [rdi+20h]
0x14004be9a  mov     rcx, rbp
0x14004be9d  shl     rcx, 5
0x14004bea1  mov     r9, r14
0x14004bea4  mov     r8, r15
0x14004bea7  mov     edx, 14h
0x14004beac  mov     r12, [rcx+rax]
0x14004beb0  mov     rcx, [rbx+170h]
0x14004beb7  mov     rax, [rdi+200h]
0x14004bebe  mov     [rsp+78h+var_50], rcx
0x14004bec3  mov     rcx, [rdi+208h]
0x14004beca  mov     [rsp+78h+var_58], r12
0x14004becf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004bed4  mov     esi, eax
0x14004bed6  cmp     eax, 1
0x14004bed9  jnz     short loc_14004BF24
0x14004bedb  mov     r8, r14
0x14004bede  lea     rcx, aSS_4; "%s.%s"
0x14004bee5  mov     rdx, r15
0x14004bee8  call    sqlite3_mprintf
0x14004beed  cmp     dword ptr [rdi+28h], 2
0x14004bef1  jg      short loc_14004BEF7
0x14004bef3  test    ebp, ebp
0x14004bef5  jz      short loc_14004BF09
0x14004bef7  mov     r8, rax
0x14004befa  lea     rcx, aSZ; "%s.%z"
0x14004bf01  mov     rdx, r12
0x14004bf04  call    sqlite3_mprintf
0x14004bf09  mov     r8, rax
0x14004bf0c  lea     rdx, aAccessToZIsPro; "access to %z is prohibited"
0x14004bf13  mov     rcx, rbx
0x14004bf16  call    sqlite3ErrorMsg
0x14004bf1b  mov     dword ptr [rbx+18h], 17h
0x14004bf22  jmp     short loc_14004BF42
0x14004bf24  test    esi, 0FFFFFFFDh
0x14004bf2a  jz      short loc_14004BF42
0x14004bf2c  lea     rdx, aAuthorizerMalf; "authorizer malfunction"
0x14004bf33  mov     rcx, rbx
0x14004bf36  call    sqlite3ErrorMsg
0x14004bf3b  mov     dword ptr [rbx+18h], 1
0x14004bf42  mov     eax, esi
0x14004bf44  add     rsp, 40h
0x14004bf48  pop     r15
0x14004bf4a  pop     r14
0x14004bf4c  pop     r12
0x14004bf4e  pop     rdi
0x14004bf4f  pop     rsi
0x14004bf50  pop     rbp
0x14004bf51  pop     rbx
0x14004bf52  retn
```
