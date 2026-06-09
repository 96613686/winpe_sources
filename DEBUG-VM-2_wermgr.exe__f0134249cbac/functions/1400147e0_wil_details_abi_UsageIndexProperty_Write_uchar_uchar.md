# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1400147e0`
- end: `0x1400148c8`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012970`

## callees

- `0x140002f0e`
- `0x1400147e0`
- `0x140014d88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014843`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014843`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  _WORD *v4; // r9
  _WORD *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 1;
    if ( v4 + 1 > (_WORD *)a3 )
      return 0;
    if ( v4 )
    {
      *v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > (_WORD *)a3 )
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
    if ( v8 + 1 <= (_WORD *)a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - (unsigned __int8 *)v8, (char *)this + 8, 2u);
      ++v8;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( (unsigned __int8 *)((char *)v8 + v11) > a3 )
    return 0;
  memcpy_s(v8, a3 - (unsigned __int8 *)v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = (unsigned __int8 *)v8 + *v10;
  return result;
}

```

## disassembly

```asm
0x1400147e0  push    rbx
0x1400147e2  push    rbp
0x1400147e3  push    rsi
0x1400147e4  push    rdi
0x1400147e5  push    r14
0x1400147e7  push    r15
0x1400147e9  sub     rsp, 28h
0x1400147ed  mov     al, [rcx+2]
0x1400147f0  xor     ebp, ebp
0x1400147f2  mov     r9, [rdx]
0x1400147f5  mov     rdi, r8
0x1400147f8  mov     r15, rdx
0x1400147fb  mov     rsi, rcx
0x1400147fe  cmp     al, 1
0x140014800  jnz     short loc_14001481E
0x140014802  lea     rbx, [r9+2]
0x140014806  cmp     rbx, r8
0x140014809  ja      loc_140014899
0x14001480f  test    r9, r9
0x140014812  jz      short loc_140014843
0x140014814  movzx   eax, word ptr [rcx+4]
0x140014818  mov     [r9], ax
0x14001481c  jmp     short loc_140014859
0x14001481e  cmp     al, 2
0x140014820  jnz     short loc_140014856
0x140014822  lea     rbx, [r9+4]
0x140014826  cmp     rbx, rdi
0x140014829  ja      short loc_140014899
0x14001482b  test    r9, r9
0x14001482e  jz      short loc_140014843
0x140014830  lea     rax, [rcx+4]
0x140014834  test    rax, rax
0x140014837  jz      short loc_140014840
0x140014839  mov     eax, [rax]
0x14001483b  mov     [r9], eax
0x14001483e  jmp     short loc_140014859
0x140014840  mov     [r9], eax
0x140014843  call    cs:__imp__o__errno
0x140014849  mov     dword ptr [rax], 16h
0x14001484f  call    _invalid_parameter_noinfo
0x140014854  jmp     short loc_140014859
0x140014856  mov     rbx, r9
0x140014859  cmp     [rsi], bp
0x14001485c  jnz     short loc_140014887
0x14001485e  lea     r14, [rbx+2]
0x140014862  cmp     r14, rdi
0x140014865  ja      short loc_140014899
0x140014867  lea     rbp, [rsi+8]
0x14001486b  mov     rdx, rdi
0x14001486e  sub     rdx, rbx; DestinationSize
0x140014871  mov     r8, rbp; Source
0x140014874  mov     r9d, 2; SourceSize
0x14001487a  mov     rcx, rbx; Destination
0x14001487d  call    memcpy_s
0x140014882  mov     rbx, r14
0x140014885  jmp     short loc_14001488B
0x140014887  lea     rbp, [rsi+8]
0x14001488b  movzx   r9d, word ptr [rbp+0]; SourceSize
0x140014890  lea     rax, [r9+rbx]
0x140014894  cmp     rax, rdi
0x140014897  jbe     short loc_14001489D
0x140014899  xor     al, al
0x14001489b  jmp     short loc_1400148BB
0x14001489d  mov     r8, [rsi+18h]; Source
0x1400148a1  sub     rdi, rbx
0x1400148a4  mov     rdx, rdi; DestinationSize
0x1400148a7  mov     rcx, rbx; Destination
0x1400148aa  call    memcpy_s
0x1400148af  movzx   ecx, word ptr [rbp+0]
0x1400148b3  mov     al, 1
0x1400148b5  add     rcx, rbx
0x1400148b8  mov     [r15], rcx
0x1400148bb  add     rsp, 28h
0x1400148bf  pop     r15
0x1400148c1  pop     r14
0x1400148c3  pop     rdi
0x1400148c4  pop     rsi
0x1400148c5  pop     rbp
0x1400148c6  pop     rbx
0x1400148c7  retn
```
