# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1400044e8`
- end: `0x1400045c1`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1400035bc`
- `0x140003720`
- `0x14000417c`
- `0x1400043b8`
- `0x14000c8fc`

## callees

- `0x1400044e8`
- `0x140006030`
- `0x14000959e`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140004524`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140004524`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  unsigned __int16 *v3; // rax
  unsigned __int16 *v7; // rbx
  unsigned __int16 v8; // cx
  __int16 v9; // ax
  unsigned __int8 *v10; // rcx
  bool result; // al

  v3 = (unsigned __int16 *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v3 + 1;
    if ( v3 + 1 > (unsigned __int16 *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      v8 = *v3;
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
      invalid_parameter_noinfo();
      v8 = 0;
    }
    *((_DWORD *)this + 1) = v8;
  }
  else if ( *((_BYTE *)this + 2) == 2 )
  {
    v7 = v3 + 2;
    if ( v3 + 2 > (unsigned __int16 *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    memcpy_s((char *)this + 4, 4u, v3, 4u);
  }
  else
  {
    v7 = (unsigned __int16 *)*a2;
  }
  v9 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v9 )
    goto LABEL_14;
  if ( v7 + 1 > (unsigned __int16 *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7++, 2u);
LABEL_14:
  v10 = (unsigned __int8 *)v7 + *((unsigned __int16 *)this + 4);
  if ( v10 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v10;
  return result;
}

```

## disassembly

```asm
0x1400044e8  push    rbx
0x1400044ea  push    rbp
0x1400044eb  push    rsi
0x1400044ec  push    rdi
0x1400044ed  push    r14
0x1400044ef  push    r15
0x1400044f1  sub     rsp, 28h
0x1400044f5  mov     rax, [rdx]
0x1400044f8  xor     ebp, ebp
0x1400044fa  cmp     byte ptr [rcx+2], 1
0x1400044fe  mov     rsi, r8
0x140004501  mov     r15, rdx
0x140004504  mov     rdi, rcx
0x140004507  jnz     short loc_14000453F
0x140004509  lea     rbx, [rax+2]
0x14000450d  cmp     rbx, r8
0x140004510  ja      loc_1400045A7
0x140004516  mov     [rcx+10h], rax
0x14000451a  test    rax, rax
0x14000451d  jz      short loc_140004524
0x14000451f  movzx   ecx, word ptr [rax]
0x140004522  jmp     short loc_140004537
0x140004524  call    cs:__imp__o__errno
0x14000452a  mov     dword ptr [rax], 16h
0x140004530  call    _invalid_parameter_noinfo
0x140004535  mov     ecx, ebp
0x140004537  movzx   eax, cx
0x14000453a  mov     [rdi+4], eax
0x14000453d  jmp     short loc_14000456B
0x14000453f  cmp     byte ptr [rcx+2], 2
0x140004543  jnz     short loc_140004568
0x140004545  lea     rbx, [rax+4]
0x140004549  cmp     rbx, rsi
0x14000454c  ja      short loc_1400045A7
0x14000454e  mov     edx, 4; DestinationSize
0x140004553  mov     [rcx+10h], rax
0x140004557  mov     r9d, edx; SourceSize
0x14000455a  add     rcx, 4; Destination
0x14000455e  mov     r8, rax; Source
0x140004561  call    memcpy_s
0x140004566  jmp     short loc_14000456B
0x140004568  mov     rbx, rax
0x14000456b  movzx   eax, word ptr [rdi]
0x14000456e  lea     r14, [rdi+8]
0x140004572  mov     [r14], ax
0x140004576  test    ax, ax
0x140004579  jnz     short loc_14000459B
0x14000457b  lea     rbp, [rbx+2]
0x14000457f  cmp     rbp, rsi
0x140004582  ja      short loc_1400045A7
0x140004584  mov     r9d, 2; SourceSize
0x14000458a  mov     r8, rbx; Source
0x14000458d  mov     edx, r9d; DestinationSize
0x140004590  mov     rcx, r14; Destination
0x140004593  call    memcpy_s
0x140004598  mov     rbx, rbp
0x14000459b  movzx   ecx, word ptr [r14]
0x14000459f  add     rcx, rbx
0x1400045a2  cmp     rcx, rsi
0x1400045a5  jbe     short loc_1400045AB
0x1400045a7  xor     al, al
0x1400045a9  jmp     short loc_1400045B4
0x1400045ab  mov     [rdi+18h], rbx
0x1400045af  mov     al, 1
0x1400045b1  mov     [r15], rcx
0x1400045b4  add     rsp, 28h
0x1400045b8  pop     r15
0x1400045ba  pop     r14
0x1400045bc  pop     rdi
0x1400045bd  pop     rsi
0x1400045be  pop     rbp
0x1400045bf  pop     rbx
0x1400045c0  retn
```
