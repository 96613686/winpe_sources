# ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)

- ea: `0x1400124d0`
- end: `0x14001260e`
- name: `??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z`
- size: `318`
- prototype: `ATL::CDacl::CAccessAce *__fastcall(ATL::CDacl::CAccessAce *this, const struct ATL::CSid *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140012610`

## callees

- `0x140002b4c`
- `0x140002e74`
- `0x14000916c`
- `0x1400123d8`
- `0x1400124d0`
- `0x140014c70`

## import_xrefs

- `ADVAPI32!IsValidSid` at `0x140012584`
- `ADVAPI32!IsValidSid` at `0x140012584`
- `ADVAPI32!GetLengthSid` at `0x140012591`
- `ADVAPI32!GetLengthSid` at `0x140012591`
- `ADVAPI32!CopySid` at `0x1400125a0`
- `ADVAPI32!CopySid` at `0x1400125a0`

## pseudocode

```c
ATL::CDacl::CAccessAce *__fastcall ATL::CDacl::CAccessAce::CAccessAce(
        ATL::CDacl::CAccessAce *this,
        const struct ATL::CSid *a2)
{
  _QWORD *v4; // rsi
  struct ATL::IAtlStringMgr *Instance; // rax
  char *v6; // rdi
  DWORD LengthSid; // eax
  int Error; // eax

  *(_QWORD *)this = &ATL::CAcl::CAce::`vftable';
  v4 = (_QWORD *)((char *)this + 8);
  *((_QWORD *)this + 1) = &ATL::CSid::`vftable';
  *((_BYTE *)this + 84) = *((_BYTE *)a2 + 76);
  *((_DWORD *)this + 22) = *((_DWORD *)a2 + 20);
  *((_QWORD *)this + 12) = ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)a2 + 11) - 24LL) + 24;
  v4[12] = ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)a2 + 12) - 24LL) + 24;
  v4[13] = ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)a2 + 13) - 24LL) + 24;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v4[14] = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
  if ( *((_BYTE *)a2 + 76) )
  {
    v6 = (char *)a2 + 8;
    if ( !IsValidSid(v6) )
      ATL::AtlThrowImpl(-2147024809);
    LengthSid = GetLengthSid(v6);
    if ( !CopySid(LengthSid, v4 + 1, v6) )
    {
      Error = ATL::AtlHresultFromLastError();
      ATL::AtlThrowImpl(Error);
    }
  }
  *((_DWORD *)this + 32) = 0x80000000;
  *((_BYTE *)this + 132) = 0;
  *((_QWORD *)this + 17) = 0;
  *(_QWORD *)this = &ATL::CDacl::CAccessAce::`vftable';
  *((_BYTE *)this + 144) = 1;
  return this;
}

```

## disassembly

```asm
0x1400124d0  mov     r11, rsp
0x1400124d3  mov     [r11+10h], rbx
0x1400124d7  mov     [r11+18h], rsi
0x1400124db  mov     [r11+8], rcx
0x1400124df  push    rdi
0x1400124e0  sub     rsp, 20h
0x1400124e4  mov     rdi, rdx
0x1400124e7  mov     rbx, rcx
0x1400124ea  lea     rax, ??_7CAce@CAcl@ATL@@6B@; const ATL::CAcl::CAce::`vftable'
0x1400124f1  mov     [rcx], rax
0x1400124f4  lea     rsi, [rcx+8]
0x1400124f8  mov     [r11+8], rsi
0x1400124fc  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x140012503  mov     [rsi], rax
0x140012506  mov     al, [rdx+4Ch]
0x140012509  mov     [rsi+4Ch], al
0x14001250c  mov     eax, [rdx+50h]
0x14001250f  mov     [rsi+50h], eax
0x140012512  mov     rcx, [rdx+58h]
0x140012516  sub     rcx, 18h
0x14001251a  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001251f  add     rax, 18h
0x140012523  mov     [rsi+58h], rax
0x140012527  mov     rcx, [rdi+60h]
0x14001252b  sub     rcx, 18h
0x14001252f  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140012534  add     rax, 18h
0x140012538  mov     [rsi+60h], rax
0x14001253c  mov     rcx, [rdi+68h]
0x140012540  sub     rcx, 18h
0x140012544  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140012549  add     rax, 18h
0x14001254d  mov     [rsi+68h], rax
0x140012551  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140012556  mov     rcx, rax
0x140012559  test    rax, rax
0x14001255c  jz      loc_1400125F8
0x140012562  mov     rax, [rax]
0x140012565  mov     rax, [rax+18h]
0x140012569  call    cs:__guard_dispatch_icall_fptr
0x14001256f  add     rax, 18h
0x140012573  mov     [rsi+70h], rax
0x140012577  cmp     byte ptr [rdi+4Ch], 0
0x14001257b  jz      short loc_1400125AA
0x14001257d  add     rdi, 8
0x140012581  mov     rcx, rdi; pSid
0x140012584  call    cs:__imp_IsValidSid
0x14001258a  test    eax, eax
0x14001258c  jz      short loc_140012603
0x14001258e  mov     rcx, rdi; pSid
0x140012591  call    cs:__imp_GetLengthSid
0x140012597  lea     rdx, [rsi+8]; pDestinationSid
0x14001259b  mov     r8, rdi; pSourceSid
0x14001259e  mov     ecx, eax; nDestinationSidLength
0x1400125a0  call    cs:__imp_CopySid
0x1400125a6  test    eax, eax
0x1400125a8  jz      short loc_1400125EA
0x1400125aa  mov     dword ptr [rbx+80h], 80000000h
0x1400125b4  mov     byte ptr [rbx+84h], 0
0x1400125bb  mov     qword ptr [rbx+88h], 0
0x1400125c6  lea     rax, ??_7CAccessAce@CDacl@ATL@@6B@; const ATL::CDacl::CAccessAce::`vftable'
0x1400125cd  mov     [rbx], rax
0x1400125d0  mov     byte ptr [rbx+90h], 1
0x1400125d7  mov     rax, rbx
0x1400125da  mov     rbx, [rsp+28h+arg_8]
0x1400125df  mov     rsi, [rsp+28h+arg_10]
0x1400125e4  add     rsp, 20h
0x1400125e8  pop     rdi
0x1400125e9  retn
0x1400125ea  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1400125ef  nop
0x1400125f0  mov     ecx, eax; int
0x1400125f2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400125f8  mov     ecx, 80004005h; int
0x1400125fd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140012603  mov     ecx, 80070057h; int
0x140012608  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
