# CNetworkItemFactory::s_CreateItem(ushort const *,CNetworkItem *)

- ea: `0x18000542c`
- end: `0x1800054a8`
- name: `?s_CreateItem@CNetworkItemFactory@@CAPEAVIDToNetworkItemRecord@@PEBGPEAVCNetworkItem@@@Z`
- size: `124`
- prototype: `LPWSTR *__fastcall(const unsigned __int16 *, WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003d28`

## callees

- `0x18000542c`
- `0x1800070c8`
- `0x18000b010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005494`
- `ole32!CoTaskMemFree` at `0x180005494`
- `SHLWAPI!SHStrDupW` at `0x180005445`
- `SHLWAPI!SHStrDupW` at `0x180005445`

## pseudocode

```c
LPWSTR *__fastcall CNetworkItemFactory::s_CreateItem(const unsigned __int16 *a1, WCHAR *a2)
{
  LPWSTR *v3; // rbx
  LPWSTR *v4; // rax
  LPWSTR ppwsz; // [rsp+40h] [rbp+18h] BYREF
  LPWSTR *v7; // [rsp+48h] [rbp+20h]

  v3 = 0;
  ppwsz = 0;
  if ( SHStrDupW(a1, &ppwsz) >= 0 )
  {
    v4 = (LPWSTR *)operator new(0x18u);
    v3 = v4;
    v7 = v4;
    if ( v4 )
    {
      *v4 = ppwsz;
      v4[1] = a2;
      (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)a2 + 8LL))(a2);
      *((_DWORD *)v3 + 4) = 1;
    }
    else
    {
      v3 = 0;
    }
    if ( !v3 )
      CoTaskMemFree(ppwsz);
  }
  return v3;
}

```

## disassembly

```asm
0x18000542c  mov     [rsp+arg_0], rbx
0x180005431  push    rdi
0x180005432  sub     rsp, 20h
0x180005436  mov     rdi, rdx
0x180005439  xor     ebx, ebx
0x18000543b  mov     [rsp+28h+ppwsz], rbx
0x180005440  lea     rdx, [rsp+28h+ppwsz]; ppwsz
0x180005445  call    cs:__imp_SHStrDupW
0x18000544b  test    eax, eax
0x18000544d  js      short loc_18000549A
0x18000544f  lea     ecx, [rbx+18h]; unsigned __int64
0x180005452  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005457  mov     rbx, rax
0x18000545a  mov     [rsp+28h+arg_18], rax
0x18000545f  test    rax, rax
0x180005462  jz      short loc_180005488
0x180005464  mov     rax, [rsp+28h+ppwsz]
0x180005469  mov     [rbx], rax
0x18000546c  mov     [rbx+8], rdi
0x180005470  mov     rax, [rdi]
0x180005473  mov     rcx, rdi
0x180005476  mov     rax, [rax+8]
0x18000547a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000547f  mov     dword ptr [rbx+10h], 1
0x180005486  jmp     short loc_18000548A
0x180005488  xor     ebx, ebx
0x18000548a  test    rbx, rbx
0x18000548d  jnz     short loc_18000549A
0x18000548f  mov     rcx, [rsp+28h+ppwsz]; pv
0x180005494  call    cs:__imp_CoTaskMemFree
0x18000549a  mov     rax, rbx
0x18000549d  mov     rbx, [rsp+28h+arg_0]
0x1800054a2  add     rsp, 20h
0x1800054a6  pop     rdi
0x1800054a7  retn
```
