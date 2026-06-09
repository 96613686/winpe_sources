# ABO_WRAPPER::CheckADSICompat(ABO_NODE *,int *)

- ea: `0x18000b54c`
- end: `0x18000b686`
- name: `?CheckADSICompat@ABO_WRAPPER@@AEAAJPEAVABO_NODE@@PEAH@Z`
- size: `314`
- prototype: `__int64 __fastcall(ABO_WRAPPER *__hidden this, struct ABO_NODE *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e6e0`

## callees

- `0x1800047b0`
- `0x1800077dc`
- `0x18000b54c`
- `0x18000fec4`
- `0x1800141f8`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000b5e9`
- `msvcrt!_wcsnicmp` at `0x18000b5e9`
- `msvcrt!_wcsicmp` at `0x18000b599`
- `msvcrt!_wcsicmp` at `0x18000b599`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000b589`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000b589`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::CheckADSICompat(ABO_WRAPPER *this, struct ABO_NODE *a2, int *a3)
{
  struct PROPERTY_ENTRY *v3; // r14
  volatile signed __int32 *v6; // rsi
  BOOL v7; // ebx
  const wchar_t *Str; // rax
  int v9; // edi
  __int64 v10; // r13
  __int64 v11; // r15
  __int64 v12; // rax
  const wchar_t *v13; // rax
  int Entry; // eax
  unsigned int v15; // ebx
  struct PROPERTY_ENTRY *v17; // [rsp+70h] [rbp+8h] BYREF

  v3 = 0;
  v17 = 0;
  if ( !a2 || !a3 )
  {
    v15 = -2147024809;
    goto LABEL_17;
  }
  v6 = 0;
  v7 = 0;
  Str = STRU::QueryStr((struct ABO_NODE *)((char *)a2 + 56));
  v9 = 1;
  if ( _wcsicmp(Str, L"ROOT") )
  {
    Entry = PROPERTY_BAG::FindEntry((struct ABO_NODE *)((char *)a2 + 184), 0x3EAu, &v17);
    v3 = v17;
    v7 = Entry >= 0;
  }
  else
  {
    v10 = *((_QWORD *)a2 + 2);
    v11 = 0;
    if ( *(_DWORD *)(v10 + 216) )
    {
      while ( 1 )
      {
        v12 = *(_QWORD *)(v10 + 208);
        v17 = (struct PROPERTY_ENTRY *)(unsigned int)v11;
        v13 = (const wchar_t *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v12 + 8 * v11) + 16LL))(*(_QWORD *)(v12 + 8 * v11));
        if ( !_wcsnicmp(L"IIsWebServer", v13, 0xCu) )
          break;
        v11 = (unsigned int)(v11 + 1);
        if ( (unsigned int)v11 >= *(_DWORD *)(v10 + 216) )
          goto LABEL_11;
      }
      v6 = *(volatile signed __int32 **)(*(_QWORD *)(v10 + 208) + 8LL * (_QWORD)v17);
      _InterlockedAdd(v6 + 2, 1u);
      if ( (unsigned int)SITE_CUSTOM_PROVIDER::FHasApplication((SITE_CUSTOM_PROVIDER *)v6) )
        goto LABEL_14;
    }
  }
LABEL_11:
  if ( *((_DWORD *)a2 + 10) )
    v7 = 1;
  v9 = v7;
LABEL_14:
  *a3 = v9;
  v15 = 0;
  if ( v6 )
    CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider((CUSTOM_PROPERTY_PROVIDER *)v6);
LABEL_17:
  if ( v3 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v3);
  return v15;
}

```

## disassembly

