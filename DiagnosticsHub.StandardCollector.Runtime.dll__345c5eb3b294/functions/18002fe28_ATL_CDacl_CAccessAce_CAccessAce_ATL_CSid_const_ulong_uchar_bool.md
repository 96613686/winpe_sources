# ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)

- ea: `0x18002fe28`
- end: `0x18002ff72`
- name: `??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z`
- size: `330`
- prototype: `__int64 __fastcall(ATL::CDacl::CAccessAce *__hidden this, const struct ATL::CSid *, unsigned int, unsigned __int8, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18002fb2c`
- `0x180030260`

## callees

- `0x180002604`
- `0x18000288c`
- `0x18002fe28`
- `0x180031390`
- `0x18003151c`
- `0x18004b640`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x18002fef2`
- `ADVAPI32!GetLengthSid` at `0x18002fef2`
- `ADVAPI32!CopySid` at `0x18002ff01`
- `ADVAPI32!CopySid` at `0x18002ff01`
- `ADVAPI32!IsValidSid` at `0x18002fee5`
- `ADVAPI32!IsValidSid` at `0x18002fee5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
ATL::CDacl::CAccessAce *__fastcall ATL::CDacl::CAccessAce::CAccessAce(
        ATL::CDacl::CAccessAce *this,
        const struct ATL::CSid *a2,
        int a3,
        char a4,
        bool a5)
{
  _QWORD *v9; // rsi
  struct ATL::IAtlStringMgr *Instance; // rax
  char *v11; // rdi
  DWORD LengthSid; // eax
  int Error; // eax

  *(_QWORD *)this = &ATL::CAcl::CAce::`vftable';
  v9 = (_QWORD *)((char *)this + 8);
  *((_QWORD *)this + 1) = &ATL::CSid::`vftable';
  *((_BYTE *)this + 84) = *((_BYTE *)a2 + 76);
  *((_DWORD *)this + 22) = *((_DWORD *)a2 + 20);
  *((_QWORD *)this + 12) = ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)a2 + 11) - 24LL) + 24;
  v9[12] = ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)a2 + 12) - 24LL) + 24;
  v9[13] = ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)a2 + 13) - 24LL) + 24;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v9[14] = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
  if ( *((_BYTE *)a2 + 76) )
  {
    v11 = (char *)a2 + 8;
    if ( !IsValidSid(v11) )
      ATL::AtlThrowImpl(-2147024809);
    LengthSid = GetLengthSid(v11);
    if ( !CopySid(LengthSid, v9 + 1, v11) )
    {
      Error = ATL::AtlHresultFromLastError();
      ATL::AtlThrowImpl(Error);
    }
  }
  *((_DWORD *)this + 32) = a3;
  *((_BYTE *)this + 132) = a4;
  *((_QWORD *)this + 17) = 0;
  *(_QWORD *)this = &ATL::CDacl::CAccessAce::`vftable';
  *((_BYTE *)this + 144) = a5;
  return this;
}

```

## disassembly

```asm
0x18002fe28  mov     r11, rsp
0x18002fe2b  mov     [r11+10h], rbx
0x18002fe2f  mov     [r11+18h], rbp
0x18002fe33  mov     [r11+8], rcx
0x18002fe37  push    rsi
0x18002fe38  push    rdi
0x18002fe39  push    r14
0x18002fe3b  sub     rsp, 20h
0x18002fe3f  mov     bpl, r9b
0x18002fe42  mov     r14d, r8d
0x18002fe45  mov     rdi, rdx
0x18002fe48  mov     rbx, rcx
0x18002fe4b  lea     rax, ??_7CAce@CAcl@ATL@@6B@; const ATL::CAcl::CAce::`vftable'
0x18002fe52  mov     [rcx], rax
0x18002fe55  lea     rsi, [rcx+8]
0x18002fe59  mov     [r11+8], rsi
0x18002fe5d  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x18002fe64  mov     [rsi], rax
0x18002fe67  mov     al, [rdx+4Ch]
0x18002fe6a  mov     [rsi+4Ch], al
0x18002fe6d  mov     eax, [rdx+50h]
0x18002fe70  mov     [rsi+50h], eax
0x18002fe73  mov     rcx, [rdx+58h]
0x18002fe77  sub     rcx, 18h
0x18002fe7b  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18002fe80  add     rax, 18h
0x18002fe84  mov     [rsi+58h], rax
0x18002fe88  mov     rcx, [rdi+60h]
0x18002fe8c  sub     rcx, 18h
0x18002fe90  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18002fe95  add     rax, 18h
0x18002fe99  mov     [rsi+60h], rax
0x18002fe9d  mov     rcx, [rdi+68h]
0x18002fea1  sub     rcx, 18h
0x18002fea5  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18002feaa  add     rax, 18h
0x18002feae  mov     [rsi+68h], rax
0x18002feb2  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18002feb7  mov     rcx, rax
0x18002feba  test    rax, rax
0x18002febd  jz      loc_18002FF5C
0x18002fec3  mov     rax, [rax]
0x18002fec6  mov     rax, [rax+18h]
0x18002feca  call    cs:__guard_dispatch_icall_fptr
0x18002fed0  add     rax, 18h
0x18002fed4  mov     [rsi+70h], rax
0x18002fed8  cmp     byte ptr [rdi+4Ch], 0
0x18002fedc  jz      short loc_18002FF0B
0x18002fede  add     rdi, 8
0x18002fee2  mov     rcx, rdi; pSid
0x18002fee5  call    cs:__imp_IsValidSid
0x18002feeb  test    eax, eax
0x18002feed  jz      short loc_18002FF67
0x18002feef  mov     rcx, rdi; pSid
0x18002fef2  call    cs:__imp_GetLengthSid
0x18002fef8  lea     rdx, [rsi+8]; pDestinationSid
0x18002fefc  mov     r8, rdi; pSourceSid
0x18002feff  mov     ecx, eax; nDestinationSidLength
0x18002ff01  call    cs:__imp_CopySid
0x18002ff07  test    eax, eax
0x18002ff09  jz      short loc_18002FF4E
0x18002ff0b  mov     [rbx+80h], r14d
0x18002ff12  mov     [rbx+84h], bpl
0x18002ff19  mov     qword ptr [rbx+88h], 0
0x18002ff24  lea     rax, ??_7CAccessAce@CDacl@ATL@@6B@; const ATL::CDacl::CAccessAce::`vftable'
0x18002ff2b  mov     [rbx], rax
0x18002ff2e  mov     al, [rsp+38h+arg_20]
0x18002ff32  mov     [rbx+90h], al
0x18002ff38  mov     rax, rbx
0x18002ff3b  mov     rbx, [rsp+38h+arg_8]
0x18002ff40  mov     rbp, [rsp+38h+arg_10]
0x18002ff45  add     rsp, 20h
0x18002ff49  pop     r14
0x18002ff4b  pop     rdi
0x18002ff4c  pop     rsi
0x18002ff4d  retn
0x18002ff4e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002ff53  nop
0x18002ff54  mov     ecx, eax; int
0x18002ff56  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002ff5c  mov     ecx, 80004005h; int
0x18002ff61  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002ff67  mov     ecx, 80070057h; int
0x18002ff6c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
