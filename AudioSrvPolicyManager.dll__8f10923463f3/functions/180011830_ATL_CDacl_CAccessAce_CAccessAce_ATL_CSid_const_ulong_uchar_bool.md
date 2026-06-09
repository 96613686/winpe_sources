# ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)

- ea: `0x180011830`
- end: `0x180011967`
- name: `??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z`
- size: `311`
- prototype: `__int64 __fastcall(ATL::CDacl::CAccessAce *__hidden this, const struct ATL::CSid *, unsigned int, unsigned __int8, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c3d0`
- `0x1800475d0`

## callees

- `0x180011830`
- `0x180011970`
- `0x18002bd9c`
- `0x18002ccf0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180011902`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180011902`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800118f3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800118f3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800118e6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800118e6`

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
  char *v10; // rdi
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
  v9[14] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( *((_BYTE *)a2 + 76) )
  {
    v10 = (char *)a2 + 8;
    if ( !IsValidSid(v10) )
      ATL::AtlThrowImpl(-2147024809);
    LengthSid = GetLengthSid(v10);
    if ( !CopySid(LengthSid, v9 + 1, v10) )
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
0x180011830  mov     r11, rsp
0x180011833  mov     [r11+10h], rbx
0x180011837  mov     [r11+18h], rbp
0x18001183b  mov     [r11+8], rcx
0x18001183f  push    rsi
0x180011840  push    rdi
0x180011841  push    r14
0x180011843  sub     rsp, 20h
0x180011847  mov     bpl, r9b
0x18001184a  mov     r14d, r8d
0x18001184d  mov     rdi, rdx
0x180011850  mov     rbx, rcx
0x180011853  lea     rax, ??_7CAce@CAcl@ATL@@6B@; const ATL::CAcl::CAce::`vftable'
0x18001185a  mov     [rcx], rax
0x18001185d  lea     rsi, [rcx+8]
0x180011861  mov     [r11+8], rsi
0x180011865  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x18001186c  mov     [rsi], rax
0x18001186f  mov     al, [rdx+4Ch]
0x180011872  mov     [rsi+4Ch], al
0x180011875  mov     eax, [rdx+50h]
0x180011878  mov     [rsi+50h], eax
0x18001187b  mov     rcx, [rdx+58h]
0x18001187f  sub     rcx, 18h
0x180011883  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180011888  add     rax, 18h
0x18001188c  mov     [rsi+58h], rax
0x180011890  mov     rcx, [rdi+60h]
0x180011894  sub     rcx, 18h
0x180011898  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001189d  add     rax, 18h
0x1800118a1  mov     [rsi+60h], rax
0x1800118a5  mov     rcx, [rdi+68h]
0x1800118a9  sub     rcx, 18h
0x1800118ad  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800118b2  add     rax, 18h
0x1800118b6  mov     [rsi+68h], rax
0x1800118ba  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800118c1  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800118c8  mov     rax, [rax+18h]
0x1800118cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118d1  add     rax, 18h
0x1800118d5  mov     [rsi+70h], rax
0x1800118d9  cmp     byte ptr [rdi+4Ch], 0
0x1800118dd  jz      short loc_18001190C
0x1800118df  add     rdi, 8
0x1800118e3  mov     rcx, rdi; pSid
0x1800118e6  call    cs:__imp_IsValidSid
0x1800118ec  test    eax, eax
0x1800118ee  jz      short loc_18001194F
0x1800118f0  mov     rcx, rdi; pSid
0x1800118f3  call    cs:__imp_GetLengthSid
0x1800118f9  lea     rdx, [rsi+8]; pDestinationSid
0x1800118fd  mov     r8, rdi; pSourceSid
0x180011900  mov     ecx, eax; nDestinationSidLength
0x180011902  call    cs:__imp_CopySid
0x180011908  test    eax, eax
0x18001190a  jz      short loc_18001195A
0x18001190c  mov     [rbx+80h], r14d
0x180011913  mov     [rbx+84h], bpl
0x18001191a  mov     qword ptr [rbx+88h], 0
0x180011925  lea     rax, ??_7CAccessAce@CDacl@ATL@@6B@; const ATL::CDacl::CAccessAce::`vftable'
0x18001192c  mov     [rbx], rax
0x18001192f  mov     al, [rsp+38h+arg_20]
0x180011933  mov     [rbx+90h], al
0x180011939  mov     rax, rbx
0x18001193c  mov     rbx, [rsp+38h+arg_8]
0x180011941  mov     rbp, [rsp+38h+arg_10]
0x180011946  add     rsp, 20h
0x18001194a  pop     r14
0x18001194c  pop     rdi
0x18001194d  pop     rsi
0x18001194e  retn
0x18001194f  mov     ecx, 80070057h; int
0x180011954  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001195a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001195f  mov     ecx, eax; int
0x180011961  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
