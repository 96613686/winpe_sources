# NLG::RegistryKey::ContainsValue(_variant_t &,_bstr_t *)

- ea: `0x1800420dc`
- end: `0x1800421c5`
- name: `?ContainsValue@RegistryKey@NLG@@QEBA_NAEAV_variant_t@@PEAV_bstr_t@@@Z`
- size: `233`
- prototype: `bool __fastcall(NLG::RegistryKey *__hidden this, struct _variant_t *, struct _bstr_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180049618`

## callees

- `0x180005190`
- `0x180009790`
- `0x18001a07c`
- `0x18001a0d8`
- `0x180038adc`
- `0x1800419c4`
- `0x1800420dc`
- `0x180049e50`
- `0x180049ec8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall NLG::RegistryKey::ContainsValue(NLG::RegistryKey *this, unsigned __int16 **a2, struct _bstr_t *a3)
{
  unsigned int ValueCount; // ebp
  unsigned int i; // ebx
  __int64 ValueName; // rax
  unsigned int v9; // edx
  VARIANTARG v11; // [rsp+30h] [rbp-38h] BYREF
  volatile signed __int32 *v12; // [rsp+70h] [rbp+8h] BYREF

  if ( *(_QWORD *)this )
  {
    ValueCount = NLG::RegistryKey::GetValueCount(this);
    if ( ValueCount )
    {
      for ( i = 0; i < ValueCount; ++i )
      {
        NLG::RegistryKey::GetValue(this, &v11, i);
        if ( (unsigned __int8)_variant_t::operator==(&v11, a2)
          || v11.vt == 8 && *(_WORD *)a2 == 8 && !(unsigned int)CMN_CompareStringNoCaseW(v11.bstrVal, a2[1]) )
        {
          if ( a3 )
          {
            ValueName = NLG::RegistryKey::GetValueName(this, &v12, i);
            _bstr_t::operator=(a3, ValueName);
            _bstr_t::_Free(&v12, v9);
          }
          _variant_t::~_variant_t(&v11);
          return 1;
        }
        _variant_t::~_variant_t(&v11);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800420dc  mov     rax, rsp
0x1800420df  push    rsi
0x1800420e0  push    rdi
0x1800420e1  push    r14
0x1800420e3  sub     rsp, 50h
0x1800420e7  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x1800420ef  mov     [rax+10h], rbx
0x1800420f3  mov     [rax+18h], rbp
0x1800420f7  mov     r14, r8
0x1800420fa  mov     rsi, rdx
0x1800420fd  mov     rdi, rcx
0x180042100  cmp     qword ptr [rcx], 0
0x180042104  jz      loc_1800421AE
0x18004210a  call    ?GetValueCount@RegistryKey@NLG@@QEBAKXZ; NLG::RegistryKey::GetValueCount(void)
0x18004210f  mov     ebp, eax
0x180042111  test    eax, eax
0x180042113  jz      loc_1800421AE
0x180042119  xor     ebx, ebx
0x18004211b  cmp     ebx, ebp
0x18004211d  jnb     loc_1800421AE
0x180042123  mov     r8d, ebx
0x180042126  lea     rdx, [rsp+68h+var_38]
0x18004212b  mov     rcx, rdi
0x18004212e  call    ?GetValue@RegistryKey@NLG@@QEBA?AV_variant_t@@K@Z; NLG::RegistryKey::GetValue(ulong)
0x180042133  nop
0x180042134  mov     rdx, rsi
0x180042137  lea     rcx, [rsp+68h+var_38]
0x18004213c  call    ??8_variant_t@@QEBA_NPEBUtagVARIANT@@@Z; _variant_t::operator==(tagVARIANT const *)
0x180042141  test    al, al
0x180042143  jnz     short loc_180042173
0x180042145  cmp     [rsp+68h+var_38], 8
0x18004214b  jnz     short loc_180042165
0x18004214d  cmp     word ptr [rsi], 8
0x180042151  jnz     short loc_180042165
0x180042153  mov     rdx, [rsi+8]
0x180042157  mov     rcx, [rsp+68h+var_30]
0x18004215c  call    CMN_CompareStringNoCaseW
0x180042161  test    eax, eax
0x180042163  jz      short loc_180042173
0x180042165  lea     rcx, [rsp+68h+var_38]; this
0x18004216a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004216f  inc     ebx
0x180042171  jmp     short loc_18004211B
0x180042173  test    r14, r14
0x180042176  jz      short loc_1800421A0
0x180042178  mov     r8d, ebx
0x18004217b  lea     rdx, [rsp+68h+arg_0]
0x180042180  mov     rcx, rdi
0x180042183  call    ?GetValueName@RegistryKey@NLG@@QEBA?AV_bstr_t@@K@Z; NLG::RegistryKey::GetValueName(ulong)
0x180042188  nop
0x180042189  mov     rdx, rax
0x18004218c  mov     rcx, r14
0x18004218f  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180042194  nop
0x180042195  lea     rcx, [rsp+68h+arg_0]; this
0x18004219a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004219f  nop
0x1800421a0  lea     rcx, [rsp+68h+var_38]; this
0x1800421a5  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800421aa  mov     al, 1
0x1800421ac  jmp     short loc_1800421B0
0x1800421ae  xor     al, al
0x1800421b0  lea     r11, [rsp+68h+var_18]
0x1800421b5  mov     rbx, [r11+28h]
0x1800421b9  mov     rbp, [r11+30h]
0x1800421bd  mov     rsp, r11
0x1800421c0  pop     r14
0x1800421c2  pop     rdi
0x1800421c3  pop     rsi
0x1800421c4  retn
```
