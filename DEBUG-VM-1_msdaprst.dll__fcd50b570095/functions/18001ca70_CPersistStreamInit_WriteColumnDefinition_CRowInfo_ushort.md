# CPersistStreamInit::WriteColumnDefinition(CRowInfo &,ushort)

- ea: `0x18001ca70`
- end: `0x18001cceb`
- name: `?WriteColumnDefinition@CPersistStreamInit@@AEAAJAEAVCRowInfo@@G@Z`
- size: `635`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *, unsigned __int16)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18001e7a4`

## callees

- `0x180003abc`
- `0x180004038`
- `0x180004070`
- `0x1800041f8`
- `0x18001b728`
- `0x18001c818`
- `0x18001ca70`
- `0x18001ccf4`
- `0x18001ce6c`
- `0x18001d3b4`
- `0x18001e348`
- `0x18001f470`
- `0x18001f818`
- `0x18002e060`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteColumnDefinition(
        CPersistStreamInit *this,
        struct CRowInfo *a2,
        unsigned __int16 a3)
{
  __int64 v3; // rax
  __int64 v7; // r14
  unsigned __int16 *v8; // r12
  unsigned __int16 *Name; // rax
  CMetaData *v10; // rcx
  unsigned __int16 *v11; // r15
  unsigned __int16 v12; // dx
  BOOL v13; // eax
  unsigned __int8 v14; // bp
  __int64 result; // rax
  bool v16; // r9
  bool v17; // r9
  unsigned int Ordinal; // eax
  unsigned __int64 v19; // r9
  bool v20; // r9
  unsigned int Flags; // eax
  int v22; // [rsp+20h] [rbp-268h]
  unsigned int v23[4]; // [rsp+30h] [rbp-258h] BYREF
  unsigned __int16 v24[256]; // [rsp+40h] [rbp-248h] BYREF

  v3 = *((_QWORD *)a2 + 8);
  v23[0] = 0;
  v7 = 2LL * a3;
  v8 = *(unsigned __int16 **)(v3 + 16LL * a3);
  Name = CMetaData::mdGetName(a2, a3);
  v11 = (unsigned __int16 *)&wszZls;
  if ( Name )
    v11 = Name;
  v13 = (CMetaData::mdGetFlags(v10, a3) & 0x2000) != 0 || CMetaData::mdGetType(a2, v12) == 136;
  v14 = 6 - v13;
  result = CPersistStreamInit::Indent(this, *((_DWORD *)this + 12));
  if ( (int)result >= 0 )
  {
    result = CPersistStreamInit::WriteTag(this, 0x30u, v23);
    if ( (int)result >= 0 )
    {
      result = CPersistStreamInit::WriteNamespace(this, 0x3Fu);
      if ( (int)result >= 0 )
      {
        result = CPersistStreamInit::WriteTag(this, v14, v23);
        if ( (int)result >= 0 )
        {
          result = CPersistStreamInit::WriteAttributeDefinition(
                     this,
                     *(void **)(*((_QWORD *)this + 9) + 48LL),
                     v8,
                     v16,
                     0,
                     0);
          if ( (int)result >= 0 )
          {
            ++*((_DWORD *)this + 12);
            if ( !*(_BYTE *)(*((_QWORD *)a2 + 8) + 8 * v7 + 8)
              || (result = CPersistStreamInit::WriteAttributeDefinition(
                             this,
                             *(void **)(*((_QWORD *)this + 9) + 1728LL),
                             v11,
                             v17,
                             65,
                             1),
                  (int)result >= 0) )
            {
              Ordinal = CMetaData::mdGetOrdinal(a2, a3);
              CPersistStreamInit::_ulto(this, Ordinal, v24, v19, v22);
              result = CPersistStreamInit::WriteAttributeDefinition(
                         this,
                         *(void **)(*((_QWORD *)this + 9) + 1680LL),
                         v24,
                         v20,
                         65,
                         0);
              if ( (int)result >= 0 )
              {
                Flags = CMetaData::mdGetFlags(a2, a3);
                result = CPersistStreamInit::WriteColumnFlags(this, Flags);
                if ( (int)result >= 0 )
                {
                  result = CPersistStreamInit::WriteColumnMetaData(this, a2, a3);
                  if ( (int)result >= 0 )
                  {
                    result = CPersistStreamInit::WriteTag(this, 0x31u, v23);
                    if ( (int)result >= 0 )
                    {
                      result = CPersistStreamInit::WriteTag(this, 0x28u, v23);
                      if ( (int)result >= 0 )
                      {
                        result = CPersistStreamInit::WriteColumnTypeInfo(this, a2, a3);
                        if ( (int)result >= 0 )
                        {
                          CPersistStreamInit::Indent(this, --*((_DWORD *)this + 12));
                          result = CPersistStreamInit::WriteTag(this, 0x33u, v23);
                          if ( (int)result >= 0 )
                          {
                            result = CPersistStreamInit::WriteNamespace(this, 0x3Fu);
                            if ( (int)result >= 0 )
                            {
                              result = CPersistStreamInit::WriteTag(this, v14, v23);
                              if ( (int)result >= 0 )
                              {
                                result = CPersistStreamInit::WriteTag(this, 0x31u, v23);
                                if ( (int)result >= 0 )
                                  return CPersistStreamInit::WriteTag(this, 0x28u, v23);
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ca70  push    rbx
0x18001ca72  push    rbp
0x18001ca73  push    rsi
0x18001ca74  push    rdi
0x18001ca75  push    r12
0x18001ca77  push    r14
0x18001ca79  push    r15
0x18001ca7b  sub     rsp, 250h
0x18001ca82  mov     rax, cs:__security_cookie
0x18001ca89  xor     rax, rsp
0x18001ca8c  mov     [rsp+288h+var_48], rax
0x18001ca94  mov     rax, [rdx+40h]
0x18001ca98  mov     rdi, rdx
0x18001ca9b  movzx   esi, r8w
0x18001ca9f  mov     rbx, rcx
0x18001caa2  mov     [rsp+288h+var_258], 0
0x18001caaa  mov     r14d, esi
0x18001caad  add     r14, r14
0x18001cab0  movzx   edx, si; unsigned __int16
0x18001cab3  mov     rcx, rdi; this
0x18001cab6  mov     r12, [rax+r14*8]
0x18001caba  call    ?mdGetName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetName(ushort)
0x18001cabf  test    rax, rax
0x18001cac2  lea     r15, ?wszZls@@3PAGA; ushort near * wszZls
0x18001cac9  movzx   edx, si; unsigned __int16
0x18001cacc  cmovnz  r15, rax
0x18001cad0  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18001cad5  bt      eax, 0Dh
0x18001cad9  jb      short loc_18001CAF1
0x18001cadb  mov     rcx, rdi; this
0x18001cade  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x18001cae3  mov     ecx, 88h
0x18001cae8  cmp     ax, cx
0x18001caeb  jz      short loc_18001CAF1
0x18001caed  xor     eax, eax
0x18001caef  jmp     short loc_18001CAF6
0x18001caf1  mov     eax, 1
0x18001caf6  mov     edx, [rbx+30h]; unsigned int
0x18001caf9  neg     eax
0x18001cafb  mov     rcx, rbx; this
0x18001cafe  sbb     bpl, bpl
0x18001cb01  add     bpl, 6
0x18001cb05  call    ?Indent@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::Indent(ulong)
0x18001cb0a  test    eax, eax
0x18001cb0c  js      loc_18001CCC9
0x18001cb12  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001cb17  mov     dl, 30h ; '0'; unsigned __int8
0x18001cb19  mov     rcx, rbx; this
0x18001cb1c  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001cb21  test    eax, eax
0x18001cb23  js      loc_18001CCC9
0x18001cb29  mov     dl, 3Fh ; '?'; unsigned __int8
0x18001cb2b  mov     rcx, rbx; this
0x18001cb2e  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001cb33  test    eax, eax
0x18001cb35  js      loc_18001CCC9
0x18001cb3b  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001cb40  mov     dl, bpl; unsigned __int8
0x18001cb43  mov     rcx, rbx; this
0x18001cb46  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001cb4b  test    eax, eax
0x18001cb4d  js      loc_18001CCC9
0x18001cb53  mov     rdx, [rbx+48h]
0x18001cb57  mov     r8, r12; unsigned __int16 *
0x18001cb5a  mov     [rsp+288h+var_260], 0; bool
0x18001cb5f  mov     rcx, rbx; this
0x18001cb62  mov     [rsp+288h+var_268], 0; char
0x18001cb67  mov     rdx, [rdx+30h]; void *
0x18001cb6b  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001cb70  test    eax, eax
0x18001cb72  js      loc_18001CCC9
0x18001cb78  inc     dword ptr [rbx+30h]
0x18001cb7b  mov     rax, [rdi+40h]
0x18001cb7f  cmp     byte ptr [rax+r14*8+8], 0
0x18001cb85  jz      short loc_18001CBAF
0x18001cb87  mov     rdx, [rbx+48h]
0x18001cb8b  mov     r8, r15; unsigned __int16 *
0x18001cb8e  mov     [rsp+288h+var_260], 1; bool
0x18001cb93  mov     rcx, rbx; this
0x18001cb96  mov     [rsp+288h+var_268], 41h ; 'A'; int
0x18001cb9b  mov     rdx, [rdx+6C0h]; void *
0x18001cba2  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001cba7  test    eax, eax
0x18001cba9  js      loc_18001CCC9
0x18001cbaf  movzx   edx, si; unsigned __int16
0x18001cbb2  mov     rcx, rdi; this
0x18001cbb5  call    ?mdGetOrdinal@CMetaData@@QEAAKG@Z; CMetaData::mdGetOrdinal(ushort)
0x18001cbba  mov     edx, eax; unsigned int
0x18001cbbc  lea     r8, [rsp+288h+var_248]; void *
0x18001cbc1  mov     rcx, rbx; this
0x18001cbc4  call    ?_ulto@CPersistStreamInit@@AEBAXKPEAX_KH@Z; CPersistStreamInit::_ulto(ulong,void *,unsigned __int64,int)
0x18001cbc9  mov     rdx, [rbx+48h]
0x18001cbcd  lea     r8, [rsp+288h+var_248]; unsigned __int16 *
0x18001cbd2  mov     [rsp+288h+var_260], 0; bool
0x18001cbd7  mov     rcx, rbx; this
0x18001cbda  mov     [rsp+288h+var_268], 41h ; 'A'; char
0x18001cbdf  mov     rdx, [rdx+690h]; void *
0x18001cbe6  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001cbeb  test    eax, eax
0x18001cbed  js      loc_18001CCC9
0x18001cbf3  movzx   edx, si; unsigned __int16
0x18001cbf6  mov     rcx, rdi; this
0x18001cbf9  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18001cbfe  mov     edx, eax; unsigned int
0x18001cc00  mov     rcx, rbx; this
0x18001cc03  call    ?WriteColumnFlags@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::WriteColumnFlags(ulong)
0x18001cc08  test    eax, eax
0x18001cc0a  js      loc_18001CCC9
0x18001cc10  movzx   r8d, si; unsigned __int16
0x18001cc14  mov     rdx, rdi; struct CRowInfo *
0x18001cc17  mov     rcx, rbx; this
0x18001cc1a  call    ?WriteColumnMetaData@CPersistStreamInit@@AEAAJAEAVCRowInfo@@G@Z; CPersistStreamInit::WriteColumnMetaData(CRowInfo &,ushort)
0x18001cc1f  test    eax, eax
0x18001cc21  js      loc_18001CCC9
0x18001cc27  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001cc2c  mov     dl, 31h ; '1'; unsigned __int8
0x18001cc2e  mov     rcx, rbx; this
0x18001cc31  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001cc36  test    eax, eax
0x18001cc38  js      loc_18001CCC9
0x18001cc3e  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001cc43  mov     dl, 28h ; '('; unsigned __int8
0x18001cc45  mov     rcx, rbx; this
0x18001cc48  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001cc4d  test    eax, eax
0x18001cc4f  js      short loc_18001CCC9
0x18001cc51  movzx   r8d, si; unsigned __int16
0x18001cc55  mov     rdx, rdi; struct CRowInfo *
0x18001cc58  mov     rcx, rbx; this
0x18001cc5b  call    ?WriteColumnTypeInfo@CPersistStreamInit@@AEAAJAEAVCRowInfo@@G@Z; CPersistStreamInit::WriteColumnTypeInfo(CRowInfo &,ushort)
0x18001cc60  test    eax, eax
0x18001cc62  js      short loc_18001CCC9
0x18001cc64  dec     dword ptr [rbx+30h]
0x18001cc67  mov     rcx, rbx; this
0x18001cc6a  mov     edx, [rbx+30h]; unsigned int
0x18001cc6d  call    ?Indent@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::Indent(ulong)
0x18001cc72  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001cc77  mov     dl, 33h ; '3'; unsigned __int8
0x18001cc79  mov     rcx, rbx; this
0x18001cc7c  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001cc81  test    eax, eax
0x18001cc83  js      short loc_18001CCC9
0x18001cc85  mov     dl, 3Fh ; '?'; unsigned __int8
0x18001cc87  mov     rcx, rbx; this
0x18001cc8a  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001cc8f  test    eax, eax
0x18001cc91  js      short loc_18001CCC9
0x18001cc93  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001cc98  mov     dl, bpl; unsigned __int8
0x18001cc9b  mov     rcx, rbx; this
0x18001cc9e  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001cca3  test    eax, eax
0x18001cca5  js      short loc_18001CCC9
0x18001cca7  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001ccac  mov     dl, 31h ; '1'; unsigned __int8
0x18001ccae  mov     rcx, rbx; this
0x18001ccb1  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001ccb6  test    eax, eax
0x18001ccb8  js      short loc_18001CCC9
0x18001ccba  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001ccbf  mov     dl, 28h ; '('; unsigned __int8
0x18001ccc1  mov     rcx, rbx; this
0x18001ccc4  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001ccc9  mov     rcx, [rsp+288h+var_48]
0x18001ccd1  xor     rcx, rsp; StackCookie
0x18001ccd4  call    __security_check_cookie
0x18001ccd9  add     rsp, 250h
0x18001cce0  pop     r15
0x18001cce2  pop     r14
0x18001cce4  pop     r12
0x18001cce6  pop     rdi
0x18001cce7  pop     rsi
0x18001cce8  pop     rbp
0x18001cce9  pop     rbx
0x18001ccea  retn
```
