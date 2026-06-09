# KdcFreeDomainInfo(_KDC_DOMAIN_INFO *)

- ea: `0x180058284`
- end: `0x1800583f8`
- name: `?KdcFreeDomainInfo@@YAXPEAU_KDC_DOMAIN_INFO@@@Z`
- size: `372`
- prototype: `void __fastcall(struct _KDC_DOMAIN_INFO *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180056f60`
- `0x180057068`
- `0x180057d68`

## callees

- `0x180003908`
- `0x180058284`
- `0x18005a090`
- `0x18007dc20`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x1800582ca`
- `ntdll!RtlDeleteCriticalSection` at `0x1800582ca`

## pseudocode

```c
void __fastcall KdcFreeDomainInfo(struct _KDC_DOMAIN_INFO *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  size_t v4; // r8
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  size_t v8; // r8
  void *v9; // rcx
  void *v10; // rcx
  size_t v11; // r8
  void *v12; // rcx
  void *v13; // rcx
  size_t v14; // r8

  if ( a1 )
  {
    KerbFreeString((char *)a1 + 32);
    KerbFreeString((char *)a1 + 16);
    v2 = (void *)*((_QWORD *)a1 + 11);
    if ( v2 )
      MIDL_user_free(v2);
    if ( *((_DWORD *)a1 + 66) )
    {
      RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 224));
      *((_DWORD *)a1 + 66) = 0;
    }
    v3 = (void *)*((_QWORD *)a1 + 12);
    if ( v3 )
    {
      MIDL_user_free(v3);
      *((_QWORD *)a1 + 12) = 0;
    }
    v4 = *((unsigned __int16 *)a1 + 56);
    v5 = (void *)*((_QWORD *)a1 + 15);
    *((_DWORD *)a1 + 26) = 0;
    memset_0(v5, 0, v4);
    KerbFreeString((char *)a1 + 112);
    v6 = (void *)*((_QWORD *)a1 + 16);
    if ( v6 )
    {
      MIDL_user_free(v6);
      *((_QWORD *)a1 + 16) = 0;
    }
    v7 = (void *)*((_QWORD *)a1 + 19);
    v8 = *((unsigned __int16 *)a1 + 72);
    *((_DWORD *)a1 + 34) = 0;
    memset_0(v7, 0, v8);
    KerbFreeString((char *)a1 + 144);
    v9 = (void *)*((_QWORD *)a1 + 20);
    if ( v9 )
    {
      MIDL_user_free(v9);
      *((_QWORD *)a1 + 20) = 0;
    }
    v10 = (void *)*((_QWORD *)a1 + 23);
    v11 = *((unsigned __int16 *)a1 + 88);
    *((_DWORD *)a1 + 42) = 0;
    memset_0(v10, 0, v11);
    KerbFreeString((char *)a1 + 176);
    v12 = (void *)*((_QWORD *)a1 + 24);
    if ( v12 )
    {
      MIDL_user_free(v12);
      *((_QWORD *)a1 + 24) = 0;
    }
    v13 = (void *)*((_QWORD *)a1 + 27);
    v14 = *((unsigned __int16 *)a1 + 104);
    *((_DWORD *)a1 + 50) = 0;
    memset_0(v13, 0, v14);
    KerbFreeString((char *)a1 + 208);
    MIDL_user_free(a1);
  }
}

```

## disassembly

```asm
0x180058284  test    rcx, rcx
0x180058287  jz      locret_1800583F7
0x18005828d  mov     [rsp+arg_0], rbx
0x180058292  push    rdi
0x180058293  sub     rsp, 20h
0x180058297  mov     rdi, rcx
0x18005829a  add     rcx, 20h ; ' '
0x18005829e  call    KerbFreeString
0x1800582a3  lea     rcx, [rdi+10h]
0x1800582a7  call    KerbFreeString
0x1800582ac  mov     rcx, [rdi+58h]; void *
0x1800582b0  test    rcx, rcx
0x1800582b3  jz      short loc_1800582BA
0x1800582b5  call    MIDL_user_free
0x1800582ba  cmp     dword ptr [rdi+108h], 0
0x1800582c1  jz      short loc_1800582DA
0x1800582c3  lea     rcx, [rdi+0E0h]; CriticalSection
0x1800582ca  call    cs:__imp_RtlDeleteCriticalSection
0x1800582d0  mov     dword ptr [rdi+108h], 0
0x1800582da  mov     rcx, [rdi+60h]; void *
0x1800582de  test    rcx, rcx
0x1800582e1  jz      short loc_1800582F0
0x1800582e3  call    MIDL_user_free
0x1800582e8  mov     qword ptr [rdi+60h], 0
0x1800582f0  movzx   r8d, word ptr [rdi+70h]; Size
0x1800582f5  xor     edx, edx; Val
0x1800582f7  mov     rcx, [rdi+78h]; void *
0x1800582fb  mov     dword ptr [rdi+68h], 0
0x180058302  call    memset_0
0x180058307  lea     rcx, [rdi+70h]
0x18005830b  call    KerbFreeString
0x180058310  mov     rcx, [rdi+80h]; void *
0x180058317  test    rcx, rcx
0x18005831a  jz      short loc_18005832C
0x18005831c  call    MIDL_user_free
0x180058321  mov     qword ptr [rdi+80h], 0
0x18005832c  mov     rcx, [rdi+98h]; void *
0x180058333  lea     rbx, [rdi+90h]
0x18005833a  movzx   r8d, word ptr [rbx]; Size
0x18005833e  xor     edx, edx; Val
0x180058340  mov     dword ptr [rdi+88h], 0
0x18005834a  call    memset_0
0x18005834f  mov     rcx, rbx
0x180058352  call    KerbFreeString
0x180058357  mov     rcx, [rdi+0A0h]; void *
0x18005835e  test    rcx, rcx
0x180058361  jz      short loc_180058373
0x180058363  call    MIDL_user_free
0x180058368  mov     qword ptr [rdi+0A0h], 0
0x180058373  mov     rcx, [rdi+0B8h]; void *
0x18005837a  lea     rbx, [rdi+0B0h]
0x180058381  movzx   r8d, word ptr [rbx]; Size
0x180058385  xor     edx, edx; Val
0x180058387  mov     dword ptr [rdi+0A8h], 0
0x180058391  call    memset_0
0x180058396  mov     rcx, rbx
0x180058399  call    KerbFreeString
0x18005839e  mov     rcx, [rdi+0C0h]; void *
0x1800583a5  test    rcx, rcx
0x1800583a8  jz      short loc_1800583BA
0x1800583aa  call    MIDL_user_free
0x1800583af  mov     qword ptr [rdi+0C0h], 0
0x1800583ba  mov     rcx, [rdi+0D8h]; void *
0x1800583c1  lea     rbx, [rdi+0D0h]
0x1800583c8  movzx   r8d, word ptr [rbx]; Size
0x1800583cc  xor     edx, edx; Val
0x1800583ce  mov     dword ptr [rdi+0C8h], 0
0x1800583d8  call    memset_0
0x1800583dd  mov     rcx, rbx
0x1800583e0  call    KerbFreeString
0x1800583e5  mov     rcx, rdi; void *
0x1800583e8  call    MIDL_user_free
0x1800583ed  mov     rbx, [rsp+28h+arg_0]
0x1800583f2  add     rsp, 20h
0x1800583f6  pop     rdi
0x1800583f7  retn
```
