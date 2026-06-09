# ABO_WRAPPER::IsExemptFromAppPoolReadAccessCheck(ABO_NODE *,ACCESS_GRANTED *)

- ea: `0x18000eb58`
- end: `0x18000ec37`
- name: `?IsExemptFromAppPoolReadAccessCheck@ABO_WRAPPER@@AEAAHPEAVABO_NODE@@PEAW4ACCESS_GRANTED@@@Z`
- size: `223`
- prototype: `int(ABO_WRAPPER *__hidden this, struct ABO_NODE *, enum ACCESS_GRANTED *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000b770`

## callees

- `0x180009a14`
- `0x180009a60`
- `0x18000eb58`
- `0x18000ec40`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ebc0`
- `msvcrt!_wcsicmp` at `0x18000ebf8`
- `msvcrt!_wcsicmp` at `0x18000ebc0`
- `msvcrt!_wcsicmp` at `0x18000ebf8`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000eb76`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000eb76`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::IsExemptFromAppPoolReadAccessCheck(
        ABO_WRAPPER *this,
        struct ABO_NODE *a2,
        enum ACCESS_GRANTED *a3)
{
  const wchar_t *Str; // rsi
  ABO_NODE *v6; // rcx
  int IsTheLmNode; // eax
  __int64 result; // rax
  ABO_NODE *v9; // rbx

  if ( !a2 )
    return 0;
  Str = STRU::QueryStr((struct ABO_NODE *)((char *)a2 + 56));
  if ( *((_QWORD *)a2 + 2)
    && !(unsigned int)ABO_NODE::IsTheLmNode(a2)
    && !(unsigned int)ABO_NODE::IsTheW3svcNode(a2)
    && !(unsigned int)ABO_NODE::IsTheApppoolsNode(a2) )
  {
    if ( _wcsicmp(Str, L"FILTERS") )
    {
      if ( _wcsicmp(Str, L"MIMEMAP") )
        return 0;
      v9 = (ABO_NODE *)*((_QWORD *)a2 + 2);
      if ( !v9 )
        return 0;
      if ( (unsigned int)ABO_NODE::IsTheW3svcNode(v9) )
      {
LABEL_15:
        result = 1;
        *(_DWORD *)a3 = 1;
        return result;
      }
      IsTheLmNode = ABO_NODE::IsTheLmNode(v9);
    }
    else
    {
      v6 = (ABO_NODE *)*((_QWORD *)a2 + 2);
      if ( !v6 )
        return 0;
      IsTheLmNode = ABO_NODE::IsTheW3svcNode(v6);
    }
    if ( !IsTheLmNode )
      return 0;
    goto LABEL_15;
  }
  *(_DWORD *)a3 = 3;
  return 1;
}

```

## disassembly

```asm
0x18000eb58  mov     [rsp+arg_0], rbx
0x18000eb5d  mov     [rsp+arg_8], rsi
0x18000eb62  push    rdi
0x18000eb63  sub     rsp, 20h
0x18000eb67  mov     rdi, r8
0x18000eb6a  mov     rbx, rdx
0x18000eb6d  test    rdx, rdx
0x18000eb70  jz      short loc_18000EBDC
0x18000eb72  lea     rcx, [rdx+38h]
0x18000eb76  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18000eb7c  cmp     qword ptr [rbx+10h], 0
0x18000eb81  mov     rsi, rax
0x18000eb84  jz      loc_18000EC2A
0x18000eb8a  mov     rcx, rbx; this
0x18000eb8d  call    ?IsTheLmNode@ABO_NODE@@QEAAHXZ; ABO_NODE::IsTheLmNode(void)
0x18000eb92  test    eax, eax
0x18000eb94  jnz     loc_18000EC2A
0x18000eb9a  mov     rcx, rbx; this
0x18000eb9d  call    ?IsTheW3svcNode@ABO_NODE@@QEAAHXZ; ABO_NODE::IsTheW3svcNode(void)
0x18000eba2  test    eax, eax
0x18000eba4  jnz     loc_18000EC2A
0x18000ebaa  mov     rcx, rbx; this
0x18000ebad  call    ?IsTheApppoolsNode@ABO_NODE@@QEAAHXZ; ABO_NODE::IsTheApppoolsNode(void)
0x18000ebb2  test    eax, eax
0x18000ebb4  jnz     short loc_18000EC2A
0x18000ebb6  lea     rdx, aFilters; "FILTERS"
0x18000ebbd  mov     rcx, rsi; String1
0x18000ebc0  call    cs:__imp__wcsicmp
0x18000ebc6  test    eax, eax
0x18000ebc8  jnz     short loc_18000EBEE
0x18000ebca  mov     rcx, [rbx+10h]; this
0x18000ebce  test    rcx, rcx
0x18000ebd1  jz      short loc_18000EBDC
0x18000ebd3  call    ?IsTheW3svcNode@ABO_NODE@@QEAAHXZ; ABO_NODE::IsTheW3svcNode(void)
0x18000ebd8  test    eax, eax
0x18000ebda  jnz     short loc_18000EC21
0x18000ebdc  xor     eax, eax
0x18000ebde  mov     rbx, [rsp+28h+arg_0]
0x18000ebe3  mov     rsi, [rsp+28h+arg_8]
0x18000ebe8  add     rsp, 20h
0x18000ebec  pop     rdi
0x18000ebed  retn
0x18000ebee  lea     rdx, aMimemap; "MIMEMAP"
0x18000ebf5  mov     rcx, rsi; String1
0x18000ebf8  call    cs:__imp__wcsicmp
0x18000ebfe  test    eax, eax
0x18000ec00  jnz     short loc_18000EBDC
0x18000ec02  mov     rbx, [rbx+10h]
0x18000ec06  test    rbx, rbx
0x18000ec09  jz      short loc_18000EBDC
0x18000ec0b  mov     rcx, rbx; this
0x18000ec0e  call    ?IsTheW3svcNode@ABO_NODE@@QEAAHXZ; ABO_NODE::IsTheW3svcNode(void)
0x18000ec13  test    eax, eax
0x18000ec15  jnz     short loc_18000EC21
0x18000ec17  mov     rcx, rbx; this
0x18000ec1a  call    ?IsTheLmNode@ABO_NODE@@QEAAHXZ; ABO_NODE::IsTheLmNode(void)
0x18000ec1f  jmp     short loc_18000EBD8
0x18000ec21  mov     eax, 1
0x18000ec26  mov     [rdi], eax
0x18000ec28  jmp     short loc_18000EBDE
0x18000ec2a  mov     dword ptr [rdi], 3
0x18000ec30  mov     eax, 1
0x18000ec35  jmp     short loc_18000EBDE
```
