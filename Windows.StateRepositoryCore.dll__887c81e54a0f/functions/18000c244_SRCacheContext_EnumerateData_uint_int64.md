# SRCacheContext::EnumerateData(uint,__int64 *)

- ea: `0x18000c244`
- end: `0x18000c2df`
- name: `?EnumerateData@SRCacheContext@@QEAAJIPEA_J@Z`
- size: `155`
- prototype: `__int64 __fastcall(SRCacheContext *this, unsigned int, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cd60`

## callees

- `0x180001ed0`
- `0x18000940c`
- `0x18000c244`
- `0x18000c8ac`
- `0x18000faac`

## string_xrefs

- `0x18000c295`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext::EnumerateData(SRCacheContext *this, unsigned int a2, __int64 *a3)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rdx
  struct _FILETIME *v8; // [rsp+20h] [rbp-58h]
  int v9; // [rsp+20h] [rbp-58h]
  unsigned int v10; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 v11[20]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *a3 = 0;
  v10 = 17;
  v4 = Common::RegistryKey::EnumKey(this, a2, &v10, v11, v8);
  v5 = v4;
  if ( v4 != -2147024637 )
  {
    if ( v4 < 0 )
    {
      v6 = 349;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
        (const char *)(unsigned int)v5,
        v9);
      return (unsigned int)v5;
    }
    v5 = SRCacheContext::StringToInt64(v11, a3);
    if ( v5 < 0 )
    {
      v6 = 350;
      goto LABEL_4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c244  mov     [rsp+arg_18], rbx
0x18000c249  push    rdi
0x18000c24a  sub     rsp, 70h
0x18000c24e  mov     rax, cs:__security_cookie
0x18000c255  xor     rax, rsp
0x18000c258  mov     [rsp+78h+var_18], rax
0x18000c25d  mov     rdi, r8
0x18000c260  mov     qword ptr [r8], 0
0x18000c267  lea     r8, [rsp+78h+var_48]; unsigned int *
0x18000c26c  mov     [rsp+78h+var_48], 11h
0x18000c274  lea     r9, [rsp+78h+var_40]; unsigned __int16 *
0x18000c279  call    ?EnumKey@RegistryKey@Common@@QEAAJKPEAKPEAGPEAU_FILETIME@@@Z; Common::RegistryKey::EnumKey(ulong,ulong *,ushort *,_FILETIME *)
0x18000c27e  mov     ebx, eax
0x18000c280  cmp     eax, 80070103h
0x18000c285  jz      short loc_18000C2C2
0x18000c287  test    eax, eax
0x18000c289  jns     short loc_18000C2A8
0x18000c28b  mov     edx, 15Dh; void *
0x18000c290  mov     rcx, [rsp+78h]; this
0x18000c295  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c29c  mov     r9d, ebx; char *
0x18000c29f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c2a4  mov     eax, ebx
0x18000c2a6  jmp     short loc_18000C2C4
0x18000c2a8  mov     rdx, rdi; __int64 *
0x18000c2ab  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x18000c2b0  call    ?StringToInt64@SRCacheContext@@CAJPEBGPEA_J@Z; SRCacheContext::StringToInt64(ushort const *,__int64 *)
0x18000c2b5  mov     ebx, eax
0x18000c2b7  test    eax, eax
0x18000c2b9  jns     short loc_18000C2C2
0x18000c2bb  mov     edx, 15Eh
0x18000c2c0  jmp     short loc_18000C290
0x18000c2c2  xor     eax, eax
0x18000c2c4  mov     rcx, [rsp+78h+var_18]
0x18000c2c9  xor     rcx, rsp; StackCookie
0x18000c2cc  call    __security_check_cookie
0x18000c2d1  mov     rbx, [rsp+78h+arg_18]
0x18000c2d9  add     rsp, 70h
0x18000c2dd  pop     rdi
0x18000c2de  retn
```
