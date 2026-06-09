# _anonymous_namespace_::StorageValue_256_::TryReadChild

- ea: `0x180026aa4`
- end: `0x180026c94`
- name: `_anonymous_namespace_::StorageValue_256_::TryReadChild`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180026a90`

## callees

- `0x1800032a0`
- `0x1800032c4`
- `0x180026734`
- `0x180026aa4`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall anonymous_namespace_::StorageValue_256_::TryReadChild(__int64 a1, _QWORD *a2)
{
  const WCHAR *v3; // r8
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  __int64 v6; // rdx
  char v7; // di
  char v8; // di
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  void (__fastcall ***v11)(_QWORD, __int64); // rcx
  void (__fastcall ***v12)(_QWORD, _QWORD); // rcx
  _QWORD *v14; // [rsp+20h] [rbp-68h]
  _QWORD *v15; // [rsp+28h] [rbp-60h]
  _QWORD v16[6]; // [rsp+38h] [rbp-50h] BYREF
  _QWORD *v17; // [rsp+68h] [rbp-20h]

  v15 = a2;
  v3 = (const WCHAR *)(a1 - 56);
  if ( *(_QWORD *)(a1 - 56 + 24) > 7u )
    v3 = *(const WCHAR **)v3;
  ReadRegistryT<256>::TryOpen(v16, *(HKEY *)(a1 - 24), v3);
  v4 = v17;
  if ( v17 )
  {
    v5 = operator new(0x28u);
    v5[2] = &ReadRegistryT<256>::`vbtable';
    v5[4] = &IConstHierarchicalStorage::`vftable';
    *v5 = 0;
    v5[1] = 0;
    *v5 = *v4;
    v5[1] = v4[1];
    *v4 = 0;
    v4[1] = 0;
    *(_QWORD *)((char *)v5 + *(int *)(v5[2] + 4LL) + 16) = &ReadRegistryT<256>::`vftable';
    v6 = *(int *)(v5[2] + 4LL);
    *(_DWORD *)((char *)v5 + v6 + 12) = v6 - 16;
    v15 = 0;
    v7 = 49;
    v4 = v14;
    if ( v5 )
    {
      *a2 = (char *)v5 + *(int *)(v5[2] + 4LL) + 16;
      v8 = 57;
      goto LABEL_10;
    }
  }
  else
  {
    v7 = 6;
    v14 = 0;
  }
  *a2 = 0;
  v8 = v7 | 8;
  if ( (v8 & 4) != 0 )
  {
    v8 &= ~4u;
    if ( v14 )
    {
      v9 = (void (__fastcall ***)(_QWORD, __int64))((char *)v14 + *(int *)(v14[2] + 4LL) + 16);
      (**v9)(v9, 1);
    }
  }
LABEL_10:
  if ( (v8 & 2) != 0 )
  {
    v8 &= ~2u;
    if ( v4 )
    {
      v10 = (void (__fastcall ***)(_QWORD, __int64))((char *)v4 + *(int *)(v4[2] + 4LL) + 16);
      (**v10)(v10, 1);
    }
  }
  if ( (v8 & 1) != 0 && v15 )
  {
    v11 = (void (__fastcall ***)(_QWORD, __int64))((char *)v15 + *(int *)(v15[2] + 4LL) + 16);
    (**v11)(v11, 1);
  }
  if ( v17 )
  {
    v12 = (void (__fastcall ***)(_QWORD, _QWORD))((char *)v17 + *(int *)(v17[2] + 4LL) + 16);
    (**v12)(v12, 0);
  }
  return a2;
}

