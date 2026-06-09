# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000861c`
- end: `0x180008704`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006468`

## callees

- `0x18000207a`
- `0x18000861c`
- `0x180008f08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000867f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000867f`

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
0x18000861c  push    rbx
0x18000861e  push    rbp
0x18000861f  push    rsi
0x180008620  push    rdi
0x180008621  push    r14
0x180008623  push    r15
0x180008625  sub     rsp, 28h
0x180008629  mov     al, [rcx+2]
0x18000862c  xor     ebp, ebp
0x18000862e  mov     r9, [rdx]
0x180008631  mov     rdi, r8
0x180008634  mov     r15, rdx
0x180008637  mov     rsi, rcx
0x18000863a  cmp     al, 1
0x18000863c  jnz     short loc_18000865A
0x18000863e  lea     rbx, [r9+2]
0x180008642  cmp     rbx, r8
0x180008645  ja      loc_1800086D5
0x18000864b  test    r9, r9
0x18000864e  jz      short loc_18000867F
0x180008650  movzx   eax, word ptr [rcx+4]
0x180008654  mov     [r9], ax
0x180008658  jmp     short loc_180008695
0x18000865a  cmp     al, 2
0x18000865c  jnz     short loc_180008692
0x18000865e  lea     rbx, [r9+4]
0x180008662  cmp     rbx, rdi
0x180008665  ja      short loc_1800086D5
0x180008667  test    r9, r9
0x18000866a  jz      short loc_18000867F
0x18000866c  lea     rax, [rcx+4]
0x180008670  test    rax, rax
0x180008673  jz      short loc_18000867C
0x180008675  mov     eax, [rax]
0x180008677  mov     [r9], eax
0x18000867a  jmp     short loc_180008695
0x18000867c  mov     [r9], eax
0x18000867f  call    cs:__imp__o__errno
0x180008685  mov     dword ptr [rax], 16h
0x18000868b  call    _invalid_parameter_noinfo
0x180008690  jmp     short loc_180008695
0x180008692  mov     rbx, r9
0x180008695  cmp     [rsi], bp
0x180008698  jnz     short loc_1800086C3
0x18000869a  lea     r14, [rbx+2]
0x18000869e  cmp     r14, rdi
0x1800086a1  ja      short loc_1800086D5
0x1800086a3  lea     rbp, [rsi+8]
0x1800086a7  mov     rdx, rdi
0x1800086aa  sub     rdx, rbx; DestinationSize
0x1800086ad  mov     r8, rbp; Source
0x1800086b0  mov     r9d, 2; SourceSize
0x1800086b6  mov     rcx, rbx; Destination
0x1800086b9  call    memcpy_s
0x1800086be  mov     rbx, r14
0x1800086c1  jmp     short loc_1800086C7
0x1800086c3  lea     rbp, [rsi+8]
0x1800086c7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x1800086cc  lea     rax, [r9+rbx]
0x1800086d0  cmp     rax, rdi
0x1800086d3  jbe     short loc_1800086D9
0x1800086d5  xor     al, al
0x1800086d7  jmp     short loc_1800086F7
0x1800086d9  mov     r8, [rsi+18h]; Source
0x1800086dd  sub     rdi, rbx
0x1800086e0  mov     rdx, rdi; DestinationSize
0x1800086e3  mov     rcx, rbx; Destination
0x1800086e6  call    memcpy_s
0x1800086eb  movzx   ecx, word ptr [rbp+0]
0x1800086ef  mov     al, 1
0x1800086f1  add     rcx, rbx
0x1800086f4  mov     [r15], rcx
0x1800086f7  add     rsp, 28h
0x1800086fb  pop     r15
0x1800086fd  pop     r14
0x1800086ff  pop     rdi
0x180008700  pop     rsi
0x180008701  pop     rbp
0x180008702  pop     rbx
0x180008703  retn
```
