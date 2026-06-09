# Windows::Security::Isolation::BrokerUtils::AddItemArrayToBfs(void *,IShellItemArray *)

- ea: `0x140010654`
- end: `0x14001075c`
- name: `?AddItemArrayToBfs@BrokerUtils@Isolation@Security@Windows@@SAXPEAXPEAUIShellItemArray@@@Z`
- size: `264`
- prototype: `void __fastcall(char *, struct IShellItemArray *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c360`

## callees

- `0x1400066d0`
- `0x140007df4`
- `0x140010654`
- `0x140010764`
- `0x140014010`

## string_xrefs

- `0x140010683`: `onecoreuap\ds\security\isolation\broker\lib\brokerutils.cpp`
- `0x1400106a4`: `onecoreuap\ds\security\isolation\broker\lib\brokerutils.cpp`
- `0x1400106db`: `onecoreuap\ds\security\isolation\broker\lib\brokerutils.cpp`
- `0x14001071f`: `onecoreuap\ds\security\isolation\broker\lib\brokerutils.cpp`

## pseudocode

```c
void __fastcall Windows::Security::Isolation::BrokerUtils::AddItemArrayToBfs(char *a1, struct IShellItemArray *a2)
{
  int v4; // eax
  const char *v5; // r9
  unsigned int i; // ebx
  struct IShellItemArrayVtbl *lpVtbl; // rax
  int v8; // eax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v11; // [rsp+30h] [rbp+8h] BYREF
  struct IShellItem *v12; // [rsp+40h] [rbp+18h] BYREF

  try
  {
    if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
        (const char *)0x80070006LL,
        v9);
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
        (const char *)0x80004003LL,
        v9);
    v11 = 0;
    v4 = ((__int64 (__fastcall *)(struct IShellItemArray *, unsigned int *))a2->lpVtbl->GetCount)(a2, &v11);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
        (const char *)(unsigned int)v4,
        v9);
    for ( i = 0; i < v11; ++i )
    {
      lpVtbl = a2->lpVtbl;
      v12 = 0;
      v8 = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, struct IShellItem **))lpVtbl->GetItemAt)(
             a2,
             i,
             &v12);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x29,
          (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
          (const char *)(unsigned int)v8,
          v9);
      Windows::Security::Isolation::BrokerUtils::AddItemToBfs(a1, v12);
      wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(&v12);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Throw_CaughtException(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
      v5);
  }
}

```

## disassembly

```asm
0x140010654  mov     [rsp+arg_8], rbx
0x140010659  mov     [rsp+arg_18], rsi
0x14001065e  push    rdi; int
0x14001065f  sub     rsp, 20h
0x140010663  mov     rdi, rdx
0x140010666  mov     rsi, rcx
0x140010669  lea     rax, [rcx-1]
0x14001066d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140010671  setnbe  al
0x140010674  mov     rcx, [rsp+28h]; this
0x140010679  test    al, al
0x14001067b  jz      short loc_140010694
0x14001067d  mov     r9d, 80070006h; char *
0x140010683  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\isolation\\br"...
0x14001068a  mov     edx, 1Fh; void *
0x14001068f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140010694  mov     rcx, [rsp+28h]; this
0x140010699  test    rdi, rdi
0x14001069c  jnz     short loc_1400106B3
0x14001069e  mov     r9d, 80004003h; char *
0x1400106a4  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\isolation\\br"...
0x1400106ab  lea     edx, [rdi+20h]; void *
0x1400106ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400106b3  mov     [rsp+28h+arg_0], 0
0x1400106bb  mov     rax, [rdx]
0x1400106be  lea     rdx, [rsp+28h+arg_0]
0x1400106c3  mov     rcx, rdi
0x1400106c6  mov     rax, [rax+38h]
0x1400106ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106cf  mov     rcx, [rsp+28h]; this
0x1400106d4  test    eax, eax
0x1400106d6  jns     short loc_1400106EC
0x1400106d8  mov     r9d, eax; char *
0x1400106db  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\isolation\\br"...
0x1400106e2  mov     edx, 24h ; '$'; void *
0x1400106e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400106ec  xor     ebx, ebx
0x1400106ee  cmp     ebx, [rsp+28h+arg_0]
0x1400106f2  jnb     short loc_14001074C
0x1400106f4  mov     rax, [rdi]
0x1400106f7  mov     [rsp+28h+arg_10], 0
0x140010700  lea     r8, [rsp+28h+arg_10]
0x140010705  mov     edx, ebx
0x140010707  mov     rcx, rdi
0x14001070a  mov     rax, [rax+40h]
0x14001070e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010713  mov     rcx, [rsp+28h]; this
0x140010718  test    eax, eax
0x14001071a  jns     short loc_140010730
0x14001071c  mov     r9d, eax; char *
0x14001071f  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\isolation\\br"...
0x140010726  mov     edx, 29h ; ')'; void *
0x14001072b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140010730  mov     rdx, [rsp+28h+arg_10]; struct IShellItem *
0x140010735  mov     rcx, rsi; void *
0x140010738  call    ?AddItemToBfs@BrokerUtils@Isolation@Security@Windows@@SAXPEAXPEAUIShellItem@@@Z; Windows::Security::Isolation::BrokerUtils::AddItemToBfs(void *,IShellItem *)
0x14001073d  nop
0x14001073e  lea     rcx, [rsp+28h+arg_10]
0x140010743  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x140010748  inc     ebx
0x14001074a  jmp     short loc_1400106EE
0x14001074c  mov     rbx, [rsp+28h+arg_8]
0x140010751  mov     rsi, [rsp+28h+arg_18]
0x140010756  add     rsp, 20h
0x14001075a  pop     rdi
0x14001075b  retn
```
