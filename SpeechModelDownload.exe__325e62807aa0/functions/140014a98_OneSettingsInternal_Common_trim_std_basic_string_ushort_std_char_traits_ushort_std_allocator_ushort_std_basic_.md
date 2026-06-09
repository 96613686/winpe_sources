# OneSettingsInternal::Common::trim<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140014a98`
- end: `0x140014c14`
- name: `??$trim@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Common@OneSettingsInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `380`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400177a0`
- `0x14001a878`
- `0x14001a9ac`
- `0x14001ab2c`
- `0x14001aec0`
- `0x14001afc0`
- `0x14001b130`

## callees

- `0x140002600`
- `0x1400138c8`
- `0x140013a2c`
- `0x140014a98`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x140014af4`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x140014b29`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x140014af4`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x140014b29`

## pseudocode

```c
__int64 __fastcall OneSettingsInternal::Common::trim<std::wstring>(__int64 a1, _QWORD *a2)
{
  char *v2; // rdi
  _QWORD *v4; // rcx
  _QWORD *v5; // r14
  unsigned __int16 *v6; // rbx
  unsigned __int16 *v7; // rsi
  _QWORD *v8; // rcx
  char *i; // rbx
  _OWORD *v10; // rcx
  char v11; // bl
  char v12; // bl
  _OWORD v14[2]; // [rsp+30h] [rbp-68h] BYREF
  _OWORD v15[2]; // [rsp+50h] [rbp-48h] BYREF

  v2 = (char *)a2;
  v4 = a2;
  if ( a2[3] > 7u )
    v4 = (_QWORD *)*a2;
  v5 = a2 + 2;
  v6 = (unsigned __int16 *)v4 + a2[2];
  v7 = (unsigned __int16 *)a2;
  if ( a2[3] > 7u )
    v7 = (unsigned __int16 *)*a2;
  while ( v7 != v6 && (unsigned int)_o_isspace(*v7) )
    ++v7;
  if ( *((_QWORD *)v2 + 3) <= 7u )
  {
    v8 = v2;
  }
  else
  {
    v8 = *(_QWORD **)v2;
    v2 = *(char **)v2;
  }
  for ( i = (char *)v8 + 2 * *v5; i != v2 && (unsigned int)_o_isspace(*((unsigned __int16 *)i - 1)); i -= 2 )
    ;
  if ( v7 < (unsigned __int16 *)i )
  {
    memset(v14, 0, sizeof(v14));
    std::wstring::_Construct<1,unsigned short const *>(v14, v7, (i - (char *)v7) >> 1);
    v10 = v14;
    v11 = 2;
  }
  else
  {
    v15[0] = 0;
    v15[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v15[0]) = 0;
    v10 = v15;
    v11 = 1;
  }
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_OWORD *)a1 = *v10;
  *(_OWORD *)(a1 + 16) = v10[1];
  *((_QWORD *)v10 + 2) = 0;
  *((_QWORD *)v10 + 3) = 7;
  *(_WORD *)v10 = 0;
  v12 = v11 | 4;
  if ( (v12 & 2) != 0 )
  {
    v12 &= ~2u;
    std::wstring::~wstring(v14);
  }
  if ( (v12 & 1) != 0 )
    std::wstring::~wstring(v15);
  return a1;
}

```

## disassembly

