# std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x140007854`
- end: `0x1400078e5`
- name: `??1_Clear_guard@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA@XZ`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140007484`

## callees

- `0x140007854`
- `0x14001382c`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::_Clear_guard::~_Clear_guard(
        unsigned __int64 **a1)
{
  unsigned __int64 *v1; // rbx
  _QWORD **v2; // rcx
  _QWORD *v3; // rcx
  _QWORD *v4; // rdi
  void *v5; // rdi
  unsigned __int64 v6; // rcx

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = (_QWORD **)v1[1];
    *v2[1] = 0;
    v3 = *v2;
    if ( v3 )
    {
      do
      {
        v4 = (_QWORD *)*v3;
        operator delete(v3);
        v3 = v4;
      }
      while ( v4 );
    }
    *(_QWORD *)v1[1] = v1[1];
    *(_QWORD *)(v1[1] + 8) = v1[1];
    v1[2] = 0;
    v5 = (void *)v1[3];
    v6 = (v1[4] - (unsigned __int64)v5 + 7) >> 3;
    if ( (unsigned __int64)v5 > v1[4] )
      v6 = 0;
    if ( v6 )
      memset64(v5, v1[1], v6);
  }
}

```

## disassembly

```asm
0x140007854  mov     [rsp+arg_8], rbx
0x140007859  mov     [rsp+arg_10], rsi
0x14000785e  push    rdi
0x14000785f  sub     rsp, 20h
0x140007863  mov     rbx, [rcx]
0x140007866  xor     esi, esi
0x140007868  test    rbx, rbx
0x14000786b  jz      short loc_1400078D5
0x14000786d  cmp     [rbx+10h], rsi
0x140007871  jz      short loc_1400078D5
0x140007873  mov     rcx, [rbx+8]
0x140007877  mov     rax, [rcx+8]
0x14000787b  mov     [rax], rsi
0x14000787e  mov     rcx, [rcx]; Block
0x140007881  test    rcx, rcx
0x140007884  jz      short loc_14000789B
0x140007886  mov     rdi, [rcx]
0x140007889  mov     edx, 28h ; '('
0x14000788e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007893  mov     rcx, rdi
0x140007896  test    rdi, rdi
0x140007899  jnz     short loc_140007886
0x14000789b  mov     rax, [rbx+8]
0x14000789f  mov     [rax], rax
0x1400078a2  mov     rax, [rbx+8]
0x1400078a6  mov     [rax+8], rax
0x1400078aa  mov     [rbx+10h], rsi
0x1400078ae  mov     rdi, [rbx+18h]
0x1400078b2  mov     rcx, [rbx+20h]
0x1400078b6  sub     rcx, rdi
0x1400078b9  add     rcx, 7
0x1400078bd  shr     rcx, 3
0x1400078c1  cmp     rdi, [rbx+20h]
0x1400078c5  cmova   rcx, rsi
0x1400078c9  test    rcx, rcx
0x1400078cc  jz      short loc_1400078D5
0x1400078ce  mov     rax, [rbx+8]
0x1400078d2  rep stosq
0x1400078d5  mov     rbx, [rsp+28h+arg_8]
0x1400078da  mov     rsi, [rsp+28h+arg_10]
0x1400078df  add     rsp, 20h
0x1400078e3  pop     rdi
0x1400078e4  retn
```
