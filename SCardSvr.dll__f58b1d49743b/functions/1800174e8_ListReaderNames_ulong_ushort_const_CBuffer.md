# ListReaderNames(ulong,ushort const *,CBuffer &)

- ea: `0x1800174e8`
- end: `0x18001765b`
- name: `?ListReaderNames@@YAXKPEBGAEAVCBuffer@@@Z`
- size: `371`
- prototype: `void __fastcall(__int64, const unsigned __int16 *, struct CBuffer *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180029f78`

## callees

- `0x180009d80`
- `0x18000a2c0`
- `0x18001241c`
- `0x1800174e8`
- `0x180017664`
- `0x18001b814`
- `0x180023168`
- `0x1800320a0`
- `0x1800324dc`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1800175ed`
- `KERNEL32!lstrcmpiW` at `0x1800175ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ListReaderNames(__int64 a1, const unsigned __int16 *a2, struct CBuffer *a3)
{
  const unsigned __int16 *v5; // rcx
  void *v6; // rsi
  const WCHAR *i; // rax
  ulong v8; // ecx
  const unsigned __int16 *v9; // rdi
  const unsigned __int16 *v10; // rdx
  unsigned int *v11; // r9
  void **v12; // [rsp+38h] [rbp-70h] BYREF
  void *Block; // [rsp+40h] [rbp-68h]
  __int64 v14; // [rsp+48h] [rbp-60h]
  _QWORD v15[5]; // [rsp+50h] [rbp-58h] BYREF
  int v16; // [rsp+78h] [rbp-30h]
  LPCWSTR lpString1; // [rsp+C8h] [rbp+20h] BYREF

  v15[2] = &CBuffer::`vftable';
  v15[3] = 0;
  v15[4] = 0;
  v15[0] = 0;
  v16 = 1010;
  v12 = &CBuffer::`vftable';
  Block = 0;
  v14 = 0;
  *((_DWORD *)a3 + 4) = 0;
  ListKnownKeys(a1, (struct CBuffer *)&v12);
  v5 = &Data;
  v6 = Block;
  if ( HIDWORD(v14) )
    v5 = (const unsigned __int16 *)Block;
  for ( i = FirstString(v5); ; i = NextString(v9) )
  {
    v9 = i;
    if ( !i )
      break;
    FindKey(v8, i, (DWORD *)v15);
    lpString1 = 0;
    CRegistry::GetValue((CRegistry *)v15, v10, (unsigned __int16 **)&lpString1, v11);
    if ( !lpString1 )
    {
      v12 = &CBuffer::`vftable';
      if ( v6 )
        operator delete[](v6);
      Block = 0;
      v14 = 0;
      CRegistry::~CRegistry((CRegistry *)v15);
      return;
    }
    if ( !lstrcmpiW(lpString1, a2) )
      MStrAdd(a3, v9);
  }
  if ( v6 )
    operator delete[](v6);
  CRegistry::~CRegistry((CRegistry *)v15);
}

```

## disassembly

```asm
0x1800174e8  mov     rax, rsp
0x1800174eb  mov     [rax+18h], r8
0x1800174ef  mov     [rax+10h], rdx
0x1800174f3  push    rsi
0x1800174f4  push    rdi
0x1800174f5  push    r12
0x1800174f7  push    r14
0x1800174f9  push    r15
0x1800174fb  sub     rsp, 80h
0x180017502  mov     r15, r8
0x180017505  mov     r12, rdx
0x180017508  lea     r14, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18001750f  mov     [rax-48h], r14
0x180017513  mov     qword ptr [rax-40h], 0
0x18001751b  mov     qword ptr [rax-38h], 0
0x180017523  mov     qword ptr [rax-58h], 0
0x18001752b  mov     dword ptr [rax-30h], 3F2h
0x180017532  mov     [rax-70h], r14
0x180017536  mov     qword ptr [rax-68h], 0
0x18001753e  mov     qword ptr [rax-60h], 0
0x180017546  mov     dword ptr [r8+10h], 0
0x18001754e  lea     rdx, [rax-70h]
0x180017552  call    ListKnownKeys
0x180017557  lea     rcx, Data
0x18001755e  mov     rsi, [rsp+0A8h+Block]
0x180017563  cmp     [rsp+0A8h+var_5C], 0
0x180017568  cmova   rcx, rsi; unsigned __int16 *
0x18001756c  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x180017571  mov     rdi, rax
0x180017574  mov     [rsp+0A8h+var_78], rax
0x180017579  test    rax, rax
0x18001757c  jz      loc_180017633
0x180017582  lea     r8, [rsp+0A8h+var_58]
0x180017587  mov     rdx, rax
0x18001758a  call    FindKey
0x18001758f  mov     [rsp+0A8h+lpString1], 0
0x18001759b  lea     r8, [rsp+0A8h+lpString1]; unsigned __int16 **
0x1800175a3  lea     rcx, [rsp+0A8h+var_58]; this
0x1800175a8  call    ?GetValue@CRegistry@@QEAAXPEBGPEAPEAGPEAK@Z; CRegistry::GetValue(ushort const *,ushort * *,ulong *)
0x1800175ad  mov     rcx, [rsp+0A8h+lpString1]; lpString1
0x1800175b5  test    rcx, rcx
0x1800175b8  jnz     short loc_1800175EA
0x1800175ba  mov     [rsp+0A8h+var_70], r14
0x1800175bf  test    rsi, rsi
0x1800175c2  jz      short loc_1800175CC
0x1800175c4  mov     rcx, rsi; Block
0x1800175c7  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800175cc  mov     [rsp+0A8h+Block], 0
0x1800175d5  mov     qword ptr [rsp+48h], 0
0x1800175de  lea     rcx, [rsp+0A8h+var_58]; this
0x1800175e3  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x1800175e8  jmp     short loc_18001764B
0x1800175ea  mov     rdx, r12; lpString2
0x1800175ed  call    cs:__imp_lstrcmpiW
0x1800175f3  test    eax, eax
0x1800175f5  jnz     short loc_180017603
0x1800175f7  mov     rdx, rdi; unsigned __int16 *
0x1800175fa  mov     rcx, r15; this
0x1800175fd  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBG@Z; MStrAdd(CBuffer &,ushort const *)
0x180017602  nop
0x180017603  jmp     short loc_180017626
0x180017605  lea     r14, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18001760c  mov     r15, [rsp+0A8h+arg_10]
0x180017614  mov     r12, [rsp+0A8h+arg_8]
0x18001761c  mov     rdi, [rsp+0A8h+var_78]
0x180017621  mov     rsi, [rsp+0A8h+Block]
0x180017626  mov     rcx, rdi; unsigned __int16 *
0x180017629  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18001762e  jmp     loc_180017571
0x180017633  test    rsi, rsi
0x180017636  jz      short loc_180017641
0x180017638  mov     rcx, rsi; Block
0x18001763b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180017640  nop
0x180017641  lea     rcx, [rsp+0A8h+var_58]; this
0x180017646  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18001764b  add     rsp, 80h
0x180017652  pop     r15
0x180017654  pop     r14
0x180017656  pop     r12
0x180017658  pop     rdi
0x180017659  pop     rsi
0x18001765a  retn
```
