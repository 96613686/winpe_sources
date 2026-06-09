# SRCacheContext::SetField(ushort const *,ushort const *)

- ea: `0x18000c7f0`
- end: `0x18000c8a6`
- name: `?SetField@SRCacheContext@@QEAAJPEBG0@Z`
- size: `182`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, const BYTE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d390`

## callees

- `0x18000940c`
- `0x18000c7f0`
- `0x18000ec40`
- `0x18000fdf0`

## string_xrefs

- `0x18000c817`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000c858`: `onecore\base\appmodel\common\registrykey.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext::SetField(HKEY *this, const unsigned __int16 *a2, const BYTE *a3)
{
  const BYTE *v3; // r11
  LSTATUS v6; // ebx
  __int64 v7; // rdx
  DWORD v9; // edi
  int v10; // r9d
  int v11; // eax
  unsigned int v12; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned __int64 v14; // [rsp+60h] [rbp+8h] BYREF

  v3 = a3;
  if ( !*this )
  {
    v6 = -2147019873;
    v7 = 288;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)(unsigned int)v6,
      v12);
    return (unsigned int)v6;
  }
  v9 = a3 != 0;
  v10 = 0;
  v14 = 0;
  if ( a3 )
  {
    v11 = StringCchLengthW((const unsigned __int16 *)a3, (unsigned __int64)a2, &v14);
    v6 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1ED,
        (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
        (const char *)(unsigned int)v11,
        v12);
LABEL_9:
      v7 = 291;
      goto LABEL_3;
    }
    v10 = v14 + 1;
  }
  v6 = Common::RegistryKey::SetValue(this, a2, v3, 2 * v10, v9);
  if ( v6 < 0 )
    goto LABEL_9;
  return 0;
}

```

## disassembly

```asm
0x18000c7f0  push    rbx
0x18000c7f2  push    rbp
0x18000c7f3  push    rsi
0x18000c7f4  push    rdi
0x18000c7f5  sub     rsp, 38h
0x18000c7f9  cmp     qword ptr [rcx], 0
0x18000c7fd  mov     r11, r8
0x18000c800  mov     rbp, rdx
0x18000c803  mov     rsi, rcx
0x18000c806  jnz     short loc_18000C82A
0x18000c808  mov     ebx, 8007139Fh
0x18000c80d  mov     edx, 120h; void *
0x18000c812  mov     rcx, [rsp+58h]; this
0x18000c817  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c81e  mov     r9d, ebx; char *
0x18000c821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c826  mov     eax, ebx
0x18000c828  jmp     short loc_18000C89D
0x18000c82a  xor     edi, edi
0x18000c82c  test    r11, r11
0x18000c82f  setnz   dil
0x18000c833  xor     r9d, r9d
0x18000c836  mov     [rsp+58h+arg_0], r9
0x18000c83b  test    r11, r11
0x18000c83e  jz      short loc_18000C876
0x18000c840  lea     r8, [rsp+58h+arg_0]; unsigned __int64 *
0x18000c845  mov     rcx, r11; unsigned __int16 *
0x18000c848  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000c84d  mov     ebx, eax
0x18000c84f  test    eax, eax
0x18000c851  jns     short loc_18000C86E
0x18000c853  mov     rcx, [rsp+58h]; this
0x18000c858  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\regist"...
0x18000c85f  mov     r9d, eax; char *
0x18000c862  mov     edx, 1EDh; void *
0x18000c867  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c86c  jmp     short loc_18000C891
0x18000c86e  mov     r9, [rsp+58h+arg_0]
0x18000c873  inc     r9
0x18000c876  add     r9d, r9d; unsigned int
0x18000c879  mov     [rsp+58h+var_38], edi; unsigned int
0x18000c87d  mov     r8, r11; void *
0x18000c880  mov     rdx, rbp; unsigned __int16 *
0x18000c883  mov     rcx, rsi; this
0x18000c886  call    ?SetValue@RegistryKey@Common@@QEAAJPEBGPEBXKK@Z; Common::RegistryKey::SetValue(ushort const *,void const *,ulong,ulong)
0x18000c88b  mov     ebx, eax
0x18000c88d  test    eax, eax
0x18000c88f  jns     short loc_18000C89B
0x18000c891  mov     edx, 123h
0x18000c896  jmp     loc_18000C812
0x18000c89b  xor     eax, eax
0x18000c89d  add     rsp, 38h
0x18000c8a1  pop     rdi
0x18000c8a2  pop     rsi
0x18000c8a3  pop     rbp
0x18000c8a4  pop     rbx
0x18000c8a5  retn
```
