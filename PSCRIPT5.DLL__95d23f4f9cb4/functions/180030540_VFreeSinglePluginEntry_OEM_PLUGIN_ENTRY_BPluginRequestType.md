# VFreeSinglePluginEntry(_OEM_PLUGIN_ENTRY *,BPluginRequestType)

- ea: `0x180030540`
- end: `0x180030648`
- name: `?VFreeSinglePluginEntry@@YAXPEAU_OEM_PLUGIN_ENTRY@@W4BPluginRequestType@@@Z`
- size: `264`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002fea0`
- `0x180030480`

## callees

- `0x180030540`
- `0x18005d010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800305e7`
- `KERNEL32!FreeLibrary` at `0x1800305e7`
- `KERNEL32!GetProcAddress` at `0x1800305c2`
- `KERNEL32!GetProcAddress` at `0x1800305c2`
- `KERNEL32!LocalFree` at `0x1800305fd`
- `KERNEL32!LocalFree` at `0x18003060c`
- `KERNEL32!LocalFree` at `0x18003061b`
- `KERNEL32!LocalFree` at `0x1800305fd`
- `KERNEL32!LocalFree` at `0x18003060c`
- `KERNEL32!LocalFree` at `0x18003061b`

## string_xrefs

- `0x1800305b8`: `DllCanUnloadNow`

## pseudocode

```c
void __fastcall VFreeSinglePluginEntry(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // esi
  HMODULE v4; // rdi
  void (*ProcAddress)(void); // rax
  HMODULE v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  if ( *(_QWORD *)(a1 + 32) )
  {
    v2 = *(_QWORD *)(a1 + 72);
    if ( v2 )
    {
      if ( *(_QWORD *)(a1 + 80) == *(_QWORD *)&IID_IPrintOemPS.Data1
        && *(_QWORD *)(a1 + 88) == *(_QWORD *)IID_IPrintOemPS.Data4
        || *(_QWORD *)(a1 + 80) == *(_QWORD *)&IID_IPrintOemPS2.Data1
        && *(_QWORD *)(a1 + 88) == *(_QWORD *)IID_IPrintOemPS2.Data4 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
      }
      v3 = *(_DWORD *)(a1 + 48);
      if ( (v3 & 0x10) != 0 )
        goto LABEL_17;
      v4 = *(HMODULE *)(a1 + 32);
      if ( !v4 )
        goto LABEL_17;
      ProcAddress = (void (*)(void))GetProcAddress(*(HMODULE *)(a1 + 32), "DllCanUnloadNow");
      if ( !ProcAddress )
        goto LABEL_17;
      if ( (v3 & 0x40) == 0 )
        ProcAddress();
      v6 = v4;
    }
    else
    {
      if ( (*(_BYTE *)(a1 + 48) & 0x10) != 0 )
      {
LABEL_17:
        *(_QWORD *)(a1 + 32) = 0;
        goto LABEL_18;
      }
      v6 = *(HMODULE *)(a1 + 32);
    }
    FreeLibrary(v6);
    goto LABEL_17;
  }
LABEL_18:
  if ( *(_QWORD *)a1 )
    LocalFree(*(HLOCAL *)a1);
  v7 = *(void **)(a1 + 8);
  if ( v7 )
    LocalFree(v7);
  v8 = *(void **)(a1 + 16);
  if ( v8 )
    LocalFree(v8);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180030540  mov     [rsp+arg_0], rbx
0x180030545  mov     [rsp+arg_8], rsi
0x18003054a  push    rdi
0x18003054b  sub     rsp, 20h
0x18003054f  cmp     qword ptr [rcx+20h], 0
0x180030554  mov     rbx, rcx
0x180030557  jz      loc_1800305F5
0x18003055d  mov     rcx, [rcx+48h]
0x180030561  test    rcx, rcx
0x180030564  jz      short loc_1800305DD
0x180030566  mov     rax, [rbx+50h]
0x18003056a  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data1
0x180030571  jnz     short loc_180030580
0x180030573  mov     rax, [rbx+58h]
0x180030577  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data4
0x18003057e  jz      short loc_18003059A
0x180030580  mov     rax, [rbx+50h]
0x180030584  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x18003058b  jnz     short loc_1800305A6
0x18003058d  mov     rax, [rbx+58h]
0x180030591  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x180030598  jnz     short loc_1800305A6
0x18003059a  mov     rax, [rcx]
0x18003059d  mov     rax, [rax+10h]
0x1800305a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305a6  mov     esi, [rbx+30h]
0x1800305a9  test    sil, 10h
0x1800305ad  jnz     short loc_1800305ED
0x1800305af  mov     rdi, [rbx+20h]
0x1800305b3  test    rdi, rdi
0x1800305b6  jz      short loc_1800305ED
0x1800305b8  lea     rdx, aDllcanunloadno; "DllCanUnloadNow"
0x1800305bf  mov     rcx, rdi; hModule
0x1800305c2  call    cs:__imp_GetProcAddress
0x1800305c8  test    rax, rax
0x1800305cb  jz      short loc_1800305ED
0x1800305cd  test    sil, 40h
0x1800305d1  jnz     short loc_1800305D8
0x1800305d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305d8  mov     rcx, rdi
0x1800305db  jmp     short loc_1800305E7
0x1800305dd  test    byte ptr [rbx+30h], 10h
0x1800305e1  jnz     short loc_1800305ED
0x1800305e3  mov     rcx, [rbx+20h]; hLibModule
0x1800305e7  call    cs:__imp_FreeLibrary
0x1800305ed  mov     qword ptr [rbx+20h], 0
0x1800305f5  mov     rcx, [rbx]; hMem
0x1800305f8  test    rcx, rcx
0x1800305fb  jz      short loc_180030603
0x1800305fd  call    cs:__imp_LocalFree
0x180030603  mov     rcx, [rbx+8]; hMem
0x180030607  test    rcx, rcx
0x18003060a  jz      short loc_180030612
0x18003060c  call    cs:__imp_LocalFree
0x180030612  mov     rcx, [rbx+10h]; hMem
0x180030616  test    rcx, rcx
0x180030619  jz      short loc_180030621
0x18003061b  call    cs:__imp_LocalFree
0x180030621  mov     rsi, [rsp+28h+arg_8]
0x180030626  mov     qword ptr [rbx], 0
0x18003062d  mov     qword ptr [rbx+8], 0
0x180030635  mov     qword ptr [rbx+10h], 0
0x18003063d  mov     rbx, [rsp+28h+arg_0]
0x180030642  add     rsp, 20h
0x180030646  pop     rdi
0x180030647  retn
```
