# Broker::ApplicationIdentity::~ApplicationIdentity(void)

- ea: `0x18000f370`
- end: `0x18000f431`
- name: `??1ApplicationIdentity@Broker@@QEAA@XZ`
- size: `193`
- prototype: `void __fastcall(Broker::ApplicationIdentity *__hidden this)`
- caller_count: `35`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001b78`
- `0x1800022b0`
- `0x1800029c0`
- `0x180007880`
- `0x18000ec10`
- `0x18000f680`
- `0x180010560`
- `0x180016590`
- `0x180018754`
- `0x18001abbc`
- `0x18001aee0`
- `0x18001b5d0`
- `0x18001bb90`
- `0x18001e150`
- `0x18001ea70`
- `0x18001eba0`
- `0x18001fd50`
- `0x180021780`
- `0x1800224d0`
- `0x1800226c0`
- `0x1800227b4`
- `0x180023390`
- `0x180023490`
- `0x180023600`
- `0x180023b40`
- `0x180023db0`
- `0x180023fa0`
- `0x180024610`
- `0x1800248d0`
- `0x180024900`
- `0x1800257d8`
- `0x18002583a`
- `0x180025a1c`
- `0x180025d3e`
- `0x180025eab`

## callees

- `0x18000f370`
- `0x180019130`
- `0x18001d364`
- `0x18001e0d8`

## pseudocode

```c
void __fastcall Broker::ApplicationIdentity::~ApplicationIdentity(Broker::ApplicationIdentity *this)
{
  unsigned __int64 v1; // rdx
  unsigned __int64 v3; // rdx
  void *v4; // rcx
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  void *v7; // [rsp+38h] [rbp+10h] BYREF

  v1 = *((_QWORD *)this + 10);
  if ( v1 > 7 )
    std::_Deallocate<16>(*((void **)this + 7), 2 * v1 + 2);
  *((_QWORD *)this + 10) = 7;
  *((_QWORD *)this + 9) = 0;
  *((_WORD *)this + 28) = 0;
  v3 = *((_QWORD *)this + 6);
  if ( v3 > 7 )
    std::_Deallocate<16>(*((void **)this + 3), 2 * v3 + 2);
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 7;
  *((_WORD *)this + 12) = 0;
  v4 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    v5 = *((_QWORD *)this + 2) - (_QWORD)v4;
    v7 = *(void **)this;
    v6 = v5;
    if ( v5 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v7, &v6);
      v5 = v6;
      v4 = v7;
    }
    operator delete(v4, v5);
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x18000f370  mov     [rsp+arg_10], rbx
0x18000f375  push    rdi
0x18000f376  sub     rsp, 20h
0x18000f37a  mov     rdx, [rcx+50h]
0x18000f37e  mov     rbx, rcx
0x18000f381  cmp     rdx, 7
0x18000f385  ja      short loc_18000F3F0
0x18000f387  xor     edi, edi
0x18000f389  mov     qword ptr [rbx+50h], 7
0x18000f391  mov     [rbx+48h], rdi
0x18000f395  mov     [rbx+38h], di
0x18000f399  mov     rdx, [rbx+30h]
0x18000f39d  cmp     rdx, 7
0x18000f3a1  ja      short loc_18000F403
0x18000f3a3  mov     [rbx+28h], rdi
0x18000f3a7  mov     qword ptr [rbx+30h], 7
0x18000f3af  mov     [rbx+18h], di
0x18000f3b3  mov     rcx, [rbx]; void *
0x18000f3b6  test    rcx, rcx
0x18000f3b9  jz      short loc_18000F3E5
0x18000f3bb  mov     rdx, [rbx+10h]
0x18000f3bf  sub     rdx, rcx; unsigned __int64
0x18000f3c2  mov     [rsp+28h+arg_8], rcx
0x18000f3c7  mov     [rsp+28h+arg_0], rdx
0x18000f3cc  cmp     rdx, 1000h
0x18000f3d3  jnb     short loc_18000F416
0x18000f3d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f3da  mov     [rbx], rdi
0x18000f3dd  mov     [rbx+8], rdi
0x18000f3e1  mov     [rbx+10h], rdi
0x18000f3e5  mov     rbx, [rsp+28h+arg_10]
0x18000f3ea  add     rsp, 20h
0x18000f3ee  pop     rdi
0x18000f3ef  retn
0x18000f3f0  mov     rcx, [rcx+38h]
0x18000f3f4  lea     rdx, ds:2[rdx*2]
0x18000f3fc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f401  jmp     short loc_18000F387
0x18000f403  mov     rcx, [rbx+18h]
0x18000f407  lea     rdx, ds:2[rdx*2]
0x18000f40f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f414  jmp     short loc_18000F3A3
0x18000f416  lea     rdx, [rsp+28h+arg_0]; unsigned __int64 *
0x18000f41b  lea     rcx, [rsp+28h+arg_8]; void **
0x18000f420  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000f425  mov     rdx, [rsp+28h+arg_0]
0x18000f42a  mov     rcx, [rsp+28h+arg_8]
0x18000f42f  jmp     short loc_18000F3D5
```
