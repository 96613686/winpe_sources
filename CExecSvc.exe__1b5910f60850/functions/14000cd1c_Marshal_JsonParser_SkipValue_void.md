# Marshal::JsonParser::SkipValue(void)

- ea: `0x14000cd1c`
- end: `0x14000d0c3`
- name: `?SkipValue@JsonParser@Marshal@@QEAA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ`
- size: `935`
- prototype: `__int64 *__fastcall(Marshal::JsonParser *this, __int64 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x14000a7bc`

## callees

- `0x140002310`
- `0x14000696c`
- `0x140008230`
- `0x140008fec`
- `0x14000a714`
- `0x14000adb4`
- `0x14000af70`
- `0x14000b040`
- `0x14000b3f4`
- `0x14000b4ac`
- `0x14000b8c8`
- `0x14000cd1c`
- `0x14000e9dc`
- `0x14000eb10`

## pseudocode

```c
__int64 *__fastcall Marshal::JsonParser::SkipValue(Marshal::JsonParser *this, __int64 *a2)
{
  __int64 v4; // rsi
  int v5; // ecx
  __int64 v6; // r9
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned __int64 v18; // rax
  int *v19; // rdx
  int v20; // eax
  char Element; // al
  __int64 v22; // r8
  unsigned __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // r8
  unsigned __int64 v27; // r9
  __int64 v28; // rdx
  unsigned __int64 v29; // r8
  char v30[16]; // [rsp+20h] [rbp-49h] BYREF
  _QWORD v31[2]; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v32[2]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v33[2]; // [rsp+50h] [rbp-19h] BYREF
  char v34[16]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v35; // [rsp+70h] [rbp+7h] BYREF
  __int128 v36; // [rsp+80h] [rbp+17h] BYREF
  __int128 v37; // [rsp+90h] [rbp+27h]

  v4 = *((_QWORD *)this + 2);
  v36 = 0;
  v37 = 0u;
  while ( 1 )
  {
    v5 = Marshal::JsonParser::PeekValueType(this);
    if ( !v5 )
    {
      Marshal::JsonParser::ParseNumber(this, (__int64)v34);
      goto LABEL_19;
    }
    v7 = v5 - 1;
    if ( !v7 )
    {
      Marshal::JsonParser::ParseString(this);
      goto LABEL_19;
    }
    v8 = v7 - 1;
    if ( v8 )
      break;
    if ( !Marshal::JsonParser::BeginAggregate(this, 91, 93, 7) )
      goto LABEL_19;
    v30[0] = 0;
LABEL_12:
    std::vector<bool>::push_back(&v36, v30);
LABEL_13:
    if ( !*((_QWORD *)&v37 + 1) )
      goto LABEL_14;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( !Marshal::JsonParser::BeginAggregate(this, 123, 125, 9) )
      goto LABEL_19;
    Marshal::JsonParser::ParseObjectKey((void **)this);
    v30[0] = 1;
    goto LABEL_12;
  }
  v10 = v9 - 1;
  if ( v10 )
  {
    if ( v10 == 1 )
      Marshal::JsonParser::ParseNull(this);
  }
  else
  {
    Marshal::JsonParser::ParseBoolean(this);
  }
LABEL_19:
  v14 = *((_QWORD *)&v37 + 1);
  v15 = v36;
  while ( v14 )
  {
    if ( v14 >= 0 )
      v16 = v15 + 4 * ((unsigned __int64)v14 >> 5);
    else
      v16 = v15 - (4 * ((unsigned __int64)~v14 >> 5) + 4);
    v17 = v14 & 0x1F;
    v18 = v17 - 1;
    if ( v17 )
      v19 = (int *)(v16 + 4 * (v18 >> 5));
    else
      v19 = (int *)(v16 - (4 * (~v18 >> 5) + 4));
    v20 = *v19;
    if ( _bittest(&v20, ((_BYTE)v17 - 1) & 0x1F) )
    {
      Element = Marshal::JsonParser::NextElement(this, 125, 10);
      if ( Element )
      {
        Marshal::JsonParser::ParseObjectKey((void **)this);
        Element = 1;
      }
    }
    else
    {
      Element = Marshal::JsonParser::NextElement(this, 93, 8);
    }
    if ( Element )
      goto LABEL_13;
    if ( v37 >= 0 )
      v22 = v36 + 4LL * (*((_QWORD *)&v37 + 1) >> 5);
    else
      v22 = v36 - (4LL * (~*((_QWORD *)&v37 + 1) >> 5) + 4);
    v23 = (BYTE8(v37) & 0x1F) - 1LL;
    if ( (BYTE8(v37) & 0x1F) != 0 )
      v24 = v22 + 4 * (v23 >> 5);
    else
      v24 = v22 - (4 * (~v23 >> 5) + 4);
    if ( *((_QWORD *)&v37 + 1) )
    {
      v25 = 32 * ((v24 - (__int64)v36) >> 2) + (((BYTE8(v37) & 0x1F) - 1) & 0x1F);
      if ( v25 >= 0 )
        v26 = v36 + 4 * ((unsigned __int64)v25 >> 5);
      else
        v26 = v36 - (4 * ((unsigned __int64)~v25 >> 5) + 4);
      v27 = v25 & 0x1F;
    }
    else
    {
      v27 = 0;
      v26 = v36;
    }
    if ( v37 >= 0 )
      v28 = v36 + 4LL * (*((_QWORD *)&v37 + 1) >> 5);
    else
      v28 = v36 - (4LL * (~*((_QWORD *)&v37 + 1) >> 5) + 4);
    v31[0] = v26;
    v31[1] = v27;
    v32[0] = v28;
    v32[1] = BYTE8(v37) & 0x1F;
    if ( v27 >= 0x1F )
      v26 += 4;
    v33[0] = v26;
    v33[1] = (v27 + 1) & -(__int64)(v27 < 0x1F);
    std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>>(
      &v35,
      v33,
      v32,
      (__int64)v31);
    v14 = *((_QWORD *)&v37 + 1) - 1LL;
    if ( (unsigned __int64)(*((_QWORD *)&v37 + 1) - 1LL) > 0x7FFFFFFFFFFFFFFFLL )
      std::vector<bool>::_Xlen(v14);
    v29 = (unsigned __int64)(v14 + 31) >> 5;
    v15 = v36;
    if ( v29 < (__int64)(*((_QWORD *)&v36 + 1) - v36) >> 2 && (_QWORD)v36 + 4 * v29 != *((_QWORD *)&v36 + 1) )
      *((_QWORD *)&v36 + 1) = v36 + 4 * v29;
    --*((_QWORD *)&v37 + 1);
    if ( (v14 & 0x1F) != 0 )
    {
      *(_DWORD *)(v36 + 4 * v29 - 4) &= (1 << (v14 & 0x1F)) - 1;
      v14 = *((_QWORD *)&v37 + 1);
      v15 = v36;
    }
  }
LABEL_14:
  v11 = *((_QWORD *)this + 3) - v4;
  v12 = *(_QWORD *)this + 2 * v4;
  *a2 = v12;
  a2[1] = v11;
  std::vector<unsigned int>::~vector<unsigned int>(&v36, v12, v11, v6);
  return a2;
}

```

