# _wctomb_internal

- ea: `0x1800580ec`
- end: `0x18005829c`
- name: `_wctomb_internal`
- size: `432`
- prototype: ``
- caller_count: `23`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180049714`
- `0x180049c4c`
- `0x18004a19c`
- `0x18004a6d4`
- `0x18004ab44`
- `0x18004aff4`
- `0x18004ff60`
- `0x180050034`
- `0x180050150`
- `0x180050224`
- `0x1800502f8`
- `0x180050414`
- `0x18005420c`
- `0x1800543f8`
- `0x1800545e4`
- `0x1800547d0`
- `0x180054970`
- `0x180054b10`
- `0x18005829c`
- `0x180058388`
- `0x180058438`
- `0x180058500`
- `0x1800588a8`

## callees

- `0x180007b48`
- `0x18000b794`
- `0x18001512c`
- `0x1800580ec`
- `0x18005c794`
- `0x180060550`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005824a`
- `KERNEL32!GetLastError` at `0x18005824a`

## pseudocode

```c
__int64 __fastcall wctomb_internal(int *a1, _BYTE *a2, size_t a3, unsigned __int16 a4, struct _Mbstatet *a5)
{
  unsigned int v5; // ebx
  struct _Mbstatet *v9; // rdi
  unsigned int v10; // esi
  struct _Mbstatet v11; // rax
  int v12; // ecx
  int v13; // eax
  __int64 result; // rax
  int v15; // eax
  __int64 v16; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int16 v17; // [rsp+78h] [rbp+20h] BYREF

  v17 = a4;
  v5 = 0;
  if ( !a2 && a3 )
  {
    if ( a1 )
      *a1 = 0;
    return 0;
  }
  if ( a1 )
    *a1 = -1;
  v9 = a5;
  if ( a3 > 0x7FFFFFFF )
  {
    v10 = 22;
LABEL_39:
    *(_DWORD *)&v9[5]._Byte = v10;
    LOBYTE(v9[6]._Wchar) = 1;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v9);
    return v10;
  }
  if ( !LOBYTE(a5[5]._Wchar) )
  {
    __crt_cached_ptd_host::update_locale_slow((__crt_cached_ptd_host *)a5);
    a4 = v17;
  }
  v11 = v9[3];
  v12 = *(_DWORD *)(*(_QWORD *)&v11 + 12LL);
  if ( v12 != 65001 )
  {
    if ( !*(_QWORD *)(*(_QWORD *)&v11 + 312LL) )
    {
      if ( a4 > 0xFFu )
      {
        if ( a2 && a3 )
          memset(a2, 0, a3);
        goto LABEL_23;
      }
      if ( !a2 )
      {
LABEL_27:
        if ( a1 )
          *a1 = 1;
        return 0;
      }
      if ( a3 )
      {
        *a2 = a4;
        goto LABEL_27;
      }
LABEL_38:
      v10 = 34;
      goto LABEL_39;
    }
    LODWORD(v16) = 0;
    v15 = _acrt_WideCharToMultiByte(v12, 0, (unsigned int)&v17, 1, (_DWORD)a2, a3, 0, (__int64)&v16);
    if ( v15 )
    {
      if ( !(_DWORD)v16 )
      {
        if ( a1 )
          *a1 = v15;
        return 0;
      }
    }
    else if ( GetLastError() == 122 )
    {
      if ( a2 && a3 )
        memset(a2, 0, a3);
      goto LABEL_38;
    }
LABEL_23:
    result = 42;
    *(_DWORD *)&v9[5]._Byte = 42;
    LOBYTE(v9[6]._Wchar) = 1;
    return result;
  }
  v16 = 0;
  v13 = __crt_mbstring::__c32rtomb_utf8((__crt_mbstring *)a2, (char *)a4, (__crt_mbstring *)&v16, v9);
  if ( a1 )
    *a1 = v13;
  if ( v13 <= 4 )
    return 0;
  if ( LOBYTE(v9[6]._Wchar) )
    return *(unsigned int *)&v9[5]._Byte;
  return v5;
}

```

## disassembly

