# NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,ulong>(_NETSETUPPROPKEY const &,ulong const &)

- ea: `0x18001b168`
- end: `0x18001b1df`
- name: `??$SetPropertyToValue@$06K@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBK@Z`
- size: `119`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001e3a8`
- `0x18001e734`
- `0x18001f2e4`
- `0x1800209dc`
- `0x180021650`
- `0x1800223a4`

## callees

- `0x18000d974`
- `0x18002b720`
- `0x18002d560`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
        __int64 a1,
        __int128 *a2,
        __int64 a3)
{
  __int128 v4; // xmm0
  __int64 v5; // rax
  _BYTE v7[16]; // [rsp+20h] [rbp-60h] BYREF
  unsigned int v8; // [rsp+30h] [rbp-50h]
  __int64 v9; // [rsp+34h] [rbp-4Ch] BYREF
  int v10; // [rsp+3Ch] [rbp-44h]
  _OWORD v11[2]; // [rsp+50h] [rbp-30h] BYREF
  int v12; // [rsp+70h] [rbp-10h]
  int v13; // [rsp+74h] [rbp-Ch]
  __int64 v14; // [rsp+78h] [rbp-8h]

  v4 = *a2;
  v8 = *((_DWORD *)a2 + 4);
  v9 = 0;
  v10 = 0;
  v11[0] = v4;
  v11[1] = v8;
  v12 = 7;
  v14 = a3;
  v13 = 4;
  v5 = NetSetup2::Property::Property((NetSetup2::Property *)v7, (const struct _NETSETUPPROPERTY *)v11);
  NetSetup2::ObjectCreationTemplate::SetProperty(a1, v5);
  return std::vector<unsigned char>::_Tidy((char *)&v9 + 4);
}

```

## disassembly

```asm
0x18001b168  mov     [rsp-8+arg_0], rbx
0x18001b16d  push    rbp
0x18001b16e  mov     rbp, rsp
0x18001b171  sub     rsp, 80h
0x18001b178  mov     rbx, rcx
0x18001b17b  movups  xmm0, xmmword ptr [rdx]
0x18001b17e  mov     eax, [rdx+10h]
0x18001b181  mov     dword ptr [rbp+var_50], eax
0x18001b184  xor     eax, eax
0x18001b186  mov     qword ptr [rbp+var_50+4], rax
0x18001b18a  mov     dword ptr [rbp+var_50+0Ch], eax
0x18001b18d  movups  [rbp+var_30], xmm0
0x18001b191  movups  xmm0, [rbp+var_50]
0x18001b195  movups  [rbp+var_20], xmm0
0x18001b199  mov     [rbp+var_10], 7
0x18001b1a0  mov     [rbp+var_8], r8
0x18001b1a4  mov     [rbp+var_C], 4
0x18001b1ab  lea     rdx, [rbp+var_30]; struct _NETSETUPPROPERTY *
0x18001b1af  lea     rcx, [rbp+var_60]; this
0x18001b1b3  call    ??0Property@NetSetup2@@QEAA@AEBU_NETSETUPPROPERTY@@@Z; NetSetup2::Property::Property(_NETSETUPPROPERTY const &)
0x18001b1b8  nop
0x18001b1b9  mov     rdx, rax
0x18001b1bc  mov     rcx, rbx
0x18001b1bf  call    ?SetProperty@ObjectCreationTemplate@NetSetup2@@QEAAX$$QEAVProperty@2@@Z; NetSetup2::ObjectCreationTemplate::SetProperty(NetSetup2::Property &&)
0x18001b1c4  nop
0x18001b1c5  lea     rcx, [rbp+var_50+8]
0x18001b1c9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001b1ce  mov     rbx, [rsp+80h+arg_0]
0x18001b1d6  add     rsp, 80h
0x18001b1dd  pop     rbp
0x18001b1de  retn
```
