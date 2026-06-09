# ESESession::_AddIndex(_INDEXTABLE_ID,char const *)

- ea: `0x18001848c`
- end: `0x180018628`
- name: `?_AddIndex@ESESession@@AEAAJW4_INDEXTABLE_ID@@PEBD@Z`
- size: `412`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800173c4`
- `0x180017f74`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x18000a998`
- `0x180010638`
- `0x1800179c8`
- `0x18001848c`
- `0x18002120a`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18001855d`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18001855d`
- `ESENT!JetCreateIndex2A` at `0x1800185cf`
- `ESENT!JetCreateIndex2A` at `0x1800185cf`

## string_xrefs

- `0x1800184ba`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x1800184d2`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180018602`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::_AddIndex(__int64 a1, int a2, __int64 a3)
{
  __int64 v4; // r14
  __int64 TableDefinitionFromTableId; // r13
  __int64 i; // rdi
  __int64 v8; // r9
  unsigned __int8 *v9; // rax
  __int64 v10; // r8
  int v11; // ecx
  int v12; // edx
  __int64 v13; // r9
  unsigned int HresultFromJetError; // ebx
  __int64 v15; // r9
  JET_SESID v16; // rcx
  JET_ERR v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rcx
  JET_INDEXCREATE_A pindexcreate; // [rsp+30h] [rbp-39h] BYREF
  struct tagJET_UNICODEINDEX v23; // [rsp+D0h] [rbp+67h] BYREF

  v4 = a2;
  if ( *(_DWORD *)(a1 + 24) == -1 )
    Log_AssertionEvent(
      a1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      1335);
  if ( (_DWORD)v4 == -1 )
    Log_AssertionEvent(
      a1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      1336);
  TableDefinitionFromTableId = GetTableDefinitionFromTableId((unsigned int)v4);
  v23 = 0;
  for ( i = 0; (unsigned int)i < *(_DWORD *)(TableDefinitionFromTableId + 40); i = (unsigned int)(i + 1) )
  {
    memset_0(&pindexcreate, 0, sizeof(pindexcreate));
    v8 = *(_QWORD *)(TableDefinitionFromTableId + 32);
    v9 = *(unsigned __int8 **)(v8 + 48 * i + 8);
    v10 = a3 - (_QWORD)v9;
    do
    {
      v11 = v9[v10];
      v12 = *v9 - v11;
      if ( v12 )
        break;
      ++v9;
    }
    while ( v11 );
    if ( !v12 )
    {
      if ( *(_DWORD *)(v8 + 48 * i + 24) == 2048 )
      {
        v23 = g_pimIMIndex_UnicodeIdx;
        pindexcreate.pidxunicode = &v23;
      }
      else
      {
        pindexcreate.lcid = GetSystemDefaultLCID();
      }
      v13 = *(_QWORD *)(TableDefinitionFromTableId + 32);
      pindexcreate.cbStruct = 80;
      pindexcreate.szIndexName = *(char **)(v13 + 48 * i + 8);
      pindexcreate.szKey = *(char **)(v13 + 48 * i + 16);
      HresultFromJetError = ULongLongToULong(*(_QWORD *)(v13 + 48 * i + 32), &pindexcreate.cbKey);
      if ( (HresultFromJetError & 0x80000000) != 0 )
      {
        v18 = 1374;
        v19 = 1;
        v20 = HresultFromJetError;
        goto LABEL_19;
      }
      v16 = *(_QWORD *)(a1 + 56);
      pindexcreate.grbit = *(_DWORD *)(v15 + 48 * i + 24);
      pindexcreate.ulDensity = 80;
      pindexcreate.cConditionalColumn = 0;
      pindexcreate.rgconditionalcolumn = 0;
      v17 = JetCreateIndex2A(v16, *(_QWORD *)(a1 + 48 * v4 + 112), &pindexcreate, 1u);
      if ( v17 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v17);
        v18 = 1386;
        v19 = 0;
        v20 = HresultFromJetError;
LABEL_19:
        Log_HREvent(
          v20,
          v19,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
          v18);
        return HresultFromJetError;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001848c  push    rbp
0x18001848e  push    rbx
0x18001848f  push    rsi
0x180018490  push    rdi
0x180018491  push    r12
0x180018493  push    r13
0x180018495  push    r14
0x180018497  push    r15
0x180018499  lea     rbp, [rsp-1Fh]
0x18001849e  sub     rsp, 88h
0x1800184a5  cmp     dword ptr [rcx+18h], 0FFFFFFFFh
0x1800184a9  mov     r12, r8
0x1800184ac  movsxd  r14, edx
0x1800184af  mov     r15, rcx
0x1800184b2  jnz     short loc_1800184C6
0x1800184b4  mov     r8d, 537h
0x1800184ba  lea     rdx, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800184c1  call    Log_AssertionEvent
0x1800184c6  cmp     r14d, 0FFFFFFFFh
0x1800184ca  jnz     short loc_1800184DE
0x1800184cc  mov     r8d, 538h
0x1800184d2  lea     rdx, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800184d9  call    Log_AssertionEvent
0x1800184de  mov     ecx, r14d
0x1800184e1  call    ?GetTableDefinitionFromTableId@@YAPEBUDatabaseTableDefinition@@W4_INDEXTABLE_ID@@@Z; GetTableDefinitionFromTableId(_INDEXTABLE_ID)
0x1800184e6  mov     r13, rax
0x1800184e9  mov     [rbp+57h+arg_0], 0
0x1800184f1  xor     edi, edi
0x1800184f3  cmp     edi, [r13+28h]
0x1800184f7  jnb     loc_180018612
0x1800184fd  xor     edx, edx; Val
0x1800184ff  lea     rcx, [rbp+57h+pindexcreate]; void *
0x180018503  lea     r8d, [rdx+50h]; Size
0x180018507  call    memset_0
0x18001850c  mov     r9, [r13+20h]
0x180018510  lea     rsi, [rdi+rdi*2]
0x180018514  add     rsi, rsi
0x180018517  mov     r8, r12
0x18001851a  mov     rax, [r9+rsi*8+8]
0x18001851f  sub     r8, rax
0x180018522  movzx   edx, byte ptr [rax]
0x180018525  movzx   ecx, byte ptr [rax+r8]
0x18001852a  sub     edx, ecx
0x18001852c  jnz     short loc_180018535
0x18001852e  inc     rax
0x180018531  test    ecx, ecx
0x180018533  jnz     short loc_180018522
0x180018535  test    edx, edx
0x180018537  jnz     loc_1800185D9
0x18001853d  cmp     dword ptr [r9+rsi*8+18h], 800h
0x180018546  jnz     short loc_18001855D
0x180018548  mov     rax, cs:?g_pimIMIndex_UnicodeIdx@@3UtagJET_UNICODEINDEX@@B; tagJET_UNICODEINDEX const g_pimIMIndex_UnicodeIdx
0x18001854f  mov     [rbp+57h+arg_0], rax
0x180018553  lea     rax, [rbp+57h+arg_0]
0x180018557  mov     qword ptr [rbp+57h+pindexcreate.28h], rax
0x18001855b  jmp     short loc_180018566
0x18001855d  call    cs:__imp_GetSystemDefaultLCID
0x180018563  mov     dword ptr [rbp+57h+pindexcreate.28h], eax
0x180018566  mov     r9, [r13+20h]
0x18001856a  lea     rdx, [rbp+57h+pindexcreate.cbKey]; unsigned int *
0x18001856e  mov     [rbp+57h+pindexcreate.cbStruct], 50h ; 'P'
0x180018575  mov     rax, [r9+rsi*8+8]
0x18001857a  mov     [rbp+57h+pindexcreate.szIndexName], rax
0x18001857e  mov     rax, [r9+rsi*8+10h]
0x180018583  mov     [rbp+57h+pindexcreate.szKey], rax
0x180018587  mov     rcx, [r9+rsi*8+20h]; unsigned __int64
0x18001858c  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180018591  mov     ebx, eax
0x180018593  test    eax, eax
0x180018595  js      short loc_1800185F5
0x180018597  mov     eax, [r9+rsi*8+18h]
0x18001859c  lea     rdx, [r14+r14*2]
0x1800185a0  mov     rcx, [r15+38h]; sesid
0x1800185a4  lea     r8, [rbp+57h+pindexcreate]; pindexcreate
0x1800185a8  add     rdx, rdx
0x1800185ab  mov     [rbp+57h+pindexcreate.grbit], eax
0x1800185ae  mov     r9d, 1; cIndexCreate
0x1800185b4  mov     [rbp+57h+pindexcreate.ulDensity], 50h ; 'P'
0x1800185bb  mov     [rbp+57h+pindexcreate.cConditionalColumn], 0
0x1800185c2  mov     [rbp+57h+pindexcreate.rgconditionalcolumn], 0
0x1800185ca  mov     rdx, [r15+rdx*8+70h]; tableid
0x1800185cf  call    cs:__imp_JetCreateIndex2A
0x1800185d5  test    eax, eax
0x1800185d7  js      short loc_1800185E0
0x1800185d9  inc     edi
0x1800185db  jmp     loc_1800184F3
0x1800185e0  mov     ecx, eax; int
0x1800185e2  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800185e7  mov     ebx, eax
0x1800185e9  mov     r9d, 56Ah
0x1800185ef  xor     edx, edx
0x1800185f1  mov     ecx, eax
0x1800185f3  jmp     short loc_180018602
0x1800185f5  mov     r9d, 55Eh
0x1800185fb  mov     edx, 1
0x180018600  mov     ecx, ebx
0x180018602  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018609  call    Log_HREvent
0x18001860e  mov     eax, ebx
0x180018610  jmp     short loc_180018614
0x180018612  xor     eax, eax
0x180018614  add     rsp, 88h
0x18001861b  pop     r15
0x18001861d  pop     r14
0x18001861f  pop     r13
0x180018621  pop     r12
0x180018623  pop     rdi
0x180018624  pop     rsi
0x180018625  pop     rbx
0x180018626  pop     rbp
0x180018627  retn
```
