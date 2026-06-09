# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800085fc`
- end: `0x1800086e4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800069b4`

## callees

- `0x180002652`
- `0x1800085fc`
- `0x180008a94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000865f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000865f`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int8 *v4; // r9
  unsigned __int8 *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    if ( v4 )
    {
      *(_WORD *)v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    if ( v4 )
    {
      v9 = (_DWORD *)((char *)this + 4);
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v4 = *v9;
        goto LABEL_13;
      }
      *(_DWORD *)v4 = (_DWORD)v9;
    }
    goto LABEL_11;
  }
  v8 = *a2;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v8 + 2 <= a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - v8, (char *)this + 8, 2u);
      v8 += 2;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( &v8[v11] > a3 )
    return 0;
  memcpy_s(v8, a3 - v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = &v8[*v10];
  return result;
}

```

## disassembly

```asm
0x1800085fc  push    rbx
0x1800085fe  push    rbp
0x1800085ff  push    rsi
0x180008600  push    rdi
0x180008601  push    r14
0x180008603  push    r15
0x180008605  sub     rsp, 28h
0x180008609  mov     al, [rcx+2]
0x18000860c  xor     ebp, ebp
0x18000860e  mov     r9, [rdx]
0x180008611  mov     rdi, r8
0x180008614  mov     r15, rdx
0x180008617  mov     rsi, rcx
0x18000861a  cmp     al, 1
0x18000861c  jnz     short loc_18000863A
0x18000861e  lea     rbx, [r9+2]
0x180008622  cmp     rbx, r8
0x180008625  ja      loc_1800086B5
0x18000862b  test    r9, r9
0x18000862e  jz      short loc_18000865F
0x180008630  movzx   eax, word ptr [rcx+4]
0x180008634  mov     [r9], ax
0x180008638  jmp     short loc_180008675
0x18000863a  cmp     al, 2
0x18000863c  jnz     short loc_180008672
0x18000863e  lea     rbx, [r9+4]
0x180008642  cmp     rbx, rdi
0x180008645  ja      short loc_1800086B5
0x180008647  test    r9, r9
0x18000864a  jz      short loc_18000865F
0x18000864c  lea     rax, [rcx+4]
0x180008650  test    rax, rax
0x180008653  jz      short loc_18000865C
0x180008655  mov     eax, [rax]
0x180008657  mov     [r9], eax
0x18000865a  jmp     short loc_180008675
0x18000865c  mov     [r9], eax
0x18000865f  call    cs:__imp__o__errno
0x180008665  mov     dword ptr [rax], 16h
0x18000866b  call    _invalid_parameter_noinfo
0x180008670  jmp     short loc_180008675
0x180008672  mov     rbx, r9
0x180008675  cmp     [rsi], bp
0x180008678  jnz     short loc_1800086A3
0x18000867a  lea     r14, [rbx+2]
0x18000867e  cmp     r14, rdi
0x180008681  ja      short loc_1800086B5
0x180008683  lea     rbp, [rsi+8]
0x180008687  mov     rdx, rdi
0x18000868a  sub     rdx, rbx; DestinationSize
0x18000868d  mov     r8, rbp; Source
0x180008690  mov     r9d, 2; SourceSize
0x180008696  mov     rcx, rbx; Destination
0x180008699  call    memcpy_s
0x18000869e  mov     rbx, r14
0x1800086a1  jmp     short loc_1800086A7
0x1800086a3  lea     rbp, [rsi+8]
0x1800086a7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x1800086ac  lea     rax, [r9+rbx]
0x1800086b0  cmp     rax, rdi
0x1800086b3  jbe     short loc_1800086B9
0x1800086b5  xor     al, al
0x1800086b7  jmp     short loc_1800086D7
0x1800086b9  mov     r8, [rsi+18h]; Source
0x1800086bd  sub     rdi, rbx
0x1800086c0  mov     rdx, rdi; DestinationSize
0x1800086c3  mov     rcx, rbx; Destination
0x1800086c6  call    memcpy_s
0x1800086cb  movzx   ecx, word ptr [rbp+0]
0x1800086cf  mov     al, 1
0x1800086d1  add     rcx, rbx
0x1800086d4  mov     [r15], rcx
0x1800086d7  add     rsp, 28h
0x1800086db  pop     r15
0x1800086dd  pop     r14
0x1800086df  pop     rdi
0x1800086e0  pop     rsi
0x1800086e1  pop     rbp
0x1800086e2  pop     rbx
0x1800086e3  retn
```
