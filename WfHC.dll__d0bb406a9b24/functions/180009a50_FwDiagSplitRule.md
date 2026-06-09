# FwDiagSplitRule

- ea: `0x180009a50`
- end: `0x180009c0c`
- name: `FwDiagSplitRule`
- size: `444`
- prototype: `__int64 __fastcall(__int64, __int128 *, unsigned __int8)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180008b80`
- `0x180008e50`
- `0x1800096b0`
- `0x180009c20`
- `0x180009e10`
- `0x180009fb0`

## callees

- `0x180009a50`
- `0x18000c5b0`

## import_xrefs

- `FirewallAPI!FwFree` at `0x180009bb0`
- `FirewallAPI!FwFree` at `0x180009bb0`
- `FirewallAPI!FWSetFirewallRule` at `0x180009b45`
- `FirewallAPI!FWSetFirewallRule` at `0x180009b45`
- `FirewallAPI!FWAddFirewallRule` at `0x180009ba0`
- `FirewallAPI!FWAddFirewallRule` at `0x180009ba0`
- `fwbase!FwStringCopy` at `0x180009bc7`
- `fwbase!FwStringCopy` at `0x180009bc7`
- `RPCRT4!UuidCreate` at `0x180009b5d`
- `RPCRT4!UuidCreate` at `0x180009b5d`
- `RPCRT4!UuidToStringW` at `0x180009b76`
- `RPCRT4!UuidToStringW` at `0x180009b76`
- `RPCRT4!RpcStringFreeW` at `0x180009be6`
- `RPCRT4!RpcStringFreeW` at `0x180009be6`

## pseudocode

```c
__int64 __fastcall FwDiagSplitRule(__int64 a1, __int128 *a2, unsigned __int8 a3)
{
  int v3; // r14d
  _BYTE *v4; // rax
  __int128 *v6; // rcx
  __int64 v9; // rdx
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int64 v24; // rcx
  unsigned int v25; // edi
  int v26; // esi
  RPC_WSTR v27; // rcx
  int v28; // eax
  RPC_WSTR StringUuid[2]; // [rsp+20h] [rbp-258h] BYREF
  _BYTE v31[16]; // [rsp+30h] [rbp-248h] BYREF
  RPC_WSTR v32; // [rsp+40h] [rbp-238h]
  int v33; // [rsp+58h] [rbp-220h]
  UUID Uuid; // [rsp+230h] [rbp-48h] BYREF

  v3 = *((_DWORD *)a2 + 10);
  v4 = v31;
  StringUuid[0] = 0;
  v6 = a2;
  Uuid = 0;
  v9 = 3;
  do
  {
    v4 += 128;
    v10 = *v6;
    v11 = v6[1];
    v6 += 8;
    *((_OWORD *)v4 - 8) = v10;
    v12 = *(v6 - 6);
    *((_OWORD *)v4 - 7) = v11;
    v13 = *(v6 - 5);
    *((_OWORD *)v4 - 6) = v12;
    v14 = *(v6 - 4);
    *((_OWORD *)v4 - 5) = v13;
    v15 = *(v6 - 3);
    *((_OWORD *)v4 - 4) = v14;
    v16 = *(v6 - 2);
    *((_OWORD *)v4 - 3) = v15;
    v17 = *(v6 - 1);
    *((_OWORD *)v4 - 2) = v16;
    *((_OWORD *)v4 - 1) = v17;
    --v9;
  }
  while ( v9 );
  v18 = v6[1];
  *(_OWORD *)v4 = *v6;
  v19 = v6[2];
  *((_OWORD *)v4 + 1) = v18;
  v20 = v6[3];
  *((_OWORD *)v4 + 2) = v19;
  v21 = v6[4];
  *((_OWORD *)v4 + 3) = v20;
  v22 = v6[5];
  *((_OWORD *)v4 + 4) = v21;
  v23 = v6[6];
  v24 = *((_QWORD *)v6 + 14);
  *((_OWORD *)v4 + 5) = v22;
  *((_OWORD *)v4 + 6) = v23;
  *((_QWORD *)v4 + 14) = v24;
  v33 = a3 & (unsigned __int8)v3 & 7;
  v25 = FWSetFirewallRule(a1, v31);
  if ( !v25 )
  {
    v25 = UuidCreate(&Uuid);
    if ( !v25 )
    {
      v25 = UuidToStringW(&Uuid, StringUuid);
      if ( !v25 )
      {
        v32 = StringUuid[0];
        v26 = (unsigned __int8)v3 & (unsigned __int8)~a3 & 7;
        v33 = v26;
        v25 = FWAddFirewallRule(a1, v31);
        if ( !v25 )
        {
          FwFree(*((_QWORD *)a2 + 2));
          v27 = v32;
          *((_QWORD *)a2 + 2) = 0;
          v28 = FwStringCopy(v27, a2 + 1);
          if ( v28 >= 0 )
            *((_DWORD *)a2 + 10) = v26;
          else
            v25 = (unsigned __int16)v28;
        }
      }
    }
  }
  if ( StringUuid[0] )
    RpcStringFreeW(StringUuid);
  return v25;
}

```

