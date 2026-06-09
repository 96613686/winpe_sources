# std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x1400076f8`
- end: `0x140007789`
- name: `??1_Clear_guard@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@QEAA@XZ`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140006ed0`

## callees

- `0x1400076f8`
- `0x14001382c`

## pseudocode

```c
void __fastcall std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Clear_guard::~_Clear_guard(
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
0x1400076f8  mov     [rsp+arg_8], rbx
0x1400076fd  mov     [rsp+arg_10], rsi
0x140007702  push    rdi
0x140007703  sub     rsp, 20h
0x140007707  mov     rbx, [rcx]
0x14000770a  xor     esi, esi
0x14000770c  test    rbx, rbx
0x14000770f  jz      short loc_140007779
0x140007711  cmp     [rbx+10h], rsi
0x140007715  jz      short loc_140007779
0x140007717  mov     rcx, [rbx+8]
0x14000771b  mov     rax, [rcx+8]
0x14000771f  mov     [rax], rsi
0x140007722  mov     rcx, [rcx]; Block
0x140007725  test    rcx, rcx
0x140007728  jz      short loc_14000773F
0x14000772a  mov     rdi, [rcx]
0x14000772d  mov     edx, 20h ; ' '
0x140007732  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007737  mov     rcx, rdi
0x14000773a  test    rdi, rdi
0x14000773d  jnz     short loc_14000772A
0x14000773f  mov     rax, [rbx+8]
0x140007743  mov     [rax], rax
0x140007746  mov     rax, [rbx+8]
0x14000774a  mov     [rax+8], rax
0x14000774e  mov     [rbx+10h], rsi
0x140007752  mov     rdi, [rbx+18h]
0x140007756  mov     rcx, [rbx+20h]
0x14000775a  sub     rcx, rdi
0x14000775d  add     rcx, 7
0x140007761  shr     rcx, 3
0x140007765  cmp     rdi, [rbx+20h]
0x140007769  cmova   rcx, rsi
0x14000776d  test    rcx, rcx
0x140007770  jz      short loc_140007779
0x140007772  mov     rax, [rbx+8]
0x140007776  rep stosq
0x140007779  mov     rbx, [rsp+28h+arg_8]
0x14000777e  mov     rsi, [rsp+28h+arg_10]
0x140007783  add     rsp, 20h
0x140007787  pop     rdi
0x140007788  retn
```
