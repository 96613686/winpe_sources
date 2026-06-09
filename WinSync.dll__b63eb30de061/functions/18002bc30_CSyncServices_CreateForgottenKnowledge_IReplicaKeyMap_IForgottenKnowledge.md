# CSyncServices::CreateForgottenKnowledge(IReplicaKeyMap *,IForgottenKnowledge * *)

- ea: `0x18002bc30`
- end: `0x18002bd15`
- name: `?CreateForgottenKnowledge@CSyncServices@@UEAAJPEAUIReplicaKeyMap@@PEAPEAUIForgottenKnowledge@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(CSyncServices *__hidden this, struct IReplicaKeyMap *, struct IForgottenKnowledge **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002bd20`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002bc30`
- `0x180094010`

## string_xrefs

- `0x18002bc65`: `CSyncServices::CreateForgottenKnowledge`
- `0x18002bcee`: `CSyncServices::CreateForgottenKnowledge`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateForgottenKnowledge(
        CSyncServices *this,
        struct IReplicaKeyMap *a2,
        struct IForgottenKnowledge **a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateForgottenKnowledge");
  }
  v6 = *(_QWORD *)this;
  v9 = 0;
  v7 = (*(__int64 (__fastcall **)(CSyncServices *, _QWORD, struct IReplicaKeyMap *, __int64 *))(v6 + 56))(
         this,
         0,
         a2,
         &v9);
  if ( !v7 )
  {
    v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IForgottenKnowledge **))v9)(
           v9,
           &IID_IForgottenKnowledge,
           a3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateForgottenKnowledge",
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x18002bc30  push    rbx
0x18002bc32  push    rbp
0x18002bc33  push    rsi
0x18002bc34  push    rdi
0x18002bc35  sub     rsp, 38h
0x18002bc39  mov     rsi, r8
0x18002bc3c  mov     rdi, rdx
0x18002bc3f  mov     rbx, rcx
0x18002bc42  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc49  lea     rbp, WPP_GLOBAL_Control
0x18002bc50  cmp     rcx, rbp
0x18002bc53  jz      short loc_18002BC7D
0x18002bc55  test    byte ptr [rcx+1Ch], 2
0x18002bc59  jz      short loc_18002BC7D
0x18002bc5b  cmp     byte ptr [rcx+19h], 5
0x18002bc5f  jb      short loc_18002BC7D
0x18002bc61  mov     rcx, [rcx+10h]
0x18002bc65  lea     r9, aCsyncservicesC_4; "CSyncServices::CreateForgottenKnowledge"
0x18002bc6c  mov     edx, 22h ; '"'
0x18002bc71  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002bc78  call    WPP_SF_s
0x18002bc7d  mov     rax, [rbx]
0x18002bc80  lea     r9, [rsp+58h+arg_0]
0x18002bc85  mov     r8, rdi
0x18002bc88  mov     [rsp+58h+arg_0], 0
0x18002bc91  xor     edx, edx
0x18002bc93  mov     rcx, rbx
0x18002bc96  mov     rax, [rax+38h]
0x18002bc9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc9f  mov     ebx, eax
0x18002bca1  test    eax, eax
0x18002bca3  jnz     short loc_18002BCD2
0x18002bca5  mov     rcx, [rsp+58h+arg_0]
0x18002bcaa  lea     rdx, IID_IForgottenKnowledge
0x18002bcb1  mov     r8, rsi
0x18002bcb4  mov     rax, [rcx]
0x18002bcb7  mov     rax, [rax]
0x18002bcba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcbf  mov     rcx, [rsp+58h+arg_0]
0x18002bcc4  mov     ebx, eax
0x18002bcc6  mov     rax, [rcx]
0x18002bcc9  mov     rax, [rax+10h]
0x18002bccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bcd9  cmp     rcx, rbp
0x18002bcdc  jz      short loc_18002BD0A
0x18002bcde  test    byte ptr [rcx+1Ch], 2
0x18002bce2  jz      short loc_18002BD0A
0x18002bce4  cmp     byte ptr [rcx+19h], 5
0x18002bce8  jb      short loc_18002BD0A
0x18002bcea  mov     rcx, [rcx+10h]
0x18002bcee  lea     r9, aCsyncservicesC_4; "CSyncServices::CreateForgottenKnowledge"
0x18002bcf5  mov     edx, 23h ; '#'
0x18002bcfa  mov     [rsp+58h+var_38], ebx
0x18002bcfe  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002bd05  call    WPP_SF_sD
0x18002bd0a  mov     eax, ebx
0x18002bd0c  add     rsp, 38h
0x18002bd10  pop     rdi
0x18002bd11  pop     rsi
0x18002bd12  pop     rbp
0x18002bd13  pop     rbx
0x18002bd14  retn
```
