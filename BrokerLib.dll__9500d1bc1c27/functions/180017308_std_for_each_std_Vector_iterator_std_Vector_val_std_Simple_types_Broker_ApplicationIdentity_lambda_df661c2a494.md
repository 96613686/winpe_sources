# std::for_each_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_Broker::ApplicationIdentity_______lambda_df661c2a494d52659c55fd0f8700369c___

- ea: `0x180017308`
- end: `0x1800173ab`
- name: `std::for_each_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_Broker::ApplicationIdentity_______lambda_df661c2a494d52659c55fd0f8700369c___`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c970`

## callees

- `0x180001120`
- `0x180004ae0`
- `0x180007be0`
- `0x180017308`

## pseudocode

```c
_QWORD *__fastcall std::for_each_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_Broker::ApplicationIdentity_______lambda_df661c2a494d52659c55fd0f8700369c___(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 i; // rsi
  const wchar_t *v8; // rax
  __int64 v10; // [rsp+30h] [rbp-38h] BYREF
  std::_Ref_count_base *v11; // [rsp+38h] [rbp-30h]

  for ( i = a2; i != a3; i += 88 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v8 = (const wchar_t *)(i + 56);
      if ( *(_QWORD *)(i + 80) > 7u )
        v8 = *(const wchar_t **)v8;
      WPP_SF__sid_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0x33u,
        &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
        *(char **)i,
        v8);
    }
    Broker::ApplicationStateTable::CreateApplicationState(*(_QWORD *)(a4 + 272), &v10, i);
    ++*(_DWORD *)(v10 + 140);
    if ( v11 )
      std::_Ref_count_base::_Decref(v11);
  }
  *a1 = a4;
  return a1;
}

```

## disassembly

```asm
0x180017308  push    rbx
0x18001730a  push    rsi
0x18001730b  push    rdi
0x18001730c  push    r14
0x18001730e  sub     rsp, 48h
0x180017312  mov     rbx, r9
0x180017315  mov     rdi, r8
0x180017318  mov     rsi, rdx
0x18001731b  mov     r14, rcx
0x18001731e  cmp     rdx, r8
0x180017321  jz      short loc_18001739B
0x180017323  mov     rcx, cs:WPP_GLOBAL_Control
0x18001732a  test    dword ptr [rcx+1Ch], 800h
0x180017331  jz      short loc_180017364
0x180017333  cmp     byte ptr [rcx+19h], 5
0x180017337  jb      short loc_180017364
0x180017339  cmp     qword ptr [rsi+50h], 7
0x18001733e  lea     rax, [rsi+38h]
0x180017342  jbe     short loc_180017347
0x180017344  mov     rax, [rax]
0x180017347  mov     r9, [rsi]
0x18001734a  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180017351  mov     rcx, [rcx+10h]; LoggerHandle
0x180017355  mov     edx, 33h ; '3'
0x18001735a  mov     [rsp+68h+var_48], rax; __int64
0x18001735f  call    WPP_SF__sid_S
0x180017364  mov     rcx, [rbx+110h]
0x18001736b  lea     rdx, [rsp+68h+var_38]
0x180017370  mov     r8, rsi
0x180017373  call    ?CreateApplicationState@ApplicationStateTable@Broker@@QEAA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@AEBUApplicationIdentity@2@@Z; Broker::ApplicationStateTable::CreateApplicationState(Broker::ApplicationIdentity const &)
0x180017378  mov     rax, [rsp+68h+var_38]
0x18001737d  inc     dword ptr [rax+8Ch]
0x180017383  mov     rcx, [rsp+68h+var_30]; this
0x180017388  test    rcx, rcx
0x18001738b  jz      short loc_180017392
0x18001738d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017392  add     rsi, 58h ; 'X'
0x180017396  cmp     rsi, rdi
0x180017399  jnz     short loc_180017323
0x18001739b  mov     [r14], rbx
0x18001739e  mov     rax, r14
0x1800173a1  add     rsp, 48h
0x1800173a5  pop     r14
0x1800173a7  pop     rdi
0x1800173a8  pop     rsi
0x1800173a9  pop     rbx
0x1800173aa  retn
```
