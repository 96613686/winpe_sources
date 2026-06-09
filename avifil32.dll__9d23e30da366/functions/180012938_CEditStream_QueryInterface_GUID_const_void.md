# CEditStream::QueryInterface(_GUID const &,void * *)

- ea: `0x180012938`
- end: `0x180012a26`
- name: `?QueryInterface@CEditStream@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `238`
- prototype: `__int64 __fastcall(CEditStream *__hidden this, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800128e0`
- `0x180012900`
- `0x180012920`

## callees

- `0x180012938`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CEditStream::QueryInterface(CEditStream *this, const struct _GUID *a2, void **a3)
{
  char *v3; // rdx
  char *v4; // rax
  __int64 v5; // rax
  char *v6; // rcx

  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
    goto LABEL_3;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_EditStream.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)CLSID_EditStream.Data4 )
  {
    v3 = (char *)this - 272;
    v4 = 0;
    if ( this != (CEditStream *)272 )
    {
      v5 = *(int *)(*(_QWORD *)v3 + 12LL);
      goto LABEL_15;
    }
LABEL_16:
    *a3 = v4;
    v6 = (char *)this + *(int *)(*(_QWORD *)v3 + 4LL) - 272;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IAVIStream.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IAVIStream.Data4 )
  {
LABEL_3:
    v3 = (char *)this - 272;
    v4 = 0;
    if ( this != (CEditStream *)272 )
    {
      v5 = *(int *)(*(_QWORD *)v3 + 4LL);
LABEL_15:
      v4 = (char *)this + v5 - 272;
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IAVIEditStream.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IAVIEditStream.Data4 )
  {
    v3 = (char *)this - 272;
    v4 = 0;
    if ( this != (CEditStream *)272 )
    {
      v5 = *(int *)(*(_QWORD *)v3 + 8LL);
      goto LABEL_15;
    }
    goto LABEL_16;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x180012938  sub     rsp, 28h
0x18001293c  mov     rax, [rdx]
0x18001293f  mov     r9, rcx
0x180012942  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180012949  jnz     short loc_180012973
0x18001294b  mov     rax, [rdx+8]
0x18001294f  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180012956  jnz     short loc_180012973
0x180012958  lea     rdx, [rcx-110h]
0x18001295f  xor     eax, eax
0x180012961  test    rdx, rdx
0x180012964  jz      loc_1800129F3
0x18001296a  mov     rax, [rdx]
0x18001296d  movsxd  rax, dword ptr [rax+4]
0x180012971  jmp     short loc_1800129EA
0x180012973  mov     rax, [rdx]
0x180012976  cmp     rax, qword ptr cs:CLSID_EditStream.Data1
0x18001297d  jnz     short loc_1800129A3
0x18001297f  mov     rax, [rdx+8]
0x180012983  cmp     rax, qword ptr cs:CLSID_EditStream.Data4
0x18001298a  jnz     short loc_1800129A3
0x18001298c  lea     rdx, [rcx-110h]
0x180012993  xor     eax, eax
0x180012995  test    rdx, rdx
0x180012998  jz      short loc_1800129F3
0x18001299a  mov     rax, [rdx]
0x18001299d  movsxd  rax, dword ptr [rax+0Ch]
0x1800129a1  jmp     short loc_1800129EA
0x1800129a3  mov     rax, [rdx]
0x1800129a6  cmp     rax, qword ptr cs:IID_IAVIStream.Data1
0x1800129ad  jnz     short loc_1800129BC
0x1800129af  mov     rax, [rdx+8]
0x1800129b3  cmp     rax, qword ptr cs:IID_IAVIStream.Data4
0x1800129ba  jz      short loc_180012958
0x1800129bc  mov     rax, [rdx]
0x1800129bf  cmp     rax, qword ptr cs:IID_IAVIEditStream.Data1
0x1800129c6  jnz     short loc_180012A17
0x1800129c8  mov     rax, [rdx+8]
0x1800129cc  cmp     rax, qword ptr cs:IID_IAVIEditStream.Data4
0x1800129d3  jnz     short loc_180012A17
0x1800129d5  lea     rdx, [rcx-110h]
0x1800129dc  xor     eax, eax
0x1800129de  test    rdx, rdx
0x1800129e1  jz      short loc_1800129F3
0x1800129e3  mov     rax, [rdx]
0x1800129e6  movsxd  rax, dword ptr [rax+8]
0x1800129ea  add     rax, 0FFFFFFFFFFFFFEF0h
0x1800129f0  add     rax, r9
0x1800129f3  mov     [r8], rax
0x1800129f6  add     r9, 0FFFFFFFFFFFFFEF0h
0x1800129fd  mov     rax, [rdx]
0x180012a00  movsxd  rcx, dword ptr [rax+4]
0x180012a04  add     rcx, r9
0x180012a07  mov     rax, [rcx]
0x180012a0a  mov     rax, [rax+8]
0x180012a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a13  xor     eax, eax
0x180012a15  jmp     short loc_180012A21
0x180012a17  xor     eax, eax
0x180012a19  mov     [r8], rax
0x180012a1c  mov     eax, 80004002h
0x180012a21  add     rsp, 28h
0x180012a25  retn
```
