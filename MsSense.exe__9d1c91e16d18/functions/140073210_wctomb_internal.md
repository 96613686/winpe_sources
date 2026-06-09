# _wctomb_internal

- ea: `0x140073210`
- end: `0x1400733c0`
- name: `_wctomb_internal`
- size: `432`
- prototype: `__int64 __fastcall(int *, _BYTE *, unsigned __int64, unsigned __int16, __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140064a54`
- `0x140065a04`

## callees

- `0x14006147c`
- `0x140065e50`
- `0x140073210`
- `0x14007ad18`
- `0x14007d248`
- `0x1400802f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14007336e`
- `KERNEL32!GetLastError` at `0x14007336e`

## pseudocode

```c
__int64 __fastcall wctomb_internal(
        int *a1,
        _BYTE *a2,
        unsigned __int64 a3,
        unsigned __int16 a4,
        __crt_cached_ptd_host *a5)
{
  unsigned int v5; // ebx
  __crt_cached_ptd_host *v9; // rdi
  unsigned int v10; // esi
  __int64 v11; // rax
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
    *((_DWORD *)v9 + 11) = v10;
    *((_BYTE *)v9 + 48) = 1;
    sub_14006147C(0, 0, 0, 0, 0, v9);
    return v10;
  }
  if ( !*((_BYTE *)a5 + 40) )
  {
    __crt_cached_ptd_host::update_locale_slow(a5);
    a4 = v17;
  }
  v11 = *((_QWORD *)v9 + 3);
  v12 = *(_DWORD *)(v11 + 12);
  if ( v12 != 65001 )
  {
    if ( !*(_QWORD *)(v11 + 312) )
    {
      if ( a4 > 0xFFu )
      {
        if ( a2 && a3 )
          sub_1400802F0(a2, 0, a3);
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
        sub_1400802F0(a2, 0, a3);
      goto LABEL_38;
    }
LABEL_23:
    result = 42;
    *((_DWORD *)v9 + 11) = 42;
    *((_BYTE *)v9 + 48) = 1;
    return result;
  }
  v16 = 0;
  v13 = sub_14007D248(a2, a4, &v16, v9);
  if ( a1 )
    *a1 = v13;
  if ( v13 <= 4 )
    return 0;
  if ( *((_BYTE *)v9 + 48) )
    return *((unsigned int *)v9 + 11);
  return v5;
}

```

## disassembly

