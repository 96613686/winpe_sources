# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,char *)

- ea: `0x180011994`
- end: `0x180011a8a`
- name: `?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGPEAD@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011414`

## callees

- `0x1800118bc`
- `0x180011994`
- `0x180011a90`
- `0x18001d918`
- `0x18003aedc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a5b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
        _QWORD *a1,
        const unsigned __int16 *a2,
        char *a3)
{
  unsigned __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rcx
  void *v9; // rdi
  int v10; // ebx
  unsigned __int64 v11; // rsi
  int v12; // eax
  LPVOID pv; // [rsp+30h] [rbp-58h] BYREF
  __int64 v15; // [rsp+38h] [rbp-50h]
  unsigned __int64 v16; // [rsp+40h] [rbp-48h]

  if ( *a1 && *(_WORD *)*a1 )
  {
    pv = 0;
    v6 = 32;
    v15 = 0;
    v16 = 0;
    while ( 1 )
    {
      v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
             (__int64)&pv,
             v6);
      v9 = pv;
      v10 = v7;
      if ( v7 < 0 )
        goto LABEL_8;
      v11 = v16;
      v12 = `Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat'::`2'::_lambda_1_::operator()(
              v8,
              a2,
              a3,
              (unsigned __int16 *)pv,
              v16);
      v10 = v12;
      if ( v12 != -2147024774 )
        break;
      v6 = v11 + 32;
      if ( v11 + 32 < v11 )
      {
        v10 = -2147024362;
        goto LABEL_8;
      }
    }
    if ( v12 >= 0 )
    {
      v15 = -1;
LABEL_11:
      v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(a1, &pv);
      goto LABEL_12;
    }
LABEL_8:
    if ( v9 )
    {
      CoTaskMemFree(v9);
      v9 = 0;
      pv = 0;
    }
    v15 = 0;
    v16 = 0;
    if ( v10 >= 0 )
      goto LABEL_11;
LABEL_12:
    if ( v9 )
      CoTaskMemFree(v9);
  }
  else
  {
    return (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat();
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180011994  push    rbx
0x180011996  push    rbp
0x180011997  push    rsi
0x180011998  push    rdi
0x180011999  push    r12
0x18001199b  push    r14
0x18001199d  push    r15
0x18001199f  sub     rsp, 50h
0x1800119a3  mov     rax, [rcx]
0x1800119a6  xor     r12d, r12d
0x1800119a9  mov     rbp, r8
0x1800119ac  mov     r15, rdx
0x1800119af  mov     r14, rcx
0x1800119b2  test    rax, rax
0x1800119b5  jz      loc_180011A72
0x1800119bb  cmp     [rax], r12w
0x1800119bf  jz      loc_180011A72
0x1800119c5  mov     [rsp+88h+pv], r12
0x1800119ca  lea     eax, [r12+20h]
0x1800119cf  mov     [rsp+88h+var_50], r12
0x1800119d4  mov     [rsp+88h+var_48], r12
0x1800119d9  mov     rdx, rax
0x1800119dc  lea     rcx, [rsp+88h+pv]
0x1800119e1  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800119e6  mov     rdi, [rsp+88h+pv]
0x1800119eb  mov     ebx, eax
0x1800119ed  test    eax, eax
0x1800119ef  js      short loc_180011A20
0x1800119f1  mov     rsi, [rsp+88h+var_48]
0x1800119f6  mov     r9, rdi
0x1800119f9  mov     r8, rbp
0x1800119fc  mov     [rsp+88h+var_68], rsi
0x180011a01  mov     rdx, r15
0x180011a04  call    ??R_lambda_1_@?1??InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGPEAD@Z@QEBAJ01PEAG_K@Z; `Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,char *)'::`2'::_lambda_1_::operator()(ushort const *,char *,ushort *,unsigned __int64)
0x180011a09  mov     ebx, eax
0x180011a0b  cmp     eax, 8007007Ah
0x180011a10  jnz     short loc_180011A63
0x180011a12  lea     rax, [rsi+20h]
0x180011a16  cmp     rax, rsi
0x180011a19  jnb     short loc_1800119D9
0x180011a1b  mov     ebx, 80070216h
0x180011a20  test    rdi, rdi
0x180011a23  jz      short loc_180011A36
0x180011a25  mov     rcx, rdi; pv
0x180011a28  call    cs:__imp_CoTaskMemFree
0x180011a2e  mov     rdi, r12
0x180011a31  mov     [rsp+88h+pv], r12
0x180011a36  mov     [rsp+88h+var_50], r12
0x180011a3b  mov     [rsp+88h+var_48], r12
0x180011a40  test    ebx, ebx
0x180011a42  js      short loc_180011A53
0x180011a44  lea     rdx, [rsp+88h+pv]
0x180011a49  mov     rcx, r14
0x180011a4c  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x180011a51  mov     ebx, eax
0x180011a53  test    rdi, rdi
0x180011a56  jz      short loc_180011A79
0x180011a58  mov     rcx, rdi; pv
0x180011a5b  call    cs:__imp_CoTaskMemFree
0x180011a61  jmp     short loc_180011A79
0x180011a63  test    eax, eax
0x180011a65  js      short loc_180011A20
0x180011a67  mov     [rsp+88h+var_50], 0FFFFFFFFFFFFFFFFh
0x180011a70  jmp     short loc_180011A44
0x180011a72  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGPEAD@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,char *)
0x180011a77  mov     ebx, eax
0x180011a79  mov     eax, ebx
0x180011a7b  add     rsp, 50h
0x180011a7f  pop     r15
0x180011a81  pop     r14
0x180011a83  pop     r12
0x180011a85  pop     rdi
0x180011a86  pop     rsi
0x180011a87  pop     rbp
0x180011a88  pop     rbx
0x180011a89  retn
```
