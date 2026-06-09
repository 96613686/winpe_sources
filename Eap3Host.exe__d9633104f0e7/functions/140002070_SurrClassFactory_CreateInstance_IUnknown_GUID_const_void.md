# SurrClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140002070`
- end: `0x14000213e`
- name: `?CreateInstance@SurrClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `206`
- prototype: `__int64 __fastcall(SurrClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140002070`
- `0x140003010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1400020d1`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1400020d1`

## pseudocode

```c
__int64 __fastcall SurrClassFactory::CreateInstance(
        SurrClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 result; // rax
  LPVOID *ppv; // rdi
  const IID *v8; // rcx

  if ( a2 )
    return 2147746064LL;
  if ( *(_QWORD *)&a3->Data1 == 0x4C1267FBC48CA462LL && *(_QWORD *)a3->Data4 == 0xAEA80F4615641AA2uLL )
  {
    ppv = (LPVOID *)((char *)this + 8);
    if ( *((_QWORD *)this + 1) )
      goto LABEL_8;
    v8 = &rclsid;
    goto LABEL_7;
  }
  if ( *(_QWORD *)&a3->Data1 == 0x42CECE5B9DAA7B9DLL && *(_QWORD *)a3->Data4 == 0x44AC84C2BB3242B9LL )
  {
    ppv = (LPVOID *)((char *)this + 16);
    if ( *((_QWORD *)this + 2) )
      goto LABEL_8;
    v8 = (const IID *)qword_140004660;
LABEL_7:
    if ( CoGetClassObject(v8, 1u, 0, &GUID_00000001_0000_0000_c000_000000000046, ppv) )
      return 2147942414LL;
LABEL_8:
    result = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const struct _GUID *, void **))(*(_QWORD *)*ppv + 24LL))(
               *ppv,
               0,
               a3,
               a4);
    if ( !(_DWORD)result )
      return result;
    return 2147942414LL;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x140002070  mov     [rsp+arg_0], rbx
0x140002075  mov     [rsp+arg_8], rsi
0x14000207a  push    rdi
0x14000207b  sub     rsp, 30h
0x14000207f  mov     rsi, r9
0x140002082  mov     rbx, r8
0x140002085  test    rdx, rdx
0x140002088  jz      short loc_140002094
0x14000208a  mov     eax, 80040110h
0x14000208f  jmp     loc_14000212E
0x140002094  mov     rax, [r8]
0x140002097  cmp     rax, cs:qword_140004670
0x14000209e  jnz     short loc_1400020FD
0x1400020a0  mov     rax, [r8+8]
0x1400020a4  cmp     rax, cs:qword_140004678
0x1400020ab  jnz     short loc_1400020FD
0x1400020ad  lea     rdi, [rcx+8]
0x1400020b1  cmp     qword ptr [rdi], 0
0x1400020b5  jnz     short loc_1400020DB
0x1400020b7  lea     rcx, rclsid; rclsid
0x1400020be  xor     r8d, r8d; pvReserved
0x1400020c1  mov     [rsp+38h+ppv], rdi; ppv
0x1400020c6  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x1400020cd  lea     edx, [r8+1]; dwClsContext
0x1400020d1  call    cs:__imp_CoGetClassObject
0x1400020d7  test    eax, eax
0x1400020d9  jnz     short loc_1400020F6
0x1400020db  mov     rcx, [rdi]
0x1400020de  mov     r9, rsi
0x1400020e1  mov     r8, rbx
0x1400020e4  xor     edx, edx
0x1400020e6  mov     rax, [rcx]
0x1400020e9  mov     rax, [rax+18h]
0x1400020ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400020f2  test    eax, eax
0x1400020f4  jz      short loc_14000212E
0x1400020f6  mov     eax, 8007000Eh
0x1400020fb  jmp     short loc_14000212E
0x1400020fd  mov     rax, [r8]
0x140002100  cmp     rax, cs:qword_140004650
0x140002107  jnz     short loc_140002129
0x140002109  mov     rax, [r8+8]
0x14000210d  cmp     rax, cs:qword_140004658
0x140002114  jnz     short loc_140002129
0x140002116  lea     rdi, [rcx+10h]
0x14000211a  cmp     qword ptr [rdi], 0
0x14000211e  jnz     short loc_1400020DB
0x140002120  lea     rcx, qword_140004660
0x140002127  jmp     short loc_1400020BE
0x140002129  mov     eax, 80004002h
0x14000212e  mov     rbx, [rsp+38h+arg_0]
0x140002133  mov     rsi, [rsp+38h+arg_8]
0x140002138  add     rsp, 30h
0x14000213c  pop     rdi
0x14000213d  retn
```
