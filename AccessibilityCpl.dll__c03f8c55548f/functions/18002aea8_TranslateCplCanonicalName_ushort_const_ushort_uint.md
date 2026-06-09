# TranslateCplCanonicalName(ushort const *,ushort *,uint)

- ea: `0x18002aea8`
- end: `0x18002af46`
- name: `?TranslateCplCanonicalName@@YAJPEBGPEAGI@Z`
- size: `158`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a940`

## callees

- `0x18001a67c`
- `0x18002aea8`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002aee2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002aee2`

## pseudocode

```c
__int64 __fastcall TranslateCplCanonicalName(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  HRESULT v4; // ebx
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
0x18002aea8  mov     r11, rsp
0x18002aeab  mov     [r11+8], rbx
0x18002aeaf  mov     [r11+10h], rsi
0x18002aeb3  push    rdi
0x18002aeb4  sub     rsp, 30h
0x18002aeb8  mov     rdi, rdx
0x18002aebb  mov     qword ptr [r11+20h], 0
0x18002aec3  xor     edx, edx; pUnkOuter
0x18002aec5  lea     rax, [r11+20h]
0x18002aec9  mov     rsi, rcx
0x18002aecc  mov     [r11-18h], rax
0x18002aed0  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18002aed7  lea     rcx, CLSID_OpenControlPanel; rclsid
0x18002aede  lea     r8d, [rdx+1]; dwClsContext
0x18002aee2  call    cs:__imp_CoCreateInstance
0x18002aee8  mov     ebx, eax
0x18002aeea  test    eax, eax
0x18002aeec  js      short loc_18002AF34
0x18002aeee  mov     rcx, [rsp+38h+arg_18]
0x18002aef3  mov     r9d, 104h
0x18002aef9  mov     r8, rdi
0x18002aefc  mov     rdx, rsi
0x18002aeff  mov     rax, [rcx]
0x18002af02  mov     rax, [rax+20h]
0x18002af06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af0b  mov     ebx, eax
0x18002af0d  test    eax, eax
0x18002af0f  jns     short loc_18002AF23
0x18002af11  mov     r8, rsi; unsigned __int16 *
0x18002af14  mov     edx, 104h; unsigned __int64
0x18002af19  mov     rcx, rdi; unsigned __int16 *
0x18002af1c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002af21  mov     ebx, eax
0x18002af23  mov     rcx, [rsp+38h+arg_18]
0x18002af28  mov     rax, [rcx]
0x18002af2b  mov     rax, [rax+10h]
0x18002af2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af34  mov     rsi, [rsp+38h+arg_8]
0x18002af39  mov     eax, ebx
0x18002af3b  mov     rbx, [rsp+38h+arg_0]
0x18002af40  add     rsp, 30h
0x18002af44  pop     rdi
0x18002af45  retn
```
