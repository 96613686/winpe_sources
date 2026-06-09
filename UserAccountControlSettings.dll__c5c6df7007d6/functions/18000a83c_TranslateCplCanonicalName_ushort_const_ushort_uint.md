# TranslateCplCanonicalName(ushort const *,ushort *,uint)

- ea: `0x18000a83c`
- end: `0x18000a8da`
- name: `?TranslateCplCanonicalName@@YAJPEBGPEAGI@Z`
- size: `158`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a278`

## callees

- `0x180006af0`
- `0x18000a83c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a876`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a876`

## pseudocode

```c
__int64 __fastcall TranslateCplCanonicalName(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  int v4; // ebx
  LPVOID v6; // [rsp+58h] [rbp+20h] BYREF

  v6 = 0;
  v4 = CoCreateInstance(&CLSID_OpenControlPanel, 0, 1u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, &v6);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, unsigned __int16 *, __int64))(*(_QWORD *)v6 + 32LL))(
           v6,
           a1,
           a2,
           260);
    if ( v4 < 0 )
      v4 = StringCchCopyW(a2, 0x104u, a1);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000a83c  mov     r11, rsp
0x18000a83f  mov     [r11+8], rbx
0x18000a843  mov     [r11+10h], rsi
0x18000a847  push    rdi
0x18000a848  sub     rsp, 30h
0x18000a84c  mov     rdi, rdx
0x18000a84f  mov     qword ptr [r11+20h], 0
0x18000a857  xor     edx, edx; pUnkOuter
0x18000a859  lea     rax, [r11+20h]
0x18000a85d  mov     rsi, rcx
0x18000a860  mov     [r11-18h], rax
0x18000a864  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18000a86b  lea     rcx, CLSID_OpenControlPanel; rclsid
0x18000a872  lea     r8d, [rdx+1]; dwClsContext
0x18000a876  call    cs:__imp_CoCreateInstance
0x18000a87c  mov     ebx, eax
0x18000a87e  test    eax, eax
0x18000a880  js      short loc_18000A8C8
0x18000a882  mov     rcx, [rsp+38h+arg_18]
0x18000a887  mov     r9d, 104h
0x18000a88d  mov     r8, rdi
0x18000a890  mov     rdx, rsi
0x18000a893  mov     rax, [rcx]
0x18000a896  mov     rax, [rax+20h]
0x18000a89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a89f  mov     ebx, eax
0x18000a8a1  test    eax, eax
0x18000a8a3  jns     short loc_18000A8B7
0x18000a8a5  mov     r8, rsi; unsigned __int16 *
0x18000a8a8  mov     edx, 104h; unsigned __int64
0x18000a8ad  mov     rcx, rdi; unsigned __int16 *
0x18000a8b0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a8b5  mov     ebx, eax
0x18000a8b7  mov     rcx, [rsp+38h+arg_18]
0x18000a8bc  mov     rax, [rcx]
0x18000a8bf  mov     rax, [rax+10h]
0x18000a8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8c8  mov     rsi, [rsp+38h+arg_8]
0x18000a8cd  mov     eax, ebx
0x18000a8cf  mov     rbx, [rsp+38h+arg_0]
0x18000a8d4  add     rsp, 30h
0x18000a8d8  pop     rdi
0x18000a8d9  retn
```
