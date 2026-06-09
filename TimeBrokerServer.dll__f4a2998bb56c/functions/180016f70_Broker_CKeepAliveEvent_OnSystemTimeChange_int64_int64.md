# Broker::CKeepAliveEvent::OnSystemTimeChange(__int64,__int64)

- ea: `0x180016f70`
- end: `0x180017037`
- name: `?OnSystemTimeChange@CKeepAliveEvent@Broker@@UEAAX_J0@Z`
- size: `199`
- prototype: `void __fastcall(Broker::CKeepAliveEvent *__hidden this, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009f70`
- `0x180016f70`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180016fcc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180016fcc`

## pseudocode

```c
void __fastcall Broker::CKeepAliveEvent::OnSystemTimeChange(Broker::CKeepAliveEvent *this, __int64 a2, __int64 a3)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  signed __int64 v7; // rdx
  __int64 v8; // rax
  signed __int64 v9; // rdx

  v5 = *(_QWORD *)(*((_QWORD *)this + 31) + 16LL);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids,
      (unsigned int)v5,
      HIDWORD(v5));
  v6 = *((_QWORD *)this + 38);
  v7 = *((_QWORD *)this + 8) - 10000 * (GetTickCount64() - v6);
  if ( v7 > 0 )
  {
    v8 = v7 + a3;
    v9 = v7 - *((_QWORD *)this + 7);
    *((_QWORD *)this + 4) = v8;
    *((_QWORD *)this + 3) = a3 + v9;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids,
      (unsigned int)v5,
      HIDWORD(v5));
}

```

## disassembly

```asm
0x180016f70  push    rbx
0x180016f72  push    rbp
0x180016f73  push    rsi
0x180016f74  push    rdi
0x180016f75  sub     rsp, 38h
0x180016f79  mov     rbx, [rcx+0F8h]
0x180016f80  mov     rbp, r8
0x180016f83  mov     rsi, rcx
0x180016f86  mov     rbx, [rbx+10h]
0x180016f8a  mov     [rsp+58h+arg_0], rbx
0x180016f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f96  test    byte ptr [rcx+1Ch], 40h
0x180016f9a  jz      short loc_180016FC5
0x180016f9c  cmp     byte ptr [rcx+19h], 4
0x180016fa0  jb      short loc_180016FC5
0x180016fa2  mov     rcx, [rcx+10h]
0x180016fa6  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180016fad  mov     rax, rbx
0x180016fb0  mov     edx, 23h ; '#'
0x180016fb5  shr     rax, 20h
0x180016fb9  mov     r9d, ebx
0x180016fbc  mov     [rsp+58h+var_38], eax
0x180016fc0  call    WPP_SF_DD
0x180016fc5  mov     rdi, [rsi+130h]
0x180016fcc  call    cs:__imp_GetTickCount64
0x180016fd2  mov     rdx, [rsi+40h]
0x180016fd6  sub     rax, rdi
0x180016fd9  imul    rcx, rax, 2710h
0x180016fe0  sub     rdx, rcx
0x180016fe3  test    rdx, rdx
0x180016fe6  jle     short loc_180016FFB
0x180016fe8  lea     rax, [rdx+rbp]
0x180016fec  sub     rdx, [rsi+38h]
0x180016ff0  add     rdx, rbp
0x180016ff3  mov     [rsi+20h], rax
0x180016ff7  mov     [rsi+18h], rdx
0x180016ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x180017002  test    byte ptr [rcx+1Ch], 40h
0x180017006  jz      short loc_18001702E
0x180017008  cmp     byte ptr [rcx+19h], 4
0x18001700c  jb      short loc_18001702E
0x18001700e  mov     eax, dword ptr [rsp+58h+arg_0+4]
0x180017012  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180017019  mov     rcx, [rcx+10h]
0x18001701d  mov     edx, 24h ; '$'
0x180017022  mov     r9d, ebx
0x180017025  mov     [rsp+58h+var_38], eax
0x180017029  call    WPP_SF_DD
0x18001702e  add     rsp, 38h
0x180017032  pop     rdi
0x180017033  pop     rsi
0x180017034  pop     rbp
0x180017035  pop     rbx
0x180017036  retn
```
