# CombinedFilterInfo::GetSerializedSize(ulong *,ulong *,ulong *)

- ea: `0x18005ed10`
- end: `0x18005edc7`
- name: `?GetSerializedSize@CombinedFilterInfo@@AEAAJPEAK00@Z`
- size: `183`
- prototype: `__int64 __fastcall(CombinedFilterInfo *__hidden this, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005ede0`

## callees

- `0x18001ae20`
- `0x18005ed10`
- `0x180094010`

## string_xrefs

- `0x18005ed9f`: `CombinedFilterInfo::GetSerializedSize`

## pseudocode

```c
__int64 __fastcall CombinedFilterInfo::GetSerializedSize(
        CombinedFilterInfo *this,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // r8d
  unsigned int v10; // ebx

  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 24LL))(*((_QWORD *)this + 5), 0);
  v9 = 0;
  if ( v8 != -2147024662 )
    v9 = v8;
  if ( !v9 )
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *))(**((_QWORD **)this + 6) + 24LL))(
           *((_QWORD *)this + 6),
           0,
           a4);
  v10 = 0;
  if ( v9 != -2147024662 )
    v10 = v9;
  if ( !v10 )
    *a2 = *a4 + *a3 + 20;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      (unsigned int)"CombinedFilterInfo::GetSerializedSize",
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x18005ed10  push    rbx
0x18005ed12  push    rsi
0x18005ed13  push    rdi
0x18005ed14  push    r14
0x18005ed16  sub     rsp, 38h
0x18005ed1a  mov     rbx, rcx
0x18005ed1d  mov     r14, rdx
0x18005ed20  mov     rcx, [rcx+28h]
0x18005ed24  xor     edx, edx
0x18005ed26  mov     rdi, r9
0x18005ed29  mov     rsi, r8
0x18005ed2c  mov     rax, [rcx]
0x18005ed2f  mov     rax, [rax+18h]
0x18005ed33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed38  xor     r8d, r8d
0x18005ed3b  cmp     eax, 800700EAh
0x18005ed40  cmovnz  r8d, eax
0x18005ed44  test    r8d, r8d
0x18005ed47  jnz     short loc_18005ED61
0x18005ed49  mov     rcx, [rbx+30h]
0x18005ed4d  mov     r8, rdi
0x18005ed50  xor     edx, edx
0x18005ed52  mov     rax, [rcx]
0x18005ed55  mov     rax, [rax+18h]
0x18005ed59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed5e  mov     r8d, eax
0x18005ed61  xor     ebx, ebx
0x18005ed63  cmp     r8d, 800700EAh
0x18005ed6a  cmovnz  ebx, r8d
0x18005ed6e  test    ebx, ebx
0x18005ed70  jnz     short loc_18005ED7C
0x18005ed72  mov     ecx, [rsi]
0x18005ed74  add     ecx, 14h
0x18005ed77  add     ecx, [rdi]
0x18005ed79  mov     [r14], ecx
0x18005ed7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ed83  lea     rax, WPP_GLOBAL_Control
0x18005ed8a  cmp     rcx, rax
0x18005ed8d  jz      short loc_18005EDBB
0x18005ed8f  test    byte ptr [rcx+1Ch], 40h
0x18005ed93  jz      short loc_18005EDBB
0x18005ed95  cmp     byte ptr [rcx+19h], 5
0x18005ed99  jb      short loc_18005EDBB
0x18005ed9b  mov     rcx, [rcx+10h]
0x18005ed9f  lea     r9, aCombinedfilter_0; "CombinedFilterInfo::GetSerializedSize"
0x18005eda6  mov     edx, 0Eh
0x18005edab  mov     [rsp+58h+var_38], ebx
0x18005edaf  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x18005edb6  call    WPP_SF_sD
0x18005edbb  mov     eax, ebx
0x18005edbd  add     rsp, 38h
0x18005edc1  pop     r14
0x18005edc3  pop     rdi
0x18005edc4  pop     rsi
0x18005edc5  pop     rbx
0x18005edc6  retn
```
