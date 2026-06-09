# Dynamo::details::ContextEntry::GetRuleId(void)

- ea: `0x1400477c0`
- end: `0x1400478d0`
- name: `?GetRuleId@ContextEntry@details@Dynamo@@UEBA?AV?$unique_ptr@_JU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@XZ`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14003d008`
- `0x1400477c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004785f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004785f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400477fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400477fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400478ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400478ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14004787f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14004787f`

## string_xrefs

- `0x1400478be`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Dynamo::details::ContextEntry::GetRuleId(__int64 a1, _QWORD *a2)
{
  int v3; // eax
  int ValueW; // eax
  _QWORD *v5; // rax
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+10h]
  DWORD pcbData; // [rsp+70h] [rbp+18h] BYREF
  _QWORD *v10; // [rsp+78h] [rbp+20h]
  HKEY hkey; // [rsp+80h] [rbp+28h] BYREF
  __int64 pvData; // [rsp+88h] [rbp+30h] BYREF

  v10 = a2;
  hkey = 0;
  v3 = RegOpenKeyExW(*(HKEY *)(a1 + 16), L"RuleId", 0, 0x20019u, &hkey);
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  if ( v3 == -2147024894 )
    goto LABEL_4;
  pvData = 0;
  pcbData = 8;
  ValueW = RegGetValueW(hkey, 0, L"RuleId", 0x48u, 0, &pvData, &pcbData);
  if ( ValueW > 0 )
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  if ( ValueW == -2147024894 )
  {
LABEL_4:
    *a2 = 0;
  }
  else
  {
    v5 = LocalAlloc(0, 8u);
    *a2 = v5;
    if ( v5 )
      *v5 = pvData;
    if ( !*a2 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x130E,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v6);
  }
  if ( hkey )
    RegCloseKey(hkey);
  return a2;
}

```

## disassembly

```asm
0x1400477c0  mov     [rsp-10h+arg_8], rdx
0x1400477c5  push    rbp
0x1400477c6  push    rbx
0x1400477c7  mov     rbp, rsp
0x1400477ca  sub     rsp, 58h
0x1400477ce  mov     rbx, rdx
0x1400477d1  mov     [rbp+var_18], 0
0x1400477d8  mov     [rbp+hkey], 0
0x1400477e0  lea     rax, [rbp+hkey]
0x1400477e4  mov     [rsp+58h+phkResult], rax; phkResult
0x1400477e9  mov     r9d, 20019h; samDesired
0x1400477ef  xor     r8d, r8d; ulOptions
0x1400477f2  lea     rdx, aRuleid; "RuleId"
0x1400477f9  mov     rcx, [rcx+10h]; hKey
0x1400477fd  call    cs:__imp_RegOpenKeyExW
0x140047803  test    eax, eax
0x140047805  jle     short loc_14004780F
0x140047807  movzx   eax, ax
0x14004780a  or      eax, 80070000h
0x14004780f  cmp     eax, 80070002h
0x140047814  jnz     short loc_140047822
0x140047816  mov     qword ptr [rbx], 0
0x14004781d  jmp     loc_1400478A5
0x140047822  mov     [rbp+arg_18], 0
0x14004782a  mov     [rbp+arg_0], 8
0x140047831  lea     rax, [rbp+arg_0]
0x140047835  mov     [rsp+58h+pcbData], rax; pcbData
0x14004783a  lea     rax, [rbp+arg_18]
0x14004783e  mov     [rsp+58h+pvData], rax; pvData
0x140047843  mov     [rsp+58h+phkResult], 0; pdwType
0x14004784c  mov     r9d, 48h ; 'H'; dwFlags
0x140047852  lea     r8, aRuleid; "RuleId"
0x140047859  xor     edx, edx; lpSubKey
0x14004785b  mov     rcx, [rbp+hkey]; hkey
0x14004785f  call    cs:__imp_RegGetValueW
0x140047865  test    eax, eax
0x140047867  jle     short loc_140047871
0x140047869  movzx   eax, ax
0x14004786c  or      eax, 80070000h
0x140047871  cmp     eax, 80070002h
0x140047876  jz      short loc_140047816
0x140047878  mov     edx, 8; uBytes
0x14004787d  xor     ecx, ecx; uFlags
0x14004787f  call    cs:__imp_LocalAlloc
0x140047885  mov     [rbx], rax
0x140047888  test    rax, rax
0x14004788b  jz      short loc_140047894
0x14004788d  mov     rcx, [rbp+arg_18]
0x140047891  mov     [rax], rcx
0x140047894  mov     [rbp+var_18], 2
0x14004789b  mov     rcx, [rbp+10h]; this
0x14004789f  cmp     qword ptr [rbx], 0
0x1400478a3  jz      short loc_1400478BE
0x1400478a5  mov     rcx, [rbp+hkey]; hKey
0x1400478a9  test    rcx, rcx
0x1400478ac  jz      short loc_1400478B4
0x1400478ae  call    cs:__imp_RegCloseKey
0x1400478b4  mov     rax, rbx
0x1400478b7  add     rsp, 58h
0x1400478bb  pop     rbx
0x1400478bc  pop     rbp
0x1400478bd  retn
0x1400478be  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400478c5  mov     edx, 130Eh; void *
0x1400478ca  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
