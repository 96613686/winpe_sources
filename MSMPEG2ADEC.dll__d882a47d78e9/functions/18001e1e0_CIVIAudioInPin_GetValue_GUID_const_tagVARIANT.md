# CIVIAudioInPin::GetValue(_GUID const *,tagVARIANT *)

- ea: `0x18001e1e0`
- end: `0x18001e400`
- name: `?GetValue@CIVIAudioInPin@@UEAAJPEBU_GUID@@PEAUtagVARIANT@@@Z`
- size: `544`
- prototype: `int(CIVIAudioInPin *__hidden this, const struct _GUID *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18001e1e0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001e2b6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e2b6`
- `OLEAUT32!__imp_VariantClear` at `0x18001e251`
- `OLEAUT32!__imp_VariantClear` at `0x18001e251`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001e2a0`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001e2a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e2cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e2cb`

## pseudocode

```c
__int64 __fastcall CIVIAudioInPin::GetValue(CIVIAudioInPin *this, const struct _GUID *a2, struct tagVARIANT *a3)
{
  __int64 v4; // rcx
  GUID *v6; // rcx
  const OLECHAR *v7; // rcx
  BSTR v8; // rax
  LPOLESTR v9; // rcx
  __int64 v10; // rax
  LONG v11; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  LPOLESTR lpsz; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_e5005239_bd89_4be3_9c0f_5dde317988cc.Data1
    || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_e5005239_bd89_4be3_9c0f_5dde317988cc.Data4 )
  {
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_4a52cda8_30f8_4216_be0f_ba0b2025921d.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_4a52cda8_30f8_4216_be0f_ba0b2025921d.Data4 )
    {
      v10 = *((_QWORD *)this + 65);
      a3->vt = 19;
      v11 = *(_DWORD *)(v10 + 6564);
    }
    else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_971d2723_1acb_42e7_855c_520a4b70a5f2.Data1
           && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_971d2723_1acb_42e7_855c_520a4b70a5f2.Data4 )
    {
      v12 = *((_QWORD *)this + 65);
      a3->vt = 19;
      v11 = *(_DWORD *)(v12 + 6460);
    }
    else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_1d3583c4_1583_474e_b71a_5ee463c198e4.Data1
           && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_1d3583c4_1583_474e_b71a_5ee463c198e4.Data4 )
    {
      v13 = *((_QWORD *)this + 65);
      a3->vt = 19;
      v11 = *(_DWORD *)(v13 + 6544);
    }
    else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_17f89cb3_c38d_4368_9ede_63b94d177f9f.Data1
           && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_17f89cb3_c38d_4368_9ede_63b94d177f9f.Data4 )
    {
      v14 = *((_QWORD *)this + 65);
      a3->vt = 19;
      v11 = *(_DWORD *)(v14 + 6548);
    }
    else
    {
      if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_59488217_007a_4f7a_8e41_5c48b1eac5c6.Data1
        || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_59488217_007a_4f7a_8e41_5c48b1eac5c6.Data4 )
      {
        return 2147942487LL;
      }
      v15 = *((_QWORD *)this + 65);
      a3->vt = 19;
      v11 = *(_DWORD *)(v15 + 6552);
    }
    a3->lVal = v11;
    return 0;
  }
  v4 = *((_QWORD *)this + 65);
  lpsz = 0;
  switch ( *(_DWORD *)(v4 + 6452) )
  {
    case 3:
      v6 = &GUID_8e4228a0_f000_4e0b_8f54_ab8d24ad61a2;
      break;
    case 4:
      v6 = &GUID_91106f36_02c5_4f75_9719_3b7abf75e1f6;
      break;
    case 5:
      v6 = &GUID_f2421da5_bbb4_4cd5_a996_933c6b5d1347;
      break;
    case 6:
      v6 = &GUID_600bc0ca_6a1f_4e91_b241_1bbeb1cb19e0;
      break;
    case 9:
      v6 = &GUID_97df7828_b94a_47e2_a4bc_51194db22a4d;
      break;
    default:
      VariantClear(a3);
      return 2147500037LL;
  }
  StringFromCLSID(v6, &lpsz);
  v7 = lpsz;
  a3->vt = 8;
  v8 = SysAllocString(v7);
  v9 = lpsz;
  a3->llVal = (LONGLONG)v8;
  CoTaskMemFree(v9);
  return 0;
}

```

