# Bcp47::GetExtensionSubstring(Windows::Internal::CLanguage const &,ushort)

- ea: `0x18001fd68`
- end: `0x18001fef3`
- name: `?GetExtensionSubstring@Bcp47@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVCLanguage@Internal@Windows@@G@Z`
- size: `395`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180005780`

## callees

- `0x180004080`
- `0x180004bb4`
- `0x180005750`
- `0x18000d8f8`
- `0x180010078`
- `0x180013294`
- `0x18001f4a0`
- `0x18001fa7c`
- `0x18001fd68`
- `0x1800227c0`

## import_xrefs

- `msvcrt!towlower` at `0x18001fdb8`
- `msvcrt!towlower` at `0x18001fdb8`

## pseudocode

```c
_QWORD *__fastcall Bcp47::GetExtensionSubstring(_QWORD *a1, __int64 a2, __int64 a3)
{
  wint_t v3; // bx
  wint_t v6; // r14
  __int64 v7; // r8
  __int64 v8; // rbx
  int SubtagFields; // eax
  _WORD *v10; // rdx
  _WORD *v11; // r8
  _WORD *v12; // r9
  _WORD *i; // rcx
  __int64 v14; // r9
  _QWORD pExceptionObject[3]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v17[4]; // [rsp+50h] [rbp-B8h] BYREF
  _WORD v18[88]; // [rsp+78h] [rbp-90h] BYREF

  pExceptionObject[2] = -2;
  v3 = a3;
  pExceptionObject[0] = a1;
  Bcp47::GetExtensionSingletons(v17, a2, a3);
  v6 = towlower(v3);
  LOWORD(pExceptionObject[0]) = v6;
  v8 = -1;
  if ( std::wstring::find(v17, pExceptionObject, 0, 1) == -1 )
  {
    std::wstring::wstring((__int64)a1, (__int64)&qword_18002C640);
  }
  else
  {
    SubtagFields = Windows::Internal::CLanguage::GetSubtagFields(a2, 96, v7, v18);
    if ( SubtagFields < 0 )
    {
      LODWORD(pExceptionObject[0]) = SubtagFields;
      throw (long *)pExceptionObject;
    }
    v10 = v18;
    do
      ++v8;
    while ( v18[v8] );
    v11 = &v18[v8];
    v12 = v11;
    while ( v10 != v11 )
    {
      for ( i = v10 + 1; i != v11 && *i != 45; ++i )
        ;
      if ( (char *)i - (char *)v10 == 2 )
      {
        if ( *v10 == v6 )
        {
          v12 = i;
          if ( i != v11 )
            v12 = i + 1;
        }
        else if ( v12 != v11 )
        {
          break;
        }
        if ( *v10 == 120 )
          break;
      }
      v10 = i;
      if ( i != v11 )
        v10 = i + 1;
    }
    a1[3] = 7;
    std::wstring::_Eos(a1, 0);
    std::wstring::_Construct<unsigned short *>(a1, v14);
  }
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)v17);
  return a1;
}

