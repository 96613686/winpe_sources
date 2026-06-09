# CMidi2VirtualMidiBidi::Callback(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64,__int64)

- ea: `0x18001b010`
- end: `0x18001b08e`
- name: `?Callback@CMidi2VirtualMidiBidi@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J2@Z`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180009784`
- `0x18001b010`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall CMidi2VirtualMidiBidi::Callback(__int64 a1, unsigned int a2, __int64 a3, unsigned int a4, int a5)
{
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v9; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a4 >= 4 )
  {
    v7 = *(_QWORD *)(a1 + 32);
    if ( v7 )
    {
      v9 = a5;
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 24LL))(v7, a2);
      if ( v5 >= 0 )
        return 0;
      v6 = 238;
    }
    else
    {
      v5 = -2147418113;
      v6 = 242;
    }
  }
  else
  {
    v5 = -2147024809;
    v6 = 234;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidibidi.cpp",
    (const char *)(unsigned int)v5,
    v9);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001b010  push    rbx
0x18001b012  sub     rsp, 40h
0x18001b016  mov     r10d, edx
0x18001b019  cmp     r9d, 4
0x18001b01d  jnb     short loc_18001B02B
0x18001b01f  mov     ebx, 80070057h
0x18001b024  mov     edx, 0EAh
0x18001b029  jmp     short loc_18001B072
0x18001b02b  mov     rcx, [rcx+20h]
0x18001b02f  test    rcx, rcx
0x18001b032  jz      short loc_18001B068
0x18001b034  mov     rdx, [rsp+48h+arg_28]
0x18001b039  mov     rax, [rcx]
0x18001b03c  mov     [rsp+48h+var_20], rdx
0x18001b041  mov     rdx, [rsp+48h+arg_20]
0x18001b046  mov     [rsp+48h+var_28], rdx
0x18001b04b  mov     edx, r10d
0x18001b04e  mov     rax, [rax+18h]
0x18001b052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b057  mov     ebx, eax
0x18001b059  test    eax, eax
0x18001b05b  jns     short loc_18001B064
0x18001b05d  mov     edx, 0EEh
0x18001b062  jmp     short loc_18001B072
0x18001b064  xor     eax, eax
0x18001b066  jmp     short loc_18001B088
0x18001b068  mov     ebx, 8000FFFFh
0x18001b06d  mov     edx, 0F2h; void *
0x18001b072  mov     rcx, [rsp+48h]; this
0x18001b077  lea     r8, aAvcoreMidi2Tra_5; "avcore\\midi2\\transport\\virtualmiditr"...
0x18001b07e  mov     r9d, ebx; char *
0x18001b081  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b086  mov     eax, ebx
0x18001b088  add     rsp, 40h
0x18001b08c  pop     rbx
0x18001b08d  retn
```
