# Apx::ApfHelper::CreateUuid(_GUID *)

- ea: `0x18000b350`
- end: `0x18000b3e4`
- name: `?CreateUuid@ApfHelper@Apx@@SAJPEAU_GUID@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(UUID *Uuid)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017278`

## callees

- `0x18000a12c`
- `0x18000b350`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000b39a`
- `RPCRT4!UuidCreate` at `0x18000b39a`

## pseudocode

```c
__int64 __fastcall Apx::ApfHelper::CreateUuid(UUID *Uuid)
{
  unsigned int v2; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids);
  }
  *Uuid = 0;
  v2 = UuidCreate(Uuid) != 0 ? 0x80010136 : 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids);
  }
  return v2;
}

```

## disassembly

```asm
0x18000b350  mov     [rsp+arg_0], rbx
0x18000b355  push    rdi
0x18000b356  sub     rsp, 20h
0x18000b35a  mov     rbx, rcx
0x18000b35d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b364  lea     rdi, WPP_GLOBAL_Control
0x18000b36b  cmp     rcx, rdi
0x18000b36e  jz      short loc_18000B391
0x18000b370  test    byte ptr [rcx+1Ch], 1
0x18000b374  jz      short loc_18000B391
0x18000b376  cmp     byte ptr [rcx+19h], 5
0x18000b37a  jb      short loc_18000B391
0x18000b37c  mov     rcx, [rcx+10h]
0x18000b380  lea     r8, WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids
0x18000b387  mov     edx, 1Bh
0x18000b38c  call    WPP_SF_
0x18000b391  xorps   xmm0, xmm0
0x18000b394  movups  xmmword ptr [rbx], xmm0
0x18000b397  mov     rcx, rbx; Uuid
0x18000b39a  call    cs:__imp_UuidCreate
0x18000b3a0  neg     eax
0x18000b3a2  sbb     ebx, ebx
0x18000b3a4  and     ebx, 80010136h
0x18000b3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3b1  cmp     rcx, rdi
0x18000b3b4  jz      short loc_18000B3D7
0x18000b3b6  test    byte ptr [rcx+1Ch], 1
0x18000b3ba  jz      short loc_18000B3D7
0x18000b3bc  cmp     byte ptr [rcx+19h], 5
0x18000b3c0  jb      short loc_18000B3D7
0x18000b3c2  mov     rcx, [rcx+10h]
0x18000b3c6  lea     r8, WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids
0x18000b3cd  mov     edx, 1Ch
0x18000b3d2  call    WPP_SF_
0x18000b3d7  mov     eax, ebx
0x18000b3d9  mov     rbx, [rsp+28h+arg_0]
0x18000b3de  add     rsp, 20h
0x18000b3e2  pop     rdi
0x18000b3e3  retn
```
