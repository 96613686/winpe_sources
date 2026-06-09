# CoreKnowledge::AddOrReplaceRangeSetIndexForColumn(SyncId const &,ulong &)

- ea: `0x18008c0c8`
- end: `0x18008c256`
- name: `?AddOrReplaceRangeSetIndexForColumn@CoreKnowledge@@AEAAJAEBVSyncId@@AEAK@Z`
- size: `398`
- prototype: `__int64 __fastcall(CoreKnowledge *this, const struct SyncId *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18008c67c`

## callees

- `0x18000c270`
- `0x180011f60`
- `0x18001a038`
- `0x18001a1f0`
- `0x18001ae20`
- `0x18008bffc`
- `0x18008c0c8`

## string_xrefs

- `0x18008c105`: `CoreKnowledge::AddOrReplaceRangeSetIndexForColumn`
- `0x18008c227`: `CoreKnowledge::AddOrReplaceRangeSetIndexForColumn`

## pseudocode

```c
__int64 __fastcall CoreKnowledge::AddOrReplaceRangeSetIndexForColumn(
        CoreKnowledge *this,
        const struct SyncId *a2,
        unsigned int *a3)
{
  __int64 v6; // rbp
  int v7; // ebx
  unsigned int v8; // edi
  const struct SyncId *v9; // r14
  int v10; // eax
  unsigned int v11; // esi
  int v12; // r14d
  __int64 v13; // r14
  __int64 v14; // rdx
  __int64 v15; // rdi
  __int64 v16; // rbx
  _BYTE v18[4]; // [rsp+30h] [rbp-68h] BYREF
  int v19; // [rsp+34h] [rbp-64h]
  __int64 v20; // [rsp+38h] [rbp-60h]
  int v21; // [rsp+40h] [rbp-58h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      WPP_02a3190e7da53667064fc8f16087bf64_Traceguids,
      "CoreKnowledge::AddOrReplaceRangeSetIndexForColumn");
  }
  v6 = 0;
  v7 = *((_DWORD *)this + 8) - 1;
  while ( v7 >= (int)v6 )
  {
    v8 = (v7 + (int)v6) / 2;
    v9 = (const struct SyncId *)(*((_QWORD *)this + 6) + 24LL * v8);
    v10 = SyncId::Compare(a2, v9);
    if ( v10 <= 0 )
    {
      if ( v10 >= 0 )
      {
        v11 = 0;
        *((_DWORD *)v9 + 4) = *a3;
        goto LABEL_17;
      }
      v7 = v8 - 1;
    }
    else
    {
      v6 = v8 + 1;
    }
  }
  v12 = *((_DWORD *)this + 8);
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v11 = Vector<ColumnEntry,1>::Add((char *)this + 32, v18);
  SyncId::~SyncId((SyncId *)v18);
  if ( !v11 )
  {
    v13 = (unsigned int)(v12 - 1);
    while ( (int)v13 >= (int)v6 )
    {
      v14 = *((_QWORD *)this + 6);
      v15 = v14 + 24 * v13;
      v16 = v14 + 24LL * (unsigned int)(v13 + 1);
      SyncId::operator=(v16, v15);
      v13 = (unsigned int)(v13 - 1);
      *(_DWORD *)(v16 + 16) = *(_DWORD *)(v15 + 16);
    }
    SyncId::operator=(*((_QWORD *)this + 6) + 24 * v6, (__int64)a2);
    *(_DWORD *)(*((_QWORD *)this + 6) + 24 * v6 + 16) = *a3;
  }
LABEL_17:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      (unsigned int)WPP_02a3190e7da53667064fc8f16087bf64_Traceguids,
      (unsigned int)"CoreKnowledge::AddOrReplaceRangeSetIndexForColumn",
      v11);
  }
  return v11;
}

```

## disassembly

