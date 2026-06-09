# wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)

- ea: `0x18000fae0`
- end: `0x18000fb5d`
- name: `??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z`
- size: `125`
- prototype: `void __fastcall(__int64, _BYTE *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800122ac`
- `0x1800123bc`
- `0x180017380`
- `0x18001d318`

## callees

- `0x18000fae0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000fb05`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000fb05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb51`

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
0x18000fae0  test    rdx, rdx
0x18000fae3  jz      short locret_18000FB5C
0x18000fae5  mov     [rsp+ppMalloc], rcx
0x18000faea  push    rbx
0x18000faeb  sub     rsp, 20h
0x18000faef  mov     rbx, rdx
0x18000faf2  mov     [rsp+28h+ppMalloc], 0
0x18000fafb  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18000fb00  mov     ecx, 1; dwMemContext
0x18000fb05  call    cs:__imp_CoGetMalloc
0x18000fb0b  test    eax, eax
0x18000fb0d  js      short loc_18000FB4E
0x18000fb0f  mov     rcx, [rsp+28h+ppMalloc]
0x18000fb14  mov     rdx, rbx
0x18000fb17  mov     rax, [rcx]
0x18000fb1a  mov     rax, [rax+30h]
0x18000fb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb23  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fb27  jz      short loc_18000FB3D
0x18000fb29  mov     rcx, rbx
0x18000fb2c  test    rax, rax
0x18000fb2f  jz      short loc_18000FB3D
0x18000fb31  mov     byte ptr [rcx], 0
0x18000fb34  inc     rcx
0x18000fb37  sub     rax, 1
0x18000fb3b  jnz     short loc_18000FB31
0x18000fb3d  mov     rcx, [rsp+28h+ppMalloc]
0x18000fb42  mov     rax, [rcx]
0x18000fb45  mov     rax, [rax+10h]
0x18000fb49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb4e  mov     rcx, rbx; pv
0x18000fb51  call    cs:__imp_CoTaskMemFree
0x18000fb57  add     rsp, 20h
0x18000fb5b  pop     rbx
0x18000fb5c  retn
```
