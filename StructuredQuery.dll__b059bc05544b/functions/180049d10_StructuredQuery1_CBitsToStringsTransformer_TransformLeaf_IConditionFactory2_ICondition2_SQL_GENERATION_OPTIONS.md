# StructuredQuery1::CBitsToStringsTransformer::TransformLeaf(IConditionFactory2 *,ICondition2 *,SQL_GENERATION_OPTIONS,ICondition2 * *,int *)

- ea: `0x180049d10`
- end: `0x180049fa2`
- name: `?TransformLeaf@CBitsToStringsTransformer@StructuredQuery1@@UEAAJPEAUIConditionFactory2@@PEAUICondition2@@W4SQL_GENERATION_OPTIONS@@PEAPEAU4@PEAH@Z`
- size: `658`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000bd20`
- `0x18004146c`
- `0x180049d10`
- `0x18005daf0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180049de6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180049de6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049f4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049f4a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049f54`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049f54`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::CBitsToStringsTransformer::TransformLeaf(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        int a4,
        _QWORD *a5,
        _DWORD *a6)
{
  _QWORD *v6; // r14
  _DWORD *v7; // r15
  __int64 v10; // rax
  __int64 (__fastcall *v12)(__int64 *, __int128 *, _QWORD, PROPVARIANT *); // rax
  int v13; // ebx
  __int64 v14; // rax
  int v15; // r12d
  int v16; // eax
  unsigned int v17; // ecx
  void *v18; // r14
  GUID *v19; // r10
  unsigned int v20; // r15d
  const size_t *v21; // r11
  __int64 v22; // r8
  __int64 v23; // r9
  int v24; // edi
  int v25; // eax
  __int64 result; // rax
  __int64 (__fastcall *v27)(__int64, const PROPERTYKEY *, __int64, const wchar_t *, const size_t *, _DWORD, GUID *, void **); // rax
  __int64 (__fastcall *v28)(__int64, const PROPERTYKEY *, __int64, __int128 *, const WCHAR *, const size_t *, _QWORD, _QWORD, _QWORD, _DWORD, GUID *, __int64 *); // rax
  __int64 v29; // [rsp+70h] [rbp-79h] BYREF
  void *v30; // [rsp+78h] [rbp-71h] BYREF
  int v31; // [rsp+80h] [rbp-69h]
  int v32; // [rsp+84h] [rbp-65h]
  BOOL v33; // [rsp+88h] [rbp-61h]
  PCNZWCH lpString1; // [rsp+90h] [rbp-59h] BYREF
  __int64 v35; // [rsp+98h] [rbp-51h] BYREF
  _QWORD *v36; // [rsp+A0h] [rbp-49h]
  _DWORD *v37; // [rsp+A8h] [rbp-41h]
  __int128 v38; // [rsp+B0h] [rbp-39h] BYREF
  __int64 v39; // [rsp+C0h] [rbp-29h]
  PROPVARIANT pvar[2]; // [rsp+C8h] [rbp-21h] BYREF
  __int64 v41; // [rsp+D8h] [rbp-11h]
  __int128 v42; // [rsp+E0h] [rbp-9h] BYREF
  int v43; // [rsp+F0h] [rbp+7h]

  v6 = a5;
  v7 = a6;
  v43 = 0;
  v41 = 0;
  v10 = *a3;
  v31 = a4;
  v36 = a5;
  v37 = a6;
  v12 = *(__int64 (__fastcall **)(__int64 *, __int128 *, _QWORD, PROPVARIANT *))(v10 + 128);
  v35 = 0;
  v42 = 0;
  *(_OWORD *)pvar = 0;
  v13 = v12(a3, &v42, 0, pvar);
  if ( v13 < 0 )
    goto LABEL_20;
  v14 = *a3;
  v15 = (int)pvar[1];
  lpString1 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, PCNZWCH *))(v14 + 88))(a3, &lpString1);
  if ( v13 < 0 )
    goto LABEL_19;
  v16 = CompareStringW(0x7Fu, 1u, lpString1, -1, L"System.StructuredQueryType.AnyBitsSet", -1);
  v17 = *(_DWORD *)(a1 + 40);
  v32 = v16;
  v30 = 0;
  v33 = v16 == 2;
  v13 = FixedCapacityObjectCollection::CreateInstance(v17, &GUID_5632b1a4_e38a_400a_928a_d4cd63230295, &v30);
  if ( v13 < 0 )
    goto LABEL_18;
  v18 = v30;
  v19 = &GUID_0fc988d4_c935_4b97_a973_46282ea175c8;
  v20 = 0;
  v21 = &cchOriginalDestLength;
  while ( v20 < *(_DWORD *)(a1 + 40) )
  {
    v22 = *(_QWORD *)(a1 + 32);
    v23 = 2LL * v20;
    v24 = *(_DWORD *)(v22 + 16LL * v20 + 8);
    if ( (v15 & v24) == v24 )
    {
      v29 = 0;
      if ( (v31 & 0x80u) == 0 || !operator==((__int64)&v42, (__int64)&PKEY_SFGAOFlags) )
        goto LABEL_10;
      if ( v24 != 0x400000 )
      {
        if ( v24 == 528384 )
        {
          v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, GUID *, __int64 *))(*(_QWORD *)a2 + 56LL))(
                  a2,
                  0,
                  0,
                  v19,
                  &v29);
          goto LABEL_12;
        }
        if ( v24 == 0x80000 )
        {
          v39 = 0;
          v38 = 0;
          LOWORD(v38) = 19;
          v28 = *(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int64, __int128 *, const WCHAR *, const size_t *, _QWORD, _QWORD, _QWORD, _DWORD, GUID *, __int64 *))(*(_QWORD *)a2 + 112LL);
          DWORD2(v38) = 2;
          v25 = v28(
                  a2,
                  &PKEY_FileAttributes,
                  14,
                  &v38,
                  L"System.StructuredQueryType.AllBitsSet",
                  v21,
                  0,
                  0,
                  0,
                  0,
                  v19,
                  &v29);
