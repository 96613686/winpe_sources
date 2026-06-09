# CSyncServices::CreateReplicaKeyMap(uchar const *,IReplicaKeyMap * *)

- ea: `0x1800072e0`
- end: `0x1800073ba`
- name: `?CreateReplicaKeyMap@CSyncServices@@UEAAJPEBEPEAPEAUIReplicaKeyMap@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(CSyncServices *this, const unsigned __int8 *, struct IReplicaKeyMap **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002c510`

## callees

- `0x1800072e0`
- `0x1800073c0`
- `0x18001a038`
- `0x18001ae20`

## string_xrefs

- `0x18000736a`: `CSyncServices::CreateReplicaKeyMap`
- `0x180007396`: `CSyncServices::CreateReplicaKeyMap`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateReplicaKeyMap(
        CSyncServices *this,
        const unsigned __int8 *a2,
        struct IReplicaKeyMap **a3)
{
  PVOID *v6; // rcx
  struct _ID_PARAMETER_PAIR *v7; // rdx
  int v8; // eax
  unsigned int v9; // ebx
  struct _ID_PARAMETER_PAIR v11; // [rsp+60h] [rbp+8h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateReplicaKeyMap");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = (struct _ID_PARAMETER_PAIR *)*((_QWORD *)this + 6);
  if ( v7 )
  {
    v11 = *v7;
    *(&v11.cbIdSize + 1) = 0;
    v8 = KnowledgeServices::CreateReplicaKeyMap(&v11, a2, a3);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v9 = v8;
  }
  else
  {
    v9 = -2147217407;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      27,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateReplicaKeyMap",
      v9);
  return v9;
}

```

## disassembly

```asm
0x1800072e0  push    rbx
0x1800072e2  push    rbp
0x1800072e3  push    rsi
0x1800072e4  push    rdi
0x1800072e5  sub     rsp, 38h
0x1800072e9  mov     rdi, r8
0x1800072ec  mov     rsi, rdx
0x1800072ef  mov     rbx, rcx
0x1800072f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072f9  lea     rbp, WPP_GLOBAL_Control
0x180007300  cmp     rcx, rbp
0x180007303  jz      short loc_18000730B
0x180007305  test    byte ptr [rcx+1Ch], 2
0x180007309  jnz     short loc_180007388
0x18000730b  mov     rdx, [rbx+30h]
0x18000730f  test    rdx, rdx
0x180007312  jz      short loc_180007353
0x180007314  mov     eax, [rdx]
0x180007316  lea     rcx, [rsp+58h+arg_0]; struct _ID_PARAMETER_PAIR *
0x18000731b  mov     [rsp+58h+arg_0.fIsVariable], eax
0x18000731f  mov     r8, rdi; struct IReplicaKeyMap **
0x180007322  movzx   eax, word ptr [rdx+4]
0x180007326  mov     rdx, rsi; unsigned __int8 *
0x180007329  mov     [rsp+58h+arg_0.cbIdSize], ax
0x18000732e  xor     eax, eax
0x180007330  mov     word ptr [rsp+58h+arg_0+6], ax
0x180007335  call    ?CreateReplicaKeyMap@KnowledgeServices@@SAJAEBU_ID_PARAMETER_PAIR@@PEBEPEAPEAUIReplicaKeyMap@@@Z; KnowledgeServices::CreateReplicaKeyMap(_ID_PARAMETER_PAIR const &,uchar const *,IReplicaKeyMap * *)
0x18000733a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007341  mov     ebx, eax
0x180007343  cmp     rcx, rbp
0x180007346  jnz     short loc_18000735A
0x180007348  mov     eax, ebx
0x18000734a  add     rsp, 38h
0x18000734e  pop     rdi
0x18000734f  pop     rsi
0x180007350  pop     rbp
0x180007351  pop     rbx
0x180007352  retn
0x180007353  mov     ebx, 80041001h
0x180007358  jmp     short loc_180007343
0x18000735a  test    byte ptr [rcx+1Ch], 2
0x18000735e  jz      short loc_180007348
0x180007360  cmp     byte ptr [rcx+19h], 5
0x180007364  jb      short loc_180007348
0x180007366  mov     rcx, [rcx+10h]
0x18000736a  lea     r9, aCsyncservicesC_15; "CSyncServices::CreateReplicaKeyMap"
0x180007371  mov     edx, 1Bh
0x180007376  mov     [rsp+58h+var_38], ebx
0x18000737a  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x180007381  call    WPP_SF_sD
0x180007386  jmp     short loc_180007348
0x180007388  cmp     byte ptr [rcx+19h], 5
0x18000738c  jb      loc_18000730B
0x180007392  mov     rcx, [rcx+10h]
0x180007396  lea     r9, aCsyncservicesC_15; "CSyncServices::CreateReplicaKeyMap"
0x18000739d  mov     edx, 1Ah
0x1800073a2  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x1800073a9  call    WPP_SF_s
0x1800073ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073b5  jmp     loc_18000730B
```
