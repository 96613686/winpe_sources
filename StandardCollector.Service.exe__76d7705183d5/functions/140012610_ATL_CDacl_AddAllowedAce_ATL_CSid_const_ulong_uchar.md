# ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)

- ea: `0x140012610`
- end: `0x14001270e`
- name: `?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z`
- size: `254`
- prototype: `bool(ATL::CDacl *__hidden this, const struct ATL::CSid *, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140011b04`

## callees

- `0x140002e74`
- `0x1400124d0`
- `0x140012610`
- `0x140012844`
- `0x140013834`
- `0x14001473e`
- `0x140014c70`

## import_xrefs

- `ADVAPI32!IsValidSid` at `0x140012637`
- `ADVAPI32!IsValidSid` at `0x140012637`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1400126dd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1400126dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall ATL::CDacl::AddAllowedAce(ATL::CDacl *this, const struct ATL::CSid *a2)
{
  ATL::CDacl *v3; // rsi
  ATL::CDacl::CAccessAce *v4; // rbx
  unsigned __int64 v5; // r15
  ATL::CDacl::CAccessAce *v7; // [rsp+30h] [rbp-38h]
  void *v11; // [rsp+40h] [rbp-28h]

  v3 = this;
  if ( !*((_BYTE *)a2 + 76) || !IsValidSid((char *)a2 + 8) )
    return 0;
  if ( *((_BYTE *)v3 + 16) )
  {
    (*(void (__fastcall **)(ATL::CDacl *))(*(_QWORD *)v3 + 16LL))(v3);
    *((_BYTE *)v3 + 16) = 0;
  }
  try
  {
    v11 = operator new(0x98u);
    memset_0(v11, 0, 0x98u);
    v4 = ATL::CDacl::CAccessAce::CAccessAce((ATL::CDacl::CAccessAce *)v11, a2);
    v7 = v4;
  }
  catch ( ... )
  {
    v4 = v7;
    v3 = this;
  }
  if ( !v4
    || (v5 = *((_QWORD *)v3 + 4), v5 >= *((_QWORD *)v3 + 5))
    && (_mm_lfence(),
        !(unsigned __int8)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
                            (char *)v3 + 24,
                            v5 + 1)) )
  {
    ATL::AtlThrowImpl(-2147024882);
  }
  *(_QWORD *)(*((_QWORD *)v3 + 3) + 8 * v5) = v4;
  ++*((_QWORD *)v3 + 4);
  free(*((void **)v3 + 1));
  *((_QWORD *)v3 + 1) = 0;
  return 1;
}

```

## disassembly

```asm
0x140012610  mov     [rsp+arg_10], rbx
0x140012615  push    rsi
0x140012616  push    r14
0x140012618  push    r15
0x14001261a  sub     rsp, 50h
0x14001261e  mov     rbx, rdx
0x140012621  mov     rsi, rcx
0x140012624  mov     [rsp+68h+var_30], rcx
0x140012629  cmp     byte ptr [rdx+4Ch], 0
0x14001262d  jz      loc_1400126EF
0x140012633  lea     rcx, [rdx+8]; pSid
0x140012637  call    cs:__imp_IsValidSid
0x14001263d  test    eax, eax
0x14001263f  jz      loc_1400126EF
0x140012645  cmp     byte ptr [rsi+10h], 0
0x140012649  jz      short loc_14001265F
0x14001264b  mov     rax, [rsi]
0x14001264e  mov     rcx, rsi
0x140012651  mov     rax, [rax+10h]
0x140012655  call    cs:__guard_dispatch_icall_fptr
0x14001265b  mov     byte ptr [rsi+10h], 0
0x14001265f  mov     [rsp+68h+var_38], 0
0x140012668  mov     r15d, 98h
0x14001266e  mov     ecx, r15d; Size
0x140012671  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012676  mov     r14, rax
0x140012679  mov     [rsp+68h+var_28], rax
0x14001267e  mov     r8d, r15d; Size
0x140012681  xor     edx, edx; Val
0x140012683  mov     rcx, rax; void *
0x140012686  call    memset_0
0x14001268b  mov     rdx, rbx; struct ATL::CSid *
0x14001268e  mov     rcx, r14; this
0x140012691  call    ??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z; ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)
0x140012696  mov     rbx, rax
0x140012699  mov     [rsp+68h+var_38], rax
0x14001269e  jmp     short loc_1400126AA
0x1400126a0  mov     rbx, [rsp+68h+var_38]
0x1400126a5  mov     rsi, [rsp+68h+var_30]
0x1400126aa  test    rbx, rbx
0x1400126ad  jz      short loc_140012703
0x1400126af  mov     r15, [rsi+20h]
0x1400126b3  cmp     r15, [rsi+28h]
0x1400126b7  jb      short loc_1400126CD
0x1400126b9  lfence
0x1400126bc  lea     rdx, [r15+1]
0x1400126c0  lea     rcx, [rsi+18h]
0x1400126c4  call    ?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)
0x1400126c9  test    al, al
0x1400126cb  jz      short loc_140012703
0x1400126cd  mov     rax, [rsi+18h]
0x1400126d1  mov     [rax+r15*8], rbx
0x1400126d5  inc     qword ptr [rsi+20h]
0x1400126d9  mov     rcx, [rsi+8]; Block
0x1400126dd  call    cs:__imp_free
0x1400126e3  mov     qword ptr [rsi+8], 0
0x1400126eb  mov     al, 1
0x1400126ed  jmp     short loc_1400126F1
0x1400126ef  xor     al, al
0x1400126f1  mov     rbx, [rsp+68h+arg_10]
0x1400126f9  add     rsp, 50h
0x1400126fd  pop     r15
0x1400126ff  pop     r14
0x140012701  pop     rsi
0x140012702  retn
0x140012703  mov     ecx, 8007000Eh; int
0x140012708  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