LABEL_12:
          v13 = v25;
        }
        else
        {
LABEL_10:
          if ( v32 != 2 || !*(_DWORD *)(v22 + 8 * v23 + 12) )
          {
            v25 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, const size_t *, _DWORD, GUID *, __int64 *))(*(_QWORD *)a2 + 88LL))(
                    a2,
                    a1 + 8,
                    1,
                    *(_QWORD *)(v22 + 8 * v23),
                    v21,
                    0,
                    v19,
                    &v29);
            goto LABEL_12;
          }
        }
LABEL_13:
        if ( v13 >= 0 && v29 )
        {
          v13 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v18 + 40LL))(v18);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          v15 &= ~v24;
        }
        goto LABEL_7;
      }
      v27 = *(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int64, const wchar_t *, const size_t *, _DWORD, GUID *, void **))(*(_QWORD *)a2 + 88LL);
      v30 = 0;
      v13 = v27(a2, &PKEY_Kind, 1, L"Folder", v21, 0, v19, &v30);
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, GUID *, __int64 *))(*(_QWORD *)a2 + 64LL))(
                a2,
                v30,
                0,
                &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                &v29);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v30 + 16LL))(v30);
        goto LABEL_13;
      }
    }
LABEL_7:
    ++v20;
    v19 = &GUID_0fc988d4_c935_4b97_a973_46282ea175c8;
    v21 = &cchOriginalDestLength;
    if ( v13 < 0 )
      goto LABEL_17;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, BOOL, void *, _QWORD, GUID *, __int64 *))(*(_QWORD *)a2 + 72LL))(
          a2,
          v33,
          v18,
          0,
          &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
          &v35);
LABEL_17:
  (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
  v6 = v36;
  v7 = v37;
LABEL_18:
  CoTaskMemFree((LPVOID)lpString1);
LABEL_19:
  PropVariantClear(pvar);
LABEL_20:
  *v6 = v35;
  result = (unsigned int)v13;
  *v7 = 1;
  return result;
}