## disassembly

```asm
0x18001e1e0  push    rbx
0x18001e1e2  sub     rsp, 20h
0x18001e1e6  mov     rbx, r8
0x18001e1e9  test    rdx, rdx
0x18001e1ec  jz      loc_18001E3F4
0x18001e1f2  test    rbx, rbx
0x18001e1f5  jz      loc_18001E3F4
0x18001e1fb  mov     rax, [rdx]
0x18001e1fe  cmp     rax, qword ptr cs:_GUID_e5005239_bd89_4be3_9c0f_5dde317988cc.Data1
0x18001e205  mov     [rsp+28h+arg_0], rdi
0x18001e20a  jnz     loc_18001E2E5
0x18001e210  mov     rax, [rdx+8]
0x18001e214  cmp     rax, qword ptr cs:_GUID_e5005239_bd89_4be3_9c0f_5dde317988cc.Data4
0x18001e21b  jnz     loc_18001E2E5
0x18001e221  mov     rcx, [rcx+208h]
0x18001e228  xor     edi, edi
0x18001e22a  mov     [rsp+28h+lpsz], rdi
0x18001e22f  mov     edx, [rcx+1934h]
0x18001e235  sub     edx, 3
0x18001e238  jz      short loc_18001E294
0x18001e23a  sub     edx, 1
0x18001e23d  jz      short loc_18001E28B
0x18001e23f  sub     edx, 1
0x18001e242  jz      short loc_18001E282
0x18001e244  sub     edx, 1
0x18001e247  jz      short loc_18001E279
0x18001e249  cmp     edx, 3
0x18001e24c  jz      short loc_18001E270
0x18001e24e  mov     rcx, rbx; pvarg
0x18001e251  call    cs:__imp_VariantClear
0x18001e258  nop     dword ptr [rax+rax+00h]
0x18001e25d  mov     edi, 80004005h
0x18001e262  mov     eax, edi
0x18001e264  mov     rdi, [rsp+28h+arg_0]
0x18001e269  add     rsp, 20h
0x18001e26d  pop     rbx
0x18001e26e  retn
0x18001e270  lea     rcx, _GUID_97df7828_b94a_47e2_a4bc_51194db22a4d
0x18001e277  jmp     short loc_18001E29B
0x18001e279  lea     rcx, _GUID_600bc0ca_6a1f_4e91_b241_1bbeb1cb19e0
0x18001e280  jmp     short loc_18001E29B
0x18001e282  lea     rcx, _GUID_f2421da5_bbb4_4cd5_a996_933c6b5d1347
0x18001e289  jmp     short loc_18001E29B
0x18001e28b  lea     rcx, _GUID_91106f36_02c5_4f75_9719_3b7abf75e1f6
0x18001e292  jmp     short loc_18001E29B
0x18001e294  lea     rcx, _GUID_8e4228a0_f000_4e0b_8f54_ab8d24ad61a2; rclsid
0x18001e29b  lea     rdx, [rsp+28h+lpsz]; lplpsz
0x18001e2a0  call    cs:__imp_StringFromCLSID
0x18001e2a7  nop     dword ptr [rax+rax+00h]
0x18001e2ac  mov     rcx, [rsp+28h+lpsz]; psz
0x18001e2b1  mov     word ptr [rbx], 8
0x18001e2b6  call    cs:__imp_SysAllocString
0x18001e2bd  nop     dword ptr [rax+rax+00h]
0x18001e2c2  mov     rcx, [rsp+28h+lpsz]; pv
0x18001e2c7  mov     [rbx+8], rax
0x18001e2cb  call    cs:__imp_CoTaskMemFree
0x18001e2d2  nop     dword ptr [rax+rax+00h]
0x18001e2d7  mov     eax, edi
0x18001e2d9  mov     rdi, [rsp+28h+arg_0]
0x18001e2de  add     rsp, 20h
0x18001e2e2  pop     rbx
0x18001e2e3  retn
0x18001e2e5  mov     rax, [rdx]
0x18001e2e8  cmp     rax, qword ptr cs:_GUID_4a52cda8_30f8_4216_be0f_ba0b2025921d.Data1
0x18001e2ef  jnz     short loc_18001E325
0x18001e2f1  mov     rax, [rdx+8]
0x18001e2f5  cmp     rax, qword ptr cs:_GUID_4a52cda8_30f8_4216_be0f_ba0b2025921d.Data4
0x18001e2fc  jnz     short loc_18001E325
0x18001e2fe  mov     rax, [rcx+208h]
0x18001e305  mov     word ptr [r8], 13h
0x18001e30b  mov     eax, [rax+19A4h]
0x18001e311  xor     edi, edi
0x18001e313  mov     [r8+8], eax
0x18001e317  mov     eax, edi
0x18001e319  mov     rdi, [rsp+28h+arg_0]
0x18001e31e  add     rsp, 20h
0x18001e322  pop     rbx
0x18001e323  retn
0x18001e325  mov     rax, [rdx]
0x18001e328  cmp     rax, qword ptr cs:_GUID_971d2723_1acb_42e7_855c_520a4b70a5f2.Data1
0x18001e32f  jnz     short loc_18001E353
0x18001e331  mov     rax, [rdx+8]
0x18001e335  cmp     rax, qword ptr cs:_GUID_971d2723_1acb_42e7_855c_520a4b70a5f2.Data4
0x18001e33c  jnz     short loc_18001E353
0x18001e33e  mov     rax, [rcx+208h]
0x18001e345  mov     word ptr [r8], 13h
0x18001e34b  mov     eax, [rax+193Ch]
0x18001e351  jmp     short loc_18001E311
0x18001e353  mov     rax, [rdx]
0x18001e356  cmp     rax, qword ptr cs:_GUID_1d3583c4_1583_474e_b71a_5ee463c198e4.Data1
0x18001e35d  jnz     short loc_18001E381
0x18001e35f  mov     rax, [rdx+8]
0x18001e363  cmp     rax, qword ptr cs:_GUID_1d3583c4_1583_474e_b71a_5ee463c198e4.Data4
0x18001e36a  jnz     short loc_18001E381
0x18001e36c  mov     rax, [rcx+208h]
0x18001e373  mov     word ptr [r8], 13h
0x18001e379  mov     eax, [rax+1990h]
0x18001e37f  jmp     short loc_18001E311
0x18001e381  mov     rax, [rdx]
0x18001e384  cmp     rax, qword ptr cs:_GUID_17f89cb3_c38d_4368_9ede_63b94d177f9f.Data1
0x18001e38b  jnz     short loc_18001E3B2
0x18001e38d  mov     rax, [rdx+8]
0x18001e391  cmp     rax, qword ptr cs:_GUID_17f89cb3_c38d_4368_9ede_63b94d177f9f.Data4
0x18001e398  jnz     short loc_18001E3B2
0x18001e39a  mov     rax, [rcx+208h]
0x18001e3a1  mov     word ptr [r8], 13h
0x18001e3a7  mov     eax, [rax+1994h]
0x18001e3ad  jmp     loc_18001E311
0x18001e3b2  mov     rax, [rdx]
0x18001e3b5  cmp     rax, qword ptr cs:_GUID_59488217_007a_4f7a_8e41_5c48b1eac5c6.Data1
0x18001e3bc  jnz     short loc_18001E3E3
0x18001e3be  mov     rax, [rdx+8]
0x18001e3c2  cmp     rax, qword ptr cs:_GUID_59488217_007a_4f7a_8e41_5c48b1eac5c6.Data4
0x18001e3c9  jnz     short loc_18001E3E3
0x18001e3cb  mov     rax, [rcx+208h]
0x18001e3d2  mov     word ptr [r8], 13h
0x18001e3d8  mov     eax, [rax+1998h]
0x18001e3de  jmp     loc_18001E311
0x18001e3e3  mov     rdi, [rsp+28h+arg_0]
0x18001e3e8  mov     eax, 80070057h
0x18001e3ed  add     rsp, 20h
0x18001e3f1  pop     rbx
0x18001e3f2  retn
0x18001e3f4  mov     eax, 80070057h
0x18001e3f9  add     rsp, 20h
0x18001e3fd  pop     rbx
0x18001e3fe  retn
```
