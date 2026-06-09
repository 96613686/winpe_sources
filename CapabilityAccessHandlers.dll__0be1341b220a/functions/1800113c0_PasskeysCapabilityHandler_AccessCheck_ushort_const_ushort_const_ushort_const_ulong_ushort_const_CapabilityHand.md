# PasskeysCapabilityHandler::AccessCheck(ushort const *,ushort const *,ushort const *,ulong,ushort const *,CapabilityHandlerAccessStatus *)

- ea: `0x1800113c0`
- end: `0x180011427`
- name: `?AccessCheck@PasskeysCapabilityHandler@@UEAAJPEBG00K0PEAW4CapabilityHandlerAccessStatus@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(PasskeysCapabilityHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, wchar_t *String1, enum CapabilityHandlerAccessStatus *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800113c0`
- `0x180013634`

## pseudocode

```c
__int64 __fastcall PasskeysCapabilityHandler::AccessCheck(
        PasskeysCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        wchar_t *String1,
        enum CapabilityHandlerAccessStatus *a7)
{
  if ( !a2 || !a3 || !a7 )
    return 2147942487LL;
  *(_DWORD *)a7 = 1;
  if ( String1 && !wcscmp_0(String1, L"windows.immersivecontrolpanel_cw5n1h2txyewy") )
    *(_DWORD *)a7 = 2;
  else
    *(_DWORD *)a7 = a4 != 0;
  return 0;
}

```

## disassembly

```asm
0x1800113c0  mov     [rsp+arg_0], rbx
0x1800113c5  push    rdi
0x1800113c6  sub     rsp, 20h
0x1800113ca  mov     rdi, r9
0x1800113cd  test    rdx, rdx
0x1800113d0  jz      short loc_180011417
0x1800113d2  test    r8, r8
0x1800113d5  jz      short loc_180011417
0x1800113d7  mov     rbx, [rsp+28h+arg_30]
0x1800113dc  test    rbx, rbx
0x1800113df  jz      short loc_180011417
0x1800113e1  mov     rcx, [rsp+28h+String1]; String1
0x1800113e6  mov     dword ptr [rbx], 1
0x1800113ec  test    rcx, rcx
0x1800113ef  jz      short loc_18001140B
0x1800113f1  lea     rdx, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x1800113f8  call    wcscmp_0
0x1800113fd  test    eax, eax
0x1800113ff  jnz     short loc_18001140B
0x180011401  mov     dword ptr [rbx], 2
0x180011407  xor     eax, eax
0x180011409  jmp     short loc_18001141C
0x18001140b  xor     eax, eax
0x18001140d  test    rdi, rdi
0x180011410  setnz   al
0x180011413  mov     [rbx], eax
0x180011415  jmp     short loc_180011407
0x180011417  mov     eax, 80070057h
0x18001141c  mov     rbx, [rsp+28h+arg_0]
0x180011421  add     rsp, 20h
0x180011425  pop     rdi
0x180011426  retn
```
