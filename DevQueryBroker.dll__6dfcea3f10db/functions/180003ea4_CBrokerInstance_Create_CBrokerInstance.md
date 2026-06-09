# CBrokerInstance::Create(CBrokerInstance * *)

- ea: `0x180003ea4`
- end: `0x180003f79`
- name: `?Create@CBrokerInstance@@SAJPEAPEAV1@@Z`
- size: `213`
- prototype: `__int64 __fastcall(struct CBrokerInstance **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ec0`

## callees

- `0x1800011d4`
- `0x180003ea4`

## import_xrefs

- `BrokerLib!BrInitializeBrokerInstance2` at `0x180003f33`
- `BrokerLib!BrInitializeBrokerInstance2` at `0x180003f33`
- `BrokerLib!BrCreateBrokerInstance2` at `0x180003f10`
- `BrokerLib!BrCreateBrokerInstance2` at `0x180003f10`

## pseudocode

```c
__int64 __fastcall CBrokerInstance::Create(struct CBrokerInstance **a1)
{
  int v1; // eax
  unsigned int v2; // ecx
  bool v3; // cc
  _QWORD *v4; // rdx
  _QWORD v6[7]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v7; // [rsp+70h] [rbp+8h] BYREF

  v7 = 0;
  v6[0] = CBrokerInstance::OnCreateEvent;
  v6[1] = &CBrokerInstance::OnDeleteEvent;
  v6[2] = &CBrokerInstance::OnEnableEvent;
  v6[3] = &CBrokerInstance::OnDisableEvent;
  v6[4] = 0;
  g_pDqbInstance = 0;
  v1 = BrCreateBrokerInstance2(v6, qword_18000E4B0, 1, &qword_18000E4A8, &v7);
  v2 = v1;
  v3 = v1 <= 0;
  if ( v1 || (v1 = BrInitializeBrokerInstance2(v7, 0, 0), v2 = v1, v3 = v1 <= 0, v1) )
  {
    if ( !v3 )
      return (unsigned __int16)v1 | 0x80070000;
  }
  else
  {
    v4 = operator new(8u);
    if ( v4 )
    {
      v2 = 0;
      *v4 = v7;
      g_pDqbInstance = v4;
    }
    else
    {
      g_pDqbInstance = 0;
      return (unsigned int)-2147024882;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180003ea4  mov     r11, rsp
0x180003ea7  mov     [r11+8], rcx
0x180003eab  sub     rsp, 68h
0x180003eaf  lea     rax, ?OnCreateEvent@CBrokerInstance@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAU_BR_EVENT_PARAMETERS@@PEBGPEAX55PEAPEAXPEAKPEAU_BR_NEW_EVENT_INFORMATION@@@Z; CBrokerInstance::OnCreateEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,_BR_EVENT_PARAMETERS *,ushort const *,void *,void *,void *,void * *,ulong *,_BR_NEW_EVENT_INFORMATION *)
0x180003eb6  mov     qword ptr [r11+8], 0
0x180003ebe  mov     [r11-38h], rax
0x180003ec2  lea     r9, qword_18000E4A8
0x180003ec9  lea     rax, ?OnDeleteEvent@CBrokerInstance@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; CBrokerInstance::OnDeleteEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x180003ed0  mov     r8d, 1
0x180003ed6  mov     [r11-30h], rax
0x180003eda  lea     rdx, qword_18000E4B0
0x180003ee1  lea     rax, ?OnEnableEvent@CBrokerInstance@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; CBrokerInstance::OnEnableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x180003ee8  mov     [r11-28h], rax
0x180003eec  lea     rcx, [r11-38h]
0x180003ef0  lea     rax, ?OnDisableEvent@CBrokerInstance@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; CBrokerInstance::OnDisableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x180003ef7  mov     [r11-20h], rax
0x180003efb  xor     eax, eax
0x180003efd  mov     [r11-18h], rax
0x180003f01  mov     cs:?g_pDqbInstance@@3PEAVCBrokerInstance@@EA, rax; CBrokerInstance * g_pDqbInstance
0x180003f08  lea     rax, [r11+8]
0x180003f0c  mov     [r11-48h], rax
0x180003f10  call    cs:__imp_BrCreateBrokerInstance2
0x180003f16  mov     ecx, eax
0x180003f18  test    eax, eax
0x180003f1a  jz      short loc_180003F29
0x180003f1c  jle     short loc_180003F72
0x180003f1e  movzx   ecx, ax
0x180003f21  or      ecx, 80070000h
0x180003f27  jmp     short loc_180003F72
0x180003f29  mov     rcx, [rsp+68h+arg_0]
0x180003f2e  xor     r8d, r8d
0x180003f31  xor     edx, edx
0x180003f33  call    cs:__imp_BrInitializeBrokerInstance2
0x180003f39  mov     ecx, eax
0x180003f3b  test    eax, eax
0x180003f3d  jnz     short loc_180003F1C
0x180003f3f  lea     ecx, [rax+8]; Size
0x180003f42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003f47  mov     rdx, rax
0x180003f4a  test    rax, rax
0x180003f4d  jz      short loc_180003F62
0x180003f4f  mov     rax, [rsp+68h+arg_0]
0x180003f54  xor     ecx, ecx
0x180003f56  mov     [rdx], rax
0x180003f59  mov     cs:?g_pDqbInstance@@3PEAVCBrokerInstance@@EA, rdx; CBrokerInstance * g_pDqbInstance
0x180003f60  jmp     short loc_180003F72
0x180003f62  mov     cs:?g_pDqbInstance@@3PEAVCBrokerInstance@@EA, 0; CBrokerInstance * g_pDqbInstance
0x180003f6d  mov     ecx, 8007000Eh
0x180003f72  mov     eax, ecx
0x180003f74  add     rsp, 68h
0x180003f78  retn
```