```asm
0x1800580ec  mov     [rsp+arg_0], rbx
0x1800580f1  mov     [rsp+arg_10], rbp
0x1800580f6  mov     [rsp+arg_18], r9w
0x1800580fc  push    rsi
0x1800580fd  push    rdi
0x1800580fe  push    r14
0x180058100  sub     rsp, 40h
0x180058104  xor     ebx, ebx
0x180058106  mov     rbp, r8
0x180058109  mov     r14, rdx
0x18005810c  mov     rsi, rcx
0x18005810f  test    rdx, rdx
0x180058112  jnz     short loc_180058129
0x180058114  test    r8, r8
0x180058117  jz      short loc_180058129
0x180058119  test    rcx, rcx
0x18005811c  jz      loc_180058246
0x180058122  mov     [rcx], ebx
0x180058124  jmp     loc_180058246
0x180058129  test    rsi, rsi
0x18005812c  jz      short loc_180058131
0x18005812e  or      dword ptr [rcx], 0FFFFFFFFh
0x180058131  mov     rdi, [rsp+58h+arg_20]
0x180058139  cmp     rbp, 7FFFFFFFh
0x180058140  jbe     short loc_18005814C
0x180058142  mov     esi, 16h
0x180058147  jmp     loc_180058275
0x18005814c  cmp     [rdi+28h], bl
0x18005814f  jnz     short loc_18005815F
0x180058151  mov     rcx, rdi; this
0x180058154  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180058159  movzx   r9d, [rsp+58h+arg_18]
0x18005815f  mov     rax, [rdi+18h]
0x180058163  mov     ecx, [rax+0Ch]
0x180058166  cmp     ecx, 0FDE9h
0x18005816c  jnz     short loc_1800581A3
0x18005816e  movzx   edx, r9w; char *
0x180058172  lea     r8, [rsp+58h+arg_8]; char32_t
0x180058177  mov     r9, rdi; struct _Mbstatet *
0x18005817a  mov     [rsp+58h+arg_8], rbx
0x18005817f  mov     rcx, r14; this
0x180058182  call    ?__c32rtomb_utf8@__crt_mbstring@@YA_KPEAD_UPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c32rtomb_utf8(char *,char32_t,_Mbstatet *,__crt_cached_ptd_host &)
0x180058187  test    rsi, rsi
0x18005818a  jz      short loc_18005818E
0x18005818c  mov     [rsi], eax
0x18005818e  cmp     eax, 4
0x180058191  jle     loc_180058246
0x180058197  cmp     [rdi+30h], bl
0x18005819a  jz      short loc_18005819F
0x18005819c  mov     ebx, [rdi+2Ch]
0x18005819f  mov     eax, ebx
0x1800581a1  jmp     short loc_1800581DA
0x1800581a3  cmp     [rax+138h], rbx
0x1800581aa  jnz     short loc_180058207
0x1800581ac  mov     eax, 0FFh
0x1800581b1  cmp     r9w, ax
0x1800581b5  jbe     short loc_1800581ED
0x1800581b7  test    r14, r14
0x1800581ba  jz      short loc_1800581CE
0x1800581bc  test    rbp, rbp
0x1800581bf  jz      short loc_1800581CE
0x1800581c1  mov     r8, rbp; Size
0x1800581c4  xor     edx, edx; Val
0x1800581c6  mov     rcx, r14; void *
0x1800581c9  call    memset
0x1800581ce  mov     eax, 2Ah ; '*'
0x1800581d3  mov     [rdi+2Ch], eax
0x1800581d6  mov     byte ptr [rdi+30h], 1
0x1800581da  mov     rbx, [rsp+58h+arg_0]
0x1800581df  mov     rbp, [rsp+58h+arg_10]
0x1800581e4  add     rsp, 40h
0x1800581e8  pop     r14
0x1800581ea  pop     rdi
0x1800581eb  pop     rsi
0x1800581ec  retn
0x1800581ed  test    r14, r14
0x1800581f0  jz      short loc_1800581FA
0x1800581f2  test    rbp, rbp
0x1800581f5  jz      short loc_180058270
0x1800581f7  mov     [r14], r9b
0x1800581fa  test    rsi, rsi
0x1800581fd  jz      short loc_180058246
0x1800581ff  mov     dword ptr [rsi], 1
0x180058205  jmp     short loc_180058246
0x180058207  lea     rax, [rsp+58h+arg_8]
0x18005820c  mov     dword ptr [rsp+58h+arg_8], ebx
0x180058210  mov     [rsp+58h+var_20], rax
0x180058215  lea     r8, [rsp+58h+arg_18]
0x18005821a  mov     [rsp+58h+var_28], rbx
0x18005821f  mov     r9d, 1
0x180058225  mov     dword ptr [rsp+58h+var_30], ebp
0x180058229  xor     edx, edx
0x18005822b  mov     [rsp+58h+var_38], r14
0x180058230  call    __acrt_WideCharToMultiByte
0x180058235  test    eax, eax
0x180058237  jz      short loc_18005824A
0x180058239  cmp     dword ptr [rsp+58h+arg_8], ebx
0x18005823d  jnz     short loc_1800581CE
0x18005823f  test    rsi, rsi
0x180058242  jz      short loc_180058246
0x180058244  mov     [rsi], eax
0x180058246  xor     eax, eax
0x180058248  jmp     short loc_1800581DA
0x18005824a  call    cs:__imp_GetLastError
0x180058250  cmp     eax, 7Ah ; 'z'
0x180058253  jnz     loc_1800581CE
0x180058259  test    r14, r14
0x18005825c  jz      short loc_180058270
0x18005825e  test    rbp, rbp
0x180058261  jz      short loc_180058270
0x180058263  mov     r8, rbp; Size
0x180058266  xor     edx, edx; Val
0x180058268  mov     rcx, r14; void *
0x18005826b  call    memset
0x180058270  mov     esi, 22h ; '"'
0x180058275  mov     [rdi+2Ch], esi
0x180058278  xor     r9d, r9d; LineNo
0x18005827b  mov     [rsp+58h+var_30], rdi; __crt_cached_ptd_host *
0x180058280  xor     r8d, r8d; FileName
0x180058283  xor     edx, edx; FunctionName
0x180058285  mov     byte ptr [rdi+30h], 1
0x180058289  xor     ecx, ecx; Expression
0x18005828b  mov     [rsp+58h+var_38], rbx; uintptr_t
0x180058290  call    _invalid_parameter_internal
0x180058295  mov     eax, esi
0x180058297  jmp     loc_1800581DA
```
