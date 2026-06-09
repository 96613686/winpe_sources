# _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)

- ea: `0x18000b8ac`
- end: `0x18000baff`
- name: `?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z`
- size: `595`
- prototype: `__int64 __fastcall(unsigned __int16 **this, const struct tagHELPER_ATTRIBUTE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000bb08`
- `0x18000bfe0`

## callees

- `0x180002596`
- `0x18000b8ac`
- `0x18000c244`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b8e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b8ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b910`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b947`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b95c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bab0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b8e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b8ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b910`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b947`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b95c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bab0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b9e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b9e6`

## pseudocode

```c
__int64 __fastcall _attribute_t::Copy(struct tagHELPER_ATTRIBUTE *this, const struct tagHELPER_ATTRIBUTE *a2)
{
  ATTRIBUTE_TYPE type; // esi
  __int64 v6; // r15
  LPVOID *p_PWStr; // rdi
  __int64 v8; // rcx
  unsigned __int16 **v9; // rax
  const unsigned __int16 *PWStr; // rsi
  int v11; // esi
  LONGLONG *p_Int64; // rsi
  SIZE_T v13; // rbp
  unsigned __int16 *v14; // rax
  const unsigned __int16 *pwszName; // rsi

  if ( !a2 )
    return 2147942487LL;
  if ( this == a2 )
    return 0;
  type = a2->type;
  if ( this->type == AT_STRING )
  {
    CoTaskMemFree(this->PWStr);
    this->Int64 = 0;
  }
  else if ( this->type == AT_OCTET_STRING )
  {
    CoTaskMemFree(this->OctetString.lpValue);
    this->OctetString.lpValue = 0;
    this->Boolean = 0;
  }
  CoTaskMemFree(this->pwszName);
  v6 = 128;
  this->pwszName = 0;
  p_PWStr = (LPVOID *)&this->PWStr;
  v8 = 128;
  v9 = &this->PWStr;
  do
  {
    *(_BYTE *)v9 = 0;
    v9 = (unsigned __int16 **)((char *)v9 + 1);
    --v8;
  }
  while ( v8 );
  if ( type != AT_STRING )
  {
    if ( type != AT_OCTET_STRING )
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
      goto LABEL_32;
    }
    p_Int64 = &a2->Int64;
    if ( this->type == AT_STRING )
    {
      CoTaskMemFree(*p_PWStr);
      *p_PWStr = 0;
    }
    else if ( this->type == AT_OCTET_STRING )
    {
      CoTaskMemFree(this->OctetString.lpValue);
      this->OctetString.lpValue = 0;
      *(_DWORD *)p_PWStr = 0;
    }
    if ( a2 != (const struct tagHELPER_ATTRIBUTE *)-16LL )
    {
      if ( this == (struct tagHELPER_ATTRIBUTE *)-16LL || *(_DWORD *)p_Int64 >= 0xFFFFu )
      {
        v11 = -2147024809;
      }
      else
      {
        v13 = *(unsigned int *)p_Int64;
        v14 = (unsigned __int16 *)CoTaskMemAlloc(v13);
        this->OctetString.lpValue = (BYTE *)v14;
        if ( v14 )
        {
          memcpy_0(v14, a2->OctetString.lpValue, v13);
          *(_DWORD *)p_PWStr = *(_DWORD *)p_Int64;
          this->type = AT_OCTET_STRING;
          goto LABEL_32;
        }
        v11 = -2147024882;
      }
      goto LABEL_28;
    }
LABEL_32:
    this->pwszName = 0;
    pwszName = a2->pwszName;
    CoTaskMemFree(0);
    this->pwszName = 0;
    if ( pwszName )
    {
      v11 = StringCchCopyWithAlloc(&this->pwszName, 0xFFFFu, pwszName);
      if ( v11 < 0 )
        goto LABEL_34;
    }
    return 0;
  }
  PWStr = a2->PWStr;
  if ( this->type == AT_STRING )
  {
    CoTaskMemFree(*p_PWStr);
    *p_PWStr = 0;
  }
  else if ( this->type == AT_OCTET_STRING )
  {
    CoTaskMemFree(this->OctetString.lpValue);
    this->OctetString.lpValue = 0;
    *(_DWORD *)p_PWStr = 0;
  }
  if ( !PWStr )
    goto LABEL_32;
  v11 = StringCchCopyWithAlloc(&this->PWStr, 0xFFFFu, PWStr);
  if ( v11 >= 0 )
  {
    this->type = AT_STRING;
    goto LABEL_32;
  }
LABEL_28:
  this->type = AT_INVALID;
