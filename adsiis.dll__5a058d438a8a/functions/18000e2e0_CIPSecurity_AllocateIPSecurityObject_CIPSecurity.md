# CIPSecurity::AllocateIPSecurityObject(CIPSecurity * *)

- ea: `0x18000e2e0`
- end: `0x18000e3d5`
- name: `?AllocateIPSecurityObject@CIPSecurity@@SAJPEAPEAV1@@Z`
- size: `245`
- prototype: `__int64 __fastcall(struct CIPSecurity **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e490`

## callees

- `0x1800010b0`
- `0x180001e50`
- `0x18000e1d0`
- `0x18000e2e0`
- `0x180016d40`
- `0x18001cb90`

## pseudocode

```c
__int64 __fastcall CIPSecurity::AllocateIPSecurityObject(struct CIPSecurity **a1)
{
  int TypeInfoEntry; // esi
  _QWORD *v3; // rax
  CIPSecurity *v4; // rbx
  unsigned int v5; // edx
  _QWORD *v6; // rdi
  unsigned int v7; // edx
  __int64 result; // rax

  TypeInfoEntry = -2147024882;
  v3 = operator new(0xF0u);
  v4 = (CIPSecurity *)v3;
  if ( !v3 )
    return (unsigned int)TypeInfoEntry;
  *((_DWORD *)v3 + 2) = 1;
  _InterlockedIncrement(&ModuleCount::m_Count);
  v3[2] = 0;
  *v3 = &CIPSecurity::`vftable';
  *(_QWORD *)((char *)v3 + 36) = 0;
  v3[3] = 0;
  *((_DWORD *)v3 + 8) = 0;
  v3[23] = 0;
  *((_DWORD *)v3 + 48) = 0;
  *((_DWORD *)v3 + 58) = 1;
  ADDRESS_CHECK::BindCheckList((ADDRESS_CHECK *)(v3 + 3), 0, 0);
  v6 = operator new(0x38u);
  if ( !v6 )
  {
LABEL_5:
    CIPSecurity::`scalar deleting destructor'(v4, v5);
    return (unsigned int)TypeInfoEntry;
  }
  v6[2] = 0;
  *v6 = &CAggregatorDispMgr::`vftable';
  v6[3] = 0;
  *((_DWORD *)v6 + 2) = 0;
  v6[4] = 0;
  v6[5] = 0;
  *((_DWORD *)v6 + 12) = 0;
  TypeInfoEntry = CAggregatorDispMgr::LoadTypeInfoEntry(
                    (CAggregatorDispMgr *)v6,
                    &LIBID_IISOle,
                    &IID_IISIPSecurity,
                    v4,
                    1);
  if ( TypeInfoEntry < 0 )
  {
    CAggregatorDispMgr::`scalar deleting destructor'((CAggregatorDispMgr *)v6, v7);
    goto LABEL_5;
  }
  *((_QWORD *)v4 + 2) = v6;
  result = 0;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x18000e2e0  push    rbx
0x18000e2e2  push    rbp
0x18000e2e3  push    rsi
0x18000e2e4  push    rdi
0x18000e2e5  push    r14
0x18000e2e7  sub     rsp, 30h
0x18000e2eb  mov     r14, rcx
0x18000e2ee  mov     esi, 8007000Eh
0x18000e2f3  mov     ecx, 0F0h; Size
0x18000e2f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e2fd  xor     ebp, ebp
0x18000e2ff  mov     rbx, rax
0x18000e302  test    rax, rax
0x18000e305  jz      loc_18000E3BD
0x18000e30b  mov     dword ptr [rax+8], 1
0x18000e312  lock inc cs:?m_Count@ModuleCount@@0JA; long ModuleCount::m_Count
0x18000e319  lea     rcx, [rbx+18h]; this
0x18000e31d  mov     [rbx+10h], rbp
0x18000e321  lea     rax, ??_7CIPSecurity@@6B@; const CIPSecurity::`vftable'
0x18000e328  xor     r8d, r8d; unsigned int
0x18000e32b  mov     [rbx], rax
0x18000e32e  xor     edx, edx; unsigned __int8 *
0x18000e330  mov     [rcx+0Ch], rbp
0x18000e334  mov     [rcx], rbp
0x18000e337  mov     [rcx+8], ebp
0x18000e33a  mov     [rcx+0A0h], rbp
0x18000e341  mov     [rcx+0A8h], ebp
0x18000e347  mov     dword ptr [rbx+0E8h], 1
0x18000e351  call    ?BindCheckList@ADDRESS_CHECK@@QEAAHPEAEK@Z; ADDRESS_CHECK::BindCheckList(uchar *,ulong)
0x18000e356  lea     ecx, [rbp+38h]; Size
0x18000e359  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e35e  mov     rdi, rax
0x18000e361  test    rax, rax
0x18000e364  jz      short loc_18000E3B5
0x18000e366  lea     rax, ??_7CAggregatorDispMgr@@6B@; const CAggregatorDispMgr::`vftable'
0x18000e36d  mov     [rdi+10h], rbp
0x18000e371  mov     r9, rbx; void *
0x18000e374  mov     [rdi], rax
0x18000e377  lea     r8, IID_IISIPSecurity; struct _GUID *
0x18000e37e  mov     [rdi+18h], rbp
0x18000e382  lea     rdx, LIBID_IISOle; struct _GUID *
0x18000e389  mov     [rdi+8], ebp
0x18000e38c  mov     rcx, rdi; this
0x18000e38f  mov     [rdi+20h], rbp
0x18000e393  mov     [rdi+28h], rbp
0x18000e397  mov     [rdi+30h], ebp
0x18000e39a  mov     [rsp+58h+var_38], 1; int
0x18000e3a2  call    ?LoadTypeInfoEntry@CAggregatorDispMgr@@QEAAJAEBU_GUID@@0PEAXJ@Z; CAggregatorDispMgr::LoadTypeInfoEntry(_GUID const &,_GUID const &,void *,long)
0x18000e3a7  mov     esi, eax
0x18000e3a9  test    eax, eax
0x18000e3ab  jns     short loc_18000E3CA
0x18000e3ad  mov     rcx, rdi; this
0x18000e3b0  call    ??_GCAggregatorDispMgr@@QEAAPEAXI@Z; CAggregatorDispMgr::`scalar deleting destructor'(uint)
0x18000e3b5  mov     rcx, rbx; this
0x18000e3b8  call    ??_GCIPSecurity@@QEAAPEAXI@Z; CIPSecurity::`scalar deleting destructor'(uint)
0x18000e3bd  mov     eax, esi
0x18000e3bf  add     rsp, 30h
0x18000e3c3  pop     r14
0x18000e3c5  pop     rdi
0x18000e3c6  pop     rsi
0x18000e3c7  pop     rbp
0x18000e3c8  pop     rbx
0x18000e3c9  retn
0x18000e3ca  mov     [rbx+10h], rdi
0x18000e3ce  xor     eax, eax
0x18000e3d0  mov     [r14], rbx
0x18000e3d3  jmp     short loc_18000E3BF
```
