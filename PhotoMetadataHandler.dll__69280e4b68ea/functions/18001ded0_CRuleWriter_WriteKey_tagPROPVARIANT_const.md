# CRuleWriter::WriteKey(tagPROPVARIANT const *)

- ea: `0x18001ded0`
- end: `0x18001df9b`
- name: `?WriteKey@CRuleWriter@@UEAAJPEBUtagPROPVARIANT@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(CRuleWriter *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000fa14`
- `0x18001af5c`
- `0x18001ded0`
- `0x18001ed1c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001df7c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001df7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRuleWriter::WriteKey(const struct CAPABILITIES_LIST_ENTRY **this, struct tagPROPVARIANT *a2)
{
  unsigned int v3; // edx
  int v4; // edi
  int v5; // eax
  unsigned int i; // esi
  unsigned int v7; // esi
  int j; // edi
  PROPVARIANT pvar; // [rsp+20h] [rbp-28h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  v4 = CheckAndConvertWriteInput(this[4], a2, &pvar, 0);
  if ( v4 >= 0 )
  {
    v5 = 0;
    for ( i = 0; i < *((_DWORD *)this + 6); ++i )
      v5 = (*((__int64 (__fastcall **)(const struct CAPABILITIES_LIST_ENTRY **, unsigned __int64, PROPVARIANT *))*this
            + 6))(
             this,
             (unsigned __int64)this[2] + 64 * (unsigned __int64)i,
             &pvar);
    v7 = *((_DWORD *)this + 20);
    if ( v7 )
    {
      if ( *((_DWORD *)this + 16) )
      {
        for ( j = 0; j < v7; ++j )
        {
          if ( j < 0 || j >= *((_DWORD *)this + 20) )
          {
            ATL::_AtlRaiseException(0xC000008C, v3);
            __debugbreak();
          }
          CRuleWriter::RemovePathAndHandleChecksum((CRuleWriter *)this, *((const struct RULE_PATH_INFO **)this[9] + j));
        }
        v4 = 0;
      }
      else
      {
        v4 = v5;
      }
    }
  }
  PropVariantClear(&pvar);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001ded0  mov     r11, rsp
0x18001ded3  mov     [r11+8], rbx
0x18001ded7  mov     [r11+10h], rsi
0x18001dedb  push    rdi
0x18001dedc  sub     rsp, 40h
0x18001dee0  mov     rbx, rcx
0x18001dee3  xorps   xmm0, xmm0
0x18001dee6  xor     eax, eax
0x18001dee8  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x18001deed  mov     [r11-18h], rax
0x18001def1  xor     r9d, r9d; bool *
0x18001def4  lea     r8, [r11-28h]; struct tagPROPVARIANT *
0x18001def8  mov     rcx, [rcx+20h]; struct CAPABILITIES_LIST_ENTRY *
0x18001defc  call    ?CheckAndConvertWriteInput@@YAJPEBUCAPABILITIES_LIST_ENTRY@@PEBUtagPROPVARIANT@@PEAU2@PEA_N@Z; CheckAndConvertWriteInput(CAPABILITIES_LIST_ENTRY const *,tagPROPVARIANT const *,tagPROPVARIANT *,bool *)
0x18001df01  mov     edi, eax
0x18001df03  test    eax, eax
0x18001df05  js      short loc_18001DF77
0x18001df07  xor     eax, eax
0x18001df09  xor     esi, esi
0x18001df0b  cmp     [rbx+18h], eax
0x18001df0e  jbe     short loc_18001DF35
0x18001df10  mov     rax, [rbx]
0x18001df13  mov     edx, esi
0x18001df15  shl     rdx, 6
0x18001df19  add     rdx, [rbx+10h]
0x18001df1d  lea     r8, [rsp+48h+pvar]
0x18001df22  mov     rcx, rbx
0x18001df25  mov     rax, [rax+30h]
0x18001df29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df2e  inc     esi
0x18001df30  cmp     esi, [rbx+18h]
0x18001df33  jb      short loc_18001DF10
0x18001df35  mov     esi, [rbx+50h]
0x18001df38  test    esi, esi
0x18001df3a  jz      short loc_18001DF77
0x18001df3c  cmp     dword ptr [rbx+40h], 0
0x18001df40  jbe     short loc_18001DF75
0x18001df42  xor     edi, edi
0x18001df44  test    edi, edi
0x18001df46  js      short loc_18001DF6A
0x18001df48  cmp     edi, [rbx+50h]
0x18001df4b  jge     short loc_18001DF6A
0x18001df4d  movsxd  rax, edi
0x18001df50  mov     rdx, [rbx+48h]
0x18001df54  mov     rdx, [rdx+rax*8]; struct RULE_PATH_INFO *
0x18001df58  mov     rcx, rbx; this
0x18001df5b  call    ?RemovePathAndHandleChecksum@CRuleWriter@@IEAAJPEBURULE_PATH_INFO@@@Z; CRuleWriter::RemovePathAndHandleChecksum(RULE_PATH_INFO const *)
0x18001df60  inc     edi
0x18001df62  cmp     edi, esi
0x18001df64  jb      short loc_18001DF44
0x18001df66  xor     edi, edi
0x18001df68  jmp     short loc_18001DF77
0x18001df6a  mov     ecx, 0C000008Ch; unsigned int
0x18001df6f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18001df74  int     3; Trap to Debugger
0x18001df75  mov     edi, eax
0x18001df77  lea     rcx, [rsp+48h+pvar]; pvar
0x18001df7c  call    cs:__imp_PropVariantClear
0x18001df83  nop     dword ptr [rax+rax+00h]
0x18001df88  mov     eax, edi
0x18001df8a  mov     rbx, [rsp+48h+arg_0]
0x18001df8f  mov     rsi, [rsp+48h+arg_8]
0x18001df94  add     rsp, 40h
0x18001df98  pop     rdi
0x18001df99  retn
```
