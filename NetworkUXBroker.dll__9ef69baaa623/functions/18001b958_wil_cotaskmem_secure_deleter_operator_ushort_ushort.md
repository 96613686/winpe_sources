# wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)

- ea: `0x18001b958`
- end: `0x18001b9d5`
- name: `??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z`
- size: `125`
- prototype: `void __fastcall(__int64, _BYTE *)`
- caller_count: `10`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001cfd8`
- `0x18001d828`
- `0x18001d8ac`
- `0x18001d91c`
- `0x18001d97c`
- `0x18001d9c4`
- `0x18001da3c`
- `0x18001daac`
- `0x18001db34`
- `0x18001db68`

## callees

- `0x18001b958`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b9c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b9c9`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001b97d`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001b97d`

## pseudocode

```c
void __fastcall wil::cotaskmem_secure_deleter::operator()<unsigned short>(__int64 a1, _BYTE *a2)
{
  __int64 v3; // rax
  _BYTE *i; // rcx
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  if ( a2 )
  {
    ppMalloc = 0;
    if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
    {
      v3 = ((__int64 (__fastcall *)(LPMALLOC, _BYTE *))ppMalloc->lpVtbl->GetSize)(ppMalloc, a2);
      if ( v3 != -1 )
      {
        for ( i = a2; v3; --v3 )
          *i++ = 0;
      }
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
    CoTaskMemFree(a2);
  }
}

```

## disassembly

```asm
0x18001b958  test    rdx, rdx
0x18001b95b  jz      short locret_18001B9D4
0x18001b95d  mov     [rsp+ppMalloc], rcx
0x18001b962  push    rbx
0x18001b963  sub     rsp, 20h
0x18001b967  mov     rbx, rdx
0x18001b96a  mov     [rsp+28h+ppMalloc], 0
0x18001b973  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18001b978  mov     ecx, 1; dwMemContext
0x18001b97d  call    cs:__imp_CoGetMalloc
0x18001b983  test    eax, eax
0x18001b985  js      short loc_18001B9C6
0x18001b987  mov     rcx, [rsp+28h+ppMalloc]
0x18001b98c  mov     rdx, rbx
0x18001b98f  mov     rax, [rcx]
0x18001b992  mov     rax, [rax+30h]
0x18001b996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b99b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b99f  jz      short loc_18001B9B5
0x18001b9a1  mov     rcx, rbx
0x18001b9a4  test    rax, rax
0x18001b9a7  jz      short loc_18001B9B5
0x18001b9a9  mov     byte ptr [rcx], 0
0x18001b9ac  inc     rcx
0x18001b9af  sub     rax, 1
0x18001b9b3  jnz     short loc_18001B9A9
0x18001b9b5  mov     rcx, [rsp+28h+ppMalloc]
0x18001b9ba  mov     rax, [rcx]
0x18001b9bd  mov     rax, [rax+10h]
0x18001b9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9c6  mov     rcx, rbx; pv
0x18001b9c9  call    cs:__imp_CoTaskMemFree
0x18001b9cf  add     rsp, 20h
0x18001b9d3  pop     rbx
0x18001b9d4  retn
```
