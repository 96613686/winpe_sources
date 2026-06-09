# CWMVideoDecMediaObject::GetParameterValues(_GUID const *,tagVARIANT * *,ulong *)

- ea: `0x18002cbe0`
- end: `0x18002cc96`
- name: `?GetParameterValues@CWMVideoDecMediaObject@@UEAAJPEBU_GUID@@PEAPEAUtagVARIANT@@PEAK@Z`
- size: `182`
- prototype: `int(CWMVideoDecMediaObject *__hidden this, const struct _GUID *, struct tagVARIANT **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002cbe0`
- `0x1800457f9`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002cc29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002cc29`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::GetParameterValues(
        CWMVideoDecMediaObject *this,
        const struct _GUID *a2,
        struct tagVARIANT **a3,
        unsigned int *a4)
{
  __int64 v6; // rax
  struct tagVARIANT *v7; // rax
  struct tagVARIANT *v8; // rcx
  __int64 result; // rax

  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_2efd8eee_1150_4328_9cf5_66dce933fcf4.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_2efd8eee_1150_4328_9cf5_66dce933fcf4.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_2efd8eee_1150_4328_9cf5_66dce933fcf4.Data4;
  if ( v6 )
    return memcmp_0(a2, &GUID_fb5d2347_4dd8_4509_aed0_db5fa9aa93f4, 0x10u) != 0 ? -2147467263 : -2147220720;
  v7 = (struct tagVARIANT *)CoTaskMemAlloc(0x30u);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  v7[1].iVal = 1;
  v7->vt = 11;
  result = 0;
  v8->iVal = 0;
  v8[1].vt = 11;
  *a4 = 2;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18002cbe0  mov     [rsp+arg_0], rbx
0x18002cbe5  push    rdi
0x18002cbe6  sub     rsp, 20h
0x18002cbea  mov     rbx, r9
0x18002cbed  mov     rdi, r8
0x18002cbf0  mov     r10, rdx
0x18002cbf3  test    rdx, rdx
0x18002cbf6  jz      loc_18002CC86
0x18002cbfc  test    r8, r8
0x18002cbff  jz      loc_18002CC86
0x18002cc05  test    rbx, rbx
0x18002cc08  jz      short loc_18002CC86
0x18002cc0a  mov     rax, [rdx]
0x18002cc0d  sub     rax, qword ptr cs:_GUID_2efd8eee_1150_4328_9cf5_66dce933fcf4.Data1
0x18002cc14  jnz     short loc_18002CC21
0x18002cc16  mov     rax, [rdx+8]
0x18002cc1a  sub     rax, qword ptr cs:_GUID_2efd8eee_1150_4328_9cf5_66dce933fcf4.Data4
0x18002cc21  test    rax, rax
0x18002cc24  jnz     short loc_18002CC61
0x18002cc26  lea     ecx, [rax+30h]; cb
0x18002cc29  call    cs:__imp_CoTaskMemAlloc
0x18002cc2f  mov     rcx, rax
0x18002cc32  test    rax, rax
0x18002cc35  jnz     short loc_18002CC3E
0x18002cc37  mov     eax, 8007000Eh
0x18002cc3c  jmp     short loc_18002CC8B
0x18002cc3e  mov     edx, 0Bh
0x18002cc43  mov     word ptr [rcx+20h], 1
0x18002cc49  mov     [rax], dx
0x18002cc4c  xor     eax, eax
0x18002cc4e  mov     [rcx+8], ax
0x18002cc52  mov     [rcx+18h], dx
0x18002cc56  mov     dword ptr [rbx], 2
0x18002cc5c  mov     [rdi], rcx
0x18002cc5f  jmp     short loc_18002CC8B
0x18002cc61  mov     r8d, 10h; Size
0x18002cc67  lea     rdx, _GUID_fb5d2347_4dd8_4509_aed0_db5fa9aa93f4; Buf2
0x18002cc6e  mov     rcx, r10; Buf1
0x18002cc71  call    memcmp_0
0x18002cc76  neg     eax
0x18002cc78  sbb     eax, eax
0x18002cc7a  and     eax, 0FFFC3CF1h
0x18002cc7f  add     eax, 80040310h
0x18002cc84  jmp     short loc_18002CC8B
0x18002cc86  mov     eax, 80070057h
0x18002cc8b  mov     rbx, [rsp+28h+arg_0]
0x18002cc90  add     rsp, 20h
0x18002cc94  pop     rdi
0x18002cc95  retn
```
