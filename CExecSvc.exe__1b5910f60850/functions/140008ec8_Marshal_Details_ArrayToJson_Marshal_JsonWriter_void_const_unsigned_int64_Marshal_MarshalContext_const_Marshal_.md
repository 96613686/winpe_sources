# Marshal::Details::ArrayToJson(Marshal::JsonWriter &,void const *,unsigned __int64,Marshal::MarshalContext const &,Marshal::Details::BaseTypeData const *,Marshal::Details::JsonTypeData const *,unsigned __int64)

- ea: `0x140008ec8`
- end: `0x140008fe4`
- name: `?ArrayToJson@Details@Marshal@@YA_NAEAVJsonWriter@2@PEBX_KAEBVMarshalContext@2@PEBUBaseTypeData@12@PEBUJsonTypeData@12@2@Z`
- size: `284`
- prototype: `bool __fastcall(void ***this, struct Marshal::JsonWriter *, __int64, __int64, const struct Marshal::MarshalContext *, const struct Marshal::Details::BaseTypeData *, const struct Marshal::Details::JsonTypeData *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140006570`
- `0x140006610`

## callees

- `0x1400073c4`
- `0x140008ec8`
- `0x140024010`

## pseudocode

```c
bool __fastcall Marshal::Details::ArrayToJson(
        void ***this,
        struct Marshal::JsonWriter *a2,
        __int64 a3,
        __int64 a4,
        const struct Marshal::MarshalContext *a5,
        const struct Marshal::Details::BaseTypeData *a6,
        const struct Marshal::Details::JsonTypeData *a7)
{
  void **v8; // rcx
  __int64 v10; // rbp
  unsigned __int64 v12; // r10
  bool v13; // cc
  unsigned __int64 v14; // rsi
  void **v15; // rcx
  unsigned __int64 v16; // rdx
  void **v17; // rcx
  unsigned __int64 v18; // rdx

  v8 = *this;
  v10 = a3;
  v12 = (unsigned __int64)v8[2];
  if ( v12 >= (unsigned __int64)v8[3] )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v8, (__int64)a2, a3, 91);
  }
  else
  {
    v13 = (unsigned __int64)v8[3] <= 7;
    v8[2] = (void *)(v12 + 1);
    if ( !v13 )
      v8 = (void **)*v8;
    *(_DWORD *)((char *)v8 + 2 * v12) = 91;
  }
  *((_BYTE *)this + 8) = 1;
  v14 = 0;
  if ( (_QWORD)a7 * v10 )
  {
    do
    {
      if ( !*((_BYTE *)this + 8) )
      {
        v15 = *this;
        v16 = (unsigned __int64)(*this)[2];
        if ( v16 >= (unsigned __int64)(*this)[3] )
        {
          std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v15, v16, a3, 44);
        }
        else
        {
          v13 = (unsigned __int64)v15[3] <= 7;
          v15[2] = (void *)(v16 + 1);
          if ( !v13 )
            v15 = (void **)*v15;
          *(_DWORD *)((char *)v15 + 2 * v16) = 44;
        }
      }
      *((_BYTE *)this + 8) = 0;
      (*(void (__fastcall **)(void ***, char *, __int64))a6)(this, (char *)a2 + v14, a4);
      v14 += (unsigned __int64)a7;
    }
    while ( v14 < (__int64)a7 * v10 );
    v10 = a3;
  }
  v17 = *this;
  v18 = (unsigned __int64)(*this)[2];
  if ( v18 >= (unsigned __int64)(*this)[3] )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v17, v18, a3, 93);
  }
  else
  {
    v13 = (unsigned __int64)v17[3] <= 7;
    v17[2] = (void *)(v18 + 1);
    if ( !v13 )
      v17 = (void **)*v17;
    *(_DWORD *)((char *)v17 + 2 * v18) = 93;
  }
  *((_BYTE *)this + 8) = 0;
  return v10 != 0;
}

```

## disassembly

