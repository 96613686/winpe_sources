# ShieldProvider::FreeWscFirewallProductList(tagWSC_FW_PRODUCT_INFO_LIST *)

- ea: `0x180011d6c`
- end: `0x180011e11`
- name: `?FreeWscFirewallProductList@ShieldProvider@@YAXPEAUtagWSC_FW_PRODUCT_INFO_LIST@@@Z`
- size: `165`
- prototype: `void __fastcall(ShieldProvider *__hidden this, struct tagWSC_FW_PRODUCT_INFO_LIST *)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800118a4`
- `0x180013630`
- `0x1800494ec`
- `0x18004a670`
- `0x18004a8dc`
- `0x18007c764`

## callees

- `0x180011d6c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180011da6`
- `ole32!CoTaskMemFree` at `0x180011dc7`
- `ole32!CoTaskMemFree` at `0x180011de4`
- `ole32!CoTaskMemFree` at `0x180011dfb`
- `ole32!CoTaskMemFree` at `0x180011da6`
- `ole32!CoTaskMemFree` at `0x180011dc7`
- `ole32!CoTaskMemFree` at `0x180011de4`
- `ole32!CoTaskMemFree` at `0x180011dfb`

## pseudocode

```c
void __fastcall ShieldProvider::FreeWscFirewallProductList(
        ShieldProvider *this,
        struct tagWSC_FW_PRODUCT_INFO_LIST *a2)
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
        v4 = *(void **)(*((_QWORD *)this + 1) + 72 * i + 8);
        if ( v4 )
        {
          CoTaskMemFree(v4);
          *(_QWORD *)(*((_QWORD *)this + 1) + 72 * i + 8) = 0;
        }
        v5 = *(void **)(*((_QWORD *)this + 1) + 72 * i + 16);
        if ( v5 )
        {
          CoTaskMemFree(v5);
          *(_QWORD *)(*((_QWORD *)this + 1) + 72 * i + 16) = 0;
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
0x180011d6c  test    rcx, rcx
0x180011d6f  jz      locret_180011E10
0x180011d75  mov     [rsp+arg_0], rbx
0x180011d7a  mov     [rsp+arg_8], rsi
0x180011d7f  push    rdi
0x180011d80  sub     rsp, 20h
0x180011d84  cmp     qword ptr [rcx+8], 0
0x180011d89  mov     rbx, rcx
0x180011d8c  jz      short loc_180011DF8
0x180011d8e  xor     edi, edi
0x180011d90  cmp     [rcx], edi
0x180011d92  jbe     short loc_180011DE0
0x180011d94  mov     rax, [rbx+8]
0x180011d98  lea     rsi, [rdi+rdi*8]
0x180011d9c  mov     rcx, [rax+rsi*8+8]; pv
0x180011da1  test    rcx, rcx
0x180011da4  jz      short loc_180011DB9
0x180011da6  call    cs:__imp_CoTaskMemFree
0x180011dac  mov     rax, [rbx+8]
0x180011db0  mov     qword ptr [rax+rsi*8+8], 0
0x180011db9  mov     rax, [rbx+8]
0x180011dbd  mov     rcx, [rax+rsi*8+10h]; pv
0x180011dc2  test    rcx, rcx
0x180011dc5  jz      short loc_180011DDA
0x180011dc7  call    cs:__imp_CoTaskMemFree
0x180011dcd  mov     rax, [rbx+8]
0x180011dd1  mov     qword ptr [rax+rsi*8+10h], 0
0x180011dda  inc     edi
0x180011ddc  cmp     edi, [rbx]
0x180011dde  jb      short loc_180011D94
0x180011de0  mov     rcx, [rbx+8]; pv
0x180011de4  call    cs:__imp_CoTaskMemFree
0x180011dea  mov     qword ptr [rbx+8], 0
0x180011df2  mov     dword ptr [rbx], 0
0x180011df8  mov     rcx, rbx; pv
0x180011dfb  call    cs:__imp_CoTaskMemFree
0x180011e01  mov     rbx, [rsp+28h+arg_0]
0x180011e06  mov     rsi, [rsp+28h+arg_8]
0x180011e0b  add     rsp, 20h
0x180011e0f  pop     rdi
0x180011e10  retn
```
