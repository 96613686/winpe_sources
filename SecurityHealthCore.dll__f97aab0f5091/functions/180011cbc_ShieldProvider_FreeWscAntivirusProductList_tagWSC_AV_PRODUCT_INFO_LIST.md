# ShieldProvider::FreeWscAntivirusProductList(tagWSC_AV_PRODUCT_INFO_LIST *)

- ea: `0x180011cbc`
- end: `0x180011d64`
- name: `?FreeWscAntivirusProductList@ShieldProvider@@YAXPEAUtagWSC_AV_PRODUCT_INFO_LIST@@@Z`
- size: `168`
- prototype: `void __fastcall(ShieldProvider *__hidden this, struct tagWSC_AV_PRODUCT_INFO_LIST *)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180011888`
- `0x180013630`
- `0x180042b40`
- `0x180042cd0`
- `0x180043120`
- `0x18007c500`

## callees

- `0x180011cbc`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180011cf9`
- `ole32!CoTaskMemFree` at `0x180011d1a`
- `ole32!CoTaskMemFree` at `0x180011d37`
- `ole32!CoTaskMemFree` at `0x180011d4e`
- `ole32!CoTaskMemFree` at `0x180011cf9`
- `ole32!CoTaskMemFree` at `0x180011d1a`
- `ole32!CoTaskMemFree` at `0x180011d37`
- `ole32!CoTaskMemFree` at `0x180011d4e`

## pseudocode

```c
void __fastcall ShieldProvider::FreeWscAntivirusProductList(
        ShieldProvider *this,
        struct tagWSC_AV_PRODUCT_INFO_LIST *a2)
{
  __int64 i; // rdi
  void *v4; // rcx
  void *v5; // rcx

  if ( this )
  {
    if ( *((_QWORD *)this + 1) )
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)this; i = (unsigned int)(i + 1) )
      {
        v4 = *(void **)(*((_QWORD *)this + 1) + 80 * i + 8);
        if ( v4 )
        {
          CoTaskMemFree(v4);
          *(_QWORD *)(*((_QWORD *)this + 1) + 80 * i + 8) = 0;
        }
        v5 = *(void **)(*((_QWORD *)this + 1) + 80 * i + 16);
        if ( v5 )
        {
          CoTaskMemFree(v5);
          *(_QWORD *)(*((_QWORD *)this + 1) + 80 * i + 16) = 0;
        }
      }
      CoTaskMemFree(*((LPVOID *)this + 1));
      *((_QWORD *)this + 1) = 0;
      *(_DWORD *)this = 0;
    }
    CoTaskMemFree(this);
  }
}

```

## disassembly

```asm
0x180011cbc  test    rcx, rcx
0x180011cbf  jz      locret_180011D63
0x180011cc5  mov     [rsp+arg_0], rbx
0x180011cca  mov     [rsp+arg_8], rsi
0x180011ccf  push    rdi
0x180011cd0  sub     rsp, 20h
0x180011cd4  cmp     qword ptr [rcx+8], 0
0x180011cd9  mov     rbx, rcx
0x180011cdc  jz      short loc_180011D4B
0x180011cde  xor     edi, edi
0x180011ce0  cmp     [rcx], edi
0x180011ce2  jbe     short loc_180011D33
0x180011ce4  mov     rax, [rbx+8]
0x180011ce8  lea     rsi, [rdi+rdi*4]
0x180011cec  add     rsi, rsi
0x180011cef  mov     rcx, [rax+rsi*8+8]; pv
0x180011cf4  test    rcx, rcx
0x180011cf7  jz      short loc_180011D0C
0x180011cf9  call    cs:__imp_CoTaskMemFree
0x180011cff  mov     rax, [rbx+8]
0x180011d03  mov     qword ptr [rax+rsi*8+8], 0
0x180011d0c  mov     rax, [rbx+8]
0x180011d10  mov     rcx, [rax+rsi*8+10h]; pv
0x180011d15  test    rcx, rcx
0x180011d18  jz      short loc_180011D2D
0x180011d1a  call    cs:__imp_CoTaskMemFree
0x180011d20  mov     rax, [rbx+8]
0x180011d24  mov     qword ptr [rax+rsi*8+10h], 0
0x180011d2d  inc     edi
0x180011d2f  cmp     edi, [rbx]
0x180011d31  jb      short loc_180011CE4
0x180011d33  mov     rcx, [rbx+8]; pv
0x180011d37  call    cs:__imp_CoTaskMemFree
0x180011d3d  mov     qword ptr [rbx+8], 0
0x180011d45  mov     dword ptr [rbx], 0
0x180011d4b  mov     rcx, rbx; pv
0x180011d4e  call    cs:__imp_CoTaskMemFree
0x180011d54  mov     rbx, [rsp+28h+arg_0]
0x180011d59  mov     rsi, [rsp+28h+arg_8]
0x180011d5e  add     rsp, 20h
0x180011d62  pop     rdi
0x180011d63  retn
```
