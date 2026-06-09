# CNetworkExplorerFolder::s_GetDtshState(INFOBAR_STATE *)

- ea: `0x180002988`
- end: `0x180002a7f`
- name: `?s_GetDtshState@CNetworkExplorerFolder@@AEAAJPEAW4INFOBAR_STATE@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(CNetworkExplorerFolder *__hidden this, enum INFOBAR_STATE *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800027b0`
- `0x18000c690`

## callees

- `0x180002988`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800029c6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800029c6`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::s_GetDtshState(CNetworkExplorerFolder *this, enum INFOBAR_STATE *a2)
{
  int v3; // ebx
  HRESULT v4; // edi
  int v5; // eax
  int v7; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-8h] BYREF
  CNetworkExplorerFolder *v9; // [rsp+70h] [rbp+30h] BYREF
  int v10; // [rsp+80h] [rbp+40h] BYREF
  int v11; // [rsp+88h] [rbp+48h] BYREF

  v9 = this;
  ppv = 0;
  v3 = 3;
  v4 = CoCreateInstance(&CLSID_DetectionAndSharing, 0, 3u, &GUID_1fda955c_61ff_11da_978c_0008744faab7, &ppv);
  if ( v4 >= 0 )
  {
    v10 = 0;
    v11 = 0;
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, int *, int *))(*(_QWORD *)ppv + 24LL))(ppv, 1, &v10, &v11);
    if ( v4 >= 0 )
    {
      LODWORD(v9) = 0;
      v7 = 0;
      v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, CNetworkExplorerFolder **, int *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             0,
             &v9,
             &v7);
      if ( v4 < 0 )
      {
        *(_DWORD *)a2 = 2;
      }
      else if ( v10 )
      {
        v5 = 4;
        if ( !(_DWORD)v9 )
          v5 = 2;
        *(_DWORD *)a2 = v5;
      }
      else
      {
        if ( !(_DWORD)v9 )
          v3 = 1;
        *(_DWORD *)a2 = v3;
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002988  mov     [rsp-28h+arg_0], rcx
0x18000298d  push    rbp
0x18000298e  push    rbx
0x18000298f  push    rsi
0x180002990  push    rdi
0x180002991  push    r15
0x180002993  mov     rbp, rsp
0x180002996  sub     rsp, 40h
0x18000299a  mov     rsi, rdx
0x18000299d  mov     [rbp+var_8], 0
0x1800029a5  lea     rax, [rbp+var_8]
0x1800029a9  mov     ebx, 3
0x1800029ae  mov     r8d, ebx; dwClsContext
0x1800029b1  mov     [rsp+40h+ppv], rax; ppv
0x1800029b6  lea     r9, _GUID_1fda955c_61ff_11da_978c_0008744faab7; riid
0x1800029bd  xor     edx, edx; pUnkOuter
0x1800029bf  lea     rcx, CLSID_DetectionAndSharing; rclsid
0x1800029c6  call    cs:__imp_CoCreateInstance
0x1800029cc  mov     edi, eax
0x1800029ce  test    eax, eax
0x1800029d0  js      loc_180002A72
0x1800029d6  mov     rcx, [rbp+var_8]
0x1800029da  lea     r15d, [rbx-2]
0x1800029de  mov     [rbp+arg_10], 0
0x1800029e5  lea     r9, [rbp+arg_18]
0x1800029e9  mov     [rbp+arg_18], 0
0x1800029f0  lea     r8, [rbp+arg_10]
0x1800029f4  mov     edx, r15d
0x1800029f7  mov     rax, [rcx]
0x1800029fa  mov     rax, [rax+18h]
0x1800029fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a03  mov     edi, eax
0x180002a05  test    eax, eax
0x180002a07  js      short loc_180002A62
0x180002a09  mov     rcx, [rbp+var_8]
0x180002a0d  lea     r9, [rbp+var_10]
0x180002a11  mov     dword ptr [rbp+arg_0], 0
0x180002a18  lea     r8, [rbp+arg_0]
0x180002a1c  mov     [rbp+var_10], 0
0x180002a23  xor     edx, edx
0x180002a25  mov     rax, [rcx]
0x180002a28  mov     rax, [rax+18h]
0x180002a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a31  mov     edi, eax
0x180002a33  test    eax, eax
0x180002a35  js      short loc_180002A5C
0x180002a37  cmp     [rbp+arg_10], 0
0x180002a3b  jnz     short loc_180002A49
0x180002a3d  cmp     dword ptr [rbp+arg_0], 0
0x180002a41  cmovz   ebx, r15d
0x180002a45  mov     [rsi], ebx
0x180002a47  jmp     short loc_180002A62
0x180002a49  cmp     dword ptr [rbp+arg_0], 0
0x180002a4d  mov     eax, 4
0x180002a52  lea     ecx, [rax-2]
0x180002a55  cmovz   eax, ecx
0x180002a58  mov     [rsi], eax
0x180002a5a  jmp     short loc_180002A62
0x180002a5c  mov     dword ptr [rsi], 2
0x180002a62  mov     rcx, [rbp+var_8]
0x180002a66  mov     rax, [rcx]
0x180002a69  mov     rax, [rax+10h]
0x180002a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a72  mov     eax, edi
0x180002a74  add     rsp, 40h
0x180002a78  pop     r15
0x180002a7a  pop     rdi
0x180002a7b  pop     rsi
0x180002a7c  pop     rbx
0x180002a7d  pop     rbp
0x180002a7e  retn
```
