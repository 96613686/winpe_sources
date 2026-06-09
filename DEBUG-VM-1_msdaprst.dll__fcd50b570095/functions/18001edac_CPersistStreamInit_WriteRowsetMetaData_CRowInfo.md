# CPersistStreamInit::WriteRowsetMetaData(CRowInfo &)

- ea: `0x18001edac`
- end: `0x18001f19c`
- name: `?WriteRowsetMetaData@CPersistStreamInit@@AEAAJAEAVCRowInfo@@@Z`
- size: `1008`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18001e7a4`

## callees

- `0x18000266c`
- `0x18001ac00`
- `0x18001c6a4`
- `0x18001c818`
- `0x18001e348`
- `0x18001edac`
- `0x18001f470`
- `0x18001f7b4`
- `0x180027c4c`
- `0x18002a1b4`
- `0x18002e060`
- `0x180030010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001ef8d`
- `msvcrt!_wcsicmp` at `0x18001ef8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPersistStreamInit::WriteRowsetMetaData(
        CPersistStreamInit *this,
        struct CRowInfo *a2,
        __int64 a3,
        bool a4)
{
  int v6; // ebx
  __int64 i; // rax
  __int64 v8; // r12
  unsigned __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // r14
  __int16 v12; // ax
  int v13; // edx
  bool v14; // r9
  bool v15; // r9
  __int16 v16; // dx
  int *v18; // [rsp+20h] [rbp-E0h]
  unsigned int v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v21; // [rsp+40h] [rbp-C0h]
  int v22; // [rsp+48h] [rbp-B8h]
  unsigned int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24[2]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v25[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v26[256]; // [rsp+70h] [rbp-90h] BYREF

  v6 = 0;
  v19 = 0;
  v25[0] = 0;
  if ( !*((_BYTE *)a2 + 168)
    || (v6 = CPersistStreamInit::WriteAttributeDefinition(
               this,
               *(void **)(*((_QWORD *)this + 9) + 1728LL),
               *((unsigned __int16 **)a2 + 22),
               a4,
               65,
               1),
        v6 >= 0) )
  {
    if ( (***((int (__fastcall ****)(_QWORD, GUID *, _QWORD *))a2 + 13))(*((_QWORD *)a2 + 13), &IID_IRowsetInfo, v25) >= 0 )
    {
      v23 = 0;
      *(_QWORD *)v24 = 0;
      if ( !XMLProps::m_fInitialized )
        XMLProps::_InitProps();
      v18 = v24;
      if ( (*(int (__fastcall **)(_QWORD, __int64, struct tagDBPROPIDSET near **, unsigned int *))(*(_QWORD *)v25[0]
                                                                                                 + 24LL))(
             v25[0],
             2,
             &XMLProps::m_rgPropSets,
             &v23) >= 0 )
      {
        for ( i = 0; ; i = (unsigned int)(v22 + 1) )
        {
          v22 = i;
          if ( (unsigned int)i >= v23 )
            break;
          v8 = 0;
          v9 = (unsigned int)i;
          v21 = (unsigned int)i;
          v10 = 32 * i;
          v20 = v10;
          while ( (unsigned int)v8 < *(_DWORD *)(v10 + *(_QWORD *)v24 + 8) )
          {
            v11 = *(_QWORD *)(v10 + *(_QWORD *)v24);
            if ( *(_DWORD *)(v11 + 72 * v8 + 8) )
              goto LABEL_27;
            v12 = *(_WORD *)(v11 + 72 * v8 + 48);
            if ( v12 != 3 )
            {
              if ( v12 == 8 )
              {
                if ( _wcsicmp(
                       *(const wchar_t **)(v11 + 72 * v8 + 56),
                       &(&XMLProps::m_rgDefaultSets)[v9][3 * v8 + 1]->vt) )
                {
                  v6 = CPersistStreamInit::WriteAttributeDefinition(
                         this,
                         *(void **)(*((_QWORD *)this + 9)
                                  + 16LL * *((unsigned __int8 *)(&XMLProps::m_rgTagSets)[v21] + v8)),
                         *(unsigned __int16 **)(v11 + 72 * v8 + 56),
                         v15,
                         65,
                         1);
                  if ( v6 < 0 )
                  {
LABEL_15:
                    DBPROPSETOBJECT::ClearPropertySet((DBPROPSETOBJECT *)&v23);
                    goto LABEL_39;
                  }
                }
              }
              else
              {
                if ( v12 != 11
                  || *(_DWORD *)(v11 + 72 * v8) == 134 && !*(_WORD *)(v11 + 72LL * (unsigned int)(v8 - 1) + 56) )
                {
                  goto LABEL_26;
                }
                v16 = *(_WORD *)(v11 + 72 * v8 + 56);
                if ( v16 == LOWORD((&XMLProps::m_rgDefaultSets)[v9][3 * v8 + 1]) )
                  goto LABEL_26;
                v6 = CPersistStreamInit::WriteAttributeDefinition(
                       this,
                       *(void **)(*((_QWORD *)this + 9) + 16LL * *((unsigned __int8 *)(&XMLProps::m_rgTagSets)[v9] + v8)),
                       *(unsigned __int16 **)((-(__int64)(v16 != 0) & 0xFFFFFFFFFFFFFFF0uLL)
                                            + *((_QWORD *)this + 9)
                                            + 848),
                       v9,
                       65,
                       0);
                if ( v6 < 0 )
                  goto LABEL_15;
              }
              goto LABEL_25;
            }
            v13 = *(_DWORD *)(v11 + 72 * v8 + 56);
            if ( v13 != LODWORD((&XMLProps::m_rgDefaultSets)[v9][3 * v8 + 1]) )
            {
              CPersistStreamInit::_ito(this, v13, v26, v9, (int)v18);
              v6 = CPersistStreamInit::WriteAttributeDefinition(
                     this,
                     *(void **)(*((_QWORD *)this + 9) + 16LL * *((unsigned __int8 *)(&XMLProps::m_rgTagSets)[v21] + v8)),
                     v26,
                     v14,
                     65,
                     0);
              if ( v6 < 0 )
                goto LABEL_15;
LABEL_25:
              v9 = v21;
            }
LABEL_26:
            v10 = v20;
LABEL_27:
            v8 = (unsigned int)(v8 + 1);
          }
        }
      }
      DBPROPSETOBJECT::ClearPropertySet((DBPROPSETOBJECT *)&v23);
    }
    if ( *((_DWORD *)a2 + 36) )
    {
      v6 = CPersistStreamInit::Write(
             this,
             *(_BYTE **)(*((_QWORD *)this + 9) + 704LL),
             *(unsigned __int8 *)(*((_QWORD *)this + 9) + 712LL),
             &v19,
             1);
      if ( v6 >= 0 )
      {
        v6 = CPersistStreamInit::WriteNamespace(this, 0x41u);
        if ( v6 >= 0 )
        {
          v6 = CPersistStreamInit::WriteTag(this, 0x8Eu, &v19);
          if ( v6 >= 0 )
          {
            v6 = CPersistStreamInit::WriteTag(this, 0x2Bu, &v19);
            if ( v6 >= 0 )
            {
              v6 = CPersistStreamInit::WriteTag(this, 0x29u, &v19);
              if ( v6 >= 0 )
              {
                v6 = CPersistStreamInit::BinaryOut(this, *((unsigned __int8 **)a2 + 19), *((_DWORD *)a2 + 36));
                if ( v6 >= 0 )
                  v6 = CPersistStreamInit::WriteTag(this, 0x29u, &v19);
              }
            }
          }
        }
      }
    }
  }
LABEL_39:
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v25);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001edac  mov     [rsp-8+arg_10], rbx
0x18001edb1  push    rbp
0x18001edb2  push    rsi
0x18001edb3  push    rdi
0x18001edb4  push    r12
0x18001edb6  push    r13
0x18001edb8  push    r14
0x18001edba  push    r15
0x18001edbc  lea     rbp, [rsp-180h]
0x18001edc4  sub     rsp, 280h
0x18001edcb  mov     rax, cs:__security_cookie
0x18001edd2  xor     rax, rsp
0x18001edd5  mov     [rbp+1B0h+var_40], rax
0x18001eddc  mov     r13, rdx
0x18001eddf  mov     rdi, rcx
0x18001ede2  xor     ebx, ebx
0x18001ede4  mov     [rsp+2B0h+var_280], ebx
0x18001ede8  mov     [rsp+2B0h+var_250], rbx
0x18001eded  cmp     [rdx+0A8h], bl
0x18001edf3  jz      short loc_18001EE20
0x18001edf5  mov     rdx, [rcx+48h]
0x18001edf9  mov     [rsp+2B0h+var_288], 1; bool
0x18001edfe  mov     [rsp+2B0h+var_290], 41h ; 'A'; char
0x18001ee03  mov     r8, [r13+0B0h]; unsigned __int16 *
0x18001ee0a  mov     rdx, [rdx+6C0h]; void *
0x18001ee11  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001ee16  mov     ebx, eax
0x18001ee18  test    eax, eax
0x18001ee1a  js      loc_18001F166
0x18001ee20  mov     r9, [r13+68h]
0x18001ee24  mov     rcx, [r9]
0x18001ee27  mov     rax, [rcx]
0x18001ee2a  lea     r8, [rsp+2B0h+var_250]
0x18001ee2f  lea     rdx, IID_IRowsetInfo
0x18001ee36  mov     rcx, r9
0x18001ee39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee3e  test    eax, eax
0x18001ee40  js      loc_18001F0B1
0x18001ee46  mov     [rsp+2B0h+var_260], 0
0x18001ee4e  mov     qword ptr [rsp+2B0h+var_258], 0
0x18001ee57  cmp     cs:?m_fInitialized@XMLProps@@0KA, 0; ulong XMLProps::m_fInitialized
0x18001ee5e  jnz     short loc_18001EE65
0x18001ee60  call    ?_InitProps@XMLProps@@CAXXZ; XMLProps::_InitProps(void)
0x18001ee65  mov     rcx, [rsp+2B0h+var_250]
0x18001ee6a  mov     rax, [rcx]
0x18001ee6d  lea     rdx, [rsp+2B0h+var_258]
0x18001ee72  mov     qword ptr [rsp+2B0h+var_290], rdx; int
0x18001ee77  lea     r9, [rsp+2B0h+var_260]
0x18001ee7c  lea     r8, ?m_rgPropSets@XMLProps@@0PAUtagDBPROPIDSET@@A; tagDBPROPIDSET near * XMLProps::m_rgPropSets
0x18001ee83  mov     edx, 2
0x18001ee88  mov     rax, [rax+18h]
0x18001ee8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee91  test    eax, eax
0x18001ee93  js      loc_18001F0A6
0x18001ee99  xor     eax, eax
0x18001ee9b  lea     r10, cs:180000000h
0x18001eea2  mov     [rsp+2B0h+var_268], eax
0x18001eea6  cmp     eax, [rsp+2B0h+var_260]
0x18001eeaa  jnb     loc_18001F0A6
0x18001eeb0  xor     r12d, r12d
0x18001eeb3  mov     r9d, eax; bool
0x18001eeb6  mov     [rsp+2B0h+var_270], r9
0x18001eebb  shl     rax, 5
0x18001eebf  mov     [rsp+2B0h+var_278], rax
0x18001eec4  mov     r14, qword ptr [rsp+2B0h+var_258]
0x18001eec9  cmp     r12d, [rax+r14+8]
0x18001eece  jnb     loc_18001F08B
0x18001eed4  mov     r14, [rax+r14]
0x18001eed8  lea     r15, [r12+r12*8]
0x18001eedc  cmp     dword ptr [r14+r15*8+8], 0
0x18001eee2  jnz     loc_18001F083
0x18001eee8  movzx   eax, word ptr [r14+r15*8+30h]
0x18001eeee  cmp     ax, 3
0x18001eef2  jnz     short loc_18001EF71
0x18001eef4  mov     edx, [r14+r15*8+38h]; int
0x18001eef9  lea     rcx, [r12+r12*2]
0x18001eefd  mov     rax, rva ?m_rgDefaultSets@XMLProps@@0PAPEAUtagVARIANT@@A[r10+r9*8]; tagVARIANT * near * XMLProps::m_rgDefaultSets ...
0x18001ef05  cmp     edx, [rax+rcx*8+8]
0x18001ef09  jz      loc_18001F07E
0x18001ef0f  lea     r8, [rsp+2B0h+var_240]; void *
0x18001ef14  mov     rcx, rdi; this
0x18001ef17  call    ?_ito@CPersistStreamInit@@AEBAXHPEAX_KH@Z; CPersistStreamInit::_ito(int,void *,unsigned __int64,int)
0x18001ef1c  mov     rax, [rsp+2B0h+var_270]
0x18001ef21  lea     rcx, cs:180000000h
0x18001ef28  mov     rax, rva ?m_rgTagSets@XMLProps@@0PAPEAEA[rcx+rax*8]; uchar * near * XMLProps::m_rgTagSets ...
0x18001ef30  movzx   ecx, byte ptr [rax+r12]
0x18001ef35  add     rcx, rcx
0x18001ef38  mov     rdx, [rdi+48h]
0x18001ef3c  mov     [rsp+2B0h+var_288], 0; bool
0x18001ef41  mov     [rsp+2B0h+var_290], 41h ; 'A'; char
0x18001ef46  lea     r8, [rsp+2B0h+var_240]; unsigned __int16 *
0x18001ef4b  mov     rdx, [rdx+rcx*8]; void *
0x18001ef4f  mov     rcx, rdi; this
0x18001ef52  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001ef57  mov     ebx, eax
0x18001ef59  test    eax, eax
0x18001ef5b  jns     loc_18001F072
0x18001ef61  lea     rcx, [rsp+2B0h+var_260]; this
0x18001ef66  call    ?ClearPropertySet@DBPROPSETOBJECT@@QEAAXXZ; DBPROPSETOBJECT::ClearPropertySet(void)
0x18001ef6b  nop
0x18001ef6c  jmp     loc_18001F166
0x18001ef71  cmp     ax, 8
0x18001ef75  jnz     short loc_18001EFF0
0x18001ef77  lea     rax, [r12+r12*2]
0x18001ef7b  mov     rdx, rva ?m_rgDefaultSets@XMLProps@@0PAPEAUtagVARIANT@@A[r10+r9*8]; tagVARIANT * near * XMLProps::m_rgDefaultSets ...
0x18001ef83  mov     rdx, [rdx+rax*8+8]; String2
0x18001ef88  mov     rcx, [r14+r15*8+38h]; String1
0x18001ef8d  call    cs:__imp__wcsicmp
0x18001ef93  test    eax, eax
0x18001ef95  jz      loc_18001F072
0x18001ef9b  mov     rax, [rsp+2B0h+var_270]
0x18001efa0  lea     rcx, cs:180000000h
0x18001efa7  mov     rax, rva ?m_rgTagSets@XMLProps@@0PAPEAEA[rcx+rax*8]; uchar * near * XMLProps::m_rgTagSets ...
0x18001efaf  movzx   ecx, byte ptr [rax+r12]
0x18001efb4  add     rcx, rcx
0x18001efb7  mov     rdx, [rdi+48h]
0x18001efbb  mov     [rsp+2B0h+var_288], 1; bool
0x18001efc0  mov     [rsp+2B0h+var_290], 41h ; 'A'; char
0x18001efc5  mov     r8, [r14+r15*8+38h]; unsigned __int16 *
0x18001efca  mov     rdx, [rdx+rcx*8]; void *
0x18001efce  mov     rcx, rdi; this
0x18001efd1  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001efd6  mov     ebx, eax
0x18001efd8  test    eax, eax
0x18001efda  jns     loc_18001F072
0x18001efe0  lea     rcx, [rsp+2B0h+var_260]; this
0x18001efe5  call    ?ClearPropertySet@DBPROPSETOBJECT@@QEAAXXZ; DBPROPSETOBJECT::ClearPropertySet(void)
0x18001efea  nop
0x18001efeb  jmp     loc_18001F166
0x18001eff0  cmp     ax, 0Bh
0x18001eff4  jnz     loc_18001F07E
0x18001effa  cmp     dword ptr [r14+r15*8], 86h
0x18001f002  jnz     short loc_18001F017
0x18001f004  lea     eax, [r12-1]
0x18001f009  lea     rdx, [rax+rax*8]
0x18001f00d  xor     eax, eax
0x18001f00f  cmp     ax, [r14+rdx*8+38h]
0x18001f015  jz      short loc_18001F07E
0x18001f017  movzx   edx, word ptr [r14+r15*8+38h]
0x18001f01d  lea     rcx, [r12+r12*2]
0x18001f021  mov     rax, rva ?m_rgDefaultSets@XMLProps@@0PAPEAUtagVARIANT@@A[r10+r9*8]; tagVARIANT * near * XMLProps::m_rgDefaultSets ...
0x18001f029  cmp     dx, [rax+rcx*8+8]
0x18001f02e  jz      short loc_18001F07E
0x18001f030  mov     rcx, [rdi+48h]
0x18001f034  neg     dx
0x18001f037  sbb     r8, r8
0x18001f03a  and     r8, 0FFFFFFFFFFFFFFF0h
0x18001f03e  mov     rax, rva ?m_rgTagSets@XMLProps@@0PAPEAEA[r10+r9*8]; uchar * near * XMLProps::m_rgTagSets ...
0x18001f046  movzx   edx, byte ptr [rax+r12]
0x18001f04b  add     rdx, rdx
0x18001f04e  mov     [rsp+2B0h+var_288], 0; bool
0x18001f053  mov     [rsp+2B0h+var_290], 41h ; 'A'; char
0x18001f058  mov     r8, [r8+rcx+350h]; unsigned __int16 *
0x18001f060  mov     rdx, [rcx+rdx*8]; void *
0x18001f064  mov     rcx, rdi; this
0x18001f067  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001f06c  mov     ebx, eax
0x18001f06e  test    eax, eax
0x18001f070  js      short loc_18001F096
0x18001f072  lea     r10, cs:180000000h
0x18001f079  mov     r9, [rsp+2B0h+var_270]
0x18001f07e  mov     rax, [rsp+2B0h+var_278]
0x18001f083  inc     r12d
0x18001f086  jmp     loc_18001EEC4
0x18001f08b  mov     eax, [rsp+2B0h+var_268]
0x18001f08f  inc     eax
0x18001f091  jmp     loc_18001EEA2
0x18001f096  lea     rcx, [rsp+2B0h+var_260]; this
0x18001f09b  call    ?ClearPropertySet@DBPROPSETOBJECT@@QEAAXXZ; DBPROPSETOBJECT::ClearPropertySet(void)
0x18001f0a0  nop
0x18001f0a1  jmp     loc_18001F166
0x18001f0a6  lea     rcx, [rsp+2B0h+var_260]; this
0x18001f0ab  call    ?ClearPropertySet@DBPROPSETOBJECT@@QEAAXXZ; DBPROPSETOBJECT::ClearPropertySet(void)
0x18001f0b0  nop
0x18001f0b1  cmp     dword ptr [r13+90h], 0
0x18001f0b9  jz      loc_18001F166
0x18001f0bf  mov     rdx, [rdi+48h]
0x18001f0c3  movzx   r8d, byte ptr [rdx+2C8h]; Size
0x18001f0cb  mov     [rsp+2B0h+var_290], 1; bool
0x18001f0d0  lea     r9, [rsp+2B0h+var_280]; unsigned int *
0x18001f0d5  mov     rdx, [rdx+2C0h]; Src
0x18001f0dc  mov     rcx, rdi; this
0x18001f0df  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001f0e4  mov     ebx, eax
0x18001f0e6  test    eax, eax
0x18001f0e8  js      short loc_18001F166
0x18001f0ea  mov     dl, 41h ; 'A'; unsigned __int8
0x18001f0ec  mov     rcx, rdi; this
0x18001f0ef  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001f0f4  mov     ebx, eax
0x18001f0f6  test    eax, eax
0x18001f0f8  js      short loc_18001F166
0x18001f0fa  lea     r8, [rsp+2B0h+var_280]; unsigned int *
0x18001f0ff  mov     dl, 8Eh; unsigned __int8
0x18001f101  mov     rcx, rdi; this
0x18001f104  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f109  mov     ebx, eax
0x18001f10b  test    eax, eax
0x18001f10d  js      short loc_18001F166
0x18001f10f  lea     r8, [rsp+2B0h+var_280]; unsigned int *
0x18001f114  mov     dl, 2Bh ; '+'; unsigned __int8
0x18001f116  mov     rcx, rdi; this
0x18001f119  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f11e  mov     ebx, eax
0x18001f120  test    eax, eax
0x18001f122  js      short loc_18001F166
0x18001f124  lea     r8, [rsp+2B0h+var_280]; unsigned int *
0x18001f129  mov     dl, 29h ; ')'; unsigned __int8
0x18001f12b  mov     rcx, rdi; this
0x18001f12e  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f133  mov     ebx, eax
0x18001f135  test    eax, eax
0x18001f137  js      short loc_18001F166
0x18001f139  mov     r8d, [r13+90h]; unsigned int
0x18001f140  mov     rdx, [r13+98h]; unsigned __int8 *
0x18001f147  mov     rcx, rdi; this
0x18001f14a  call    ?BinaryOut@CPersistStreamInit@@AEAAJPEAEK@Z; CPersistStreamInit::BinaryOut(uchar *,ulong)
0x18001f14f  mov     ebx, eax
0x18001f151  test    eax, eax
0x18001f153  js      short loc_18001F166
0x18001f155  lea     r8, [rsp+2B0h+var_280]; unsigned int *
0x18001f15a  mov     dl, 29h ; ')'; unsigned __int8
0x18001f15c  mov     rcx, rdi; this
0x18001f15f  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f164  mov     ebx, eax
0x18001f166  lea     rcx, [rsp+2B0h+var_250]
0x18001f16b  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18001f170  mov     eax, ebx
0x18001f172  mov     rcx, [rbp+1B0h+var_40]
0x18001f179  xor     rcx, rsp; StackCookie
0x18001f17c  call    __security_check_cookie
0x18001f181  mov     rbx, [rsp+2B0h+arg_10]
0x18001f189  add     rsp, 280h
0x18001f190  pop     r15
0x18001f192  pop     r14
0x18001f194  pop     r13
0x18001f196  pop     r12
0x18001f198  pop     rdi
0x18001f199  pop     rsi
0x18001f19a  pop     rbp
0x18001f19b  retn
```
