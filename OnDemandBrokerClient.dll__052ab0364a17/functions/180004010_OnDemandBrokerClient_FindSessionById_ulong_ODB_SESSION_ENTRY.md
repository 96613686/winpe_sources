# OnDemandBrokerClient::FindSessionById(ulong,_ODB_SESSION_ENTRY * *)

- ea: `0x180004010`
- end: `0x18000403a`
- name: `?FindSessionById@OnDemandBrokerClient@@AEAAJKPEAPEAU_ODB_SESSION_ENTRY@@@Z`
- size: `42`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *this, int, struct _ODB_SESSION_ENTRY **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005230`
- `0x180005b70`

## callees

- `0x180004010`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::FindSessionById(
        OnDemandBrokerClient *this,
        int a2,
        struct _ODB_SESSION_ENTRY **a3)
{
  struct _ODB_SESSION_ENTRY *v3; // rax
  struct _ODB_SESSION_ENTRY *v4; // rcx

  v3 = (struct _ODB_SESSION_ENTRY *)*((_QWORD *)this + 11);
  v4 = (OnDemandBrokerClient *)((char *)this + 88);
  while ( 1 )
  {
    if ( v3 == v4 )
      return 2147943568LL;
    if ( a2 == *((_DWORD *)v3 + 4) )
      break;
    v3 = *(struct _ODB_SESSION_ENTRY **)v3;
  }
  if ( a3 )
    *a3 = v3;
  return 0;
}

```

## disassembly

```asm
0x180004010  mov     rax, [rcx+58h]
0x180004014  add     rcx, 58h ; 'X'
0x180004018  cmp     rax, rcx
0x18000401b  jz      short loc_18000402F
0x18000401d  cmp     edx, [rax+10h]
0x180004020  jz      short loc_180004027
0x180004022  mov     rax, [rax]
0x180004025  jmp     short loc_180004018
0x180004027  test    r8, r8
0x18000402a  jnz     short loc_180004035
0x18000402c  xor     eax, eax
0x18000402e  retn
0x18000402f  mov     eax, 80070490h
0x180004034  retn
0x180004035  mov     [r8], rax
0x180004038  jmp     short loc_18000402C
```