```asm
0x140014a98  mov     [rsp+arg_8], rbx
0x140014a9d  mov     [rsp+arg_10], rbp
0x140014aa2  push    rsi
0x140014aa3  push    rdi
0x140014aa4  push    r14
0x140014aa6  sub     rsp, 80h
0x140014aad  mov     rax, cs:__security_cookie
0x140014ab4  xor     rax, rsp
0x140014ab7  mov     [rsp+98h+var_28], rax
0x140014abc  mov     rdi, rdx
0x140014abf  mov     rbp, rcx
0x140014ac2  mov     [rsp+98h+var_70], rcx
0x140014ac7  mov     [rsp+98h+var_78], 0
0x140014acf  mov     rcx, rdx
0x140014ad2  cmp     qword ptr [rdx+18h], 7
0x140014ad7  jbe     short loc_140014ADC
0x140014ad9  mov     rcx, [rdx]
0x140014adc  lea     r14, [rdx+10h]
0x140014ae0  mov     rax, [r14]
0x140014ae3  lea     rbx, [rcx+rax*2]
0x140014ae7  mov     rsi, rdi
0x140014aea  jbe     short loc_140014B02
0x140014aec  mov     rsi, [rdx]
0x140014aef  jmp     short loc_140014B02
0x140014af1  movzx   ecx, word ptr [rsi]
0x140014af4  call    cs:__imp__o_isspace
0x140014afa  test    eax, eax
0x140014afc  jz      short loc_140014B07
0x140014afe  add     rsi, 2
0x140014b02  cmp     rsi, rbx
0x140014b05  jnz     short loc_140014AF1
0x140014b07  cmp     qword ptr [rdi+18h], 7
0x140014b0c  jbe     short loc_140014B16
0x140014b0e  mov     rcx, [rdi]
0x140014b11  mov     rdi, rcx
0x140014b14  jmp     short loc_140014B19
0x140014b16  mov     rcx, rdi
0x140014b19  mov     rax, [r14]
0x140014b1c  lea     rbx, [rcx+rax*2]
0x140014b20  cmp     rbx, rdi
0x140014b23  jz      short loc_140014B39
0x140014b25  movzx   ecx, word ptr [rbx-2]
0x140014b29  call    cs:__imp__o_isspace
0x140014b2f  test    eax, eax
0x140014b31  jz      short loc_140014B39
0x140014b33  add     rbx, 0FFFFFFFFFFFFFFFEh
0x140014b37  jmp     short loc_140014B20
0x140014b39  xorps   xmm0, xmm0
0x140014b3c  cmp     rsi, rbx
0x140014b3f  jb      short loc_140014B65
0x140014b41  movups  [rsp+98h+var_48], xmm0
0x140014b46  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140014b4e  movdqu  [rsp+98h+var_38], xmm1
0x140014b54  xor     eax, eax
0x140014b56  mov     word ptr [rsp+98h+var_48], ax
0x140014b5b  lea     rcx, [rsp+98h+var_48]
0x140014b60  lea     ebx, [rax+1]
0x140014b63  jmp     short loc_140014B93
0x140014b65  movups  [rsp+98h+var_68], xmm0
0x140014b6a  xorps   xmm1, xmm1
0x140014b6d  movdqu  [rsp+98h+var_58], xmm1
0x140014b73  sub     rbx, rsi
0x140014b76  sar     rbx, 1
0x140014b79  mov     r8, rbx
0x140014b7c  mov     rdx, rsi
0x140014b7f  lea     rcx, [rsp+98h+var_68]
0x140014b84  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140014b89  lea     rcx, [rsp+98h+var_68]
0x140014b8e  mov     ebx, 2
0x140014b93  mov     qword ptr [rbp+10h], 0
0x140014b9b  mov     qword ptr [rbp+18h], 0
0x140014ba3  movups  xmm0, xmmword ptr [rcx]
0x140014ba6  movups  xmmword ptr [rbp+0], xmm0
0x140014baa  movups  xmm1, xmmword ptr [rcx+10h]
0x140014bae  movups  xmmword ptr [rbp+10h], xmm1
0x140014bb2  mov     qword ptr [rcx+10h], 0
0x140014bba  mov     qword ptr [rcx+18h], 7
0x140014bc2  xor     eax, eax
0x140014bc4  mov     [rcx], ax
0x140014bc7  or      ebx, 4
0x140014bca  test    bl, 2
0x140014bcd  jz      short loc_140014BDD
0x140014bcf  and     ebx, 0FFFFFFFDh
0x140014bd2  lea     rcx, [rsp+98h+var_68]
0x140014bd7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140014bdc  nop
0x140014bdd  test    bl, 1
0x140014be0  jz      short loc_140014BEC
0x140014be2  lea     rcx, [rsp+98h+var_48]
0x140014be7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140014bec  mov     rax, rbp
0x140014bef  mov     rcx, [rsp+98h+var_28]
0x140014bf4  xor     rcx, rsp; StackCookie
0x140014bf7  call    __security_check_cookie
0x140014bfc  lea     r11, [rsp+98h+var_18]
0x140014c04  mov     rbx, [r11+28h]
0x140014c08  mov     rbp, [r11+30h]
0x140014c0c  mov     rsp, r11
0x140014c0f  pop     r14
0x140014c11  pop     rdi
0x140014c12  pop     rsi
0x140014c13  retn
```
