# FixedCapacityObjectCollection::CreateInstance(uint,_GUID const &,void * *)

- ea: `0x18000bd20`
- end: `0x18000be7f`
- name: `?CreateInstance@FixedCapacityObjectCollection@@SAJIAEBU_GUID@@PEAPEAX@Z`
- size: `351`
- prototype: `__int64 __fastcall(unsigned int, const struct _GUID *, void **)`
- caller_count: `25`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006790`
- `0x18000a340`
- `0x18000b180`
- `0x18000b9a0`
- `0x18000c3a0`
- `0x180032514`
- `0x180033268`
- `0x1800335ac`
- `0x18003d560`
- `0x180044c20`
- `0x180049d10`
- `0x18004f0d0`
- `0x1800523f8`
- `0x180056a7c`
- `0x1800575c0`
- `0x18005a874`
- `0x1800631b0`
- `0x18006a6c0`
- `0x18006dc70`
- `0x18006e8bc`
- `0x18006ec10`
- `0x18007d790`
- `0x18007d91c`
- `0x18007e894`
- `0x18007e9a4`

## callees

- `0x18000bd20`
- `0x18000be88`
- `0x18005db64`
- `0x18005e740`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000bdc7`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000bdc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bda3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bda3`

## pseudocode

```c
__int64 __fastcall FixedCapacityObjectCollection::CreateInstance(unsigned int a1, const struct _GUID *a2, void **a3)
{
  unsigned __int64 v4; // rsi
  int v6; // edi
  IMalloc *v7; // rax
  FixedCapacityObjectCollection *v8; // rax
  FixedCapacityObjectCollection *v9; // rbx
  LPVOID v10; // rax
  LPVOID v11; // r15
  size_t v12; // rdi
  __int64 (__fastcall **v13)(FixedCapacityObjectCollection *, const struct _GUID *, void **); // rax
  void *v15; // [rsp+60h] [rbp+18h] BYREF
  LPMALLOC ppMalloc; // [rsp+68h] [rbp+20h] BYREF

  v4 = a1;
  v15 = 0;
  v6 = -2147024882;
  v7 = (IMalloc *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  ppMalloc = v7;
  if ( v7 )
  {
    v8 = FixedCapacityObjectCollection::FixedCapacityObjectCollection((FixedCapacityObjectCollection *)v7);
    v9 = v8;
    if ( v8 )
    {
      if ( !(_DWORD)v4 )
        goto LABEL_10;
      *((_QWORD *)v8 + 1) = 0;
      ppMalloc = 0;
      if ( is_mul_ok(v4, 8u) )
      {
        v10 = CoTaskMemAlloc(8 * v4);
        *((_QWORD *)v9 + 1) = v10;
        v11 = v10;
        if ( v10 )
        {
          ppMalloc = 0;
          v12 = 0;
          if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
          {
            v12 = ((__int64 (__fastcall *)(LPMALLOC, LPVOID))ppMalloc->lpVtbl->GetSize)(ppMalloc, v11);
            ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
          }
          memset_0(*((void **)v9 + 1), 0, v12);
          v6 = 0;
        }
      }
      else
      {
        v6 = -2147024362;
      }
      if ( v6 >= 0 )
      {
LABEL_10:
        v13 = *(__int64 (__fastcall ***)(FixedCapacityObjectCollection *, const struct _GUID *, void **))v9;
        *((_DWORD *)v9 + 4) = v4;
        v6 = (*v13)(v9, a2, &v15);
      }
      (*(void (__fastcall **)(FixedCapacityObjectCollection *))(*(_QWORD *)v9 + 16LL))(v9);
      *a3 = v15;
    }
    else
    {
      *a3 = v15;
    }
    return (unsigned int)v6;
  }
  else
  {
    *a3 = v15;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000bd20  push    rbp
0x18000bd22  push    rsi
0x18000bd23  push    rdi
0x18000bd24  push    r12
0x18000bd26  push    r14
0x18000bd28  sub     rsp, 20h
0x18000bd2c  mov     rbp, rdx
0x18000bd2f  mov     esi, ecx
0x18000bd31  xor     r12d, r12d
0x18000bd34  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bd3b  mov     ecx, 20h ; ' '; unsigned __int64
0x18000bd40  mov     [rsp+48h+arg_10], r12
0x18000bd45  mov     r14, r8
0x18000bd48  mov     edi, 8007000Eh
0x18000bd4d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bd52  mov     [rsp+48h+ppMalloc], rax
0x18000bd57  test    rax, rax
0x18000bd5a  jz      loc_18000BE62
0x18000bd60  mov     rcx, rax; this
0x18000bd63  mov     [rsp+48h+arg_0], rbx
0x18000bd68  call    ??0FixedCapacityObjectCollection@@AEAA@XZ; FixedCapacityObjectCollection::FixedCapacityObjectCollection(void)
0x18000bd6d  mov     rbx, rax
0x18000bd70  test    rax, rax
0x18000bd73  jz      loc_18000BE58
0x18000bd79  test    esi, esi
0x18000bd7b  jz      loc_18000BE13
0x18000bd81  mov     [rax+8], r12
0x18000bd85  mov     eax, 8
0x18000bd8a  mul     rsi
0x18000bd8d  mov     [rsp+48h+ppMalloc], r12
0x18000bd92  test    rdx, rdx
0x18000bd95  jnz     loc_18000BE78
0x18000bd9b  mov     rcx, rax; cb
0x18000bd9e  mov     [rsp+48h+arg_8], r15
0x18000bda3  call    cs:__imp_CoTaskMemAlloc
0x18000bda9  mov     [rbx+8], rax
0x18000bdad  mov     r15, rax
0x18000bdb0  test    rax, rax
0x18000bdb3  jz      short loc_18000BE0A
0x18000bdb5  lea     rdx, [rsp+48h+ppMalloc]; ppMalloc
0x18000bdba  mov     [rsp+48h+ppMalloc], r12
0x18000bdbf  mov     ecx, 1; dwMemContext
0x18000bdc4  mov     edi, r12d
0x18000bdc7  call    cs:__imp_CoGetMalloc
0x18000bdcd  test    eax, eax
0x18000bdcf  js      short loc_18000BDF9
0x18000bdd1  mov     rcx, [rsp+48h+ppMalloc]
0x18000bdd6  mov     rdx, r15
0x18000bdd9  mov     rax, [rcx]
0x18000bddc  mov     rax, [rax+30h]
0x18000bde0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bde5  mov     rcx, [rsp+48h+ppMalloc]
0x18000bdea  mov     rdi, rax
0x18000bded  mov     rdx, [rcx]
0x18000bdf0  mov     rax, [rdx+10h]
0x18000bdf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdf9  mov     rcx, [rbx+8]; void *
0x18000bdfd  mov     r8, rdi; Size
0x18000be00  xor     edx, edx; Val
0x18000be02  call    memset_0
0x18000be07  mov     edi, r12d
0x18000be0a  mov     r15, [rsp+48h+arg_8]
0x18000be0f  test    edi, edi
0x18000be11  js      short loc_18000BE2E
0x18000be13  mov     rax, [rbx]
0x18000be16  lea     r8, [rsp+48h+arg_10]
0x18000be1b  mov     rdx, rbp
0x18000be1e  mov     [rbx+10h], esi
0x18000be21  mov     rcx, rbx
0x18000be24  mov     rax, [rax]
0x18000be27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be2c  mov     edi, eax
0x18000be2e  mov     rcx, [rbx]
0x18000be31  mov     rax, [rcx+10h]
0x18000be35  mov     rcx, rbx
0x18000be38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be3d  mov     rcx, [rsp+48h+arg_10]
0x18000be42  mov     [r14], rcx
0x18000be45  mov     rbx, [rsp+48h+arg_0]
0x18000be4a  mov     eax, edi
0x18000be4c  add     rsp, 20h
0x18000be50  pop     r14
0x18000be52  pop     r12
0x18000be54  pop     rdi
0x18000be55  pop     rsi
0x18000be56  pop     rbp
0x18000be57  retn
0x18000be58  mov     rax, [rsp+48h+arg_10]
0x18000be5d  mov     [r14], rax
0x18000be60  jmp     short loc_18000BE45
0x18000be62  mov     rax, [rsp+48h+arg_10]
0x18000be67  mov     [r14], rax
0x18000be6a  mov     eax, edi
0x18000be6c  add     rsp, 20h
0x18000be70  pop     r14
0x18000be72  pop     r12
0x18000be74  pop     rdi
0x18000be75  pop     rsi
0x18000be76  pop     rbp
0x18000be77  retn
0x18000be78  mov     edi, 80070216h
0x18000be7d  jmp     short loc_18000BE0F
```
