# ConvertPackageSidWorker(IVaultAllocator *,void * const,_VAULT_ITEM_ELEMENT * *)

- ea: `0x18004911c`
- end: `0x1800491f7`
- name: `?ConvertPackageSidWorker@@YAKPEAUIVaultAllocator@@QEAXPEAPEAU_VAULT_ITEM_ELEMENT@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(struct IVaultAllocator *, void *const, struct _VAULT_ITEM_ELEMENT **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800256b0`

## callees

- `0x18004911c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180049169`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180049169`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004912e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004912e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConvertPackageSidWorker(struct IVaultAllocator *a1, void *const a2, struct _VAULT_ITEM_ELEMENT **a3)
{
  __int64 LengthSid; // rbp
  void *v6; // rax
  void *v7; // rbx
  struct _VAULT_ITEM_ELEMENT *v9; // rax
  __int64 v10; // rax
  __int128 v11; // [rsp+20h] [rbp-48h]

  LengthSid = GetLengthSid(a2);
  v6 = (void *)(*(__int64 (__fastcall **)(void *, __int64))(VaultGlobals::g_RpcAlloc + 16LL))(
                 &VaultGlobals::g_RpcAlloc,
                 LengthSid);
  v7 = v6;
  if ( !v6 )
    return 14;
  if ( CopySid(LengthSid, v6, a2) )
  {
    v9 = (struct _VAULT_ITEM_ELEMENT *)(*(__int64 (__fastcall **)(void *, __int64))(VaultGlobals::g_RpcAlloc + 16LL))(
                                         &VaultGlobals::g_RpcAlloc,
                                         32);
    *a3 = v9;
    if ( !v9 )
    {
      (*(void (__fastcall **)(void *, void *))(VaultGlobals::g_RpcAlloc + 8LL))(&VaultGlobals::g_RpcAlloc, v7);
      return 14;
    }
    *(_DWORD *)v9 = 5;
    v10 = (__int64)*a3;
    *(_QWORD *)&v11 = 12;
    *((_QWORD *)&v11 + 1) = v7;
    *(_OWORD *)(v10 + 8) = v11;
    *(_QWORD *)(v10 + 24) = 0;
    return 0;
  }
  else
  {
    (*(void (__fastcall **)(void *, void *))(VaultGlobals::g_RpcAlloc + 8LL))(&VaultGlobals::g_RpcAlloc, v7);
    return 87;
  }
}

```

## disassembly

```asm
0x18004911c  push    rbx
0x18004911e  push    rbp
0x18004911f  push    rsi
0x180049120  push    rdi
0x180049121  sub     rsp, 48h
0x180049125  mov     rcx, rdx; pSid
0x180049128  mov     rdi, r8
0x18004912b  mov     rsi, rdx
0x18004912e  call    cs:__imp_GetLengthSid
0x180049134  mov     rcx, cs:?g_RpcAlloc@VaultGlobals@@3VCVaultRpcAllocator@@A; CVaultRpcAllocator VaultGlobals::g_RpcAlloc
0x18004913b  mov     ebp, eax
0x18004913d  mov     edx, eax
0x18004913f  mov     rax, [rcx+10h]
0x180049143  lea     rcx, ?g_RpcAlloc@VaultGlobals@@3VCVaultRpcAllocator@@A; CVaultRpcAllocator VaultGlobals::g_RpcAlloc
0x18004914a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004914f  mov     rbx, rax
0x180049152  test    rax, rax
0x180049155  jnz     short loc_180049161
0x180049157  mov     eax, 0Eh
0x18004915c  jmp     loc_1800491EE
0x180049161  mov     r8, rsi; pSourceSid
0x180049164  mov     rdx, rbx; pDestinationSid
0x180049167  mov     ecx, ebp; nDestinationSidLength
0x180049169  call    cs:__imp_CopySid
0x18004916f  test    eax, eax
0x180049171  lea     rcx, ?g_RpcAlloc@VaultGlobals@@3VCVaultRpcAllocator@@A; CVaultRpcAllocator VaultGlobals::g_RpcAlloc
0x180049178  mov     rax, cs:?g_RpcAlloc@VaultGlobals@@3VCVaultRpcAllocator@@A; CVaultRpcAllocator VaultGlobals::g_RpcAlloc
0x18004917f  jnz     short loc_180049194
0x180049181  mov     rax, [rax+8]
0x180049185  mov     rdx, rbx
0x180049188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004918d  mov     eax, 57h ; 'W'
0x180049192  jmp     short loc_1800491EE
0x180049194  mov     rax, [rax+10h]
0x180049198  mov     edx, 20h ; ' '
0x18004919d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800491a2  mov     [rdi], rax
0x1800491a5  test    rax, rax
0x1800491a8  jnz     short loc_1800491C6
0x1800491aa  mov     rax, cs:?g_RpcAlloc@VaultGlobals@@3VCVaultRpcAllocator@@A; CVaultRpcAllocator VaultGlobals::g_RpcAlloc
0x1800491b1  lea     rcx, ?g_RpcAlloc@VaultGlobals@@3VCVaultRpcAllocator@@A; CVaultRpcAllocator VaultGlobals::g_RpcAlloc
0x1800491b8  mov     rdx, rbx
0x1800491bb  mov     rax, [rax+8]
0x1800491bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800491c4  jmp     short loc_180049157
0x1800491c6  mov     dword ptr [rax], 5
0x1800491cc  xor     ecx, ecx
0x1800491ce  mov     rax, [rdi]
0x1800491d1  mov     qword ptr [rsp+68h+var_48], 0Ch
0x1800491da  mov     qword ptr [rsp+68h+var_48+8], rbx
0x1800491df  movups  xmm0, [rsp+68h+var_48]
0x1800491e4  movups  xmmword ptr [rax+8], xmm0
0x1800491e8  mov     [rax+18h], rcx
0x1800491ec  xor     eax, eax
0x1800491ee  add     rsp, 48h
0x1800491f2  pop     rdi
0x1800491f3  pop     rsi
0x1800491f4  pop     rbp
0x1800491f5  pop     rbx
0x1800491f6  retn
```