```asm
0x140008ec8  push    rbx
0x140008eca  push    rbp
0x140008ecb  push    rsi
0x140008ecc  push    rdi
0x140008ecd  push    r12
0x140008ecf  push    r14
0x140008ed1  push    r15
0x140008ed3  sub     rsp, 30h
0x140008ed7  mov     r14, [rsp+68h+arg_28]
0x140008edf  mov     rbx, rcx
0x140008ee2  mov     rcx, [rcx]; Src
0x140008ee5  mov     r12, r9
0x140008ee8  mov     rbp, r8
0x140008eeb  mov     [rsp+68h+var_48], r8
0x140008ef0  mov     r15, rdx
0x140008ef3  mov     r10, [rcx+10h]
0x140008ef7  cmp     r10, [rcx+18h]
0x140008efb  jnb     short loc_140008F19
0x140008efd  cmp     qword ptr [rcx+18h], 7
0x140008f02  lea     rax, [r10+1]
0x140008f06  mov     [rcx+10h], rax
0x140008f0a  jbe     short loc_140008F0F
0x140008f0c  mov     rcx, [rcx]
0x140008f0f  mov     dword ptr [rcx+r10*2], 5Bh ; '['
0x140008f17  jmp     short loc_140008F24
0x140008f19  mov     r9d, 5Bh ; '['
0x140008f1f  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x140008f24  mov     rdi, rbp
0x140008f27  mov     byte ptr [rbx+8], 1
0x140008f2b  imul    rdi, [rsp+68h+arg_30]
0x140008f34  xor     esi, esi
0x140008f36  test    rdi, rdi
0x140008f39  jz      short loc_140008F98
0x140008f3b  lea     ebp, [rsi+2Ch]
0x140008f3e  cmp     byte ptr [rbx+8], 0
0x140008f42  jnz     short loc_140008F70
0x140008f44  mov     rcx, [rbx]; Src
0x140008f47  mov     rdx, [rcx+10h]
0x140008f4b  cmp     rdx, [rcx+18h]
0x140008f4f  jnb     short loc_140008F68
0x140008f51  cmp     qword ptr [rcx+18h], 7
0x140008f56  lea     rax, [rdx+1]
0x140008f5a  mov     [rcx+10h], rax
0x140008f5e  jbe     short loc_140008F63
0x140008f60  mov     rcx, [rcx]
0x140008f63  mov     [rcx+rdx*2], ebp
0x140008f66  jmp     short loc_140008F70
0x140008f68  mov     r9d, ebp
0x140008f6b  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x140008f70  mov     byte ptr [rbx+8], 0
0x140008f74  lea     rdx, [r15+rsi]
0x140008f78  mov     rax, [r14]
0x140008f7b  mov     r8, r12
0x140008f7e  mov     rcx, rbx
0x140008f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f86  add     rsi, [rsp+68h+arg_30]
0x140008f8e  cmp     rsi, rdi
0x140008f91  jb      short loc_140008F3E
0x140008f93  mov     rbp, [rsp+68h+var_48]
0x140008f98  mov     rcx, [rbx]; Src
0x140008f9b  mov     rdx, [rcx+10h]
0x140008f9f  cmp     rdx, [rcx+18h]
0x140008fa3  jnb     short loc_140008FC0
0x140008fa5  cmp     qword ptr [rcx+18h], 7
0x140008faa  lea     rax, [rdx+1]
0x140008fae  mov     [rcx+10h], rax
0x140008fb2  jbe     short loc_140008FB7
0x140008fb4  mov     rcx, [rcx]
0x140008fb7  mov     dword ptr [rcx+rdx*2], 5Dh ; ']'
0x140008fbe  jmp     short loc_140008FCB
0x140008fc0  mov     r9d, 5Dh ; ']'
0x140008fc6  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x140008fcb  test    rbp, rbp
0x140008fce  mov     byte ptr [rbx+8], 0
0x140008fd2  setnz   al
0x140008fd5  add     rsp, 30h
0x140008fd9  pop     r15
0x140008fdb  pop     r14
0x140008fdd  pop     r12
0x140008fdf  pop     rdi
0x140008fe0  pop     rsi
0x140008fe1  pop     rbp
0x140008fe2  pop     rbx
0x140008fe3  retn
```
