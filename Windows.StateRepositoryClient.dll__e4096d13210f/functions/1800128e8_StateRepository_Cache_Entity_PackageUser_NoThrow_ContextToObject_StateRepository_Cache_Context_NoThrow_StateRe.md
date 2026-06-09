# StateRepository::Cache::Entity::PackageUser_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageUser_NoThrow &,StateRepository::Cache::Entity::PackageUser_NoThrow::CacheFlags,__int64)

- ea: `0x1800128e8`
- end: `0x180012974`
- name: `?ContextToObject@PackageUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `140`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180012fd0`

## callees

- `0x1800075e4`
- `0x18000b0f0`
- `0x1800128e8`

## string_xrefs

- `0x180012925`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18001293e`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUser.hpp`
- `0x180012907`: `InstallTime`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUser_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  int Field; // eax
  unsigned int v7; // edi
  __int64 result; // rax
  int v9; // [rsp+20h] [rbp-8h]
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int64 v12; // [rsp+40h] [rbp+18h] BYREF

  v12 = 0;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"InstallTime", &v12);
  v7 = Field;
  if ( Field >= 0 )
  {
    a2[3] = v12;
    result = 0;
    *a2 = a4;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x239,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field,
      v9);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DB,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUser.hpp",
      (const char *)v7,
      v10);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x1800128e8  mov     rax, rsp
0x1800128eb  mov     [rax+8], rbx
0x1800128ef  mov     [rax+10h], rsi
0x1800128f3  mov     [rax+18h], r8
0x1800128f7  push    rdi; int
0x1800128f8  sub     rsp, 20h
0x1800128fc  mov     rbx, rdx
0x1800128ff  mov     qword ptr [rax+18h], 0
0x180012907  lea     rdx, aInstalltime; "InstallTime"
0x18001290e  mov     rsi, r9
0x180012911  lea     r8, [rax+18h]; unsigned __int64 *
0x180012915  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEA_K@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,unsigned __int64 &)
0x18001291a  mov     edi, eax
0x18001291c  test    eax, eax
0x18001291e  jns     short loc_180012956
0x180012920  mov     rcx, [rsp+28h]; this
0x180012925  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18001292c  mov     r9d, eax; char *
0x18001292f  mov     edx, 239h; void *
0x180012934  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012939  mov     rcx, [rsp+28h]; this
0x18001293e  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\StateRepositor"...
0x180012945  mov     r9d, edi; char *
0x180012948  mov     edx, 2DBh; void *
0x18001294d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012952  mov     eax, edi
0x180012954  jmp     short loc_180012964
0x180012956  mov     rax, [rsp+28h+arg_10]
0x18001295b  mov     [rbx+18h], rax
0x18001295f  xor     eax, eax
0x180012961  mov     [rbx], rsi
0x180012964  mov     rbx, [rsp+28h+arg_0]
0x180012969  mov     rsi, [rsp+28h+arg_8]
0x18001296e  add     rsp, 20h
0x180012972  pop     rdi
0x180012973  retn
```
