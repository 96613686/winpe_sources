# Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800085cc`
- end: `0x1800086ed`
- name: `?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z`
- size: `289`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800050e0`
- `0x180005480`
- `0x180005ed0`
- `0x180006270`
- `0x180006ac0`
- `0x1800071e0`
- `0x180007650`
- `0x1800082f0`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800085cc`
- `0x18000901c`

## import_xrefs

- `bcrypt!BCryptHash` at `0x18000868e`
- `bcrypt!BCryptHash` at `0x18000868e`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::HmacData(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  char *v8; // rcx
  int v9; // r8d
  int v10; // esi
  void *v11; // rcx
  void *v12; // rbp
  int v13; // eax
  int v14; // r8d
  int v15; // r14d
  __int64 v17; // [rsp+40h] [rbp-58h] BYREF
  void *v18; // [rsp+48h] [rbp-50h]
  char *v19; // [rsp+50h] [rbp-48h]

  if ( *(_QWORD *)a4 > 0xFFFFFFFF )
  {
    v8 = "static_cast<size_t>(data.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())";
LABEL_3:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v8, (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
    return a2;
  }
  if ( *a3 > 0xFFFFFFFF )
  {
    v8 = "static_cast<size_t>(key.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())";
    goto LABEL_3;
  }
  Kerb3961::MakeBuffer(&v17);
  v10 = (int)v19;
  if ( (int)v19 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"result", (const char *)(unsigned int)v19, v9);
    v11 = v18;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v10;
    if ( !v11 )
      return a2;
LABEL_12:
    operator delete(v11, 0);
    return a2;
  }
  v12 = v18;
  v13 = BCryptHash(*(_QWORD *)(a1 + 96), a3[1], *(unsigned int *)a3, *(_QWORD *)(a4 + 8), *(_DWORD *)a4, v18, 16);
  v15 = v13;
  if ( v13 >= 0 )
  {
    *(_QWORD *)a2 = v17;
    *(_DWORD *)(a2 + 16) = v10;
    *(_QWORD *)(a2 + 8) = v12;
    return a2;
  }
  Kerb3961::Logging::Verify::StatusFailed(
    (Kerb3961::Logging::Verify *)"BCryptHash(m_checksumHandle, const_cast<uint8_t*>(key.buffer), static_cast<uint32_t>(ke"
                                 "y.length), const_cast<uint8_t*>(data.buffer), static_cast<uint32_t>(data.length), resul"
                                 "t.buffer, HASH_SIZE)",
    (const char *)(unsigned int)v13,
    v14);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v15;
  if ( v12 )
  {
    v11 = v12;
    goto LABEL_12;
  }
  return a2;
}

```

## disassembly

```asm
0x1800085cc  push    rbx
0x1800085ce  push    rbp
0x1800085cf  push    rsi
0x1800085d0  push    r13
0x1800085d2  push    r14
0x1800085d4  push    r15
0x1800085d6  sub     rsp, 68h
0x1800085da  mov     eax, 0FFFFFFFFh
0x1800085df  mov     r15, r9
0x1800085e2  mov     r14, r8
0x1800085e5  mov     rbx, rdx
0x1800085e8  mov     r13, rcx
0x1800085eb  cmp     [r9], rax
0x1800085ee  jbe     short loc_180008617
0x1800085f0  lea     rcx, aStaticCastSize_6; "static_cast<size_t>(data.length) <= sta"...
0x1800085f7  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800085fc  mov     qword ptr [rbx], 0
0x180008603  mov     qword ptr [rbx+8], 0
0x18000860b  mov     dword ptr [rbx+10h], 0C0000095h
0x180008612  jmp     loc_1800086DC
0x180008617  cmp     [r8], rax
0x18000861a  jbe     short loc_180008625
0x18000861c  lea     rcx, aStaticCastSize_2; "static_cast<size_t>(key.length) <= stat"...
0x180008623  jmp     short loc_1800085F7
0x180008625  mov     ebp, 10h
0x18000862a  lea     rcx, [rsp+98h+var_58]
0x18000862f  mov     edx, ebp
0x180008631  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180008636  mov     esi, dword ptr [rsp+98h+var_48]
0x18000863a  test    esi, esi
0x18000863c  jns     short loc_18000866A
0x18000863e  mov     edx, esi; char *
0x180008640  lea     rcx, aResult; "result"
0x180008647  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000864c  mov     rcx, [rsp+98h+var_50]
0x180008651  mov     qword ptr [rbx], 0
0x180008658  mov     qword ptr [rbx+8], 0
0x180008660  mov     [rbx+10h], esi
0x180008663  test    rcx, rcx
0x180008666  jz      short loc_1800086DC
0x180008668  jmp     short loc_1800086C4
0x18000866a  mov     eax, [r15]
0x18000866d  mov     r9, [r15+8]
0x180008671  mov     r8d, [r14]
0x180008674  mov     rdx, [r14+8]
0x180008678  mov     rcx, [r13+60h]
0x18000867c  mov     [rsp+98h+var_68], ebp
0x180008680  mov     rbp, [rsp+98h+var_50]
0x180008685  mov     [rsp+98h+var_70], rbp
0x18000868a  mov     [rsp+98h+var_78], eax
0x18000868e  call    cs:__imp_BCryptHash
0x180008694  mov     r14d, eax
0x180008697  test    eax, eax
0x180008699  jns     short loc_1800086CD
0x18000869b  mov     edx, eax; char *
0x18000869d  lea     rcx, aBcrypthashMChe; "BCryptHash(m_checksumHandle, const_cast"...
0x1800086a4  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800086a9  mov     qword ptr [rbx], 0
0x1800086b0  mov     qword ptr [rbx+8], 0
0x1800086b8  mov     [rbx+10h], r14d
0x1800086bc  test    rbp, rbp
0x1800086bf  jz      short loc_1800086DC
0x1800086c1  mov     rcx, rbp; void *
0x1800086c4  xor     edx, edx; struct std::nothrow_t *
0x1800086c6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800086cb  jmp     short loc_1800086DC
0x1800086cd  mov     rax, [rsp+98h+var_58]
0x1800086d2  mov     [rbx], rax
0x1800086d5  mov     [rbx+10h], esi
0x1800086d8  mov     [rbx+8], rbp
0x1800086dc  mov     rax, rbx
0x1800086df  add     rsp, 68h
0x1800086e3  pop     r15
0x1800086e5  pop     r14
0x1800086e7  pop     r13
0x1800086e9  pop     rsi
0x1800086ea  pop     rbp
0x1800086eb  pop     rbx
0x1800086ec  retn
```
