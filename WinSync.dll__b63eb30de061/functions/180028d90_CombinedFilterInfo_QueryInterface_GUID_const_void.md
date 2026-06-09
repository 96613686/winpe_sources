# CombinedFilterInfo::QueryInterface(_GUID const &,void * *)

- ea: `0x180028d90`
- end: `0x180028e85`
- name: `?QueryInterface@CombinedFilterInfo@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `245`
- prototype: `__int64 __fastcall(CombinedFilterInfo *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18005edd0`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180028d90`
- `0x1800290a0`
- `0x180094010`

## string_xrefs

- `0x180028dc5`: `CombinedFilterInfo::QueryInterface`
- `0x180028e5e`: `CombinedFilterInfo::QueryInterface`

## pseudocode

```c
__int64 __fastcall CombinedFilterInfo::QueryInterface(CombinedFilterInfo *this, const struct _GUID *a2, void **a3)
{
  PVOID *v6; // rcx
  unsigned int Interface; // ebx
  __int64 v8; // rax

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      "CombinedFilterInfo::QueryInterface");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ICombinedFilterInfo.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ICombinedFilterInfo.Data1 )
      v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ICombinedFilterInfo.Data4;
    if ( v8 )
    {
      Interface = FilterInfo::QueryInterface(this, a2, a3);
    }
    else
    {
      Interface = 0;
      *a3 = (void *)(((unsigned __int64)this + 32) & -(__int64)(this != 0));
      (*(void (__fastcall **)(CombinedFilterInfo *))(*(_QWORD *)this + 8LL))(this);
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    Interface = -2147467261;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      13,
      (unsigned int)WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      (unsigned int)"CombinedFilterInfo::QueryInterface",
      Interface);
  return Interface;
}

```

## disassembly

```asm
0x180028d90  push    rbx
0x180028d92  push    rbp
0x180028d93  push    rsi
0x180028d94  push    rdi
0x180028d95  sub     rsp, 38h
0x180028d99  mov     rdi, r8
0x180028d9c  mov     rbx, rdx
0x180028d9f  mov     rsi, rcx
0x180028da2  mov     rcx, cs:WPP_GLOBAL_Control
0x180028da9  lea     rbp, WPP_GLOBAL_Control
0x180028db0  cmp     rcx, rbp
0x180028db3  jz      short loc_180028DE4
0x180028db5  test    byte ptr [rcx+1Ch], 40h
0x180028db9  jz      short loc_180028DE4
0x180028dbb  cmp     byte ptr [rcx+19h], 5
0x180028dbf  jb      short loc_180028DE4
0x180028dc1  mov     rcx, [rcx+10h]
0x180028dc5  lea     r9, aCombinedfilter; "CombinedFilterInfo::QueryInterface"
0x180028dcc  mov     edx, 0Ch
0x180028dd1  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x180028dd8  call    WPP_SF_s
0x180028ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x180028de4  test    rdi, rdi
0x180028de7  jnz     short loc_180028DF0
0x180028de9  mov     ebx, 80004003h
0x180028dee  jmp     short loc_180028E49
0x180028df0  mov     rax, [rbx]
0x180028df3  sub     rax, qword ptr cs:IID_ICombinedFilterInfo.Data1
0x180028dfa  jnz     short loc_180028E07
0x180028dfc  mov     rax, [rbx+8]
0x180028e00  sub     rax, qword ptr cs:IID_ICombinedFilterInfo.Data4
0x180028e07  test    rax, rax
0x180028e0a  jnz     short loc_180028E32
0x180028e0c  xor     ebx, ebx
0x180028e0e  lea     rdx, [rsi+20h]
0x180028e12  mov     rax, rsi
0x180028e15  neg     rax
0x180028e18  sbb     rcx, rcx
0x180028e1b  and     rcx, rdx
0x180028e1e  mov     [rdi], rcx
0x180028e21  mov     rcx, rsi
0x180028e24  mov     rax, [rsi]
0x180028e27  mov     rax, [rax+8]
0x180028e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e30  jmp     short loc_180028E42
0x180028e32  mov     r8, rdi; void **
0x180028e35  mov     rdx, rbx; struct _GUID *
0x180028e38  mov     rcx, rsi; this
0x180028e3b  call    ?QueryInterface@FilterInfo@@UEAAJAEBU_GUID@@PEAPEAX@Z; FilterInfo::QueryInterface(_GUID const &,void * *)
0x180028e40  mov     ebx, eax
0x180028e42  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e49  cmp     rcx, rbp
0x180028e4c  jz      short loc_180028E7A
0x180028e4e  test    byte ptr [rcx+1Ch], 40h
0x180028e52  jz      short loc_180028E7A
0x180028e54  cmp     byte ptr [rcx+19h], 5
0x180028e58  jb      short loc_180028E7A
0x180028e5a  mov     rcx, [rcx+10h]
0x180028e5e  lea     r9, aCombinedfilter; "CombinedFilterInfo::QueryInterface"
0x180028e65  mov     edx, 0Dh
0x180028e6a  mov     [rsp+58h+var_38], ebx
0x180028e6e  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x180028e75  call    WPP_SF_sD
0x180028e7a  mov     eax, ebx
0x180028e7c  add     rsp, 38h
0x180028e80  pop     rdi
0x180028e81  pop     rsi
0x180028e82  pop     rbp
0x180028e83  pop     rbx
0x180028e84  retn
```
