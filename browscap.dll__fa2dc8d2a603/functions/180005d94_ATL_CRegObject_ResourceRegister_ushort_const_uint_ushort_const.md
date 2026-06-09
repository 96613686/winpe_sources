# ATL::CRegObject::ResourceRegister(ushort const *,uint,ushort const *)

- ea: `0x180005d94`
- end: `0x180005eaa`
- name: `?ResourceRegister@CRegObject@ATL@@QEAAJPEBGI0@Z`
- size: `278`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000672c`

## callees

- `0x1800050c0`
- `0x180005d94`
- `0x180007034`
- `0x18000b640`

## import_xrefs

- `msvcrt!free` at `0x180005e6a`
- `msvcrt!free` at `0x180005e81`
- `msvcrt!free` at `0x180005e6a`
- `msvcrt!free` at `0x180005e81`
- `msvcrt!malloc` at `0x180005de4`
- `msvcrt!malloc` at `0x180005de4`
- `KERNEL32!WideCharToMultiByte` at `0x180005e3c`
- `KERNEL32!WideCharToMultiByte` at `0x180005e3c`

## string_xrefs

- `0x180005e30`: `REGISTRY`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::ResourceRegister(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        unsigned __int16 a3,
        const unsigned __int16 *a4)
{
  _QWORD *v7; // rbx
  CHAR *lpMultiByteStr; // rdi
  _QWORD *v9; // rax
  unsigned int v10; // edi
  void *v11; // rcx
  void *v13; // rcx
  CHAR MultiByteStr[8]; // [rsp+20h] [rbp-20h] BYREF
  _QWORD *v15; // [rsp+40h] [rbp+0h]

  v7 = 0;
  v15 = 0;
  if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)0x12, (unsigned __int64)a2) )
  {
    lpMultiByteStr = MultiByteStr;
  }
  else
  {
    v9 = malloc(0x22u);
    if ( v9 )
    {
      *v9 = 0;
      v7 = v9;
      v15 = v9;
      lpMultiByteStr = (CHAR *)(v9 + 2);
    }
    else
    {
      lpMultiByteStr = 0;
    }
  }
  if ( lpMultiByteStr && (*lpMultiByteStr = 0, WideCharToMultiByte(3u, 0, L"REGISTRY", -1, lpMultiByteStr, 18, 0, 0)) )
  {
    v10 = ATL::CRegObject::RegisterFromResource(this, a2, (const char *)a3, lpMultiByteStr, 1);
    while ( v7 )
    {
      v11 = v7;
      v7 = (_QWORD *)*v7;
      free(v11);
    }
    return v10;
  }
  else
  {
    while ( v7 )
    {
      v13 = v7;
      v7 = (_QWORD *)*v7;
      free(v13);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180005d94  push    rbp
0x180005d96  push    rbx
0x180005d97  push    rsi
0x180005d98  push    rdi
0x180005d99  push    r14
0x180005d9b  push    r15
0x180005d9d  sub     rsp, 58h
0x180005da1  lea     rbp, [rsp+40h]
0x180005da6  mov     rax, cs:__security_cookie
0x180005dad  xor     rax, rbp
0x180005db0  mov     [rbp+40h+var_38], rax
0x180005db4  mov     esi, r8d
0x180005db7  mov     r14, rdx
0x180005dba  mov     r15, rcx
0x180005dbd  xor     ebx, ebx
0x180005dbf  mov     [rbp+40h+var_40], rbx
0x180005dc3  lea     ecx, [rbx+12h]; this
0x180005dc6  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180005dcb  test    al, al
0x180005dcd  jz      short loc_180005DDF
0x180005dcf  mov     eax, dword ptr [rsp+80h+lpMultiByteStr]
0x180005dd2  sub     rsp, 20h
0x180005dd6  lea     rdi, [rsp+0A0h+MultiByteStr]
0x180005ddb  mov     eax, [rdi]
0x180005ddd  jmp     short loc_180005E05
0x180005ddf  mov     ecx, 22h ; '"'; Size
0x180005de4  call    cs:__imp_malloc
0x180005dea  test    rax, rax
0x180005ded  jnz     short loc_180005DF3
0x180005def  xor     edi, edi
0x180005df1  jmp     short loc_180005E05
0x180005df3  mov     qword ptr [rax], 0
0x180005dfa  mov     rbx, rax
0x180005dfd  mov     [rbp+40h+var_40], rax
0x180005e01  lea     rdi, [rax+10h]
0x180005e05  test    rdi, rdi
0x180005e08  jz      short loc_180005E79
0x180005e0a  mov     byte ptr [rdi], 0
0x180005e0d  mov     [rsp+0A0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180005e16  mov     [rsp+0A0h+lpDefaultChar], 0; lpDefaultChar
0x180005e1f  mov     [rsp+0A0h+cbMultiByte], 12h; cbMultiByte
0x180005e27  mov     [rsp+0A0h+lpMultiByteStr], rdi; lpMultiByteStr
0x180005e2c  or      r9d, 0FFFFFFFFh; cchWideChar
0x180005e30  lea     r8, WideCharStr; "REGISTRY"
0x180005e37  xor     edx, edx; dwFlags
0x180005e39  lea     ecx, [rdx+3]; CodePage
0x180005e3c  call    cs:__imp_WideCharToMultiByte
0x180005e42  test    eax, eax
0x180005e44  jz      short loc_180005E79
0x180005e46  movzx   r8d, si; char *
0x180005e4a  mov     dword ptr [rsp+0A0h+lpMultiByteStr], 1; int
0x180005e52  mov     r9, rdi; char *
0x180005e55  mov     rdx, r14; unsigned __int16 *
0x180005e58  mov     rcx, r15; this
0x180005e5b  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBGPEBD1H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,char const *,char const *,int)
0x180005e60  mov     edi, eax
0x180005e62  jmp     short loc_180005E70
0x180005e64  mov     rcx, rbx; Block
0x180005e67  mov     rbx, [rbx]
0x180005e6a  call    cs:__imp_free
0x180005e70  test    rbx, rbx
0x180005e73  jnz     short loc_180005E64
0x180005e75  mov     eax, edi
0x180005e77  jmp     short loc_180005E91
0x180005e79  jmp     short loc_180005E87
0x180005e7b  mov     rcx, rbx; Block
0x180005e7e  mov     rbx, [rbx]
0x180005e81  call    cs:__imp_free
0x180005e87  test    rbx, rbx
0x180005e8a  jnz     short loc_180005E7B
0x180005e8c  mov     eax, 8007000Eh
0x180005e91  mov     rcx, [rbp+40h+var_38]
0x180005e95  xor     rcx, rbp; StackCookie
0x180005e98  call    __security_check_cookie
0x180005e9d  lea     rsp, [rbp+18h]
0x180005ea1  pop     r15
0x180005ea3  pop     r14
0x180005ea5  pop     rdi
0x180005ea6  pop     rsi
0x180005ea7  pop     rbx
0x180005ea8  pop     rbp
0x180005ea9  retn
```
