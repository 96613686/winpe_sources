# EnumDisks

- ea: `0x18005b7b4`
- end: `0x18005b9c8`
- name: `EnumDisks`
- size: `532`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005b9d0`

## callees

- `0x18005b7b4`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18005b8d8`
- `KERNEL32!CompareStringW` at `0x18005b8d8`
- `ole32!CoTaskMemFree` at `0x18005b8f5`
- `ole32!CoTaskMemFree` at `0x18005b90c`
- `ole32!CoTaskMemFree` at `0x18005b923`
- `ole32!CoTaskMemFree` at `0x18005b93a`
- `ole32!CoTaskMemFree` at `0x18005b951`
- `ole32!CoTaskMemFree` at `0x18005b8f5`
- `ole32!CoTaskMemFree` at `0x18005b90c`
- `ole32!CoTaskMemFree` at `0x18005b923`
- `ole32!CoTaskMemFree` at `0x18005b93a`
- `ole32!CoTaskMemFree` at `0x18005b951`

## pseudocode

```c
__int64 __fastcall EnumDisks(__int64 *a1, const WCHAR *a2, _QWORD *a3)
{
  int v6; // ebx
  int v7; // edi
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // r14
  WCHAR *v11; // rcx
  int v12; // eax
  int v14; // [rsp+30h] [rbp-79h] BYREF
  __int64 v15; // [rsp+38h] [rbp-71h] BYREF
  int v16; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v17[84]; // [rsp+44h] [rbp-65h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-11h]
  PCNZWCH lpString2; // [rsp+A0h] [rbp-9h]
  LPVOID v20; // [rsp+A8h] [rbp-1h]
  LPVOID v21; // [rsp+B0h] [rbp+7h]
  LPVOID v22; // [rsp+B8h] [rbp+Fh]

  v14 = 0;
  if ( !a1 || !a2 || !a3 )
    return 2147942487LL;
  v6 = 0;
  v7 = 0;
  while ( !v7 )
  {
    v8 = *a1;
    v15 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *, int *))(v8 + 24))(a1, 1, &v15, &v14);
    v6 = v9;
    if ( v9 == 1 )
    {
      v7 = 1;
    }
    else if ( v9 < 0 )
    {
      return (unsigned int)v6;
    }
    if ( v15 )
    {
      v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v15)(v15, &IID_IVdsDisk, a3);
      if ( v6 >= 0 )
      {
        v10 = *a3;
        if ( *a3 )
        {
          v16 = 0;
          memset_0(v17, 0, 0x7Cu);
          v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 24LL))(v10, &v16);
          if ( v6 >= 0 )
          {
            v11 = (WCHAR *)lpString2;
            if ( lpString2 )
            {
              v12 = CompareStringW(0x409u, 1u, a2, -1, lpString2, -1);
              v11 = (WCHAR *)lpString2;
              if ( v12 == 2 )
                v7 = 1;
            }
            if ( pv )
            {
              CoTaskMemFree(pv);
              v11 = (WCHAR *)lpString2;
              pv = 0;
            }
            if ( v11 )
            {
              CoTaskMemFree(v11);
              lpString2 = 0;
            }
            if ( v20 )
            {
              CoTaskMemFree(v20);
              v20 = 0;
            }
            if ( v21 )
            {
              CoTaskMemFree(v21);
              v21 = 0;
            }
            if ( v22 )
            {
              CoTaskMemFree(v22);
              v22 = 0;
            }
          }
          if ( !v7 && *a3 )
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
            *a3 = 0;
          }
        }
      }
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( v6 < 0 )
        break;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005b7b4  push    rbp
0x18005b7b6  push    rbx
0x18005b7b7  push    rsi
0x18005b7b8  push    rdi
0x18005b7b9  push    r12
0x18005b7bb  push    r14
0x18005b7bd  push    r15
0x18005b7bf  lea     rbp, [rsp-27h]
0x18005b7c4  sub     rsp, 0D0h
0x18005b7cb  mov     rax, cs:__security_cookie
0x18005b7d2  xor     rax, rsp
0x18005b7d5  mov     [rbp+57h+var_40], rax
0x18005b7d9  mov     [rbp+57h+var_D0], 0
0x18005b7e0  mov     rsi, r8
0x18005b7e3  mov     r12, rdx
0x18005b7e6  mov     r15, rcx
0x18005b7e9  test    rcx, rcx
0x18005b7ec  jz      loc_18005B9A5
0x18005b7f2  test    rdx, rdx
0x18005b7f5  jz      loc_18005B9A5
0x18005b7fb  test    r8, r8
0x18005b7fe  jz      loc_18005B9A5
0x18005b804  xor     ebx, ebx
0x18005b806  xor     edi, edi
0x18005b808  lea     r14d, [rbx+1]
0x18005b80c  test    edi, edi
0x18005b80e  jnz     loc_18005B9A1
0x18005b814  mov     rax, [r15]
0x18005b817  lea     r9, [rbp+57h+var_D0]
0x18005b81b  lea     r8, [rbp+57h+var_C8]
0x18005b81f  mov     [rbp+57h+var_C8], 0
0x18005b827  mov     edx, r14d
0x18005b82a  mov     rcx, r15
0x18005b82d  mov     rax, [rax+18h]
0x18005b831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b836  mov     ebx, eax
0x18005b838  cmp     eax, r14d
0x18005b83b  jnz     short loc_18005B842
0x18005b83d  mov     edi, r14d
0x18005b840  jmp     short loc_18005B84A
0x18005b842  test    eax, eax
0x18005b844  js      loc_18005B9A1
0x18005b84a  mov     rcx, [rbp+57h+var_C8]
0x18005b84e  test    rcx, rcx
0x18005b851  jz      short loc_18005B80C
0x18005b853  mov     rax, [rcx]
0x18005b856  lea     rdx, IID_IVdsDisk
0x18005b85d  mov     r8, rsi
0x18005b860  mov     rax, [rax]
0x18005b863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b868  mov     ebx, eax
0x18005b86a  test    eax, eax
0x18005b86c  js      loc_18005B984
0x18005b872  mov     r14, [rsi]
0x18005b875  test    r14, r14
0x18005b878  jz      loc_18005B97E
0x18005b87e  xor     edx, edx; Val
0x18005b880  mov     [rbp+57h+var_C0], 0
0x18005b887  lea     rcx, [rbp+57h+var_BC]; void *
0x18005b88b  lea     r8d, [rdx+7Ch]; Size
0x18005b88f  call    memset_0
0x18005b894  mov     rax, [r14]
0x18005b897  lea     rdx, [rbp+57h+var_C0]
0x18005b89b  mov     rcx, r14
0x18005b89e  mov     rax, [rax+18h]
0x18005b8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b8a7  mov     ebx, eax
0x18005b8a9  test    eax, eax
0x18005b8ab  js      loc_18005B95F
0x18005b8b1  mov     rcx, [rbp+57h+var_60]
0x18005b8b5  test    rcx, rcx
0x18005b8b8  jz      short loc_18005B8E9
0x18005b8ba  or      eax, 0FFFFFFFFh
0x18005b8bd  mov     r8, r12; lpString1
0x18005b8c0  mov     [rsp+100h+cchCount2], eax; cchCount2
0x18005b8c4  mov     r9d, eax; cchCount1
0x18005b8c7  mov     [rsp+100h+lpString2], rcx; lpString2
0x18005b8cc  mov     ecx, 409h; Locale
0x18005b8d1  lea     r14d, [rax+2]
0x18005b8d5  mov     edx, r14d; dwCmpFlags
0x18005b8d8  call    cs:__imp_CompareStringW
0x18005b8de  mov     rcx, [rbp+57h+var_60]
0x18005b8e2  cmp     eax, 2
0x18005b8e5  cmovz   edi, r14d
0x18005b8e9  mov     rax, [rbp+57h+pv]
0x18005b8ed  test    rax, rax
0x18005b8f0  jz      short loc_18005B907
0x18005b8f2  mov     rcx, rax; pv
0x18005b8f5  call    cs:__imp_CoTaskMemFree
0x18005b8fb  mov     rcx, [rbp+57h+var_60]; pv
0x18005b8ff  mov     [rbp+57h+pv], 0
0x18005b907  test    rcx, rcx
0x18005b90a  jz      short loc_18005B91A
0x18005b90c  call    cs:__imp_CoTaskMemFree
0x18005b912  mov     [rbp+57h+var_60], 0
0x18005b91a  mov     rcx, [rbp+57h+var_58]; pv
0x18005b91e  test    rcx, rcx
0x18005b921  jz      short loc_18005B931
0x18005b923  call    cs:__imp_CoTaskMemFree
0x18005b929  mov     [rbp+57h+var_58], 0
0x18005b931  mov     rcx, [rbp+57h+var_50]; pv
0x18005b935  test    rcx, rcx
0x18005b938  jz      short loc_18005B948
0x18005b93a  call    cs:__imp_CoTaskMemFree
0x18005b940  mov     [rbp+57h+var_50], 0
0x18005b948  mov     rcx, [rbp+57h+var_48]; pv
0x18005b94c  test    rcx, rcx
0x18005b94f  jz      short loc_18005B95F
0x18005b951  call    cs:__imp_CoTaskMemFree
0x18005b957  mov     [rbp+57h+var_48], 0
0x18005b95f  test    edi, edi
0x18005b961  jnz     short loc_18005B97E
0x18005b963  mov     rcx, [rsi]
0x18005b966  test    rcx, rcx
0x18005b969  jz      short loc_18005B97E
0x18005b96b  mov     rax, [rcx]
0x18005b96e  mov     rax, [rax+10h]
0x18005b972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b977  mov     qword ptr [rsi], 0
0x18005b97e  mov     r14d, 1
0x18005b984  mov     rcx, [rbp+57h+var_C8]
0x18005b988  test    rcx, rcx
0x18005b98b  jz      short loc_18005B999
0x18005b98d  mov     rax, [rcx]
0x18005b990  mov     rax, [rax+10h]
0x18005b994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b999  test    ebx, ebx
0x18005b99b  jns     loc_18005B80C
0x18005b9a1  mov     eax, ebx
0x18005b9a3  jmp     short loc_18005B9AA
0x18005b9a5  mov     eax, 80070057h
0x18005b9aa  mov     rcx, [rbp+57h+var_40]
0x18005b9ae  xor     rcx, rsp; StackCookie
0x18005b9b1  call    __security_check_cookie
0x18005b9b6  add     rsp, 0D0h
0x18005b9bd  pop     r15
0x18005b9bf  pop     r14
0x18005b9c1  pop     r12
0x18005b9c3  pop     rdi
0x18005b9c4  pop     rsi
0x18005b9c5  pop     rbx
0x18005b9c6  pop     rbp
0x18005b9c7  retn
```
