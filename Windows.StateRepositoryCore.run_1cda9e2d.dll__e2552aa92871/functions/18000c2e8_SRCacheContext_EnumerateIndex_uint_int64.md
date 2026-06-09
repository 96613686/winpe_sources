# SRCacheContext::EnumerateIndex(uint,__int64 *)

- ea: `0x18000c2e8`
- end: `0x18000c37c`
- name: `?EnumerateIndex@SRCacheContext@@QEAAJIPEA_J@Z`
- size: `148`
- prototype: `int(SRCacheContext *__hidden this, unsigned int, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cda0`

## callees

- `0x180001ed0`
- `0x18000940c`
- `0x18000c2e8`
- `0x18000c8ac`
- `0x18000faac`

## string_xrefs

- `0x18000c332`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext::EnumerateIndex(HKEY *this, DWORD a2, __int64 *a3)
{
  int v4; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-58h]
  unsigned int v8; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 v9[20]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *a3 = 0;
  v8 = 17;
  v4 = Common::RegistryKey::EnumKey(this, a2, &v8, v9);
  if ( v4 < 0 )
  {
    v5 = 361;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)(unsigned int)v4,
      v7);
    return (unsigned int)v4;
  }
  v4 = SRCacheContext::StringToInt64(v9, a3);
  if ( v4 < 0 )
  {
    v5 = 362;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c2e8  mov     [rsp+arg_18], rbx
0x18000c2ed  push    rdi
0x18000c2ee  sub     rsp, 70h
0x18000c2f2  mov     rax, cs:__security_cookie
0x18000c2f9  xor     rax, rsp
0x18000c2fc  mov     [rsp+78h+var_18], rax
0x18000c301  mov     rdi, r8
0x18000c304  mov     qword ptr [r8], 0
0x18000c30b  lea     r8, [rsp+78h+var_48]; unsigned int *
0x18000c310  mov     [rsp+78h+var_48], 11h
0x18000c318  lea     r9, [rsp+78h+var_40]; unsigned __int16 *
0x18000c31d  call    ?EnumKey@RegistryKey@Common@@QEAAJKPEAKPEAGPEAU_FILETIME@@@Z; Common::RegistryKey::EnumKey(ulong,ulong *,ushort *,_FILETIME *)
0x18000c322  mov     ebx, eax
0x18000c324  test    eax, eax
0x18000c326  jns     short loc_18000C345
0x18000c328  mov     edx, 169h; void *
0x18000c32d  mov     rcx, [rsp+78h]; this
0x18000c332  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c339  mov     r9d, ebx; char *
0x18000c33c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c341  mov     eax, ebx
0x18000c343  jmp     short loc_18000C361
0x18000c345  mov     rdx, rdi; __int64 *
0x18000c348  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x18000c34d  call    ?StringToInt64@SRCacheContext@@CAJPEBGPEA_J@Z; SRCacheContext::StringToInt64(ushort const *,__int64 *)
0x18000c352  mov     ebx, eax
0x18000c354  test    eax, eax
0x18000c356  jns     short loc_18000C35F
0x18000c358  mov     edx, 16Ah
0x18000c35d  jmp     short loc_18000C32D
0x18000c35f  xor     eax, eax
0x18000c361  mov     rcx, [rsp+78h+var_18]
0x18000c366  xor     rcx, rsp; StackCookie
0x18000c369  call    __security_check_cookie
0x18000c36e  mov     rbx, [rsp+78h+arg_18]
0x18000c376  add     rsp, 70h
0x18000c37a  pop     rdi
0x18000c37b  retn
```
