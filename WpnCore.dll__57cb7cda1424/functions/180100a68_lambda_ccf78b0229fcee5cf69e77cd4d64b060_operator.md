# _lambda_ccf78b0229fcee5cf69e77cd4d64b060_::operator()

- ea: `0x180100a68`
- end: `0x180100b01`
- name: `_lambda_ccf78b0229fcee5cf69e77cd4d64b060_::operator()`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801005d4`

## callees

- `0x180100a68`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100a7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100aa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100ac4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100ae7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100a7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100aa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100ac4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100ae7`

## pseudocode

```c
void ***__fastcall lambda_ccf78b0229fcee5cf69e77cd4d64b060_::operator()(void ****a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void ***result; // rax
  void *v6; // rcx

  v2 = ***a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    ***a1 = 0;
  }
  v3 = (**a1)[1];
  if ( v3 )
  {
    CoTaskMemFree(v3);
    (**a1)[1] = 0;
  }
  v4 = (**a1)[6];
  if ( v4 )
  {
    CoTaskMemFree(v4);
    (**a1)[6] = 0;
  }
  result = *a1;
  v6 = (**a1)[7];
  if ( v6 )
  {
    CoTaskMemFree(v6);
    result = *a1;
    (**a1)[7] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180100a68  push    rbx
0x180100a6a  sub     rsp, 20h
0x180100a6e  mov     rax, [rcx]
0x180100a71  mov     rbx, rcx
0x180100a74  mov     rdx, [rax]
0x180100a77  mov     rcx, [rdx]; pv
0x180100a7a  test    rcx, rcx
0x180100a7d  jz      short loc_180100A92
0x180100a7f  call    cs:__imp_CoTaskMemFree
0x180100a85  mov     rax, [rbx]
0x180100a88  mov     rdx, [rax]
0x180100a8b  mov     qword ptr [rdx], 0
0x180100a92  mov     rax, [rbx]
0x180100a95  mov     rcx, [rax]
0x180100a98  mov     rcx, [rcx+8]; pv
0x180100a9c  test    rcx, rcx
0x180100a9f  jz      short loc_180100AB5
0x180100aa1  call    cs:__imp_CoTaskMemFree
0x180100aa7  mov     rax, [rbx]
0x180100aaa  mov     rcx, [rax]
0x180100aad  mov     qword ptr [rcx+8], 0
0x180100ab5  mov     rax, [rbx]
0x180100ab8  mov     rcx, [rax]
0x180100abb  mov     rcx, [rcx+30h]; pv
0x180100abf  test    rcx, rcx
0x180100ac2  jz      short loc_180100AD8
0x180100ac4  call    cs:__imp_CoTaskMemFree
0x180100aca  mov     rax, [rbx]
0x180100acd  mov     rcx, [rax]
0x180100ad0  mov     qword ptr [rcx+30h], 0
0x180100ad8  mov     rax, [rbx]
0x180100adb  mov     rcx, [rax]
0x180100ade  mov     rcx, [rcx+38h]; pv
0x180100ae2  test    rcx, rcx
0x180100ae5  jz      short loc_180100AFB
0x180100ae7  call    cs:__imp_CoTaskMemFree
0x180100aed  mov     rax, [rbx]
0x180100af0  mov     rcx, [rax]
0x180100af3  mov     qword ptr [rcx+38h], 0
0x180100afb  add     rsp, 20h
0x180100aff  pop     rbx
0x180100b00  retn
```
