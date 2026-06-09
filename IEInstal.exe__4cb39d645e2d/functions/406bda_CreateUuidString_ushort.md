# CreateUuidString(ushort * *)

- ea: `0x406bda`
- end: `0x406c60`
- name: `?CreateUuidString@@YGJPAPAG@Z`
- size: `134`
- prototype: `RPC_STATUS __thiscall(BSTR *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x4035e8`
- `0x407b9f`

## callees

- `0x406bda`
- `0x40cb60`

## import_xrefs

- `OLEAUT32!__imp__SysAllocString@4` at `0x406c1c`
- `OLEAUT32!__imp__SysAllocString@4` at `0x406c1c`
- `RPCRT4!RpcStringFreeW` at `0x406c33`
- `RPCRT4!RpcStringFreeW` at `0x406c33`
- `RPCRT4!UuidCreate` at `0x406bfa`
- `RPCRT4!UuidCreate` at `0x406bfa`
- `RPCRT4!UuidToStringW` at `0x406c0f`
- `RPCRT4!UuidToStringW` at `0x406c0f`

## pseudocode

```c
RPC_STATUS __thiscall CreateUuidString(BSTR *this)
{
  unsigned int v2; // esi
  RPC_STATUS v3; // eax
  BSTR v4; // eax
  RPC_WSTR StringUuid; // [esp+8h] [ebp-18h] BYREF
  UUID Uuid; // [esp+Ch] [ebp-14h] BYREF

  v2 = 0;
  if ( !this )
    return -2147024809;
  v3 = UuidCreate(&Uuid);
  if ( v3 || (StringUuid = 0, (v3 = UuidToStringW(&Uuid, &StringUuid)) != 0) )
  {
    v2 = (unsigned __int16)v3 | 0x80070000;
    if ( v3 <= 0 )
      return v3;
  }
  else
  {
    v4 = SysAllocString(StringUuid);
    if ( v4 )
      *this = v4;
    else
      v2 = -2147024882;
    RpcStringFreeW(&StringUuid);
  }
  return v2;
}

```

## disassembly

```asm
0x406bda  mov     edi, edi
0x406bdc  push    ebp
0x406bdd  mov     ebp, esp
0x406bdf  sub     esp, 18h
0x406be2  mov     eax, ___security_cookie
0x406be7  xor     eax, ebp
0x406be9  mov     [ebp+var_4], eax
0x406bec  push    esi
0x406bed  push    edi
0x406bee  mov     edi, ecx
0x406bf0  xor     esi, esi
0x406bf2  test    edi, edi
0x406bf4  jz      short loc_406C4B
0x406bf6  lea     eax, [ebp+Uuid]
0x406bf9  push    eax; Uuid
0x406bfa  call    ds:__imp__UuidCreate@4; UuidCreate(x)
0x406c00  test    eax, eax
0x406c02  jnz     short loc_406C3B
0x406c04  lea     eax, [ebp+StringUuid]
0x406c07  mov     [ebp+StringUuid], esi
0x406c0a  push    eax; StringUuid
0x406c0b  lea     eax, [ebp+Uuid]
0x406c0e  push    eax; Uuid
0x406c0f  call    ds:__imp__UuidToStringW@8; UuidToStringW(x,x)
0x406c15  test    eax, eax
0x406c17  jnz     short loc_406C3B
0x406c19  push    [ebp+StringUuid]; psz
0x406c1c  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x406c22  test    eax, eax
0x406c24  jz      short loc_406C2A
0x406c26  mov     [edi], eax
0x406c28  jmp     short loc_406C2F
0x406c2a  mov     esi, 8007000Eh
0x406c2f  lea     eax, [ebp+StringUuid]
0x406c32  push    eax; String
0x406c33  call    ds:__imp__RpcStringFreeW@4; RpcStringFreeW(x)
0x406c39  jmp     short loc_406C50
0x406c3b  movzx   esi, ax
0x406c3e  or      esi, 80070000h
0x406c44  test    eax, eax
0x406c46  cmovle  esi, eax
0x406c49  jmp     short loc_406C50
0x406c4b  mov     esi, 80070057h
0x406c50  mov     ecx, [ebp+var_4]
0x406c53  mov     eax, esi
0x406c55  pop     edi
0x406c56  xor     ecx, ebp; StackCookie
0x406c58  pop     esi
0x406c59  call    @__security_check_cookie@4; __security_check_cookie(x)
0x406c5e  leave
0x406c5f  retn
```
