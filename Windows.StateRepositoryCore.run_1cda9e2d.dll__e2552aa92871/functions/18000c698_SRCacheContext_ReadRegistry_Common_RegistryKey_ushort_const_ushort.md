# SRCacheContext::ReadRegistry(Common::RegistryKey &,ushort const *,ushort * *)

- ea: `0x18000c698`
- end: `0x18000c7ca`
- name: `?ReadRegistry@SRCacheContext@@CAJAEAVRegistryKey@Common@@PEBGPEAPEAG@Z`
- size: `306`
- prototype: `__int64 __fastcall(struct Common::RegistryKey *this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ce50`
- `0x18000ced0`

## callees

- `0x18000940c`
- `0x18000bed8`
- `0x18000c698`
- `0x18000c7d0`
- `0x18000c928`
- `0x18000fafc`

## string_xrefs

- `0x18000c78c`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000c79e`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SRCacheContext::ReadRegistry(
        struct Common::RegistryKey *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned int v6; // ebx
  unsigned __int16 *v7; // rdi
  int StringValue; // eax
  unsigned int v9; // r8d
  const char *v10; // r9
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rdx
  unsigned int v15; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  unsigned int v17; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  LPBYTE v19; // [rsp+78h] [rbp+48h] BYREF

  *a3 = 0;
  if ( (unsigned __int64)(*(_QWORD *)this - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v11 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)0x8007139FLL,
      v15);
  }
  else
  {
    v6 = 260;
    v17 = 260;
    while ( 1 )
    {
      wil::make_unique_nothrow<unsigned short [0]>(&v19, v6);
      v7 = (unsigned __int16 *)v19;
      if ( !v19 )
      {
        v11 = -2147024882;
        v13 = 187;
        v12 = 2147942414LL;
        goto LABEL_16;
      }
      Type = 4;
      StringValue = Common::RegistryKey::GetStringValue(this, a2, v6, &v17, v19, &Type);
      v11 = StringValue;
      if ( StringValue >= 0 )
        break;
      if ( (unsigned int)(StringValue + 2147024894) <= 1 )
      {
        v11 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xCD, v9, v10, v15);
        goto LABEL_10;
      }
      if ( StringValue != -2147024662 )
      {
        v12 = (unsigned int)StringValue;
        v13 = 217;
LABEL_16:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
          (const char *)v12,
          v15);
        goto LABEL_10;
      }
      v6 = ++v17;
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v19);
    }
    if ( Type )
      v19 = 0;
    else
      v7 = 0;
    *a3 = v7;
    v11 = 0;
LABEL_10:
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v19);
  }
  return v11;
}

```

## disassembly

```asm
0x18000c698  mov     [rsp-28h+arg_8], rbx
0x18000c69d  push    rbp
0x18000c69e  push    rsi
0x18000c69f  push    rdi
0x18000c6a0  push    r14
0x18000c6a2  push    r15
0x18000c6a4  mov     rbp, rsp
0x18000c6a7  sub     rsp, 30h
0x18000c6ab  mov     qword ptr [r8], 0
0x18000c6b2  mov     rsi, r8
0x18000c6b5  mov     rax, [rcx]
0x18000c6b8  mov     r15, rdx
0x18000c6bb  dec     rax
0x18000c6be  mov     r14, rcx
0x18000c6c1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c6c5  ja      loc_18000C79A
0x18000c6cb  mov     ebx, 104h
0x18000c6d0  mov     [rbp+arg_0], ebx
0x18000c6d3  mov     edx, ebx
0x18000c6d5  lea     rcx, [rbp+arg_18]
0x18000c6d9  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18000c6de  mov     rdi, [rbp+arg_18]
0x18000c6e2  test    rdi, rdi
0x18000c6e5  jz      loc_18000C77B
0x18000c6eb  lea     rax, [rbp+Type]
0x18000c6ef  mov     [rbp+Type], 4
0x18000c6f6  mov     [rsp+30h+lpType], rax; lpType
0x18000c6fb  lea     r9, [rbp+arg_0]; unsigned int *
0x18000c6ff  mov     r8d, ebx; unsigned int
0x18000c702  mov     [rsp+30h+var_10], rdi; unsigned int
0x18000c707  mov     rdx, r15; unsigned __int16 *
0x18000c70a  mov     rcx, r14; this
0x18000c70d  call    ?GetStringValue@RegistryKey@Common@@QEAAJPEBGKPEAKPEAG1@Z; Common::RegistryKey::GetStringValue(ushort const *,ulong,ulong *,ushort *,ulong *)
0x18000c712  mov     ebx, eax
0x18000c714  test    eax, eax
0x18000c716  jns     short loc_18000C762
0x18000c718  lea     ecx, [rax+7FF8FFFEh]
0x18000c71e  cmp     ecx, 1
0x18000c721  jbe     short loc_18000C747
0x18000c723  cmp     eax, 800700EAh
0x18000c728  jnz     short loc_18000C73D
0x18000c72a  mov     ebx, [rbp+arg_0]
0x18000c72d  lea     rcx, [rbp+arg_18]
0x18000c731  inc     ebx
0x18000c733  mov     [rbp+arg_0], ebx
0x18000c736  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18000c73b  jmp     short loc_18000C6D3
0x18000c73d  mov     r9d, eax
0x18000c740  mov     edx, 0D9h
0x18000c745  jmp     short loc_18000C788
0x18000c747  mov     rcx, [rbp+28h]; this
0x18000c74b  mov     edx, 0CDh; void *
0x18000c750  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000c755  mov     ebx, eax
0x18000c757  lea     rcx, [rbp+arg_18]
0x18000c75b  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18000c760  jmp     short loc_18000C7B7
0x18000c762  cmp     [rbp+Type], 0
0x18000c766  jnz     short loc_18000C76C
0x18000c768  xor     edi, edi
0x18000c76a  jmp     short loc_18000C774
0x18000c76c  mov     [rbp+arg_18], 0
0x18000c774  mov     [rsi], rdi
0x18000c777  xor     ebx, ebx
0x18000c779  jmp     short loc_18000C757
0x18000c77b  mov     ebx, 8007000Eh
0x18000c780  mov     edx, 0BBh; void *
0x18000c785  mov     r9d, ebx; char *
0x18000c788  mov     rcx, [rbp+28h]; this
0x18000c78c  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c793  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c798  jmp     short loc_18000C757
0x18000c79a  mov     rcx, [rbp+28h]; this
0x18000c79e  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c7a5  mov     ebx, 8007139Fh
0x18000c7aa  mov     edx, 0B5h; void *
0x18000c7af  mov     r9d, ebx; char *
0x18000c7b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c7b7  mov     eax, ebx
0x18000c7b9  mov     rbx, [rsp+30h+arg_8]
0x18000c7be  add     rsp, 30h
0x18000c7c2  pop     r15
0x18000c7c4  pop     r14
0x18000c7c6  pop     rdi
0x18000c7c7  pop     rsi
0x18000c7c8  pop     rbp
0x18000c7c9  retn
```
