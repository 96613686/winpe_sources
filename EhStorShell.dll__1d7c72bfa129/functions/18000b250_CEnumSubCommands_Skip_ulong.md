# CEnumSubCommands::Skip(ulong)

- ea: `0x18000b250`
- end: `0x18000b2ca`
- name: `?Skip@CEnumSubCommands@@UEAAJK@Z`
- size: `122`
- prototype: `__int64 __fastcall(CEnumSubCommands *this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000453c`
- `0x1800061ec`
- `0x18000b250`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CEnumSubCommands::Skip(CEnumSubCommands *this, int a2)
{
  int v2; // ebx
  int i; // edi
  struct IUnknown *v6; // [rsp+50h] [rbp+18h] BYREF

  v2 = a2;
  for ( i = 0; v2; --v2 )
  {
    if ( i < 0 )
      break;
    v6 = 0;
    i = (*(__int64 (__fastcall **)(CEnumSubCommands *, __int64, struct IUnknown **))(*(_QWORD *)this + 24LL))(
          this,
          1,
          &v6);
    if ( v6 )
      ATL::AtlComPtrAssign(&v6, 0);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v6);
  }
  return (unsigned int)i;
}

```

## disassembly

```asm
0x18000b250  mov     [rsp+arg_0], rbx
0x18000b255  mov     [rsp+arg_8], rsi
0x18000b25a  push    rdi
0x18000b25b  sub     rsp, 30h
0x18000b25f  mov     ebx, edx
0x18000b261  mov     rsi, rcx
0x18000b264  xor     edi, edi
0x18000b266  test    edx, edx
0x18000b268  jz      short loc_18000B2B8
0x18000b26a  test    edi, edi
0x18000b26c  js      short loc_18000B2B8
0x18000b26e  mov     [rsp+38h+arg_10], 0
0x18000b277  mov     rax, [rsi]
0x18000b27a  xor     r9d, r9d
0x18000b27d  lea     r8, [rsp+38h+arg_10]
0x18000b282  lea     edx, [r9+1]
0x18000b286  mov     rcx, rsi
0x18000b289  mov     rax, [rax+18h]
0x18000b28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b292  mov     edi, eax
0x18000b294  cmp     [rsp+38h+arg_10], 0
0x18000b29a  jz      short loc_18000B2A9
0x18000b29c  xor     edx, edx; struct IUnknown *
0x18000b29e  lea     rcx, [rsp+38h+arg_10]; struct IUnknown **
0x18000b2a3  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000b2a8  nop
0x18000b2a9  lea     rcx, [rsp+38h+arg_10]
0x18000b2ae  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b2b3  add     ebx, 0FFFFFFFFh
0x18000b2b6  jnz     short loc_18000B26A
0x18000b2b8  mov     eax, edi
0x18000b2ba  mov     rbx, [rsp+38h+arg_0]
0x18000b2bf  mov     rsi, [rsp+38h+arg_8]
0x18000b2c4  add     rsp, 30h
0x18000b2c8  pop     rdi
0x18000b2c9  retn
```
