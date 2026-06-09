# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::UuidCreate(void)

- ea: `0x18001c0f4`
- end: `0x18001c19a`
- name: `?UuidCreate@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAJXZ`
- size: `166`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001be2c`
- `0x18001cc8c`

## callees

- `0x1800035cc`
- `0x18000be30`
- `0x18001c0f4`
- `0x18002fb50`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18001c151`
- `RPCRT4!UuidToStringW` at `0x18001c151`
- `RPCRT4!RpcStringFreeW` at `0x18001c173`
- `RPCRT4!RpcStringFreeW` at `0x18001c173`
- `RPCRT4!UuidCreate` at `0x18001c139`
- `RPCRT4!UuidCreate` at `0x18001c139`
- `RPCRT4!UuidCreateNil` at `0x18001c128`
- `RPCRT4!UuidCreateNil` at `0x18001c128`

## pseudocode

```c
RPC_STATUS __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::UuidCreate(
        __int64 a1)
{
  RPC_STATUS v2; // edi
  RPC_STATUS result; // eax
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-28h] BYREF
  UUID NilUuid; // [rsp+28h] [rbp-20h] BYREF

  StringUuid = 0;
  NilUuid = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a1);
  UuidCreateNil(&NilUuid);
  v2 = UuidCreate(&NilUuid);
  result = UuidToStringW(&NilUuid, &StringUuid);
  if ( !result )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
      a1,
      StringUuid);
    RpcStringFreeW(&StringUuid);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x18001c0f4  mov     [rsp+arg_8], rbx
0x18001c0f9  push    rdi
0x18001c0fa  sub     rsp, 40h
0x18001c0fe  mov     rax, cs:__security_cookie
0x18001c105  xor     rax, rsp
0x18001c108  mov     [rsp+48h+var_10], rax
0x18001c10d  and     [rsp+48h+StringUuid], 0
0x18001c113  xorps   xmm0, xmm0
0x18001c116  movups  xmmword ptr [rsp+48h+NilUuid.Data1], xmm0
0x18001c11b  mov     rbx, rcx
0x18001c11e  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x18001c123  lea     rcx, [rsp+48h+NilUuid]; NilUuid
0x18001c128  call    cs:__imp_UuidCreateNil
0x18001c12f  nop     dword ptr [rax+rax+00h]
0x18001c134  lea     rcx, [rsp+48h+NilUuid]; Uuid
0x18001c139  call    cs:__imp_UuidCreate
0x18001c140  nop     dword ptr [rax+rax+00h]
0x18001c145  lea     rdx, [rsp+48h+StringUuid]; StringUuid
0x18001c14a  mov     edi, eax
0x18001c14c  lea     rcx, [rsp+48h+NilUuid]; Uuid
0x18001c151  call    cs:__imp_UuidToStringW
0x18001c158  nop     dword ptr [rax+rax+00h]
0x18001c15d  test    eax, eax
0x18001c15f  jnz     short loc_18001C181
0x18001c161  mov     rdx, [rsp+48h+StringUuid]
0x18001c166  mov     rcx, rbx
0x18001c169  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x18001c16e  lea     rcx, [rsp+48h+StringUuid]; String
0x18001c173  call    cs:__imp_RpcStringFreeW
0x18001c17a  nop     dword ptr [rax+rax+00h]
0x18001c17f  mov     eax, edi
0x18001c181  mov     rcx, [rsp+48h+var_10]
0x18001c186  xor     rcx, rsp; StackCookie
0x18001c189  call    __security_check_cookie
0x18001c18e  mov     rbx, [rsp+48h+arg_8]
0x18001c193  add     rsp, 40h
0x18001c197  pop     rdi
0x18001c198  retn
```
