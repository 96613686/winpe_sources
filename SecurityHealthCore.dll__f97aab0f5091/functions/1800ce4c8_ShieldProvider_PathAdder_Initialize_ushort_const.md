# ShieldProvider::PathAdder::Initialize(ushort const *)

- ea: `0x1800ce4c8`
- end: `0x1800ce597`
- name: `?Initialize@PathAdder@ShieldProvider@@QEAAJPEBG@Z`
- size: `207`
- prototype: `int(ShieldProvider::PathAdder *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000cc10`

## callees

- `0x180004ae0`
- `0x18000a7ec`
- `0x1800ce4c8`
- `0x1800dab80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800ce53a`
- `KERNEL32!GetLastError` at `0x1800ce53a`
- `KERNEL32!AddDllDirectory` at `0x1800ce52b`
- `KERNEL32!AddDllDirectory` at `0x1800ce52b`

## string_xrefs

- `0x1800ce4fc`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\shieldutil\shieldproviderutil.cpp`
- `0x1800ce558`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\shieldutil\shieldproviderutil.cpp`

## pseudocode

```c
__int64 __fastcall ShieldProvider::PathAdder::Initialize(
        ShieldProvider::PathAdder *this,
        unsigned __int16 **a2,
        const unsigned __int16 *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  const struct std::nothrow_t *v6; // rdx
  WCHAR *v8; // rbx
  DLL_DIRECTORY_COOKIE v9; // rax
  const struct std::nothrow_t *v10; // rdx
  signed int LastError; // eax
  unsigned int v12; // edi
  const struct std::nothrow_t *v13; // rdx
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PCWSTR NewDirectory; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return 0;
  NewDirectory = 0;
  v4 = CommonUtil::UtilExpandEnvironmentStrings((CommonUtil *)&NewDirectory, a2, a3);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\shieldutil\\shieldproviderutil.cpp",
      (const char *)(unsigned int)v4,
      v14);
    if ( NewDirectory )
      operator delete((void *)NewDirectory, v6);
    return v5;
  }
  v8 = (WCHAR *)NewDirectory;
  v9 = AddDllDirectory(NewDirectory);
  *((_QWORD *)this + 2) = v9;
  if ( v9 )
    goto LABEL_13;
  LastError = GetLastError();
  v12 = LastError;
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
  if ( (v12 & 0x80000000) == 0 )
  {
LABEL_13:
    if ( v8 )
      operator delete(v8, v10);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3D,
    (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\shieldutil\\shieldproviderutil.cpp",
    (const char *)v12,
    v14);
  if ( v8 )
    operator delete(v8, v13);
  return v12;
}

```

## disassembly

```asm
0x1800ce4c8  mov     [rsp+arg_0], rbx
0x1800ce4cd  push    rdi; int
0x1800ce4ce  sub     rsp, 20h
0x1800ce4d2  mov     rdi, rcx
0x1800ce4d5  test    rdx, rdx
0x1800ce4d8  jz      loc_1800CE58A
0x1800ce4de  lea     rcx, [rsp+28h+NewDirectory]; this
0x1800ce4e3  mov     [rsp+28h+NewDirectory], 0
0x1800ce4ec  call    ?UtilExpandEnvironmentStrings@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::UtilExpandEnvironmentStrings(ushort * *,ushort const *)
0x1800ce4f1  mov     ebx, eax
0x1800ce4f3  test    eax, eax
0x1800ce4f5  jns     short loc_1800CE523
0x1800ce4f7  mov     rcx, [rsp+28h]; this
0x1800ce4fc  lea     r8, aOnecoreAmcoreA_13; "onecore\\amcore\\antimalware\\source\\s"...
0x1800ce503  mov     r9d, eax; char *
0x1800ce506  mov     edx, 39h ; '9'; void *
0x1800ce50b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce510  mov     rcx, [rsp+28h+NewDirectory]; void *
0x1800ce515  test    rcx, rcx
0x1800ce518  jz      short loc_1800CE51F
0x1800ce51a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ce51f  mov     eax, ebx
0x1800ce521  jmp     short loc_1800CE58C
0x1800ce523  mov     rbx, [rsp+28h+NewDirectory]
0x1800ce528  mov     rcx, rbx; NewDirectory
0x1800ce52b  call    cs:__imp_AddDllDirectory
0x1800ce531  mov     [rdi+10h], rax
0x1800ce535  test    rax, rax
0x1800ce538  jnz     short loc_1800CE57D
0x1800ce53a  call    cs:__imp_GetLastError
0x1800ce540  mov     edi, eax
0x1800ce542  test    eax, eax
0x1800ce544  jle     short loc_1800CE54F
0x1800ce546  movzx   edi, ax
0x1800ce549  or      edi, 80070000h
0x1800ce54f  test    edi, edi
0x1800ce551  jns     short loc_1800CE57D
0x1800ce553  mov     rcx, [rsp+28h]; this
0x1800ce558  lea     r8, aOnecoreAmcoreA_13; "onecore\\amcore\\antimalware\\source\\s"...
0x1800ce55f  mov     r9d, edi; char *
0x1800ce562  mov     edx, 3Dh ; '='; void *
0x1800ce567  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce56c  test    rbx, rbx
0x1800ce56f  jz      short loc_1800CE579
0x1800ce571  mov     rcx, rbx; void *
0x1800ce574  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ce579  mov     eax, edi
0x1800ce57b  jmp     short loc_1800CE58C
0x1800ce57d  test    rbx, rbx
0x1800ce580  jz      short loc_1800CE58A
0x1800ce582  mov     rcx, rbx; void *
0x1800ce585  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ce58a  xor     eax, eax
0x1800ce58c  mov     rbx, [rsp+28h+arg_0]
0x1800ce591  add     rsp, 20h
0x1800ce595  pop     rdi
0x1800ce596  retn
```