```

## disassembly

```asm
0x18001fd68  mov     rax, rsp
0x18001fd6b  push    rbp
0x18001fd6c  push    rsi
0x18001fd6d  push    rdi
0x18001fd6e  push    r14
0x18001fd70  push    r15
0x18001fd72  lea     rbp, [rax-58h]
0x18001fd76  sub     rsp, 130h
0x18001fd7d  mov     qword ptr [rsp+150h+var_110], 0FFFFFFFFFFFFFFFEh
0x18001fd86  mov     [rax+20h], rbx
0x18001fd8a  mov     rax, cs:__security_cookie
0x18001fd91  xor     rax, rsp
0x18001fd94  mov     [rbp+50h+var_30], rax
0x18001fd98  movzx   ebx, r8w
0x18001fd9c  mov     rsi, rdx
0x18001fd9f  mov     rdi, rcx
0x18001fda2  mov     qword ptr [rsp+150h+pExceptionObject], rcx
0x18001fda7  xor     r15d, r15d
0x18001fdaa  lea     rcx, [rsp+48h]
0x18001fdaf  call    ?GetExtensionSingletons@Bcp47@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVCLanguage@Internal@Windows@@@Z; Bcp47::GetExtensionSingletons(Windows::Internal::CLanguage const &)
0x18001fdb4  nop
0x18001fdb5  movzx   ecx, bx; C
0x18001fdb8  call    cs:__imp_towlower
0x18001fdbe  movzx   r14d, ax
0x18001fdc2  mov     word ptr [rsp+150h+pExceptionObject], ax
0x18001fdc7  lea     r9d, [r15+1]
0x18001fdcb  xor     r8d, r8d
0x18001fdce  lea     rdx, [rsp+150h+pExceptionObject]
0x18001fdd3  lea     rcx, [rsp+48h]
0x18001fdd8  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x18001fddd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001fde1  cmp     rax, rbx
0x18001fde4  jz      loc_18001FEB3
0x18001fdea  lea     r9, [rsp+70h]
0x18001fdef  lea     edx, [rbx+61h]
0x18001fdf2  mov     rcx, rsi
0x18001fdf5  call    ?GetSubtagFields@CLanguage@Internal@Windows@@QEBAJW4BCP47_SUBTAG_FLAGS@23@_KPEAGPEA_K@Z; Windows::Internal::CLanguage::GetSubtagFields(Windows::Internal::BCP47_SUBTAG_FLAGS,unsigned __int64,ushort *,unsigned __int64 *)
0x18001fdfa  test    eax, eax
0x18001fdfc  jns     short loc_18001FE14
0x18001fdfe  mov     dword ptr [rsp+150h+pExceptionObject], eax
0x18001fe02  lea     rdx, _TI1J; pThrowInfo
0x18001fe09  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x18001fe0e  call    _CxxThrowException_0
0x18001fe14  lea     rdx, [rsp+70h]
0x18001fe19  lea     rax, [rsp+70h]
0x18001fe1e  inc     rbx
0x18001fe21  cmp     [rax+rbx*2], r15w
0x18001fe26  jnz     short loc_18001FE1E
0x18001fe28  lea     r8, [rsp+70h]
0x18001fe2d  lea     r8, [r8+rbx*2]
0x18001fe31  mov     r9, r8
0x18001fe34  cmp     rdx, r8
0x18001fe37  jz      short loc_18001FE94
0x18001fe39  lea     rcx, [rdx+2]
0x18001fe3d  jmp     short loc_18001FE49
0x18001fe3f  cmp     word ptr [rcx], 2Dh ; '-'
0x18001fe43  jz      short loc_18001FE4E
0x18001fe45  add     rcx, 2
0x18001fe49  cmp     rcx, r8
0x18001fe4c  jnz     short loc_18001FE3F
0x18001fe4e  mov     rax, rcx
0x18001fe51  sub     rax, rdx
0x18001fe54  cmp     rax, 2
0x18001fe58  jnz     short loc_18001FE80
0x18001fe5a  movzx   r10d, word ptr [rdx]
0x18001fe5e  cmp     r10w, r14w
0x18001fe62  jnz     short loc_18001FE74
0x18001fe64  lea     rax, [rcx+2]
0x18001fe68  mov     r9, rcx
0x18001fe6b  cmp     rcx, r8
0x18001fe6e  cmovnz  r9, rax
0x18001fe72  jmp     short loc_18001FE79
0x18001fe74  cmp     r9, r8
0x18001fe77  jnz     short loc_18001FE90
0x18001fe79  cmp     r10w, 78h ; 'x'
0x18001fe7e  jz      short loc_18001FE94
0x18001fe80  lea     rax, [rcx+2]
0x18001fe84  mov     rdx, rcx
0x18001fe87  cmp     rcx, r8
0x18001fe8a  cmovnz  rdx, rax
0x18001fe8e  jmp     short loc_18001FE34
0x18001fe90  lea     r8, [rdx-2]
0x18001fe94  mov     qword ptr [rdi+18h], 7
0x18001fe9c  xor     edx, edx
0x18001fe9e  mov     rcx, rdi
0x18001fea1  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x18001fea6  mov     rdx, r9
0x18001fea9  mov     rcx, rdi
0x18001feac  call    ??$_Construct@PEAG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXPEAG0Uforward_iterator_tag@1@@Z; std::wstring::_Construct<ushort *>(ushort *,ushort *,std::forward_iterator_tag)
0x18001feb1  jmp     short loc_18001FEC3
0x18001feb3  lea     rdx, qword_18002C640
0x18001feba  mov     rcx, rdi
0x18001febd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001fec2  nop
0x18001fec3  lea     rcx, [rsp+48h]
0x18001fec8  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18001fecd  mov     rax, rdi
0x18001fed0  mov     rcx, [rbp+50h+var_30]
0x18001fed4  xor     rcx, rsp; StackCookie
0x18001fed7  call    __security_check_cookie
0x18001fedc  mov     rbx, [rsp+150h+arg_18]
0x18001fee4  add     rsp, 130h
0x18001feeb  pop     r15
0x18001feed  pop     r14
0x18001feef  pop     rdi
0x18001fef0  pop     rsi
0x18001fef1  pop     rbp
0x18001fef2  retn
```
