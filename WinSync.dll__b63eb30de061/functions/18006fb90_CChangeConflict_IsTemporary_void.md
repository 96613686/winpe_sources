# CChangeConflict::IsTemporary(void)

- ea: `0x18006fb90`
- end: `0x18006fc4d`
- name: `?IsTemporary@CChangeConflict@@UEAAJXZ`
- size: `189`
- prototype: `__int64 __fastcall(CChangeConflict *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18006fb90`
- `0x180094010`

## string_xrefs

- `0x18006fbc5`: `CChangeConflict::IsTemporary`
- `0x18006fc1f`: `CChangeConflict::IsTemporary`

## pseudocode

```c
__int64 __fastcall CChangeConflict::IsTemporary(CChangeConflict *this)
{
  PVOID *v2; // rcx
  __int64 v3; // rdx
  unsigned int v4; // ebx
  unsigned int v5; // eax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      WPP_1269ff02d2753eb151b0f5d78a0d1042_Traceguids,
      "CChangeConflict::IsTemporary");
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = *((_QWORD *)this + 4);
  v4 = -2147217379;
  if ( v3 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v3 + 112LL))(*((_QWORD *)this + 4));
    v2 = (PVOID *)WPP_GLOBAL_Control;
    v4 = v5;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v2[2],
      43,
      (unsigned int)WPP_1269ff02d2753eb151b0f5d78a0d1042_Traceguids,
      (unsigned int)"CChangeConflict::IsTemporary",
      v4);
  return v4;
}

```

## disassembly

```asm
0x18006fb90  mov     [rsp+arg_0], rbx
0x18006fb95  mov     [rsp+arg_8], rsi
0x18006fb9a  push    rdi
0x18006fb9b  sub     rsp, 30h
0x18006fb9f  mov     rdi, rcx
0x18006fba2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fba9  lea     rsi, WPP_GLOBAL_Control
0x18006fbb0  cmp     rcx, rsi
0x18006fbb3  jz      short loc_18006FBE4
0x18006fbb5  test    byte ptr [rcx+1Ch], 8
0x18006fbb9  jz      short loc_18006FBE4
0x18006fbbb  cmp     byte ptr [rcx+19h], 5
0x18006fbbf  jb      short loc_18006FBE4
0x18006fbc1  mov     rcx, [rcx+10h]
0x18006fbc5  lea     r9, aCchangeconflic_11; "CChangeConflict::IsTemporary"
0x18006fbcc  mov     edx, 2Ah ; '*'
0x18006fbd1  lea     r8, WPP_1269ff02d2753eb151b0f5d78a0d1042_Traceguids
0x18006fbd8  call    WPP_SF_s
0x18006fbdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fbe4  mov     rdx, [rdi+20h]
0x18006fbe8  mov     ebx, 8004101Dh
0x18006fbed  test    rdx, rdx
0x18006fbf0  jz      short loc_18006FC0A
0x18006fbf2  mov     rax, [rdx]
0x18006fbf5  mov     rcx, rdx
0x18006fbf8  mov     rax, [rax+70h]
0x18006fbfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fc01  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fc08  mov     ebx, eax
0x18006fc0a  cmp     rcx, rsi
0x18006fc0d  jz      short loc_18006FC3B
0x18006fc0f  test    byte ptr [rcx+1Ch], 8
0x18006fc13  jz      short loc_18006FC3B
0x18006fc15  cmp     byte ptr [rcx+19h], 5
0x18006fc19  jb      short loc_18006FC3B
0x18006fc1b  mov     rcx, [rcx+10h]
0x18006fc1f  lea     r9, aCchangeconflic_11; "CChangeConflict::IsTemporary"
0x18006fc26  mov     edx, 2Bh ; '+'
0x18006fc2b  mov     [rsp+38h+var_18], ebx
0x18006fc2f  lea     r8, WPP_1269ff02d2753eb151b0f5d78a0d1042_Traceguids
0x18006fc36  call    WPP_SF_sD
0x18006fc3b  mov     rsi, [rsp+38h+arg_8]
0x18006fc40  mov     eax, ebx
0x18006fc42  mov     rbx, [rsp+38h+arg_0]
0x18006fc47  add     rsp, 30h
0x18006fc4b  pop     rdi
0x18006fc4c  retn
```
