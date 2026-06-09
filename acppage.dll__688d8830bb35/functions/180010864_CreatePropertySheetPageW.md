# CreatePropertySheetPageW

- ea: `0x180010864`
- end: `0x1800108f9`
- name: `CreatePropertySheetPageW`
- size: `149`
- prototype: `HPROPSHEETPAGE __stdcall(LPCPROPSHEETPAGEW constPropSheetPagePointer)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a830`

## callees

- `0x1800105f8`
- `0x180010864`
- `0x180010b0c`
- `0x180017010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x1800108e5`
- `KERNEL32!DeactivateActCtx` at `0x1800108e5`

## string_xrefs

- `0x180010893`: `CreatePropertySheetPageW`

## pseudocode

```c
HPROPSHEETPAGE __stdcall CreatePropertySheetPageW(LPCPROPSHEETPAGEW constPropSheetPagePointer)
{
  struct _PSP *v2; // rdi
  __int64 (__fastcall *v3)(LPCPROPSHEETPAGEW); // rax
  ULONG_PTR ulCookie; // [rsp+38h] [rbp+10h] BYREF

  ulCookie = 0;
  v2 = 0;
  SHActivateContext(&ulCookie);
  v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_1800203E8;
  if ( qword_1800203E8 == -1 )
  {
    GetProcFromComCtl32(&qword_1800203E8, "CreatePropertySheetPageW");
    v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_1800203E8;
  }
  if ( v3 )
  {
    if ( constPropSheetPagePointer->dwSize > 0x58 )
    {
      constPropSheetPagePointer->dwFlags |= 0x4000u;
      constPropSheetPagePointer->hActCtx = g_hActCtx;
      v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_1800203E8;
    }
    v2 = (struct _PSP *)v3(constPropSheetPagePointer);
  }
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  return v2;
}

```

## disassembly

```asm
0x180010864  mov     [rsp+arg_0], rbx
0x180010869  push    rdi
0x18001086a  sub     rsp, 20h
0x18001086e  mov     rbx, rcx
0x180010871  mov     [rsp+28h+ulCookie], 0
0x18001087a  lea     rcx, [rsp+28h+ulCookie]
0x18001087f  xor     edi, edi
0x180010881  call    SHActivateContext
0x180010886  mov     rax, cs:qword_1800203E8
0x18001088d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010891  jnz     short loc_1800108AD
0x180010893  lea     rdx, aCreateproperty; "CreatePropertySheetPageW"
0x18001089a  lea     rcx, qword_1800203E8
0x1800108a1  call    _GetProcFromComCtl32
0x1800108a6  mov     rax, cs:qword_1800203E8
0x1800108ad  test    rax, rax
0x1800108b0  jz      short loc_1800108D9
0x1800108b2  cmp     dword ptr [rbx], 58h ; 'X'
0x1800108b5  jbe     short loc_1800108CE
0x1800108b7  bts     dword ptr [rbx+4], 0Eh
0x1800108bc  mov     rax, cs:g_hActCtx
0x1800108c3  mov     [rbx+58h], rax
0x1800108c7  mov     rax, cs:qword_1800203E8
0x1800108ce  mov     rcx, rbx
0x1800108d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108d6  mov     rdi, rax
0x1800108d9  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x1800108de  test    rdx, rdx
0x1800108e1  jz      short loc_1800108EB
0x1800108e3  xor     ecx, ecx; dwFlags
0x1800108e5  call    cs:__imp_DeactivateActCtx
0x1800108eb  mov     rbx, [rsp+28h+arg_0]
0x1800108f0  mov     rax, rdi
0x1800108f3  add     rsp, 20h
0x1800108f7  pop     rdi
0x1800108f8  retn
```
