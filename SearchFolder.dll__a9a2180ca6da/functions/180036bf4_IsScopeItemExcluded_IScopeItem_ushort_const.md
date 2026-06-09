# _IsScopeItemExcluded(IScopeItem *,ushort const *)

- ea: `0x180036bf4`
- end: `0x180036c89`
- name: `?_IsScopeItemExcluded@@YAHPEAUIScopeItem@@PEBG@Z`
- size: `149`
- prototype: `__int64 __fastcall(struct IScopeItem *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800310f8`
- `0x180031208`

## callees

- `0x180036bf4`
- `0x180051010`

## import_xrefs

- `SHELL32!__imp_PathComparePaths` at `0x180036c55`
- `SHELL32!__imp_PathComparePaths` at `0x180036c55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036c65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036c65`

## pseudocode

```c
__int64 __fastcall _IsScopeItemExcluded(struct IScopeItem *a1, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  __int64 v4; // rax
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  if ( a2 )
  {
    v4 = *(_QWORD *)a1;
    v7 = 0;
    if ( (*(int (__fastcall **)(struct IScopeItem *, GUID *, __int64 *))(v4 + 120))(
           a1,
           &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
           &v7) >= 0 )
    {
      pv = 0;
      if ( (*(int (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v7 + 40LL))(v7, 2147647488LL, &pv) >= 0 )
      {
        LOBYTE(v2) = (PathComparePaths(a2, pv) & 0xA) != 0;
        CoTaskMemFree(pv);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180036bf4  mov     [rsp+arg_0], rbx
0x180036bf9  push    rdi
0x180036bfa  sub     rsp, 20h
0x180036bfe  xor     ebx, ebx
0x180036c00  mov     rdi, rdx
0x180036c03  test    rdx, rdx
0x180036c06  jz      short loc_180036C7C
0x180036c08  mov     rax, [rcx]
0x180036c0b  lea     r8, [rsp+28h+arg_10]
0x180036c10  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180036c17  mov     [rsp+28h+arg_10], rbx
0x180036c1c  mov     rax, [rax+78h]
0x180036c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c25  test    eax, eax
0x180036c27  js      short loc_180036C7C
0x180036c29  mov     rcx, [rsp+28h+arg_10]
0x180036c2e  lea     r8, [rsp+28h+pv]
0x180036c33  mov     [rsp+28h+pv], rbx
0x180036c38  mov     edx, 80028000h
0x180036c3d  mov     rax, [rcx]
0x180036c40  mov     rax, [rax+28h]
0x180036c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c49  test    eax, eax
0x180036c4b  js      short loc_180036C6B
0x180036c4d  mov     rdx, [rsp+28h+pv]
0x180036c52  mov     rcx, rdi
0x180036c55  call    cs:__imp_PathComparePaths
0x180036c5b  mov     rcx, [rsp+28h+pv]; pv
0x180036c60  test    al, 0Ah
0x180036c62  setnz   bl
0x180036c65  call    cs:__imp_CoTaskMemFree
0x180036c6b  mov     rcx, [rsp+28h+arg_10]
0x180036c70  mov     rdx, [rcx]
0x180036c73  mov     rax, [rdx+10h]
0x180036c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c7c  mov     eax, ebx
0x180036c7e  mov     rbx, [rsp+28h+arg_0]
0x180036c83  add     rsp, 20h
0x180036c87  pop     rdi
0x180036c88  retn
```
