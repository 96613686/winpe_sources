# StructuredQuery1::DeleteVirtualPropertyInfoArray(StructuredQuery1::VIRTUAL_PROPERTY_INFO * *,ulong *)

- ea: `0x18005be44`
- end: `0x18005be96`
- name: `?DeleteVirtualPropertyInfoArray@StructuredQuery1@@YAXPEAPEAUVIRTUAL_PROPERTY_INFO@1@PEAK@Z`
- size: `82`
- prototype: `void __fastcall(StructuredQuery1 *__hidden this, struct StructuredQuery1::VIRTUAL_PROPERTY_INFO **, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180055050`
- `0x18005b318`

## callees

- `0x18005be44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005be69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005be78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005be69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005be78`

## pseudocode

```c
void __fastcall StructuredQuery1::DeleteVirtualPropertyInfoArray(
        void **this,
        struct StructuredQuery1::VIRTUAL_PROPERTY_INFO **a2,
        unsigned int *a3)
{
  unsigned int v3; // ebp
  __int64 v4; // rbx
  LPVOID *i; // rdi

  v3 = *(_DWORD *)a2;
  v4 = 0;
  for ( i = (LPVOID *)*this; (unsigned int)v4 < v3; v4 = (unsigned int)(v4 + 1) )
    CoTaskMemFree(i[5 * v4 + 3]);
  CoTaskMemFree(i);
  *this = 0;
  *(_DWORD *)a2 = 0;
}

```

## disassembly

```asm
0x18005be44  push    rbx
0x18005be46  push    rbp
0x18005be47  push    rsi
0x18005be48  push    rdi
0x18005be49  push    r14
0x18005be4b  sub     rsp, 20h
0x18005be4f  mov     ebp, [rdx]
0x18005be51  xor     ebx, ebx
0x18005be53  mov     rdi, [rcx]
0x18005be56  mov     rsi, rdx
0x18005be59  mov     r14, rcx
0x18005be5c  test    ebp, ebp
0x18005be5e  jz      short loc_18005BE75
0x18005be60  lea     rcx, [rbx+rbx*4]
0x18005be64  mov     rcx, [rdi+rcx*8+18h]; pv
0x18005be69  call    cs:__imp_CoTaskMemFree
0x18005be6f  inc     ebx
0x18005be71  cmp     ebx, ebp
0x18005be73  jb      short loc_18005BE60
0x18005be75  mov     rcx, rdi; pv
0x18005be78  call    cs:__imp_CoTaskMemFree
0x18005be7e  mov     qword ptr [r14], 0
0x18005be85  mov     dword ptr [rsi], 0
0x18005be8b  add     rsp, 20h
0x18005be8f  pop     r14
0x18005be91  pop     rdi
0x18005be92  pop     rsi
0x18005be93  pop     rbp
0x18005be94  pop     rbx
0x18005be95  retn
```