```asm
0x140073210  mov     [rsp+arg_0], rbx
0x140073215  mov     [rsp+arg_10], rbp
0x14007321a  mov     [rsp+arg_18], r9w
0x140073220  push    rsi
0x140073221  push    rdi
0x140073222  push    r14
0x140073224  sub     rsp, 40h
0x140073228  xor     ebx, ebx
0x14007322a  mov     rbp, r8
0x14007322d  mov     r14, rdx
0x140073230  mov     rsi, rcx
0x140073233  test    rdx, rdx
0x140073236  jnz     short loc_14007324D
0x140073238  test    r8, r8
0x14007323b  jz      short loc_14007324D
0x14007323d  test    rcx, rcx
0x140073240  jz      loc_14007336A
0x140073246  mov     [rcx], ebx
0x140073248  jmp     loc_14007336A
0x14007324d  test    rsi, rsi
0x140073250  jz      short loc_140073255
0x140073252  or      dword ptr [rcx], 0FFFFFFFFh
0x140073255  mov     rdi, [rsp+58h+arg_20]
0x14007325d  cmp     rbp, 7FFFFFFFh
0x140073264  jbe     short loc_140073270
0x140073266  mov     esi, 16h
0x14007326b  jmp     loc_140073399
0x140073270  cmp     [rdi+28h], bl
0x140073273  jnz     short loc_140073283
0x140073275  mov     rcx, rdi; this
0x140073278  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x14007327d  movzx   r9d, [rsp+58h+arg_18]
0x140073283  mov     rax, [rdi+18h]
0x140073287  mov     ecx, [rax+0Ch]
0x14007328a  cmp     ecx, 0FDE9h
0x140073290  jnz     short loc_1400732C7
0x140073292  movzx   edx, r9w
0x140073296  lea     r8, [rsp+58h+arg_8]
0x14007329b  mov     r9, rdi
0x14007329e  mov     [rsp+58h+arg_8], rbx
0x1400732a3  mov     rcx, r14
0x1400732a6  call    sub_14007D248
0x1400732ab  test    rsi, rsi
0x1400732ae  jz      short loc_1400732B2
0x1400732b0  mov     [rsi], eax
0x1400732b2  cmp     eax, 4
0x1400732b5  jle     loc_14007336A
0x1400732bb  cmp     [rdi+30h], bl
0x1400732be  jz      short loc_1400732C3
0x1400732c0  mov     ebx, [rdi+2Ch]
0x1400732c3  mov     eax, ebx
0x1400732c5  jmp     short loc_1400732FE
0x1400732c7  cmp     [rax+138h], rbx
0x1400732ce  jnz     short loc_14007332B
0x1400732d0  mov     eax, 0FFh
0x1400732d5  cmp     r9w, ax
0x1400732d9  jbe     short loc_140073311
0x1400732db  test    r14, r14
0x1400732de  jz      short loc_1400732F2
0x1400732e0  test    rbp, rbp
0x1400732e3  jz      short loc_1400732F2
0x1400732e5  mov     r8, rbp
0x1400732e8  xor     edx, edx
0x1400732ea  mov     rcx, r14
0x1400732ed  call    sub_1400802F0
0x1400732f2  mov     eax, 2Ah ; '*'
0x1400732f7  mov     [rdi+2Ch], eax
0x1400732fa  mov     byte ptr [rdi+30h], 1
0x1400732fe  mov     rbx, [rsp+58h+arg_0]
0x140073303  mov     rbp, [rsp+58h+arg_10]
0x140073308  add     rsp, 40h
0x14007330c  pop     r14
0x14007330e  pop     rdi
0x14007330f  pop     rsi
0x140073310  retn
0x140073311  test    r14, r14
0x140073314  jz      short loc_14007331E
0x140073316  test    rbp, rbp
0x140073319  jz      short loc_140073394
0x14007331b  mov     [r14], r9b
0x14007331e  test    rsi, rsi
0x140073321  jz      short loc_14007336A
0x140073323  mov     dword ptr [rsi], 1
0x140073329  jmp     short loc_14007336A
0x14007332b  lea     rax, [rsp+58h+arg_8]
0x140073330  mov     dword ptr [rsp+58h+arg_8], ebx
0x140073334  mov     [rsp+58h+var_20], rax
0x140073339  lea     r8, [rsp+58h+arg_18]
0x14007333e  mov     [rsp+58h+var_28], rbx
0x140073343  mov     r9d, 1
0x140073349  mov     dword ptr [rsp+58h+var_30], ebp
0x14007334d  xor     edx, edx
0x14007334f  mov     [rsp+58h+var_38], r14
0x140073354  call    __acrt_WideCharToMultiByte
0x140073359  test    eax, eax
0x14007335b  jz      short loc_14007336E
0x14007335d  cmp     dword ptr [rsp+58h+arg_8], ebx
0x140073361  jnz     short loc_1400732F2
0x140073363  test    rsi, rsi
0x140073366  jz      short loc_14007336A
0x140073368  mov     [rsi], eax
0x14007336a  xor     eax, eax
0x14007336c  jmp     short loc_1400732FE
0x14007336e  call    cs:GetLastError
0x140073374  cmp     eax, 7Ah ; 'z'
0x140073377  jnz     loc_1400732F2
0x14007337d  test    r14, r14
0x140073380  jz      short loc_140073394
0x140073382  test    rbp, rbp
0x140073385  jz      short loc_140073394
0x140073387  mov     r8, rbp
0x14007338a  xor     edx, edx
0x14007338c  mov     rcx, r14
0x14007338f  call    sub_1400802F0
0x140073394  mov     esi, 22h ; '"'
0x140073399  mov     [rdi+2Ch], esi
0x14007339c  xor     r9d, r9d; LineNo
0x14007339f  mov     [rsp+58h+var_30], rdi; __crt_cached_ptd_host *
0x1400733a4  xor     r8d, r8d; FileName
0x1400733a7  xor     edx, edx; FunctionName
0x1400733a9  mov     byte ptr [rdi+30h], 1
0x1400733ad  xor     ecx, ecx; Expression
0x1400733af  mov     [rsp+58h+var_38], rbx; uintptr_t
0x1400733b4  call    sub_14006147C
0x1400733b9  mov     eax, esi
0x1400733bb  jmp     loc_1400732FE
```