```asm
0x18008c0c8  push    rbx
0x18008c0ca  push    rbp
0x18008c0cb  push    rsi
0x18008c0cc  push    rdi
0x18008c0cd  push    r12
0x18008c0cf  push    r13
0x18008c0d1  push    r14
0x18008c0d3  push    r15
0x18008c0d5  sub     rsp, 58h
0x18008c0d9  mov     r12, r8
0x18008c0dc  mov     r13, rdx
0x18008c0df  mov     r15, rcx
0x18008c0e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c0e9  lea     rax, WPP_GLOBAL_Control
0x18008c0f0  cmp     rcx, rax
0x18008c0f3  jz      short loc_18008C11D
0x18008c0f5  test    byte ptr [rcx+1Ch], 40h
0x18008c0f9  jz      short loc_18008C11D
0x18008c0fb  cmp     byte ptr [rcx+19h], 5
0x18008c0ff  jb      short loc_18008C11D
0x18008c101  mov     rcx, [rcx+10h]
0x18008c105  lea     r9, aCoreknowledgeA; "CoreKnowledge::AddOrReplaceRangeSetInde"...
0x18008c10c  mov     edx, 32h ; '2'
0x18008c111  lea     r8, WPP_02a3190e7da53667064fc8f16087bf64_Traceguids
0x18008c118  call    WPP_SF_s
0x18008c11d  lea     rsi, [r15+20h]
0x18008c121  xor     ebp, ebp
0x18008c123  mov     ebx, [rsi]
0x18008c125  dec     ebx
0x18008c127  cmp     ebx, ebp
0x18008c129  jl      short loc_18008C16E
0x18008c12b  lea     eax, [rbx+rbp]
0x18008c12e  mov     ecx, 2
0x18008c133  cdq
0x18008c134  idiv    ecx
0x18008c136  mov     edi, eax
0x18008c138  lea     rcx, [rax+rax*2]
0x18008c13c  mov     rax, [r15+30h]
0x18008c140  lea     r14, [rax+rcx*8]
0x18008c144  mov     rcx, r13; struct SyncId *
0x18008c147  mov     rdx, r14; struct SyncId *
0x18008c14a  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18008c14f  test    eax, eax
0x18008c151  jle     short loc_18008C158
0x18008c153  lea     ebp, [rdi+1]
0x18008c156  jmp     short loc_18008C127
0x18008c158  jns     short loc_18008C15F
0x18008c15a  lea     ebx, [rdi-1]
0x18008c15d  jmp     short loc_18008C127
0x18008c15f  mov     eax, [r12]
0x18008c163  xor     esi, esi
0x18008c165  mov     [r14+10h], eax
0x18008c169  jmp     loc_18008C204
0x18008c16e  mov     r14d, [rsi]
0x18008c171  lea     rdx, [rsp+98h+var_68]
0x18008c176  mov     rcx, rsi
0x18008c179  mov     [rsp+98h+var_64], 0
0x18008c181  mov     [rsp+98h+var_60], 0
0x18008c18a  mov     [rsp+98h+var_58], 0
0x18008c192  call    ?Add@?$Vector@UColumnEntry@@$00@@QEAAJAEBUColumnEntry@@@Z; Vector<ColumnEntry,1>::Add(ColumnEntry const &)
0x18008c197  lea     rcx, [rsp+98h+var_68]; this
0x18008c19c  mov     esi, eax
0x18008c19e  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18008c1a3  test    esi, esi
0x18008c1a5  jnz     short loc_18008C204
0x18008c1a7  dec     r14d
0x18008c1aa  jmp     short loc_18008C1D8
0x18008c1ac  mov     rdx, [r15+30h]
0x18008c1b0  lea     rcx, [r14+r14*2]
0x18008c1b4  lea     eax, [r14+1]
0x18008c1b8  lea     rax, [rax+rax*2]
0x18008c1bc  lea     rdi, [rdx+rcx*8]
0x18008c1c0  lea     rbx, [rdx+rax*8]
0x18008c1c4  mov     rdx, rdi
0x18008c1c7  mov     rcx, rbx
0x18008c1ca  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18008c1cf  mov     eax, [rdi+10h]
0x18008c1d2  dec     r14d
0x18008c1d5  mov     [rbx+10h], eax
0x18008c1d8  cmp     r14d, ebp
0x18008c1db  jge     short loc_18008C1AC
0x18008c1dd  mov     rax, [r15+30h]
0x18008c1e1  lea     rbx, ds:0[rbp*2]
0x18008c1e9  add     rbx, rbp
0x18008c1ec  mov     rdx, r13
0x18008c1ef  lea     rcx, [rax+rbx*8]
0x18008c1f3  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18008c1f8  mov     rcx, [r15+30h]
0x18008c1fc  mov     eax, [r12]
0x18008c200  mov     [rcx+rbx*8+10h], eax
0x18008c204  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c20b  lea     rax, WPP_GLOBAL_Control
0x18008c212  cmp     rcx, rax
0x18008c215  jz      short loc_18008C243
0x18008c217  test    byte ptr [rcx+1Ch], 40h
0x18008c21b  jz      short loc_18008C243
0x18008c21d  cmp     byte ptr [rcx+19h], 5
0x18008c221  jb      short loc_18008C243
0x18008c223  mov     rcx, [rcx+10h]
0x18008c227  lea     r9, aCoreknowledgeA; "CoreKnowledge::AddOrReplaceRangeSetInde"...
0x18008c22e  mov     edx, 33h ; '3'
0x18008c233  mov     [rsp+98h+var_78], esi
0x18008c237  lea     r8, WPP_02a3190e7da53667064fc8f16087bf64_Traceguids
0x18008c23e  call    WPP_SF_sD
0x18008c243  mov     eax, esi
0x18008c245  add     rsp, 58h
0x18008c249  pop     r15
0x18008c24b  pop     r14
0x18008c24d  pop     r13
0x18008c24f  pop     r12
0x18008c251  pop     rdi
0x18008c252  pop     rsi
0x18008c253  pop     rbp
0x18008c254  pop     rbx
0x18008c255  retn
```
