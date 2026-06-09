# CommonUtil::UtilRegGetValueAlloc(HKEY__ *,ushort const *,ulong,ulong *,unsigned __int64 *,uchar * *,unsigned __int64)

- ea: `0x14000e47c`
- end: `0x14000e641`
- name: `?UtilRegGetValueAlloc@CommonUtil@@YAJPEAUHKEY__@@PEBGKPEAKPEA_KPEAPEAE_K@Z`
- size: `453`
- prototype: `__int64 __fastcall(CommonUtil *this, HKEY, const unsigned __int16 *, DWORD *, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000285c`

## callees

- `0x1400015f0`
- `0x140001614`
- `0x140002310`
- `0x14000e35c`
- `0x14000e47c`
- `0x14000fa8c`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegGetValueAlloc(
        CommonUtil *this,
        HKEY a2,
        const unsigned __int16 *a3,
        DWORD *a4,
        unsigned int *a5,
        unsigned __int64 *a6)
{
  int Value; // ecx
  __int64 result; // rax
  size_t v10; // rbx
  unsigned __int64 v11; // rcx
  void *v12; // rax
  unsigned int v13; // edi
  BYTE *v14; // rbx
  BYTE *v15; // rax
  int v16; // eax
  int v17; // esi
  size_t Size[2]; // [rsp+30h] [rbp-168h] BYREF
  BYTE Src[272]; // [rsp+40h] [rbp-158h] BYREF

  Size[0] = 260;
  Value = CommonUtil::UtilRegGetValue(this, (const WCHAR *)&stru_140012E68, a4, (unsigned int *)Size, Src);
  if ( (int)(Value + 0x80000000) < 0 || Value == -2147024662 )
  {
    if ( *a4 - 1 > 1 )
      return 2147944029LL;
    if ( Value >= 0 )
    {
      v10 = Size[0];
      v11 = Size[0];
      *(_QWORD *)a5 = Size[0];
      v12 = operator new[](v11, (const struct std::nothrow_t *)std::nothrow);
      *a6 = (unsigned __int64)v12;
      if ( v12 )
      {
        memmove_0(v12, Src, v10);
        return 0;
      }
      return 2147942414LL;
    }
  }
  result = 0;
  v13 = -2147024894;
  if ( Value != -2147024662 )
    result = (unsigned int)Value;
  if ( (_DWORD)result == -2147024894 )
    return v13;
  if ( (int)result >= 0 )
  {
    v14 = 0;
    while ( 1 )
    {
      if ( v14 )
        operator delete(v14);
      v15 = (BYTE *)operator new[](Size[0], (const struct std::nothrow_t *)std::nothrow);
      v14 = v15;
      if ( !v15 )
        return 2147942414LL;
      v16 = CommonUtil::UtilRegGetValue(this, (const WCHAR *)&stru_140012E68, a4, (unsigned int *)Size, v15);
      if ( ((v16 + 0x80000000) & 0x80000000) != 0 || v16 == -2147024662 )
      {
        if ( *a4 - 1 > 1 )
        {
          v13 = -2147023267;
LABEL_29:
          operator delete(v14);
          return v13;
        }
        if ( v16 >= 0 )
        {
          *(_QWORD *)a5 = Size[0];
          *a6 = (unsigned __int64)v14;
          return 0;
        }
      }
      v17 = 0;
      if ( v16 != -2147024662 )
        v17 = v16;
      if ( v17 == -2147024894 )
        goto LABEL_29;
      if ( v17 < 0 )
      {
        operator delete(v14);
        return (unsigned int)v17;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000e47c  mov     [rsp+arg_8], rbx
0x14000e481  push    rbp
0x14000e482  push    rsi
0x14000e483  push    rdi
0x14000e484  push    r12
0x14000e486  push    r13
0x14000e488  push    r14
0x14000e48a  push    r15
0x14000e48c  sub     rsp, 160h
0x14000e493  mov     rax, cs:__security_cookie
0x14000e49a  xor     rax, rsp
0x14000e49d  mov     [rsp+198h+var_48], rax
0x14000e4a5  mov     r15, [rsp+198h+arg_20]
0x14000e4ad  lea     rax, [rsp+198h+Src]
0x14000e4b2  mov     rbp, [rsp+198h+arg_28]
0x14000e4ba  lea     rdx, stru_140012E68; HKEY
0x14000e4c1  mov     r14, r9
0x14000e4c4  mov     [rsp+198h+Size], 104h
0x14000e4cd  mov     r8, r14; unsigned __int16 *
0x14000e4d0  mov     [rsp+198h+var_178], rax; unsigned __int64 *
0x14000e4d5  lea     r9, [rsp+198h+Size]; unsigned int *
0x14000e4da  mov     r12, rcx
0x14000e4dd  call    ?UtilRegGetValue@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAKPEA_KPEAX@Z; CommonUtil::UtilRegGetValue(HKEY__ *,ushort const *,ulong *,unsigned __int64 *,void *)
0x14000e4e2  mov     esi, 80000000h
0x14000e4e7  mov     ecx, eax
0x14000e4e9  add     eax, esi
0x14000e4eb  mov     r13d, 800700EAh
0x14000e4f1  test    esi, eax
0x14000e4f3  jnz     short loc_14000E4FA
0x14000e4f5  cmp     ecx, r13d
0x14000e4f8  jnz     short loc_14000E54D
0x14000e4fa  mov     eax, [r14]
0x14000e4fd  dec     eax
0x14000e4ff  cmp     eax, 1
0x14000e502  jbe     short loc_14000E50E
0x14000e504  mov     eax, 8007065Dh
0x14000e509  jmp     loc_14000E616
0x14000e50e  test    ecx, ecx
0x14000e510  js      short loc_14000E54D
0x14000e512  mov     rbx, [rsp+198h+Size]
0x14000e517  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e51e  mov     rcx, rbx; unsigned __int64
0x14000e521  mov     [r15], rbx
0x14000e524  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000e529  mov     [rbp+0], rax
0x14000e52d  test    rax, rax
0x14000e530  jz      loc_14000E611
0x14000e536  mov     r8, rbx; Size
0x14000e539  lea     rdx, [rsp+198h+Src]; Src
0x14000e53e  mov     rcx, rax; void *
0x14000e541  call    memmove_0
0x14000e546  xor     eax, eax
0x14000e548  jmp     loc_14000E616
0x14000e54d  xor     eax, eax
0x14000e54f  mov     edi, 80070002h
0x14000e554  cmp     ecx, r13d
0x14000e557  cmovnz  eax, ecx
0x14000e55a  cmp     eax, edi
0x14000e55c  jnz     short loc_14000E565
0x14000e55e  mov     eax, edi
0x14000e560  jmp     loc_14000E616
0x14000e565  test    eax, eax
0x14000e567  js      loc_14000E616
0x14000e56d  xor     ebx, ebx
0x14000e56f  jmp     short loc_14000E576
0x14000e571  mov     esi, 80000000h
0x14000e576  test    rbx, rbx
0x14000e579  jz      short loc_14000E583
0x14000e57b  mov     rcx, rbx; void *
0x14000e57e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e583  mov     rcx, [rsp+198h+Size]; unsigned __int64
0x14000e588  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e58f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000e594  mov     rbx, rax
0x14000e597  test    rax, rax
0x14000e59a  jz      short loc_14000E611
0x14000e59c  lea     r9, [rsp+198h+Size]; unsigned int *
0x14000e5a1  mov     [rsp+198h+var_178], rax; unsigned __int64 *
0x14000e5a6  mov     r8, r14; unsigned __int16 *
0x14000e5a9  lea     rdx, stru_140012E68; HKEY
0x14000e5b0  mov     rcx, r12; this
0x14000e5b3  call    ?UtilRegGetValue@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAKPEA_KPEAX@Z; CommonUtil::UtilRegGetValue(HKEY__ *,ushort const *,ulong *,unsigned __int64 *,void *)
0x14000e5b8  lea     ecx, [rax+rsi]
0x14000e5bb  test    esi, ecx
0x14000e5bd  jnz     short loc_14000E5C4
0x14000e5bf  cmp     eax, r13d
0x14000e5c2  jnz     short loc_14000E5D2
0x14000e5c4  mov     ecx, [r14]
0x14000e5c7  dec     ecx
0x14000e5c9  cmp     ecx, 1
0x14000e5cc  ja      short loc_14000E5FF
0x14000e5ce  test    eax, eax
0x14000e5d0  jns     short loc_14000E5EE
0x14000e5d2  xor     esi, esi
0x14000e5d4  cmp     eax, r13d
0x14000e5d7  cmovnz  esi, eax
0x14000e5da  cmp     esi, edi
0x14000e5dc  jz      short loc_14000E604
0x14000e5de  test    esi, esi
0x14000e5e0  jns     short loc_14000E571
0x14000e5e2  mov     rcx, rbx; void *
0x14000e5e5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e5ea  mov     eax, esi
0x14000e5ec  jmp     short loc_14000E616
0x14000e5ee  mov     rax, [rsp+198h+Size]
0x14000e5f3  mov     [r15], rax
0x14000e5f6  mov     [rbp+0], rbx
0x14000e5fa  jmp     loc_14000E546
0x14000e5ff  mov     edi, 8007065Dh
0x14000e604  mov     rcx, rbx; void *
0x14000e607  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e60c  jmp     loc_14000E55E
0x14000e611  mov     eax, 8007000Eh
0x14000e616  mov     rcx, [rsp+198h+var_48]
0x14000e61e  xor     rcx, rsp; StackCookie
0x14000e621  call    __security_check_cookie
0x14000e626  mov     rbx, [rsp+198h+arg_8]
0x14000e62e  add     rsp, 160h
0x14000e635  pop     r15
0x14000e637  pop     r14
0x14000e639  pop     r13
0x14000e63b  pop     r12
0x14000e63d  pop     rdi
0x14000e63e  pop     rsi
0x14000e63f  pop     rbp
0x14000e640  retn
```
