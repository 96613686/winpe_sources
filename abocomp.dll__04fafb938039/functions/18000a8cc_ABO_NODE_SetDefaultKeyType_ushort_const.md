# ABO_NODE::SetDefaultKeyType(ushort const *)

- ea: `0x18000a8cc`
- end: `0x18000a9ff`
- name: `?SetDefaultKeyType@ABO_NODE@@QEAAJPEBG@Z`
- size: `307`
- prototype: `__int64 __fastcall(ABO_NODE *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180004b80`
- `0x180007148`

## callees

- `0x18000341a`
- `0x180003460`
- `0x1800077dc`
- `0x18000a6fc`
- `0x18000a8cc`
- `0x18000fec4`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a96c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a96c`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000a9a1`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000a9a1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a91d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a91d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a9d3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a9d3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a993`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a993`

## pseudocode

```c
__int64 __fastcall ABO_NODE::SetDefaultKeyType(ABO_NODE *this, const unsigned __int16 *a2)
{
  int v4; // edi
  struct PROPERTY_ENTRY *v5; // rbx
  int Entry; // eax
  struct PROPERTY_ENTRY *v8; // [rsp+20h] [rbp-79h] BYREF
  struct _METADATA_RECORD v9; // [rsp+28h] [rbp-71h] BYREF
  _BYTE v10[64]; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 v11[32]; // [rsp+90h] [rbp-9h] BYREF

  v4 = 0;
  v5 = 0;
  v8 = 0;
  memset_0(v11, 0, sizeof(v11));
  STRU::STRU((STRU *)v10, v11, 0x20u);
  if ( !*((_DWORD *)this + 54) )
  {
    if ( !*((_DWORD *)this + 50)
      || (Entry = PROPERTY_BAG::FindEntry((ABO_NODE *)((char *)this + 184), 0x3EAu, &v8),
          v5 = v8,
          v4 = Entry,
          Entry == -2147024894) )
    {
      *(&v9.dwMDDataLen + 1) = 0;
      *(_QWORD *)&v9.dwMDDataTag = 0;
      v4 = STRU::Copy((STRU *)v10, a2);
      if ( v4 >= 0 )
      {
        *(_QWORD *)&v9.dwMDIdentifier = 1002;
        v9.dwMDUserType = 1;
        v9.dwMDDataType = 2;
        v9.pbMDData = (unsigned __int8 *)STRU::QueryStr((STRU *)v10);
        v9.dwMDDataLen = 2 * STRU::QueryCCH((STRU *)v10) + 2;
        v4 = ABO_NODE::SetData(this, &v9, 1);
      }
    }
    if ( v5 )
      PROPERTY_MAPPING::DereferencePropertyMapping(v5);
  }
  STRU::~STRU((STRU *)v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000a8cc  mov     [rsp-8+arg_10], rbx
0x18000a8d1  mov     [rsp-8+arg_18], rsi
0x18000a8d6  push    rbp
0x18000a8d7  push    rdi
0x18000a8d8  push    r14
0x18000a8da  lea     rbp, [rsp-47h]
0x18000a8df  sub     rsp, 0E0h
0x18000a8e6  mov     rax, cs:__security_cookie
0x18000a8ed  xor     rax, rsp
0x18000a8f0  mov     [rbp+57h+var_20], rax
0x18000a8f4  mov     r14, rdx
0x18000a8f7  mov     rsi, rcx
0x18000a8fa  xor     edi, edi
0x18000a8fc  lea     rcx, [rbp+57h+var_60]; void *
0x18000a900  xor     ebx, ebx
0x18000a902  xor     edx, edx; Val
0x18000a904  mov     [rbp+57h+var_D0], rbx
0x18000a908  lea     r8d, [rdi+40h]; Size
0x18000a90c  call    memset_0
0x18000a911  lea     r8d, [rdi+20h]
0x18000a915  lea     rdx, [rbp+57h+var_60]
0x18000a919  lea     rcx, [rbp+57h+var_A0]
0x18000a91d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000a923  cmp     [rsi+0D8h], ebx
0x18000a929  ja      loc_18000A9CF
0x18000a92f  lea     rcx, [rsi+0B8h]; this
0x18000a936  cmp     [rcx+10h], ebx
0x18000a939  jbe     short loc_18000A956
0x18000a93b  lea     r8, [rbp+57h+var_D0]; struct PROPERTY_ENTRY **
0x18000a93f  mov     edx, 3EAh; unsigned int
0x18000a944  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x18000a949  mov     rbx, [rbp+57h+var_D0]
0x18000a94d  mov     edi, eax
0x18000a94f  cmp     eax, 80070002h
0x18000a954  jnz     short loc_18000A9C2
0x18000a956  mov     rdx, r14
0x18000a959  mov     dword ptr [rbp+57h+var_C8+14h], 0
0x18000a960  lea     rcx, [rbp+57h+var_A0]
0x18000a964  mov     qword ptr [rbp+57h+var_C8.dwMDDataTag], 0
0x18000a96c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a972  mov     edi, eax
0x18000a974  test    eax, eax
0x18000a976  js      short loc_18000A9C2
0x18000a978  mov     edi, 1
0x18000a97d  mov     qword ptr [rbp+57h+var_C8.dwMDIdentifier], 3EAh
0x18000a985  lea     rcx, [rbp+57h+var_A0]
0x18000a989  mov     [rbp+57h+var_C8.dwMDUserType], edi
0x18000a98c  mov     [rbp+57h+var_C8.dwMDDataType], 2
0x18000a993  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a999  lea     rcx, [rbp+57h+var_A0]
0x18000a99d  mov     [rbp+57h+var_C8.pbMDData], rax
0x18000a9a1  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000a9a7  mov     r8d, edi; int
0x18000a9aa  lea     rdx, [rbp+57h+var_C8]; struct _METADATA_RECORD *
0x18000a9ae  mov     rcx, rsi; this
0x18000a9b1  lea     eax, ds:2[rax*2]
0x18000a9b8  mov     [rbp+57h+var_C8.dwMDDataLen], eax
0x18000a9bb  call    ?SetData@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@H@Z; ABO_NODE::SetData(_METADATA_RECORD *,int)
0x18000a9c0  mov     edi, eax
0x18000a9c2  test    rbx, rbx
0x18000a9c5  jz      short loc_18000A9CF
0x18000a9c7  mov     rcx, rbx; this
0x18000a9ca  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18000a9cf  lea     rcx, [rbp+57h+var_A0]
0x18000a9d3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a9d9  mov     eax, edi
0x18000a9db  mov     rcx, [rbp+57h+var_20]
0x18000a9df  xor     rcx, rsp; StackCookie
0x18000a9e2  call    __security_check_cookie
0x18000a9e7  lea     r11, [rsp+0F0h+var_10]
0x18000a9ef  mov     rbx, [r11+30h]
0x18000a9f3  mov     rsi, [r11+38h]
0x18000a9f7  mov     rsp, r11
0x18000a9fa  pop     r14
0x18000a9fc  pop     rdi
0x18000a9fd  pop     rbp
0x18000a9fe  retn
```