## disassembly

```asm
0x14000cd1c  mov     [rsp-8+arg_10], rbx
0x14000cd21  mov     [rsp-8+arg_18], rsi
0x14000cd26  push    rbp
0x14000cd27  push    rdi
0x14000cd28  push    r15
0x14000cd2a  lea     rbp, [rsp-47h]
0x14000cd2f  sub     rsp, 0B0h
0x14000cd36  mov     rax, cs:__security_cookie
0x14000cd3d  xor     rax, rsp
0x14000cd40  mov     [rbp+57h+var_20], rax
0x14000cd44  mov     rdi, rdx
0x14000cd47  mov     rbx, rcx
0x14000cd4a  mov     rsi, [rcx+10h]
0x14000cd4e  xorps   xmm0, xmm0
0x14000cd51  movups  [rbp+57h+var_30], xmm0
0x14000cd55  xorps   xmm1, xmm1
0x14000cd58  movdqu  [rbp+57h+var_40], xmm1
0x14000cd5d  mov     qword ptr [rbp+57h+var_30], 0
0x14000cd65  mov     qword ptr [rbp+57h+var_30+8], 0
0x14000cd6d  mov     r15d, 1Fh
0x14000cd73  mov     rcx, rbx
0x14000cd76  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x14000cd7b  mov     ecx, eax
0x14000cd7d  test    eax, eax
0x14000cd7f  jz      loc_14000CE6F
0x14000cd85  sub     ecx, 1
0x14000cd88  jz      loc_14000CE65
0x14000cd8e  sub     ecx, 1
0x14000cd91  jz      loc_14000CE48
0x14000cd97  sub     ecx, 1
0x14000cd9a  jz      short loc_14000CDC4
0x14000cd9c  sub     ecx, 1
0x14000cd9f  jz      short loc_14000CDB7
0x14000cda1  cmp     ecx, 1
0x14000cda4  jnz     loc_14000CE7B
0x14000cdaa  mov     rcx, rbx; this
0x14000cdad  call    ?ParseNull@JsonParser@Marshal@@QEAAXXZ; Marshal::JsonParser::ParseNull(void)
0x14000cdb2  jmp     loc_14000CE7B
0x14000cdb7  mov     rcx, rbx; this
0x14000cdba  call    ?ParseBoolean@JsonParser@Marshal@@QEAA_NXZ; Marshal::JsonParser::ParseBoolean(void)
0x14000cdbf  jmp     loc_14000CE7B
0x14000cdc4  mov     r9d, 9
0x14000cdca  mov     r8b, 7Dh ; '}'
0x14000cdcd  mov     dl, 7Bh ; '{'
0x14000cdcf  mov     rcx, rbx
0x14000cdd2  call    ?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z; Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)
0x14000cdd7  test    al, al
0x14000cdd9  jz      loc_14000CE7B
0x14000cddf  mov     rcx, rbx; this
0x14000cde2  call    ?ParseObjectKey@JsonParser@Marshal@@AEAAXXZ; Marshal::JsonParser::ParseObjectKey(void)
0x14000cde7  mov     [rbp+57h+var_A0], 1
0x14000cdeb  lea     rdx, [rbp+57h+var_A0]
0x14000cdef  lea     rcx, [rbp+57h+var_40]
0x14000cdf3  call    ?push_back@?$vector@_NV?$allocator@_N@std@@@std@@QEAAXAEB_N@Z; std::vector<bool>::push_back(bool const &)
0x14000cdf8  cmp     qword ptr [rbp+57h+var_30+8], 0
0x14000cdfd  jnz     loc_14000CD73
0x14000ce03  mov     r8, [rbx+18h]
0x14000ce07  sub     r8, rsi
0x14000ce0a  mov     rcx, [rbx]
0x14000ce0d  lea     rdx, [rcx+rsi*2]
0x14000ce11  mov     [rdi], rdx
0x14000ce14  mov     [rdi+8], r8
0x14000ce18  lea     rcx, [rbp+57h+var_40]
0x14000ce1c  call    ??1?$vector@IV?$allocator@I@std@@@std@@QEAA@XZ; std::vector<uint>::~vector<uint>(void)
0x14000ce21  mov     rax, rdi
0x14000ce24  mov     rcx, [rbp+57h+var_20]
0x14000ce28  xor     rcx, rsp; StackCookie
0x14000ce2b  call    __security_check_cookie
0x14000ce30  lea     r11, [rsp+0C0h+var_10]
0x14000ce38  mov     rbx, [r11+30h]
0x14000ce3c  mov     rsi, [r11+38h]
0x14000ce40  mov     rsp, r11
0x14000ce43  pop     r15
0x14000ce45  pop     rdi
0x14000ce46  pop     rbp
0x14000ce47  retn
0x14000ce48  mov     r9d, 7
0x14000ce4e  mov     r8b, 5Dh ; ']'
0x14000ce51  mov     dl, 5Bh ; '['
0x14000ce53  mov     rcx, rbx
0x14000ce56  call    ?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z; Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)
0x14000ce5b  test    al, al
0x14000ce5d  jz      short loc_14000CE7B
0x14000ce5f  mov     [rbp+57h+var_A0], 0
0x14000ce63  jmp     short loc_14000CDEB
0x14000ce65  mov     rcx, rbx
0x14000ce68  call    ?ParseString@JsonParser@Marshal@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Marshal::JsonParser::ParseString(void)
0x14000ce6d  jmp     short loc_14000CE7B
0x14000ce6f  lea     rdx, [rbp+57h+var_60]
0x14000ce73  mov     rcx, rbx
0x14000ce76  call    ?ParseNumber@JsonParser@Marshal@@QEAA?AUNumber@12@XZ; Marshal::JsonParser::ParseNumber(void)
0x14000ce7b  mov     rcx, qword ptr [rbp+57h+var_30+8]
0x14000ce7f  mov     rdx, qword ptr [rbp+57h+var_40]
0x14000ce83  test    rcx, rcx
0x14000ce86  jz      loc_14000CE03
0x14000ce8c  jns     short loc_14000CEAD
0x14000ce8e  mov     rax, rcx
0x14000ce91  neg     rax
0x14000ce94  jz      short loc_14000CEAD
0x14000ce96  mov     rax, rcx
0x14000ce99  not     rax
0x14000ce9c  shr     rax, 5
0x14000cea0  lea     rax, ds:4[rax*4]
0x14000cea8  sub     rdx, rax
0x14000ceab  jmp     short loc_14000CEB8
0x14000cead  mov     rax, rcx
0x14000ceb0  shr     rax, 5
0x14000ceb4  lea     rdx, [rdx+rax*4]
0x14000ceb8  mov     rax, r15
0x14000cebb  and     rcx, rax
0x14000cebe  lea     r8, [rcx-1]
0x14000cec2  mov     rax, r8
0x14000cec5  cmp     rcx, 1
0x14000cec9  jnb     short loc_14000CEDF
0x14000cecb  not     rax
0x14000cece  shr     rax, 5
0x14000ced2  lea     rax, ds:4[rax*4]
0x14000ceda  sub     rdx, rax
0x14000cedd  jmp     short loc_14000CEE7
0x14000cedf  shr     rax, 5
0x14000cee3  lea     rdx, [rdx+rax*4]
0x14000cee7  mov     al, r8b
0x14000ceea  and     al, r15b
0x14000ceed  movzx   ecx, al
0x14000cef0  mov     eax, [rdx]
0x14000cef2  bt      eax, ecx
0x14000cef5  mov     rcx, rbx
0x14000cef8  jnb     short loc_14000CF17
0x14000cefa  mov     r8d, 0Ah
0x14000cf00  mov     dl, 7Dh ; '}'
0x14000cf02  call    ?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z; Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)
0x14000cf07  test    al, al
0x14000cf09  jz      short loc_14000CF24
0x14000cf0b  mov     rcx, rbx; this
0x14000cf0e  call    ?ParseObjectKey@JsonParser@Marshal@@AEAAXXZ; Marshal::JsonParser::ParseObjectKey(void)
0x14000cf13  mov     al, 1
0x14000cf15  jmp     short loc_14000CF24
0x14000cf17  mov     r8d, 8
0x14000cf1d  mov     dl, 5Dh ; ']'
0x14000cf1f  call    ?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z; Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)
0x14000cf24  test    al, al
0x14000cf26  jnz     loc_14000CDF8
0x14000cf2c  mov     rdx, qword ptr [rbp+57h+var_40]
0x14000cf30  mov     rcx, qword ptr [rbp+57h+var_30+8]
0x14000cf34  test    rcx, rcx
0x14000cf37  jns     short loc_14000CF5B
0x14000cf39  mov     rax, rcx
0x14000cf3c  neg     rax
0x14000cf3f  jz      short loc_14000CF5B
0x14000cf41  mov     rax, rcx
0x14000cf44  not     rax
0x14000cf47  shr     rax, 5
0x14000cf4b  lea     rax, ds:4[rax*4]
0x14000cf53  mov     r8, rdx
0x14000cf56  sub     r8, rax
0x14000cf59  jmp     short loc_14000CF66
0x14000cf5b  mov     rax, rcx
0x14000cf5e  shr     rax, 5
0x14000cf62  lea     r8, [rdx+rax*4]
0x14000cf66  mov     r10, r15
0x14000cf69  mov     rax, rcx
0x14000cf6c  and     r10, rax
0x14000cf6f  lea     r9, [r10-1]
0x14000cf73  mov     rax, r9
0x14000cf76  cmp     r10, 1
0x14000cf7a  jnb     short loc_14000CF90
0x14000cf7c  not     rax
0x14000cf7f  shr     rax, 5
0x14000cf83  lea     rax, ds:4[rax*4]
0x14000cf8b  sub     r8, rax
0x14000cf8e  jmp     short loc_14000CF98
0x14000cf90  shr     rax, 5
0x14000cf94  lea     r8, [r8+rax*4]
0x14000cf98  test    rcx, rcx
0x14000cf9b  jz      short loc_14000CFE2
0x14000cf9d  sub     r8, rdx
0x14000cfa0  sar     r8, 2
0x14000cfa4  shl     r8, 5
0x14000cfa8  and     r9, r15
0x14000cfab  add     r9, r8
0x14000cfae  jns     short loc_14000CFD5
0x14000cfb0  mov     rax, r9
0x14000cfb3  neg     rax
0x14000cfb6  jz      short loc_14000CFD5
0x14000cfb8  mov     rax, r9
0x14000cfbb  not     rax
0x14000cfbe  shr     rax, 5
0x14000cfc2  lea     rax, ds:4[rax*4]
0x14000cfca  mov     r8, rdx
0x14000cfcd  sub     r8, rax
0x14000cfd0  and     r9, r15
0x14000cfd3  jmp     short loc_14000CFE8
0x14000cfd5  mov     rax, r9
0x14000cfd8  shr     rax, 5
0x14000cfdc  lea     r8, [rdx+rax*4]
0x14000cfe0  jmp     short loc_14000CFD0
0x14000cfe2  xor     r9d, r9d
0x14000cfe5  mov     r8, rdx
0x14000cfe8  test    rcx, rcx
0x14000cfeb  jns     short loc_14000D009
0x14000cfed  mov     rax, rcx
0x14000cff0  neg     rax
0x14000cff3  jz      short loc_14000D009
0x14000cff5  not     rcx
0x14000cff8  shr     rcx, 5
0x14000cffc  lea     rax, ds:4[rcx*4]
0x14000d004  sub     rdx, rax
0x14000d007  jmp     short loc_14000D011
0x14000d009  shr     rcx, 5
0x14000d00d  lea     rdx, [rdx+rcx*4]
0x14000d011  mov     [rbp+57h+var_90], r8
0x14000d015  mov     [rbp+57h+var_88], r9
0x14000d019  mov     [rbp+57h+var_80], rdx
0x14000d01d  mov     [rbp+57h+var_78], r10
0x14000d021  lea     rax, [r8+4]
0x14000d025  cmp     r9, r15
0x14000d028  cmovnb  r8, rax
0x14000d02c  mov     [rbp+57h+var_70], r8
0x14000d030  lea     rcx, [r9+1]
0x14000d034  sbb     rax, rax
0x14000d037  and     rax, rcx
0x14000d03a  mov     [rbp+57h+var_68], rax
0x14000d03e  lea     r9, [rbp+57h+var_90]
0x14000d042  lea     r8, [rbp+57h+var_80]
0x14000d046  lea     rdx, [rbp+57h+var_70]
0x14000d04a  lea     rcx, [rbp+57h+var_50]
0x14000d04e  call    ??$_Copy_vbool@V?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@V12@@std@@YA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@0@V10@00@Z; std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>>(std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>)
0x14000d053  mov     rcx, qword ptr [rbp+57h+var_30+8]
0x14000d057  dec     rcx
0x14000d05a  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000d064  cmp     rcx, rax
0x14000d067  ja      short loc_14000D0BD
0x14000d069  lea     r8, [rcx+1Fh]
0x14000d06d  shr     r8, 5
0x14000d071  mov     rax, qword ptr [rbp+57h+var_40+8]
0x14000d075  mov     rdx, qword ptr [rbp+57h+var_40]
0x14000d079  sub     rax, rdx
0x14000d07c  sar     rax, 2
0x14000d080  cmp     r8, rax
0x14000d083  jnb     short loc_14000D093
0x14000d085  lea     rax, [rdx+r8*4]
0x14000d089  cmp     rax, qword ptr [rbp+57h+var_40+8]
0x14000d08d  jz      short loc_14000D093
0x14000d08f  mov     qword ptr [rbp+57h+var_40+8], rax
0x14000d093  mov     qword ptr [rbp+57h+var_30+8], rcx
0x14000d097  mov     rax, rcx
0x14000d09a  and     rax, r15
0x14000d09d  jbe     short loc_14000D0B8
0x14000d09f  mov     rcx, rax
0x14000d0a2  mov     eax, 1
0x14000d0a7  shl     eax, cl
0x14000d0a9  dec     eax
0x14000d0ab  and     [rdx+r8*4-4], eax
0x14000d0b0  mov     rcx, qword ptr [rbp+57h+var_30+8]
0x14000d0b4  mov     rdx, qword ptr [rbp+57h+var_40]
0x14000d0b8  jmp     loc_14000CE83
0x14000d0bd  call    ?_Xlen@?$vector@_NV?$allocator@_N@std@@@std@@SAXXZ; std::vector<bool>::_Xlen(void)
```
