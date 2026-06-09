# Csl::DismHelper::IsFeatureInstalled(ushort const *,bool &)

- ea: `0x18002a780`
- end: `0x18002a817`
- name: `?IsFeatureInstalled@DismHelper@Csl@@QEAAJPEBGAEA_N@Z`
- size: `151`
- prototype: `__int64 __fastcall(Csl::DismHelper *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18002a600`
- `0x18002a6b4`

## callees

- `0x1800045e4`
- `0x18002a780`

## import_xrefs

- `DismApi!DismGetFeatureInfo` at `0x18002a7aa`
- `DismApi!DismGetFeatureInfo` at `0x18002a7aa`
- `DismApi!DismDelete` at `0x18002a7df`
- `DismApi!DismDelete` at `0x18002a7fd`
- `DismApi!DismDelete` at `0x18002a7df`
- `DismApi!DismDelete` at `0x18002a7fd`

## pseudocode

```c
__int64 __fastcall Csl::DismHelper::IsFeatureInstalled(Csl::DismHelper *this, const unsigned __int16 *a2, bool *a3)
{
  __int64 v3; // rcx
  int FeatureInfo; // eax
  unsigned int v6; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF

  v3 = *(unsigned int *)this;
  v9 = 0;
  FeatureInfo = DismGetFeatureInfo(v3, a2, 0, 1);
  v6 = FeatureInfo;
  if ( FeatureInfo >= 0 )
  {
    *a3 = *(_DWORD *)(v9 + 8) == 4;
    DismDelete();
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\csldism.cpp",
      (const char *)(unsigned int)FeatureInfo,
      (int)&v9);
    if ( v9 )
      DismDelete();
    return v6;
  }
}

```

## disassembly

```asm
0x18002a780  mov     r11, rsp
0x18002a783  mov     [r11+10h], rbx
0x18002a787  push    rdi
0x18002a788  sub     rsp, 30h
0x18002a78c  mov     ecx, [rcx]
0x18002a78e  lea     rax, [r11+8]
0x18002a792  mov     rdi, r8
0x18002a795  mov     [r11-18h], rax
0x18002a799  xor     r8d, r8d
0x18002a79c  mov     qword ptr [r11+8], 0
0x18002a7a4  mov     r9d, 1
0x18002a7aa  call    cs:__imp_DismGetFeatureInfo
0x18002a7b1  nop     dword ptr [rax+rax+00h]
0x18002a7b6  mov     ebx, eax
0x18002a7b8  test    eax, eax
0x18002a7ba  jns     short loc_18002A7EF
0x18002a7bc  mov     rcx, [rsp+38h]; this
0x18002a7c1  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002a7c8  mov     r9d, eax; char *
0x18002a7cb  mov     edx, 81h; void *
0x18002a7d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a7d5  mov     rcx, [rsp+38h+arg_0]
0x18002a7da  test    rcx, rcx
0x18002a7dd  jz      short loc_18002A7EB
0x18002a7df  call    cs:__imp_DismDelete
0x18002a7e6  nop     dword ptr [rax+rax+00h]
0x18002a7eb  mov     eax, ebx
0x18002a7ed  jmp     short loc_18002A80B
0x18002a7ef  mov     rcx, [rsp+38h+arg_0]
0x18002a7f4  cmp     dword ptr [rcx+8], 4
0x18002a7f8  setz    al
0x18002a7fb  mov     [rdi], al
0x18002a7fd  call    cs:__imp_DismDelete
0x18002a804  nop     dword ptr [rax+rax+00h]
0x18002a809  xor     eax, eax
0x18002a80b  mov     rbx, [rsp+38h+arg_8]
0x18002a810  add     rsp, 30h
0x18002a814  pop     rdi
0x18002a815  retn
```
