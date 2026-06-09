# Broker::ApplicationIdentity::~ApplicationIdentity(void)

- ea: `0x180004d70`
- end: `0x180004e31`
- name: `??1ApplicationIdentity@Broker@@QEAA@XZ`
- size: `193`
- prototype: `void __fastcall(Broker::ApplicationIdentity *__hidden this)`
- caller_count: `29`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001208`
- `0x180001450`
- `0x180004c70`
- `0x180004ca8`
- `0x180007be0`
- `0x180008724`
- `0x1800087e8`
- `0x180009460`
- `0x180009bb0`
- `0x180009ee0`
- `0x18000b918`
- `0x18000c4c0`
- `0x1800110a0`
- `0x180014a7c`
- `0x180014f50`
- `0x180017578`
- `0x18001764c`
- `0x1800178fc`
- `0x1800187b8`
- `0x1800188c0`
- `0x18001ab8c`
- `0x18001af20`
- `0x18001b5b5`
- `0x18001bffc`
- `0x18001c674`
- `0x18001c8a8`
- `0x18001ca86`
- `0x18001d9f5`
- `0x18001da6a`

## callees

- `0x180004d70`
- `0x180004e38`
- `0x180014898`
- `0x180015b58`

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
    std::_Deallocate<16>(*((_QWORD *)this + 7), 2 * v1 + 2);
  *((_QWORD *)this + 10) = 7;
  *((_QWORD *)this + 9) = 0;
  *((_WORD *)this + 28) = 0;
  v3 = *((_QWORD *)this + 6);
  if ( v3 > 7 )
    std::_Deallocate<16>(*((_QWORD *)this + 3), 2 * v3 + 2);
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
0x180004d70  mov     [rsp+arg_10], rbx
0x180004d75  push    rdi
0x180004d76  sub     rsp, 20h
0x180004d7a  mov     rdx, [rcx+50h]
0x180004d7e  mov     rbx, rcx
0x180004d81  cmp     rdx, 7
0x180004d85  ja      short loc_180004DF0
0x180004d87  xor     edi, edi
0x180004d89  mov     qword ptr [rbx+50h], 7
0x180004d91  mov     [rbx+48h], rdi
0x180004d95  mov     [rbx+38h], di
0x180004d99  mov     rdx, [rbx+30h]
0x180004d9d  cmp     rdx, 7
0x180004da1  ja      short loc_180004E03
0x180004da3  mov     [rbx+28h], rdi
0x180004da7  mov     qword ptr [rbx+30h], 7
0x180004daf  mov     [rbx+18h], di
0x180004db3  mov     rcx, [rbx]; void *
0x180004db6  test    rcx, rcx
0x180004db9  jz      short loc_180004DE5
0x180004dbb  mov     rdx, [rbx+10h]
0x180004dbf  sub     rdx, rcx; unsigned __int64
0x180004dc2  mov     [rsp+28h+arg_8], rcx
0x180004dc7  mov     [rsp+28h+arg_0], rdx
0x180004dcc  cmp     rdx, 1000h
0x180004dd3  jnb     short loc_180004E16
0x180004dd5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004dda  mov     [rbx], rdi
0x180004ddd  mov     [rbx+8], rdi
0x180004de1  mov     [rbx+10h], rdi
0x180004de5  mov     rbx, [rsp+28h+arg_10]
0x180004dea  add     rsp, 20h
0x180004dee  pop     rdi
0x180004def  retn
0x180004df0  mov     rcx, [rcx+38h]
0x180004df4  lea     rdx, ds:2[rdx*2]
0x180004dfc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180004e01  jmp     short loc_180004D87
0x180004e03  mov     rcx, [rbx+18h]
0x180004e07  lea     rdx, ds:2[rdx*2]
0x180004e0f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180004e14  jmp     short loc_180004DA3
0x180004e16  lea     rdx, [rsp+28h+arg_0]; unsigned __int64 *
0x180004e1b  lea     rcx, [rsp+28h+arg_8]; void **
0x180004e20  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180004e25  mov     rdx, [rsp+28h+arg_0]
0x180004e2a  mov     rcx, [rsp+28h+arg_8]
0x180004e2f  jmp     short loc_180004DD5
```
