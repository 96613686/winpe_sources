# Registry::TryGetValue<uint>(Registry::Key const &,std::basic_string_view<ushort,std::char_traits<ushort>> const &,std::basic_string_view<ushort,std::char_traits<ushort>> const &,uint &)

- ea: `0x18000c710`
- end: `0x18000c778`
- name: `??$TryGetValue@I@Registry@@YA_NAEBUKey@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@1AEAI@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000cc78`

## callees

- `0x18000c710`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c74b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c74b`

## pseudocode

```c
char __fastcall Registry::TryGetValue<unsigned int>(__int64 a1, LPCWSTR *a2, LPCWSTR *a3, _DWORD *a4)
{
  LSTATUS ValueW; // eax
  bool v6; // sf
  DWORD v8; // [rsp+50h] [rbp+8h] BYREF
  int v9; // [rsp+58h] [rbp+10h] BYREF

  v8 = 4;
  ValueW = RegGetValueW(*(HKEY *)(a1 + 8), *a2, *a3, 0x18u, 0, &v9, &v8);
  v6 = ValueW < 0;
  if ( ValueW > 0 )
    v6 = 1;
  if ( v6 )
    return 0;
  *a4 = v9;
  return 1;
}

```

## disassembly

```asm
0x18000c710  mov     r11, rsp
0x18000c713  push    rbx
0x18000c714  sub     rsp, 40h
0x18000c718  mov     rbx, r9
0x18000c71b  mov     [rsp+48h+arg_0], 4
0x18000c723  lea     rax, [r11+8]
0x18000c727  mov     [r11-18h], rax
0x18000c72b  lea     rax, [r11+10h]
0x18000c72f  mov     [r11-20h], rax
0x18000c733  mov     qword ptr [r11-28h], 0
0x18000c73b  mov     r9d, 18h; dwFlags
0x18000c741  mov     r8, [r8]; lpValue
0x18000c744  mov     rdx, [rdx]; lpSubKey
0x18000c747  mov     rcx, [rcx+8]; hkey
0x18000c74b  call    cs:__imp_RegGetValueW
0x18000c751  test    eax, eax
0x18000c753  jle     short loc_18000C75F
0x18000c755  movzx   eax, ax
0x18000c758  or      eax, 80070000h
0x18000c75d  test    eax, eax
0x18000c75f  jns     short loc_18000C765
0x18000c761  xor     al, al
0x18000c763  jmp     short loc_18000C771
0x18000c765  mov     eax, [rsp+48h+arg_8]
0x18000c769  mov     [rbx], eax
0x18000c76b  mov     al, 1
0x18000c76d  jmp     short loc_18000C771
0x18000c76f  xor     al, al
0x18000c771  add     rsp, 40h
0x18000c775  pop     rbx
0x18000c776  retn
```
