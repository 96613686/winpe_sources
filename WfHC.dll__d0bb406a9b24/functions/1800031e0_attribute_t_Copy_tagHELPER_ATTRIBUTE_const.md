# _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)

- ea: `0x1800031e0`
- end: `0x180003397`
- name: `?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(struct tagHELPER_ATTRIBUTE *this, const struct tagHELPER_ATTRIBUTE *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800033a0`
- `0x180006ebc`
- `0x1800073b0`

## callees

- `0x180002576`
- `0x180003170`
- `0x1800031e0`
- `0x180005bd0`
- `0x180005ce0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000329e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000329e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000325c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003271`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000334e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000325c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003271`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000334e`

## pseudocode

```c
__int64 __fastcall _attribute_t::Copy(struct tagHELPER_ATTRIBUTE *this, const struct tagHELPER_ATTRIBUTE *a2)
{
  ATTRIBUTE_TYPE type; // edi
  int v6; // edi
  ATTRIBUTE_TYPE v7; // eax
  LONGLONG *p_Int64; // rdi
  unsigned int v9; // eax
  size_t v10; // rbp
  BYTE *v11; // rax
  const unsigned __int16 *pwszName; // rdi

  if ( !a2 )
    return 2147942487LL;
  if ( this != a2 )
  {
    type = a2->type;
    _attribute_t::Clear((_attribute_t *)this);
    if ( type == AT_STRING )
    {
      v6 = _attribute_t::SetValue((_attribute_t *)this, a2->PWStr);
      if ( v6 < 0 )
      {
LABEL_22:
        _attribute_t::Clear((_attribute_t *)this);
        return (unsigned int)v6;
      }
    }
    else if ( type == AT_OCTET_STRING )
    {
      v7 = this->type;
      p_Int64 = &a2->Int64;
      if ( v7 == AT_STRING )
      {
        CoTaskMemFree(this->PWStr);
        this->Int64 = 0;
      }
      else if ( v7 == AT_OCTET_STRING )
      {
        CoTaskMemFree(this->OctetString.lpValue);
        this->OctetString.lpValue = 0;
        this->Boolean = 0;
      }
      if ( a2 != (const struct tagHELPER_ATTRIBUTE *)-16LL )
      {
        if ( this == (struct tagHELPER_ATTRIBUTE *)-16LL || (v9 = *(_DWORD *)p_Int64, *(_DWORD *)p_Int64 >= 0xFFFFu) )
        {
          this->type = AT_INVALID;
          _attribute_t::Clear((_attribute_t *)this);
          return 2147942487LL;
        }
        v10 = v9;
        v11 = (BYTE *)CoTaskMemAlloc(v9);
        this->OctetString.lpValue = v11;
        if ( !v11 )
        {
          this->type = AT_INVALID;
          _attribute_t::Clear((_attribute_t *)this);
          return 2147942414LL;
        }
        memcpy_0(v11, a2->OctetString.lpValue, v10);
        this->Boolean = *(_DWORD *)p_Int64;
        this->type = AT_OCTET_STRING;
      }
    }
    else
    {
      *(_OWORD *)&this->pwszName = *(_OWORD *)&a2->pwszName;
      *(_OWORD *)&this->Boolean = *(_OWORD *)&a2->Boolean;
      *((_OWORD *)&this->OctetString + 1) = *((_OWORD *)&a2->OctetString + 1);
      *((_OWORD *)&this->OctetString + 2) = *((_OWORD *)&a2->OctetString + 2);
      *((_OWORD *)&this->OctetString + 3) = *((_OWORD *)&a2->OctetString + 3);
      *((_OWORD *)&this->OctetString + 4) = *((_OWORD *)&a2->OctetString + 4);
      *((_OWORD *)&this->OctetString + 5) = *((_OWORD *)&a2->OctetString + 5);
      *((_OWORD *)&this->OctetString + 6) = *((_OWORD *)&a2->OctetString + 6);
      *((_OWORD *)&this->OctetString + 7) = *((_OWORD *)&a2->OctetString + 7);
    }
    this->pwszName = 0;
    pwszName = a2->pwszName;
    CoTaskMemFree(0);
    this->pwszName = 0;
    if ( pwszName )
    {
      v6 = StringCchCopyWithAlloc(&this->pwszName, 0xFFFFu, pwszName);
      if ( v6 < 0 )
        goto LABEL_22;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800031e0  push    rbx
0x1800031e2  push    rsi
0x1800031e3  push    rdi
0x1800031e4  sub     rsp, 20h
0x1800031e8  mov     rsi, rdx
0x1800031eb  mov     rbx, rcx
0x1800031ee  test    rdx, rdx
0x1800031f1  jnz     short loc_180003200
0x1800031f3  mov     eax, 80070057h
0x1800031f8  add     rsp, 20h
0x1800031fc  pop     rdi
0x1800031fd  pop     rsi
0x1800031fe  pop     rbx
0x1800031ff  retn
0x180003200  mov     [rsp+38h+arg_0], rbp
0x180003205  mov     [rsp+38h+arg_8], r14
0x18000320a  mov     [rsp+38h+arg_10], r15
0x18000320f  cmp     rbx, rsi
0x180003212  jz      loc_18000337E
0x180003218  mov     edi, [rdx+8]
0x18000321b  call    ?Clear@_attribute_t@@QEAAXXZ; _attribute_t::Clear(void)
0x180003220  xor     r15d, r15d
0x180003223  cmp     edi, 0Ah
0x180003226  jnz     short loc_180003243
0x180003228  mov     rdx, [rsi+10h]; unsigned __int16 *
0x18000322c  mov     rcx, rbx; this
0x18000322f  call    ?SetValue@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetValue(ushort const *)
0x180003234  mov     edi, eax
0x180003236  test    eax, eax
0x180003238  js      loc_180003372
0x18000323e  jmp     loc_180003346
0x180003243  cmp     edi, 0Eh
0x180003246  jnz     loc_1800032FA
0x18000324c  mov     eax, [rbx+8]
0x18000324f  lea     rdi, [rsi+10h]
0x180003253  cmp     eax, 0Ah
0x180003256  jnz     short loc_180003268
0x180003258  mov     rcx, [rbx+10h]; pv
0x18000325c  call    cs:__imp_CoTaskMemFree
0x180003262  mov     [rbx+10h], r15
0x180003266  jmp     short loc_18000327F
0x180003268  cmp     eax, 0Eh
0x18000326b  jnz     short loc_18000327F
0x18000326d  mov     rcx, [rbx+18h]; pv
0x180003271  call    cs:__imp_CoTaskMemFree
0x180003277  mov     [rbx+18h], r15
0x18000327b  mov     [rbx+10h], r15d
0x18000327f  test    rdi, rdi
0x180003282  jz      loc_180003346
0x180003288  lea     r14, [rbx+10h]
0x18000328c  test    r14, r14
0x18000328f  jz      short loc_1800032E2
0x180003291  mov     eax, [rdi]
0x180003293  cmp     eax, 0FFFFh
0x180003298  jnb     short loc_1800032E2
0x18000329a  mov     ecx, eax; cb
0x18000329c  mov     ebp, eax
0x18000329e  call    cs:__imp_CoTaskMemAlloc
0x1800032a4  mov     [r14+8], rax
0x1800032a8  test    rax, rax
0x1800032ab  jnz     short loc_1800032C5
0x1800032ad  mov     rcx, rbx; this
0x1800032b0  mov     [rbx+8], r15d
0x1800032b4  mov     edi, 8007000Eh
0x1800032b9  call    ?Clear@_attribute_t@@QEAAXXZ; _attribute_t::Clear(void)
0x1800032be  mov     eax, edi
0x1800032c0  jmp     loc_180003380
0x1800032c5  mov     rdx, [rdi+8]; Src
0x1800032c9  mov     r8, rbp; Size
0x1800032cc  mov     rcx, rax; void *
0x1800032cf  call    memcpy_0
0x1800032d4  mov     eax, [rdi]
0x1800032d6  mov     [r14], eax
0x1800032d9  mov     dword ptr [rbx+8], 0Eh
0x1800032e0  jmp     short loc_180003346
0x1800032e2  mov     rcx, rbx; this
0x1800032e5  mov     [rbx+8], r15d
0x1800032e9  mov     edi, 80070057h
0x1800032ee  call    ?Clear@_attribute_t@@QEAAXXZ; _attribute_t::Clear(void)
0x1800032f3  mov     eax, edi
0x1800032f5  jmp     loc_180003380
0x1800032fa  movups  xmm0, xmmword ptr [rsi]
0x1800032fd  movups  xmmword ptr [rbx], xmm0
0x180003300  movups  xmm1, xmmword ptr [rsi+10h]
0x180003304  movups  xmmword ptr [rbx+10h], xmm1
0x180003308  movups  xmm0, xmmword ptr [rsi+20h]
0x18000330c  movups  xmmword ptr [rbx+20h], xmm0
0x180003310  movups  xmm1, xmmword ptr [rsi+30h]
0x180003314  movups  xmmword ptr [rbx+30h], xmm1
0x180003318  movups  xmm0, xmmword ptr [rsi+40h]
0x18000331c  movups  xmmword ptr [rbx+40h], xmm0
0x180003320  movups  xmm1, xmmword ptr [rsi+50h]
0x180003324  movups  xmmword ptr [rbx+50h], xmm1
0x180003328  movups  xmm0, xmmword ptr [rsi+60h]
0x18000332c  movups  xmmword ptr [rbx+60h], xmm0
0x180003330  movups  xmm1, xmmword ptr [rsi+70h]
0x180003334  movups  xmmword ptr [rbx+70h], xmm1
0x180003338  movups  xmm0, xmmword ptr [rsi+80h]
0x18000333f  movups  xmmword ptr [rbx+80h], xmm0
0x180003346  mov     [rbx], r15
0x180003349  xor     ecx, ecx; pv
0x18000334b  mov     rdi, [rsi]
0x18000334e  call    cs:__imp_CoTaskMemFree
0x180003354  mov     [rbx], r15
0x180003357  test    rdi, rdi
0x18000335a  jz      short loc_18000337E
0x18000335c  mov     r8, rdi; unsigned __int16 *
0x18000335f  mov     edx, 0FFFFh; unsigned __int64
0x180003364  mov     rcx, rbx; unsigned __int16 **
0x180003367  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000336c  mov     edi, eax
0x18000336e  test    eax, eax
0x180003370  jns     short loc_18000337E
0x180003372  mov     rcx, rbx; this
0x180003375  call    ?Clear@_attribute_t@@QEAAXXZ; _attribute_t::Clear(void)
0x18000337a  mov     eax, edi
0x18000337c  jmp     short loc_180003380
0x18000337e  xor     eax, eax
0x180003380  mov     r14, [rsp+38h+arg_8]
0x180003385  mov     rbp, [rsp+38h+arg_0]
0x18000338a  mov     r15, [rsp+38h+arg_10]
0x18000338f  add     rsp, 20h
0x180003393  pop     rdi
0x180003394  pop     rsi
0x180003395  pop     rbx
0x180003396  retn
```
