# CheckRpcClientIdentity(ulong,int *)

- ea: `0x140022a08`
- end: `0x140022ac2`
- name: `?CheckRpcClientIdentity@@YAJKPEAH@Z`
- size: `186`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14001fe80`
- `0x14001ffe0`

## callees

- `0x14001da70`
- `0x14002233c`
- `0x140022a08`
- `0x140022c00`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x140022a2c`
- `RPCRT4!RpcImpersonateClient` at `0x140022a2c`

## pseudocode

```c
__int64 __fastcall CheckRpcClientIdentity(__int64 a1, int *a2)
{
  unsigned int v4; // edx
  void *v5; // rcx
  RPC_STATUS v6; // ebx
  unsigned int v7; // ebx

  if ( !a2 )
    return 2147942487LL;
  *a2 = 0;
  v6 = RpcImpersonateClient(0);
  if ( v6 )
  {
    v7 = v6 | 0x80010000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids, v7);
  }
  else
  {
    v7 = CheckClientIdentity(v5, v4, a2);
    if ( (v7 & 0x80000000) != 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids, v7);
    }
    MpRpcRevertToSelf();
  }
  return v7;
}

```

## disassembly

```asm
0x140022a08  mov     [rsp+arg_0], rbx
0x140022a0d  push    rdi
0x140022a0e  sub     rsp, 20h
0x140022a12  mov     rdi, rdx
0x140022a15  test    rdx, rdx
0x140022a18  jnz     short loc_140022A24
0x140022a1a  mov     eax, 80070057h
0x140022a1f  jmp     loc_140022AB7
0x140022a24  xor     ecx, ecx; BindingHandle
0x140022a26  mov     dword ptr [rdx], 0
0x140022a2c  call    cs:__imp_RpcImpersonateClient
0x140022a32  mov     ebx, eax
0x140022a34  test    eax, eax
0x140022a36  jz      short loc_140022A71
0x140022a38  or      ebx, 80010000h
0x140022a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140022a45  lea     rax, WPP_GLOBAL_Control
0x140022a4c  cmp     rcx, rax
0x140022a4f  jz      short loc_140022AB5
0x140022a51  test    byte ptr [rcx+1Ch], 1
0x140022a55  jz      short loc_140022AB5
0x140022a57  mov     rcx, [rcx+10h]
0x140022a5b  lea     r8, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids
0x140022a62  mov     edx, 0Eh
0x140022a67  mov     r9d, ebx
0x140022a6a  call    WPP_SF_d
0x140022a6f  jmp     short loc_140022AB5
0x140022a71  mov     r8, rdi; int *
0x140022a74  call    ?CheckClientIdentity@@YAJPEAXKPEAH@Z; CheckClientIdentity(void *,ulong,int *)
0x140022a79  mov     ebx, eax
0x140022a7b  test    eax, eax
0x140022a7d  jns     short loc_140022AB0
0x140022a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140022a86  lea     rax, WPP_GLOBAL_Control
0x140022a8d  cmp     rcx, rax
0x140022a90  jz      short loc_140022AB0
0x140022a92  test    byte ptr [rcx+1Ch], 1
0x140022a96  jz      short loc_140022AB0
0x140022a98  mov     rcx, [rcx+10h]
0x140022a9c  lea     r8, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids
0x140022aa3  mov     edx, 0Fh
0x140022aa8  mov     r9d, ebx
0x140022aab  call    WPP_SF_d
0x140022ab0  call    ?MpRpcRevertToSelf@@YAXXZ; MpRpcRevertToSelf(void)
0x140022ab5  mov     eax, ebx
0x140022ab7  mov     rbx, [rsp+28h+arg_0]
0x140022abc  add     rsp, 20h
0x140022ac0  pop     rdi
0x140022ac1  retn
```