## disassembly

```asm
0x180009a50  push    rbx
0x180009a52  push    rbp
0x180009a53  push    rsi
0x180009a54  push    rdi
0x180009a55  push    r14
0x180009a57  sub     rsp, 250h
0x180009a5e  mov     rax, cs:__security_cookie
0x180009a65  xor     rax, rsp
0x180009a68  mov     [rsp+278h+var_38], rax
0x180009a70  mov     r14d, [rdx+28h]
0x180009a74  lea     rax, [rsp+278h+var_248]
0x180009a79  mov     rbx, rcx
0x180009a7c  mov     [rsp+278h+StringUuid], 0
0x180009a85  xorps   xmm0, xmm0
0x180009a88  mov     rcx, rdx
0x180009a8b  mov     rbp, rdx
0x180009a8e  mov     esi, r8d
0x180009a91  movups  xmmword ptr [rsp+278h+Uuid.Data1], xmm0
0x180009a99  mov     edx, 3
0x180009a9e  xchg    ax, ax
0x180009aa0  lea     rax, [rax+80h]
0x180009aa7  movups  xmm0, xmmword ptr [rcx]
0x180009aaa  movups  xmm1, xmmword ptr [rcx+10h]
0x180009aae  lea     rcx, [rcx+80h]
0x180009ab5  movups  xmmword ptr [rax-80h], xmm0
0x180009ab9  movups  xmm0, xmmword ptr [rcx-60h]
0x180009abd  movups  xmmword ptr [rax-70h], xmm1
0x180009ac1  movups  xmm1, xmmword ptr [rcx-50h]
0x180009ac5  movups  xmmword ptr [rax-60h], xmm0
0x180009ac9  movups  xmm0, xmmword ptr [rcx-40h]
0x180009acd  movups  xmmword ptr [rax-50h], xmm1
0x180009ad1  movups  xmm1, xmmword ptr [rcx-30h]
0x180009ad5  movups  xmmword ptr [rax-40h], xmm0
0x180009ad9  movups  xmm0, xmmword ptr [rcx-20h]
0x180009add  movups  xmmword ptr [rax-30h], xmm1
0x180009ae1  movups  xmm1, xmmword ptr [rcx-10h]
0x180009ae5  movups  xmmword ptr [rax-20h], xmm0
0x180009ae9  movups  xmmword ptr [rax-10h], xmm1
0x180009aed  sub     rdx, 1
0x180009af1  jnz     short loc_180009AA0
0x180009af3  movups  xmm0, xmmword ptr [rcx]
0x180009af6  lea     rdx, [rsp+278h+var_248]
0x180009afb  movups  xmm1, xmmword ptr [rcx+10h]
0x180009aff  movups  xmmword ptr [rax], xmm0
0x180009b02  movups  xmm0, xmmword ptr [rcx+20h]
0x180009b06  movups  xmmword ptr [rax+10h], xmm1
0x180009b0a  movups  xmm1, xmmword ptr [rcx+30h]
0x180009b0e  movups  xmmword ptr [rax+20h], xmm0
0x180009b12  movups  xmm0, xmmword ptr [rcx+40h]
0x180009b16  movups  xmmword ptr [rax+30h], xmm1
0x180009b1a  movups  xmm1, xmmword ptr [rcx+50h]
0x180009b1e  movups  xmmword ptr [rax+40h], xmm0
0x180009b22  movups  xmm0, xmmword ptr [rcx+60h]
0x180009b26  mov     rcx, [rcx+70h]
0x180009b2a  movups  xmmword ptr [rax+50h], xmm1
0x180009b2e  movups  xmmword ptr [rax+60h], xmm0
0x180009b32  mov     [rax+70h], rcx
0x180009b36  mov     eax, r14d
0x180009b39  and     eax, esi
0x180009b3b  mov     rcx, rbx
0x180009b3e  and     eax, 7
0x180009b41  mov     [rsp+278h+var_220], eax
0x180009b45  call    cs:__imp_FWSetFirewallRule
0x180009b4b  mov     edi, eax
0x180009b4d  test    eax, eax
0x180009b4f  jnz     loc_180009BD9
0x180009b55  lea     rcx, [rsp+278h+Uuid]; Uuid
0x180009b5d  call    cs:__imp_UuidCreate
0x180009b63  mov     edi, eax
0x180009b65  test    eax, eax
0x180009b67  jnz     short loc_180009BD9
0x180009b69  lea     rdx, [rsp+278h+StringUuid]; StringUuid
0x180009b6e  lea     rcx, [rsp+278h+Uuid]; Uuid
0x180009b76  call    cs:__imp_UuidToStringW
0x180009b7c  mov     edi, eax
0x180009b7e  test    eax, eax
0x180009b80  jnz     short loc_180009BD9
0x180009b82  mov     rax, [rsp+278h+StringUuid]
0x180009b87  lea     rdx, [rsp+278h+var_248]
0x180009b8c  not     esi
0x180009b8e  mov     [rsp+278h+var_238], rax
0x180009b93  and     esi, r14d
0x180009b96  mov     rcx, rbx
0x180009b99  and     esi, 7
0x180009b9c  mov     [rsp+278h+var_220], esi
0x180009ba0  call    cs:__imp_FWAddFirewallRule
0x180009ba6  mov     edi, eax
0x180009ba8  test    eax, eax
0x180009baa  jnz     short loc_180009BD9
0x180009bac  mov     rcx, [rbp+10h]
0x180009bb0  call    cs:__imp_FwFree
0x180009bb6  mov     rcx, [rsp+278h+var_238]
0x180009bbb  lea     rdx, [rbp+10h]
0x180009bbf  mov     qword ptr [rbp+10h], 0
0x180009bc7  call    cs:__imp_FwStringCopy
0x180009bcd  test    eax, eax
0x180009bcf  jns     short loc_180009BD6
0x180009bd1  movzx   edi, ax
0x180009bd4  jmp     short loc_180009BD9
0x180009bd6  mov     [rbp+28h], esi
0x180009bd9  cmp     [rsp+278h+StringUuid], 0
0x180009bdf  jz      short loc_180009BEC
0x180009be1  lea     rcx, [rsp+278h+StringUuid]; String
0x180009be6  call    cs:__imp_RpcStringFreeW
0x180009bec  mov     eax, edi
0x180009bee  mov     rcx, [rsp+278h+var_38]
0x180009bf6  xor     rcx, rsp; StackCookie
0x180009bf9  call    __security_check_cookie
0x180009bfe  add     rsp, 250h
0x180009c05  pop     r14
0x180009c07  pop     rdi
0x180009c08  pop     rsi
0x180009c09  pop     rbp
0x180009c0a  pop     rbx
0x180009c0b  retn
```
