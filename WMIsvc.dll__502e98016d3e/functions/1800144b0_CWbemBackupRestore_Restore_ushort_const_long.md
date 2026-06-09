# CWbemBackupRestore::Restore(ushort const *,long)

- ea: `0x1800144b0`
- end: `0x1800148dd`
- name: `?Restore@CWbemBackupRestore@@UEAAJPEBGJ@Z`
- size: `1069`
- prototype: `__int64 __fastcall(CWbemBackupRestore *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ae04`
- `0x18000dcdc`
- `0x180010710`
- `0x180010740`
- `0x1800144b0`

## import_xrefs

- `wbemcomn!??0CInsertionString@@QEAA@J@Z` at `0x180014837`
- `wbemcomn!??0CInsertionString@@QEAA@J@Z` at `0x180014837`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x1800148b7`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x1800148b7`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x18001463b`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x1800148a3`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x18001463b`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x1800148a3`
- `wbemcomn!?Open@CEventLog@@QEAAHXZ` at `0x180014519`
- `wbemcomn!?Open@CEventLog@@QEAAHXZ` at `0x180014519`
- `wbemcomn!??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z` at `0x180014502`
- `wbemcomn!??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z` at `0x180014502`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800144de`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800144de`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
__int64 __fastcall CWbemBackupRestore::Restore(CWbemBackupRestore *this, const unsigned __int16 *a2, int a3)
{
  CEventLog *v3; // rax
  CInsertionString *v4; // r13
  CInsertionString *v5; // r12
  CInsertionString *v6; // r15
  CInsertionString *v7; // r14
  CInsertionString *v8; // rsi
  CInsertionString *v9; // rdi
  CInsertionString *v10; // rbx
  CInsertionString *v11; // rax
  CEventLog *v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  CInsertionString *v15; // r13
  CInsertionString *v16; // r12
  CInsertionString *v17; // r15
  CInsertionString *v18; // r14
  CInsertionString *v19; // rsi
  CInsertionString *v20; // rdi
  CInsertionString *v21; // rbx
  CInsertionString *v22; // rax
  CInsertionString *v23; // r13
  CInsertionString *v24; // r12
  CInsertionString *v25; // r15
  CInsertionString *v26; // r14
  CInsertionString *v27; // rsi
  CInsertionString *v28; // rdi
  CInsertionString *v29; // rbx
  CInsertionString *v30; // rax
  unsigned int v31; // edx
  CInsertionString *v33; // [rsp+28h] [rbp-E0h]
  int v34[2]; // [rsp+78h] [rbp-90h] BYREF
  CEventLog *v35; // [rsp+80h] [rbp-88h]
  CInsertionString *v36; // [rsp+88h] [rbp-80h]
  _BYTE *v37; // [rsp+90h] [rbp-78h]
  _BYTE *v38; // [rsp+98h] [rbp-70h]
  _BYTE *v39; // [rsp+A0h] [rbp-68h]
  _BYTE *v40; // [rsp+A8h] [rbp-60h]
  _BYTE *v41; // [rsp+B0h] [rbp-58h]
  _BYTE *v42; // [rsp+B8h] [rbp-50h]
  _BYTE *v43; // [rsp+C0h] [rbp-48h]
  _BYTE *v44; // [rsp+C8h] [rbp-40h]
  _BYTE *v45; // [rsp+D0h] [rbp-38h]
  _BYTE v46[16]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v47[16]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v48[16]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v49[16]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v50[16]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v51[16]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v52[16]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v53[16]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v54[16]; // [rsp+158h] [rbp+50h] BYREF
  _QWORD v55[2]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v56[80]; // [rsp+178h] [rbp+70h] BYREF
  CInsertionString *v60; // [rsp+1F0h] [rbp+E8h]
  int v61; // [rsp+1F0h] [rbp+E8h]

  v3 = (CEventLog *)CWin32DefaultArena::WbemMemAlloc(0x58u);
  if ( v3 )
    v3 = CEventLog::CEventLog(v3, 0, (const struct _GUID *)S_WinMgmtR, 0xAu);
  v35 = v3;
  if ( v3 )
  {
    CEventLog::Open(v3);
    v36 = (CInsertionString *)v55;
    v60 = CInsertionString::CInsertionString((CInsertionString *)v55);
    v37 = v46;
    *(_QWORD *)v34 = CInsertionString::CInsertionString((CInsertionString *)v46);
    v38 = v47;
    v4 = CInsertionString::CInsertionString((CInsertionString *)v47);
    v39 = v48;
    v5 = CInsertionString::CInsertionString((CInsertionString *)v48);
    v40 = v49;
    v6 = CInsertionString::CInsertionString((CInsertionString *)v49);
    v41 = v50;
    v7 = CInsertionString::CInsertionString((CInsertionString *)v50);
    v42 = v51;
    v8 = CInsertionString::CInsertionString((CInsertionString *)v51);
    v43 = v52;
    v9 = CInsertionString::CInsertionString((CInsertionString *)v52);
    v44 = v53;
    v10 = CInsertionString::CInsertionString((CInsertionString *)v53);
    v45 = v54;
    v11 = CInsertionString::CInsertionString((CInsertionString *)v54);
    v33 = v10;
    v12 = v35;
    CEventLog::Report(
      v35,
      2,
      WBEM_MC_WBEM_REPOSITORY_STARTING_RECOVERY,
      v11,
      v33,
      v9,
      v8,
      v7,
      v6,
      v5,
      v4,
      *(_QWORD *)v34,
      v60);
  }
  else
  {
    v12 = 0;
  }
  v34[0] = 0;
  v13 = CWbemBackupRestore::RestoreHelper(this, a2, a3, v34);
  v14 = v13;
  v61 = v13;
  if ( v12 )
  {
    if ( !v34[0] )
    {
      if ( v13 < 0 )
      {
        v55[0] = v56;
        v36 = CInsertionString::CInsertionString((CInsertionString *)v56);
        v45 = v54;
        *(_QWORD *)v34 = CInsertionString::CInsertionString((CInsertionString *)v54);
        v44 = v53;
        v23 = CInsertionString::CInsertionString((CInsertionString *)v53);
        v43 = v52;
        v24 = CInsertionString::CInsertionString((CInsertionString *)v52);
        v42 = v51;
        v25 = CInsertionString::CInsertionString((CInsertionString *)v51);
        v41 = v50;
        v26 = CInsertionString::CInsertionString((CInsertionString *)v50);
        v40 = v49;
        v27 = CInsertionString::CInsertionString((CInsertionString *)v49);
        v39 = v48;
        v28 = CInsertionString::CInsertionString((CInsertionString *)v48);
        v38 = v47;
        v29 = CInsertionString::CInsertionString((CInsertionString *)v47, v61);
        v37 = v46;
        v30 = CInsertionString::CInsertionString((CInsertionString *)v46, a2);
        CEventLog::Report(
          v35,
          1,
          WBEM_MC_WBEM_REPOSITORY_BACKUP_RESTORE_FAILURE,
          v30,
          v29,
          v28,
          v27,
          v26,
          v25,
          v24,
          v23,
          *(_QWORD *)v34,
          v36);
      }
      else
      {
        v45 = v54;
        *(_QWORD *)v34 = CInsertionString::CInsertionString((CInsertionString *)v54);
        v44 = v53;
        v36 = CInsertionString::CInsertionString((CInsertionString *)v53);
        v43 = v52;
        v15 = CInsertionString::CInsertionString((CInsertionString *)v52);
        v42 = v51;
        v16 = CInsertionString::CInsertionString((CInsertionString *)v51);
        v41 = v50;
        v17 = CInsertionString::CInsertionString((CInsertionString *)v50);
        v40 = v49;
        v18 = CInsertionString::CInsertionString((CInsertionString *)v49);
        v39 = v48;
        v19 = CInsertionString::CInsertionString((CInsertionString *)v48);
        v38 = v47;
        v20 = CInsertionString::CInsertionString((CInsertionString *)v47);
        v37 = v46;
        v21 = CInsertionString::CInsertionString((CInsertionString *)v46);
        v55[0] = v56;
        v22 = CInsertionString::CInsertionString((CInsertionString *)v56, a2);
        CEventLog::Report(
          v35,
          2,
          WBEM_MC_WBEM_REPOSITORY_BACKUP_RESTORED,
          v22,
          v21,
          v20,
          v19,
          v18,
          v17,
          v16,
          v15,
          v36,
          *(_QWORD *)v34);
      }
      v14 = v61;
      v12 = v35;
    }
    CEventLog::Close(v12);
    CEventLog::`scalar deleting destructor'(v35, v31);
  }
  return v14;
}

```

## disassembly

```asm
0x1800144b0  mov     rax, rsp
0x1800144b3  mov     [rax+18h], r8d
0x1800144b7  mov     [rax+10h], rdx
0x1800144bb  mov     [rax+8], rcx
0x1800144bf  push    rbp
0x1800144c0  push    rbx
0x1800144c1  push    rsi
0x1800144c2  push    rdi
0x1800144c3  push    r12
0x1800144c5  push    r13
0x1800144c7  push    r14
0x1800144c9  push    r15
0x1800144cb  lea     rbp, [rax-0C8h]
0x1800144d2  sub     rsp, 188h
0x1800144d9  mov     ecx, 58h ; 'X'
0x1800144de  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800144e4  mov     [rbp+0C0h+arg_18], rax
0x1800144eb  test    rax, rax
0x1800144ee  jz      short loc_180014508
0x1800144f0  mov     r9d, 0Ah
0x1800144f6  lea     r8, S_WinMgmtR
0x1800144fd  xor     edx, edx
0x1800144ff  mov     rcx, rax
0x180014502  call    cs:__imp_??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z; CEventLog::CEventLog(ushort const *,_GUID const &,ulong)
0x180014508  mov     [rsp+1C0h+var_148], rax
0x18001450d  test    rax, rax
0x180014510  jz      loc_180014643
0x180014516  mov     rcx, rax
0x180014519  call    cs:__imp_?Open@CEventLog@@QEAAHXZ; CEventLog::Open(void)
0x18001451f  lea     rax, [rbp+0C0h+var_60]
0x180014523  mov     [rbp+0C0h+var_140], rax
0x180014527  lea     rcx, [rbp+0C0h+var_60]; this
0x18001452b  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180014530  mov     [rbp+0C0h+arg_18], rax
0x180014537  lea     rax, [rbp+0C0h+var_F0]
0x18001453b  mov     [rbp+0C0h+var_138], rax
0x18001453f  lea     rcx, [rbp+0C0h+var_F0]; this
0x180014543  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180014548  mov     qword ptr [rsp+1C0h+var_150], rax
0x18001454d  lea     rax, [rbp+0C0h+var_E0]
0x180014551  mov     [rbp+0C0h+var_130], rax
0x180014555  lea     rcx, [rbp+0C0h+var_E0]; this
0x180014559  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18001455e  mov     r13, rax
0x180014561  lea     rax, [rbp+0C0h+var_D0]
0x180014565  mov     [rbp+0C0h+var_128], rax
0x180014569  lea     rcx, [rbp+0C0h+var_D0]; this
0x18001456d  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180014572  mov     r12, rax
0x180014575  lea     rax, [rbp+0C0h+var_C0]
0x180014579  mov     [rbp+0C0h+var_120], rax
0x18001457d  lea     rcx, [rbp+0C0h+var_C0]; this
0x180014581  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180014586  mov     r15, rax
0x180014589  lea     rax, [rbp+0C0h+var_B0]
0x18001458d  mov     [rbp+0C0h+var_118], rax
0x180014591  lea     rcx, [rbp+0C0h+var_B0]; this
0x180014595  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18001459a  mov     r14, rax
0x18001459d  lea     rax, [rbp+0C0h+var_A0]
0x1800145a1  mov     [rbp+0C0h+var_110], rax
0x1800145a5  lea     rcx, [rbp+0C0h+var_A0]; this
0x1800145a9  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800145ae  mov     rsi, rax
0x1800145b1  lea     rax, [rbp+0C0h+var_90]
0x1800145b5  mov     [rbp+0C0h+var_108], rax
0x1800145b9  lea     rcx, [rbp+0C0h+var_90]; this
0x1800145bd  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800145c2  mov     rdi, rax
0x1800145c5  lea     rax, [rbp+0C0h+var_80]
0x1800145c9  mov     [rbp+0C0h+var_100], rax
0x1800145cd  lea     rcx, [rbp+0C0h+var_80]; this
0x1800145d1  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800145d6  mov     rbx, rax
0x1800145d9  lea     rax, [rbp+0C0h+var_70]
0x1800145dd  mov     [rbp+0C0h+var_F8], rax
0x1800145e1  lea     rcx, [rbp+0C0h+var_70]; this
0x1800145e5  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800145ea  nop
0x1800145eb  mov     edx, 2
0x1800145f0  mov     rcx, [rbp+0C0h+arg_18]
0x1800145f7  mov     [rsp+60h], rcx
0x1800145fc  mov     rcx, qword ptr [rsp+1C0h+var_150]
0x180014601  mov     [rsp+1C0h+var_168], rcx
0x180014606  mov     [rsp+1C0h+var_170], r13
0x18001460b  mov     [rsp+1C0h+var_178], r12
0x180014610  mov     [rsp+1C0h+var_180], r15
0x180014615  mov     [rsp+1C0h+var_188], r14
0x18001461a  mov     [rsp+1C0h+var_190], rsi
0x18001461f  mov     [rsp+1C0h+var_198], rdi
0x180014624  mov     [rsp+1C0h+var_1A0], rbx
0x180014629  mov     r9, rax
0x18001462c  lea     r8, WBEM_MC_WBEM_REPOSITORY_STARTING_RECOVERY
0x180014633  mov     rbx, [rsp+1C0h+var_148]
0x180014638  mov     rcx, rbx
0x18001463b  call    cs:__imp_?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z; CEventLog::Report(ushort,_EVENT_DESCRIPTOR const &,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString)
0x180014641  jmp     short loc_180014648
0x180014643  mov     rbx, [rsp+1C0h+var_148]
0x180014648  mov     [rsp+1C0h+var_150], 0
0x180014650  lea     r9, [rsp+1C0h+var_150]; int *
0x180014655  mov     r8d, [rbp+0C0h+arg_10]; int
0x18001465c  mov     rdx, [rbp+0C0h+arg_8]; unsigned __int16 *
0x180014663  mov     rcx, [rbp+0C0h+arg_0]; this
0x18001466a  call    ?RestoreHelper@CWbemBackupRestore@@IEAAJPEBGJAEAH@Z; CWbemBackupRestore::RestoreHelper(ushort const *,long,int &)
0x18001466f  mov     edi, eax
0x180014671  mov     dword ptr [rbp+0C0h+arg_18], eax
0x180014677  test    rbx, rbx
0x18001467a  jz      loc_1800148C7
0x180014680  cmp     [rsp+1C0h+var_150], 0
0x180014685  jnz     loc_1800148B4
0x18001468b  test    eax, eax
0x18001468d  js      loc_180014782
0x180014693  lea     rax, [rbp+0C0h+var_70]
0x180014697  mov     [rbp+0C0h+var_F8], rax
0x18001469b  lea     rcx, [rbp+0C0h+var_70]; this
0x18001469f  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800146a4  mov     qword ptr [rsp+1C0h+var_150], rax
0x1800146a9  lea     rax, [rbp+0C0h+var_80]
0x1800146ad  mov     [rbp+0C0h+var_100], rax
0x1800146b1  lea     rcx, [rbp+0C0h+var_80]; this
0x1800146b5  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800146ba  mov     [rbp+0C0h+var_140], rax
0x1800146be  lea     rax, [rbp+0C0h+var_90]
0x1800146c2  mov     [rbp+0C0h+var_108], rax
0x1800146c6  lea     rcx, [rbp+0C0h+var_90]; this
0x1800146ca  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800146cf  mov     r13, rax
0x1800146d2  lea     rax, [rbp+0C0h+var_A0]
0x1800146d6  mov     [rbp+0C0h+var_110], rax
0x1800146da  lea     rcx, [rbp+0C0h+var_A0]; this
0x1800146de  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800146e3  mov     r12, rax
0x1800146e6  lea     rax, [rbp+0C0h+var_B0]
0x1800146ea  mov     [rbp+0C0h+var_118], rax
0x1800146ee  lea     rcx, [rbp+0C0h+var_B0]; this
0x1800146f2  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800146f7  mov     r15, rax
0x1800146fa  lea     rax, [rbp+0C0h+var_C0]
0x1800146fe  mov     [rbp+0C0h+var_120], rax
0x180014702  lea     rcx, [rbp+0C0h+var_C0]; this
0x180014706  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18001470b  mov     r14, rax
0x18001470e  lea     rax, [rbp+0C0h+var_D0]
0x180014712  mov     [rbp+0C0h+var_128], rax
0x180014716  lea     rcx, [rbp+0C0h+var_D0]; this
0x18001471a  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18001471f  mov     rsi, rax
0x180014722  lea     rax, [rbp+0C0h+var_E0]
0x180014726  mov     [rbp+0C0h+var_130], rax
0x18001472a  lea     rcx, [rbp+0C0h+var_E0]; this
0x18001472e  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180014733  mov     rdi, rax
0x180014736  lea     rax, [rbp+0C0h+var_F0]
0x18001473a  mov     [rbp+0C0h+var_138], rax
0x18001473e  lea     rcx, [rbp+0C0h+var_F0]; this
0x180014742  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180014747  mov     rbx, rax
0x18001474a  lea     rax, [rbp+0C0h+var_50]
0x18001474e  mov     [rbp+0C0h+var_60], rax
0x180014752  mov     rdx, [rbp+0C0h+arg_8]; unsigned __int16 *
0x180014759  lea     rcx, [rbp+0C0h+var_50]; this
0x18001475d  call    ??0CInsertionString@@QEAA@PEBG@Z; CInsertionString::CInsertionString(ushort const *)
0x180014762  nop
0x180014763  mov     edx, 2
0x180014768  mov     rcx, qword ptr [rsp+1C0h+var_150]
0x18001476d  mov     [rsp+60h], rcx
0x180014772  mov     rcx, [rbp+0C0h+var_140]
0x180014776  lea     r8, WBEM_MC_WBEM_REPOSITORY_BACKUP_RESTORED
0x18001477d  jmp     loc_180014873
0x180014782  lea     rax, [rbp+0C0h+var_50]
0x180014786  mov     [rbp+0C0h+var_60], rax
0x18001478a  lea     rcx, [rbp+0C0h+var_50]; this
0x18001478e  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180014793  mov     [rbp+0C0h+var_140], rax
0x180014797  lea     rax, [rbp+0C0h+var_70]
0x18001479b  mov     [rbp+0C0h+var_F8], rax
0x18001479f  lea     rcx, [rbp+0C0h+var_70]; this
0x1800147a3  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800147a8  mov     qword ptr [rsp+1C0h+var_150], rax
0x1800147ad  lea     rax, [rbp+0C0h+var_80]
0x1800147b1  mov     [rbp+0C0h+var_100], rax
0x1800147b5  lea     rcx, [rbp+0C0h+var_80]; this
0x1800147b9  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800147be  mov     r13, rax
0x1800147c1  lea     rax, [rbp+0C0h+var_90]
0x1800147c5  mov     [rbp+0C0h+var_108], rax
0x1800147c9  lea     rcx, [rbp+0C0h+var_90]; this
0x1800147cd  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800147d2  mov     r12, rax
0x1800147d5  lea     rax, [rbp+0C0h+var_A0]
0x1800147d9  mov     [rbp+0C0h+var_110], rax
0x1800147dd  lea     rcx, [rbp+0C0h+var_A0]; this
0x1800147e1  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800147e6  mov     r15, rax
0x1800147e9  lea     rax, [rbp+0C0h+var_B0]
0x1800147ed  mov     [rbp+0C0h+var_118], rax
0x1800147f1  lea     rcx, [rbp+0C0h+var_B0]; this
0x1800147f5  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800147fa  mov     r14, rax
0x1800147fd  lea     rax, [rbp+0C0h+var_C0]
0x180014801  mov     [rbp+0C0h+var_120], rax
0x180014805  lea     rcx, [rbp+0C0h+var_C0]; this
0x180014809  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18001480e  mov     rsi, rax
0x180014811  lea     rax, [rbp+0C0h+var_D0]
0x180014815  mov     [rbp+0C0h+var_128], rax
0x180014819  lea     rcx, [rbp+0C0h+var_D0]; this
0x18001481d  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180014822  mov     rdi, rax
0x180014825  lea     rax, [rbp+0C0h+var_E0]
0x180014829  mov     [rbp+0C0h+var_130], rax
0x18001482d  mov     edx, dword ptr [rbp+0C0h+arg_18]
0x180014833  lea     rcx, [rbp+0C0h+var_E0]
0x180014837  call    cs:__imp_??0CInsertionString@@QEAA@J@Z; CInsertionString::CInsertionString(long)
0x18001483d  mov     rbx, rax
0x180014840  lea     rax, [rbp+0C0h+var_F0]
0x180014844  mov     [rbp+0C0h+var_138], rax
0x180014848  mov     rdx, [rbp+0C0h+arg_8]; unsigned __int16 *
0x18001484f  lea     rcx, [rbp+0C0h+var_F0]; this
0x180014853  call    ??0CInsertionString@@QEAA@PEBG@Z; CInsertionString::CInsertionString(ushort const *)
0x180014858  nop
0x180014859  mov     edx, 1
0x18001485e  mov     rcx, [rbp+0C0h+var_140]
0x180014862  mov     [rsp+60h], rcx
0x180014867  mov     rcx, qword ptr [rsp+1C0h+var_150]
0x18001486c  lea     r8, WBEM_MC_WBEM_REPOSITORY_BACKUP_RESTORE_FAILURE
0x180014873  mov     [rsp+1C0h+var_168], rcx
0x180014878  mov     [rsp+1C0h+var_170], r13
0x18001487d  mov     [rsp+1C0h+var_178], r12
0x180014882  mov     [rsp+1C0h+var_180], r15
0x180014887  mov     [rsp+1C0h+var_188], r14
0x18001488c  mov     [rsp+1C0h+var_190], rsi
0x180014891  mov     [rsp+1C0h+var_198], rdi
0x180014896  mov     [rsp+1C0h+var_1A0], rbx
0x18001489b  mov     r9, rax
0x18001489e  mov     rcx, [rsp+1C0h+var_148]
0x1800148a3  call    cs:__imp_?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z; CEventLog::Report(ushort,_EVENT_DESCRIPTOR const &,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString)
0x1800148a9  mov     edi, dword ptr [rbp+0C0h+arg_18]
0x1800148af  mov     rbx, [rsp+1C0h+var_148]
0x1800148b4  mov     rcx, rbx
0x1800148b7  call    cs:__imp_?Close@CEventLog@@QEAAHXZ; CEventLog::Close(void)
0x1800148bd  mov     rcx, [rsp+1C0h+var_148]; this
0x1800148c2  call    ??_GCEventLog@@QEAAPEAXI@Z; CEventLog::`scalar deleting destructor'(uint)
0x1800148c7  mov     eax, edi
0x1800148c9  add     rsp, 188h
0x1800148d0  pop     r15
0x1800148d2  pop     r14
0x1800148d4  pop     r13
0x1800148d6  pop     r12
0x1800148d8  pop     rdi
0x1800148d9  pop     rsi
0x1800148da  pop     rbx
0x1800148db  pop     rbp
0x1800148dc  retn
```
