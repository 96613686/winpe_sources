# DiagHubCommon::ScopeGuard__lambda_27a9827b0e63ea89443a9643f49afd6f___::_ScopeGuard__lambda_27a9827b0e63ea89443a9643f49afd6f___

- ea: `0x180014d50`
- end: `0x180014e5d`
- name: `DiagHubCommon::ScopeGuard__lambda_27a9827b0e63ea89443a9643f49afd6f___::_ScopeGuard__lambda_27a9827b0e63ea89443a9643f49afd6f___`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011e80`
- `0x18004c46b`

## callees

- `0x180014d50`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180014e0f`
- `ole32!CoTaskMemFree` at `0x180014e0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180014dde`
- `OLEAUT32!__imp_SysFreeString` at `0x180014df4`
- `OLEAUT32!__imp_SysFreeString` at `0x180014dde`
- `OLEAUT32!__imp_SysFreeString` at `0x180014df4`

## pseudocode

```c
_QWORD *__fastcall DiagHubCommon::ScopeGuard__lambda_27a9827b0e63ea89443a9643f49afd6f___::_ScopeGuard__lambda_27a9827b0e63ea89443a9643f49afd6f___(
        __int64 a1)
{
  _QWORD *v1; // r8
  unsigned __int64 v2; // rdi
  _QWORD *result; // rax
  __int64 v5; // rbp
  unsigned int v6; // ecx
  __int64 v7; // rsi
  __int64 v8; // r14
  __int64 v9; // rcx

  v1 = *(_QWORD **)(a1 + 16);
  v2 = 0;
  result = (_QWORD *)((unsigned __int64)((unsigned __int128)((__int64)(v1[1] - *v1) * (__int128)0x2AAAAAAAAAAAAAABLL) >> 64) >> 63);
  if ( (v1[1] - *v1) / 24LL )
  {
    v5 = 0;
    do
    {
      result = *(_QWORD **)(a1 + 8);
      if ( v2 >= (__int64)(result[1] - *result) >> 3 )
        break;
      if ( **(_DWORD **)a1 )
      {
        v6 = *(_DWORD *)(*v1 + v5 + 8);
        if ( v6 )
        {
          v7 = 0;
          v8 = v6;
          do
          {
            SysFreeString(*(BSTR *)(*(_QWORD *)(**(_QWORD **)(a1 + 8) + 8 * v2) + v7 + 24));
            SysFreeString(*(BSTR *)(*(_QWORD *)(**(_QWORD **)(a1 + 8) + 8 * v2) + v7 + 16));
            v7 += 32;
            --v8;
          }
          while ( v8 );
        }
      }
      CoTaskMemFree(*(LPVOID *)(**(_QWORD **)(a1 + 8) + 8 * v2));
      v1 = *(_QWORD **)(a1 + 16);
      ++v2;
      v5 += 24;
      v9 = v1[1] - *v1;
      result = (_QWORD *)((unsigned __int64)((unsigned __int128)(v9 * (__int128)0x2AAAAAAAAAAAAAABLL) >> 64) >> 63);
    }
    while ( v2 < v9 / 24 );
  }
  return result;
}

```

## disassembly

```asm
0x180014d50  mov     [rsp+arg_0], rbx
0x180014d55  mov     [rsp+arg_8], rbp
0x180014d5a  mov     [rsp+arg_10], rsi
0x180014d5f  push    rdi
0x180014d60  push    r14
0x180014d62  push    r15
0x180014d64  sub     rsp, 20h
0x180014d68  mov     r8, [rcx+10h]
0x180014d6c  mov     r15, 2AAAAAAAAAAAAAABh
0x180014d76  mov     rax, r15
0x180014d79  xor     edi, edi
0x180014d7b  mov     rbx, rcx
0x180014d7e  mov     rdx, [r8+8]
0x180014d82  sub     rdx, [r8]
0x180014d85  imul    rdx
0x180014d88  sar     rdx, 2
0x180014d8c  mov     rax, rdx
0x180014d8f  shr     rax, 3Fh
0x180014d93  add     rdx, rax
0x180014d96  jz      loc_180014E44
0x180014d9c  xor     ebp, ebp
0x180014d9e  mov     rax, [rbx+8]
0x180014da2  mov     rcx, [rax+8]
0x180014da6  sub     rcx, [rax]
0x180014da9  sar     rcx, 3
0x180014dad  cmp     rdi, rcx
0x180014db0  jnb     loc_180014E44
0x180014db6  mov     rax, [rbx]
0x180014db9  cmp     dword ptr [rax], 0
0x180014dbc  jz      short loc_180014E04
0x180014dbe  mov     rax, [r8]
0x180014dc1  mov     ecx, [rax+rbp+8]
0x180014dc5  test    ecx, ecx
0x180014dc7  jz      short loc_180014E04
0x180014dc9  xor     esi, esi
0x180014dcb  mov     r14d, ecx
0x180014dce  mov     rax, [rbx+8]
0x180014dd2  mov     rcx, [rax]
0x180014dd5  mov     rcx, [rcx+rdi*8]
0x180014dd9  mov     rcx, [rcx+rsi+18h]; bstrString
0x180014dde  call    cs:__imp_SysFreeString
0x180014de4  mov     rax, [rbx+8]
0x180014de8  mov     rcx, [rax]
0x180014deb  mov     rcx, [rcx+rdi*8]
0x180014def  mov     rcx, [rcx+rsi+10h]; bstrString
0x180014df4  call    cs:__imp_SysFreeString
0x180014dfa  lea     rsi, [rsi+20h]
0x180014dfe  sub     r14, 1
0x180014e02  jnz     short loc_180014DCE
0x180014e04  mov     rax, [rbx+8]
0x180014e08  mov     rcx, [rax]
0x180014e0b  mov     rcx, [rcx+rdi*8]; pv
0x180014e0f  call    cs:__imp_CoTaskMemFree
0x180014e15  mov     r8, [rbx+10h]
0x180014e19  mov     rax, r15
0x180014e1c  inc     rdi
0x180014e1f  add     rbp, 18h
0x180014e23  mov     rcx, [r8+8]
0x180014e27  sub     rcx, [r8]
0x180014e2a  imul    rcx
0x180014e2d  sar     rdx, 2
0x180014e31  mov     rax, rdx
0x180014e34  shr     rax, 3Fh
0x180014e38  add     rdx, rax
0x180014e3b  cmp     rdi, rdx
0x180014e3e  jb      loc_180014D9E
0x180014e44  mov     rbx, [rsp+38h+arg_0]
0x180014e49  mov     rbp, [rsp+38h+arg_8]
0x180014e4e  mov     rsi, [rsp+38h+arg_10]
0x180014e53  add     rsp, 20h
0x180014e57  pop     r15
0x180014e59  pop     r14
0x180014e5b  pop     rdi
0x180014e5c  retn
```
