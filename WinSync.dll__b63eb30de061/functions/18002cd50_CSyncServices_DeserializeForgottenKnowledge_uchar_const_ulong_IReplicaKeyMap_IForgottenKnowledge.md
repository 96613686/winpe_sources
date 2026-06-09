# CSyncServices::DeserializeForgottenKnowledge(uchar const *,ulong,IReplicaKeyMap *,IForgottenKnowledge * *)

- ea: `0x18002cd50`
- end: `0x18002ce56`
- name: `?DeserializeForgottenKnowledge@CSyncServices@@UEAAJPEBEKPEAUIReplicaKeyMap@@PEAPEAUIForgottenKnowledge@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(CSyncServices *__hidden this, const unsigned __int8 *, unsigned int, struct IReplicaKeyMap *, struct IForgottenKnowledge **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18002ce60`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002cd50`
- `0x180094010`

## string_xrefs

- `0x18002cd91`: `CSyncServices::DeserializeForgottenKnowledge`
- `0x18002ce25`: `CSyncServices::DeserializeForgottenKnowledge`

## pseudocode

```c
__int64 __fastcall CSyncServices::DeserializeForgottenKnowledge(
        CSyncServices *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        struct IReplicaKeyMap *a4,
        struct IForgottenKnowledge **a5)
{
  __int64 v9; // rax
  unsigned int v10; // ebx
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::DeserializeForgottenKnowledge");
  }
  v9 = *(_QWORD *)this;
  v12 = 0;
  v10 = (*(__int64 (__fastcall **)(CSyncServices *, const unsigned __int8 *, _QWORD, struct IReplicaKeyMap *, __int64 *))(v9 + 64))(
          this,
          a2,
          a3,
          a4,
          &v12);
  if ( !v10 )
  {
    v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IForgottenKnowledge **))v12)(
            v12,
            &IID_IForgottenKnowledge,
            a5);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::DeserializeForgottenKnowledge",
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x18002cd50  mov     [rsp+arg_8], rbx
0x18002cd55  mov     [rsp+arg_10], rbp
0x18002cd5a  push    rsi
0x18002cd5b  push    rdi
0x18002cd5c  push    r14
0x18002cd5e  sub     rsp, 30h
0x18002cd62  mov     rdi, r9
0x18002cd65  mov     esi, r8d
0x18002cd68  mov     rbp, rdx
0x18002cd6b  mov     rbx, rcx
0x18002cd6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd75  lea     r14, WPP_GLOBAL_Control
0x18002cd7c  cmp     rcx, r14
0x18002cd7f  jz      short loc_18002CDA9
0x18002cd81  test    byte ptr [rcx+1Ch], 2
0x18002cd85  jz      short loc_18002CDA9
0x18002cd87  cmp     byte ptr [rcx+19h], 5
0x18002cd8b  jb      short loc_18002CDA9
0x18002cd8d  mov     rcx, [rcx+10h]
0x18002cd91  lea     r9, aCsyncservicesD_4; "CSyncServices::DeserializeForgottenKnow"...
0x18002cd98  mov     edx, 24h ; '$'
0x18002cd9d  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002cda4  call    WPP_SF_s
0x18002cda9  mov     rax, [rbx]
0x18002cdac  lea     rcx, [rsp+48h+arg_0]
0x18002cdb1  mov     [rsp+48h+var_28], rcx
0x18002cdb6  mov     r9, rdi
0x18002cdb9  mov     r8d, esi
0x18002cdbc  mov     [rsp+48h+arg_0], 0
0x18002cdc5  mov     rdx, rbp
0x18002cdc8  mov     rcx, rbx
0x18002cdcb  mov     rax, [rax+40h]
0x18002cdcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdd4  mov     ebx, eax
0x18002cdd6  test    eax, eax
0x18002cdd8  jnz     short loc_18002CE09
0x18002cdda  mov     rcx, [rsp+48h+arg_0]
0x18002cddf  lea     rdx, IID_IForgottenKnowledge
0x18002cde6  mov     r8, [rsp+48h+arg_20]
0x18002cdeb  mov     rax, [rcx]
0x18002cdee  mov     rax, [rax]
0x18002cdf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdf6  mov     rcx, [rsp+48h+arg_0]
0x18002cdfb  mov     ebx, eax
0x18002cdfd  mov     rax, [rcx]
0x18002ce00  mov     rax, [rax+10h]
0x18002ce04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce09  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce10  cmp     rcx, r14
0x18002ce13  jz      short loc_18002CE41
0x18002ce15  test    byte ptr [rcx+1Ch], 2
0x18002ce19  jz      short loc_18002CE41
0x18002ce1b  cmp     byte ptr [rcx+19h], 5
0x18002ce1f  jb      short loc_18002CE41
0x18002ce21  mov     rcx, [rcx+10h]
0x18002ce25  lea     r9, aCsyncservicesD_4; "CSyncServices::DeserializeForgottenKnow"...
0x18002ce2c  mov     edx, 25h ; '%'
0x18002ce31  mov     dword ptr [rsp+48h+var_28], ebx
0x18002ce35  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002ce3c  call    WPP_SF_sD
0x18002ce41  mov     rbp, [rsp+48h+arg_10]
0x18002ce46  mov     eax, ebx
0x18002ce48  mov     rbx, [rsp+48h+arg_8]
0x18002ce4d  add     rsp, 30h
0x18002ce51  pop     r14
0x18002ce53  pop     rdi
0x18002ce54  pop     rsi
0x18002ce55  retn
```
