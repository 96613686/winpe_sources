# VFreeSinglePluginEntry(_OEM_PLUGIN_ENTRY *,BPluginRequestType)

- ea: `0x180031b40`
- end: `0x180031c67`
- name: `?VFreeSinglePluginEntry@@YAXPEAU_OEM_PLUGIN_ENTRY@@W4BPluginRequestType@@@Z`
- size: `295`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003148c`
- `0x180031a74`

## callees

- `0x180031b40`
- `0x18005f010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180031bed`
- `KERNEL32!FreeLibrary` at `0x180031bed`
- `KERNEL32!GetProcAddress` at `0x180031bc2`
- `KERNEL32!GetProcAddress` at `0x180031bc2`
- `KERNEL32!LocalFree` at `0x180031c09`
- `KERNEL32!LocalFree` at `0x180031c1e`
- `KERNEL32!LocalFree` at `0x180031c33`
- `KERNEL32!LocalFree` at `0x180031c09`
- `KERNEL32!LocalFree` at `0x180031c1e`
- `KERNEL32!LocalFree` at `0x180031c33`

## string_xrefs

- `0x180031bb8`: `DllCanUnloadNow`

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
0x180031b40  mov     [rsp+arg_0], rbx
0x180031b45  mov     [rsp+arg_8], rsi
0x180031b4a  push    rdi
0x180031b4b  sub     rsp, 20h
0x180031b4f  cmp     qword ptr [rcx+20h], 0
0x180031b54  mov     rbx, rcx
0x180031b57  jz      loc_180031C01
0x180031b5d  mov     rcx, [rcx+48h]
0x180031b61  test    rcx, rcx
0x180031b64  jz      short loc_180031BE3
0x180031b66  mov     rax, [rbx+50h]
0x180031b6a  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data1
0x180031b71  jnz     short loc_180031B80
0x180031b73  mov     rax, [rbx+58h]
0x180031b77  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data4
0x180031b7e  jz      short loc_180031B9A
0x180031b80  mov     rax, [rbx+50h]
0x180031b84  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x180031b8b  jnz     short loc_180031BA6
0x180031b8d  mov     rax, [rbx+58h]
0x180031b91  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x180031b98  jnz     short loc_180031BA6
0x180031b9a  mov     rax, [rcx]
0x180031b9d  mov     rax, [rax+10h]
0x180031ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ba6  mov     esi, [rbx+30h]
0x180031ba9  test    sil, 10h
0x180031bad  jnz     short loc_180031BF9
0x180031baf  mov     rdi, [rbx+20h]
0x180031bb3  test    rdi, rdi
0x180031bb6  jz      short loc_180031BF9
0x180031bb8  lea     rdx, aDllcanunloadno; "DllCanUnloadNow"
0x180031bbf  mov     rcx, rdi; hModule
0x180031bc2  call    cs:__imp_GetProcAddress
0x180031bc9  nop     dword ptr [rax+rax+00h]
0x180031bce  test    rax, rax
0x180031bd1  jz      short loc_180031BF9
0x180031bd3  test    sil, 40h
0x180031bd7  jnz     short loc_180031BDE
0x180031bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031bde  mov     rcx, rdi
0x180031be1  jmp     short loc_180031BED
0x180031be3  test    byte ptr [rbx+30h], 10h
0x180031be7  jnz     short loc_180031BF9
0x180031be9  mov     rcx, [rbx+20h]; hLibModule
0x180031bed  call    cs:__imp_FreeLibrary
0x180031bf4  nop     dword ptr [rax+rax+00h]
0x180031bf9  mov     qword ptr [rbx+20h], 0
0x180031c01  mov     rcx, [rbx]; hMem
0x180031c04  test    rcx, rcx
0x180031c07  jz      short loc_180031C15
0x180031c09  call    cs:__imp_LocalFree
0x180031c10  nop     dword ptr [rax+rax+00h]
0x180031c15  mov     rcx, [rbx+8]; hMem
0x180031c19  test    rcx, rcx
0x180031c1c  jz      short loc_180031C2A
0x180031c1e  call    cs:__imp_LocalFree
0x180031c25  nop     dword ptr [rax+rax+00h]
0x180031c2a  mov     rcx, [rbx+10h]; hMem
0x180031c2e  test    rcx, rcx
0x180031c31  jz      short loc_180031C3F
0x180031c33  call    cs:__imp_LocalFree
0x180031c3a  nop     dword ptr [rax+rax+00h]
0x180031c3f  mov     rsi, [rsp+28h+arg_8]
0x180031c44  mov     qword ptr [rbx], 0
0x180031c4b  mov     qword ptr [rbx+8], 0
0x180031c53  mov     qword ptr [rbx+10h], 0
0x180031c5b  mov     rbx, [rsp+28h+arg_0]
0x180031c60  add     rsp, 20h
0x180031c64  pop     rdi
0x180031c65  retn
```
