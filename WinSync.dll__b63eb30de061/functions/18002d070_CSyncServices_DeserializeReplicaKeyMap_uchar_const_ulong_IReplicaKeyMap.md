# CSyncServices::DeserializeReplicaKeyMap(uchar const *,ulong,IReplicaKeyMap * *)

- ea: `0x18002d070`
- end: `0x18002d158`
- name: `?DeserializeReplicaKeyMap@CSyncServices@@UEAAJPEBEKPEAPEAUIReplicaKeyMap@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(CSyncServices *this, const unsigned __int8 *, unsigned int, struct IReplicaKeyMap **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18002d160`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180027a68`
- `0x18002d070`

## string_xrefs

- `0x18002d0b1`: `CSyncServices::DeserializeReplicaKeyMap`
- `0x18002d127`: `CSyncServices::DeserializeReplicaKeyMap`

## pseudocode

```c
__int64 __fastcall CSyncServices::DeserializeReplicaKeyMap(
        CSyncServices *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        struct IReplicaKeyMap **a4)
{
  PVOID *v8; // rcx
  struct _ID_PARAMETER_PAIR *v9; // rdx
  unsigned int v10; // ebx
  unsigned int v11; // eax
  struct _ID_PARAMETER_PAIR v13; // [rsp+50h] [rbp+8h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::DeserializeReplicaKeyMap");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = (struct _ID_PARAMETER_PAIR *)*((_QWORD *)this + 6);
  if ( v9 )
  {
    v13 = *v9;
    *(&v13.cbIdSize + 1) = 0;
    v11 = KnowledgeServices::DeserializeReplicaKeyMap(&v13, a2, a3, a4);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v10 = v11;
  }
  else
  {
    v10 = -2147217407;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v8[2],
      29,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::DeserializeReplicaKeyMap",
      v10);
  return v10;
}

```

## disassembly

```asm
0x18002d070  mov     [rsp+arg_8], rbx
0x18002d075  mov     [rsp+arg_10], rbp
0x18002d07a  push    rsi
0x18002d07b  push    rdi
0x18002d07c  push    r14
0x18002d07e  sub     rsp, 30h
0x18002d082  mov     rdi, r9
0x18002d085  mov     esi, r8d
0x18002d088  mov     rbp, rdx
0x18002d08b  mov     rbx, rcx
0x18002d08e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d095  lea     r14, WPP_GLOBAL_Control
0x18002d09c  cmp     rcx, r14
0x18002d09f  jz      short loc_18002D0D0
0x18002d0a1  test    byte ptr [rcx+1Ch], 2
0x18002d0a5  jz      short loc_18002D0D0
0x18002d0a7  cmp     byte ptr [rcx+19h], 5
0x18002d0ab  jb      short loc_18002D0D0
0x18002d0ad  mov     rcx, [rcx+10h]
0x18002d0b1  lea     r9, aCsyncservicesD_5; "CSyncServices::DeserializeReplicaKeyMap"
0x18002d0b8  mov     edx, 1Ch
0x18002d0bd  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002d0c4  call    WPP_SF_s
0x18002d0c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0d0  mov     rdx, [rbx+30h]
0x18002d0d4  test    rdx, rdx
0x18002d0d7  jnz     short loc_18002D0E0
0x18002d0d9  mov     ebx, 80041001h
0x18002d0de  jmp     short loc_18002D112
0x18002d0e0  mov     eax, [rdx]
0x18002d0e2  lea     rcx, [rsp+48h+arg_0]; struct _ID_PARAMETER_PAIR *
0x18002d0e7  mov     [rsp+48h+arg_0.fIsVariable], eax
0x18002d0eb  mov     r9, rdi; struct IReplicaKeyMap **
0x18002d0ee  movzx   eax, word ptr [rdx+4]
0x18002d0f2  mov     r8d, esi; unsigned int
0x18002d0f5  mov     [rsp+48h+arg_0.cbIdSize], ax
0x18002d0fa  mov     rdx, rbp; unsigned __int8 *
0x18002d0fd  xor     eax, eax
0x18002d0ff  mov     word ptr [rsp+48h+arg_0+6], ax
0x18002d104  call    ?DeserializeReplicaKeyMap@KnowledgeServices@@SAJAEBU_ID_PARAMETER_PAIR@@PEBEKPEAPEAUIReplicaKeyMap@@@Z; KnowledgeServices::DeserializeReplicaKeyMap(_ID_PARAMETER_PAIR const &,uchar const *,ulong,IReplicaKeyMap * *)
0x18002d109  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d110  mov     ebx, eax
0x18002d112  cmp     rcx, r14
0x18002d115  jz      short loc_18002D143
0x18002d117  test    byte ptr [rcx+1Ch], 2
0x18002d11b  jz      short loc_18002D143
0x18002d11d  cmp     byte ptr [rcx+19h], 5
0x18002d121  jb      short loc_18002D143
0x18002d123  mov     rcx, [rcx+10h]
0x18002d127  lea     r9, aCsyncservicesD_5; "CSyncServices::DeserializeReplicaKeyMap"
0x18002d12e  mov     edx, 1Dh
0x18002d133  mov     [rsp+48h+var_28], ebx
0x18002d137  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002d13e  call    WPP_SF_sD
0x18002d143  mov     rbp, [rsp+48h+arg_10]
0x18002d148  mov     eax, ebx
0x18002d14a  mov     rbx, [rsp+48h+arg_8]
0x18002d14f  add     rsp, 30h
0x18002d153  pop     r14
0x18002d155  pop     rdi
0x18002d156  pop     rsi
0x18002d157  retn
```
