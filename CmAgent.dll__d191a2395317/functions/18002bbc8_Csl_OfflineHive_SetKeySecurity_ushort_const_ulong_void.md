# Csl::OfflineHive::SetKeySecurity(ushort const *,ulong,void *)

- ea: `0x18002bbc8`
- end: `0x18002bca1`
- name: `?SetKeySecurity@OfflineHive@Csl@@QEAAJPEBGKPEAX@Z`
- size: `217`
- prototype: `__int64 __fastcall(Csl::OfflineHive *this, const unsigned __int16 *, __int64, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028afc`

## callees

- `0x180007b4c`
- `0x18002bbc8`
- `0x18002c6e0`
- `0x18002d190`
- `0x18002d748`

## string_xrefs

- `0x18002bc11`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002bc62`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::SetKeySecurity(
        Csl::OfflineHive *this,
        const unsigned __int16 *a2,
        __int64 a3,
        void *a4)
{
  __int64 v6; // rbx
  __int64 v7; // rax
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // edi
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v6 = 0;
  v15 = 0;
  if ( !a2 )
    goto LABEL_10;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  if ( !v7 )
    goto LABEL_10;
  v8 = OROpenKey(*((_QWORD *)this + 1), a2, &v15);
  if ( v8 )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x3CC,
           (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
           (const char *)v8);
    if ( v15 )
      ORCloseKey(v15);
    return v9;
  }
  v6 = v15;
  v11 = v15;
  if ( !v15 )
LABEL_10:
    v11 = *((_QWORD *)this + 1);
  v12 = ORSetKeySecurity(v11, 4, a4);
  if ( v12 )
  {
    v13 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x3D2,
            (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)v12);
    if ( v6 )
      ORCloseKey(v6);
    return v13;
  }
  else
  {
    if ( v6 )
      ORCloseKey(v6);
    return 0;
  }
}

```

## disassembly

```asm
0x18002bbc8  push    rbx
0x18002bbca  push    rbp
0x18002bbcb  push    rsi
0x18002bbcc  push    rdi
0x18002bbcd  sub     rsp, 28h
0x18002bbd1  mov     rsi, r9
0x18002bbd4  mov     rdi, rcx
0x18002bbd7  xor     ebp, ebp
0x18002bbd9  mov     ebx, ebp
0x18002bbdb  mov     [rsp+48h+arg_8], rbx
0x18002bbe0  test    rdx, rdx
0x18002bbe3  jz      short loc_18002BC45
0x18002bbe5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002bbe9  inc     rax
0x18002bbec  cmp     [rdx+rax*2], bp
0x18002bbf0  jnz     short loc_18002BBE9
0x18002bbf2  test    rax, rax
0x18002bbf5  jz      short loc_18002BC45
0x18002bbf7  lea     r8, [rsp+48h+arg_8]
0x18002bbfc  mov     rcx, [rcx+8]
0x18002bc00  call    OROpenKey
0x18002bc05  test    eax, eax
0x18002bc07  jz      short loc_18002BC38
0x18002bc09  mov     rcx, [rsp+48h]; this
0x18002bc0e  mov     r9d, eax; char *
0x18002bc11  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002bc18  mov     edx, 3CCh; void *
0x18002bc1d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002bc22  mov     ebx, eax
0x18002bc24  mov     rcx, [rsp+48h+arg_8]
0x18002bc29  test    rcx, rcx
0x18002bc2c  jz      short loc_18002BC34
0x18002bc2e  call    ORCloseKey
0x18002bc33  nop
0x18002bc34  mov     eax, ebx
0x18002bc36  jmp     short loc_18002BC97
0x18002bc38  mov     rbx, [rsp+48h+arg_8]
0x18002bc3d  test    rbx, rbx
0x18002bc40  mov     rcx, rbx
0x18002bc43  jnz     short loc_18002BC49
0x18002bc45  mov     rcx, [rdi+8]
0x18002bc49  mov     r8, rsi
0x18002bc4c  mov     edx, 4
0x18002bc51  call    ORSetKeySecurity
0x18002bc56  test    eax, eax
0x18002bc58  jz      short loc_18002BC87
0x18002bc5a  mov     rcx, [rsp+48h]; this
0x18002bc5f  mov     r9d, eax; char *
0x18002bc62  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002bc69  mov     edx, 3D2h; void *
0x18002bc6e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002bc73  mov     edi, eax
0x18002bc75  test    rbx, rbx
0x18002bc78  jz      short loc_18002BC83
0x18002bc7a  mov     rcx, rbx
0x18002bc7d  call    ORCloseKey
0x18002bc82  nop
0x18002bc83  mov     eax, edi
0x18002bc85  jmp     short loc_18002BC97
0x18002bc87  test    rbx, rbx
0x18002bc8a  jz      short loc_18002BC95
0x18002bc8c  mov     rcx, rbx
0x18002bc8f  call    ORCloseKey
0x18002bc94  nop
0x18002bc95  xor     eax, eax
0x18002bc97  add     rsp, 28h
0x18002bc9b  pop     rdi
0x18002bc9c  pop     rsi
0x18002bc9d  pop     rbp
0x18002bc9e  pop     rbx
0x18002bc9f  retn
```
