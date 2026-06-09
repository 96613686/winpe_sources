# NetSetupGetOrCreateIdFromProperties(_NETSETUP_OBJECT_TYPE,NetSetup2::PropertyArray const &,_GUID *)

- ea: `0x18004467c`
- end: `0x1800447c5`
- name: `?NetSetupGetOrCreateIdFromProperties@@YAXW4_NETSETUP_OBJECT_TYPE@@AEBVPropertyArray@NetSetup2@@PEAU_GUID@@@Z`
- size: `329`
- prototype: `void __high(enum _NETSETUP_OBJECT_TYPE, const struct NetSetup2::PropertyArray *, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18006e5b8`

## callees

- `0x180017d20`
- `0x180030f80`
- `0x18004467c`
- `0x18005097c`
- `0x18005c848`
- `0x1800620ec`
- `0x180065035`
- `0x1800810d0`

## import_xrefs

- `RPCRT4!UuidCreateNil` at `0x180044790`
- `RPCRT4!UuidCreateNil` at `0x180044790`
- `RPCRT4!UuidCreate` at `0x1800447a6`
- `RPCRT4!UuidCreate` at `0x1800447a6`

## pseudocode

```c
int __fastcall NetSetupGetOrCreateIdFromProperties(unsigned int a1, __int64 *a2, UUID *a3)
{
  unsigned int v4; // r10d
  __int64 v5; // rcx
  __int64 *v6; // r8
  __int64 v7; // r9
  __int64 v8; // rax
  struct _GUID *Guid; // rax
  _BYTE pExceptionObject[208]; // [rsp+20h] [rbp-F8h] BYREF
  UUID NilUuid; // [rsp+F0h] [rbp-28h] BYREF

  v4 = a1;
  v5 = *a2;
  v6 = a2;
  v7 = 0;
  while ( v5 != v6[1] )
  {
    if ( *(_DWORD *)(v5 + 20) )
    {
      if ( *(_DWORD *)(v5 + 16) == 2 )
      {
        v8 = *(_QWORD *)v5 - NETSETUPPKEY_Object_Id;
        if ( *(_QWORD *)v5 == NETSETUPPKEY_Object_Id )
          v8 = *(_QWORD *)(v5 + 8) - *(&NETSETUPPKEY_Object_Id + 1);
        if ( !v8 )
          goto LABEL_12;
      }
      if ( operator==(v5, (__int64)NETSETUPPKEY_FilterDriver_BindName) )
      {
LABEL_12:
        Guid = NetSetup2::Property::GetGuid((NetSetup2::Property *)v5, &NilUuid);
        *a3 = *Guid;
        return (int)Guid;
      }
      if ( operator==(v5, (__int64)&NETSETUPPKEY_Driver_BindName) )
        v7 = v5;
    }
    v5 += 48;
  }
  if ( v4 == 3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4b88b089970e3aec0e95da985ca9f982_Traceguids);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
  if ( v7 )
  {
    CreateIdFromHash(v4, v7, a3);
    NilUuid = *a3;
    LODWORD(Guid) = UuidCreateNil(&NilUuid);
  }
  else
  {
    *a3 = *(UUID *)L"NSObjId";
    LODWORD(Guid) = UuidCreate(a3);
  }
  return (int)Guid;
}

```

## disassembly