```

## disassembly

```asm
0x180026aa4  mov     [rsp+arg_10], rbx
0x180026aa9  mov     [rsp+arg_18], rsi
0x180026aae  push    rdi
0x180026aaf  sub     rsp, 80h
0x180026ab6  mov     rax, cs:__security_cookie
0x180026abd  xor     rax, rsp
0x180026ac0  mov     [rsp+88h+var_18], rax
0x180026ac5  mov     rsi, rdx
0x180026ac8  mov     [rsp+88h+var_60], rdx
0x180026acd  mov     [rsp+88h+var_58], 0
0x180026ad5  lea     r8, [rcx-38h]
0x180026ad9  cmp     qword ptr [r8+18h], 7
0x180026ade  jbe     short loc_180026AE3
0x180026ae0  mov     r8, [r8]
0x180026ae3  mov     rdx, [rcx-18h]
0x180026ae7  lea     rcx, [rsp+88h+var_50]
0x180026aec  call    ?TryOpen@?$ReadRegistryT@$0BAA@@@SA?AV?$Optional@V?$ReadRegistryT@$0BAA@@@@@PEAUHKEY__@@PEBG@Z; ReadRegistryT<256>::TryOpen(HKEY__ *,ushort const *)
0x180026af1  nop
0x180026af2  mov     rbx, [rsp+88h+var_20]
0x180026af7  test    rbx, rbx
0x180026afa  jz      loc_180026BA5
0x180026b00  mov     ecx, 28h ; '('; Size
0x180026b05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026b0a  lea     rcx, ??_8?$ReadRegistryT@$0BAA@@@7B@; const ReadRegistryT<256>::`vbtable'
0x180026b11  mov     [rax+10h], rcx
0x180026b15  lea     rcx, ??_7IConstHierarchicalStorage@@6B@; const IConstHierarchicalStorage::`vftable'
0x180026b1c  mov     [rax+20h], rcx
0x180026b20  mov     qword ptr [rax], 0
0x180026b27  mov     qword ptr [rax+8], 0
0x180026b2f  mov     rcx, [rbx]
0x180026b32  mov     [rax], rcx
0x180026b35  mov     rcx, [rbx+8]
0x180026b39  mov     [rax+8], rcx
0x180026b3d  mov     qword ptr [rbx], 0
0x180026b44  mov     qword ptr [rbx+8], 0
0x180026b4c  mov     rcx, [rax+10h]
0x180026b50  movsxd  rdx, dword ptr [rcx+4]
0x180026b54  lea     rcx, ??_7?$ReadRegistryT@$0BAA@@@6B@; const ReadRegistryT<256>::`vftable'
0x180026b5b  mov     [rdx+rax+10h], rcx
0x180026b60  mov     rcx, [rax+10h]
0x180026b64  movsxd  rdx, dword ptr [rcx+4]
0x180026b68  lea     r8d, [rdx-10h]
0x180026b6c  mov     [rdx+rax+0Ch], r8d
0x180026b71  lea     rcx, [rsp+88h+var_60]
0x180026b76  mov     qword ptr [rcx], 0
0x180026b7d  mov     edi, 31h ; '1'
0x180026b82  mov     rbx, [rsp+88h+var_68]
0x180026b87  test    rax, rax
0x180026b8a  jz      short loc_180026BB2
0x180026b8c  mov     rcx, [rax+10h]
0x180026b90  movsxd  rcx, dword ptr [rcx+4]
0x180026b94  add     rcx, 10h
0x180026b98  add     rcx, rax
0x180026b9b  mov     [rsi], rcx
0x180026b9e  mov     edi, 39h ; '9'
0x180026ba3  jmp     short loc_180026BEC
0x180026ba5  lea     rax, [rsp+88h+var_68]
0x180026baa  mov     edi, 6
0x180026baf  mov     [rax], rbx
0x180026bb2  xor     eax, eax
0x180026bb4  mov     [rsi], rax
0x180026bb7  or      edi, 8
0x180026bba  test    dil, 4
0x180026bbe  jz      short loc_180026BEC
0x180026bc0  and     edi, 0FFFFFFFBh
0x180026bc3  mov     rdx, [rsp+88h+var_68]
0x180026bc8  test    rdx, rdx
0x180026bcb  jz      short loc_180026BEC
0x180026bcd  mov     rax, [rdx+10h]
0x180026bd1  movsxd  rcx, dword ptr [rax+4]
0x180026bd5  add     rcx, 10h
0x180026bd9  add     rcx, rdx
0x180026bdc  mov     rax, [rcx]
0x180026bdf  mov     edx, 1
0x180026be4  mov     rax, [rax]
0x180026be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bec  test    dil, 2
0x180026bf0  jz      short loc_180026C19
0x180026bf2  and     edi, 0FFFFFFFDh
0x180026bf5  test    rbx, rbx
0x180026bf8  jz      short loc_180026C19
0x180026bfa  mov     rax, [rbx+10h]
0x180026bfe  movsxd  rcx, dword ptr [rax+4]
0x180026c02  add     rcx, 10h
0x180026c06  add     rcx, rbx
0x180026c09  mov     rax, [rcx]
0x180026c0c  mov     edx, 1
0x180026c11  mov     rax, [rax]
0x180026c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c19  test    dil, 1
0x180026c1d  jz      short loc_180026C49
0x180026c1f  mov     r8, [rsp+88h+var_60]
0x180026c24  test    r8, r8
0x180026c27  jz      short loc_180026C49
0x180026c29  mov     rax, [r8+10h]
0x180026c2d  movsxd  rcx, dword ptr [rax+4]
0x180026c31  add     r8, 10h
0x180026c35  add     rcx, r8
0x180026c38  mov     rax, [rcx]
0x180026c3b  mov     edx, 1
0x180026c40  mov     rax, [rax]
0x180026c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c48  nop
0x180026c49  mov     rax, [rsp+88h+var_20]
0x180026c4e  test    rax, rax
0x180026c51  jz      short loc_180026C6F
0x180026c53  mov     rcx, [rax+10h]
0x180026c57  movsxd  rcx, dword ptr [rcx+4]
0x180026c5b  add     rax, 10h
0x180026c5f  add     rcx, rax
0x180026c62  mov     rdx, [rcx]
0x180026c65  mov     rax, [rdx]
0x180026c68  xor     edx, edx
0x180026c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c6f  mov     rax, rsi
0x180026c72  mov     rcx, [rsp+88h+var_18]
0x180026c77  xor     rcx, rsp; StackCookie
0x180026c7a  call    __security_check_cookie
0x180026c7f  lea     r11, [rsp+88h+var_8]
0x180026c87  mov     rbx, [r11+20h]
0x180026c8b  mov     rsi, [r11+28h]
0x180026c8f  mov     rsp, r11
0x180026c92  pop     rdi
0x180026c93  retn
```
