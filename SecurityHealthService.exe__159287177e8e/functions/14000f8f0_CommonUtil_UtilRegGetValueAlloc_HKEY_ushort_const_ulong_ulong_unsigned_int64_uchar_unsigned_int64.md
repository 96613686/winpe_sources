# CommonUtil::UtilRegGetValueAlloc(HKEY__ *,ushort const *,ulong,ulong *,unsigned __int64 *,uchar * *,unsigned __int64)

- ea: `0x14000f8f0`
- end: `0x14000faad`
- name: `?UtilRegGetValueAlloc@CommonUtil@@YAJPEAUHKEY__@@PEBGKPEAKPEA_KPEAPEAE_K@Z`
- size: `445`
- prototype: `__int64 __fastcall(CommonUtil *this, const WCHAR *, const unsigned __int16 *, DWORD *, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000fb20`

## callees

- `0x1400015d0`
- `0x1400015f4`
- `0x140002450`
- `0x14000f7d0`
- `0x14000f8f0`
- `0x1400121ec`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegGetValueAlloc(
        CommonUtil *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        DWORD *a4,
        unsigned int *a5,
        unsigned __int64 *a6)
{
  int Value; // ecx
  __int64 result; // rax
  size_t v11; // rbx
  unsigned __int64 v12; // rcx
  void *v13; // rax
  unsigned int v14; // edi
  BYTE *v15; // rbx
  BYTE *v16; // rax
  int v17; // eax
  int v18; // esi
  size_t Size[2]; // [rsp+30h] [rbp-168h] BYREF
  BYTE Src[272]; // [rsp+40h] [rbp-158h] BYREF

  Size[0] = 260;
  Value = CommonUtil::UtilRegGetValue(this, a2, a4, (unsigned int *)Size, Src);
  if ( (int)(Value + 0x80000000) < 0 || Value == -2147024662 )
  {
    if ( *a4 - 1 > 1 )
      return 2147944029LL;
    if ( Value >= 0 )
    {
      v11 = Size[0];
      v12 = Size[0];
      *(_QWORD *)a5 = Size[0];
      v13 = operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
      *a6 = (unsigned __int64)v13;
      if ( v13 )
      {
        memmove_0(v13, Src, v11);
        return 0;
      }
      return 2147942414LL;
    }
  }
  result = 0;
  v14 = -2147024894;
  if ( Value != -2147024662 )
    result = (unsigned int)Value;
  if ( (_DWORD)result == -2147024894 )
    return v14;
  if ( (int)result >= 0 )
  {
    v15 = 0;
    while ( 1 )
    {
      if ( v15 )
        operator delete(v15);
      v16 = (BYTE *)operator new[](Size[0], (const struct std::nothrow_t *)&std::nothrow);
      v15 = v16;
      if ( !v16 )
        return 2147942414LL;
      v17 = CommonUtil::UtilRegGetValue(this, a2, a4, (unsigned int *)Size, v16);
      if ( ((v17 + 0x80000000) & 0x80000000) != 0 || v17 == -2147024662 )
      {
        if ( *a4 - 1 > 1 )
        {
          v14 = -2147023267;
LABEL_29:
          operator delete(v15);
          return v14;
        }
        if ( v17 >= 0 )
        {
          *(_QWORD *)a5 = Size[0];
          *a6 = (unsigned __int64)v15;
          return 0;
        }
      }
      v18 = 0;
      if ( v17 != -2147024662 )
        v18 = v17;
      if ( v18 == -2147024894 )
        goto LABEL_29;
      if ( v18 < 0 )
      {
        operator delete(v15);
        return (unsigned int)v18;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000f8f0  mov     [rsp+arg_10], rbx
0x14000f8f5  push    rbp
0x14000f8f6  push    rsi
0x14000f8f7  push    rdi
0x14000f8f8  push    r12
0x14000f8fa  push    r13
0x14000f8fc  push    r14
0x14000f8fe  push    r15
0x14000f900  sub     rsp, 160h
0x14000f907  mov     rax, cs:__security_cookie
0x14000f90e  xor     rax, rsp
0x14000f911  mov     [rsp+198h+var_48], rax
0x14000f919  mov     r15, [rsp+198h+arg_20]
0x14000f921  lea     rax, [rsp+198h+Src]
0x14000f926  mov     rbp, [rsp+198h+arg_28]
0x14000f92e  mov     r14, r9
0x14000f931  mov     r8, r14; unsigned __int16 *
0x14000f934  mov     [rsp+198h+Size], 104h
0x14000f93d  lea     r9, [rsp+198h+Size]; unsigned int *
0x14000f942  mov     [rsp+198h+var_178], rax; unsigned __int64 *
0x14000f947  mov     r13, rdx
0x14000f94a  mov     r12, rcx
0x14000f94d  call    ?UtilRegGetValue@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAKPEA_KPEAX@Z; CommonUtil::UtilRegGetValue(HKEY__ *,ushort const *,ulong *,unsigned __int64 *,void *)
0x14000f952  mov     esi, 80000000h
0x14000f957  mov     ecx, eax
0x14000f959  add     eax, esi
0x14000f95b  mov     edx, 800700EAh
0x14000f960  test    esi, eax
0x14000f962  jnz     short loc_14000F968
0x14000f964  cmp     ecx, edx
0x14000f966  jnz     short loc_14000F9BB
0x14000f968  mov     eax, [r14]
0x14000f96b  dec     eax
0x14000f96d  cmp     eax, 1
0x14000f970  jbe     short loc_14000F97C
0x14000f972  mov     eax, 8007065Dh
0x14000f977  jmp     loc_14000FA82
0x14000f97c  test    ecx, ecx
0x14000f97e  js      short loc_14000F9BB
0x14000f980  mov     rbx, [rsp+198h+Size]
0x14000f985  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000f98c  mov     rcx, rbx; unsigned __int64
0x14000f98f  mov     [r15], rbx
0x14000f992  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000f997  mov     [rbp+0], rax
0x14000f99b  test    rax, rax
0x14000f99e  jz      loc_14000FA7D
0x14000f9a4  mov     r8, rbx; Size
0x14000f9a7  lea     rdx, [rsp+198h+Src]; Src
0x14000f9ac  mov     rcx, rax; void *
0x14000f9af  call    memmove_0
0x14000f9b4  xor     eax, eax
0x14000f9b6  jmp     loc_14000FA82
0x14000f9bb  xor     eax, eax
0x14000f9bd  mov     edi, 80070002h
0x14000f9c2  cmp     ecx, edx
0x14000f9c4  cmovnz  eax, ecx
0x14000f9c7  cmp     eax, edi
0x14000f9c9  jnz     short loc_14000F9D2
0x14000f9cb  mov     eax, edi
0x14000f9cd  jmp     loc_14000FA82
0x14000f9d2  test    eax, eax
0x14000f9d4  js      loc_14000FA82
0x14000f9da  xor     ebx, ebx
0x14000f9dc  jmp     short loc_14000F9E3
0x14000f9de  mov     esi, 80000000h
0x14000f9e3  test    rbx, rbx
0x14000f9e6  jz      short loc_14000F9F0
0x14000f9e8  mov     rcx, rbx; void *
0x14000f9eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f9f0  mov     rcx, [rsp+198h+Size]; unsigned __int64
0x14000f9f5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000f9fc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000fa01  mov     rbx, rax
0x14000fa04  test    rax, rax
0x14000fa07  jz      short loc_14000FA7D
0x14000fa09  lea     r9, [rsp+198h+Size]; unsigned int *
0x14000fa0e  mov     [rsp+198h+var_178], rax; unsigned __int64 *
0x14000fa13  mov     r8, r14; unsigned __int16 *
0x14000fa16  mov     rdx, r13; HKEY
0x14000fa19  mov     rcx, r12; this
0x14000fa1c  call    ?UtilRegGetValue@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAKPEA_KPEAX@Z; CommonUtil::UtilRegGetValue(HKEY__ *,ushort const *,ulong *,unsigned __int64 *,void *)
0x14000fa21  mov     edx, 800700EAh; unsigned __int64
0x14000fa26  lea     ecx, [rax+rsi]
0x14000fa29  test    esi, ecx
0x14000fa2b  jnz     short loc_14000FA31
0x14000fa2d  cmp     eax, edx
0x14000fa2f  jnz     short loc_14000FA3F
0x14000fa31  mov     ecx, [r14]
0x14000fa34  dec     ecx
0x14000fa36  cmp     ecx, 1
0x14000fa39  ja      short loc_14000FA6B
0x14000fa3b  test    eax, eax
0x14000fa3d  jns     short loc_14000FA5A
0x14000fa3f  xor     esi, esi
0x14000fa41  cmp     eax, edx
0x14000fa43  cmovnz  esi, eax
0x14000fa46  cmp     esi, edi
0x14000fa48  jz      short loc_14000FA70
0x14000fa4a  test    esi, esi
0x14000fa4c  jns     short loc_14000F9DE
0x14000fa4e  mov     rcx, rbx; void *
0x14000fa51  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000fa56  mov     eax, esi
0x14000fa58  jmp     short loc_14000FA82
0x14000fa5a  mov     rax, [rsp+198h+Size]
0x14000fa5f  mov     [r15], rax
0x14000fa62  mov     [rbp+0], rbx
0x14000fa66  jmp     loc_14000F9B4
0x14000fa6b  mov     edi, 8007065Dh
0x14000fa70  mov     rcx, rbx; void *
0x14000fa73  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000fa78  jmp     loc_14000F9CB
0x14000fa7d  mov     eax, 8007000Eh
0x14000fa82  mov     rcx, [rsp+198h+var_48]
0x14000fa8a  xor     rcx, rsp; StackCookie
0x14000fa8d  call    __security_check_cookie
0x14000fa92  mov     rbx, [rsp+198h+arg_10]
0x14000fa9a  add     rsp, 160h
0x14000faa1  pop     r15
0x14000faa3  pop     r14
0x14000faa5  pop     r13
0x14000faa7  pop     r12
0x14000faa9  pop     rdi
0x14000faaa  pop     rsi
0x14000faab  pop     rbp
0x14000faac  retn
```