LABEL_34:
  if ( this->type == AT_STRING )
  {
    CoTaskMemFree(*p_PWStr);
    *p_PWStr = 0;
  }
  else if ( this->type == AT_OCTET_STRING )
  {
    CoTaskMemFree(this->OctetString.lpValue);
    this->OctetString.lpValue = 0;
    *(_DWORD *)p_PWStr = 0;
  }
  CoTaskMemFree(this->pwszName);
  this->pwszName = 0;
  do
  {
    *(_BYTE *)p_PWStr = 0;
    p_PWStr = (LPVOID *)((char *)p_PWStr + 1);
    --v6;
  }
  while ( v6 );
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000b8ac  push    rbx
0x18000b8ae  push    rbp
0x18000b8af  push    rsi
0x18000b8b0  push    rdi
0x18000b8b1  push    r12
0x18000b8b3  push    r14
0x18000b8b5  push    r15
0x18000b8b7  sub     rsp, 20h
0x18000b8bb  xor     r12d, r12d
0x18000b8be  mov     r14, rdx
0x18000b8c1  mov     rbx, rcx
0x18000b8c4  test    rdx, rdx
0x18000b8c7  jnz     short loc_18000B8D3
0x18000b8c9  mov     eax, 80070057h
0x18000b8ce  jmp     loc_18000BAF0
0x18000b8d3  cmp     rbx, r14
0x18000b8d6  jz      loc_18000BAEE
0x18000b8dc  cmp     dword ptr [rcx+8], 0Ah
0x18000b8e0  mov     esi, [rdx+8]
0x18000b8e3  jnz     short loc_18000B8F5
0x18000b8e5  mov     rcx, [rcx+10h]; pv
0x18000b8e9  call    cs:__imp_CoTaskMemFree
0x18000b8ef  mov     [rbx+10h], r12
0x18000b8f3  jmp     short loc_18000B90D
0x18000b8f5  cmp     dword ptr [rcx+8], 0Eh
0x18000b8f9  jnz     short loc_18000B90D
0x18000b8fb  mov     rcx, [rcx+18h]; pv
0x18000b8ff  call    cs:__imp_CoTaskMemFree
0x18000b905  mov     [rbx+18h], r12
0x18000b909  mov     [rbx+10h], r12d
0x18000b90d  mov     rcx, [rbx]; pv
0x18000b910  call    cs:__imp_CoTaskMemFree
0x18000b916  mov     r15d, 80h
0x18000b91c  mov     [rbx], r12
0x18000b91f  lea     rdi, [rbx+10h]
0x18000b923  mov     ecx, r15d
0x18000b926  mov     rax, rdi
0x18000b929  mov     [rax], r12b
0x18000b92c  inc     rax
0x18000b92f  sub     rcx, 1
0x18000b933  jnz     short loc_18000B929
0x18000b935  cmp     esi, 0Ah
0x18000b938  jnz     short loc_18000B994
0x18000b93a  cmp     dword ptr [rbx+8], 0Ah
0x18000b93e  mov     rsi, [r14+10h]
0x18000b942  jnz     short loc_18000B952
0x18000b944  mov     rcx, [rdi]; pv
0x18000b947  call    cs:__imp_CoTaskMemFree
0x18000b94d  mov     [rdi], r12
0x18000b950  jmp     short loc_18000B969
0x18000b952  cmp     dword ptr [rbx+8], 0Eh
0x18000b956  jnz     short loc_18000B969
0x18000b958  mov     rcx, [rbx+18h]; pv
0x18000b95c  call    cs:__imp_CoTaskMemFree
0x18000b962  mov     [rbx+18h], r12
0x18000b966  mov     [rdi], r12d
0x18000b969  test    rsi, rsi
0x18000b96c  jz      loc_18000BA7B
0x18000b972  mov     r8, rsi; unsigned __int16 *
0x18000b975  mov     edx, 0FFFFh; unsigned __int64
0x18000b97a  mov     rcx, rdi; unsigned __int16 **
0x18000b97d  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000b982  mov     esi, eax
0x18000b984  test    eax, eax
0x18000b986  js      short loc_18000B9FA
0x18000b988  mov     dword ptr [rbx+8], 0Ah
0x18000b98f  jmp     loc_18000BA7B
0x18000b994  cmp     esi, 0Eh
0x18000b997  jnz     loc_18000BA26
0x18000b99d  cmp     dword ptr [rbx+8], 0Ah
0x18000b9a1  lea     rsi, [r14+10h]
0x18000b9a5  jnz     short loc_18000B9B5
0x18000b9a7  mov     rcx, [rdi]; pv
0x18000b9aa  call    cs:__imp_CoTaskMemFree
0x18000b9b0  mov     [rdi], r12
0x18000b9b3  jmp     short loc_18000B9CC
0x18000b9b5  cmp     dword ptr [rbx+8], 0Eh
0x18000b9b9  jnz     short loc_18000B9CC
0x18000b9bb  mov     rcx, [rbx+18h]; pv
0x18000b9bf  call    cs:__imp_CoTaskMemFree
0x18000b9c5  mov     [rbx+18h], r12
0x18000b9c9  mov     [rdi], r12d
0x18000b9cc  test    rsi, rsi
0x18000b9cf  jz      loc_18000BA7B
0x18000b9d5  test    rdi, rdi
0x18000b9d8  jz      short loc_18000BA1F
0x18000b9da  cmp     dword ptr [rsi], 0FFFFh
0x18000b9e0  jnb     short loc_18000BA1F
0x18000b9e2  mov     ebp, [rsi]
0x18000b9e4  mov     ecx, ebp; cb
0x18000b9e6  call    cs:__imp_CoTaskMemAlloc
0x18000b9ec  mov     [rdi+8], rax
0x18000b9f0  test    rax, rax
0x18000b9f3  jnz     short loc_18000BA03
0x18000b9f5  mov     esi, 8007000Eh
0x18000b9fa  mov     [rbx+8], r12d
0x18000b9fe  jmp     loc_18000BAA7
0x18000ba03  mov     rdx, [rsi+8]; Src
0x18000ba07  mov     r8, rbp; Size
0x18000ba0a  mov     rcx, rax; void *
0x18000ba0d  call    memcpy_0
0x18000ba12  mov     eax, [rsi]
0x18000ba14  mov     [rdi], eax
0x18000ba16  mov     dword ptr [rbx+8], 0Eh
0x18000ba1d  jmp     short loc_18000BA7B
0x18000ba1f  mov     esi, 80070057h
0x18000ba24  jmp     short loc_18000B9FA
0x18000ba26  movups  xmm0, xmmword ptr [r14]
0x18000ba2a  movups  xmmword ptr [rbx], xmm0
0x18000ba2d  movups  xmm1, xmmword ptr [r14+10h]
0x18000ba32  movups  xmmword ptr [rbx+10h], xmm1
0x18000ba36  movups  xmm0, xmmword ptr [r14+20h]
0x18000ba3b  movups  xmmword ptr [rbx+20h], xmm0
0x18000ba3f  movups  xmm1, xmmword ptr [r14+30h]
0x18000ba44  movups  xmmword ptr [rbx+30h], xmm1
0x18000ba48  movups  xmm0, xmmword ptr [r14+40h]
0x18000ba4d  movups  xmmword ptr [rbx+40h], xmm0
0x18000ba51  movups  xmm1, xmmword ptr [r14+50h]
0x18000ba56  movups  xmmword ptr [rbx+50h], xmm1
0x18000ba5a  movups  xmm0, xmmword ptr [r14+60h]
0x18000ba5f  movups  xmmword ptr [rbx+60h], xmm0
0x18000ba63  movups  xmm1, xmmword ptr [r14+70h]
0x18000ba68  movups  xmmword ptr [rbx+70h], xmm1
0x18000ba6c  movups  xmm0, xmmword ptr [r14+80h]
0x18000ba74  movups  xmmword ptr [rbx+80h], xmm0
0x18000ba7b  mov     [rbx], r12
0x18000ba7e  xor     ecx, ecx; pv
0x18000ba80  mov     rsi, [r14]
0x18000ba83  call    cs:__imp_CoTaskMemFree
0x18000ba89  mov     [rbx], r12
0x18000ba8c  test    rsi, rsi
0x18000ba8f  jz      short loc_18000BAEE
0x18000ba91  mov     r8, rsi; unsigned __int16 *
0x18000ba94  mov     edx, 0FFFFh; unsigned __int64
0x18000ba99  mov     rcx, rbx; unsigned __int16 **
0x18000ba9c  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000baa1  mov     esi, eax
0x18000baa3  test    eax, eax
0x18000baa5  jns     short loc_18000BAEE
0x18000baa7  cmp     dword ptr [rbx+8], 0Ah
0x18000baab  jnz     short loc_18000BABB
0x18000baad  mov     rcx, [rdi]; pv
0x18000bab0  call    cs:__imp_CoTaskMemFree
0x18000bab6  mov     [rdi], r12
0x18000bab9  jmp     short loc_18000BAD2
0x18000babb  cmp     dword ptr [rbx+8], 0Eh
0x18000babf  jnz     short loc_18000BAD2
0x18000bac1  mov     rcx, [rbx+18h]; pv
0x18000bac5  call    cs:__imp_CoTaskMemFree
0x18000bacb  mov     [rbx+18h], r12
0x18000bacf  mov     [rdi], r12d
0x18000bad2  mov     rcx, [rbx]; pv
0x18000bad5  call    cs:__imp_CoTaskMemFree
0x18000badb  mov     [rbx], r12
0x18000bade  mov     [rdi], r12b
0x18000bae1  inc     rdi
0x18000bae4  sub     r15, 1
0x18000bae8  jnz     short loc_18000BADE
0x18000baea  mov     eax, esi
0x18000baec  jmp     short loc_18000BAF0
0x18000baee  xor     eax, eax
0x18000baf0  add     rsp, 20h
0x18000baf4  pop     r15
0x18000baf6  pop     r14
0x18000baf8  pop     r12
0x18000bafa  pop     rdi
0x18000bafb  pop     rsi
0x18000bafc  pop     rbp
0x18000bafd  pop     rbx
0x18000bafe  retn
```
