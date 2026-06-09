# BfeIPsecTunnelAddKeyingPolicy

- ea: `0x18002e2f0`
- end: `0x18002e430`
- name: `BfeIPsecTunnelAddKeyingPolicy`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002e8a0`

## callees

- `0x180007cd0`
- `0x180012d8c`
- `0x1800197d0`
- `0x18002e2f0`
- `0x180030154`
- `0x180036e40`
- `0x18005aa60`
- `0x18005b4fc`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18002e344`
- `RPCRT4!UuidCreate` at `0x18002e344`

## string_xrefs

- `0x18002e3f3`: `UuidCreate`
- `0x18008c34c`: `BfeObjectAddCopyAndAssociate`

## pseudocode

```c
__int64 __fastcall BfeIPsecTunnelAddKeyingPolicy(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // eax
  __int64 v9; // rcx
  __int128 v10; // xmm0
  __int128 v11; // xmm0
  __int64 v12; // rbx
  _QWORD v14[3]; // [rsp+28h] [rbp-51h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-39h] BYREF
  __int128 v16; // [rsp+50h] [rbp-29h]
  __int64 v17; // [rsp+68h] [rbp-11h]
  __int128 v18; // [rsp+70h] [rbp-9h]
  int v19; // [rsp+80h] [rbp+7h]
  _QWORD *v20; // [rsp+88h] [rbp+Fh]

  v14[0] = 1;
  v14[2] = 0;
  memset_0(&Uuid, 0, 0x58u);
  v14[1] = a4;
  v8 = UuidCreate(&Uuid);
  if ( v8 )
  {
    v12 = WfpReportSysErrorAsWinError(v9, "UuidCreate", v8);
  }
  else
  {
    v10 = *(_OWORD *)(a2 + 16);
    v17 = *(_QWORD *)(a2 + 40);
    v16 = v10;
    v11 = *(_OWORD *)(a2 + 48);
    v19 = 0;
    v20 = v14;
    v18 = v11;
    v12 = BfeObjectAddCopy(1, &Uuid, a3);
    if ( v12 || (v12 = BfeObjectAssociate(1, (_QWORD *)((a1 - 144) & -(__int64)(a1 != 0)), 0)) != 0 )
      WfpReportError(v12, "BfeObjectAddCopyAndAssociate");
  }
  if ( v12 )
    WfpReportError(v12, "BfeIPsecTunnelAddKeyingPolicy");
  return v12;
}

```

## disassembly

```asm
0x18002e2f0  push    rbp
0x18002e2f2  push    rbx
0x18002e2f3  push    rsi
0x18002e2f4  push    rdi
0x18002e2f5  push    r14
0x18002e2f7  lea     rbp, [rsp-37h]
0x18002e2fc  sub     rsp, 0B0h
0x18002e303  mov     rax, cs:__security_cookie
0x18002e30a  xor     rax, rsp
0x18002e30d  mov     [rbp+57h+var_30], rax
0x18002e311  mov     rdi, rdx
0x18002e314  mov     [rbp+57h+var_A8], 1
0x18002e31c  xor     edx, edx; Val
0x18002e31e  mov     [rbp+57h+var_98], 0
0x18002e326  mov     r14, r8
0x18002e329  mov     rsi, rcx
0x18002e32c  lea     rcx, [rbp+57h+Uuid]; void *
0x18002e330  mov     rbx, r9
0x18002e333  lea     r8d, [rdx+58h]; Size
0x18002e337  call    memset_0
0x18002e33c  lea     rcx, [rbp+57h+Uuid]; Uuid
0x18002e340  mov     [rbp+57h+var_A0], rbx
0x18002e344  call    cs:__imp_UuidCreate
0x18002e34b  nop     dword ptr [rax+rax+00h]
0x18002e350  test    eax, eax
0x18002e352  jnz     loc_18002E3F0
0x18002e358  movups  xmm0, xmmword ptr [rdi+10h]
0x18002e35c  mov     rax, [rdi+28h]
0x18002e360  lea     r9, [rbp+57h+var_B0]
0x18002e364  mov     [rbp+57h+var_68], rax
0x18002e368  lea     rdx, [rbp+57h+Uuid]
0x18002e36c  movdqu  [rbp+57h+var_80], xmm0
0x18002e371  lea     rax, [rbp+57h+var_A8]
0x18002e375  mov     r8, r14
0x18002e378  movups  xmm0, xmmword ptr [rdi+30h]
0x18002e37c  mov     ecx, 1
0x18002e381  mov     [rbp+57h+var_50], 0
0x18002e388  mov     [rbp+57h+var_48], rax
0x18002e38c  movdqu  [rbp+57h+var_60], xmm0
0x18002e391  mov     [rbp+57h+var_B0], 0
0x18002e399  call    BfeObjectAddCopy
0x18002e39e  mov     rdi, [rbp+57h+var_B0]
0x18002e3a2  mov     rbx, rax
0x18002e3a5  test    rax, rax
0x18002e3a8  jnz     short loc_18002E404
0x18002e3aa  lea     rax, [rsi-90h]
0x18002e3b1  mov     r8, rdi
0x18002e3b4  neg     rsi
0x18002e3b7  lea     ecx, [rbx+1]
0x18002e3ba  sbb     rdx, rdx
0x18002e3bd  and     rdx, rax
0x18002e3c0  call    BfeObjectAssociate
0x18002e3c5  mov     rbx, rax
0x18002e3c8  test    rax, rax
0x18002e3cb  jnz     short loc_18002E404
0x18002e3cd  test    rbx, rbx
0x18002e3d0  jnz     short loc_18002E41F
0x18002e3d2  mov     rax, rbx
0x18002e3d5  mov     rcx, [rbp+57h+var_30]
0x18002e3d9  xor     rcx, rsp; StackCookie
0x18002e3dc  call    __security_check_cookie
0x18002e3e1  add     rsp, 0B0h
0x18002e3e8  pop     r14
0x18002e3ea  pop     rdi
0x18002e3eb  pop     rsi
0x18002e3ec  pop     rbx
0x18002e3ed  pop     rbp
0x18002e3ee  retn
0x18002e3f0  mov     r8d, eax
0x18002e3f3  lea     rdx, aUuidcreate; "UuidCreate"
0x18002e3fa  call    WfpReportSysErrorAsWinError
0x18002e3ff  mov     rbx, rax
0x18002e402  jmp     short loc_18002E3CD
0x18002e404  test    rdi, rdi
0x18002e407  jz      loc_18008C34C
0x18002e40d  mov     rcx, rdi
0x18002e410  call    BfeObjectDeleteAlways
0x18002e415  test    rbx, rbx
0x18002e418  jz      short loc_18002E3D2
0x18002e41a  jmp     loc_18008C34C
0x18002e41f  lea     rdx, aBfeipsectunnel_0; "BfeIPsecTunnelAddKeyingPolicy"
0x18002e426  mov     rcx, rbx
0x18002e429  call    WfpReportError
0x18002e42e  jmp     short loc_18002E3D2
0x18008c34c  lea     rdx, aBfeobjectaddco_1; "BfeObjectAddCopyAndAssociate"
0x18008c353  mov     rcx, rbx
0x18008c356  call    WfpReportError
0x18008c35b  nop
0x18008c35c  jmp     loc_18002E3CD
```