```asm
0x18000b54c  mov     [rsp+arg_0], rcx
0x18000b551  push    rbx
0x18000b552  push    rbp
0x18000b553  push    rsi
0x18000b554  push    rdi
0x18000b555  push    r12
0x18000b557  push    r13
0x18000b559  push    r14
0x18000b55b  push    r15
0x18000b55d  sub     rsp, 28h
0x18000b561  xor     r14d, r14d
0x18000b564  mov     r12, r8
0x18000b567  mov     [rsp+68h+arg_0], r14
0x18000b56c  mov     rbp, rdx
0x18000b56f  test    rdx, rdx
0x18000b572  jz      loc_18000B661
0x18000b578  test    r8, r8
0x18000b57b  jz      loc_18000B661
0x18000b581  lea     rcx, [rdx+38h]
0x18000b585  xor     esi, esi
0x18000b587  xor     ebx, ebx
0x18000b589  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18000b58f  mov     rcx, rax; String1
0x18000b592  lea     rdx, aRoot_0; "ROOT"
0x18000b599  call    cs:__imp__wcsicmp
0x18000b59f  lea     edi, [rsi+1]
0x18000b5a2  test    eax, eax
0x18000b5a4  jnz     short loc_18000B623
0x18000b5a6  mov     r13, [rbp+10h]
0x18000b5aa  xor     r15d, r15d
0x18000b5ad  cmp     [r13+0D8h], ebx
0x18000b5b4  jbe     loc_18000B643
0x18000b5ba  mov     rax, [r13+0D0h]
0x18000b5c1  mov     ecx, r15d
0x18000b5c4  mov     [rsp+68h+arg_0], rcx
0x18000b5c9  mov     rcx, [rax+r15*8]
0x18000b5cd  mov     rax, [rcx]
0x18000b5d0  mov     rax, [rax+10h]
0x18000b5d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5d9  mov     rdx, rax; String2
0x18000b5dc  lea     rcx, aIiswebserver; "IIsWebServer"
0x18000b5e3  mov     r8d, 0Ch; MaxCount
0x18000b5e9  call    cs:__imp__wcsnicmp
0x18000b5ef  test    eax, eax
0x18000b5f1  jz      short loc_18000B601
0x18000b5f3  add     r15d, edi
0x18000b5f6  cmp     r15d, [r13+0D8h]
0x18000b5fd  jb      short loc_18000B5BA
0x18000b5ff  jmp     short loc_18000B643
0x18000b601  mov     rax, [r13+0D0h]
0x18000b608  mov     rsi, [rsp+68h+arg_0]
0x18000b60d  mov     rsi, [rax+rsi*8]
0x18000b611  lock add [rsi+8], edi
0x18000b615  mov     rcx, rsi; this
0x18000b618  call    ?FHasApplication@SITE_CUSTOM_PROVIDER@@QEAAHXZ; SITE_CUSTOM_PROVIDER::FHasApplication(void)
0x18000b61d  test    eax, eax
0x18000b61f  jz      short loc_18000B643
0x18000b621  jmp     short loc_18000B64C
0x18000b623  lea     rcx, [rbp+0B8h]; this
0x18000b62a  mov     edx, 3EAh; unsigned int
0x18000b62f  lea     r8, [rsp+68h+arg_0]; struct PROPERTY_ENTRY **
0x18000b634  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x18000b639  mov     r14, [rsp+68h+arg_0]
0x18000b63e  test    eax, eax
0x18000b640  cmovns  ebx, edi
0x18000b643  cmp     dword ptr [rbp+28h], 0
0x18000b647  cmova   ebx, edi
0x18000b64a  mov     edi, ebx
0x18000b64c  mov     [r12], edi
0x18000b650  xor     ebx, ebx
0x18000b652  test    rsi, rsi
0x18000b655  jz      short loc_18000B666
0x18000b657  mov     rcx, rsi; this
0x18000b65a  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x18000b65f  jmp     short loc_18000B666
0x18000b661  mov     ebx, 80070057h
0x18000b666  test    r14, r14
0x18000b669  jz      short loc_18000B673
0x18000b66b  mov     rcx, r14; this
0x18000b66e  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18000b673  mov     eax, ebx
0x18000b675  add     rsp, 28h
0x18000b679  pop     r15
0x18000b67b  pop     r14
0x18000b67d  pop     r13
0x18000b67f  pop     r12
0x18000b681  pop     rdi
0x18000b682  pop     rsi
0x18000b683  pop     rbp
0x18000b684  pop     rbx
0x18000b685  retn
```
