# _attributes_array_t::Copy(ulong,tagHELPER_ATTRIBUTE *)

- ea: `0x180006ebc`
- end: `0x180007285`
- name: `?Copy@_attributes_array_t@@QEAAJKPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `969`
- prototype: `__int64 __fastcall(LPVOID *this, unsigned int, struct tagHELPER_ATTRIBUTE *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800043a0`
- `0x180004500`

## callees

- `0x180002576`
- `0x1800031e0`
- `0x180003b60`
- `0x180005ce0`
- `0x180006ebc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006f2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800070dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006f2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800070dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006f12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006fc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006fe3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ffb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000702f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007048`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000709b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800070b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000721b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007225`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007253`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006f12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006fc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006fe3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ffb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000702f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007048`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000709b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800070b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000721b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007225`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007253`

## pseudocode

```c
__int64 __fastcall _attributes_array_t::Copy(LPVOID *this, unsigned int a2, struct tagHELPER_ATTRIBUTE *a3)
{
  __int64 v3; // rdi
  struct tagHELPER_ATTRIBUTE *v4; // r14
  __int64 v7; // rbx
  _BYTE *v8; // rax
  __int64 result; // rax
  unsigned int v10; // r13d
  char *v11; // rbx
  __int64 v12; // rdi
  BYTE *lpValue; // rcx
  const unsigned __int16 *PWStr; // r14
  struct tagHELPER_ATTRIBUTE *v15; // rbx
  ATTRIBUTE_TYPE type; // r15d
  LPVOID *p_PWStr; // rdi
  char *p_Char; // rax
  __int64 v19; // rcx
  int v20; // r14d
  BYTE *v21; // rax
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int64 v30; // rax
  unsigned __int16 *pv; // [rsp+20h] [rbp-79h]
  LONGLONG Int64; // [rsp+28h] [rbp-71h]
  struct tagHELPER_ATTRIBUTE v33; // [rsp+30h] [rbp-69h] BYREF
  ATTRIBUTE_TYPE v34; // [rsp+108h] [rbp+6Fh]
  BYTE *Src; // [rsp+118h] [rbp+7Fh]

  v3 = a2;
  v4 = a3;
  if ( a2 && a3 )
  {
    if ( a2 > 0x1C71C71 )
      return (unsigned int)-2147024362;
    _attributes_array_t::FreeElements((_attributes_array_t *)this);
    CoTaskMemFree(this[1]);
    this[1] = 0;
    v7 = 144 * v3;
    *(_DWORD *)this = 0;
    v8 = CoTaskMemAlloc(144 * v3);
    this[1] = v8;
    if ( !v8 )
      return (unsigned int)-2147024882;
    for ( ; v7; --v7 )
      *v8++ = 0;
    *(_DWORD *)this = v3;
    v10 = 0;
    if ( !(_DWORD)v3 )
      return 0;
    while ( 1 )
    {
      v11 = (char *)this[1];
      v33.pwszName = 0;
      v33.type = AT_INVALID;
      v12 = v10;
      _attribute_t::Copy(&v33, &v4[v12]);
      lpValue = v33.OctetString.lpValue;
      PWStr = v33.PWStr;
      v15 = (struct tagHELPER_ATTRIBUTE *)&v11[v12 * 144];
      type = v33.type;
      Src = v33.OctetString.lpValue;
      Int64 = v33.Int64;
      v34 = v33.type;
      pv = v33.pwszName;
      if ( v15 == &v33 )
        goto LABEL_49;
      if ( v15->type == AT_STRING )
      {
        CoTaskMemFree(v15->PWStr);
        v15->Int64 = 0;
      }
      else if ( v15->type == AT_OCTET_STRING )
      {
        CoTaskMemFree(v15->OctetString.lpValue);
        v15->OctetString.lpValue = 0;
        v15->Boolean = 0;
      }
      CoTaskMemFree(v15->pwszName);
      p_PWStr = (LPVOID *)&v15->PWStr;
      v15->pwszName = 0;
      p_Char = &v15->Char;
      v19 = 128;
      do
      {
        *p_Char++ = 0;
        --v19;
      }
      while ( v19 );
      if ( type == AT_STRING )
      {
        if ( v15->type == AT_STRING )
        {
          CoTaskMemFree(*p_PWStr);
          *p_PWStr = 0;
        }
        else if ( v15->type == AT_OCTET_STRING )
        {
          CoTaskMemFree(v15->OctetString.lpValue);
          v15->OctetString.lpValue = 0;
          *(_DWORD *)p_PWStr = 0;
        }
        if ( PWStr )
        {
          v20 = StringCchCopyWithAlloc(&v15->PWStr, 0xFFFFu, PWStr);
          if ( v20 < 0 )
            goto LABEL_35;
          v15->type = AT_STRING;
        }
      }
      else if ( type == AT_OCTET_STRING )
      {
        if ( v15->type == AT_STRING )
        {
          CoTaskMemFree(*p_PWStr);
          *p_PWStr = 0;
        }
        else if ( v15->type == AT_OCTET_STRING )
        {
          CoTaskMemFree(v15->OctetString.lpValue);
          v15->OctetString.lpValue = 0;
          *(_DWORD *)p_PWStr = 0;
        }
        if ( v15 == (struct tagHELPER_ATTRIBUTE *)-16LL || (unsigned int)PWStr >= 0xFFFF )
        {
          v20 = -2147024809;
          goto LABEL_35;
        }
        v21 = (BYTE *)CoTaskMemAlloc((unsigned int)PWStr);
        v15->OctetString.lpValue = v21;
        if ( !v21 )
        {
          type = v34;
          v20 = -2147024882;
LABEL_35:
          v15->type = AT_INVALID;
          goto LABEL_41;
        }
        memcpy_0(v21, Src, (unsigned int)PWStr);
        type = v34;
        *(_DWORD *)p_PWStr = (_DWORD)PWStr;
        v15->type = AT_OCTET_STRING;
      }
      else
      {
        v22 = *(_OWORD *)&v33.Boolean;
        *(_OWORD *)&v15->pwszName = *(_OWORD *)&v33.pwszName;
        v23 = *((_OWORD *)&v33.OctetString + 1);
        *(_OWORD *)&v15->Boolean = v22;
        v24 = *((_OWORD *)&v33.OctetString + 2);
        *((_OWORD *)&v15->OctetString + 1) = v23;
        v25 = *((_OWORD *)&v33.OctetString + 3);
        *((_OWORD *)&v15->OctetString + 2) = v24;
        v26 = *((_OWORD *)&v33.OctetString + 4);
        *((_OWORD *)&v15->OctetString + 3) = v25;
        v27 = *((_OWORD *)&v33.OctetString + 5);
        *((_OWORD *)&v15->OctetString + 4) = v26;
        v28 = *((_OWORD *)&v33.OctetString + 6);
        *((_OWORD *)&v15->OctetString + 5) = v27;
        v29 = *((_OWORD *)&v33.OctetString + 7);
        *((_OWORD *)&v15->OctetString + 6) = v28;
        *((_OWORD *)&v15->OctetString + 7) = v29;
      }
      v15->pwszName = 0;
      CoTaskMemFree(0);
      v15->pwszName = 0;
      if ( !pv || (v20 = StringCchCopyWithAlloc(&v15->pwszName, 0xFFFFu, pv), v20 >= 0) )
      {
        lpValue = Src;
LABEL_49:
        v20 = 0;
        goto LABEL_50;
      }
LABEL_41:
      if ( v15->type == AT_STRING )
      {
        CoTaskMemFree(*p_PWStr);
        *p_PWStr = 0;
      }
      else if ( v15->type == AT_OCTET_STRING )
      {
        CoTaskMemFree(v15->OctetString.lpValue);
        v15->OctetString.lpValue = 0;
        *(_DWORD *)p_PWStr = 0;
      }
      CoTaskMemFree(v15->pwszName);
      v30 = 128;
      v15->pwszName = 0;
      do
      {
        *(_BYTE *)p_PWStr = 0;
        p_PWStr = (LPVOID *)((char *)p_PWStr + 1);
        --v30;
      }
      while ( v30 );
      lpValue = Src;
LABEL_50:
      if ( type == AT_STRING )
      {
        lpValue = (BYTE *)Int64;
      }
      else if ( type != AT_OCTET_STRING )
      {
        goto LABEL_54;
      }
      CoTaskMemFree(lpValue);
LABEL_54:
      CoTaskMemFree(pv);
      if ( v20 < 0 )
      {
        _attributes_array_t::FreeElements((_attributes_array_t *)this);
        CoTaskMemFree(this[1]);
        result = (unsigned int)v20;
        this[1] = 0;
        *(_DWORD *)this = 0;
        return result;
      }
      v4 = a3;
      if ( ++v10 >= *(_DWORD *)this )
        return 0;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180006ebc  mov     [rsp-8+arg_0], rbx
0x180006ec1  mov     [rsp-8+arg_10], r8
0x180006ec6  push    rbp
0x180006ec7  push    rsi
0x180006ec8  push    rdi
0x180006ec9  push    r12
0x180006ecb  push    r13
0x180006ecd  push    r14
0x180006ecf  push    r15
0x180006ed1  lea     rbp, [rsp-27h]
0x180006ed6  sub     rsp, 0C0h
0x180006edd  xor     r15d, r15d
0x180006ee0  mov     edi, edx
0x180006ee2  mov     r14, r8
0x180006ee5  mov     rsi, rcx
0x180006ee8  test    edx, edx
0x180006eea  jz      loc_180007265
0x180006ef0  test    r8, r8
0x180006ef3  jz      loc_180007265
0x180006ef9  cmp     edi, 1C71C71h
0x180006eff  jbe     short loc_180006F09
0x180006f01  mov     r12d, 80070216h
0x180006f07  jmp     short loc_180006F3F
0x180006f09  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x180006f0e  mov     rcx, [rsi+8]; pv
0x180006f12  call    cs:__imp_CoTaskMemFree
0x180006f18  lea     rbx, [rdi+rdi*8]
0x180006f1c  mov     [rsi+8], r15
0x180006f20  shl     rbx, 4
0x180006f24  mov     rcx, rbx; cb
0x180006f27  mov     [rsi], r15d
0x180006f2a  call    cs:__imp_CoTaskMemAlloc
0x180006f30  mov     [rsi+8], rax
0x180006f34  test    rax, rax
0x180006f37  jnz     short loc_180006F47
0x180006f39  mov     r12d, 8007000Eh
0x180006f3f  mov     eax, r12d
0x180006f42  jmp     loc_18000726A
0x180006f47  test    rbx, rbx
0x180006f4a  jz      short loc_180006F58
0x180006f4c  mov     [rax], r15b
0x180006f4f  inc     rax
0x180006f52  sub     rbx, 1
0x180006f56  jnz     short loc_180006F4C
0x180006f58  mov     [rsi], edi
0x180006f5a  mov     r13d, r15d
0x180006f5d  test    edi, edi
0x180006f5f  jz      loc_180007243
0x180006f65  mov     r12d, 8007000Eh
0x180006f6b  mov     rbx, [rsi+8]
0x180006f6f  lea     rcx, [rbp+57h+var_C0]; this
0x180006f73  mov     eax, r13d
0x180006f76  mov     qword ptr [rbp+57h+var_C0], r15
0x180006f7a  mov     dword ptr [rbp+57h+var_C0+8], r15d
0x180006f7e  lea     rdi, [rax+rax*8]
0x180006f82  shl     rdi, 4
0x180006f86  lea     rdx, [rdi+r14]; struct tagHELPER_ATTRIBUTE *
0x180006f8a  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x180006f8f  mov     rcx, [rbp+57h+cb+8]
0x180006f93  lea     rdx, [rbp+57h+var_C0]
0x180006f97  mov     r14, [rbp+57h+cb]
0x180006f9b  add     rbx, rdi
0x180006f9e  mov     rax, qword ptr [rbp+57h+var_C0]
0x180006fa2  mov     r15d, dword ptr [rbp+57h+var_C0+8]
0x180006fa6  mov     [rbp+57h+Src], rcx
0x180006faa  mov     [rbp+57h+var_C8], r14
0x180006fae  mov     [rbp+57h+arg_8], r15d
0x180006fb2  mov     [rbp+57h+pv], rax
0x180006fb6  cmp     rbx, rdx
0x180006fb9  jz      loc_180007206
0x180006fbf  cmp     dword ptr [rbx+8], 0Ah
0x180006fc3  jnz     short loc_180006FD9
0x180006fc5  mov     rcx, [rbx+10h]; pv
0x180006fc9  call    cs:__imp_CoTaskMemFree
0x180006fcf  mov     qword ptr [rbx+10h], 0
0x180006fd7  jmp     short loc_180006FF8
0x180006fd9  cmp     dword ptr [rbx+8], 0Eh
0x180006fdd  jnz     short loc_180006FF8
0x180006fdf  mov     rcx, [rbx+18h]; pv
0x180006fe3  call    cs:__imp_CoTaskMemFree
0x180006fe9  mov     qword ptr [rbx+18h], 0
0x180006ff1  mov     dword ptr [rbx+10h], 0
0x180006ff8  mov     rcx, [rbx]; pv
0x180006ffb  call    cs:__imp_CoTaskMemFree
0x180007001  lea     rdi, [rbx+10h]
0x180007005  mov     qword ptr [rbx], 0
0x18000700c  mov     rax, rdi
0x18000700f  mov     ecx, 80h
0x180007014  mov     byte ptr [rax], 0
0x180007017  inc     rax
0x18000701a  sub     rcx, 1
0x18000701e  jnz     short loc_180007014
0x180007020  cmp     r15d, 0Ah
0x180007024  jnz     short loc_180007088
0x180007026  cmp     [rbx+8], r15d
0x18000702a  jnz     short loc_18000703E
0x18000702c  mov     rcx, [rdi]; pv
0x18000702f  call    cs:__imp_CoTaskMemFree
0x180007035  mov     qword ptr [rdi], 0
0x18000703c  jmp     short loc_18000705C
0x18000703e  cmp     dword ptr [rbx+8], 0Eh
0x180007042  jnz     short loc_18000705C
0x180007044  mov     rcx, [rbx+18h]; pv
0x180007048  call    cs:__imp_CoTaskMemFree
0x18000704e  mov     qword ptr [rbx+18h], 0
0x180007056  mov     dword ptr [rdi], 0
0x18000705c  test    r14, r14
0x18000705f  jz      loc_18000716F
0x180007065  mov     r8, r14; unsigned __int16 *
0x180007068  mov     edx, 0FFFFh; unsigned __int64
0x18000706d  mov     rcx, rdi; unsigned __int16 **
0x180007070  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180007075  mov     r14d, eax
0x180007078  test    eax, eax
0x18000707a  js      short loc_1800070F2
0x18000707c  mov     dword ptr [rbx+8], 0Ah
0x180007083  jmp     loc_18000716F
0x180007088  cmp     r15d, 0Eh
0x18000708c  jnz     loc_180007125
0x180007092  cmp     dword ptr [rbx+8], 0Ah
0x180007096  jnz     short loc_1800070AA
0x180007098  mov     rcx, [rdi]; pv
0x18000709b  call    cs:__imp_CoTaskMemFree
0x1800070a1  mov     qword ptr [rdi], 0
0x1800070a8  jmp     short loc_1800070C8
0x1800070aa  cmp     dword ptr [rbx+8], 0Eh
0x1800070ae  jnz     short loc_1800070C8
0x1800070b0  mov     rcx, [rbx+18h]; pv
0x1800070b4  call    cs:__imp_CoTaskMemFree
0x1800070ba  mov     qword ptr [rbx+18h], 0
0x1800070c2  mov     dword ptr [rdi], 0
0x1800070c8  test    rdi, rdi
0x1800070cb  jz      short loc_18000711D
0x1800070cd  cmp     r14d, 0FFFFh
0x1800070d4  jnb     short loc_18000711D
0x1800070d6  mov     ecx, r14d; cb
0x1800070d9  mov     r15d, r14d
0x1800070dc  call    cs:__imp_CoTaskMemAlloc
0x1800070e2  mov     [rdi+8], rax
0x1800070e6  test    rax, rax
0x1800070e9  jnz     short loc_1800070FE
0x1800070eb  mov     r15d, [rbp+57h+arg_8]
0x1800070ef  mov     r14d, r12d
0x1800070f2  mov     dword ptr [rbx+8], 0
0x1800070f9  jmp     loc_1800071A5
0x1800070fe  mov     rdx, [rbp+57h+Src]; Src
0x180007102  mov     r8, r15; Size
0x180007105  mov     rcx, rax; void *
0x180007108  call    memcpy_0
0x18000710d  mov     r15d, [rbp+57h+arg_8]
0x180007111  mov     [rdi], r14d
0x180007114  mov     dword ptr [rbx+8], 0Eh
0x18000711b  jmp     short loc_18000716F
0x18000711d  mov     r14d, 80070057h
0x180007123  jmp     short loc_1800070F2
0x180007125  movups  xmm0, [rbp+57h+var_C0]
0x180007129  movups  xmm1, xmmword ptr [rbp+57h+cb]
0x18000712d  movups  xmmword ptr [rbx], xmm0
0x180007130  movups  xmm0, [rbp+57h+var_A0]
0x180007134  movups  xmmword ptr [rbx+10h], xmm1
0x180007138  movups  xmm1, [rbp+57h+var_90]
0x18000713c  movups  xmmword ptr [rbx+20h], xmm0
0x180007140  movups  xmm0, [rbp+57h+var_80]
0x180007144  movups  xmmword ptr [rbx+30h], xmm1
0x180007148  movups  xmm1, [rbp+57h+var_70]
0x18000714c  movups  xmmword ptr [rbx+40h], xmm0
0x180007150  movups  xmm0, [rbp+57h+var_60]
0x180007154  movups  xmmword ptr [rbx+50h], xmm1
0x180007158  movups  xmm1, [rbp+57h+var_50]
0x18000715c  movups  xmmword ptr [rbx+60h], xmm0
0x180007160  movups  xmm0, [rbp+57h+var_40]
0x180007164  movups  xmmword ptr [rbx+70h], xmm1
0x180007168  movups  xmmword ptr [rbx+80h], xmm0
0x18000716f  xor     ecx, ecx; pv
0x180007171  mov     qword ptr [rbx], 0
0x180007178  call    cs:__imp_CoTaskMemFree
0x18000717e  mov     rax, [rbp+57h+pv]
0x180007182  mov     qword ptr [rbx], 0
0x180007189  test    rax, rax
0x18000718c  jz      short loc_180007202
0x18000718e  mov     r8, rax; unsigned __int16 *
0x180007191  mov     edx, 0FFFFh; unsigned __int64
0x180007196  mov     rcx, rbx; unsigned __int16 **
0x180007199  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000719e  mov     r14d, eax
0x1800071a1  test    eax, eax
0x1800071a3  jns     short loc_180007202
0x1800071a5  cmp     dword ptr [rbx+8], 0Ah
0x1800071a9  jnz     short loc_1800071BD
0x1800071ab  mov     rcx, [rdi]; pv
0x1800071ae  call    cs:__imp_CoTaskMemFree
0x1800071b4  mov     qword ptr [rdi], 0
0x1800071bb  jmp     short loc_1800071DB
0x1800071bd  cmp     dword ptr [rbx+8], 0Eh
0x1800071c1  jnz     short loc_1800071DB
0x1800071c3  mov     rcx, [rbx+18h]; pv
0x1800071c7  call    cs:__imp_CoTaskMemFree
0x1800071cd  mov     qword ptr [rbx+18h], 0
0x1800071d5  mov     dword ptr [rdi], 0
0x1800071db  mov     rcx, [rbx]; pv
0x1800071de  call    cs:__imp_CoTaskMemFree
0x1800071e4  mov     eax, 80h
0x1800071e9  mov     qword ptr [rbx], 0
0x1800071f0  mov     byte ptr [rdi], 0
0x1800071f3  inc     rdi
0x1800071f6  sub     rax, 1
0x1800071fa  jnz     short loc_1800071F0
0x1800071fc  mov     rcx, [rbp+57h+Src]
0x180007200  jmp     short loc_180007209
0x180007202  mov     rcx, [rbp+57h+Src]; pv
0x180007206  xor     r14d, r14d
0x180007209  cmp     r15d, 0Ah
0x18000720d  jnz     short loc_180007215
0x18000720f  mov     rcx, [rbp+57h+var_C8]
0x180007213  jmp     short loc_18000721B
0x180007215  cmp     r15d, 0Eh
0x180007219  jnz     short loc_180007221
0x18000721b  call    cs:__imp_CoTaskMemFree
0x180007221  mov     rcx, [rbp+57h+pv]; pv
0x180007225  call    cs:__imp_CoTaskMemFree
0x18000722b  xor     r15d, r15d
0x18000722e  test    r14d, r14d
0x180007231  js      short loc_180007247
0x180007233  mov     r14, [rbp+57h+arg_10]
0x180007237  inc     r13d
0x18000723a  cmp     r13d, [rsi]
0x18000723d  jb      loc_180006F6B
0x180007243  xor     eax, eax
0x180007245  jmp     short loc_18000726A
0x180007247  mov     rcx, rsi; this
0x18000724a  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x18000724f  mov     rcx, [rsi+8]; pv
0x180007253  call    cs:__imp_CoTaskMemFree
0x180007259  mov     eax, r14d
0x18000725c  mov     [rsi+8], r15
0x180007260  mov     [rsi], r15d
0x180007263  jmp     short loc_18000726A
0x180007265  mov     eax, 80070057h
0x18000726a  mov     rbx, [rsp+0F0h+arg_0]
0x180007272  add     rsp, 0C0h
0x180007279  pop     r15
0x18000727b  pop     r14
0x18000727d  pop     r13
0x18000727f  pop     r12
0x180007281  pop     rdi
0x180007282  pop     rsi
0x180007283  pop     rbp
0x180007284  retn
```
