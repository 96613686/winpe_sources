# LanguageComponentsInstallerTelemetry::GetSerializedFeatureList(std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>> const &)

- ea: `0x180024d34`
- end: `0x180024e47`
- name: `?GetSerializedFeatureList@LanguageComponentsInstallerTelemetry@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@3@@Z`
- size: `275`
- prototype: `_QWORD *__fastcall(_QWORD *Src, __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025240`
- `0x1800253c8`

## callees

- `0x180003520`
- `0x180006380`
- `0x18000e978`
- `0x180021b6c`
- `0x180024d34`
- `0x180025c30`

## pseudocode

```c
_QWORD *__fastcall LanguageComponentsInstallerTelemetry::GetSerializedFeatureList(_QWORD *Src, __int64 *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rsi
  int v5; // ebp
  char v6; // r14
  __int64 v7; // rcx
  _QWORD *v8; // rdx
  char *v10[4]; // [rsp+40h] [rbp-68h] BYREF

  v3 = a2[1];
  v4 = *a2;
  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 7;
  *(_WORD *)Src = 0;
  v5 = 4;
  v6 = 1;
  while ( v4 != v3 )
  {
    CbsLanguageFeature::ToString(v4, v10);
    v5 |= 0x38u;
    if ( v10[2] )
    {
      if ( !v6 )
      {
        v7 = Src[2];
        if ( Src[3] == v7 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(
            Src,
            59);
        }
        else
        {
          Src[2] = v7 + 1;
          if ( Src[3] <= 7u )
            v8 = Src;
          else
            v8 = (_QWORD *)*Src;
          *(_DWORD *)((char *)v8 + 2 * v7) = 59;
        }
      }
      std::wstring::append(Src);
      v6 = 0;
    }
    std::wstring::~wstring(v10);
    v4 += 192;
  }
  return Src;
}

```

## disassembly

```asm
0x180024d34  push    rbx
0x180024d36  push    rbp
0x180024d37  push    rsi
0x180024d38  push    rdi
0x180024d39  push    r13
0x180024d3b  push    r14
0x180024d3d  sub     rsp, 78h
0x180024d41  mov     rax, cs:__security_cookie
0x180024d48  xor     rax, rsp
0x180024d4b  mov     [rsp+0A8h+var_48], rax
0x180024d50  mov     rdi, rcx
0x180024d53  mov     [rsp+0A8h+var_70], rcx
0x180024d58  mov     [rsp+0A8h+var_78], 0
0x180024d60  mov     rbx, [rdx+8]
0x180024d64  mov     rsi, [rdx]
0x180024d67  xorps   xmm0, xmm0
0x180024d6a  movups  xmmword ptr [rcx], xmm0
0x180024d6d  mov     qword ptr [rcx+10h], 0
0x180024d75  mov     qword ptr [rcx+18h], 7
0x180024d7d  xor     eax, eax
0x180024d7f  mov     [rcx], ax
0x180024d82  lea     ebp, [rax+4]
0x180024d85  mov     [rsp+0A8h+var_78], ebp
0x180024d89  mov     r14b, 1
0x180024d8c  lea     r13d, [rax+3Bh]
0x180024d90  mov     rax, rsi
0x180024d93  cmp     rax, rbx
0x180024d96  jz      loc_180024E2A
0x180024d9c  lea     rdx, [rsp+0A8h+var_68]
0x180024da1  mov     rcx, rsi
0x180024da4  call    ?ToString@CbsLanguageFeature@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CbsLanguageFeature::ToString(void)
0x180024da9  or      ebp, 38h
0x180024dac  mov     [rsp+0A8h+var_78], ebp
0x180024db0  cmp     [rsp+0A8h+var_58], 0
0x180024db6  jz      short loc_180024E14
0x180024db8  test    r14b, r14b
0x180024dbb  jnz     short loc_180024E04
0x180024dbd  mov     rcx, [rdi+10h]
0x180024dc1  mov     rax, [rdi+18h]
0x180024dc5  sub     rax, rcx
0x180024dc8  cmp     rax, 1
0x180024dcc  jb      short loc_180024DEE
0x180024dce  lea     rax, [rcx+1]
0x180024dd2  mov     [rdi+10h], rax
0x180024dd6  cmp     qword ptr [rdi+18h], 7
0x180024ddb  jbe     short loc_180024DE2
0x180024ddd  mov     rdx, [rdi]
0x180024de0  jmp     short loc_180024DE5
0x180024de2  mov     rdx, rdi
0x180024de5  mov     dword ptr [rdx+rcx*2], 3Bh ; ';'
0x180024dec  jmp     short loc_180024E04
0x180024dee  mov     [rsp+0A8h+var_88], r13w; __int16
0x180024df4  mov     edx, 1
0x180024df9  mov     r9d, edx
0x180024dfc  mov     rcx, rdi; Src
0x180024dff  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180024e04  lea     rdx, [rsp+0A8h+var_68]
0x180024e09  mov     rcx, rdi; Src
0x180024e0c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180024e11  xor     r14b, r14b
0x180024e14  lea     rcx, [rsp+0A8h+var_68]; void *
0x180024e19  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024e1e  add     rsi, 0C0h
0x180024e25  jmp     loc_180024D90
0x180024e2a  mov     rax, rdi
0x180024e2d  mov     rcx, [rsp+0A8h+var_48]
0x180024e32  xor     rcx, rsp; StackCookie
0x180024e35  call    __security_check_cookie
0x180024e3a  add     rsp, 78h
0x180024e3e  pop     r14
0x180024e40  pop     r13
0x180024e42  pop     rdi
0x180024e43  pop     rsi
0x180024e44  pop     rbp
0x180024e45  pop     rbx
0x180024e46  retn
```
