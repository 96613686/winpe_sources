# APPLICATION_CUSTOM_PROVIDER::SetAppPoolID(ABO_NODE *,ushort *)

- ea: `0x18001af78`
- end: `0x18001b14f`
- name: `?SetAppPoolID@APPLICATION_CUSTOM_PROVIDER@@QEAAJPEAVABO_NODE@@PEAG@Z`
- size: `471`
- prototype: `int(APPLICATION_CUSTOM_PROVIDER *__hidden this, struct ABO_NODE *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800186c0`
- `0x18001ad10`

## callees

- `0x180002990`
- `0x18000341a`
- `0x180003460`
- `0x1800065a8`
- `0x1800077dc`
- `0x180007838`
- `0x18000fa00`
- `0x18000fd48`
- `0x1800186c0`
- `0x18001af78`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b00b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b00b`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001b050`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001b050`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001afcd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001afcd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001b110`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001b110`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b040`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b0d2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b040`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b0d2`

## pseudocode

```c
__int64 __fastcall APPLICATION_CUSTOM_PROVIDER::SetAppPoolID(
        APPLICATION_CUSTOM_PROVIDER *this,
        struct ABO_NODE *a2,
        unsigned __int16 *a3)
{
  int v6; // ebx
  PROPERTY_ENTRY *v7; // rax
  PROPERTY_ENTRY *v8; // rax
  PROPERTY_MAPPING *v9; // rsi
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, const wchar_t *, unsigned __int16 *, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  struct _METADATA_RECORD v14; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[56]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v16[256]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(v16, 0, sizeof(v16));
  STRU::STRU((STRU *)v15, v16, 0x100u);
  if ( a3 )
  {
    if ( (unsigned int)ABO_NODE::FApplicationNode(a2) )
    {
      *(&v14.dwMDDataLen + 1) = 0;
      *(_QWORD *)&v14.dwMDDataTag = 0;
      v6 = STRU::Copy((STRU *)v15, a3);
      if ( v6 < 0 )
        goto LABEL_12;
      v14.dwMDIdentifier = 9101;
      v14.dwMDAttributes = 1;
      v14.dwMDUserType = 1;
      v14.dwMDDataType = 2;
      v14.pbMDData = (unsigned __int8 *)STRU::QueryStr((STRU *)v15);
      v14.dwMDDataLen = 2 * STRU::QueryCCH((STRU *)v15) + 2;
      v7 = (PROPERTY_ENTRY *)operator new(0x50u);
      if ( !v7 || (v8 = PROPERTY_ENTRY::PROPERTY_ENTRY(v7, 1), (v9 = v8) == 0) )
      {
        v6 = -2147024888;
        goto LABEL_12;
      }
      v6 = PROPERTY_ENTRY::Create(v8, &v14);
      if ( v6 < 0
        || (v6 = PROPERTY_BAG::AddEntry((struct ABO_NODE *)((char *)a2 + 184), v9, 1), v6 < 0)
        || (v10 = *((_QWORD *)this + 3),
            v11 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)v10 + 128LL),
            Str = STRU::QueryStr((STRU *)v15),
            v6 = v11(v10, L"applicationPool", Str, 0),
            v6 < 0) )
      {
        PROPERTY_MAPPING::DereferencePropertyMapping(v9);
        goto LABEL_12;
      }
      PROPERTY_MAPPING::DereferencePropertyMapping(v9);
    }
    v6 = CUSTOM_PROPERTY_PROVIDER::SetAppPoolIdRecursive(a2, a3);
    goto LABEL_12;
  }
  v6 = -2147024809;
LABEL_12:
  STRU::~STRU((STRU *)v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001af78  mov     [rsp-8+arg_18], rbx
0x18001af7d  push    rbp
0x18001af7e  push    rsi
0x18001af7f  push    rdi
0x18001af80  push    r14
0x18001af82  push    r15
0x18001af84  lea     rbp, [rsp-1A0h]
0x18001af8c  sub     rsp, 2A0h
0x18001af93  mov     rax, cs:__security_cookie
0x18001af9a  xor     rax, rsp
0x18001af9d  mov     [rbp+1C0h+var_30], rax
0x18001afa4  mov     r15, r8
0x18001afa7  mov     r14, rdx
0x18001afaa  mov     rdi, rcx
0x18001afad  xor     edx, edx; Val
0x18001afaf  mov     r8d, 200h; Size
0x18001afb5  lea     rcx, [rbp+1C0h+var_230]; void *
0x18001afb9  call    memset_0
0x18001afbe  mov     r8d, 100h
0x18001afc4  lea     rdx, [rbp+1C0h+var_230]
0x18001afc8  lea     rcx, [rsp+2C0h+var_268]
0x18001afcd  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001afd3  test    r15, r15
0x18001afd6  jnz     short loc_18001AFE2
0x18001afd8  mov     ebx, 80070057h
0x18001afdd  jmp     loc_18001B10B
0x18001afe2  mov     rcx, r14; this
0x18001afe5  call    ?FApplicationNode@ABO_NODE@@QEAAHXZ; ABO_NODE::FApplicationNode(void)
0x18001afea  test    eax, eax
0x18001afec  jz      loc_18001B0FE
0x18001aff2  mov     rdx, r15
0x18001aff5  mov     dword ptr [rsp+2C0h+var_290+14h], 0
0x18001affd  lea     rcx, [rsp+2C0h+var_268]
0x18001b002  mov     qword ptr [rsp+2C0h+var_290.dwMDDataTag], 0
0x18001b00b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001b011  mov     ebx, eax
0x18001b013  test    eax, eax
0x18001b015  js      loc_18001B10B
0x18001b01b  lea     rcx, [rsp+2C0h+var_268]
0x18001b020  mov     [rsp+2C0h+var_290.dwMDIdentifier], 238Dh
0x18001b028  mov     [rsp+2C0h+var_290.dwMDAttributes], 1
0x18001b030  mov     [rsp+2C0h+var_290.dwMDUserType], 1
0x18001b038  mov     [rsp+2C0h+var_290.dwMDDataType], 2
0x18001b040  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001b046  lea     rcx, [rsp+2C0h+var_268]
0x18001b04b  mov     [rsp+2C0h+var_290.pbMDData], rax
0x18001b050  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001b056  mov     ecx, 50h ; 'P'; Size
0x18001b05b  lea     eax, ds:2[rax*2]
0x18001b062  mov     [rsp+2C0h+var_290.dwMDDataLen], eax
0x18001b066  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b06b  test    rax, rax
0x18001b06e  jz      loc_18001B148
0x18001b074  mov     edx, 1; int
0x18001b079  mov     rcx, rax; this
0x18001b07c  call    ??0PROPERTY_ENTRY@@QEAA@H@Z; PROPERTY_ENTRY::PROPERTY_ENTRY(int)
0x18001b081  mov     rsi, rax
0x18001b084  test    rax, rax
0x18001b087  jz      loc_18001B148
0x18001b08d  lea     rdx, [rsp+2C0h+var_290]; struct _METADATA_RECORD *
0x18001b092  mov     rcx, rax; this
0x18001b095  call    ?Create@PROPERTY_ENTRY@@QEAAJPEAU_METADATA_RECORD@@@Z; PROPERTY_ENTRY::Create(_METADATA_RECORD *)
0x18001b09a  mov     ebx, eax
0x18001b09c  test    eax, eax
0x18001b09e  js      loc_18001B13E
0x18001b0a4  lea     rcx, [r14+0B8h]; this
0x18001b0ab  mov     r8d, 1; int
0x18001b0b1  mov     rdx, rsi; struct PROPERTY_ENTRY *
0x18001b0b4  call    ?AddEntry@PROPERTY_BAG@@QEAAJPEAVPROPERTY_ENTRY@@H@Z; PROPERTY_BAG::AddEntry(PROPERTY_ENTRY *,int)
0x18001b0b9  mov     ebx, eax
0x18001b0bb  test    eax, eax
0x18001b0bd  js      short loc_18001B13E
0x18001b0bf  mov     rdi, [rdi+18h]
0x18001b0c3  lea     rcx, [rsp+2C0h+var_268]
0x18001b0c8  mov     rax, [rdi]
0x18001b0cb  mov     rbx, [rax+80h]
0x18001b0d2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001b0d8  xor     r9d, r9d
0x18001b0db  lea     rdx, aApplicationpoo_0; "applicationPool"
0x18001b0e2  mov     r8, rax
0x18001b0e5  mov     rcx, rdi
0x18001b0e8  mov     rax, rbx
0x18001b0eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0f0  mov     ebx, eax
0x18001b0f2  test    eax, eax
0x18001b0f4  js      short loc_18001B13E
0x18001b0f6  mov     rcx, rsi; this
0x18001b0f9  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18001b0fe  mov     rdx, r15; unsigned __int16 *
0x18001b101  mov     rcx, r14; struct ABO_NODE *
0x18001b104  call    ?SetAppPoolIdRecursive@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVABO_NODE@@PEAG@Z; CUSTOM_PROPERTY_PROVIDER::SetAppPoolIdRecursive(ABO_NODE *,ushort *)
0x18001b109  mov     ebx, eax
0x18001b10b  lea     rcx, [rsp+2C0h+var_268]
0x18001b110  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001b116  mov     eax, ebx
0x18001b118  mov     rcx, [rbp+1C0h+var_30]
0x18001b11f  xor     rcx, rsp; StackCookie
0x18001b122  call    __security_check_cookie
0x18001b127  mov     rbx, [rsp+2C0h+arg_18]
0x18001b12f  add     rsp, 2A0h
0x18001b136  pop     r15
0x18001b138  pop     r14
0x18001b13a  pop     rdi
0x18001b13b  pop     rsi
0x18001b13c  pop     rbp
0x18001b13d  retn
0x18001b13e  mov     rcx, rsi; this
0x18001b141  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18001b146  jmp     short loc_18001B10B
0x18001b148  mov     ebx, 80070008h
0x18001b14d  jmp     short loc_18001B10B
```
