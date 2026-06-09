# OnDemandBrokerClient::QueryInterface(_GUID const &,void * *)

- ea: `0x180004200`
- end: `0x1800042b2`
- name: `?QueryInterface@OnDemandBrokerClient@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `178`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005f40`
- `0x180005f50`

## callees

- `0x180004200`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::QueryInterface(OnDemandBrokerClient *this, const struct _GUID *a2, void **a3)
{
  OnDemandBrokerClient *v3; // r9
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax

  v3 = this;
  if ( !a3 )
    return 2147942487LL;
  v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_2b919653_22cc_4e45_a4f6_75501c927355.Data1;
  if ( !v5 )
    v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_2b919653_22cc_4e45_a4f6_75501c927355.Data4;
  if ( v5 )
  {
    v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_605f4e9c_15db_4d5e_8c8d_1592cab61863.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_605f4e9c_15db_4d5e_8c8d_1592cab61863.Data1 )
      v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_605f4e9c_15db_4d5e_8c8d_1592cab61863.Data4;
    if ( v6 )
    {
      v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_4d17f09c_1b17_4fd6_b57e_bd858b2f04b3.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_4d17f09c_1b17_4fd6_b57e_bd858b2f04b3.Data1 )
        v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_4d17f09c_1b17_4fd6_b57e_bd858b2f04b3.Data4;
      if ( v7 )
      {
        *a3 = 0;
        return 2147500034LL;
      }
      this = (OnDemandBrokerClient *)((char *)this + 16);
    }
    else
    {
      this = (OnDemandBrokerClient *)((char *)this + 8);
    }
    if ( !v3 )
      this = 0;
  }
  *a3 = this;
  if ( this )
    (*(void (__fastcall **)(OnDemandBrokerClient *))(*(_QWORD *)v3 + 8LL))(v3);
  return 0;
}

```

## disassembly

```asm
0x180004200  sub     rsp, 28h
0x180004204  mov     r9, rcx
0x180004207  test    r8, r8
0x18000420a  jnz     short loc_180004216
0x18000420c  mov     eax, 80070057h
0x180004211  add     rsp, 28h
0x180004215  retn
0x180004216  mov     rax, [rdx]
0x180004219  mov     [rsp+28h+var_8], rbx
0x18000421e  xor     ebx, ebx
0x180004220  sub     rax, qword ptr cs:_GUID_2b919653_22cc_4e45_a4f6_75501c927355.Data1
0x180004227  jnz     short loc_180004234
0x180004229  mov     rax, [rdx+8]
0x18000422d  sub     rax, qword ptr cs:_GUID_2b919653_22cc_4e45_a4f6_75501c927355.Data4
0x180004234  test    rax, rax
0x180004237  jnz     short loc_18000424A
0x180004239  mov     [r8], rcx
0x18000423c  test    rcx, rcx
0x18000423f  jnz     short loc_1800042A1
0x180004241  mov     eax, ebx
0x180004243  mov     rbx, [rsp+28h+var_8]
0x180004248  jmp     short loc_180004211
0x18000424a  mov     rax, [rdx]
0x18000424d  sub     rax, qword ptr cs:_GUID_605f4e9c_15db_4d5e_8c8d_1592cab61863.Data1
0x180004254  jnz     short loc_180004261
0x180004256  mov     rax, [rdx+8]
0x18000425a  sub     rax, qword ptr cs:_GUID_605f4e9c_15db_4d5e_8c8d_1592cab61863.Data4
0x180004261  test    rax, rax
0x180004264  jz      short loc_180004288
0x180004266  mov     rax, [rdx]
0x180004269  sub     rax, qword ptr cs:_GUID_4d17f09c_1b17_4fd6_b57e_bd858b2f04b3.Data1
0x180004270  jnz     short loc_18000427D
0x180004272  mov     rax, [rdx+8]
0x180004276  sub     rax, qword ptr cs:_GUID_4d17f09c_1b17_4fd6_b57e_bd858b2f04b3.Data4
0x18000427d  test    rax, rax
0x180004280  jnz     short loc_180004297
0x180004282  add     rcx, 10h
0x180004286  jmp     short loc_18000428C
0x180004288  add     rcx, 8
0x18000428c  xor     eax, eax
0x18000428e  test    r9, r9
0x180004291  cmovz   rcx, rax
0x180004295  jmp     short loc_180004239
0x180004297  mov     [r8], rbx
0x18000429a  mov     eax, 80004002h
0x18000429f  jmp     short loc_180004243
0x1800042a1  mov     rcx, [r9]
0x1800042a4  mov     rax, [rcx+8]
0x1800042a8  mov     rcx, r9
0x1800042ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042b0  jmp     short loc_180004241
```
