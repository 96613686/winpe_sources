# Csl::OfflineHive::DeleteKeyRecursive(ushort const *)

- ea: `0x18002ad68`
- end: `0x18002ae2f`
- name: `?DeleteKeyRecursive@OfflineHive@Csl@@QEAAJPEBG@Z`
- size: `199`
- prototype: `__int64 __fastcall(Csl::OfflineHive *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180029264`

## callees

- `0x1800045e4`
- `0x18000adb8`
- `0x18002acb0`
- `0x18002ad68`
- `0x18002af0c`

## string_xrefs

- `0x18002adac`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002adf1`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::DeleteKeyRecursive(Csl::OfflineHive *this, const unsigned __int16 *a2)
{
  int v4; // eax
  unsigned int v5; // edi
  unsigned int v6; // ebx
  const unsigned __int16 **i; // rbx
  int v8; // eax
  __int64 v9; // rdx
  int v11[4]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(__m128i *)v11 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v12 = -1;
  v4 = Csl::OfflineHive::EnumerateSubkeys(this, a2, v11);
  v5 = -2147024894;
  v6 = v4;
  if ( v4 != -2147024894 )
  {
    if ( v4 >= 0 )
    {
      for ( i = *(const unsigned __int16 ***)v11; i != *(const unsigned __int16 ***)&v11[2]; i += 4 )
      {
        v8 = Csl::OfflineHive::DeleteKey(this, *i);
        v5 = v8;
        if ( v8 < 0 )
        {
          v9 = 413;
LABEL_9:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v9,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)(unsigned int)v8,
            v11[0]);
          goto LABEL_13;
        }
      }
      v8 = Csl::OfflineHive::DeleteKey(this, a2);
      v5 = v8;
      if ( v8 < 0 )
      {
        v9 = 418;
        goto LABEL_9;
      }
      v5 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x197,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
        (const char *)(unsigned int)v4,
        v11[0]);
      v5 = v6;
    }
  }
LABEL_13:
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)v11);
  return v5;
}

```

## disassembly

```asm
0x18002ad68  push    rbx
0x18002ad6a  push    rbp
0x18002ad6b  push    rsi
0x18002ad6c  push    rdi
0x18002ad6d  sub     rsp, 48h
0x18002ad71  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18002ad79  lea     r8, [rsp+68h+var_48]
0x18002ad7e  movdqu  xmmword ptr [rsp+68h+var_48], xmm0; int
0x18002ad84  mov     rbp, rdx
0x18002ad87  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFFh
0x18002ad90  mov     rsi, rcx
0x18002ad93  call    ?EnumerateSubkeys@OfflineHive@Csl@@QEBAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@_N@Z; Csl::OfflineHive::EnumerateSubkeys(ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &,bool)
0x18002ad98  mov     edi, 80070002h
0x18002ad9d  mov     ebx, eax
0x18002ad9f  cmp     eax, edi
0x18002ada1  jz      short loc_18002AE19
0x18002ada3  test    eax, eax
0x18002ada5  jns     short loc_18002ADC4
0x18002ada7  mov     rcx, [rsp+68h]; this
0x18002adac  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002adb3  mov     r9d, eax; char *
0x18002adb6  mov     edx, 197h; void *
0x18002adbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002adc0  mov     edi, ebx
0x18002adc2  jmp     short loc_18002AE19
0x18002adc4  mov     rbx, qword ptr [rsp+68h+var_48]
0x18002adc9  mov     rcx, rsi; this
0x18002adcc  cmp     rbx, qword ptr [rsp+68h+var_48+8]
0x18002add1  jz      short loc_18002AE02
0x18002add3  mov     rdx, [rbx]; unsigned __int16 *
0x18002add6  call    ?DeleteKey@OfflineHive@Csl@@QEAAJPEBG@Z; Csl::OfflineHive::DeleteKey(ushort const *)
0x18002addb  mov     edi, eax
0x18002addd  test    eax, eax
0x18002addf  js      short loc_18002ADE7
0x18002ade1  add     rbx, 20h ; ' '
0x18002ade5  jmp     short loc_18002ADC9
0x18002ade7  mov     edx, 19Dh; void *
0x18002adec  mov     rcx, [rsp+68h]; this
0x18002adf1  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002adf8  mov     r9d, eax; char *
0x18002adfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ae00  jmp     short loc_18002AE19
0x18002ae02  mov     rdx, rbp; unsigned __int16 *
0x18002ae05  call    ?DeleteKey@OfflineHive@Csl@@QEAAJPEBG@Z; Csl::OfflineHive::DeleteKey(ushort const *)
0x18002ae0a  mov     edi, eax
0x18002ae0c  test    eax, eax
0x18002ae0e  jns     short loc_18002AE17
0x18002ae10  mov     edx, 1A2h
0x18002ae15  jmp     short loc_18002ADEC
0x18002ae17  xor     edi, edi
0x18002ae19  lea     rcx, [rsp+68h+var_48]
0x18002ae1e  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18002ae23  mov     eax, edi
0x18002ae25  add     rsp, 48h
0x18002ae29  pop     rdi
0x18002ae2a  pop     rsi
0x18002ae2b  pop     rbp
0x18002ae2c  pop     rbx
0x18002ae2d  retn
```