```asm
0x18004467c  push    rbx
0x18004467e  sub     rsp, 110h
0x180044685  mov     rax, cs:__security_cookie
0x18004468c  xor     rax, rsp
0x18004468f  mov     [rsp+118h+var_18], rax
0x180044697  mov     rbx, r8
0x18004469a  mov     r10d, ecx
0x18004469d  mov     rcx, [rdx]; this
0x1800446a0  mov     r8, rdx
0x1800446a3  xor     r9d, r9d
0x1800446a6  cmp     rcx, [r8+8]
0x1800446aa  jz      short loc_180044715
0x1800446ac  cmp     dword ptr [rcx+14h], 0
0x1800446b0  jz      short loc_1800446F6
0x1800446b2  cmp     dword ptr [rcx+10h], 2
0x1800446b6  jnz     short loc_1800446D4
0x1800446b8  mov     rax, [rcx]
0x1800446bb  sub     rax, qword ptr cs:NETSETUPPKEY_Object_Id
0x1800446c2  jnz     short loc_1800446CF
0x1800446c4  mov     rax, [rcx+8]
0x1800446c8  sub     rax, qword ptr cs:NETSETUPPKEY_Object_Id+8
0x1800446cf  test    rax, rax
0x1800446d2  jz      short loc_1800446FC
0x1800446d4  lea     rdx, NETSETUPPKEY_FilterDriver_BindName
0x1800446db  call    ??8@YA_NAEBU_NETSETUPPROPKEY@@0@Z; operator==(_NETSETUPPROPKEY const &,_NETSETUPPROPKEY const &)
0x1800446e0  test    al, al
0x1800446e2  jnz     short loc_1800446FC
0x1800446e4  lea     rdx, NETSETUPPKEY_Driver_BindName
0x1800446eb  call    ??8@YA_NAEBU_NETSETUPPROPKEY@@0@Z; operator==(_NETSETUPPROPKEY const &,_NETSETUPPROPKEY const &)
0x1800446f0  test    al, al
0x1800446f2  cmovnz  r9, rcx
0x1800446f6  add     rcx, 30h ; '0'
0x1800446fa  jmp     short loc_1800446A6
0x1800446fc  lea     rdx, [rsp+118h+NilUuid]; retstr
0x180044704  call    ?GetGuid@Property@NetSetup2@@QEBA?AU_GUID@@XZ; NetSetup2::Property::GetGuid(void)
0x180044709  movups  xmm0, xmmword ptr [rax]
0x18004470c  movdqu  xmmword ptr [rbx], xmm0
0x180044710  jmp     loc_1800447AC
0x180044715  cmp     r10d, 3
0x180044719  jnz     short loc_180044769
0x18004471b  mov     rcx, cs:WPP_GLOBAL_Control
0x180044722  lea     rax, WPP_GLOBAL_Control
0x180044729  cmp     rcx, rax
0x18004472c  jz      short loc_180044748
0x18004472e  cmp     byte ptr [rcx+19h], 2
0x180044732  jb      short loc_180044748
0x180044734  mov     rcx, [rcx+10h]
0x180044738  lea     edx, [r10+8]
0x18004473c  lea     r8, WPP_4b88b089970e3aec0e95da985ca9f982_Traceguids
0x180044743  call    WPP_SF_
0x180044748  mov     edx, 80070057h; int
0x18004474d  lea     rcx, [rsp+118h+pExceptionObject]; this
0x180044752  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180044757  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18004475e  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180044763  call    _CxxThrowException_0
0x180044769  test    r9, r9
0x18004476c  jz      short loc_180044798
0x18004476e  mov     r8, rbx
0x180044771  mov     rdx, r9
0x180044774  mov     ecx, r10d
0x180044777  call    CreateIdFromHash
0x18004477c  movups  xmm0, xmmword ptr [rbx]
0x18004477f  lea     rcx, [rsp+118h+NilUuid]; NilUuid
0x180044787  movdqu  xmmword ptr [rsp+118h+NilUuid.Data1], xmm0
0x180044790  call    cs:__imp_UuidCreateNil
0x180044796  jmp     short loc_1800447AC
0x180044798  movups  xmm0, xmmword ptr cs:aNsobjid; "NSObjId"
0x18004479f  mov     rcx, rbx; Uuid
0x1800447a2  movdqu  xmmword ptr [rbx], xmm0
0x1800447a6  call    cs:__imp_UuidCreate
0x1800447ac  mov     rcx, [rsp+118h+var_18]
0x1800447b4  xor     rcx, rsp; StackCookie
0x1800447b7  call    __security_check_cookie
0x1800447bc  add     rsp, 110h
0x1800447c3  pop     rbx
0x1800447c4  retn
```
