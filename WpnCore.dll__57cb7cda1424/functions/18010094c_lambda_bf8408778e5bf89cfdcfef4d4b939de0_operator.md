# _lambda_bf8408778e5bf89cfdcfef4d4b939de0_::operator()

- ea: `0x18010094c`
- end: `0x180100a5f`
- name: `_lambda_bf8408778e5bf89cfdcfef4d4b939de0_::operator()`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801005b4`

## callees

- `0x18010094c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100982`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801009a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801009ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801009ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100a3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100982`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801009a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801009ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801009ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100a3f`

## pseudocode

```c
void **__fastcall lambda_bf8408778e5bf89cfdcfef4d4b939de0_::operator()(void ***a1)
{
  unsigned int i; // esi
  __int64 v3; // rdi
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void **result; // rax
  void *v10; // rcx

  for ( i = 0; i < *((_DWORD *)a1 + 2); ++i )
  {
    v3 = 176LL * i;
    v4 = *(void **)((char *)**a1 + v3 + 40);
    if ( v4 )
    {
      CoTaskMemFree(v4);
      *(_QWORD *)((char *)**a1 + v3 + 40) = 0;
    }
    v5 = *(void **)((char *)**a1 + v3);
    if ( v5 )
    {
      CoTaskMemFree(v5);
      *(_QWORD *)((char *)**a1 + v3) = 0;
    }
    v6 = *(void **)((char *)**a1 + v3 + 8);
    if ( v6 )
    {
      CoTaskMemFree(v6);
      *(_QWORD *)((char *)**a1 + v3 + 8) = 0;
    }
    v7 = *(void **)((char *)**a1 + v3 + 80);
    if ( v7 )
    {
      CoTaskMemFree(v7);
      *(_QWORD *)((char *)**a1 + v3 + 80) = 0;
    }
    v8 = *(void **)((char *)**a1 + v3 + 88);
    if ( v8 )
    {
      CoTaskMemFree(v8);
      *(_QWORD *)((char *)**a1 + v3 + 88) = 0;
    }
  }
  result = *a1;
  v10 = **a1;
  if ( v10 )
  {
    CoTaskMemFree(v10);
    result = *a1;
    **a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18010094c  mov     [rsp+arg_0], rbx
0x180100951  mov     [rsp+arg_8], rsi
0x180100956  push    rdi
0x180100957  sub     rsp, 20h
0x18010095b  xor     esi, esi
0x18010095d  mov     rbx, rcx
0x180100960  cmp     [rcx+8], esi
0x180100963  jbe     loc_180100A34
0x180100969  mov     eax, esi
0x18010096b  imul    rdi, rax, 0B0h
0x180100972  mov     rax, [rbx]
0x180100975  mov     rcx, [rax]
0x180100978  mov     rcx, [rcx+rdi+28h]; pv
0x18010097d  test    rcx, rcx
0x180100980  jz      short loc_180100997
0x180100982  call    cs:__imp_CoTaskMemFree
0x180100988  mov     rax, [rbx]
0x18010098b  mov     rcx, [rax]
0x18010098e  mov     qword ptr [rcx+rdi+28h], 0
0x180100997  mov     rax, [rbx]
0x18010099a  mov     rcx, [rax]
0x18010099d  mov     rcx, [rdi+rcx]; pv
0x1801009a1  test    rcx, rcx
0x1801009a4  jz      short loc_1801009BA
0x1801009a6  call    cs:__imp_CoTaskMemFree
0x1801009ac  mov     rax, [rbx]
0x1801009af  mov     rcx, [rax]
0x1801009b2  mov     qword ptr [rdi+rcx], 0
0x1801009ba  mov     rax, [rbx]
0x1801009bd  mov     rcx, [rax]
0x1801009c0  mov     rcx, [rcx+rdi+8]; pv
0x1801009c5  test    rcx, rcx
0x1801009c8  jz      short loc_1801009DF
0x1801009ca  call    cs:__imp_CoTaskMemFree
0x1801009d0  mov     rax, [rbx]
0x1801009d3  mov     rcx, [rax]
0x1801009d6  mov     qword ptr [rcx+rdi+8], 0
0x1801009df  mov     rax, [rbx]
0x1801009e2  mov     rcx, [rax]
0x1801009e5  mov     rcx, [rcx+rdi+50h]; pv
0x1801009ea  test    rcx, rcx
0x1801009ed  jz      short loc_180100A04
0x1801009ef  call    cs:__imp_CoTaskMemFree
0x1801009f5  mov     rax, [rbx]
0x1801009f8  mov     rcx, [rax]
0x1801009fb  mov     qword ptr [rcx+rdi+50h], 0
0x180100a04  mov     rax, [rbx]
0x180100a07  mov     rcx, [rax]
0x180100a0a  mov     rcx, [rcx+rdi+58h]; pv
0x180100a0f  test    rcx, rcx
0x180100a12  jz      short loc_180100A29
0x180100a14  call    cs:__imp_CoTaskMemFree
0x180100a1a  mov     rax, [rbx]
0x180100a1d  mov     rcx, [rax]
0x180100a20  mov     qword ptr [rcx+rdi+58h], 0
0x180100a29  inc     esi
0x180100a2b  cmp     esi, [rbx+8]
0x180100a2e  jb      loc_180100969
0x180100a34  mov     rax, [rbx]
0x180100a37  mov     rcx, [rax]; pv
0x180100a3a  test    rcx, rcx
0x180100a3d  jz      short loc_180100A4F
0x180100a3f  call    cs:__imp_CoTaskMemFree
0x180100a45  mov     rax, [rbx]
0x180100a48  mov     qword ptr [rax], 0
0x180100a4f  mov     rbx, [rsp+28h+arg_0]
0x180100a54  mov     rsi, [rsp+28h+arg_8]
0x180100a59  add     rsp, 20h
0x180100a5d  pop     rdi
0x180100a5e  retn
```
