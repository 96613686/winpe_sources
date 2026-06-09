# MtfPrimitiveImpl::Deserialize(IStream *)

- ea: `0x180026ee0`
- end: `0x1800270e8`
- name: `?Deserialize@MtfPrimitiveImpl@@UEAAJPEAUIStream@@@Z`
- size: `520`
- prototype: `__int64 __fastcall(MtfPrimitiveImpl *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180026ee0`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180026f4b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180026f7f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180026f4b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180026f7f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002704b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002705b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002708c`
- `OLEAUT32!__imp_SysFreeString` at `0x180027095`
- `OLEAUT32!__imp_SysFreeString` at `0x18002704b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002705b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002708c`
- `OLEAUT32!__imp_SysFreeString` at `0x180027095`

## pseudocode

```c
__int64 __fastcall MtfPrimitiveImpl::Deserialize(MtfPrimitiveImpl *this, struct IStream *a2)
{
  OLECHAR *v4; // rsi
  __int64 v5; // rax
  OLECHAR *v6; // r14
  OLECHAR *v7; // rcx
  OLECHAR *v8; // rcx
  __int64 v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+38h] [rbp-28h] BYREF
  __int128 v13; // [rsp+40h] [rbp-20h] BYREF
  __int64 v14; // [rsp+50h] [rbp-10h]

  v14 = 0;
  v11 = 0;
  v12 = 0;
  v4 = 0;
  v5 = *(_QWORD *)a2;
  v13 = 0;
  v6 = 0;
  if ( (*(int (__fastcall **)(struct IStream *, __int128 *, __int64, _QWORD))(v5 + 24))(a2, &v13, 24, 0) >= 0 )
  {
    v4 = SysAllocStringLen(0, WORD1(v14));
    if ( (*(int (__fastcall **)(struct IStream *, OLECHAR *, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL))(
           a2,
           v4,
           2 * (unsigned int)WORD1(v14),
           0) >= 0 )
    {
      v6 = SysAllocStringLen(0, WORD2(v14));
      if ( (*(int (__fastcall **)(struct IStream *, OLECHAR *, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL))(
             a2,
             v6,
             2 * (unsigned int)WORD2(v14),
             0) >= 0
        && (!BYTE6(v14)
         || (int)((__int64 (__fastcall *)(GUID *, _QWORD, __int64, GUID *, __int64 *))Hooked_CoCreateInstance)(
                   &CLSID_MtfPropertyBag,
                   0,
                   1,
                   &GUID_06445657_3a07_492d_94c3_052034ef2d12,
                   &v12) >= 0
         && (*(int (__fastcall **)(__int64, struct IStream *))(*(_QWORD *)v12 + 40LL))(v12, a2) >= 0
         && (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v12)(
              v12,
              &GUID_47445657_8d68_4b3b_b716_b0debdd9b3f5,
              &v11) >= 0) )
      {
        v7 = (OLECHAR *)*((_QWORD *)this + 1);
        *(_OWORD *)((char *)this + 36) = v13;
        *((_WORD *)this + 26) = v14;
        SysFreeString(v7);
        v8 = (OLECHAR *)*((_QWORD *)this + 2);
        *((_QWORD *)this + 1) = v4;
        v4 = 0;
        SysFreeString(v8);
        v9 = *((_QWORD *)this + 3);
        *((_QWORD *)this + 2) = v6;
        v6 = 0;
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        *((_QWORD *)this + 3) = v11;
        v11 = 0;
      }
    }
  }
  SysFreeString(v4);
  SysFreeString(v6);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return 0;
}

```

## disassembly

```asm
0x180026ee0  mov     [rsp-18h+arg_10], rbx
0x180026ee5  mov     [rsp-18h+arg_18], rsi
0x180026eea  push    rbp
0x180026eeb  push    rdi
0x180026eec  push    r14
0x180026eee  mov     rbp, rsp
0x180026ef1  sub     rsp, 60h
0x180026ef5  mov     rax, cs:__security_cookie
0x180026efc  xor     rax, rsp
0x180026eff  mov     [rbp+var_8], rax
0x180026f03  xor     eax, eax
0x180026f05  mov     rdi, rdx
0x180026f08  mov     [rbp+var_10], rax
0x180026f0c  mov     rbx, rcx
0x180026f0f  mov     [rbp+var_30], rax
0x180026f13  xorps   xmm0, xmm0
0x180026f16  mov     [rbp+var_28], rax
0x180026f1a  xor     esi, esi
0x180026f1c  mov     rax, [rdx]
0x180026f1f  xor     r9d, r9d
0x180026f22  lea     rdx, [rbp+var_20]
0x180026f26  mov     rcx, rdi
0x180026f29  movups  [rbp+var_20], xmm0
0x180026f2d  lea     r8d, [rsi+18h]
0x180026f31  xor     r14d, r14d
0x180026f34  mov     rax, [rax+18h]
0x180026f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f3d  test    eax, eax
0x180026f3f  js      loc_180027089
0x180026f45  movzx   edx, word ptr [rbp+var_10+2]; ui
0x180026f49  xor     ecx, ecx; strIn
0x180026f4b  call    cs:__imp_SysAllocStringLen
0x180026f51  mov     rcx, [rdi]
0x180026f54  xor     r9d, r9d
0x180026f57  movzx   r8d, word ptr [rbp+var_10+2]
0x180026f5c  mov     rsi, rax
0x180026f5f  add     r8d, r8d
0x180026f62  mov     rdx, rsi
0x180026f65  mov     rax, [rcx+18h]
0x180026f69  mov     rcx, rdi
0x180026f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f71  test    eax, eax
0x180026f73  js      loc_180027089
0x180026f79  movzx   edx, word ptr [rbp+var_10+4]; ui
0x180026f7d  xor     ecx, ecx; strIn
0x180026f7f  call    cs:__imp_SysAllocStringLen
0x180026f85  mov     rcx, [rdi]
0x180026f88  xor     r9d, r9d
0x180026f8b  movzx   r8d, word ptr [rbp+var_10+4]
0x180026f90  mov     r14, rax
0x180026f93  add     r8d, r8d
0x180026f96  mov     rdx, r14
0x180026f99  mov     rax, [rcx+18h]
0x180026f9d  mov     rcx, rdi
0x180026fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fa5  test    eax, eax
0x180026fa7  js      loc_180027089
0x180026fad  cmp     byte ptr [rbp+var_10+6], 0
0x180026fb1  jz      short loc_18002701D
0x180026fb3  xor     edx, edx
0x180026fb5  lea     rax, [rbp+var_28]
0x180026fb9  mov     [rsp+60h+var_40], rax
0x180026fbe  lea     r9, _GUID_06445657_3a07_492d_94c3_052034ef2d12
0x180026fc5  mov     rax, cs:?Hooked_CoCreateInstance@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*Hooked_CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x180026fcc  lea     rcx, CLSID_MtfPropertyBag
0x180026fd3  lea     r8d, [rdx+1]
0x180026fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fdc  test    eax, eax
0x180026fde  js      loc_180027089
0x180026fe4  mov     rcx, [rbp+var_28]
0x180026fe8  mov     rdx, rdi
0x180026feb  mov     rax, [rcx]
0x180026fee  mov     rax, [rax+28h]
0x180026ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ff7  test    eax, eax
0x180026ff9  js      loc_180027089
0x180026fff  mov     rcx, [rbp+var_28]
0x180027003  lea     r8, [rbp+var_30]
0x180027007  lea     rdx, _GUID_47445657_8d68_4b3b_b716_b0debdd9b3f5
0x18002700e  mov     rax, [rcx]
0x180027011  mov     rax, [rax]
0x180027014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027019  test    eax, eax
0x18002701b  js      short loc_180027089
0x18002701d  mov     eax, dword ptr [rbp+var_20]
0x180027020  mov     rcx, [rbx+8]; bstrString
0x180027024  mov     [rbx+24h], eax
0x180027027  mov     eax, dword ptr [rbp+var_20+4]
0x18002702a  mov     [rbx+28h], eax
0x18002702d  mov     eax, dword ptr [rbp+var_20+8]
0x180027030  mov     [rbx+2Ch], eax
0x180027033  movzx   eax, word ptr [rbp+var_20+0Ch]
0x180027037  mov     [rbx+30h], ax
0x18002703b  movzx   eax, word ptr [rbp+var_20+0Eh]
0x18002703f  mov     [rbx+32h], ax
0x180027043  movzx   eax, word ptr [rbp+var_10]
0x180027047  mov     [rbx+34h], ax
0x18002704b  call    cs:__imp_SysFreeString
0x180027051  mov     rcx, [rbx+10h]; bstrString
0x180027055  mov     [rbx+8], rsi
0x180027059  xor     esi, esi
0x18002705b  call    cs:__imp_SysFreeString
0x180027061  mov     rcx, [rbx+18h]
0x180027065  mov     [rbx+10h], r14
0x180027069  xor     r14d, r14d
0x18002706c  test    rcx, rcx
0x18002706f  jz      short loc_18002707D
0x180027071  mov     rax, [rcx]
0x180027074  mov     rax, [rax+10h]
0x180027078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002707d  mov     rax, [rbp+var_30]
0x180027081  mov     [rbx+18h], rax
0x180027085  mov     [rbp+var_30], rsi
0x180027089  mov     rcx, rsi; bstrString
0x18002708c  call    cs:__imp_SysFreeString
0x180027092  mov     rcx, r14; bstrString
0x180027095  call    cs:__imp_SysFreeString
0x18002709b  mov     rcx, [rbp+var_30]
0x18002709f  test    rcx, rcx
0x1800270a2  jz      short loc_1800270B0
0x1800270a4  mov     rax, [rcx]
0x1800270a7  mov     rax, [rax+10h]
0x1800270ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270b0  mov     rcx, [rbp+var_28]
0x1800270b4  test    rcx, rcx
0x1800270b7  jz      short loc_1800270C5
0x1800270b9  mov     rax, [rcx]
0x1800270bc  mov     rax, [rax+10h]
0x1800270c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270c5  xor     eax, eax
0x1800270c7  mov     rcx, [rbp+var_8]
0x1800270cb  xor     rcx, rsp; StackCookie
0x1800270ce  call    __security_check_cookie
0x1800270d3  lea     r11, [rsp+60h+var_s0]
0x1800270d8  mov     rbx, [r11+30h]
0x1800270dc  mov     rsi, [r11+38h]
0x1800270e0  mov     rsp, r11
0x1800270e3  pop     r14
0x1800270e5  pop     rdi
0x1800270e6  pop     rbp
0x1800270e7  retn
```