```

## disassembly

```asm
0x180049d10  mov     [rsp-8+arg_18], rbx
0x180049d15  push    rbp
0x180049d16  push    rsi
0x180049d17  push    rdi
0x180049d18  push    r12
0x180049d1a  push    r13
0x180049d1c  push    r14
0x180049d1e  push    r15
0x180049d20  lea     rbp, [rsp-17h]
0x180049d25  sub     rsp, 100h
0x180049d2c  mov     rax, cs:__security_cookie
0x180049d33  xor     rax, rsp
0x180049d36  mov     [rbp+47h+var_38], rax
0x180049d3a  mov     r14, [rbp+47h+arg_20]
0x180049d3e  xor     eax, eax
0x180049d40  mov     r15, [rbp+47h+arg_28]
0x180049d44  mov     rdi, r8
0x180049d47  mov     [rbp+47h+var_40], eax
0x180049d4a  mov     rsi, rdx
0x180049d4d  mov     [rbp+47h+var_58], rax
0x180049d51  lea     rdx, [rbp+47h+var_50]
0x180049d55  mov     rax, [r8]
0x180049d58  mov     r13, rcx
0x180049d5b  mov     [rbp+47h+var_B0], r9d
0x180049d5f  xorps   xmm0, xmm0
0x180049d62  xorps   xmm1, xmm1
0x180049d65  mov     [rbp+47h+var_90], r14
0x180049d69  lea     r9, [rbp+47h+pvar]
0x180049d6d  mov     [rbp+47h+var_88], r15
0x180049d71  mov     rax, [rax+80h]
0x180049d78  xor     r8d, r8d
0x180049d7b  mov     rcx, rdi
0x180049d7e  mov     [rbp+47h+var_98], 0
0x180049d86  movups  [rbp+47h+var_50], xmm0
0x180049d8a  movups  xmmword ptr [rbp+47h+pvar], xmm1
0x180049d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d93  mov     ebx, eax
0x180049d95  test    eax, eax
0x180049d97  js      loc_180049F5A
0x180049d9d  mov     rax, [rdi]
0x180049da0  lea     rdx, [rbp+47h+lpString1]
0x180049da4  mov     r12d, dword ptr [rbp+47h+pvar+8]
0x180049da8  mov     rcx, rdi
0x180049dab  mov     [rbp+47h+lpString1], 0
0x180049db3  mov     rax, [rax+58h]
0x180049db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049dbc  mov     ebx, eax
0x180049dbe  test    eax, eax
0x180049dc0  js      loc_180049F50
0x180049dc6  mov     r8, [rbp+47h+lpString1]; lpString1
0x180049dca  lea     rax, aSystemStructur_4; "System.StructuredQueryType.AnyBitsSet"
0x180049dd1  or      r9d, 0FFFFFFFFh; cchCount1
0x180049dd5  mov     [rsp+130h+cchCount2], r9d; cchCount2
0x180049dda  mov     [rsp+130h+lpString2], rax; lpString2
0x180049ddf  lea     edx, [r9+2]; dwCmpFlags
0x180049de3  lea     ecx, [rdx+7Eh]; Locale
0x180049de6  call    cs:__imp_CompareStringW
0x180049dec  mov     ecx, [r13+28h]; unsigned int
0x180049df0  lea     r8, [rbp+47h+var_B8]; void **
0x180049df4  xor     edi, edi
0x180049df6  mov     [rbp+47h+var_AC], eax
0x180049df9  cmp     eax, 2
0x180049dfc  mov     [rbp+47h+var_B8], 0
0x180049e04  lea     rdx, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295; struct _GUID *
0x180049e0b  setz    dil
0x180049e0f  mov     [rbp+47h+var_A8], edi
0x180049e12  call    ?CreateInstance@FixedCapacityObjectCollection@@SAJIAEBU_GUID@@PEAPEAX@Z; FixedCapacityObjectCollection::CreateInstance(uint,_GUID const &,void * *)
0x180049e17  mov     ebx, eax
0x180049e19  test    eax, eax
0x180049e1b  js      loc_180049F46
0x180049e21  mov     r14, [rbp+47h+var_B8]
0x180049e25  lea     r10, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x180049e2c  xor     r15d, r15d
0x180049e2f  lea     r11, cchOriginalDestLength
0x180049e36  cmp     r15d, [r13+28h]
0x180049e3a  jnb     loc_180049F00
0x180049e40  mov     r8, [r13+20h]
0x180049e44  mov     r9d, r15d
0x180049e47  add     r9, r9
0x180049e4a  mov     edi, [r8+r9*8+8]
0x180049e4f  mov     eax, edi
0x180049e51  and     eax, r12d
0x180049e54  cmp     eax, edi
0x180049e56  jz      short loc_180049E72
0x180049e58  inc     r15d
0x180049e5b  lea     r10, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x180049e62  lea     r11, cchOriginalDestLength
0x180049e69  test    ebx, ebx
0x180049e6b  jns     short loc_180049E36
0x180049e6d  jmp     loc_180049F2F
0x180049e72  test    byte ptr [rbp+47h+var_B0], 80h
0x180049e76  mov     [rbp+47h+var_C0], 0
0x180049e7e  jnz     loc_18008A874
0x180049e84  cmp     [rbp+47h+var_AC], 2
0x180049e88  jz      loc_180049F91
0x180049e8e  mov     rax, [rsi]
0x180049e91  lea     rcx, [rbp+47h+var_C0]
0x180049e95  mov     r9, [r8+r9*8]
0x180049e99  lea     rdx, [r13+8]
0x180049e9d  mov     [rsp+130h+var_F8], rcx
0x180049ea2  mov     r8d, 1
0x180049ea8  mov     [rsp+130h+var_100], r10
0x180049ead  mov     rcx, rsi
0x180049eb0  mov     rax, [rax+58h]
0x180049eb4  mov     [rsp+130h+cchCount2], 0
0x180049ebc  mov     [rsp+130h+lpString2], r11
0x180049ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ec6  mov     ebx, eax
0x180049ec8  test    ebx, ebx
0x180049eca  js      short loc_180049E58
0x180049ecc  mov     rdx, [rbp+47h+var_C0]
0x180049ed0  test    rdx, rdx
0x180049ed3  jz      short loc_180049E58
0x180049ed5  mov     rax, [r14]
0x180049ed8  mov     rcx, r14
0x180049edb  mov     rax, [rax+28h]
0x180049edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ee4  mov     rcx, [rbp+47h+var_C0]
0x180049ee8  mov     ebx, eax
0x180049eea  mov     rax, [rcx]
0x180049eed  mov     rax, [rax+10h]
0x180049ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ef6  not     edi
0x180049ef8  and     r12d, edi
0x180049efb  jmp     loc_180049E58
0x180049f00  mov     rax, [rsi]
0x180049f03  lea     rcx, [rbp+47h+var_98]
0x180049f07  mov     edx, [rbp+47h+var_A8]
0x180049f0a  xor     r9d, r9d
0x180049f0d  mov     qword ptr [rsp+130h+cchCount2], rcx
0x180049f12  mov     r8, r14
0x180049f15  lea     rcx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x180049f1c  mov     rax, [rax+48h]
0x180049f20  mov     [rsp+130h+lpString2], rcx
0x180049f25  mov     rcx, rsi
0x180049f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f2d  mov     ebx, eax
0x180049f2f  mov     rax, [r14]
0x180049f32  mov     rcx, r14
0x180049f35  mov     rax, [rax+10h]
0x180049f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f3e  mov     r14, [rbp+47h+var_90]
0x180049f42  mov     r15, [rbp+47h+var_88]
0x180049f46  mov     rcx, [rbp+47h+lpString1]; pv
0x180049f4a  call    cs:__imp_CoTaskMemFree
0x180049f50  lea     rcx, [rbp+47h+pvar]; pvar
0x180049f54  call    cs:__imp_PropVariantClear
0x180049f5a  mov     rax, [rbp+47h+var_98]
0x180049f5e  mov     [r14], rax
0x180049f61  mov     eax, ebx
0x180049f63  mov     dword ptr [r15], 1
0x180049f6a  mov     rcx, [rbp+47h+var_38]
0x180049f6e  xor     rcx, rsp; StackCookie
0x180049f71  call    __security_check_cookie
0x180049f76  mov     rbx, [rsp+130h+arg_18]
0x180049f7e  add     rsp, 100h
0x180049f85  pop     r15
0x180049f87  pop     r14
0x180049f89  pop     r13
0x180049f8b  pop     r12
0x180049f8d  pop     rdi
0x180049f8e  pop     rsi
0x180049f8f  pop     rbp
0x180049f90  retn
0x180049f91  cmp     dword ptr [r8+r9*8+0Ch], 0
0x180049f97  jz      loc_180049E8E
0x180049f9d  jmp     loc_180049EC8
0x18008a874  lea     rdx, PKEY_SFGAOFlags
0x18008a87b  lea     rcx, [rbp+47h+var_50]
0x18008a87f  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18008a884  test    eax, eax
0x18008a886  jz      loc_180049E84
0x18008a88c  cmp     edi, 400000h
0x18008a892  jnz     loc_18008A926
0x18008a898  mov     rax, [rsi]
0x18008a89b  lea     rcx, [rbp+47h+var_B8]
0x18008a89f  mov     [rsp+130h+var_F8], rcx
0x18008a8a4  lea     r9, aFolder; "Folder"
0x18008a8ab  mov     [rsp+130h+var_100], r10
0x18008a8b0  lea     rdx, PKEY_Kind
0x18008a8b7  mov     [rsp+130h+cchCount2], 0
0x18008a8bf  mov     r8d, 1
0x18008a8c5  mov     rax, [rax+58h]
0x18008a8c9  mov     rcx, rsi
0x18008a8cc  mov     [rbp+47h+var_B8], 0
0x18008a8d4  mov     [rsp+130h+lpString2], r11
0x18008a8d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a8de  mov     ebx, eax
0x18008a8e0  test    eax, eax
0x18008a8e2  js      loc_180049E58
0x18008a8e8  mov     rax, [rsi]
0x18008a8eb  lea     rcx, [rbp+47h+var_C0]
0x18008a8ef  mov     rdx, [rbp+47h+var_B8]
0x18008a8f3  lea     r9, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x18008a8fa  mov     [rsp+130h+lpString2], rcx
0x18008a8ff  xor     r8d, r8d
0x18008a902  mov     rcx, rsi
0x18008a905  mov     rax, [rax+40h]
0x18008a909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a90e  mov     rcx, [rbp+47h+var_B8]
0x18008a912  mov     ebx, eax
0x18008a914  mov     rax, [rcx]
0x18008a917  mov     rax, [rax+10h]
0x18008a91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a920  nop
0x18008a921  jmp     loc_180049EC8
0x18008a926  cmp     edi, 81000h
0x18008a92c  jnz     short loc_18008A954
0x18008a92e  mov     rax, [rsi]
0x18008a931  lea     rcx, [rbp+47h+var_C0]
0x18008a935  mov     [rsp+130h+lpString2], rcx
0x18008a93a  mov     r9, r10
0x18008a93d  xor     r8d, r8d
0x18008a940  xor     edx, edx
0x18008a942  mov     rcx, rsi
0x18008a945  mov     rax, [rax+38h]
0x18008a949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a94e  nop
0x18008a94f  jmp     loc_180049EC6
0x18008a954  cmp     edi, 80000h
0x18008a95a  jnz     loc_180049E84
0x18008a960  xor     eax, eax
0x18008a962  lea     rcx, [rbp+47h+var_C0]
0x18008a966  mov     [rsp+130h+var_D8], rcx
0x18008a96b  lea     r9, [rbp+47h+var_80]
0x18008a96f  mov     [rsp+130h+var_E0], r10
0x18008a974  lea     rcx, aSystemStructur_9; "System.StructuredQueryType.AllBitsSet"
0x18008a97b  mov     [rsp+130h+var_E8], 0
0x18008a983  lea     rdx, PKEY_FileAttributes
0x18008a98a  mov     [rbp+47h+var_70], rax
0x18008a98e  xorps   xmm0, xmm0
0x18008a991  mov     [rsp+130h+var_F0], 0
0x18008a99a  mov     eax, 13h
0x18008a99f  movups  [rbp+47h+var_80], xmm0
0x18008a9a3  mov     word ptr [rbp+47h+var_80], ax
0x18008a9a7  mov     r8d, 0Eh
0x18008a9ad  mov     rax, [rsi]
0x18008a9b0  mov     [rsp+130h+var_F8], 0
0x18008a9b9  mov     [rsp+130h+var_100], 0
0x18008a9c2  mov     qword ptr [rsp+130h+cchCount2], r11
0x18008a9c7  mov     rax, [rax+70h]
0x18008a9cb  mov     [rsp+130h+lpString2], rcx
0x18008a9d0  mov     rcx, rsi
0x18008a9d3  mov     dword ptr [rbp+47h+var_80+8], 2
0x18008a9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a9df  nop
0x18008a9e0  jmp     loc_180049EC6
```
