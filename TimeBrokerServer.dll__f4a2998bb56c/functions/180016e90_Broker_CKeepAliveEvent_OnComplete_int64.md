# Broker::CKeepAliveEvent::OnComplete(__int64)

- ea: `0x180016e90`
- end: `0x180016f4d`
- name: `?OnComplete@CKeepAliveEvent@Broker@@MEAAX_J@Z`
- size: `189`
- prototype: `void __fastcall(Broker::CKeepAliveEvent *__hidden this, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009f70`
- `0x180016e90`
- `0x18001c010`

## pseudocode

```c
void __fastcall Broker::CKeepAliveEvent::OnComplete(Broker::CKeepAliveEvent *this, __int64 a2)
{
  __int64 v4; // rbx
  _QWORD *v5; // rcx

  v4 = *(_QWORD *)(*((_QWORD *)this + 31) + 16LL);
  v5 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids,
      (unsigned int)v4,
      HIDWORD(v4));
    v5 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 22) == 2 )
  {
    (*(void (__fastcall **)(Broker::CKeepAliveEvent *, __int64))(*(_QWORD *)this + 72LL))(this, a2);
    v5 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 4u )
    WPP_SF_DD(v5[2], 34, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, (unsigned int)v4, HIDWORD(v4));
}

```

## disassembly

```asm
0x180016e90  mov     [rsp+arg_8], rbx
0x180016e95  mov     [rsp+arg_10], rsi
0x180016e9a  push    rdi
0x180016e9b  sub     rsp, 30h
0x180016e9f  mov     rbx, [rcx+0F8h]
0x180016ea6  mov     rsi, rdx
0x180016ea9  mov     rdi, rcx
0x180016eac  mov     rbx, [rbx+10h]
0x180016eb0  mov     [rsp+38h+arg_0], rbx
0x180016eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ebc  test    byte ptr [rcx+1Ch], 1
0x180016ec0  jz      short loc_180016EF2
0x180016ec2  cmp     byte ptr [rcx+19h], 4
0x180016ec6  jb      short loc_180016EF2
0x180016ec8  mov     rcx, [rcx+10h]
0x180016ecc  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180016ed3  mov     rax, rbx
0x180016ed6  mov     edx, 21h ; '!'
0x180016edb  shr     rax, 20h
0x180016edf  mov     r9d, ebx
0x180016ee2  mov     [rsp+38h+var_18], eax
0x180016ee6  call    WPP_SF_DD
0x180016eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ef2  cmp     dword ptr [rdi+58h], 2
0x180016ef6  jnz     short loc_180016F11
0x180016ef8  mov     rax, [rdi]
0x180016efb  mov     rdx, rsi
0x180016efe  mov     rcx, rdi
0x180016f01  mov     rax, [rax+48h]
0x180016f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f11  test    byte ptr [rcx+1Ch], 1
0x180016f15  jz      short loc_180016F3D
0x180016f17  cmp     byte ptr [rcx+19h], 4
0x180016f1b  jb      short loc_180016F3D
0x180016f1d  mov     eax, dword ptr [rsp+38h+arg_0+4]
0x180016f21  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180016f28  mov     rcx, [rcx+10h]
0x180016f2c  mov     edx, 22h ; '"'
0x180016f31  mov     r9d, ebx
0x180016f34  mov     [rsp+38h+var_18], eax
0x180016f38  call    WPP_SF_DD
0x180016f3d  mov     rbx, [rsp+38h+arg_8]
0x180016f42  mov     rsi, [rsp+38h+arg_10]
0x180016f47  add     rsp, 30h
0x180016f4b  pop     rdi
0x180016f4c  retn
```
